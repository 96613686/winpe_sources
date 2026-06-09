# Microsoft.Crm.Controls.FilterPopup::.ctor

- ea: `0xc8e0`
- end: `0xc95c`
- name: `Microsoft.Crm.Controls.FilterPopup::.ctor`
- size: `124`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0xd1e0`
- `0xd410`
- `0xd640`
- `0xe010`
- `0xe290`
- `0xe4d0`

## callees

- `0xc8e0`
- `0x118d0`
- `0x11b90`

## string_xrefs

- `0xc923`: `attributeXml`

## pseudocode

```c

```

## disassembly

```asm
0xc8e0  ldarg.0
0xc8e1  ldstr    a0// "0"
0xc8e6  stfld    string Microsoft.Crm.Controls.FilterPopup::_tabIndex
0xc8eb  ldarg.0
0xc8ec  call     instance void Microsoft.Crm.Controls.CommandBarPopup::.ctor()
0xc8f1  ldarg.0
0xc8f2  ldarg.3
0xc8f3  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Controls.FilterPopup::_organizationContext
0xc8f8  ldarg.0
0xc8f9  ldarg.1
0xc8fa  stfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Controls.CommandBarControl::_customProperties
0xc8ff  ldarg.0
0xc900  ldarg.0
0xc901  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Controls.CommandBarControl::_customProperties
0xc906  callvirt instance object [mscorlib]System.Collections.Hashtable::Clone()
0xc90b  castclass [mscorlib]System.Collections.Hashtable
0xc910  stfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Controls.FilterPopup::_properties
0xc915  ldarg.2
0xc916  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc91b  brtrue.s loc_C92E
0xc91d  ldarg.0
0xc91e  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Controls.CommandBarControl::get_CustomProperties()
0xc923  ldstr    aAttributexml// "attributeXml"
0xc928  ldarg.2
0xc929  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xc92e  ldarg.1
0xc92f  ldstr    aGridid// "gridid"
0xc934  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xc939  castclass [mscorlib]System.String
0xc93e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc943  brtrue.s loc_C95B
0xc945  ldarg.0
0xc946  ldarg.1
0xc947  ldstr    aGridid// "gridid"
0xc94c  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xc951  castclass [mscorlib]System.String
0xc956  stfld    string Microsoft.Crm.Controls.FilterPopup::_gridId
0xc95b  ret
```
