# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::RegisterClientSideControl_0

- ea: `0x18140`
- end: `0x18229`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::RegisterClientSideControl_0`
- size: `233`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18130`
- `0x1b280`

## callees

- `0x17ea0`
- `0x17ef0`
- `0x17f30`
- `0x180c0`
- `0x180e0`
- `0x18140`

## string_xrefs

- `0x181f2`: `userPrivilegeMask`

## pseudocode

```c

```

## disassembly

```asm
0x18140  ldarg.1
0x18141  ldstr    aAttributeclass// "attributeClassName"
0x18146  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1814b  ldarg.2
0x1814c  ldstr    aControlclassna// "controlClassName"
0x18151  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x18156  ldarg.0
0x18157  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::get_ClientSideAttributeId()
0x1815c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x18161  brtrue   loc_18228
0x18166  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x1816b  stloc.0
0x1816c  ldloc.0
0x1816d  ldstr    aAttribute// "attribute"
0x18172  ldarg.0
0x18173  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::get_ClientSideAttributeId()
0x18178  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x1817d  ldarg.0
0x1817e  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x18183  ldarg.2
0x18184  ldnull
0x18185  ldnull
0x18186  ldloc.0
0x18187  ldarg.0
0x18188  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1818d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string)
0x18192  ldarg.0
0x18193  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::get_RegisterClientSideAttribute()
0x18198  brfalse  loc_18228
0x1819d  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x181a2  stloc.1
0x181a3  ldloc.1
0x181a4  ldstr    aId// "id"
0x181a9  ldarg.0
0x181aa  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::get_ClientSideAttributeId()
0x181af  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x181b4  ldloc.1
0x181b5  ldstr    aName// "name"
0x181ba  ldarg.0
0x181bb  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::_metadata
0x181c0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x181c5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x181ca  ldarg.0
0x181cb  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::get_IsSecuredCreate()
0x181d0  brtrue.s loc_181D5
0x181d2  ldc.i4.1
0x181d3  br.s     loc_181D6
0x181d5  ldc.i4.0
0x181d6  ldarg.0
0x181d7  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::get_IsSecuredRead()
0x181dc  brtrue.s loc_181E1
0x181de  ldc.i4.2
0x181df  br.s     loc_181E2
0x181e1  ldc.i4.0
0x181e2  or
0x181e3  ldarg.0
0x181e4  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::get_IsSecuredUpdate()
0x181e9  brtrue.s loc_181EE
0x181eb  ldc.i4.4
0x181ec  br.s     loc_181EF
0x181ee  ldc.i4.0
0x181ef  or
0x181f0  stloc.2
0x181f1  ldloc.1
0x181f2  ldstr    aUserprivilegem// "userPrivilegeMask"
0x181f7  ldloc.2
0x181f8  box      Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FormDataAttributePrivileges
0x181fd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x18202  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x18207  stloc.3
0x18208  ldloc.3
0x18209  ldstr    aParent// "parent"
0x1820e  ldstr    aPrimaryentity// "PrimaryEntity"
0x18213  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x18218  ldarg.0
0x18219  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1821e  ldarg.1
0x1821f  ldloc.1
0x18220  ldnull
0x18221  ldloc.3
0x18222  ldnull
0x18223  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string)
0x18228  ret
```
