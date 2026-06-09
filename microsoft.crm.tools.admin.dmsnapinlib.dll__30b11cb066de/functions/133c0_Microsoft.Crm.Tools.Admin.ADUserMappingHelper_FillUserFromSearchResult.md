# Microsoft.Crm.Tools.Admin.ADUserMappingHelper::FillUserFromSearchResult

- ea: `0x133c0`
- end: `0x13411`
- name: `Microsoft.Crm.Tools.Admin.ADUserMappingHelper::FillUserFromSearchResult`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x13200`

## callees

- `0x133c0`
- `0x13420`

## string_xrefs

- `0x133d5`: `Wrong filter used during the search in Active Directory resulted in this error. `

## pseudocode

```c

```

## disassembly

```asm
0x133c0  ldarg.0
0x133c1  brtrue.s loc_133CA
0x133c3  ldc.i4.0
0x133c4  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.SearchBadUserCountError::.ctor(int32)
0x133c9  ret
0x133ca  nop
0x133cb  ldarg.0
0x133cc  callvirt instance int32 [System.DirectoryServices]System.DirectoryServices.SearchResultCollection::get_Count()
0x133d1  stloc.0
0x133d2  leave.s  loc_133ED
0x133d4  stloc.1
0x133d5  ldstr    aWrongFilterUse// "Wrong filter used during the search in "...
0x133da  ldc.i4.1
0x133db  newarr   [mscorlib]System.Object
0x133e0  dup
0x133e1  ldc.i4.0
0x133e2  ldloc.1
0x133e3  stelem.ref
0x133e4  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarning(string, object[])
0x133e9  ldc.i4.0
0x133ea  stloc.0
0x133eb  leave.s  loc_133ED
0x133ed  ldc.i4.1
0x133ee  ldloc.0
0x133ef  bne.un.s loc_13405
0x133f1  ldarg.0
0x133f2  ldc.i4.0
0x133f3  callvirt instance class [System.DirectoryServices]System.DirectoryServices.SearchResult [System.DirectoryServices]System.DirectoryServices.SearchResultCollection::get_Item(int32)
0x133f8  ldarg.1
0x133f9  call     void Microsoft.Crm.Tools.Admin.ADUserMappingHelper::FillUserFromSearchResult(class [System.DirectoryServices]System.DirectoryServices.SearchResult sr, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User user)
0x133fe  ldarg.1
0x133ff  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.SearchSuccess::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User)
0x13404  ret
0x13405  ldarg.0
0x13406  callvirt instance int32 [System.DirectoryServices]System.DirectoryServices.SearchResultCollection::get_Count()
0x1340b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.SearchBadUserCountError::.ctor(int32)
0x13410  ret
```
