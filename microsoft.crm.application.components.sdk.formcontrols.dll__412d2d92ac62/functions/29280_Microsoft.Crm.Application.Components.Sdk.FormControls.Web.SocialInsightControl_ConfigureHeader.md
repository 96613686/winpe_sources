# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::ConfigureHeader

- ea: `0x29280`
- end: `0x29377`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::ConfigureHeader`
- size: `247`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x17950`
- `0x17aa0`
- `0x29280`
- `0x29a70`
- `0x29b00`

## string_xrefs

- `0x292d4`: `/_static/_common/scripts/SalesCommonImported.js`
- `0x292e4`: `/_static/_common/scripts/SalesCrmSoapProxyService.js`

## pseudocode

```c

```

## disassembly

```asm
0x29280  ldarg.0
0x29281  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::ConfigureHeader()
0x29286  ldarg.0
0x29287  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2928c  ldc.i4.1
0x2928d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0x29292  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x29297  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x2929c  stloc.2
0x2929d  ldloca.s 2
0x2929f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x292a4  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x292a9  stloc.0
0x292aa  ldarg.0
0x292ab  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x292b0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x292b5  ldstr    aStaticCss0Soci// "/_static/css/{0}/SocialInsights.css"
0x292ba  ldc.i4.1
0x292bb  newarr   [mscorlib]System.Object
0x292c0  dup
0x292c1  ldc.i4.0
0x292c2  ldloc.0
0x292c3  stelem.ref
0x292c4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x292c9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x292ce  ldarg.0
0x292cf  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x292d4  ldstr    aStaticCommonSc_0// "/_static/_common/scripts/SalesCommonImp"...
0x292d9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x292de  ldarg.0
0x292df  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x292e4  ldstr    aStaticCommonSc_3// "/_static/_common/scripts/SalesCrmSoapPr"...
0x292e9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x292ee  ldarg.0
0x292ef  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x292f4  ldstr    aStaticControls_23// "/_static/_controls/SocialInsights/Socia"...
0x292f9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x292fe  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x29303  stloc.1
0x29304  ldarg.0
0x29305  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::get_IsWorkflowEditorPage()
0x2930a  brtrue.s loc_29376
0x2930c  ldloc.1
0x2930d  ldstr    aControlid// "ControlId"
0x29312  ldarg.0
0x29313  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x29318  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2931d  ldloc.1
0x2931e  ldstr    aFormid// "FormId"
0x29323  ldarg.0
0x29324  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_CurrentFormDescriptor()
0x29329  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor::get_ID()
0x2932e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x29333  ldloc.1
0x29334  ldstr    aFormtype// "FormType"
0x29339  ldarg.0
0x2933a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_CurrentFormDescriptor()
0x2933f  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor::get_IsUserForm()
0x29344  brtrue.s loc_2934D
0x29346  ldc.i4   0x406
0x2934b  br.s     loc_29352
0x2934d  ldc.i4   0x407
0x29352  box      [mscorlib]System.Int32
0x29357  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2935c  ldarg.0
0x2935d  ldstr    aMscrmSocialins// "Mscrm.SocialInsights.Runtime.Controls.S"...
0x29362  ldloc.1
0x29363  ldnull
0x29364  ldnull
0x29365  ldarg.0
0x29366  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x2936b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string)
0x29370  ldarg.0
0x29371  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::SetClientVariables()
0x29376  ret
```
