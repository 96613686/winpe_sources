# Microsoft.Crm.Metadata.Generators.UserContextGenerator::CreateFCBContext

- ea: `0x41b60`
- end: `0x432e3`
- name: `Microsoft.Crm.Metadata.Generators.UserContextGenerator::CreateFCBContext`
- size: `6019`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x41920`

## callees

- `0x41b60`
- `0xbd040`
- `0xbd940`
- `0xbdb40`
- `0xbdb80`
- `0xbdbb0`
- `0xbdbd0`
- `0xbdc10`
- `0x1c7190`

## string_xrefs

- `0x41dc5`: `AllowExcelBrowserCache`
- `0x41dfc`: `DocumentTemplateUCI`
- `0x41e33`: `ExcelDocumentTemplate`
- `0x41e6a`: `EnableExcelTemplatePerfFix`
- `0x41ea1`: `WordDocumentTemplate`
- `0x41f7d`: `TaskBasedFlow`
- `0x420c7`: `AppLinking`
- `0x4216c`: `ServiceCaseTopicAnalysis`
- `0x42207`: `PrivilegeBasedMetadataSync`
- `0x424c3`: `DocumentRecommendations`
- `0x424fa`: `ProductRecommendations`
- `0x42824`: `InteractionCentricEmailLink`
- `0x42be4`: `TimelineWallCommandBarActivities`
- `0x42dd3`: `UnifiedClientCacheModeEnabled`
- `0x42f1d`: `UseNewRIConfig`
- `0x4308c`: `LinkedInAnalysis`
- `0x430c3`: `EmailEngagementComposeForUCI`
- `0x430eb`: `UCIMetadataClientBrowserCache`

## pseudocode

```c

