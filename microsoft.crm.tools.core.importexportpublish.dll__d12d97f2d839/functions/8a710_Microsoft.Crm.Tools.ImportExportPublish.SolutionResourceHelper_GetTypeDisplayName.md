# Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetTypeDisplayName

- ea: `0x8a710`
- end: `0x8aba7`
- name: `Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetTypeDisplayName`
- size: `1175`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x3b230`

## callees

- `0x8a710`
- `0x8abb0`

## string_xrefs

- `0x8a8e9`: `Object_Singular_SolutionComponentAttribute`
- `0x8a919`: `Object_Singular_ComplexControl`
- `0x8a931`: `Object_Singular_ContractTemplate`
- `0x8a9c1`: `Object_Singular_FieldSecurityProfile`
- `0x8a9cd`: `Object_Singular_KbArticleTemplate`
- `0x8a9e5`: `Object_Singular_MailMergeTemplate`
- `0x8aa21`: `Object_Singular_PluginAssembly`
- `0x8aa2d`: `Object_Singular_PluginType`
- `0x8aa8d`: `Object_Singular_RibbonCommand`
- `0x8aac9`: `Object_Singular_RibbonTabToCommandMap`
- `0x8aae1`: `Object_Singular_RolePrivileges`
- `0x8ab35`: `Object_Singular_ServiceEndpoint`
- `0x8ab71`: `Object_Singular_Template`

## pseudocode

```c

