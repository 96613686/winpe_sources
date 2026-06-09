# Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::.ctor_1

- ea: `0x167d0`
- end: `0x168f9`
- name: `Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::.ctor_1`
- size: `297`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7ca0`
- `0x7ce0`
- `0x167d0`
- `0x178d0`
- `0x196a0`
- `0x19a30`
- `0x19c30`
- `0x19c60`

## string_xrefs

- `0x16806`: `ServiceEndpointMetadata`
- `0x1687f`: `The provided uri did not return any Service Endpoints!\n{0}`

## pseudocode

```c

```

## disassembly

```asm
0x167d0  ldarg.0
0x167d1  ldc.i4.4
0x167d2  stfld    valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::_tokenEndpointType
0x167d7  ldarg.0
0x167d8  call     instance void [mscorlib]System.Object::.ctor()
0x167dd  ldarg.0
0x167de  ldarg.1
0x167df  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::set_ServiceUri(class [System]System.Uri)
0x167e4  ldarg.0
0x167e5  ldtoken  var<u1>
0x167ea  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x167ef  ldarg.0
0x167f0  call     instance class [System]System.Uri class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_ServiceUri()
0x167f5  ldarg.2
0x167f6  call     class Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::RetrieveServiceEndpointMetadata(class [mscorlib]System.Type contractType, class [System]System.Uri serviceUri, bool checkForSecondary)
0x167fb  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::set_ServiceEndpointMetadata(class Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata)
0x16800  ldarg.0
0x16801  call     instance class Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_ServiceEndpointMetadata()
0x16806  ldstr    aServiceendpoin// "ServiceEndpointMetadata"
0x1680b  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x16810  ldarg.0
0x16811  call     instance class Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_ServiceEndpointMetadata()
0x16816  callvirt instance class Microsoft.Xrm.Sdk.Client.ServiceEndpointDictionary Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata::get_ServiceEndpoints()
0x1681b  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint>::get_Count()
0x16820  brtrue.s loc_16899
0x16822  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x16827  stloc.0
0x16828  ldarg.0
0x16829  call     instance class Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_ServiceEndpointMetadata()
0x1682e  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.MetadataConversionError> Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata::get_MetadataConversionErrors()
0x16833  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.MetadataConversionError>::get_Count()
0x16838  ldc.i4.0
0x16839  ble.s    loc_16876
0x1683b  ldarg.0
0x1683c  call     instance class Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_ServiceEndpointMetadata()
0x16841  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.MetadataConversionError> Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata::get_MetadataConversionErrors()
0x16846  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.MetadataConversionError>::GetEnumerator()
0x1684b  stloc.1
0x1684c  br.s     loc_16862
0x1684e  ldloc.1
0x1684f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.ServiceModel]System.ServiceModel.Description.MetadataConversionError>::get_Current()
0x16854  stloc.2
0x16855  ldloc.0
0x16856  ldloc.2
0x16857  callvirt instance string [System.ServiceModel]System.ServiceModel.Description.MetadataConversionError::get_Message()
0x1685c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x16861  pop
0x16862  ldloc.1
0x16863  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x16868  brtrue.s loc_1684E
0x1686a  leave.s  loc_16876
0x1686c  ldloc.1
0x1686d  brfalse.s loc_16875
0x1686f  ldloc.1
0x16870  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16875  endfinally
0x16876  ldc.i4.0
0x16877  ldc.i4.2
0x16878  newarr   [mscorlib]System.Object
0x1687d  dup
0x1687e  ldc.i4.0
0x1687f  ldstr    aTheProvidedUri// "The provided uri did not return any Ser"...
0x16884  stelem.ref
0x16885  dup
0x16886  ldc.i4.1
0x16887  ldloc.0
0x16888  callvirt instance string [mscorlib]System.Object::ToString()
0x1688d  stelem.ref
0x1688e  call     string Microsoft.Xrm.Sdk.ClientExceptionHelper::FormatMessage(int32 errorCode, object[] arguments)
0x16893  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x16898  throw
0x16899  ldarg.0
0x1689a  ldarg.0
0x1689b  call     instance class Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_ServiceEndpointMetadata()
0x168a0  callvirt instance class Microsoft.Xrm.Sdk.Client.ServiceEndpointDictionary Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata::get_ServiceEndpoints()
0x168a5  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::set_ServiceEndpoints(class Microsoft.Xrm.Sdk.Client.ServiceEndpointDictionary)
0x168aa  ldarg.0
0x168ab  call     instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_CurrentServiceEndpoint()
0x168b0  brfalse.s loc_168F8
0x168b2  ldarg.0
0x168b3  newobj   instance void Microsoft.Xrm.Sdk.Client.CrossRealmIssuerEndpointCollection::.ctor()
0x168b8  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::set_CrossRealmIssuerEndpoints(class Microsoft.Xrm.Sdk.Client.CrossRealmIssuerEndpointCollection)
0x168bd  ldarg.0
0x168be  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::SetAuthenticationConfiguration()
0x168c3  ldarg.2
0x168c4  brfalse.s loc_168CD
0x168c6  ldarg.0
0x168c7  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::SetEndpointSwitchingBehavior()
0x168cc  ret
0x168cd  ldarg.0
0x168ce  call     instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_CurrentServiceEndpoint()
0x168d3  callvirt instance class [System.ServiceModel]System.ServiceModel.EndpointAddress [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Address()
0x168d8  callvirt instance class [System]System.Uri [System.ServiceModel]System.ServiceModel.EndpointAddress::get_Uri()
0x168dd  ldarg.1
0x168de  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x168e3  brfalse.s loc_168F1
0x168e5  ldarg.0
0x168e6  call     instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_CurrentServiceEndpoint()
0x168eb  ldarg.1
0x168ec  call     void Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::ReplaceEndpointAddress(class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint endpoint, class [System]System.Uri adddress)
0x168f1  ldarg.0
0x168f2  ldarg.1
0x168f3  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::set_PrimaryEndpoint(class [System]System.Uri)
0x168f8  ret
```
