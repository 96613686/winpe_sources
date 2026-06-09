# Microsoft.Crm.Application.Ribbon.DynamicMenuBuilderFactory::GetDynamicMenuBuilder_2

- ea: `0x4f6e0`
- end: `0x4fac3`
- name: `Microsoft.Crm.Application.Ribbon.DynamicMenuBuilderFactory::GetDynamicMenuBuilder_2`
- size: `995`
- prototype: ``
- caller_count: `4`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x4f6b0`
- `0x4f6c0`
- `0x4f6d0`
- `0x54560`

## callees

- `0x2fb90`
- `0x4c960`
- `0x4f680`
- `0x4f6e0`
- `0x4fd00`
- `0x50360`
- `0x50c20`
- `0x50c40`
- `0x99590`
- `0x99ac0`
- `0x99ad0`
- `0x99ef0`
- `0x9a620`
- `0x9b320`
- `0x9b330`
- `0x9ca50`

## string_xrefs

- `0x4f977`: `Mscrm.DynamicMenu.Grid.OpenSource`
- `0x4f98c`: `Mscrm.DynamicMenu.ChangeControlCommand`

## pseudocode

```c

```

## disassembly

```asm
0x4f6e0  ldarg.2
0x4f6e1  brfalse.s loc_4F6E6
0x4f6e3  ldarg.2
0x4f6e4  br.s     loc_4F6ED
0x4f6e6  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4f6eb  stloc.2
0x4f6ec  ldloc.2
0x4f6ed  stloc.0
0x4f6ee  ldarg.0
0x4f6ef  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x4f6f4  stloc.3
0x4f6f5  ldloc.3
0x4f6f6  ldc.i4   0x817399C7
0x4f6fb  bgt.un   loc_4F78F
0x4f700  ldloc.3
0x4f701  ldc.i4   0x2D560B9E
0x4f706  bgt.un.s loc_4F746
0x4f708  ldloc.3
0x4f709  ldc.i4   0xF7DA4D4
0x4f70e  bgt.un.s loc_4F72B
0x4f710  ldloc.3
0x4f711  ldc.i4   0x3B6C67C
0x4f716  beq      loc_4F826
0x4f71b  ldloc.3
0x4f71c  ldc.i4   0xF7DA4D4
0x4f721  beq      loc_4F961
0x4f726  br       loc_4FA89
0x4f72b  ldloc.3
0x4f72c  ldc.i4   0x21EFE921
0x4f731  beq      loc_4F8CE
0x4f736  ldloc.3
0x4f737  ldc.i4   0x2D560B9E
0x4f73c  beq      loc_4F8F8
0x4f741  br       loc_4FA89
0x4f746  ldloc.3
0x4f747  ldc.i4   0x4BE10B4D
0x4f74c  bgt.un.s loc_4F769
0x4f74e  ldloc.3
0x4f74f  ldc.i4   0x45F5995E
0x4f754  beq      loc_4F9A0
0x4f759  ldloc.3
0x4f75a  ldc.i4   0x4BE10B4D
0x4f75f  beq      loc_4F8E3
0x4f764  br       loc_4FA89
0x4f769  ldloc.3
0x4f76a  ldc.i4   0x5B4908EF
0x4f76f  beq      loc_4F88F
0x4f774  ldloc.3
0x4f775  ldc.i4   0x791CB477
0x4f77a  beq      loc_4F865
0x4f77f  ldloc.3
0x4f780  ldc.i4   0x817399C7
0x4f785  beq      loc_4F83B
0x4f78a  br       loc_4FA89
0x4f78f  ldloc.3
0x4f790  ldc.i4   0xBE04BEE6
0x4f795  bgt.un.s loc_4F7E0
0x4f797  ldloc.3
0x4f798  ldc.i4   0xAB515E4C
0x4f79d  bgt.un.s loc_4F7BA
0x4f79f  ldloc.3
0x4f7a0  ldc.i4   0xA1D91F66
0x4f7a5  beq      loc_4F976
0x4f7aa  ldloc.3
0x4f7ab  ldc.i4   0xAB515E4C
0x4f7b0  beq      loc_4F94C
0x4f7b5  br       loc_4FA89
0x4f7ba  ldloc.3
0x4f7bb  ldc.i4   0xAC740CA4
0x4f7c0  beq      loc_4F90D
0x4f7c5  ldloc.3
0x4f7c6  ldc.i4   0xAF1FF817
0x4f7cb  beq      loc_4F8B9
0x4f7d0  ldloc.3
0x4f7d1  ldc.i4   0xBE04BEE6
0x4f7d6  beq      loc_4F87A
0x4f7db  br       loc_4FA89
0x4f7e0  ldloc.3
0x4f7e1  ldc.i4   0xC155169E
0x4f7e6  bgt.un.s loc_4F800
0x4f7e8  ldloc.3
0x4f7e9  ldc.i4   0xC040710D
0x4f7ee  beq      loc_4F8A4
0x4f7f3  ldloc.3
0x4f7f4  ldc.i4   0xC155169E
0x4f7f9  beq.s    loc_4F850
0x4f7fb  br       loc_4FA89
0x4f800  ldloc.3
0x4f801  ldc.i4   0xDAC40D0C
0x4f806  beq      loc_4F922
0x4f80b  ldloc.3
0x4f80c  ldc.i4   0xDE4AA4BD
0x4f811  beq      loc_4F98B
0x4f816  ldloc.3
0x4f817  ldc.i4   0xE8C9512A
0x4f81c  beq      loc_4F937
0x4f821  br       loc_4FA89
0x4f826  ldarg.0
0x4f827  ldstr    aMscrmDynamicme// "Mscrm.DynamicMenu.GoTo"
0x4f82c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4f831  brtrue   loc_4F9B5
0x4f836  br       loc_4FA89
0x4f83b  ldarg.0
0x4f83c  ldstr    aMscrmDynamicme_0// "Mscrm.DynamicMenu.Outlook.GoTo"
0x4f841  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4f846  brtrue   loc_4F9BF
0x4f84b  br       loc_4FA89
0x4f850  ldarg.0
0x4f851  ldstr    aMscrmDynamicme_1// "Mscrm.DynamicMenu.NewRecord"
0x4f856  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4f85b  brtrue   loc_4F9C9
0x4f860  br       loc_4FA89
0x4f865  ldarg.0
0x4f866  ldstr    aMscrmDynamicme_2// "Mscrm.DynamicMenu.Outlook.NewRecord"
0x4f86b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4f870  brtrue   loc_4F9D3
0x4f875  br       loc_4FA89
0x4f87a  ldarg.0
0x4f87b  ldstr    aMscrmDynamicme_3// "Mscrm.DynamicMenu.NewActivity"
0x4f880  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4f885  brtrue   loc_4F9DD
0x4f88a  br       loc_4FA89
0x4f88f  ldarg.0
0x4f890  ldstr    aMscrmDynamicme_4// "Mscrm.DynamicMenu.Outlook.NewActivity"
0x4f895  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4f89a  brtrue   loc_4F9ED
0x4f89f  br       loc_4FA89
0x4f8a4  ldarg.0
0x4f8a5  ldstr    aMscrmDynamicme_5// "Mscrm.DynamicMenu.Form.AddActivity"
0x4f8aa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4f8af  brtrue   loc_4F9FD
0x4f8b4  br       loc_4FA89
0x4f8b9  ldarg.0
0x4f8ba  ldstr    aMscrmDynamicme_6// "Mscrm.DynamicMenu.Grid.AddActivity"
0x4f8bf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4f8c4  brtrue   loc_4FA0D
0x4f8c9  br       loc_4FA89
0x4f8ce  ldarg.0
0x4f8cf  ldstr    aMscrmDynamicme_7// "Mscrm.DynamicMenu.Grid.NewCustomActivit"...
0x4f8d4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4f8d9  brtrue   loc_4FA1D
0x4f8de  br       loc_4FA89
0x4f8e3  ldarg.0
0x4f8e4  ldstr    aMscrmDynamicme_8// "Mscrm.DynamicMenu.Subgrid.NewActivityMe"...
0x4f8e9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4f8ee  brtrue   loc_4FA2D
0x4f8f3  br       loc_4FA89
0x4f8f8  ldarg.0
0x4f8f9  ldstr    aMscrmDynamicme_9// "Mscrm.DynamicMenu.Grid.QualifyAs"
0x4f8fe  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4f903  brtrue   loc_4FA3D
0x4f908  br       loc_4FA89
0x4f90d  ldarg.0
0x4f90e  ldstr    aMscrmDynamicme_10// "Mscrm.DynamicMenu.Grid.DisqualifyAs"
0x4f913  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4f918  brtrue   loc_4FA48
0x4f91d  br       loc_4FA89
0x4f922  ldarg.0
0x4f923  ldstr    aMscrmDynamicme_11// "Mscrm.DynamicMenu.Form.QualifyAs"
0x4f928  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4f92d  brtrue   loc_4FA53
0x4f932  br       loc_4FA89
0x4f937  ldarg.0
0x4f938  ldstr    aMscrmDynamicme_12// "Mscrm.DynamicMenu.Form.DisqualifyAs"
0x4f93d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4f942  brtrue   loc_4FA5E
0x4f947  br       loc_4FA89
0x4f94c  ldarg.0
0x4f94d  ldstr    aMscrmDynamicme_13// "Mscrm.DynamicMenu.Grid.ChangeLocation"
0x4f952  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4f957  brtrue   loc_4FA69
0x4f95c  br       loc_4FA89
0x4f961  ldarg.0
0x4f962  ldstr    aMscrmDynamicme_14// "Mscrm.DynamicMenu.Grid.EditLocation"
0x4f967  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4f96c  brtrue   loc_4FA69
0x4f971  br       loc_4FA89
0x4f976  ldarg.0
0x4f977  ldstr    aMscrmDynamicme_15// "Mscrm.DynamicMenu.Grid.OpenSource"
0x4f97c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4f981  brtrue   loc_4FA69
0x4f986  br       loc_4FA89
0x4f98b  ldarg.0
0x4f98c  ldstr    aMscrmDynamicme_16// "Mscrm.DynamicMenu.ChangeControlCommand"
0x4f991  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4f996  brtrue   loc_4FA74
0x4f99b  br       loc_4FA89
0x4f9a0  ldarg.0
0x4f9a1  ldstr    aMscrmFormFlows_0// "Mscrm.Form.Flows"
0x4f9a6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4f9ab  brtrue   loc_4FA7F
0x4f9b0  br       loc_4FA89
0x4f9b5  ldarg.0
0x4f9b6  ldarg.1
0x4f9b7  ldc.i4.1
0x4f9b8  ldloc.0
0x4f9b9  newobj   instance void Microsoft.Crm.Application.Ribbon.GoToMenuBuilder::.ctor(string commandPrefix, string idPrefix, bool isWebClient, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4f9be  ret
0x4f9bf  ldarg.0
0x4f9c0  ldarg.1
0x4f9c1  ldc.i4.0
0x4f9c2  ldloc.0
0x4f9c3  newobj   instance void Microsoft.Crm.Application.Ribbon.GoToMenuBuilder::.ctor(string commandPrefix, string idPrefix, bool isWebClient, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4f9c8  ret
0x4f9c9  ldarg.0
0x4f9ca  ldarg.1
0x4f9cb  ldc.i4.1
0x4f9cc  ldloc.0
0x4f9cd  newobj   instance void Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilder::.ctor(string commandPrefix, string idPrefix, bool isWebClient, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4f9d2  ret
0x4f9d3  ldarg.0
0x4f9d4  ldarg.1
0x4f9d5  ldc.i4.0
0x4f9d6  ldloc.0
0x4f9d7  newobj   instance void Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilder::.ctor(string commandPrefix, string idPrefix, bool isWebClient, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4f9dc  ret
0x4f9dd  ldarg.s  5
0x4f9df  ldc.i4.0
0x4f9e0  ldarg.0
0x4f9e1  ldarg.1
0x4f9e2  ldc.i4.1
0x4f9e3  ldloc.0
0x4f9e4  ldarg.3
0x4f9e5  ldarg.s  6
0x4f9e7  callvirt instance class Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase Microsoft.Crm.Application.Ribbon.IMenuBuilderFactory::RetrieveMenu(valuetype Microsoft.Crm.Application.Ribbon.MenuValidator menuValidator, string commandId, string idPrefix, bool isWebClient, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext, int32 languageCode, bool replaceLocalStrings)
0x4f9ec  ret
0x4f9ed  ldarg.s  5
0x4f9ef  ldc.i4.1
0x4f9f0  ldarg.0
0x4f9f1  ldarg.1
0x4f9f2  ldc.i4.1
0x4f9f3  ldloc.0
0x4f9f4  ldarg.3
0x4f9f5  ldarg.s  6
0x4f9f7  callvirt instance class Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase Microsoft.Crm.Application.Ribbon.IMenuBuilderFactory::RetrieveMenu(valuetype Microsoft.Crm.Application.Ribbon.MenuValidator menuValidator, string commandId, string idPrefix, bool isWebClient, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext, int32 languageCode, bool replaceLocalStrings)
0x4f9fc  ret
0x4f9fd  ldarg.s  5
0x4f9ff  ldc.i4.2
0x4fa00  ldarg.0
0x4fa01  ldarg.1
0x4fa02  ldc.i4.1
0x4fa03  ldloc.0
0x4fa04  ldc.i4.0
0x4fa05  ldarg.s  6
0x4fa07  callvirt instance class Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase Microsoft.Crm.Application.Ribbon.IMenuBuilderFactory::RetrieveMenu(valuetype Microsoft.Crm.Application.Ribbon.MenuValidator menuValidator, string commandId, string idPrefix, bool isWebClient, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext, int32 languageCode, bool replaceLocalStrings)
0x4fa0c  ret
0x4fa0d  ldarg.s  5
0x4fa0f  ldc.i4.3
0x4fa10  ldarg.0
0x4fa11  ldarg.1
0x4fa12  ldc.i4.1
0x4fa13  ldloc.0
0x4fa14  ldc.i4.0
0x4fa15  ldarg.s  6
0x4fa17  callvirt instance class Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase Microsoft.Crm.Application.Ribbon.IMenuBuilderFactory::RetrieveMenu(valuetype Microsoft.Crm.Application.Ribbon.MenuValidator menuValidator, string commandId, string idPrefix, bool isWebClient, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext, int32 languageCode, bool replaceLocalStrings)
0x4fa1c  ret
0x4fa1d  ldarg.s  5
0x4fa1f  ldc.i4.4
0x4fa20  ldarg.0
0x4fa21  ldarg.1
0x4fa22  ldc.i4.1
0x4fa23  ldloc.0
0x4fa24  ldc.i4.0
0x4fa25  ldarg.s  6
0x4fa27  callvirt instance class Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase Microsoft.Crm.Application.Ribbon.IMenuBuilderFactory::RetrieveMenu(valuetype Microsoft.Crm.Application.Ribbon.MenuValidator menuValidator, string commandId, string idPrefix, bool isWebClient, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext, int32 languageCode, bool replaceLocalStrings)
0x4fa2c  ret
0x4fa2d  ldarg.s  5
0x4fa2f  ldc.i4.5
0x4fa30  ldarg.0
0x4fa31  ldarg.1
0x4fa32  ldc.i4.1
0x4fa33  ldloc.0
0x4fa34  ldarg.3
0x4fa35  ldarg.s  6
0x4fa37  callvirt instance class Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase Microsoft.Crm.Application.Ribbon.IMenuBuilderFactory::RetrieveMenu(valuetype Microsoft.Crm.Application.Ribbon.MenuValidator menuValidator, string commandId, string idPrefix, bool isWebClient, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext, int32 languageCode, bool replaceLocalStrings)
0x4fa3c  ret
0x4fa3d  ldarg.0
0x4fa3e  ldarg.1
0x4fa3f  ldloc.0
0x4fa40  ldc.i4.1
0x4fa41  ldc.i4.0
0x4fa42  newobj   instance void Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.ConvertAsMenuBuilder::.ctor(string commandPrefix, string idPrefix, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, bool isQualify, bool isForm)
0x4fa47  ret
0x4fa48  ldarg.0
0x4fa49  ldarg.1
0x4fa4a  ldloc.0
0x4fa4b  ldc.i4.0
0x4fa4c  ldc.i4.0
0x4fa4d  newobj   instance void Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.ConvertAsMenuBuilder::.ctor(string commandPrefix, string idPrefix, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, bool isQualify, bool isForm)
0x4fa52  ret
0x4fa53  ldarg.0
0x4fa54  ldarg.1
0x4fa55  ldloc.0
0x4fa56  ldc.i4.1
0x4fa57  ldc.i4.1
0x4fa58  newobj   instance void Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.ConvertAsMenuBuilder::.ctor(string commandPrefix, string idPrefix, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, bool isQualify, bool isForm)
0x4fa5d  ret
0x4fa5e  ldarg.0
0x4fa5f  ldarg.1
0x4fa60  ldloc.0
  ... truncated ...
```
