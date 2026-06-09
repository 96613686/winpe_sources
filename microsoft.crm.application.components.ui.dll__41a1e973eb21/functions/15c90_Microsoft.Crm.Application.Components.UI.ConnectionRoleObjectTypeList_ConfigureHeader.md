# Microsoft.Crm.Application.Components.UI.ConnectionRoleObjectTypeList::ConfigureHeader

- ea: `0x15c90`
- end: `0x15d1d`
- name: `Microsoft.Crm.Application.Components.UI.ConnectionRoleObjectTypeList::ConfigureHeader`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3380`
- `0x39f0`
- `0x23b60`
- `0x23f10`
- `0x24080`
- `0x24280`

## string_xrefs

- `0x15cdf`: `readOnly`

## pseudocode

```c

```

## disassembly

```asm
0x15c90  ldarg.0
0x15c91  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::ConfigureHeader()
0x15c96  ldarg.0
0x15c97  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x15c9c  ldstr    aStaticControls_60// "/_static/_controls/connectionroleobject"...
0x15ca1  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0x15ca6  ldarg.0
0x15ca7  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x15cac  ldstr    aStaticControls_61// "/_static/_controls/connectionroleobject"...
0x15cb1  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x15cb6  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x15cbb  stloc.0
0x15cbc  ldloc.0
0x15cbd  ldstr    aRadiobuttonall// "radioButtonAllId"
0x15cc2  ldarg.0
0x15cc3  ldfld    string Microsoft.Crm.Application.Components.UI.ConnectionRoleObjectTypeList::rAllId
0x15cc8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x15ccd  ldloc.0
0x15cce  ldstr    aRadiobuttonsel// "radioButtonSelectedId"
0x15cd3  ldarg.0
0x15cd4  ldfld    string Microsoft.Crm.Application.Components.UI.ConnectionRoleObjectTypeList::rSelectedId
0x15cd9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x15cde  ldloc.0
0x15cdf  ldstr    aReadonly_0// "readOnly"
0x15ce4  ldarg.0
0x15ce5  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControl::get_ReadOnly()
0x15cea  box      [mscorlib]System.Boolean
0x15cef  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x15cf4  ldarg.0
0x15cf5  ldstr    aMscrmForminput_4// "Mscrm.FormInputControl.ConnectionRoleOb"...
0x15cfa  ldloc.0
0x15cfb  ldnull
0x15cfc  ldnull
0x15cfd  ldarg.0
0x15cfe  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x15d03  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string componentTypeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> events, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> references, string elementId)
0x15d08  ldarg.0
0x15d09  ldstr    aMscrmForminput_5// "Mscrm.FormInputControl.ConnectionRoleOb"...
0x15d0e  ldnull
0x15d0f  ldnull
0x15d10  ldnull
0x15d11  ldarg.0
0x15d12  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x15d17  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string componentTypeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> events, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> references, string elementId)
0x15d1c  ret
```
