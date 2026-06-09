# Microsoft.Crm.Application.Components.UI.AccessPrivilegeList::.ctor

- ea: `0x145b0`
- end: `0x145df`
- name: `Microsoft.Crm.Application.Components.UI.AccessPrivilegeList::.ctor`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x146b0`
- `0x146d0`
- `0x23840`

## string_xrefs

- `0x145b1`: `ms-crm-AccessRights`
- `0x145cd`: `Mscrm.FormInputControl.AccessPrivilegeBehavior`

## pseudocode

```c

```

## disassembly

```asm
0x145b0  ldarg.0
0x145b1  ldstr    aMsCrmAccessrig// "ms-crm-AccessRights"
0x145b6  stfld    string Microsoft.Crm.Application.Components.UI.AccessPrivilegeList::_className
0x145bb  ldarg.0
0x145bc  call     instance void Microsoft.Crm.Application.Components.UI.CrmFormUIControl::.ctor()
0x145c1  ldarg.0
0x145c2  ldstr    aMscrmNumberatt// "Mscrm.NumberAttribute"
0x145c7  call     instance void Microsoft.Crm.Application.Components.UI.AccessPrivilegeList::set_ClientSideAttributeClassName(string value)
0x145cc  ldarg.0
0x145cd  ldstr    aMscrmForminput_2// "Mscrm.FormInputControl.AccessPrivilegeB"...
0x145d2  call     instance void Microsoft.Crm.Application.Components.UI.AccessPrivilegeList::set_ClientSideFormInputBehaviorClassName(string value)
0x145d7  ldarg.0
0x145d8  ldc.i4.0
0x145d9  stfld    int32 Microsoft.Crm.Application.Components.UI.AccessPrivilegeList::_accessPrivileges
0x145de  ret
```
