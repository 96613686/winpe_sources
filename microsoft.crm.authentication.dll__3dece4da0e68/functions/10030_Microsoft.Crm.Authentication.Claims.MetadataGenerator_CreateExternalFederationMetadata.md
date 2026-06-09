# Microsoft.Crm.Authentication.Claims.MetadataGenerator::CreateExternalFederationMetadata

- ea: `0x10030`
- end: `0x1010b`
- name: `Microsoft.Crm.Authentication.Claims.MetadataGenerator::CreateExternalFederationMetadata`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xffc0`

## callees

- `0xfec0`
- `0x10030`
- `0x101d0`
- `0x10300`
- `0x10380`

## string_xrefs

- `0x100e3`: `http://docs.oasis-open.org/wsfed/federation/200706`

## pseudocode

```c

```

## disassembly

```asm
0x10030  ldarg.0
0x10031  ldarg.1
0x10032  call     instance class [System.IdentityModel]System.IdentityModel.Metadata.EntityDescriptor Microsoft.Crm.Authentication.Claims.MetadataGenerator::CreateDefaultMetadata(class [System]System.Uri uri)
0x10037  stloc.0
0x10038  ldarg.0
0x10039  ldarg.2
0x1003a  call     instance void Microsoft.Crm.Authentication.Claims.MetadataGenerator::set_relyingPartyEncryptionName(string value)
0x1003f  newobj   instance void [System.IdentityModel]System.IdentityModel.Metadata.ApplicationServiceDescriptor::.ctor()
0x10044  stloc.1
0x10045  ldarg.0
0x10046  ldloc.0
0x10047  ldloc.1
0x10048  call     instance void Microsoft.Crm.Authentication.Claims.MetadataGenerator::CreateApplicationMetadata(class [System.IdentityModel]System.IdentityModel.Metadata.EntityDescriptor metadata, class [System.IdentityModel]System.IdentityModel.Metadata.ApplicationServiceDescriptor item)
0x1004d  ldloc.1
0x1004e  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [System.IdentityModel]System.IdentityModel.Protocols.WSTrust.EndpointReference> [System.IdentityModel]System.IdentityModel.Metadata.ApplicationServiceDescriptor::get_Endpoints()
0x10053  ldarg.1
0x10054  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x10059  newobj   instance void [System.IdentityModel]System.IdentityModel.Protocols.WSTrust.EndpointReference::.ctor(string)
0x1005e  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [System.IdentityModel]System.IdentityModel.Protocols.WSTrust.EndpointReference>::Add(var<u1>)
0x10063  ldloc.1
0x10064  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [System.IdentityModel]System.IdentityModel.Protocols.WSTrust.EndpointReference> [System.IdentityModel]System.IdentityModel.Metadata.ApplicationServiceDescriptor::get_PassiveRequestorEndpoints()
0x10069  ldarg.1
0x1006a  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x1006f  newobj   instance void [System.IdentityModel]System.IdentityModel.Protocols.WSTrust.EndpointReference::.ctor(string)
0x10074  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [System.IdentityModel]System.IdentityModel.Protocols.WSTrust.EndpointReference>::Add(var<u1>)
0x10079  ldc.i4.m1
0x1007a  stloc.2
0x1007b  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x10080  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x10085  ldc.i4.2
0x10086  bne.un.s loc_1008C
0x10088  ldc.i4.1
0x10089  stloc.2
0x1008a  br.s     loc_1008E
0x1008c  ldc.i4.2
0x1008d  stloc.2
0x1008e  ldloc.2
0x1008f  ldc.i4.m1
0x10090  ble.s    loc_100DD
0x10092  ldloc.2
0x10093  call     class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System]System.Uri> Microsoft.Crm.Authentication.Claims.MetadataGenerator::RetrieveAudienceUris(int32 endpointType)
0x10098  stloc.3
0x10099  ldloc.3
0x1009a  brfalse.s loc_100DD
0x1009c  ldloc.3
0x1009d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System]System.Uri>::GetEnumerator()
0x100a2  stloc.s  4
0x100a4  br.s     loc_100C6
0x100a6  ldloc.s  4
0x100a8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System]System.Uri>::get_Current()
0x100ad  stloc.s  5
0x100af  ldloc.1
0x100b0  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [System.IdentityModel]System.IdentityModel.Protocols.WSTrust.EndpointReference> [System.IdentityModel]System.IdentityModel.Metadata.WebServiceDescriptor::get_TargetScopes()
0x100b5  ldloc.s  5
0x100b7  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x100bc  newobj   instance void [System.IdentityModel]System.IdentityModel.Protocols.WSTrust.EndpointReference::.ctor(string)
0x100c1  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [System.IdentityModel]System.IdentityModel.Protocols.WSTrust.EndpointReference>::Add(var<u1>)
0x100c6  ldloc.s  4
0x100c8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x100cd  brtrue.s loc_100A6
0x100cf  leave.s  loc_100DD
0x100d1  ldloc.s  4
0x100d3  brfalse.s loc_100DC
0x100d5  ldloc.s  4
0x100d7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x100dc  endfinally
0x100dd  ldloc.1
0x100de  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [System]System.Uri> [System.IdentityModel]System.IdentityModel.Metadata.RoleDescriptor::get_ProtocolsSupported()
0x100e3  ldstr    aHttpDocsOasisO_1// "http://docs.oasis-open.org/wsfed/federa"...
0x100e8  newobj   instance void [System]System.Uri::.ctor(string)
0x100ed  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [System]System.Uri>::Add(var<u1>)
0x100f2  ldloc.0
0x100f3  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [System.IdentityModel]System.IdentityModel.Metadata.RoleDescriptor> [System.IdentityModel]System.IdentityModel.Metadata.EntityDescriptor::get_RoleDescriptors()
0x100f8  ldloc.1
0x100f9  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [System.IdentityModel]System.IdentityModel.Metadata.RoleDescriptor>::Add(var<u1>)
0x100fe  newobj   instance void [System.IdentityModel]System.IdentityModel.Metadata.MetadataSerializer::.ctor()
0x10103  ldarg.3
0x10104  ldloc.0
0x10105  callvirt instance void [System.IdentityModel]System.IdentityModel.Metadata.MetadataSerializer::WriteMetadata(class [mscorlib]System.IO.Stream, class [System.IdentityModel]System.IdentityModel.Metadata.MetadataBase)
0x1010a  ret
```
