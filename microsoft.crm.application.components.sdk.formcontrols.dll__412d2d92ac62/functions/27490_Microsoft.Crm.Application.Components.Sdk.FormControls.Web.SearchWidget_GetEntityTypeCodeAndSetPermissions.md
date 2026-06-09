# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::GetEntityTypeCodeAndSetPermissions

- ea: `0x27490`
- end: `0x27508`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::GetEntityTypeCodeAndSetPermissions`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x272a0`

## callees

- `0x27490`
- `0x27550`
- `0x27680`

## string_xrefs

- `0x2749f`: `havePrivilegeForAssociate`
- `0x274e5`: `havePrivilegeForAssociate`
- `0x274c1`: `havePrivilegeForDisassociate`
- `0x274f6`: `havePrivilegeForDisassociate`

## pseudocode

```c

```

## disassembly

```asm
0x27490  ldarg.0
0x27491  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_EntityTypeCode()
0x27496  ldc.i4.0
0x27497  ble.s    loc_274DF
0x27499  ldarg.0
0x2749a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x2749f  ldstr    aHaveprivilegef// "havePrivilegeForAssociate"
0x274a4  ldarg.0
0x274a5  ldarg.0
0x274a6  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_EntityTypeCode()
0x274ab  ldc.i4.1
0x274ac  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::RetrieveParentAndArticleEntityPermissions(int32 entityTypeCode, bool forAssociate)
0x274b1  box      [mscorlib]System.Boolean
0x274b6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x274bb  ldarg.0
0x274bc  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x274c1  ldstr    aHaveprivilegef_0// "havePrivilegeForDisassociate"
0x274c6  ldarg.0
0x274c7  ldarg.0
0x274c8  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_EntityTypeCode()
0x274cd  ldc.i4.0
0x274ce  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::RetrieveParentAndArticleEntityPermissions(int32 entityTypeCode, bool forAssociate)
0x274d3  box      [mscorlib]System.Boolean
0x274d8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x274dd  br.s     loc_27501
0x274df  ldarg.0
0x274e0  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x274e5  ldstr    aHaveprivilegef// "havePrivilegeForAssociate"
0x274ea  ldnull
0x274eb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x274f0  ldarg.0
0x274f1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::properties
0x274f6  ldstr    aHaveprivilegef_0// "havePrivilegeForDisassociate"
0x274fb  ldnull
0x274fc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x27501  ldarg.0
0x27502  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_EntityTypeCode()
0x27507  ret
```
