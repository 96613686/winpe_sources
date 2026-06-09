# Microsoft.Crm.Authentication.Claims.MetadataGenerator::RetrieveAudienceUris

- ea: `0x101d0`
- end: `0x101ec`
- name: `Microsoft.Crm.Authentication.Claims.MetadataGenerator::RetrieveAudienceUris`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10030`
- `0x10110`

## callees

- `0x101d0`
- `0x101f0`

## pseudocode

```c

```

## disassembly

```asm
0x101d0  ldarg.0
0x101d1  ldc.i4.m1
0x101d2  ble.s    loc_101E1
0x101d4  ldarg.0
0x101d5  ldc.i4.1
0x101d6  call     class [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider [Microsoft.Crm.Core]Microsoft.Crm.WebServices.OrganizationEndpointProviderFactory::Create(int32, bool)
0x101db  call     class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System]System.Uri> Microsoft.Crm.Authentication.Claims.MetadataGenerator::RetrieveAudienceUris(class [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider endpointProvider)
0x101e0  ret
0x101e1  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System]System.Uri>::.ctor()
0x101e6  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System]System.Uri>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0x101eb  ret
```
