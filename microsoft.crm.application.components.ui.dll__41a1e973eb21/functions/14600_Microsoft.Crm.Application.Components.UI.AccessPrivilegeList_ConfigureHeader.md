# Microsoft.Crm.Application.Components.UI.AccessPrivilegeList::ConfigureHeader

- ea: `0x14600`
- end: `0x14657`
- name: `Microsoft.Crm.Application.Components.UI.AccessPrivilegeList::ConfigureHeader`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x3380`
- `0x14600`
- `0x14660`
- `0x146a0`
- `0x146c0`
- `0x238a0`
- `0x238c0`
- `0x23b60`
- `0x23f10`

## string_xrefs

- `0x14629`: `ms-crm-AccessRights`
- `0x1460c`: `/_static/_forms/AccessPrivilegeBehavior.js`

## pseudocode

```c

```

## disassembly

```asm
0x14600  ldarg.0
0x14601  call     instance void Microsoft.Crm.Application.Components.UI.CrmFormUIControl::ConfigureHeader()
0x14606  ldarg.0
0x14607  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1460c  ldstr    aStaticFormsAcc// "/_static/_forms/AccessPrivilegeBehavior"...
0x14611  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x14616  ldarg.0
0x14617  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1461c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x14621  brtrue.s loc_14656
0x14623  ldarg.0
0x14624  call     instance string Microsoft.Crm.Application.Components.UI.AccessPrivilegeList::get_ClassName()
0x14629  ldstr    aMsCrmAccessrig// "ms-crm-AccessRights"
0x1462e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14633  brfalse.s loc_1464A
0x14635  ldarg.0
0x14636  ldarg.0
0x14637  call     instance string Microsoft.Crm.Application.Components.UI.AccessPrivilegeList::get_ClientSideFormInputBehaviorClassName()
0x1463c  ldnull
0x1463d  ldnull
0x1463e  ldnull
0x1463f  ldarg.0
0x14640  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x14645  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string componentTypeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> events, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> references, string elementId)
0x1464a  ldarg.0
0x1464b  ldarg.0
0x1464c  call     instance string Microsoft.Crm.Application.Components.UI.AccessPrivilegeList::get_ClientSideAttributeClassName()
0x14651  call     instance void Microsoft.Crm.Application.Components.UI.CrmFormUIControl::RegisterClientSideControl(string attributeClassName)
0x14656  ret
```
