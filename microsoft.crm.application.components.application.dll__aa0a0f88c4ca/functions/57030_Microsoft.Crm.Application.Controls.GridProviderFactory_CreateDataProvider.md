# Microsoft.Crm.Application.Controls.GridProviderFactory::CreateDataProvider

- ea: `0x57030`
- end: `0x57b66`
- name: `Microsoft.Crm.Application.Controls.GridProviderFactory::CreateDataProvider`
- size: `2870`
- prototype: ``
- caller_count: `0`
- callee_count: `60`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x51900`
- `0x542b0`
- `0x54510`
- `0x54610`
- `0x54630`
- `0x57030`
- `0x57c80`
- `0x57d00`
- `0x590b0`
- `0x59a20`
- `0x59c10`
- `0x59d50`
- `0x59e70`
- `0x59e90`
- `0x59fb0`
- `0x59fd0`
- `0x5a9c0`
- `0x5aa30`
- `0x5afb0`
- `0x5b200`
- `0x5b5d0`
- `0x5b7a0`
- `0x5b820`
- `0x5b960`
- `0x5c160`
- `0x5c7e0`
- `0x5c900`
- `0x5c920`
- `0x5d520`
- `0x5d5f0`
- `0x5d710`
- `0x5d7c0`
- `0xb6740`
- `0xb6dc0`
- `0xb6ff0`
- `0xb7f70`
- `0xb8570`
- `0xbb810`
- `0xbf000`
- `0xbf550`
- `0xbfe70`
- `0xc0470`
- `0xc0830`
- `0xc0ad0`
- `0xc4060`
- `0xc4a30`
- `0xc4dc0`
- `0xc5080`
- `0xc5650`
- `0xc5ee0`

## string_xrefs

- `0x57047`: `Microsoft.Crm.Application.Components.Application`
- `0x5703a`: `Attempting to load the crm application grid data provider.  Assembly : {0} Class : {1}`
- `0x57543`: `Microsoft.Crm.Service.Application.Controls.ConvertRuleGridDataProvider`
- `0x57558`: `Microsoft.Crm.Service.Application.Controls.ScheduleSearchDataProvider`
- `0x5756d`: `Microsoft.Crm.Service.Application.Controls.ServiceRestrictionsGridDataProvider`
- `0x57582`: `Microsoft.Crm.Service.Application.Controls.SlaGridDataProvider`
- `0x57597`: `Microsoft.Crm.Service.Application.Controls.EntitlementChannelGridDataProvider`
- `0x575ac`: `Microsoft.Crm.Service.Application.Controls.HolidaysGridDataProvider`
- `0x5762a`: `Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyDataProvider`
- `0x57669`: `Microsoft.Crm.Application.Controls.SystemCustomization.WordTemplateGridDataProvider`
- `0x576e7`: `Microsoft.Crm.Application.Controls.SystemCustomization.DependenciesForUninstallDataProvider`
- `0x577b9`: `Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider`
- `0x577ce`: `Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentLookupFilter`
- `0x578a0`: `Microsoft.Crm.Application.Controls.TeamTemplateGridDataProvider`
- `0x57987`: `Microsoft.Crm.Application.Controls.BulkDeleteFailureGridDataProvider`
- `0x57b4c`: `Unkown grid data provider '{0}' attempting to be instantiated.  Loading default GridDataProvider...`

## pseudocode

```c

