# Microsoft.Crm.Authentication.Claims.MetadataGenerator::CreateFederationMetadata

- ea: `0x10110`
- end: `0x101cd`
- name: `Microsoft.Crm.Authentication.Claims.MetadataGenerator::CreateFederationMetadata`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xff50`

## callees

- `0xfec0`
- `0x10110`
- `0x101d0`
- `0x10300`
- `0x10380`

## string_xrefs

- `0x101a5`: `http://docs.oasis-open.org/wsfed/federation/200706`

## pseudocode

```c

```

## disassembly

```asm
0x10110  ldarg.0
0x10111  ldarg.1
0x10112  call     instance class [System.IdentityModel]System.IdentityModel.Metadata.EntityDescriptor Microsoft.Crm.Authentication.Claims.MetadataGenerator::CreateDefaultMetadata(class [System]System.Uri uri)
0x10117  stloc.0
0x10118  ldarg.0
0x10119  ldarg.2
0x1011a  call     instance void Microsoft.Crm.Authentication.Claims.MetadataGenerator::set_relyingPartyEncryptionName(string value)
0x1011f  newobj   instance void [System.IdentityModel]System.IdentityModel.Metadata.ApplicationServiceDescriptor::.ctor()
0x10124  stloc.1
0x10125  ldarg.0
0x10126  ldloc.0
0x10127  ldloc.1
0x10128  call     instance void Microsoft.Crm.Authentication.Claims.MetadataGenerator::CreateApplicationMetadata(class [System.IdentityModel]System.IdentityModel.Metadata.EntityDescriptor metadata, class [System.IdentityModel]System.IdentityModel.Metadata.ApplicationServiceDescriptor item)
0x1012d  ldloc.1
0x1012e  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [System.IdentityModel]System.IdentityModel.Protocols.WSTrust.EndpointReference> [System.IdentityModel]System.IdentityModel.Metadata.ApplicationServiceDescriptor::get_Endpoints()
0x10133  ldarg.1
0x10134  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x10139  newobj   instance void [System.IdentityModel]System.IdentityModel.Protocols.WSTrust.EndpointReference::.ctor(string)
0x1013e  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [System.IdentityModel]System.IdentityModel.Protocols.WSTrust.EndpointReference>::Add(var<u1>)
0x10143  ldloc.1
0x10144  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [System.IdentityModel]System.IdentityModel.Protocols.WSTrust.EndpointReference> [System.IdentityModel]System.IdentityModel.Metadata.ApplicationServiceDescriptor::get_PassiveRequestorEndpoints()
0x10149  ldarg.1
0x1014a  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x1014f  newobj   instance void [System.IdentityModel]System.IdentityModel.Protocols.WSTrust.EndpointReference::.ctor(string)
0x10154  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [System.IdentityModel]System.IdentityModel.Protocols.WSTrust.EndpointReference>::Add(var<u1>)
0x10159  ldc.i4.0
0x1015a  call     class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System]System.Uri> Microsoft.Crm.Authentication.Claims.MetadataGenerator::RetrieveAudienceUris(int32 endpointType)
0x1015f  stloc.2
0x10160  ldloc.2
0x10161  brfalse.s loc_1019F
0x10163  ldloc.2
0x10164  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System]System.Uri>::GetEnumerator()
0x10169  stloc.3
0x1016a  br.s     loc_1018B
0x1016c  ldloc.3
0x1016d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System]System.Uri>::get_Current()
0x10172  stloc.s  4
0x10174  ldloc.1
0x10175  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [System.IdentityModel]System.IdentityModel.Protocols.WSTrust.EndpointReference> [System.IdentityModel]System.IdentityModel.Metadata.WebServiceDescriptor::get_TargetScopes()
0x1017a  ldloc.s  4
0x1017c  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x10181  newobj   instance void [System.IdentityModel]System.IdentityModel.Protocols.WSTrust.EndpointReference::.ctor(string)
0x10186  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [System.IdentityModel]System.IdentityModel.Protocols.WSTrust.EndpointReference>::Add(var<u1>)
0x1018b  ldloc.3
0x1018c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x10191  brtrue.s loc_1016C
0x10193  leave.s  loc_1019F
0x10195  ldloc.3
0x10196  brfalse.s loc_1019E
0x10198  ldloc.3
0x10199  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1019e  endfinally
0x1019f  ldloc.1
0x101a0  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [System]System.Uri> [System.IdentityModel]System.IdentityModel.Metadata.RoleDescriptor::get_ProtocolsSupported()
0x101a5  ldstr    aHttpDocsOasisO_1// "http://docs.oasis-open.org/wsfed/federa"...
0x101aa  newobj   instance void [System]System.Uri::.ctor(string)
0x101af  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [System]System.Uri>::Add(var<u1>)
0x101b4  ldloc.0
0x101b5  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [System.IdentityModel]System.IdentityModel.Metadata.RoleDescriptor> [System.IdentityModel]System.IdentityModel.Metadata.EntityDescriptor::get_RoleDescriptors()
0x101ba  ldloc.1
0x101bb  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [System.IdentityModel]System.IdentityModel.Metadata.RoleDescriptor>::Add(var<u1>)
0x101c0  newobj   instance void [System.IdentityModel]System.IdentityModel.Metadata.MetadataSerializer::.ctor()
0x101c5  ldarg.3
0x101c6  ldloc.0
0x101c7  callvirt instance void [System.IdentityModel]System.IdentityModel.Metadata.MetadataSerializer::WriteMetadata(class [mscorlib]System.IO.Stream, class [System.IdentityModel]System.IdentityModel.Metadata.MetadataBase)
0x101cc  ret
```
