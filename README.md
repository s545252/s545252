### Hi there 👋 I'm Madhu
- 🔭 I’m currently working on WebApps.
- 🌱 I’m currently learning masters in Northwest Missouri State University
- 👯 I’m looking to collaborate on Programming and Devops
- 🤔 I’m looking for help with Programming.
- 💬 Ask me about 
- 📫 How to reach me: s545252@nwmissouri.com

# assignment02-dulugunti

## Madhumitha Reddy Dulugunti
###### OIA
#### OIA has inspired **artists**, __poets__ and every visitor who visits Santorini. Oia is best known for breathtaking sunsets; if truth be told, sunrise in Oia is also magical. In Oia there are two types of dwellings, the cave houses dug into the volcanic rock on the Caldera cliffs, and the Captains houses. 

---
## Summer Trip

1. Directions from Maryville city to Los Angeles
    1. With car drive should go through Oklahoma city for 8 hours from start place.
    2. After overnight stay drive to kingman city for next 5 hours.
    3. Stay upnight and start to Los Angeles for about 6 hours for destination.

2. My favourite places to visit in Los Angeles are
    1. Universal Studios Hollywood
    2. Disneyland Resort
    3. Santa Monica

* Novels
* Travel cards
    * UNO
    * Business Cards

[AboutMe](https://github.com/s545252/assignment02-dulugunti/blob/main/AboutMe.md)

---
# My Favourite Food/Drinks

The following table shows the list of my favourite food/drinks at location available.

| **Food/drinks**          | **Location** | **Cost(dollar)**|
|:----------------:| :------------: | :------: |
| Shrimps Biryani   | Hyderabad | 10 |
| Frankies | Hyderbad | 4 |
| Hazeelnut thikshake| Karimnagar | 5|
|Shawharma | Karimnagar | 6 |

---

# Quotes:
> Believe in you and the rest will too. - *Madhu*

> Everything in the world is hyped. Don't fall for it and live your life a certain way to prove a point that doesn't exist. - *Manasa*

----
# Code Fencing
## Dynamic programming

Dynamic programming is both a mathematical optimization method and a computer programming method. The method was developed by Richard Bellman in the 1950s and has found applications in numerous fields, from aerospace engineering to economics.
Given an quick-link to the source <https://en.wikipedia.org/wiki/Dynamic_programming>

```
int m, n;
vector<long long> dp_before(n), dp_cur(n);

long long C(int i, int j);

// compute dp_cur[l], ... dp_cur[r] (inclusive)
void compute(int l, int r, int optl, int optr) {
    if (l > r)
        return;

    int mid = (l + r) >> 1;
    pair<long long, int> best = {LLONG_MAX, -1};

    for (int k = optl; k <= min(mid, optr); k++) {
        best = min(best, {(k ? dp_before[k - 1] : 0) + C(k, mid), k});
    }

    dp_cur[mid] = best.first;
    int opt = best.second;

    compute(l, mid - 1, optl, opt);
    compute(mid + 1, r, opt, optr);
}

int solve() {
    for (int i = 0; i < n; i++)
        dp_before[i] = C(0, i);

    for (int i = 1; i < m; i++) {
        compute(0, n - 1, 0, n - 1);
        dp_before = dp_cur;
    }

    return dp_before[n - 1];
}
```

<https://cp-algorithms.com/dynamic_programming/divide-and-conquer-dp.html>
