# Mint Marketcap
A stats website that tries to guess how much money bitcoiners store on ecash mints

# What is Mint Marketcap?
While arguing with a monero person recently, I wondered if cashu mints are already more popular than monero. On monero, there's a public blockchain where I can count the number of transactions per day, but I'm not sure of a good way to get a similar tx count for cashu mints. But I thought of one thing:

I can get the \*marketcap\* of monero easily from many different websites, and, while cashu can't really \*have\* a marketcap, I \*did\* think of something that's \*kind of\* similar: how much money is stored in cashu mints. To estimate that I came up with this website.

# How to try it
Just click here: https://supertestnet.github.io/mint_marketcap/

# What it does
It queries every cashu mint for an invoice, extracts their pubkey from the invoice, and queries amboss to find out the public capacity of that mint. Then I assume the channels are roughly 50/50 balanced, which means half of that money is on the mint's side and is therefore custodied by the mint.

Voila! That tells me how close cashu is to overtaking monero. It's probably not very \*good\* data, but it \*is\* data.

# Why do you say this data probably isn't very good?
I'm basically guessing right now, especially about these two items: (1) the mint's only channels are their publicly listed ones (2) all of their channels are, on average, 50/50 balanced

I'm not sure how likely those things are to be way off. They are probably way off due to reasons I can't think of, but as for #1, my intuition tells me that their channels are *almost* all public because people who are considering opening a channel to a mint have an incentive to make it public: you make money if people use it, and they can't use it if they don't know about it.

But some people might open a private channel anyway if they are just looking for a peer with good connections and don't want all their liquidity to be used up by people trying to get into the mint. So that could throw #1 off.

As for #2, well, I suppose that one probably *is* way off. I suspect mints are "liquidity sinks," similar to exchanges. They are probably constantly seeking more inbound capacity as more people try to get "in" than "out." So they might be very imbalanced, it might even be like 80/20 rather than 50/50, which -- if true -- would probably bump up the number I want to see grow. But I don't want to sway from 50/50 just based on a hunch; I'd rather do it for data-backed reasons. Can anyone think of a data-based way to estimate how much liquidity in a mint's channels is likely to be on the mint's side?

Also, the mint might use its lightning node for additional purposes beyond just custodying other people's money, so it is likely that the overall balance of "money stored on a cashu mint" is lower than the amount I estimate from each mint's public capacity. So yeah, the numbers probably aren't very good, but it's the best I can think of right now.
