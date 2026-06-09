# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::Render

- ea: `0x25e10`
- end: `0x25fd5`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::Render`
- size: `453`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x25e10`
- `0x25fe0`
- `0x26020`
- `0x266c0`
- `0x26fe0`
- `0x27210`
- `0x27510`
- `0x27540`

## string_xrefs

- `0x25f35`: `masterComponentId`
- `0x25f11`: `isControlReadOnly`
- `0x25fa1`: `publicLinkPrefix`
- `0x25ec9`: `canCreateEmail`
- `0x25f65`: `isParatureConfigured`
- `0x25f7d`: `isRelevanceSearchConfiguredForKM`
- `0x25eed`: `havePrivilegeForAssociate`
- `0x25ef9`: `havePrivilegeForDisassociate`

## pseudocode

```c

```

## disassembly

```asm
0x25e10  ldarg.0
0x25e11  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_IsBulkEditMode()
0x25e16  brfalse.s loc_25E44
0x25e18  ldarg.1
0x25e19  ldstr    aDivStyleBorder_0// "<div style=\"border:1px solid #6699cc;h"...
0x25e1e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25e23  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x25e28  ldstr    aKmcontrolBulke// "KMControl.BulkEdit.Disabled"
0x25e2d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x25e32  ldarg.1
0x25e33  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x25e38  ldarg.1
0x25e39  ldstr    aDiv_0// "</div>"
0x25e3e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25e43  ret
0x25e44  ldarg.0
0x25e45  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_IsWorkFlowMode()
0x25e4a  brfalse.s loc_25E78
0x25e4c  ldarg.1
0x25e4d  ldstr    aDivStyleBorder_1// "<div style=\"border:1px solid #D6D6D6;h"...
0x25e52  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25e57  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x25e5c  ldstr    aKmcontrolWorkf// "KMControl.WorkFlow.Disabled"
0x25e61  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x25e66  ldarg.1
0x25e67  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x25e6c  ldarg.1
0x25e6d  ldstr    aDiv_0// "</div>"
0x25e72  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25e77  ret
0x25e78  ldarg.0
0x25e79  call     instance void [System.Web]System.Web.UI.Control::EnsureChildControls()
0x25e7e  ldarg.0
0x25e7f  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::SetTabIndexes()
0x25e84  ldarg.0
0x25e85  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_IsHostedInTabbedControl()
0x25e8a  brtrue.s loc_25E93
0x25e8c  ldsfld   string [mscorlib]System.String::Empty
0x25e91  br.s     loc_25E98
0x25e93  ldstr    aKmwallheaderTa// "kmWallHeader-TabbedControl"
0x25e98  stloc.0
0x25e99  ldarg.1
0x25e9a  ldstr    aDivId0ClassScr_0// "<div id=\"{0}\" class=\"scrollingelemen"...
0x25e9f  ldarg.0
0x25ea0  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x25ea5  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x25eaa  ldloc.0
0x25eab  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0x25eb0  ldarg.0
0x25eb1  call     instance valuetype Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidgetContext Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_WidgetContext()
0x25eb6  brtrue   loc_25FB7
0x25ebb  ldarg.0
0x25ebc  ldarg.1
0x25ebd  ldstr    aIskmenabled// "isKMEnabled"
0x25ec2  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::AddAttributes(class [System.Web]System.Web.UI.HtmlTextWriter output, string propertyKeyName)
0x25ec7  ldarg.0
0x25ec8  ldarg.1
0x25ec9  ldstr    aCancreateemail// "canCreateEmail"
0x25ece  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::AddAttributes(class [System.Web]System.Web.UI.HtmlTextWriter output, string propertyKeyName)
0x25ed3  ldarg.0
0x25ed4  ldarg.1
0x25ed5  ldstr    aBlockresult// "blockResult"
0x25eda  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::AddAttributes(class [System.Web]System.Web.UI.HtmlTextWriter output, string propertyKeyName)
0x25edf  ldarg.0
0x25ee0  ldarg.1
0x25ee1  ldstr    aDepartmentid// "departmentId"
0x25ee6  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::AddAttributes(class [System.Web]System.Web.UI.HtmlTextWriter output, string propertyKeyName)
0x25eeb  ldarg.0
0x25eec  ldarg.1
0x25eed  ldstr    aHaveprivilegef// "havePrivilegeForAssociate"
0x25ef2  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::AddAttributes(class [System.Web]System.Web.UI.HtmlTextWriter output, string propertyKeyName)
0x25ef7  ldarg.0
0x25ef8  ldarg.1
0x25ef9  ldstr    aHaveprivilegef_0// "havePrivilegeForDisassociate"
0x25efe  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::AddAttributes(class [System.Web]System.Web.UI.HtmlTextWriter output, string propertyKeyName)
0x25f03  ldarg.0
0x25f04  ldarg.1
0x25f05  ldstr    aIntersecttable// "intersectTableName"
0x25f0a  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::AddAttributes(class [System.Web]System.Web.UI.HtmlTextWriter output, string propertyKeyName)
0x25f0f  ldarg.0
0x25f10  ldarg.1
0x25f11  ldstr    aIscontrolreado// "isControlReadOnly"
0x25f16  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::AddAttributes(class [System.Web]System.Web.UI.HtmlTextWriter output, string propertyKeyName)
0x25f1b  ldarg.0
0x25f1c  ldarg.1
0x25f1d  ldstr    aIshostedintabb// "isHostedInTabbedControl"
0x25f22  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::AddAttributes(class [System.Web]System.Web.UI.HtmlTextWriter output, string propertyKeyName)
0x25f27  ldarg.0
0x25f28  ldarg.1
0x25f29  ldstr    aIsusdcontext// "isUsdContext"
0x25f2e  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::AddAttributes(class [System.Web]System.Web.UI.HtmlTextWriter output, string propertyKeyName)
0x25f33  ldarg.0
0x25f34  ldarg.1
0x25f35  ldstr    aMastercomponen// "masterComponentId"
0x25f3a  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::AddAttributes(class [System.Web]System.Web.UI.HtmlTextWriter output, string propertyKeyName)
0x25f3f  ldarg.0
0x25f40  ldarg.1
0x25f41  ldstr    aReferencedenti// "referencedEntityColumnName"
0x25f46  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::AddAttributes(class [System.Web]System.Web.UI.HtmlTextWriter output, string propertyKeyName)
0x25f4b  ldarg.0
0x25f4c  ldarg.1
0x25f4d  ldstr    aRelationshipna// "relationShipName"
0x25f52  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::AddAttributes(class [System.Web]System.Web.UI.HtmlTextWriter output, string propertyKeyName)
0x25f57  ldarg.0
0x25f58  ldarg.1
0x25f59  ldstr    aSelectprimaryc// "selectPrimaryCustomer"
0x25f5e  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::AddAttributes(class [System.Web]System.Web.UI.HtmlTextWriter output, string propertyKeyName)
0x25f63  ldarg.0
0x25f64  ldarg.1
0x25f65  ldstr    aIsparatureconf// "isParatureConfigured"
0x25f6a  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::AddAttributes(class [System.Web]System.Web.UI.HtmlTextWriter output, string propertyKeyName)
0x25f6f  ldarg.0
0x25f70  ldarg.1
0x25f71  ldstr    aUsenativecrm// "useNativeCrm"
0x25f76  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::AddAttributes(class [System.Web]System.Web.UI.HtmlTextWriter output, string propertyKeyName)
0x25f7b  ldarg.0
0x25f7c  ldarg.1
0x25f7d  ldstr    aIsrelevancesea// "isRelevanceSearchConfiguredForKM"
0x25f82  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::AddAttributes(class [System.Web]System.Web.UI.HtmlTextWriter output, string propertyKeyName)
0x25f87  ldarg.0
0x25f88  ldarg.1
0x25f89  ldstr    aUseexternalpor// "useExternalPortal"
0x25f8e  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::AddAttributes(class [System.Web]System.Web.UI.HtmlTextWriter output, string propertyKeyName)
0x25f93  ldarg.0
0x25f94  ldarg.1
0x25f95  ldstr    aEnableautosugg// "enableAutoSuggestions"
0x25f9a  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::AddAttributes(class [System.Web]System.Web.UI.HtmlTextWriter output, string propertyKeyName)
0x25f9f  ldarg.0
0x25fa0  ldarg.1
0x25fa1  ldstr    aPubliclinkpref// "publicLinkPrefix"
0x25fa6  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::AddAttributes(class [System.Web]System.Web.UI.HtmlTextWriter output, string propertyKeyName)
0x25fab  ldarg.0
0x25fac  ldarg.1
0x25fad  ldstr    aSelectdefaultl// "selectDefaultLanguage"
0x25fb2  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::AddAttributes(class [System.Web]System.Web.UI.HtmlTextWriter output, string propertyKeyName)
0x25fb7  ldarg.1
0x25fb8  ldstr    asc_3033C// ">"
0x25fbd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25fc2  ldarg.0
0x25fc3  ldarg.1
0x25fc4  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::RenderSearchAndFilters(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x25fc9  ldarg.1
0x25fca  ldstr    aDiv_0// "</div>"
0x25fcf  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25fd4  ret
```
