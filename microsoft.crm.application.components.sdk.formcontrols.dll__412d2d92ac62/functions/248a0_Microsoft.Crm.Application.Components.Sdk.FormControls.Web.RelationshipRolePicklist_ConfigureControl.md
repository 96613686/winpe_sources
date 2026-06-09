# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RelationshipRolePicklist::ConfigureControl

- ea: `0x248a0`
- end: `0x24924`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RelationshipRolePicklist::ConfigureControl`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x17cf0`
- `0x239d0`
- `0x239f0`
- `0x23a60`
- `0x24860`
- `0x24880`
- `0x248a0`
- `0x24930`

## pseudocode

```c

```

## disassembly

```asm
0x248a0  ldarg.0
0x248a1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x248a6  isinst   [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select
0x248ab  dup
0x248ac  ldstr    aPotc// "pOTC"
0x248b1  ldarg.0
0x248b2  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RelationshipRolePicklist::get_PrimaryObjectTypeCode()
0x248b7  stloc.0
0x248b8  ldloca.s 0
0x248ba  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x248bf  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x248c4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddExpando(string, string)
0x248c9  dup
0x248ca  ldstr    aAotc// "aOTC"
0x248cf  ldarg.0
0x248d0  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RelationshipRolePicklist::get_AssociatedObjectTypeCode()
0x248d5  stloc.0
0x248d6  ldloca.s 0
0x248d8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x248dd  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x248e2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddExpando(string, string)
0x248e7  ldarg.0
0x248e8  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RelationshipRolePicklist::get_PrimaryObjectTypeCode()
0x248ed  brfalse.s loc_24903
0x248ef  ldarg.0
0x248f0  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RelationshipRolePicklist::get_AssociatedObjectTypeCode()
0x248f5  brfalse.s loc_24903
0x248f7  ldarg.0
0x248f8  ldarg.0
0x248f9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RelationshipRolePicklist::RetrieveActiveRoles()
0x248fe  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistLookupControl::set_DataEntities(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection value)
0x24903  ldarg.0
0x24904  ldstr    aMsCrmSelectbox_2// "ms-crm-SelectBox-RelationshipRole"
0x24909  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistLookupControl::set_ClassName(string value)
0x2490e  ldsfld   string [mscorlib]System.String::Empty
0x24913  ldsfld   string [mscorlib]System.String::Empty
0x24918  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x2491d  ldarg.0
0x2491e  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistLookupControl::ConfigureControl()
0x24923  ret
```
