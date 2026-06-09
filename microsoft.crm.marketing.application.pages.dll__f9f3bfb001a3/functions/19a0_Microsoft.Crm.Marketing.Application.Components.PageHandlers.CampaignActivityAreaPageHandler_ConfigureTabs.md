# Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityAreaPageHandler::ConfigureTabs

- ea: `0x19a0`
- end: `0x1b24`
- name: `Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityAreaPageHandler::ConfigureTabs`
- size: `388`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x19a0`

## pseudocode

```c

```

## disassembly

```asm
0x19a0  ldc.i4.0
0x19a1  stloc.0
0x19a2  ldarg.0
0x19a3  call     instance string [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::get_CurrentTabId()
0x19a8  stloc.1
0x19a9  ldloc.1
0x19aa  ldstr    aAreabulkoperat// "areaBulkOperationSuccesses"
0x19af  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19b4  brtrue.s loc_19DB
0x19b6  ldloc.1
0x19b7  ldstr    aAreabulkoperat_0// "areaBulkOperationFailures"
0x19bc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19c1  brtrue   loc_1AE1
0x19c6  ldloc.1
0x19c7  ldstr    aAreatargetlist// "areaTargetLists"
0x19cc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19d1  brtrue   loc_1AFE
0x19d6  br       loc_1B1D
0x19db  ldc.i4.1
0x19dc  newarr   [mscorlib]System.String
0x19e1  dup
0x19e2  ldc.i4.0
0x19e3  ldstr    aChanneltypecod// "channeltypecode"
0x19e8  stelem.ref
0x19e9  stloc.2
0x19ea  ldloca.s 3
0x19ec  ldarg.0
0x19ed  call     instance string [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::get_CurrentObjectId()
0x19f2  call     instance void [mscorlib]System.Guid::.ctor(string)
0x19f7  ldstr    aCampaignactivi// "campaignactivity"
0x19fc  ldloc.3
0x19fd  ldloc.2
0x19fe  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a03  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a08  ldstr    aChanneltypecod// "channeltypecode"
0x1a0d  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x1a12  unbox.any [mscorlib]System.Int32
0x1a17  stloc.0
0x1a18  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a1d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x1a22  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x1a27  ldstr    aAddingBulkOper// "Adding Bulk Operation Success Tab for C"...
0x1a2c  ldc.i4.1
0x1a2d  newarr   [mscorlib]System.Object
0x1a32  dup
0x1a33  ldc.i4.0
0x1a34  ldloc.0
0x1a35  box      [mscorlib]System.Int32
0x1a3a  stelem.ref
0x1a3b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1a40  ldloc.0
0x1a41  ldc.i4.1
0x1a42  sub
0x1a43  switch   loc_1AB1, loc_1AC9, loc_1A99, loc_1A99, loc_1A69, loc_1A69, loc_1A81, loc_1A81
0x1a68  ret
0x1a69  ldarg.0
0x1a6a  ldc.i4   0x106C
0x1a6f  ldstr    aF29c4474E26b4a// "{F29C4474-E26B-4A46-9DEA-A792532379AD}"
0x1a74  ldstr    aBulkoperationR// "BulkOperation.RetrieveSuccessessActivit"...
0x1a79  ldc.i4.1
0x1a7a  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::ConfigureAreaPage(int32, string, string, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode)
0x1a7f  pop
0x1a80  ret
0x1a81  ldarg.0
0x1a82  ldc.i4   0x106A
0x1a87  ldstr    aCc98cb1f65524f// "{CC98CB1F-6552-4FD8-9E2F-39A1CAD2F710}"
0x1a8c  ldstr    aBulkoperationR// "BulkOperation.RetrieveSuccessessActivit"...
0x1a91  ldc.i4.1
0x1a92  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::ConfigureAreaPage(int32, string, string, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode)
0x1a97  pop
0x1a98  ret
0x1a99  ldarg.0
0x1a9a  ldc.i4   0x106F
0x1a9f  ldstr    aBf36046aD0174a// "{BF36046A-D017-4A5F-927D-086522EC08ED}"
0x1aa4  ldstr    aBulkoperationR// "BulkOperation.RetrieveSuccessessActivit"...
0x1aa9  ldc.i4.1
0x1aaa  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::ConfigureAreaPage(int32, string, string, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode)
0x1aaf  pop
0x1ab0  ret
0x1ab1  ldarg.0
0x1ab2  ldc.i4   0x1072
0x1ab7  ldstr    aF6a2f89168464b// "{F6A2F891-6846-4B21-B922-712695AFD65C}"
0x1abc  ldstr    aBulkoperationR// "BulkOperation.RetrieveSuccessessActivit"...
0x1ac1  ldc.i4.1
0x1ac2  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::ConfigureAreaPage(int32, string, string, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode)
0x1ac7  pop
0x1ac8  ret
0x1ac9  ldarg.0
0x1aca  ldc.i4   0x1068
0x1acf  ldstr    a5b5f75f6B58542// "{5B5F75F6-B585-4212-952A-B4CBB64E2627}"
0x1ad4  ldstr    aBulkoperationR// "BulkOperation.RetrieveSuccessessActivit"...
0x1ad9  ldc.i4.1
0x1ada  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::ConfigureAreaPage(int32, string, string, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode)
0x1adf  pop
0x1ae0  ret
0x1ae1  ldarg.0
0x1ae2  ldc.i4   0x1135
0x1ae7  ldstr    aAc88f09079c54b// "{AC88F090-79C5-4B0E-9627-664B4B763EDB}"
0x1aec  ldstr    aBulkoperationR_0// "BulkOperation.RetrieveFailures"
0x1af1  ldc.i4.2
0x1af2  ldstr    aBulkoperationL// "BulkOperation_logs"
0x1af7  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::ConfigureAreaPage(int32, string, string, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode, string)
0x1afc  pop
0x1afd  ret
0x1afe  ldarg.0
0x1aff  ldc.i4   0x10CC
0x1b04  ldstr    aBdd9354753f646// "{BDD93547-53F6-4609-B591-9F48CE86295F}"
0x1b09  ldstr    aCampaignactivi_1// "CampaignActivity.RetrieveItems"
0x1b0e  ldc.i4.2
0x1b0f  ldstr    aCampaignactivi_2// "campaignactivitylist_association"
0x1b14  ldc.i4.0
0x1b15  ldc.i4.1
0x1b16  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::ConfigureAreaPage(int32, string, string, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode, string, bool, int32)
0x1b1b  pop
0x1b1c  ret
0x1b1d  ldarg.0
0x1b1e  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::ConfigureTabs()
0x1b23  ret
```
