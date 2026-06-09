# Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderGridList::AttachRenderer

- ea: `0xd00a0`
- end: `0xd0add`
- name: `Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderGridList::AttachRenderer`
- size: `2621`
- prototype: ``
- caller_count: `9`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xcd570`
- `0xcfa60`
- `0xcfa90`
- `0xcfd80`
- `0xcfdb0`
- `0xcfdf0`
- `0xd2540`
- `0xd7290`
- `0xd7480`

## callees

- `0xcd850`
- `0xd0010`
- `0xd00a0`
- `0xd0ae0`
- `0xd0b40`
- `0xd0c10`
- `0xd0c30`
- `0xd9750`
- `0xd9770`
- `0xd97b0`
- `0xdaca0`
- `0xde340`
- `0xf0f70`

## string_xrefs

- `0xd05e4`: `Crm.EmailTemplateGlobal`
- `0xd0677`: `Crm.SolutionComponentIcon`
- `0xd0734`: `Crm.ServiceTimeCode`
- `0xd08d8`: `Crm.Fieldlink`
- `0xd0941`: `Crm.PropertiesConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0xd00a0  ldarg.1
0xd00a1  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnUIInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column::get_UIInfo()
0xd00a6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnUIInfo::get_RendererType()
0xd00ab  stloc.1
0xd00ac  ldloc.1
0xd00ad  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0xd00b2  stloc.2
0xd00b3  ldloc.2
0xd00b4  ldc.i4   0x94861273
0xd00b9  bgt.un   loc_D02D4
0xd00be  ldloc.2
0xd00bf  ldc.i4   0x509E8E52
0xd00c4  bgt.un   loc_D01C1
0xd00c9  ldloc.2
0xd00ca  ldc.i4   0x2CE0F1C1
0xd00cf  bgt.un.s loc_D013D
0xd00d1  ldloc.2
0xd00d2  ldc.i4   0x1BE34ABF
0xd00d7  bgt.un.s loc_D00FF
0xd00d9  ldloc.2
0xd00da  ldc.i4   0xC79A529
0xd00df  beq      loc_D0901
0xd00e4  ldloc.2
0xd00e5  ldc.i4   0x12860A02
0xd00ea  beq      loc_D0748
0xd00ef  ldloc.2
0xd00f0  ldc.i4   0x1BE34ABF
0xd00f5  beq      loc_D064C
0xd00fa  br       loc_D09D7
0xd00ff  ldloc.2
0xd0100  ldc.i4   0x268E6BB4
0xd0105  bgt.un.s loc_D0122
0xd0107  ldloc.2
0xd0108  ldc.i4   0x223B3F22
0xd010d  beq      loc_D071E
0xd0112  ldloc.2
0xd0113  ldc.i4   0x268E6BB4
0xd0118  beq      loc_D0805
0xd011d  br       loc_D09D7
0xd0122  ldloc.2
0xd0123  ldc.i4   0x289BFCA8
0xd0128  beq      loc_D04FC
0xd012d  ldloc.2
0xd012e  ldc.i4   0x2CE0F1C1
0xd0133  beq      loc_D0844
0xd0138  br       loc_D09D7
0xd013d  ldloc.2
0xd013e  ldc.i4   0x3D18E2A9
0xd0143  bgt.un.s loc_D0183
0xd0145  ldloc.2
0xd0146  ldc.i4   0x37F9F65B
0xd014b  bgt.un.s loc_D0168
0xd014d  ldloc.2
0xd014e  ldc.i4   0x338A76EF
0xd0153  beq      loc_D04E7
0xd0158  ldloc.2
0xd0159  ldc.i4   0x37F9F65B
0xd015e  beq      loc_D068B
0xd0163  br       loc_D09D7
0xd0168  ldloc.2
0xd0169  ldc.i4   0x3902F19C
0xd016e  beq      loc_D0622
0xd0173  ldloc.2
0xd0174  ldc.i4   0x3D18E2A9
0xd0179  beq      loc_D08D7
0xd017e  br       loc_D09D7
0xd0183  ldloc.2
0xd0184  ldc.i4   0x4143A71A
0xd0189  bgt.un.s loc_D01A6
0xd018b  ldloc.2
0xd018c  ldc.i4   0x3DF5F53A
0xd0191  beq      loc_D05B9
0xd0196  ldloc.2
0xd0197  ldc.i4   0x4143A71A
0xd019c  beq      loc_D05F8
0xd01a1  br       loc_D09D7
0xd01a6  ldloc.2
0xd01a7  ldc.i4   0x42C403C1
0xd01ac  beq      loc_D0970
0xd01b1  ldloc.2
0xd01b2  ldc.i4   0x509E8E52
0xd01b7  beq      loc_D0772
0xd01bc  br       loc_D09D7
0xd01c1  ldloc.2
0xd01c2  ldc.i4   0x7E0C3808
0xd01c7  bgt.un   loc_D0250
0xd01cc  ldloc.2
0xd01cd  ldc.i4   0x7415F11E
0xd01d2  bgt.un.s loc_D0212
0xd01d4  ldloc.2
0xd01d5  ldc.i4   0x65BAC4B6
0xd01da  bgt.un.s loc_D01F7
0xd01dc  ldloc.2
0xd01dd  ldc.i4   0x51285C5E
0xd01e2  beq      loc_D06CA
0xd01e7  ldloc.2
0xd01e8  ldc.i4   0x65BAC4B6
0xd01ed  beq      loc_D0733
0xd01f2  br       loc_D09D7
0xd01f7  ldloc.2
0xd01f8  ldc.i4   0x685506C9
0xd01fd  beq      loc_D075D
0xd0202  ldloc.2
0xd0203  ldc.i4   0x7415F11E
0xd0208  beq      loc_D058F
0xd020d  br       loc_D09D7
0xd0212  ldloc.2
0xd0213  ldc.i4   0x793654D4
0xd0218  bgt.un.s loc_D0235
0xd021a  ldloc.2
0xd021b  ldc.i4   0x7858D554
0xd0220  beq      loc_D08C2
0xd0225  ldloc.2
0xd0226  ldc.i4   0x793654D4
0xd022b  beq      loc_D0961
0xd0230  br       loc_D09D7
0xd0235  ldloc.2
0xd0236  ldc.i4   0x7A62636C
0xd023b  beq      loc_D07F0
0xd0240  ldloc.2
0xd0241  ldc.i4   0x7E0C3808
0xd0246  beq      loc_D0637
0xd024b  br       loc_D09D7
0xd0250  ldloc.2
0xd0251  ldc.i4   0x8AB0F193
0xd0256  bgt.un.s loc_D0296
0xd0258  ldloc.2
0xd0259  ldc.i4   0x84990BCB
0xd025e  bgt.un.s loc_D027B
0xd0260  ldloc.2
0xd0261  ldc.i4   0x823B4DBF
0xd0266  beq      loc_D092B
0xd026b  ldloc.2
0xd026c  ldc.i4   0x84990BCB
0xd0271  beq      loc_D0787
0xd0276  br       loc_D09D7
0xd027b  ldloc.2
0xd027c  ldc.i4   0x8779951C
0xd0281  beq      loc_D06B5
0xd0286  ldloc.2
0xd0287  ldc.i4   0x8AB0F193
0xd028c  beq      loc_D0709
0xd0291  br       loc_D09D7
0xd0296  ldloc.2
0xd0297  ldc.i4   0x8B9FE088
0xd029c  bgt.un.s loc_D02B9
0xd029e  ldloc.2
0xd029f  ldc.i4   0x8B67E985
0xd02a4  beq      loc_D08AD
0xd02a9  ldloc.2
0xd02aa  ldc.i4   0x8B9FE088
0xd02af  beq      loc_D05A4
0xd02b4  br       loc_D09D7
0xd02b9  ldloc.2
0xd02ba  ldc.i4   0x92571DFB
0xd02bf  beq      loc_D0859
0xd02c4  ldloc.2
0xd02c5  ldc.i4   0x94861273
0xd02ca  beq      loc_D057A
0xd02cf  br       loc_D09D7
0xd02d4  ldloc.2
0xd02d5  ldc.i4   0xD1631704
0xd02da  bgt.un   loc_D03D7
0xd02df  ldloc.2
0xd02e0  ldc.i4   0xB5B932E6
0xd02e5  bgt.un.s loc_D0353
0xd02e7  ldloc.2
0xd02e8  ldc.i4   0xA311790F
0xd02ed  bgt.un.s loc_D0315
0xd02ef  ldloc.2
0xd02f0  ldc.i4   0x94C356FA
0xd02f5  beq      loc_D0883
0xd02fa  ldloc.2
0xd02fb  ldc.i4   0x95241A3A
0xd0300  beq      loc_D05CE
0xd0305  ldloc.2
0xd0306  ldc.i4   0xA311790F
0xd030b  beq      loc_D097F
0xd0310  br       loc_D09D7
0xd0315  ldloc.2
0xd0316  ldc.i4   0xA9AC69EA
0xd031b  bgt.un.s loc_D0338
0xd031d  ldloc.2
0xd031e  ldc.i4   0xA4BDAA19
0xd0323  beq      loc_D053B
0xd0328  ldloc.2
0xd0329  ldc.i4   0xA9AC69EA
0xd032e  beq      loc_D0898
0xd0333  br       loc_D09D7
0xd0338  ldloc.2
0xd0339  ldc.i4   0xB39CEB7B
0xd033e  beq      loc_D079C
0xd0343  ldloc.2
0xd0344  ldc.i4   0xB5B932E6
0xd0349  beq      loc_D07C6
0xd034e  br       loc_D09D7
0xd0353  ldloc.2
0xd0354  ldc.i4   0xC40B0CF7
0xd0359  bgt.un.s loc_D0399
0xd035b  ldloc.2
0xd035c  ldc.i4   0xC1374E85
0xd0361  bgt.un.s loc_D037E
0xd0363  ldloc.2
0xd0364  ldc.i4   0xB7739FB6
0xd0369  beq      loc_D086E
0xd036e  ldloc.2
0xd036f  ldc.i4   0xC1374E85
0xd0374  beq      loc_D07DB
0xd0379  br       loc_D09D7
0xd037e  ldloc.2
0xd037f  ldc.i4   0xC1C33E1F
0xd0384  beq      loc_D0550
0xd0389  ldloc.2
0xd038a  ldc.i4   0xC40B0CF7
0xd038f  beq      loc_D06F4
0xd0394  br       loc_D09D7
0xd0399  ldloc.2
0xd039a  ldc.i4   0xC9FFBE29
0xd039f  bgt.un.s loc_D03BC
0xd03a1  ldloc.2
0xd03a2  ldc.i4   0xC5BD6133
0xd03a7  beq      loc_D0661
0xd03ac  ldloc.2
0xd03ad  ldc.i4   0xC9FFBE29
0xd03b2  beq      loc_D08EC
0xd03b7  br       loc_D09D7
0xd03bc  ldloc.2
0xd03bd  ldc.i4   0xCD5A9932
0xd03c2  beq      loc_D0676
0xd03c7  ldloc.2
0xd03c8  ldc.i4   0xD1631704
0xd03cd  beq      loc_D05E3
0xd03d2  br       loc_D09D7
0xd03d7  ldloc.2
0xd03d8  ldc.i4   0xEA514F3B
0xd03dd  bgt.un   loc_D0466
0xd03e2  ldloc.2
0xd03e3  ldc.i4   0xDFB175AD
0xd03e8  bgt.un.s loc_D0428
0xd03ea  ldloc.2
0xd03eb  ldc.i4   0xD9844140
0xd03f0  bgt.un.s loc_D040D
0xd03f2  ldloc.2
0xd03f3  ldc.i4   0xD1A1CFE0
0xd03f8  beq      loc_D0952
0xd03fd  ldloc.2
0xd03fe  ldc.i4   0xD9844140
0xd0403  beq      loc_D0565
0xd0408  br       loc_D09D7
0xd040d  ldloc.2
0xd040e  ldc.i4   0xDA35889F
0xd0413  beq      loc_D060D
0xd0418  ldloc.2
0xd0419  ldc.i4   0xDFB175AD
0xd041e  beq      loc_D099D
0xd0423  br       loc_D09D7
0xd0428  ldloc.2
0xd0429  ldc.i4   0xE2A74CD8
0xd042e  bgt.un.s loc_D044B
0xd0430  ldloc.2
0xd0431  ldc.i4   0xE22EDD70
0xd0436  beq      loc_D098E
0xd043b  ldloc.2
0xd043c  ldc.i4   0xE2A74CD8
0xd0441  beq      loc_D0916
0xd0446  br       loc_D09D7
0xd044b  ldloc.2
0xd044c  ldc.i4   0xE4BD9C3E
0xd0451  beq      loc_D082F
0xd0456  ldloc.2
0xd0457  ldc.i4   0xEA514F3B
0xd045c  beq      loc_D09AC
0xd0461  br       loc_D09D7
0xd0466  ldloc.2
0xd0467  ldc.i4   0xF6A799AF
0xd046c  bgt.un.s loc_D04AC
0xd046e  ldloc.2
0xd046f  ldc.i4   0xF4293B18
0xd0474  bgt.un.s loc_D0491
0xd0476  ldloc.2
0xd0477  ldc.i4   0xF388D5FE
0xd047c  beq      loc_D09BB
0xd0481  ldloc.2
0xd0482  ldc.i4   0xF4293B18
0xd0487  beq      loc_D06A0
0xd048c  br       loc_D09D7
0xd0491  ldloc.2
0xd0492  ldc.i4   0xF5674CD4
0xd0497  beq      loc_D0526
0xd049c  ldloc.2
0xd049d  ldc.i4   0xF6A799AF
0xd04a2  beq      loc_D07B1
0xd04a7  br       loc_D09D7
0xd04ac  ldloc.2
0xd04ad  ldc.i4   0xF758858B
0xd04b2  bgt.un.s loc_D04CC
0xd04b4  ldloc.2
0xd04b5  ldc.i4   0xF6F2376B
0xd04ba  beq      loc_D06DF
0xd04bf  ldloc.2
  ... truncated ...
```
