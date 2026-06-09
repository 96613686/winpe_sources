# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.OrgInsightsControl::SetUpInnerIFrameControl

- ea: `0x29cb0`
- end: `0x29d93`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.OrgInsightsControl::SetUpInnerIFrameControl`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x29ca0`

## callees

- `0x1bff0`
- `0x1c050`
- `0x1c070`
- `0x1c0a0`
- `0x1c0d0`
- `0x1c150`
- `0x1c670`
- `0x29c40`
- `0x29c60`
- `0x29c80`
- `0x29c90`

## string_xrefs

- `0x29d28`: `orginsightsconfigurationid=`
- `0x29d46`: `&isuserorginsightsconfiguration=`

## pseudocode

```c

```

## disassembly

```asm
0x29cb0  ldarg.0
0x29cb1  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::.ctor()
0x29cb6  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.OrgInsightsControl::set_InnerFrameControl(class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl value)
0x29cbb  ldarg.0
0x29cbc  call     instance class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.OrgInsightsControl::get_InnerFrameControl()
0x29cc1  ldarg.0
0x29cc2  ldfld    bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.OrgInsightsControl::_passParams
0x29cc7  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::set_PassParameters(bool value)
0x29ccc  ldarg.0
0x29ccd  call     instance class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.OrgInsightsControl::get_InnerFrameControl()
0x29cd2  ldc.i4.0
0x29cd3  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::set_Security(bool value)
0x29cd8  ldarg.0
0x29cd9  call     instance class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.OrgInsightsControl::get_InnerFrameControl()
0x29cde  ldtoken  Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ScrollingBehavior
0x29ce3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x29ce8  ldarg.0
0x29ce9  ldfld    valuetype Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ScrollingBehavior Microsoft.Crm.Application.Components.Sdk.FormControls.Web.OrgInsightsControl::_scrolling
0x29cee  box      Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ScrollingBehavior
0x29cf3  call     string [mscorlib]System.Enum::GetName(class [mscorlib]System.Type, object)
0x29cf8  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::set_Scrolling(string value)
0x29cfd  ldarg.0
0x29cfe  call     instance class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.OrgInsightsControl::get_InnerFrameControl()
0x29d03  ldarg.0
0x29d04  ldfld    bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.OrgInsightsControl::_border
0x29d09  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::set_Border(bool value)
0x29d0e  ldarg.0
0x29d0f  call     instance class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.OrgInsightsControl::get_InnerFrameControl()
0x29d14  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x29d19  ldstr    aSandbox_0// "Sandbox"
0x29d1e  ldstr    aAllowScripts// "allow-scripts"
0x29d23  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x29d28  ldstr    aOrginsightscon// "orginsightsconfigurationid="
0x29d2d  ldarg.0
0x29d2e  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.OrgInsightsControl::get_VisualizationId()
0x29d33  stloc.1
0x29d34  ldloca.s 1
0x29d36  constrained. [mscorlib]System.Guid
0x29d3c  callvirt instance string [mscorlib]System.Object::ToString()
0x29d41  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0x29d46  ldstr    aIsuserorginsig// "&isuserorginsightsconfiguration="
0x29d4b  ldarg.0
0x29d4c  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.OrgInsightsControl::get_IsUserChart()
0x29d51  stloc.2
0x29d52  ldloca.s 2
0x29d54  call     instance string [mscorlib]System.Boolean::ToString()
0x29d59  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x29d5e  stloc.0
0x29d5f  ldarg.0
0x29d60  call     instance class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.OrgInsightsControl::get_InnerFrameControl()
0x29d65  ldstr    aToolsAdminOrgi// "/tools/admin/orginsightschart.aspx?"
0x29d6a  ldloc.0
0x29d6b  call     string [mscorlib]System.String::Concat(string, string)
0x29d70  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::set_Url(string value)
0x29d75  ldarg.0
0x29d76  call     instance class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.OrgInsightsControl::get_InnerFrameControl()
0x29d7b  ldc.i4.1
0x29d7c  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::set_UseDelayInitialize(bool value)
0x29d81  ldarg.0
0x29d82  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x29d87  ldarg.0
0x29d88  call     instance class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.OrgInsightsControl::get_InnerFrameControl()
0x29d8d  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x29d92  ret
```
