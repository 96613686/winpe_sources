# Microsoft.Crm.Authentication.Claims.MetadataGenerator::GetRequiredClaims

- ea: `0x103c0`
- end: `0x10406`
- name: `Microsoft.Crm.Authentication.Claims.MetadataGenerator::GetRequiredClaims`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0xfe90`

## callees

- `0xfed0`
- `0xfee0`

## string_xrefs

- `0x103ef`: `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name`

## pseudocode

```c

```

## disassembly

```asm
0x103c0  ldarg.0
0x103c1  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.IdentityModel]System.IdentityModel.Metadata.DisplayClaim>::.ctor()
0x103c6  call     instance void Microsoft.Crm.Authentication.Claims.MetadataGenerator::set_RequiredClaims(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.IdentityModel]System.IdentityModel.Metadata.DisplayClaim> value)
0x103cb  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.ClaimTypes::get_IdentityClaimType()
0x103d0  newobj   instance void [System.IdentityModel]System.IdentityModel.Metadata.DisplayClaim::.ctor(string)
0x103d5  stloc.0
0x103d6  ldloc.0
0x103d7  ldc.i4.0
0x103d8  callvirt instance void [System.IdentityModel]System.IdentityModel.Metadata.DisplayClaim::set_Optional(bool)
0x103dd  ldarg.0
0x103de  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.IdentityModel]System.IdentityModel.Metadata.DisplayClaim> Microsoft.Crm.Authentication.Claims.MetadataGenerator::get_RequiredClaims()
0x103e3  ldloc.0
0x103e4  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.IdentityModel]System.IdentityModel.Metadata.DisplayClaim>::Add(var<u1>)
0x103e9  ldarg.0
0x103ea  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.IdentityModel]System.IdentityModel.Metadata.DisplayClaim> Microsoft.Crm.Authentication.Claims.MetadataGenerator::get_RequiredClaims()
0x103ef  ldstr    aHttpSchemasXml_0// "http://schemas.xmlsoap.org/ws/2005/05/i"...
0x103f4  newobj   instance void [System.IdentityModel]System.IdentityModel.Metadata.DisplayClaim::.ctor(string)
0x103f9  dup
0x103fa  ldc.i4.0
0x103fb  callvirt instance void [System.IdentityModel]System.IdentityModel.Metadata.DisplayClaim::set_Optional(bool)
0x10400  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.IdentityModel]System.IdentityModel.Metadata.DisplayClaim>::Add(var<u1>)
0x10405  ret
```