```

## disassembly

```asm
0x8a710  ldarg.0
0x8a711  ldc.i4.1
0x8a712  sub
0x8a713  switch   loc_8A979, loc_8A8E9, loc_8AA45, loc_8A90D, loc_8A8F5, loc_8AB7D, loc_8A9D9, loc_8AA51, loc_8A9FD, loc_8A991, loc_8A9A9, loc_8A99D, loc_8A9F1, loc_8ABA1, loc_8ABA1, loc_8ABA1, loc_8ABA1, loc_8ABA1, loc_8ABA1, loc_8AAD5, loc_8AAE1, loc_8A961, loc_8A96D, loc_8AA15, loc_8AA09, loc_8AB05, loc_8ABA1, loc_8ABA1, loc_8AB95, loc_8AA39, loc_8AA5D, loc_8AA75, loc_8AA69, loc_8AA81, loc_8A8D1, loc_8AB71, loc_8A931, loc_8A9CD, loc_8A9E5, loc_8ABA1, loc_8ABA1, loc_8ABA1, loc_8ABA1, loc_8ABA1, loc_8ABA1, loc_8A985, loc_8A901, loc_8AA8D, loc_8AA99, loc_8AAA5, loc_8ABA1, loc_8AABD, loc_8AAC9, loc_8ABA1, loc_8AAB1 \
0x8a894  ldarg.0
0x8a895  ldc.i4   0x96
0x8a89a  sub
0x8a89b  switch   loc_8AAED, loc_8AAF9, loc_8AB4D, loc_8AB59, loc_8A93D, loc_8A949, loc_8ABA1, loc_8ABA1, loc_8ABA1, loc_8ABA1, loc_8A955
0x8a8cc  br       loc_8ABA1
0x8a8d1  ldstr    aObjectSingular// "Object_Singular_ActivityMimeAttachment"
0x8a8d6  ldarg.1
0x8a8d7  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8a8dc  ret
0x8a8dd  ldstr    aObjectSingular_0// "Object_Singular_AppModule"
0x8a8e2  ldarg.1
0x8a8e3  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8a8e8  ret
0x8a8e9  ldstr    aObjectSingular_1// "Object_Singular_SolutionComponentAttrib"...
0x8a8ee  ldarg.1
0x8a8ef  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8a8f4  ret
0x8a8f5  ldstr    aObjectSingular_2// "Object_Singular_AttributeLookupValue"
0x8a8fa  ldarg.1
0x8a8fb  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8a900  ret
0x8a901  ldstr    aObjectSingular_3// "Object_Singular_AttributeMap"
0x8a906  ldarg.1
0x8a907  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8a90c  ret
0x8a90d  ldstr    aObjectSingular_4// "Object_Singular_AttributePicklistValue"
0x8a912  ldarg.1
0x8a913  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8a918  ret
0x8a919  ldstr    aObjectSingular_5// "Object_Singular_ComplexControl"
0x8a91e  ldarg.1
0x8a91f  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8a924  ret
0x8a925  ldstr    aObjectSingular_6// "Object_Singular_ConnectionRole"
0x8a92a  ldarg.1
0x8a92b  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8a930  ret
0x8a931  ldstr    aObjectSingular_7// "Object_Singular_ContractTemplate"
0x8a936  ldarg.1
0x8a937  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8a93c  ret
0x8a93d  ldstr    aObjectSingular_8// "Object_Singular_ConvertRule"
0x8a942  ldarg.1
0x8a943  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8a948  ret
0x8a949  ldstr    aObjectSingular_9// "Object_Singular_ConvertRuleItem"
0x8a94e  ldarg.1
0x8a94f  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8a954  ret
0x8a955  ldstr    aObjectSingular_10// "Object_Singular_DependencyFeature"
0x8a95a  ldarg.1
0x8a95b  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8a960  ret
0x8a961  ldstr    aObjectSingular_11// "Object_Singular_DisplayString"
0x8a966  ldarg.1
0x8a967  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8a96c  ret
0x8a96d  ldstr    aObjectSingular_12// "Object_Singular_DisplayStringMap"
0x8a972  ldarg.1
0x8a973  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8a978  ret
0x8a979  ldstr    aObjectSingular_13// "Object_Singular_Entity"
0x8a97e  ldarg.1
0x8a97f  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8a984  ret
0x8a985  ldstr    aObjectSingular_14// "Object_Singular_EntityMap"
0x8a98a  ldarg.1
0x8a98b  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8a990  ret
0x8a991  ldstr    aObjectSingular_15// "Object_Singular_EntityRelationship"
0x8a996  ldarg.1
0x8a997  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8a99c  ret
0x8a99d  ldstr    aObjectSingular_16// "Object_Singular_EntityRelationshipRelat"...
0x8a9a2  ldarg.1
0x8a9a3  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8a9a8  ret
0x8a9a9  ldstr    aObjectSingular_17// "Object_Singular_EntityRelationshipRole"
0x8a9ae  ldarg.1
0x8a9af  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8a9b4  ret
0x8a9b5  ldstr    aObjectSingular_18// "Object_Singular_FieldPermission"
0x8a9ba  ldarg.1
0x8a9bb  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8a9c0  ret
0x8a9c1  ldstr    aObjectSingular_19// "Object_Singular_FieldSecurityProfile"
0x8a9c6  ldarg.1
0x8a9c7  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8a9cc  ret
0x8a9cd  ldstr    aObjectSingular_20// "Object_Singular_KbArticleTemplate"
0x8a9d2  ldarg.1
0x8a9d3  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8a9d8  ret
0x8a9d9  ldstr    aObjectSingular_21// "Object_Singular_LocalizedLabel"
0x8a9de  ldarg.1
0x8a9df  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8a9e4  ret
0x8a9e5  ldstr    aObjectSingular_22// "Object_Singular_MailMergeTemplate"
0x8a9ea  ldarg.1
0x8a9eb  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8a9f0  ret
0x8a9f1  ldstr    aObjectSingular_23// "Object_Singular_ManagedProperty"
0x8a9f6  ldarg.1
0x8a9f7  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8a9fc  ret
0x8a9fd  ldstr    aObjectSingular_24// "Object_Singular_OptionSet"
0x8aa02  ldarg.1
0x8aa03  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8aa08  ret
0x8aa09  ldstr    aObjectSingular_25// "Object_Singular_Organization"
0x8aa0e  ldarg.1
0x8aa0f  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8aa14  ret
0x8aa15  ldstr    aObjectSingular_26// "Object_Singular_OrganizationUI"
0x8aa1a  ldarg.1
0x8aa1b  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8aa20  ret
0x8aa21  ldstr    aObjectSingular_27// "Object_Singular_PluginAssembly"
0x8aa26  ldarg.1
0x8aa27  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8aa2c  ret
0x8aa2d  ldstr    aObjectSingular_28// "Object_Singular_PluginType"
0x8aa32  ldarg.1
0x8aa33  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8aa38  ret
0x8aa39  ldstr    aObjectSingular_29// "Object_Singular_ProcessTrigger"
0x8aa3e  ldarg.1
0x8aa3f  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8aa44  ret
0x8aa45  ldstr    aObjectSingular_30// "Object_Singular_Relationship"
0x8aa4a  ldarg.1
0x8aa4b  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8aa50  ret
0x8aa51  ldstr    aObjectSingular_31// "Object_Singular_RelationshipExtraCondit"...
0x8aa56  ldarg.1
0x8aa57  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8aa5c  ret
0x8aa5d  ldstr    aObjectSingular_32// "Object_Singular_Report"
0x8aa62  ldarg.1
0x8aa63  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8aa68  ret
0x8aa69  ldstr    aObjectSingular_33// "Object_Singular_ReportCategory"
0x8aa6e  ldarg.1
0x8aa6f  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8aa74  ret
0x8aa75  ldstr    aObjectSingular_34// "Object_Singular_ReportEntity"
0x8aa7a  ldarg.1
0x8aa7b  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8aa80  ret
0x8aa81  ldstr    aObjectSingular_35// "Object_Singular_ReportVisibility"
0x8aa86  ldarg.1
0x8aa87  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8aa8c  ret
0x8aa8d  ldstr    aObjectSingular_36// "Object_Singular_RibbonCommand"
0x8aa92  ldarg.1
0x8aa93  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8aa98  ret
0x8aa99  ldstr    aObjectSingular_37// "Object_Singular_RibbonContextGroup"
0x8aa9e  ldarg.1
0x8aa9f  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8aaa4  ret
0x8aaa5  ldstr    aObjectSingular_38// "Object_Singular_RibbonCustomization"
0x8aaaa  ldarg.1
0x8aaab  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8aab0  ret
0x8aab1  ldstr    aObjectSingular_39// "Object_Singular_RibbonDiff"
0x8aab6  ldarg.1
0x8aab7  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8aabc  ret
0x8aabd  ldstr    aObjectSingular_40// "Object_Singular_RibbonRule"
0x8aac2  ldarg.1
0x8aac3  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8aac8  ret
0x8aac9  ldstr    aObjectSingular_41// "Object_Singular_RibbonTabToCommandMap"
0x8aace  ldarg.1
0x8aacf  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8aad4  ret
0x8aad5  ldstr    aObjectSingular_42// "Object_Singular_Role"
0x8aada  ldarg.1
0x8aadb  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8aae0  ret
0x8aae1  ldstr    aObjectSingular_43// "Object_Singular_RolePrivileges"
0x8aae6  ldarg.1
0x8aae7  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8aaec  ret
0x8aaed  ldstr    aObjectSingular_44// "Object_Singular_RoutingRule"
0x8aaf2  ldarg.1
0x8aaf3  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8aaf8  ret
0x8aaf9  ldstr    aObjectSingular_45// "Object_Singular_RoutingRuleItem"
0x8aafe  ldarg.1
0x8aaff  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8ab04  ret
0x8ab05  ldstr    aObjectSingular_46// "Object_Singular_SavedQuery"
0x8ab0a  ldarg.1
0x8ab0b  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8ab10  ret
0x8ab11  ldstr    aObjectSingular_47// "Object_Singular_SavedQueryVisualization"
0x8ab16  ldarg.1
0x8ab17  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8ab1c  ret
0x8ab1d  ldstr    aObjectSingular_48// "Object_Singular_SdkMessageProcessingSte"...
0x8ab22  ldarg.1
0x8ab23  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8ab28  ret
0x8ab29  ldstr    aObjectSingular_49// "Object_Singular_SdkMessageProcessingSte"...
0x8ab2e  ldarg.1
0x8ab2f  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8ab34  ret
0x8ab35  ldstr    aObjectSingular_50// "Object_Singular_ServiceEndpoint"
0x8ab3a  ldarg.1
0x8ab3b  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8ab40  ret
0x8ab41  ldstr    aObjectSingular_51// "Object_Singular_SiteMap"
0x8ab46  ldarg.1
0x8ab47  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8ab4c  ret
0x8ab4d  ldstr    aObjectSingular_52// "Object_Singular_SLA"
0x8ab52  ldarg.1
0x8ab53  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8ab58  ret
0x8ab59  ldstr    aObjectSingular_53// "Object_Singular_SLAItem"
0x8ab5e  ldarg.1
0x8ab5f  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8ab64  ret
0x8ab65  ldstr    aObjectSingular_54// "Object_Singular_SystemForm"
0x8ab6a  ldarg.1
0x8ab6b  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8ab70  ret
0x8ab71  ldstr    aObjectSingular_55// "Object_Singular_Template"
0x8ab76  ldarg.1
0x8ab77  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8ab7c  ret
0x8ab7d  ldstr    aObjectSingular_56// "Object_Singular_ViewAttribute"
0x8ab82  ldarg.1
0x8ab83  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8ab88  ret
0x8ab89  ldstr    aObjectSingular_57// "Object_Singular_WebResource"
0x8ab8e  ldarg.1
0x8ab8f  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8ab94  ret
0x8ab95  ldstr    aObjectSingular_58// "Object_Singular_Workflow"
0x8ab9a  ldarg.1
0x8ab9b  call     string Microsoft.Crm.Tools.ImportExportPublish.SolutionResourceHelper::GetResourceString(string resourceKey, bool usingEncode)
0x8aba0  ret
0x8aba1  ldsfld   string [mscorlib]System.String::Empty
0x8aba6  ret
```