```

## disassembly

```asm
0x57030  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x57035  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x5703a  ldstr    aAttemptingToLo// "Attempting to load the crm application "...
0x5703f  ldc.i4.2
0x57040  newarr   [mscorlib]System.Object
0x57045  dup
0x57046  ldc.i4.0
0x57047  ldstr    aMicrosoftCrmAp_31// "Microsoft.Crm.Application.Components.Ap"...
0x5704c  stelem.ref
0x5704d  dup
0x5704e  ldc.i4.1
0x5704f  ldarg.0
0x57050  stelem.ref
0x57051  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x57056  ldarg.0
0x57057  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x5705c  stloc.0
0x5705d  ldloc.0
0x5705e  ldc.i4   0x7CA5ED5D
0x57063  bgt.un   loc_5727E
0x57068  ldloc.0
0x57069  ldc.i4   0x44C5BEE3
0x5706e  bgt.un   loc_5716B
0x57073  ldloc.0
0x57074  ldc.i4   0x1FE9FFF5
0x57079  bgt.un.s loc_570E7
0x5707b  ldloc.0
0x5707c  ldc.i4   0x11E5D1F2
0x57081  bgt.un.s loc_570A9
0x57083  ldloc.0
0x57084  ldc.i4   0x2A6AD81
0x57089  beq      loc_577B8
0x5708e  ldloc.0
0x5708f  ldc.i4   0x7166BA4
0x57094  beq      loc_57668
0x57099  ldloc.0
0x5709a  ldc.i4   0x11E5D1F2
0x5709f  beq      loc_574EE
0x570a4  br       loc_57B42
0x570a9  ldloc.0
0x570aa  ldc.i4   0x13341B63
0x570af  bgt.un.s loc_570CC
0x570b1  ldloc.0
0x570b2  ldc.i4   0x13110442
0x570b7  beq      loc_575AB
0x570bc  ldloc.0
0x570bd  ldc.i4   0x13341B63
0x570c2  beq      loc_5773A
0x570c7  br       loc_57B42
0x570cc  ldloc.0
0x570cd  ldc.i4   0x17B2DC23
0x570d2  beq      loc_57947
0x570d7  ldloc.0
0x570d8  ldc.i4   0x1FE9FFF5
0x570dd  beq      loc_577A3
0x570e2  br       loc_57B42
0x570e7  ldloc.0
0x570e8  ldc.i4   0x31437B78
0x570ed  bgt.un.s loc_5712D
0x570ef  ldloc.0
0x570f0  ldc.i4   0x2735C008
0x570f5  bgt.un.s loc_57112
0x570f7  ldloc.0
0x570f8  ldc.i4   0x2168B1B2
0x570fd  beq      loc_576BC
0x57102  ldloc.0
0x57103  ldc.i4   0x2735C008
0x57108  beq      loc_57875
0x5710d  br       loc_57B42
0x57112  ldloc.0
0x57113  ldc.i4   0x30D9877B
0x57118  beq      loc_579C5
0x5711d  ldloc.0
0x5711e  ldc.i4   0x31437B78
0x57123  beq      loc_57971
0x57128  br       loc_57B42
0x5712d  ldloc.0
0x5712e  ldc.i4   0x42718D53
0x57133  bgt.un.s loc_57150
0x57135  ldloc.0
0x57136  ldc.i4   0x3A04F7B7
0x5713b  beq      loc_578F3
0x57140  ldloc.0
0x57141  ldc.i4   0x42718D53
0x57146  beq      loc_575FF
0x5714b  br       loc_57B42
0x57150  ldloc.0
0x57151  ldc.i4   0x43352CE8
0x57156  beq      loc_574C4
0x5715b  ldloc.0
0x5715c  ldc.i4   0x44C5BEE3
0x57161  beq      loc_57779
0x57166  br       loc_57B42
0x5716b  ldloc.0
0x5716c  ldc.i4   0x662B982A
0x57171  bgt.un   loc_571FA
0x57176  ldloc.0
0x57177  ldc.i4   0x52F11374
0x5717c  bgt.un.s loc_571BC
0x5717e  ldloc.0
0x5717f  ldc.i4   0x4E73BB0C
0x57184  bgt.un.s loc_571A1
0x57186  ldloc.0
0x57187  ldc.i4   0x4C476295
0x5718c  beq      loc_5795C
0x57191  ldloc.0
0x57192  ldc.i4   0x4E73BB0C
0x57197  beq      loc_57932
0x5719c  br       loc_57B42
0x571a1  ldloc.0
0x571a2  ldc.i4   0x4F1255E4
0x571a7  beq      loc_576A7
0x571ac  ldloc.0
0x571ad  ldc.i4   0x52F11374
0x571b2  beq      loc_5784B
0x571b7  br       loc_57B42
0x571bc  ldloc.0
0x571bd  ldc.i4   0x6054DB8C
0x571c2  bgt.un.s loc_571DF
0x571c4  ldloc.0
0x571c5  ldc.i4   0x5759BC37
0x571ca  beq      loc_57710
0x571cf  ldloc.0
0x571d0  ldc.i4   0x6054DB8C
0x571d5  beq      loc_576E6
0x571da  br       loc_57B42
0x571df  ldloc.0
0x571e0  ldc.i4   0x6348474C
0x571e5  beq      loc_575EA
0x571ea  ldloc.0
0x571eb  ldc.i4   0x662B982A
0x571f0  beq      loc_577E2
0x571f5  br       loc_57B42
0x571fa  ldloc.0
0x571fb  ldc.i4   0x7753F011
0x57200  bgt.un.s loc_57240
0x57202  ldloc.0
0x57203  ldc.i4   0x6B749AAD
0x57208  bgt.un.s loc_57225
0x5720a  ldloc.0
0x5720b  ldc.i4   0x6A4E1631
0x57210  beq      loc_57596
0x57215  ldloc.0
0x57216  ldc.i4   0x6B749AAD
0x5721b  beq      loc_575D5
0x57220  br       loc_57B42
0x57225  ldloc.0
0x57226  ldc.i4   0x6C8366BB
0x5722b  beq      loc_57908
0x57230  ldloc.0
0x57231  ldc.i4   0x7753F011
0x57236  beq      loc_57581
0x5723b  br       loc_57B42
0x57240  ldloc.0
0x57241  ldc.i4   0x78C998B3
0x57246  bgt.un.s loc_57263
0x57248  ldloc.0
0x57249  ldc.i4   0x778E814C
0x5724e  beq      loc_57518
0x57253  ldloc.0
0x57254  ldc.i4   0x78C998B3
0x57259  beq      loc_57692
0x5725e  br       loc_57B42
0x57263  ldloc.0
0x57264  ldc.i4   0x79FE59FC
0x57269  beq      loc_57503
0x5726e  ldloc.0
0x5726f  ldc.i4   0x7CA5ED5D
0x57274  beq      loc_57836
0x57279  br       loc_57B42
0x5727e  ldloc.0
0x5727f  ldc.i4   0x9BAA1BC3
0x57284  bgt.un   loc_5739C
0x57289  ldloc.0
0x5728a  ldc.i4   0x8D1186CA
0x5728f  bgt.un   loc_57318
0x57294  ldloc.0
0x57295  ldc.i4   0x8247A274
0x5729a  bgt.un.s loc_572DA
0x5729c  ldloc.0
0x5729d  ldc.i4   0x7E62FFE8
0x572a2  bgt.un.s loc_572BF
0x572a4  ldloc.0
0x572a5  ldc.i4   0x7DBA01E8
0x572aa  beq      loc_574AF
0x572af  ldloc.0
0x572b0  ldc.i4   0x7E62FFE8
0x572b5  beq      loc_5763E
0x572ba  br       loc_57B42
0x572bf  ldloc.0
0x572c0  ldc.i4   0x7E7BBCF7
0x572c5  beq      loc_5752D
0x572ca  ldloc.0
0x572cb  ldc.i4   0x8247A274
0x572d0  beq      loc_5778E
0x572d5  br       loc_57B42
0x572da  ldloc.0
0x572db  ldc.i4   0x836FC199
0x572e0  bgt.un.s loc_572FD
0x572e2  ldloc.0
0x572e3  ldc.i4   0x82544A64
0x572e8  beq      loc_5774F
0x572ed  ldloc.0
0x572ee  ldc.i4   0x836FC199
0x572f3  beq      loc_577F7
0x572f8  br       loc_57B42
0x572fd  ldloc.0
0x572fe  ldc.i4   0x8AA8768B
0x57303  beq      loc_57986
0x57308  ldloc.0
0x57309  ldc.i4   0x8D1186CA
0x5730e  beq      loc_57542
0x57313  br       loc_57B42
0x57318  ldloc.0
0x57319  ldc.i4   0x971C7B2F
0x5731e  bgt.un.s loc_5735E
0x57320  ldloc.0
0x57321  ldc.i4   0x9566CA37
0x57326  bgt.un.s loc_57343
0x57328  ldloc.0
0x57329  ldc.i4   0x93FAF0CD
0x5732e  beq      loc_5780C
0x57333  ldloc.0
0x57334  ldc.i4   0x9566CA37
0x57339  beq      loc_576FB
0x5733e  br       loc_57B42
0x57343  ldloc.0
0x57344  ldc.i4   0x95CFD018
0x57349  beq      loc_57653
0x5734e  ldloc.0
0x5734f  ldc.i4   0x971C7B2F
0x57354  beq      loc_578DE
0x57359  br       loc_57B42
0x5735e  ldloc.0
0x5735f  ldc.i4   0x9B7C215B
0x57364  bgt.un.s loc_57381
0x57366  ldloc.0
0x57367  ldc.i4   0x986E20C3
0x5736c  beq      loc_5788A
0x57371  ldloc.0
0x57372  ldc.i4   0x9B7C215B
0x57377  beq      loc_5799B
0x5737c  br       loc_57B42
0x57381  ldloc.0
0x57382  ldc.i4   0x9B7D3685
0x57387  beq      loc_5789F
0x5738c  ldloc.0
0x5738d  ldc.i4   0x9BAA1BC3
0x57392  beq      loc_577CD
0x57397  br       loc_57B42
0x5739c  ldloc.0
0x5739d  ldc.i4   0xBCAABB06
0x573a2  bgt.un   loc_5742B
0x573a7  ldloc.0
0x573a8  ldc.i4   0xAB752336
0x573ad  bgt.un.s loc_573ED
0x573af  ldloc.0
0x573b0  ldc.i4   0x9D81D2E3
0x573b5  bgt.un.s loc_573D2
0x573b7  ldloc.0
0x573b8  ldc.i4   0x9BD4ACF7
0x573bd  beq      loc_574D9
0x573c2  ldloc.0
0x573c3  ldc.i4   0x9D81D2E3
0x573c8  beq      loc_578C9
0x573cd  br       loc_57B42
0x573d2  ldloc.0
0x573d3  ldc.i4   0x9EF0AB1E
0x573d8  beq      loc_579B0
0x573dd  ldloc.0
0x573de  ldc.i4   0xAB752336
0x573e3  beq      loc_57725
0x573e8  br       loc_57B42
0x573ed  ldloc.0
0x573ee  ldc.i4   0xB54D067E
0x573f3  bgt.un.s loc_57410
0x573f5  ldloc.0
0x573f6  ldc.i4   0xB4FF9873
0x573fb  beq      loc_57821
0x57400  ldloc.0
0x57401  ldc.i4   0xB54D067E
0x57406  beq      loc_57614
0x5740b  br       loc_57B42
0x57410  ldloc.0
0x57411  ldc.i4   0xB68681AD
0x57416  beq      loc_575C0
0x5741b  ldloc.0
0x5741c  ldc.i4   0xBCAABB06
0x57421  beq      loc_57629
0x57426  br       loc_57B42
0x5742b  ldloc.0
0x5742c  ldc.i4   0xE0019521
0x57431  bgt.un.s loc_57471
0x57433  ldloc.0
0x57434  ldc.i4   0xD42EC543
0x57439  bgt.un.s loc_57456
0x5743b  ldloc.0
0x5743c  ldc.i4   0xCE74F3E3
0x57441  beq      loc_576D1
0x57446  ldloc.0
  ... truncated ...
```
