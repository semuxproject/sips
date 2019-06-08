# RFP: Adjusting the Supply Curve
version 1, edited on 11 March 2019
by honeycrypto

## Abstract

This issue was initially opened by @argoncoindev here [Issue #124](https://github.com/semuxproject/semux-core/issues/124). Unlike to many other existing cryptocurrencies, Semux has a very high inflation for many years ahead. 

Here is how the supply curve looks like in current implementation. Please note that premine is excluded due to discussions about burning it in RFP-001.
![supply curve 1](https://semux.info/img/rfps/proposal-02.png)

| Year | Estimated Inflation |
|---|---|
| 2019 | 31.70% |
| 2020 | 25.07% |
| 2021 | 19.92% |
| 2022 | 16.53% |
| 2023 | 14.13% |
| 2024 | 12.34% |
| 2025 | 10.94% |
| ...  | ...   |
| 2041 | 3.17% |
| ...  | ...   |
| 2056 | 0% |

## Motivation 
Semux core developers and community of validators agreed on their vision of Semux as decentralized and scalable platform for dapps. But due to high inflation Semux became a high profitable coin for stakers and risky asset for those who want to use SEM by its primary purposes as means of payment and fuel of the network. 

Semux Community agreed that changes to supply curve are needed to protect primary users of SEM coin and to boost future dapps development. 

## Proposal by [semuxgo](https://github.com/semuxgo)
```
--------------------------
Adjust block rewards
--------------------------
block # 0  -  2m :  3 SEM / block
block # 2m -  6m :  2 SEM / block
block # 6m - 14m :  1 SEM / block
```

This proposal will lead to approx 28,2 million SEM created by 2031 (excluding the potential premine of Semux Foundation) with the 0% inflation after that. 
![supply curve 2](https://semux.info/img/rfps/proposal-01.png)

| Year | Estimated Inflation |
|---|---|
| 2019 | 31.70% |
| 2020 | 16.74% |
| 2021 | 14.28% |
| 2022 | 12.45% |
| 2023 | 11.03% |
| 2024 | 5.01% |
| 2025 | 4.76% |
| 2026 | 4.54% |
| 2027 | 4.34% |
| 2028 | 4.15% |
| 2029 | 3.98% |
| 2030 | 3.83% |
| 2031 | 3.68% |
| 2032 | 0.00% |

While in the long run this proposal will reduce the total SEM supply almost by 3 times, it's easy to see that for many years the inflation rate will stay almost as high as in existing codebase: 

| Year | Currently | New proposal |
|---|---|---|
| 2019 | 31.70% | 31.70% |
| 2020 | 25.07% | 16.74% |
| 2021 | 19.92% | 14.28% |

I think this model is not much different from existing codebase, so this won't help to move from 'super pos coin' to 'platform for dapps' in the nearest future.

## Other simulations
I've analyzed many other models with reducing block reward every block, reducing block reward every 2880 blocks (1 day), reward adjustment every 28 days and so on. Most of them lead to relatively high inflation for the next 1-3 years and further smooth drop to approx 0%. 

Here is the example of reducing block reward by 1000/1001 every 2880 blocks. Please note that it starts from ~ 2 SEM block reward immediately because we're already 400+ cycles/days away from block height 1 with 3 SEM reward. 
![supply curve 3](https://semux.info/img/rfps/proposal-04.png)

| Year | Estimated Inflation |
|---|---|
| 2019 | 21.17% |
| 2020 | 13.66% |
| 2021 | 8.48% |
| 2022 | 5.49% |
| 2023 | 3.64% |
| ... | ... |
| 2033 | 0.09% |

Conclusion: all those models don't solve the problem of high inflation for the next 3-5 years. Also at some point block reward becaming a dust. 

## Proposal-by-honeycrypto 
I've got surprisingly interesting results when simulated infinite supply with constant and low yearly inflation. Here is the example with approx 2% per year inflation. Block reward starts at 0.183876845 SEM per block and will be rising very slowly each year. By 2040 block reward will reach 0.284519616 SEM and circulating supply will rise from 10M SEM to approx 15M in 20 years.

![supply curve 4](https://semux.info/img/rfps/proposal-03.png)

| Year | Inflation |
|---|---|
| 2019 | 1.94% |
| 2020 | 1.94% |
| ... | ... |
| 2100+ | 1.94% |

In this case the block reward can be recalculated every 365 * 2880 blocks considering the existing supply. This block reward can be valid for the next window of 1,051,200 blocks (approx 1 year).

#### Main proposal considering the preparation and activation period
This is a major change, so I'd propose to give more than enough time to validators and community members to discuss it and get ready to it. We can target for a block #2,016,000 for activation of new model, this is expected to happen in December 2019 - January 2020. 

In this case we will get a higher initial supply (due to +2.5M SEM minted at 3 SEM/block reward for the rest of 2019) and slightly higher initial block reward: 

![supply curve 5](https://semux.info/img/rfps/proposal-03-a.png)

#### Some thoughts on premine and RFP-001
And finally, we can consider RFP-001 and the premine of Semux Foundation which will likely be between 3.5M SEM and 5M SEM. Here is the idea of how the supply curve will look like if we activate this proposal of max 2% per year inflation at block height #2,016,000 considering the initial supply of 17.1M coins (9.6M exists + 2.5M to be mined in 2019 + up to 5M Premine): 

![supply curve 6](https://semux.info/img/rfps/proposal-03-b.png)

| Year | Inflation |
|---|---|
| 2019 | 20.90% ** |
| 2020 | 1.94% |
| ... | ... |
| 2100+ | 1.94% |

** _it's lower than in existing codebase (31.70%) and proposal by semux (31.70%) because this time we counted also up to 5M SEM of premine in circulating supply. Obviously, this should be done in all 3 cases so in 2019 it's either 31.70% (excluding premine) or 20.90% (counting up to 5M SEM of premine)._

In this model block reward starts from 0.32 SEM per block in 2020 and it will hit 1 SEM / block in 2076. 2 SEM / block in the year 2111. 

By the year 2100 there will be approx 85 million SEM circulating. The big picture: 

![supply curve 7](https://semux.info/img/rfps/proposal-03-c.png)
