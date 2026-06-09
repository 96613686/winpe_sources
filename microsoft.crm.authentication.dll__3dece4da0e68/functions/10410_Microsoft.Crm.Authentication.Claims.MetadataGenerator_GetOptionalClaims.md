# Microsoft.Crm.Authentication.Claims.MetadataGenerator::GetOptionalClaims

- ea: `0x10410`
- end: `0x10438`
- name: `Microsoft.Crm.Authentication.Claims.MetadataGenerator::GetOptionalClaims`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xfe90`

## callees

- `0xfef0`
- `0xff00`

## string_xrefs

- `0x10421`: `http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid`

## pseudocode

```c

```

## disassembly

```asm
0x10410  ldarg.0
0x10411  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.IdentityModel]System.IdentityModel.Metadata.DisplayClaim>::.ctor()
0x10416  call     instance void Microsoft.Crm.Authentication.Claims.MetadataGenerator::set_OptionalClaims(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.IdentityModel]System.IdentityModel.Metadata.DisplayClaim> value)
0x1041b  ldarg.0
0x1041c  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.IdentityModel]System.IdentityModel.Metadata.DisplayClaim> Microsoft.Crm.Authentication.Claims.MetadataGenerator::get_OptionalClaims()
0x10421  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/ws/2008/06"...
0x10426  newobj   instance void [System.IdentityModel]System.IdentityModel.Metadata.DisplayClaim::.ctor(string)
0x1042b  dup
0x1042c  ldc.i4.1
0x1042d  callvirt instance void [System.IdentityModel]System.IdentityModel.Metadata.DisplayClaim::set_Optional(bool)
0x10432  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.IdentityModel]System.IdentityModel.Metadata.DisplayClaim>::Add(var<u1>)
0x10437  ret
```
