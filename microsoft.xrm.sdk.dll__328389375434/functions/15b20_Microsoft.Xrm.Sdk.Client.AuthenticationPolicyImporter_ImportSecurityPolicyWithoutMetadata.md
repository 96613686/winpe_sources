# Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ImportSecurityPolicyWithoutMetadata

- ea: `0x15b20`
- end: `0x15ba6`
- name: `Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ImportSecurityPolicyWithoutMetadata`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x15ab0`

## callees

- `0x15b20`
- `0x15bb0`

## string_xrefs

- `0x15b26`: `http://schemas.xmlsoap.org/ws/2005/05/identity/issuer/self`

## pseudocode

```c

```

## disassembly

```asm
0x15b20  ldarg.2
0x15b21  call     void Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::RemoveIssuerMetadataForOnline(class [System.ServiceModel]System.ServiceModel.Description.PolicyConversionContext context)
0x15b26  ldstr    aHttpSchemasXml_0// "http://schemas.xmlsoap.org/ws/2005/05/i"...
0x15b2b  newobj   instance void [System]System.Uri::.ctor(string)
0x15b30  ldc.i4.0
0x15b31  newarr   [System.ServiceModel]System.ServiceModel.Channels.AddressHeader
0x15b36  newobj   instance void [System.ServiceModel]System.ServiceModel.EndpointAddress::.ctor(class [System]System.Uri, class [System.ServiceModel]System.ServiceModel.Channels.AddressHeader[])
0x15b3b  newobj   instance void [System.ServiceModel]System.ServiceModel.Description.MetadataExchangeClient::.ctor(class [System.ServiceModel]System.ServiceModel.EndpointAddress)
0x15b40  stloc.0
0x15b41  ldloc.0
0x15b42  ldc.i4.0
0x15b43  callvirt instance void [System.ServiceModel]System.ServiceModel.Description.MetadataExchangeClient::set_ResolveMetadataReferences(bool)
0x15b48  ldarg.0
0x15b49  ldfld    object Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::_lockObject
0x15b4e  stloc.1
0x15b4f  ldc.i4.0
0x15b50  stloc.2
0x15b51  ldloc.1
0x15b52  ldloca.s 2
0x15b54  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x15b59  ldarg.1
0x15b5a  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<object, object> [System.ServiceModel]System.ServiceModel.Description.MetadataImporter::get_State()
0x15b5f  brfalse.s loc_15B72
0x15b61  ldarg.1
0x15b62  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<object, object> [System.ServiceModel]System.ServiceModel.Description.MetadataImporter::get_State()
0x15b67  ldstr    aMetadataexchan// "MetadataExchangeClientKey"
0x15b6c  ldloc.0
0x15b6d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<object, object>::set_Item(var<u1>, !!T0)
0x15b72  ldarg.0
0x15b73  ldfld    class [System.ServiceModel]System.ServiceModel.Description.IPolicyImportExtension Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::_importer
0x15b78  ldarg.1
0x15b79  ldarg.2
0x15b7a  callvirt instance void [System.ServiceModel]System.ServiceModel.Description.IPolicyImportExtension::ImportPolicy(class [System.ServiceModel]System.ServiceModel.Description.MetadataImporter, class [System.ServiceModel]System.ServiceModel.Description.PolicyConversionContext)
0x15b7f  leave.s  loc_15BA5
0x15b81  ldarg.1
0x15b82  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<object, object> [System.ServiceModel]System.ServiceModel.Description.MetadataImporter::get_State()
0x15b87  brfalse.s loc_15B9A
0x15b89  ldarg.1
0x15b8a  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<object, object> [System.ServiceModel]System.ServiceModel.Description.MetadataImporter::get_State()
0x15b8f  ldstr    aMetadataexchan// "MetadataExchangeClientKey"
0x15b94  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<object, object>::Remove(var<u1>)
0x15b99  pop
0x15b9a  endfinally
0x15b9b  ldloc.2
0x15b9c  brfalse.s loc_15BA4
0x15b9e  ldloc.1
0x15b9f  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x15ba4  endfinally
0x15ba5  ret
```
