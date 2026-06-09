# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddEditHiddenDivToTitleContainer

- ea: `0xc280`
- end: `0xc2f5`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddEditHiddenDivToTitleContainer`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xbee0`

## callees

- `0xc280`

## string_xrefs

- `0xc2d0`: `hiddenEditPrivilegeCheck_`

## pseudocode

```c

```

## disassembly

```asm
0xc280  ldarg.0
0xc281  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xc286  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xc28b  stloc.0
0xc28c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xc291  ldstr    aInlineeditdrop// "InlineEditDropDown.Role.Title"
0xc296  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc29b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xc2a0  stloc.1
0xc2a1  ldnull
0xc2a2  stloc.2
0xc2a3  ldstr    aDiv// "div"
0xc2a8  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0xc2ad  dup
0xc2ae  stloc.2
0xc2af  stloc.3
0xc2b0  ldloc.2
0xc2b1  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xc2b6  ldstr    aClass// "class"
0xc2bb  ldstr    aMsCrmHiddenCon// "ms-crm-hidden-container"
0xc2c0  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xc2c5  ldloc.2
0xc2c6  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xc2cb  ldstr    aId// "id"
0xc2d0  ldstr    aHiddeneditpriv// "hiddenEditPrivilegeCheck_"
0xc2d5  ldloc.0
0xc2d6  call     string [mscorlib]System.String::Concat(string, string)
0xc2db  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xc2e0  ldloc.2
0xc2e1  ldloc.1
0xc2e2  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0xc2e7  leave.s  loc_C2F3
0xc2e9  ldloc.3
0xc2ea  brfalse.s loc_C2F2
0xc2ec  ldloc.3
0xc2ed  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc2f2  endfinally
0xc2f3  ldloc.2
0xc2f4  ret
```
