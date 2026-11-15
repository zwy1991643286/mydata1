# data-code/data — v17 论文所用数据清单

> 2026-11-15 整理。与 `data-code/final_v17_code/` 的 25 个 do 文件一一对应。
> 全部为**复制**（原件仍在 data/ 与 output/gini_rerun/，未动）。

## 一、原始数据（10 个，复制自 data/，供第一节 3 个构造 do 使用）

| 文件 | 大小 | 使用者 | 内容 |
|---|---|---|---|
| `hvgv.dta` | 78 MB | 20 | 家庭追踪调查源数据（家庭面板上游） |
| `中国各县域城乡居民收入（2000-2022年）.xlsx` | 1.6 MB | 30 | 县级收入三口径（可支配/纯收入/衔接序列） |
| `county_t_new.dta` | 17 MB | 30、37 | 示范县处理变量（cid year did id、stdlgt） |
| `1999~2023年县市社会经济指标.dta` | 28 MB | 30、39、39b、39c | 县级控制变量（lnagdp/lnpop/lnfis 等）+ 二三产业从业人员 |
| `北京大学数字普惠金融指数（PKU-DFIIC）2011_2023.xlsx` | 6.9 MB | 36、41、r41perm | DFI 及分维度（覆盖广度/深度/数字化） |
| `中国乡村创新创业指数（2022版）.xlsx` | 1.3 MB | 36、41、r41perm | IEI 县级（sheet"3-县级"） |
| `创业活力.dta` | 7.4 MB | 39d、41、r41perm | 企业注册（lnentrepr） |
| `1998～2023年中国城市统计年鉴地级市面板数据.dta` | 19 MB | 41b | 地级市就业（表5 列5-6） |
| `county_nightlight_gini_panel.dta` | 46 MB | 37 | 夜间灯光不平等面板（附录基尼） |
| `电子商务进农村DID数据.xlsx` | 1.7 MB | 46、46b | 2019—2021 新批示范县名单（表4 扩展定义） |

## 二、中间面板（3 个，复制自 output/gini_rerun/，第二、三、四节分析文件直接读取）

| 文件 | 大小 | 产出 | 使用者 |
|---|---|---|---|
| `county_income_panel.dta` | 11 MB | 30 | 41/41c/46/46b/re41/r41 系列/48/51/31/32/37/39/39d/41b |
| `hh_income.dta` | 90 MB | 20 | 37、41、41c、r41hh、r41t5 |
| `county_income_mech.dta` | 13 MB | 36 | 37（家庭分来源机制） |

## 三、说明

- `_perm_results.dta`、`_hh_rank3.dta` 是 do 文件运行中**自建自删**的临时文件（postfile→use→erase），无需存档。
- do 文件内的路径是绝对全局（`$PROJ/data`、`$OUT=output/gini_rerun`）。本文件夹用于**归档与整体拷贝**；如需在本目录下直接重跑，需把各 do 文件的 `global DATA/OUT/PROJ` 改指到 `data-code/` 相应位置（或按 data-code/data 与 output 的相对结构重建目录）。
- 校验：13 个文件复制后与源文件字节数逐一一致（cp -p 保留时间戳）。
