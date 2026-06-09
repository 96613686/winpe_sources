# Microsoft.Crm.Security.User::GetAccessRightsFromPrivilegeType

- ea: `0xed40`
- end: `0xedb3`
- name: `Microsoft.Crm.Security.User::GetAccessRightsFromPrivilegeType`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xec60`

## callees

- `0xed40`

## string_xrefs

- `0xed96`: `Invalid privilege type: `
- `0xeda6`: `privilegeType`

## pseudocode

```c

```

## disassembly

```asm
0xed40  ldarg.0
0xed41  switch   loc_ED79, loc_ED86, loc_ED92, loc_ED7E, loc_ED71, loc_ED8A, loc_ED68, loc_ED6C
0xed66  br.s     loc_ED96
0xed68  ldc.i4.4
0xed69  stloc.0
0xed6a  br.s     loc_EDB1
0xed6c  ldc.i4.s 0x10
0xed6e  stloc.0
0xed6f  br.s     loc_EDB1
0xed71  ldc.i4   0x80000
0xed76  stloc.0
0xed77  br.s     loc_EDB1
0xed79  ldc.i4.s 0x20
0xed7b  stloc.0
0xed7c  br.s     loc_EDB1
0xed7e  ldc.i4   0x10000
0xed83  stloc.0
0xed84  br.s     loc_EDB1
0xed86  ldc.i4.1
0xed87  stloc.0
0xed88  br.s     loc_EDB1
0xed8a  ldc.i4   0x40000
0xed8f  stloc.0
0xed90  br.s     loc_EDB1
0xed92  ldc.i4.2
0xed93  stloc.0
0xed94  br.s     loc_EDB1
0xed96  ldstr    aInvalidPrivile// "Invalid privilege type: "
0xed9b  ldarg.0
0xed9c  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType
0xeda1  call     string [mscorlib]System.String::Concat(object, object)
0xeda6  ldstr    aPrivilegetype// "privilegeType"
0xedab  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xedb0  throw
0xedb1  ldloc.0
0xedb2  ret
```
