# Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::get_RequiredScriptReferencesQueue

- ea: `0xea530`
- end: `0xea6d8`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::get_RequiredScriptReferencesQueue`
- size: `424`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4bae0`

## callees

- `0xea530`

## string_xrefs

- `0xea567`: `/_static/_common/scripts/jquery_ui_1.8.21.min.js`
- `0xea577`: `/_static/_common/scripts/CrmServiceProxyFramework.js`
- `0xea597`: `/_static/_common/scripts/Mscrm.Caching.js`
- `0xea5c7`: `/_static/_common/scripts/InlineEditCommon.js`
- `0xea5e7`: `/_static/_controls/ReadForm/ReadFormUtilities.js`
- `0xea587`: `/_static/_common/scripts/SalesCommonImported.js`
- `0xea5b7`: `/_static/_common/scripts/SalesCommonFramework.js`

## pseudocode

```c

```

## disassembly

```asm
0xea530  ldarg.0
0xea531  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::_requiredScriptsQueue
0xea536  brtrue   loc_EA6D1
0xea53b  ldarg.0
0xea53c  newobj   instance void class [System]System.Collections.Generic.Queue`1<string>::.ctor()
0xea541  stfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::_requiredScriptsQueue
0xea546  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xea54b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xea550  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_UnifiedProcessDesigner()
0xea555  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xea55a  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xea55f  brtrue.s loc_EA571
0xea561  ldarg.0
0xea562  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::_requiredScriptsQueue
0xea567  ldstr    aStaticCommonSc_2// "/_static/_common/scripts/jquery_ui_1.8."...
0xea56c  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xea571  ldarg.0
0xea572  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::_requiredScriptsQueue
0xea577  ldstr    aStaticCommonSc_6// "/_static/_common/scripts/CrmServiceProx"...
0xea57c  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xea581  ldarg.0
0xea582  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::_requiredScriptsQueue
0xea587  ldstr    aStaticCommonSc_35// "/_static/_common/scripts/SalesCommonImp"...
0xea58c  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xea591  ldarg.0
0xea592  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::_requiredScriptsQueue
0xea597  ldstr    aStaticCommonSc_14// "/_static/_common/scripts/Mscrm.Caching."...
0xea59c  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xea5a1  ldarg.0
0xea5a2  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::_requiredScriptsQueue
0xea5a7  ldstr    aStaticControls_22// "/_static/_controls/ProcessControl/Proce"...
0xea5ac  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xea5b1  ldarg.0
0xea5b2  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::_requiredScriptsQueue
0xea5b7  ldstr    aStaticCommonSc_36// "/_static/_common/scripts/SalesCommonFra"...
0xea5bc  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xea5c1  ldarg.0
0xea5c2  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::_requiredScriptsQueue
0xea5c7  ldstr    aStaticCommonSc_24// "/_static/_common/scripts/InlineEditComm"...
0xea5cc  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xea5d1  ldarg.0
0xea5d2  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::_requiredScriptsQueue
0xea5d7  ldstr    aStaticControls_34// "/_static/_controls/inlineedit/InlineEdi"...
0xea5dc  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xea5e1  ldarg.0
0xea5e2  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::_requiredScriptsQueue
0xea5e7  ldstr    aStaticControls_32// "/_static/_controls/ReadForm/ReadFormUti"...
0xea5ec  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xea5f1  ldarg.0
0xea5f2  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::_requiredScriptsQueue
0xea5f7  ldstr    aStaticFormsFor// "/_static/_forms/form.js"
0xea5fc  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xea601  ldarg.0
0xea602  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::_requiredScriptsQueue
0xea607  ldstr    aStaticFormsTex// "/_static/_forms/TextInputBehavior.js"
0xea60c  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xea611  ldarg.0
0xea612  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::_requiredScriptsQueue
0xea617  ldstr    aStaticFormsNum// "/_static/_forms/NumberInputBehavior.js"
0xea61c  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xea621  ldarg.0
0xea622  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::_requiredScriptsQueue
0xea627  ldstr    aStaticFormsSel// "/_static/_forms/select.js"
0xea62c  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xea631  ldarg.0
0xea632  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::_requiredScriptsQueue
0xea637  ldstr    aStaticControls_15// "/_static/_controls/editableselect/edita"...
0xea63c  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xea641  ldarg.0
0xea642  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::_requiredScriptsQueue
0xea647  ldstr    aStaticControls_49// "/_static/_controls/FlyOutDialog/FlyOutD"...
0xea64c  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xea651  ldarg.0
0xea652  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::_requiredScriptsQueue
0xea657  ldstr    aStaticFormsDat// "/_static/_forms/DateTime.js"
0xea65c  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xea661  ldarg.0
0xea662  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::_requiredScriptsQueue
0xea667  ldstr    aStaticControls_50// "/_static/_controls/datetime/time.js"
0xea66c  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xea671  ldarg.0
0xea672  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::_requiredScriptsQueue
0xea677  ldstr    aStaticFormsLoo// "/_static/_forms/LookupBehavior.js"
0xea67c  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xea681  ldarg.0
0xea682  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::_requiredScriptsQueue
0xea687  ldstr    aStaticControls_51// "/_static/_controls/inlineedit/inlineedi"...
0xea68c  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xea691  ldarg.0
0xea692  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::_requiredScriptsQueue
0xea697  ldstr    aStaticGridCmds// "/_static/_grid/cmds/util.js"
0xea69c  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xea6a1  ldarg.0
0xea6a2  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::_requiredScriptsQueue
0xea6a7  ldstr    aStaticToolsSys// "/_static/tools/systemcustomization/scri"...
0xea6ac  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xea6b1  ldarg.0
0xea6b2  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::_requiredScriptsQueue
0xea6b7  ldstr    aStaticToolsSys_2// "/_static/tools/systemcustomization/busi"...
0xea6bc  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xea6c1  ldarg.0
0xea6c2  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::_requiredScriptsQueue
0xea6c7  ldstr    aStaticControls_11// "/_static/_controls/datetime/date.js"
0xea6cc  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xea6d1  ldarg.0
0xea6d2  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.ManageRuleCommonViewModel::_requiredScriptsQueue
0xea6d7  ret
```
