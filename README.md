# ggplot2 nba themes, scales, and geoms

This package contains ggplot2 themes, scales, and geoms, for all 30 NBA teams. All of the code included in this package was taken directly from Ricardo Bion's [ggtech package](https://github.com/ricardo-bion/ggtech/) and modified for use with NBA team colors and logos. 

### Install ggnba:




```r
devtools::install_github("spirgel/ggnba", 
                          dependencies=TRUE)
```

### Use ggnba


```r
library(ggnba)
library(tidyverse)

d <- diamonds %>% 
  filter(color == "G" | color == "H" |
           color == "I" | color == "J") %>% 
  ggplot(aes(x = carat, fill = color)) +
  geom_histogram(color = "black")
```


```r
d + theme_nba("heat") +
  scale_fill_nba("heat") +
  labs(title = "Miami Heat theme")
```

![](README_files/figure-html/heat_theme-1.png)<!-- -->


```r
d + theme_nba("grizzlies") +
  scale_fill_nba("grizzlies") +
  labs(title = "Memphis Grizzlies theme")
```

![](README_files/figure-html/grizzlies_theme-1.png)<!-- -->


```r
d + theme_nba("kings") +
  scale_fill_nba("kings") +
  labs(title = "Sacramento Kings theme")
```

![](README_files/figure-html/kings_theme-1.png)<!-- -->

As mentioned, the code for this package was modified from Ricardo Bion's ggtech package. His `geom_tech` was inspired by [emoGG](https://github.com/dill/emoGG), thus, so is `geom_nba`.


```r
d2 <- data.frame(x = c(1:4, 3:1), y=1:7)
```


```r
ggplot(d2, aes(x = x, y = y)) + 
  geom_nba(size=0.25, theme = "heat") + 
  theme_nba("heat") +
  ggtitle("Miami Heat geom")
```

![](README_files/figure-html/heat_geom-1.png)<!-- -->


```r
ggplot(d2, aes(x = x, y = y)) + 
  geom_nba(size=0.25, theme = "grizzlies") + 
  theme_nba("grizzlies") +
  ggtitle("Memphis Grizzlies geom")
```

![](README_files/figure-html/grizzlies_geom-1.png)<!-- -->


```r
ggplot(d2, aes(x = x, y = y)) + 
  geom_nba(size=0.25, theme = "kings") + 
  theme_nba("kings") +
  ggtitle("Sacramento Kings geom")
```

![](README_files/figure-html/kings_geom-1.png)<!-- -->
