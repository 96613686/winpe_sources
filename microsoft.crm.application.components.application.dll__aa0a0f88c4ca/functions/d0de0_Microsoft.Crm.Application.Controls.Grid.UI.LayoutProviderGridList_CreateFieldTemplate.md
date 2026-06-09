# Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderGridList::CreateFieldTemplate

- ea: `0xd0de0`
- end: `0xd1ae2`
- name: `Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderGridList::CreateFieldTemplate`
- size: `3330`
- prototype: ``
- caller_count: `1`
- callee_count: `74`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xd0c10`

## callees

- `0xcd220`
- `0xcd240`
- `0xcd7f0`
- `0xcd830`
- `0xcd850`
- `0xd0ae0`
- `0xd0de0`
- `0xd8670`
- `0xd86c0`
- `0xd8740`
- `0xd8980`
- `0xd89a0`
- `0xd9750`
- `0xd9760`
- `0xd9770`
- `0xd9790`
- `0xd97b0`
- `0xd97f0`
- `0xdaf40`
- `0xdaff0`
- `0xdb100`
- `0xdb170`
- `0xdb1d0`
- `0xdb240`
- `0xdb320`
- `0xdb360`
- `0xdb3e0`
- `0xdb560`
- `0xdb750`
- `0xdb8c0`
- `0xdb9e0`
- `0xdbbb0`
- `0xdbc60`
- `0xdbce0`
- `0xdbd40`
- `0xdbdf0`
- `0xdbe60`
- `0xdbe80`
- `0xdc080`
- `0xdc1b0`
- `0xdc350`
- `0xdc3e0`
- `0xdc450`
- `0xdc4c0`
- `0xdc530`
- `0xdc5a0`
- `0xdc600`
- `0xdc640`
- `0xdc680`
- `0xdc6a0`

## string_xrefs

- `0xd1877`: `readonly`
- `0xd12f9`: `Crm.EmailTemplateGlobal`
- `0xd138c`: `Crm.SolutionComponentIcon`
- `0xd1434`: `Crm.ServiceTimeCode`
- `0xd151b`: `Crm.Fieldlink`
- `0xd1680`: `Crm.PropertiesConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0xd0de0  ldarg.1
0xd0de1  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnUIInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column::get_UIInfo()
0xd0de6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnUIInfo::get_RendererType()
0xd0deb  stloc.0
0xd0dec  ldarg.1
0xd0ded  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column::get_Name()
0xd0df2  stloc.1
0xd0df3  ldnull
0xd0df4  stloc.2
0xd0df5  ldarg.0
0xd0df6  call     instance bool Microsoft.Crm.Application.Controls.Grid.UI.LayoutProvider::get_IsHierarchyAware()
0xd0dfb  brtrue.s loc_D0E0C
0xd0dfd  ldloc.0
0xd0dfe  ldstr    aCrmHierarchyic// "Crm.HierarchyIcon"
0xd0e03  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd0e08  brfalse.s loc_D0E0C
0xd0e0a  ldloc.2
0xd0e0b  ret
0xd0e0c  ldloc.0
0xd0e0d  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0xd0e12  stloc.3
0xd0e13  ldloc.3
0xd0e14  ldc.i4   0x94861273
0xd0e19  bgt.un   loc_D1019
0xd0e1e  ldloc.3
0xd0e1f  ldc.i4   0x51285C5E
0xd0e24  bgt.un   loc_D0F21
0xd0e29  ldloc.3
0xd0e2a  ldc.i4   0x2CE0F1C1
0xd0e2f  bgt.un.s loc_D0E9D
0xd0e31  ldloc.3
0xd0e32  ldc.i4   0x1BE34ABF
0xd0e37  bgt.un.s loc_D0E5F
0xd0e39  ldloc.3
0xd0e3a  ldc.i4   0xC79A529
0xd0e3f  beq      loc_D1640
0xd0e44  ldloc.3
0xd0e45  ldc.i4   0x12860A02
0xd0e4a  beq      loc_D145D
0xd0e4f  ldloc.3
0xd0e50  ldc.i4   0x1BE34ABF
0xd0e55  beq      loc_D134C
0xd0e5a  br       loc_D1A38
0xd0e5f  ldloc.3
0xd0e60  ldc.i4   0x268E6BB4
0xd0e65  bgt.un.s loc_D0E82
0xd0e67  ldloc.3
0xd0e68  ldc.i4   0x223B3F22
0xd0e6d  beq      loc_D141E
0xd0e72  ldloc.3
0xd0e73  ldc.i4   0x268E6BB4
0xd0e78  beq      loc_D1544
0xd0e7d  br       loc_D1A38
0xd0e82  ldloc.3
0xd0e83  ldc.i4   0x289BFCA8
0xd0e88  beq      loc_D127A
0xd0e8d  ldloc.3
0xd0e8e  ldc.i4   0x2CE0F1C1
0xd0e93  beq      loc_D156E
0xd0e98  br       loc_D1A38
0xd0e9d  ldloc.3
0xd0e9e  ldc.i4   0x3D18E2A9
0xd0ea3  bgt.un.s loc_D0EE3
0xd0ea5  ldloc.3
0xd0ea6  ldc.i4   0x37F9F65B
0xd0eab  bgt.un.s loc_D0EC8
0xd0ead  ldloc.3
0xd0eae  ldc.i4   0x338A76EF
0xd0eb3  beq      loc_D128F
0xd0eb8  ldloc.3
0xd0eb9  ldc.i4   0x37F9F65B
0xd0ebe  beq      loc_D1376
0xd0ec3  br       loc_D1A38
0xd0ec8  ldloc.3
0xd0ec9  ldc.i4   0x3902F19C
0xd0ece  beq      loc_D1322
0xd0ed3  ldloc.3
0xd0ed4  ldc.i4   0x3D18E2A9
0xd0ed9  beq      loc_D151A
0xd0ede  br       loc_D1A38
0xd0ee3  ldloc.3
0xd0ee4  ldc.i4   0x42C403C1
0xd0ee9  bgt.un.s loc_D0F06
0xd0eeb  ldloc.3
0xd0eec  ldc.i4   0x3DF5F53A
0xd0ef1  beq      loc_D12E3
0xd0ef6  ldloc.3
0xd0ef7  ldc.i4   0x42C403C1
0xd0efc  beq      loc_D16A9
0xd0f01  br       loc_D1A38
0xd0f06  ldloc.3
0xd0f07  ldc.i4   0x509E8E52
0xd0f0c  beq      loc_D1487
0xd0f11  ldloc.3
0xd0f12  ldc.i4   0x51285C5E
0xd0f17  beq      loc_D13B5
0xd0f1c  br       loc_D1A38
0xd0f21  ldloc.3
0xd0f22  ldc.i4   0x7E0C3808
0xd0f27  bgt.un.s loc_D0F95
0xd0f29  ldloc.3
0xd0f2a  ldc.i4   0x7415F11E
0xd0f2f  bgt.un.s loc_D0F57
0xd0f31  ldloc.3
0xd0f32  ldc.i4   0x65BAC4B6
0xd0f37  beq      loc_D1433
0xd0f3c  ldloc.3
0xd0f3d  ldc.i4   0x685506C9
0xd0f42  beq      loc_D1472
0xd0f47  ldloc.3
0xd0f48  ldc.i4   0x7415F11E
0xd0f4d  beq      loc_D12B9
0xd0f52  br       loc_D1A38
0xd0f57  ldloc.3
0xd0f58  ldc.i4   0x793654D4
0xd0f5d  bgt.un.s loc_D0F7A
0xd0f5f  ldloc.3
0xd0f60  ldc.i4   0x7858D554
0xd0f65  beq      loc_D1616
0xd0f6a  ldloc.3
0xd0f6b  ldc.i4   0x793654D4
0xd0f70  beq      loc_D1694
0xd0f75  br       loc_D1A38
0xd0f7a  ldloc.3
0xd0f7b  ldc.i4   0x7A62636C
0xd0f80  beq      loc_D152F
0xd0f85  ldloc.3
0xd0f86  ldc.i4   0x7E0C3808
0xd0f8b  beq      loc_D1337
0xd0f90  br       loc_D1A38
0xd0f95  ldloc.3
0xd0f96  ldc.i4   0x8AB0F193
0xd0f9b  bgt.un.s loc_D0FDB
0xd0f9d  ldloc.3
0xd0f9e  ldc.i4   0x84990BCB
0xd0fa3  bgt.un.s loc_D0FC0
0xd0fa5  ldloc.3
0xd0fa6  ldc.i4   0x823B4DBF
0xd0fab  beq      loc_D15C2
0xd0fb0  ldloc.3
0xd0fb1  ldc.i4   0x84990BCB
0xd0fb6  beq      loc_D149C
0xd0fbb  br       loc_D1A38
0xd0fc0  ldloc.3
0xd0fc1  ldc.i4   0x8779951C
0xd0fc6  beq      loc_D13A0
0xd0fcb  ldloc.3
0xd0fcc  ldc.i4   0x8AB0F193
0xd0fd1  beq      loc_D1409
0xd0fd6  br       loc_D1A38
0xd0fdb  ldloc.3
0xd0fdc  ldc.i4   0x8B9FE088
0xd0fe1  bgt.un.s loc_D0FFE
0xd0fe3  ldloc.3
0xd0fe4  ldc.i4   0x8B67E985
0xd0fe9  beq      loc_D1601
0xd0fee  ldloc.3
0xd0fef  ldc.i4   0x8B9FE088
0xd0ff4  beq      loc_D12CE
0xd0ff9  br       loc_D1A38
0xd0ffe  ldloc.3
0xd0fff  ldc.i4   0x92571DFB
0xd1004  beq      loc_D1598
0xd1009  ldloc.3
0xd100a  ldc.i4   0x94861273
0xd100f  beq      loc_D12A4
0xd1014  br       loc_D1A38
0xd1019  ldloc.3
0xd101a  ldc.i4   0xD1631704
0xd101f  bgt.un   loc_D111C
0xd1024  ldloc.3
0xd1025  ldc.i4   0xB5B932E6
0xd102a  bgt.un.s loc_D1098
0xd102c  ldloc.3
0xd102d  ldc.i4   0xA311790F
0xd1032  bgt.un.s loc_D105A
0xd1034  ldloc.3
0xd1035  ldc.i4   0x94C356FA
0xd103a  beq      loc_D14C6
0xd103f  ldloc.3
0xd1040  ldc.i4   0x95241A3A
0xd1045  beq      loc_D1448
0xd104a  ldloc.3
0xd104b  ldc.i4   0xA311790F
0xd1050  beq      loc_D16BE
0xd1055  br       loc_D1A38
0xd105a  ldloc.3
0xd105b  ldc.i4   0xA9AC69EA
0xd1060  bgt.un.s loc_D107D
0xd1062  ldloc.3
0xd1063  ldc.i4   0xA4BDAA19
0xd1068  beq      loc_D1265
0xd106d  ldloc.3
0xd106e  ldc.i4   0xA9AC69EA
0xd1073  beq      loc_D15EC
0xd1078  br       loc_D1A38
0xd107d  ldloc.3
0xd107e  ldc.i4   0xB39CEB7B
0xd1083  beq      loc_D14B1
0xd1088  ldloc.3
0xd1089  ldc.i4   0xB5B932E6
0xd108e  beq      loc_D14F0
0xd1093  br       loc_D1A38
0xd1098  ldloc.3
0xd1099  ldc.i4   0xC40B0CF7
0xd109e  bgt.un.s loc_D10DE
0xd10a0  ldloc.3
0xd10a1  ldc.i4   0xC1374E85
0xd10a6  bgt.un.s loc_D10C3
0xd10a8  ldloc.3
0xd10a9  ldc.i4   0xB7739FB6
0xd10ae  beq      loc_D15AD
0xd10b3  ldloc.3
0xd10b4  ldc.i4   0xC1374E85
0xd10b9  beq      loc_D1505
0xd10be  br       loc_D1A38
0xd10c3  ldloc.3
0xd10c4  ldc.i4   0xC1C33E1F
0xd10c9  beq      loc_D1226
0xd10ce  ldloc.3
0xd10cf  ldc.i4   0xC40B0CF7
0xd10d4  beq      loc_D13F4
0xd10d9  br       loc_D1A38
0xd10de  ldloc.3
0xd10df  ldc.i4   0xC9FFBE29
0xd10e4  bgt.un.s loc_D1101
0xd10e6  ldloc.3
0xd10e7  ldc.i4   0xC5BD6133
0xd10ec  beq      loc_D1361
0xd10f1  ldloc.3
0xd10f2  ldc.i4   0xC9FFBE29
0xd10f7  beq      loc_D162B
0xd10fc  br       loc_D1A38
0xd1101  ldloc.3
0xd1102  ldc.i4   0xCD5A9932
0xd1107  beq      loc_D138B
0xd110c  ldloc.3
0xd110d  ldc.i4   0xD1631704
0xd1112  beq      loc_D12F8
0xd1117  br       loc_D1A38
0xd111c  ldloc.3
0xd111d  ldc.i4   0xE4BD9C3E
0xd1122  bgt.un.s loc_D1190
0xd1124  ldloc.3
0xd1125  ldc.i4   0xDA35889F
0xd112a  bgt.un.s loc_D1152
0xd112c  ldloc.3
0xd112d  ldc.i4   0xD1A1CFE0
0xd1132  beq      loc_D166A
0xd1137  ldloc.3
0xd1138  ldc.i4   0xD9844140
0xd113d  beq      loc_D1211
0xd1142  ldloc.3
0xd1143  ldc.i4   0xDA35889F
0xd1148  beq      loc_D130D
0xd114d  br       loc_D1A38
0xd1152  ldloc.3
0xd1153  ldc.i4   0xE22EDD70
0xd1158  bgt.un.s loc_D1175
0xd115a  ldloc.3
0xd115b  ldc.i4   0xDFB175AD
0xd1160  beq      loc_D16E8
0xd1165  ldloc.3
0xd1166  ldc.i4   0xE22EDD70
0xd116b  beq      loc_D16D3
0xd1170  br       loc_D1A38
0xd1175  ldloc.3
0xd1176  ldc.i4   0xE2A74CD8
0xd117b  beq      loc_D1655
0xd1180  ldloc.3
0xd1181  ldc.i4   0xE4BD9C3E
0xd1186  beq      loc_D1583
0xd118b  br       loc_D1A38
0xd1190  ldloc.3
0xd1191  ldc.i4   0xF6A799AF
0xd1196  bgt.un.s loc_D11D6
0xd1198  ldloc.3
0xd1199  ldc.i4   0xF4293B18
0xd119e  bgt.un.s loc_D11BB
0xd11a0  ldloc.3
0xd11a1  ldc.i4   0xEA514F3B
0xd11a6  beq      loc_D15D7
0xd11ab  ldloc.3
0xd11ac  ldc.i4   0xF4293B18
0xd11b1  beq      loc_D13DF
0xd11b6  br       loc_D1A38
0xd11bb  ldloc.3
0xd11bc  ldc.i4   0xF5674CD4
0xd11c1  beq      loc_D1250
0xd11c6  ldloc.3
0xd11c7  ldc.i4   0xF6A799AF
0xd11cc  beq      loc_D14DB
0xd11d1  br       loc_D1A38
0xd11d6  ldloc.3
0xd11d7  ldc.i4   0xF758858B
0xd11dc  bgt.un.s loc_D11F6
0xd11de  ldloc.3
0xd11df  ldc.i4   0xF6F2376B
0xd11e4  beq      loc_D13CA
0xd11e9  ldloc.3
  ... truncated ...
```