```

## disassembly

```asm
0x41b60  ldarg.0
0x41b61  call     object[] Microsoft.Crm.ObjectModel.FeatureControlUtilities::GetAllClientFeatures(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x41b66  stloc.0
0x41b67  ldc.i4.s 0x6E
0x41b69  newarr   [mscorlib]System.Object
0x41b6e  dup
0x41b6f  ldc.i4.0
0x41b70  ldstr    aEditablegridco// "EditableGridControlPbl"
0x41b75  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41b7a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41b7f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_EditableGridControlPbl()
0x41b84  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x41b89  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41b8e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41b93  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_EditableGridControlPbl()
0x41b98  ldarg.0
0x41b99  call     bool Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail featureName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x41b9e  newobj   instance void class <>f__AnonymousType5`3<string, string, bool>::.ctor(var<u1>, !!T0, var<u1>)
0x41ba3  stelem.ref
0x41ba4  dup
0x41ba5  ldc.i4.1
0x41ba6  ldstr    aEditablegridco_0// "EditableGridControlJsEvents"
0x41bab  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41bb0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41bb5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_EditableGridControlJsEvents()
0x41bba  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x41bbf  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41bc4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41bc9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_EditableGridControlJsEvents()
0x41bce  ldarg.0
0x41bcf  call     bool Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail featureName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x41bd4  newobj   instance void class <>f__AnonymousType5`3<string, string, bool>::.ctor(var<u1>, !!T0, var<u1>)
0x41bd9  stelem.ref
0x41bda  dup
0x41bdb  ldc.i4.2
0x41bdc  ldstr    aMobileclientma// "MobileClientMashup"
0x41be1  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41be6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41beb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_MocaMashups()
0x41bf0  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x41bf5  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41bfa  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41bff  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_MocaMashups()
0x41c04  ldarg.0
0x41c05  call     bool Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail featureName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x41c0a  newobj   instance void class <>f__AnonymousType5`3<string, string, bool>::.ctor(var<u1>, !!T0, var<u1>)
0x41c0f  stelem.ref
0x41c10  dup
0x41c11  ldc.i4.3
0x41c12  ldstr    aPotassiumappfo// "PotassiumAppForOutlook"
0x41c17  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41c1c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41c21  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_PotassiumAppForOutlook()
0x41c26  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x41c2b  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41c30  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41c35  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_PotassiumAppForOutlook()
0x41c3a  ldarg.0
0x41c3b  call     bool Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail featureName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x41c40  newobj   instance void class <>f__AnonymousType5`3<string, string, bool>::.ctor(var<u1>, !!T0, var<u1>)
0x41c45  stelem.ref
0x41c46  dup
0x41c47  ldc.i4.4
0x41c48  ldstr    aOfficemailapp// "OfficeMailApp"
0x41c4d  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41c52  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41c57  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OfficeMailApp()
0x41c5c  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x41c61  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41c66  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41c6b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OfficeMailApp()
0x41c70  ldarg.0
0x41c71  call     bool Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail featureName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x41c76  newobj   instance void class <>f__AnonymousType5`3<string, string, bool>::.ctor(var<u1>, !!T0, var<u1>)
0x41c7b  stelem.ref
0x41c7c  dup
0x41c7d  ldc.i4.5
0x41c7e  ldstr    aOfficemailappm// "OfficeMailAppMobile"
0x41c83  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41c88  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41c8d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OfficeMailAppMobile()
0x41c92  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x41c97  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41c9c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41ca1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OfficeMailAppMobile()
0x41ca6  ldarg.0
0x41ca7  call     bool Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail featureName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x41cac  newobj   instance void class <>f__AnonymousType5`3<string, string, bool>::.ctor(var<u1>, !!T0, var<u1>)
0x41cb1  stelem.ref
0x41cb2  dup
0x41cb3  ldc.i4.6
0x41cb4  ldstr    aOfficemailappm_0// "OfficeMailAppMetadata"
0x41cb9  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41cbe  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41cc3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OfficeMailAppMetadata()
0x41cc8  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x41ccd  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41cd2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41cd7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OfficeMailAppMetadata()
0x41cdc  ldarg.0
0x41cdd  call     bool Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail featureName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x41ce2  newobj   instance void class <>f__AnonymousType5`3<string, string, bool>::.ctor(var<u1>, !!T0, var<u1>)
0x41ce7  stelem.ref
0x41ce8  dup
0x41ce9  ldc.i4.7
0x41cea  ldstr    aOfficemailappe// "OfficeMailAppEmailEngagement"
0x41cef  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41cf4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41cf9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OfficeMailAppEmailEngagement()
0x41cfe  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x41d03  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41d08  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41d0d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OfficeMailAppEmailEngagement()
0x41d12  ldarg.0
0x41d13  call     bool Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail featureName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x41d18  newobj   instance void class <>f__AnonymousType5`3<string, string, bool>::.ctor(var<u1>, !!T0, var<u1>)
0x41d1d  stelem.ref
0x41d1e  dup
0x41d1f  ldc.i4.8
0x41d20  ldstr    aExporttoexcelm// "ExportToExcelMobile"
0x41d25  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41d2a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41d2f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_ExportToExcelMobile()
0x41d34  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x41d39  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41d3e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41d43  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_ExportToExcelMobile()
0x41d48  ldarg.0
0x41d49  call     bool Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail featureName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x41d4e  newobj   instance void class <>f__AnonymousType5`3<string, string, bool>::.ctor(var<u1>, !!T0, var<u1>)
0x41d53  stelem.ref
0x41d54  dup
0x41d55  ldc.i4.s 9
0x41d57  ldstr    aExporttoexcel// "ExportToExcel"
0x41d5c  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41d61  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41d66  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_ExportToExcel()
0x41d6b  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x41d70  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41d75  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41d7a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_ExportToExcel()
0x41d7f  ldarg.0
0x41d80  call     bool Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail featureName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x41d85  newobj   instance void class <>f__AnonymousType5`3<string, string, bool>::.ctor(var<u1>, !!T0, var<u1>)
0x41d8a  stelem.ref
0x41d8b  dup
0x41d8c  ldc.i4.s 0xA
0x41d8e  ldstr    aExporttoexcelu// "ExportToExcelUCI"
0x41d93  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41d98  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41d9d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_ExportToExcelUCI()
0x41da2  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x41da7  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41dac  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41db1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_ExportToExcelUCI()
0x41db6  ldarg.0
0x41db7  call     bool Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail featureName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x41dbc  newobj   instance void class <>f__AnonymousType5`3<string, string, bool>::.ctor(var<u1>, !!T0, var<u1>)
0x41dc1  stelem.ref
0x41dc2  dup
0x41dc3  ldc.i4.s 0xB
0x41dc5  ldstr    aAllowexcelbrow// "AllowExcelBrowserCache"
0x41dca  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41dcf  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41dd4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AllowExcelBrowserCache()
0x41dd9  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x41dde  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41de3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41de8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AllowExcelBrowserCache()
0x41ded  ldarg.0
0x41dee  call     bool Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail featureName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x41df3  newobj   instance void class <>f__AnonymousType5`3<string, string, bool>::.ctor(var<u1>, !!T0, var<u1>)
0x41df8  stelem.ref
0x41df9  dup
0x41dfa  ldc.i4.s 0xC
0x41dfc  ldstr    aDocumenttempla// "DocumentTemplateUCI"
0x41e01  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41e06  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41e0b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_DocumentTemplateUCI()
0x41e10  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x41e15  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41e1a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41e1f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_DocumentTemplateUCI()
0x41e24  ldarg.0
0x41e25  call     bool Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail featureName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x41e2a  newobj   instance void class <>f__AnonymousType5`3<string, string, bool>::.ctor(var<u1>, !!T0, var<u1>)
0x41e2f  stelem.ref
0x41e30  dup
0x41e31  ldc.i4.s 0xD
0x41e33  ldstr    aExceldocumentt// "ExcelDocumentTemplate"
0x41e38  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41e3d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41e42  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_ExcelDocumentTemplate()
0x41e47  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x41e4c  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41e51  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41e56  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_ExcelDocumentTemplate()
0x41e5b  ldarg.0
0x41e5c  call     bool Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail featureName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x41e61  newobj   instance void class <>f__AnonymousType5`3<string, string, bool>::.ctor(var<u1>, !!T0, var<u1>)
0x41e66  stelem.ref
0x41e67  dup
0x41e68  ldc.i4.s 0xE
0x41e6a  ldstr    aEnableexceltem// "EnableExcelTemplatePerfFix"
0x41e6f  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41e74  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41e79  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_EnableExcelTemplatePerfFix()
0x41e7e  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x41e83  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41e88  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41e8d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_EnableExcelTemplatePerfFix()
0x41e92  ldarg.0
0x41e93  call     bool Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail featureName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x41e98  newobj   instance void class <>f__AnonymousType5`3<string, string, bool>::.ctor(var<u1>, !!T0, var<u1>)
0x41e9d  stelem.ref
0x41e9e  dup
0x41e9f  ldc.i4.s 0xF
0x41ea1  ldstr    aWorddocumentte// "WordDocumentTemplate"
0x41ea6  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41eab  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41eb0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_WordDocumentTemplate()
0x41eb5  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x41eba  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41ebf  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41ec4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_WordDocumentTemplate()
0x41ec9  ldarg.0
0x41eca  call     bool Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail featureName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x41ecf  newobj   instance void class <>f__AnonymousType5`3<string, string, bool>::.ctor(var<u1>, !!T0, var<u1>)
0x41ed4  stelem.ref
0x41ed5  dup
0x41ed6  ldc.i4.s 0x10
0x41ed8  ldstr    aMobileclientte// "MobileClientTelemetry"
0x41edd  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41ee2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41ee7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_MocaTelemetry()
0x41eec  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x41ef1  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41ef6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41efb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_MocaTelemetry()
0x41f00  ldarg.0
0x41f01  call     bool Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail featureName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x41f06  newobj   instance void class <>f__AnonymousType5`3<string, string, bool>::.ctor(var<u1>, !!T0, var<u1>)
0x41f0b  stelem.ref
0x41f0c  dup
0x41f0d  ldc.i4.s 0x11
0x41f0f  ldstr    aCortanaproacti// "CortanaProactiveExperience"
0x41f14  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41f19  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41f1e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_CortanaProactiveExperience()
0x41f23  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x41f28  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41f2d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41f32  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_CortanaProactiveExperience()
0x41f37  ldarg.0
0x41f38  call     bool Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail featureName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x41f3d  newobj   instance void class <>f__AnonymousType5`3<string, string, bool>::.ctor(var<u1>, !!T0, var<u1>)
0x41f42  stelem.ref
0x41f43  dup
0x41f44  ldc.i4.s 0x12
0x41f46  ldstr    aCustomcontrolm// "CustomControlMobile"
0x41f4b  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41f50  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41f55  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_CustomControlMobile()
0x41f5a  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x41f5f  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41f64  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41f69  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_CustomControlMobile()
0x41f6e  ldarg.0
0x41f6f  call     bool Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail featureName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x41f74  newobj   instance void class <>f__AnonymousType5`3<string, string, bool>::.ctor(var<u1>, !!T0, var<u1>)
0x41f79  stelem.ref
0x41f7a  dup
0x41f7b  ldc.i4.s 0x13
0x41f7d  ldstr    aTaskbasedflow_0// "TaskBasedFlow"
0x41f82  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41f87  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41f8c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_TaskBasedFlow()
0x41f91  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x41f96  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41f9b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41fa0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_TaskBasedFlow()
0x41fa5  ldarg.0
0x41fa6  call     bool Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail featureName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x41fab  newobj   instance void class <>f__AnonymousType5`3<string, string, bool>::.ctor(var<u1>, !!T0, var<u1>)
0x41fb0  stelem.ref
0x41fb1  dup
0x41fb2  ldc.i4.s 0x14
0x41fb4  ldstr    aProcessunifica// "ProcessUnification"
0x41fb9  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41fbe  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41fc3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_ProcessUnification()
0x41fc8  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x41fcd  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x41fd2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x41fd7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_ProcessUnification()
0x41fdc  ldarg.0
0x41fdd  call     bool Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail featureName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x41fe2  newobj   instance void class <>f__AnonymousType5`3<string, string, bool>::.ctor(var<u1>, !!T0, var<u1>)
0x41fe7  stelem.ref
0x41fe8  dup
  ... truncated ...
```
