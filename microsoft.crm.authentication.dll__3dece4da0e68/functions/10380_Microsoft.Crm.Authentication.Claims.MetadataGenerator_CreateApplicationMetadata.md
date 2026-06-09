# Microsoft.Crm.Authentication.Claims.MetadataGenerator::CreateApplicationMetadata

- ea: `0x10380`
- end: `0x103b3`
- name: `Microsoft.Crm.Authentication.Claims.MetadataGenerator::CreateApplicationMetadata`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x10030`
- `0x10110`

## callees

- `0xfeb0`
- `0xfed0`
- `0xfef0`
- `0x10320`
- `0x10380`
- `0x10440`

## pseudocode

```c

```

## disassembly

```asm
0x10380  ldarg.2
0x10381  brtrue.s loc_1038A
0x10383  newobj   instance void [System.IdentityModel]System.IdentityModel.Metadata.ApplicationServiceDescriptor::.ctor()
0x10388  starg.s  2
0x1038a  ldarg.0
0x1038b  ldarg.1
0x1038c  ldarg.2
0x1038d  ldarg.0
0x1038e  call     instance string Microsoft.Crm.Authentication.Claims.MetadataGenerator::get_relyingPartyEncryptionName()
0x10393  call     instance void Microsoft.Crm.Authentication.Claims.MetadataGenerator::SetServiceCertificate(class [System.IdentityModel]System.IdentityModel.Metadata.EntityDescriptor metadata, class [System.IdentityModel]System.IdentityModel.Metadata.ApplicationServiceDescriptor item, string subjectName)
0x10398  ldarg.0
0x10399  ldarg.0
0x1039a  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.IdentityModel]System.IdentityModel.Metadata.DisplayClaim> Microsoft.Crm.Authentication.Claims.MetadataGenerator::get_RequiredClaims()
0x1039f  ldarg.2
0x103a0  call     instance void Microsoft.Crm.Authentication.Claims.MetadataGenerator::AddRequestedClaims(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.IdentityModel]System.IdentityModel.Metadata.DisplayClaim> claims, class [System.IdentityModel]System.IdentityModel.Metadata.ApplicationServiceDescriptor item)
0x103a5  ldarg.0
0x103a6  ldarg.0
0x103a7  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.IdentityModel]System.IdentityModel.Metadata.DisplayClaim> Microsoft.Crm.Authentication.Claims.MetadataGenerator::get_OptionalClaims()
0x103ac  ldarg.2
0x103ad  call     instance void Microsoft.Crm.Authentication.Claims.MetadataGenerator::AddRequestedClaims(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.IdentityModel]System.IdentityModel.Metadata.DisplayClaim> claims, class [System.IdentityModel]System.IdentityModel.Metadata.ApplicationServiceDescriptor item)
0x103b2  ret
```
