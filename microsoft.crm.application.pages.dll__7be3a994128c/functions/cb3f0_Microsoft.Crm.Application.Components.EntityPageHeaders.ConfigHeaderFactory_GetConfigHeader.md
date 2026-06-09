# Microsoft.Crm.Application.Components.EntityPageHeaders.ConfigHeaderFactory::GetConfigHeader

- ea: `0xcb3f0`
- end: `0xcb4a7`
- name: `Microsoft.Crm.Application.Components.EntityPageHeaders.ConfigHeaderFactory::GetConfigHeader`
- size: `183`
- prototype: ``
- caller_count: `8`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x27170`
- `0xcdd00`
- `0xcef30`
- `0xd1e30`
- `0xd6250`
- `0xef5c0`
- `0xfce90`
- `0xff010`

## callees

- `0xcaf20`
- `0xcaf70`
- `0xcb390`
- `0xcb3f0`
- `0xcb540`
- `0xcb590`
- `0xcb930`

## string_xrefs

- `0xcb3f0`: `Microsoft.Crm.Common.Application.Pages`
- `0xcb3f5`: `CommonConfigHeaderFactory`
- `0xcb400`: `Microsoft.Crm.Service.Application.Pages`
- `0xcb405`: `ServiceConfigHeaderFactory`
- `0xcb415`: `MarketingConfigHeaderFactory`

## pseudocode

```c

```

## disassembly

```asm
0xcb3f0  ldstr    aMicrosoftCrmCo_0// "Microsoft.Crm.Common.Application.Pages"
0xcb3f5  ldstr    aCommonconfighe// "CommonConfigHeaderFactory"
0xcb3fa  call     class Microsoft.Crm.Application.Components.EntityPageHeaders.IConfigHeaderFactory Microsoft.Crm.Application.Components.EntityPageHeaders.ConfigHeaderFactory::GetConfigHeaderFactory(string assembyName, string typeName)
0xcb3ff  stloc.0
0xcb400  ldstr    aMicrosoftCrmSe// "Microsoft.Crm.Service.Application.Pages"
0xcb405  ldstr    aServiceconfigh// "ServiceConfigHeaderFactory"
0xcb40a  call     class Microsoft.Crm.Application.Components.EntityPageHeaders.IConfigHeaderFactory Microsoft.Crm.Application.Components.EntityPageHeaders.ConfigHeaderFactory::GetConfigHeaderFactory(string assembyName, string typeName)
0xcb40f  stloc.1
0xcb410  ldstr    aMicrosoftCrmMa// "Microsoft.Crm.Marketing.Application.Pag"...
0xcb415  ldstr    aMarketingconfi// "MarketingConfigHeaderFactory"
0xcb41a  call     class Microsoft.Crm.Application.Components.EntityPageHeaders.IConfigHeaderFactory Microsoft.Crm.Application.Components.EntityPageHeaders.ConfigHeaderFactory::GetConfigHeaderFactory(string assembyName, string typeName)
0xcb41f  stloc.2
0xcb420  ldarg.0
0xcb421  ldc.i4   0x440
0xcb426  bgt.s    loc_CB43B
0xcb428  ldarg.0
0xcb429  ldc.i4.8
0xcb42a  beq.s    loc_CB49B
0xcb42c  ldarg.0
0xcb42d  ldc.i4.s 9
0xcb42f  beq.s    loc_CB48F
0xcb431  ldarg.0
0xcb432  ldc.i4   0x440
0xcb437  beq.s    loc_CB495
0xcb439  br.s     loc_CB4A1
0xcb43b  ldarg.0
0xcb43c  ldc.i4   0x1068
0xcb441  bgt.s    loc_CB455
0xcb443  ldarg.0
0xcb444  ldc.i4   0x7E4
0xcb449  beq.s    loc_CB487
0xcb44b  ldarg.0
0xcb44c  ldc.i4   0x1068
0xcb451  beq.s    loc_CB477
0xcb453  br.s     loc_CB4A1
0xcb455  ldarg.0
0xcb456  ldc.i4   0x106A
0xcb45b  beq.s    loc_CB477
0xcb45d  ldarg.0
0xcb45e  ldc.i4   0x1130
0xcb463  sub
0xcb464  switch   loc_CB47F, loc_CB47F, loc_CB47F
0xcb475  br.s     loc_CB4A1
0xcb477  ldloc.0
0xcb478  ldarg.0
0xcb479  callvirt instance class Microsoft.Crm.Application.Components.EntityPageHeaders.IConfigHeader Microsoft.Crm.Application.Components.EntityPageHeaders.IConfigHeaderFactory::RetrieveConfigHeader(int32 typeCode)
0xcb47e  ret
0xcb47f  ldloc.2
0xcb480  ldarg.0
0xcb481  callvirt instance class Microsoft.Crm.Application.Components.EntityPageHeaders.IConfigHeader Microsoft.Crm.Application.Components.EntityPageHeaders.IConfigHeaderFactory::RetrieveConfigHeader(int32 typeCode)
0xcb486  ret
0xcb487  ldloc.1
0xcb488  ldarg.0
0xcb489  callvirt instance class Microsoft.Crm.Application.Components.EntityPageHeaders.IConfigHeader Microsoft.Crm.Application.Components.EntityPageHeaders.IConfigHeaderFactory::RetrieveConfigHeader(int32 typeCode)
0xcb48e  ret
0xcb48f  newobj   instance void Microsoft.Crm.Application.Components.EntityPageHeaders.TeamConfigHeader::.ctor()
0xcb494  ret
0xcb495  newobj   instance void Microsoft.Crm.Application.Components.EntityPageHeaders.SalesOrderConfigHeader::.ctor()
0xcb49a  ret
0xcb49b  newobj   instance void Microsoft.Crm.Application.Components.EntityPageHeaders.SystemUserConfigHeader::.ctor()
0xcb4a0  ret
0xcb4a1  newobj   instance void Microsoft.Crm.Application.Components.EntityPageHeaders.ConfigHeaderBase::.ctor()
0xcb4a6  ret
```
