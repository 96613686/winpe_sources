# Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::RetrieveServiceEndpointMetadata

- ea: `0x196a0`
- end: `0x198c0`
- name: `Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::RetrieveServiceEndpointMetadata`
- size: `544`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x167d0`

## callees

- `0x7ca0`
- `0x17660`
- `0x17680`
- `0x19620`
- `0x196a0`
- `0x198c0`
- `0x19920`
- `0x19960`
- `0x19990`
- `0x199b0`
- `0x199d0`
- `0x19c30`
- `0x19c40`
- `0x19c50`
- `0x19c60`
- `0x19c70`
- `0x19c80`
- `0x19c90`

## pseudocode

```c

```

## disassembly

```asm
0x196a0  newobj   instance void Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata::.ctor()
0x196a5  stloc.0
0x196a6  ldloc.0
0x196a7  ldarg.1
0x196a8  call     class Microsoft.Xrm.Sdk.Client.ServiceUrls class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<class Microsoft.Xrm.Sdk.IOrganizationService>::CalculateEndpoints(class [System]System.Uri)
0x196ad  callvirt instance void Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata::set_ServiceUrls(class Microsoft.Xrm.Sdk.Client.ServiceUrls value)
0x196b2  call     float64 Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::GetSDKVersionNumberFromAssembly()
0x196b7  stloc.1
0x196b8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x196bd  ldstr    a01Sdkversion2// "{0}{1}&sdkversion={2}"
0x196c2  ldc.i4.3
0x196c3  newarr   [mscorlib]System.Object
0x196c8  dup
0x196c9  ldc.i4.0
0x196ca  ldarg.1
0x196cb  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x196d0  stelem.ref
0x196d1  dup
0x196d2  ldc.i4.1
0x196d3  ldstr    aWsdl// "?wsdl"
0x196d8  stelem.ref
0x196d9  dup
0x196da  ldc.i4.2
0x196db  ldloc.1
0x196dc  box      [mscorlib]System.Double
0x196e1  stelem.ref
0x196e2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x196e7  newobj   instance void [System]System.Uri::.ctor(string)
0x196ec  stloc.2
0x196ed  ldloc.2
0x196ee  callvirt instance string [System]System.Uri::get_Scheme()
0x196f3  call     class [System.ServiceModel]System.ServiceModel.Description.MetadataExchangeClient Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::CreateMetadataClient(string scheme)
0x196f8  stloc.3
0x196f9  ldloc.3
0x196fa  brfalse  loc_197D2
0x196ff  ldloc.0
0x19700  ldloc.3
0x19701  ldloc.2
0x19702  ldc.i4.1
0x19703  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.MetadataSet [System.ServiceModel]System.ServiceModel.Description.MetadataExchangeClient::GetMetadata(class [System]System.Uri, valuetype [System.ServiceModel]System.ServiceModel.Description.MetadataExchangeClientMode)
0x19708  callvirt instance void Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata::set_ServiceMetadata(class [System.ServiceModel]System.ServiceModel.Description.MetadataSet value)
0x1970d  leave    loc_197D2
0x19712  stloc.s  5
0x19714  ldc.i4.1
0x19715  stloc.s  6
0x19717  ldarg.2
0x19718  brfalse  loc_197CA
0x1971d  ldloc.s  5
0x1971f  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x19724  isinst   [System]System.Net.WebException
0x19729  stloc.s  7
0x1972b  ldloc.s  7
0x1972d  brfalse  loc_197CA
0x19732  ldloc.s  7
0x19734  callvirt instance valuetype [System]System.Net.WebExceptionStatus [System]System.Net.WebException::get_Status()
0x19739  ldc.i4.1
0x1973a  beq.s    loc_1974A
0x1973c  ldloc.s  7
0x1973e  callvirt instance valuetype [System]System.Net.WebExceptionStatus [System]System.Net.WebException::get_Status()
0x19743  ldc.i4.s 0xE
0x19745  bne.un   loc_197CA
0x1974a  ldloc.0
0x1974b  callvirt instance class Microsoft.Xrm.Sdk.Client.ServiceUrls Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata::get_ServiceUrls()
0x19750  brfalse.s loc_197CA
0x19752  ldloc.0
0x19753  callvirt instance class Microsoft.Xrm.Sdk.Client.ServiceUrls Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata::get_ServiceUrls()
0x19758  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.ServiceUrls::get_PrimaryEndpoint()
0x1975d  ldarg.1
0x1975e  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x19763  brfalse.s loc_1978F
0x19765  ldloc.3
0x19766  ldloc.0
0x19767  callvirt instance class Microsoft.Xrm.Sdk.Client.ServiceUrls Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata::get_ServiceUrls()
0x1976c  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.ServiceUrls::get_AlternateEndpoint()
0x19771  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x19776  ldstr    aWsdl// "?wsdl"
0x1977b  call     string [mscorlib]System.String::Concat(string, string)
0x19780  newobj   instance void [System]System.Uri::.ctor(string)
0x19785  ldloc.0
0x19786  call     bool Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::TryRetrieveMetadata(class [System.ServiceModel]System.ServiceModel.Description.MetadataExchangeClient mcli, class [System]System.Uri serviceEndpoint, class Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata serviceEndpointMetadata)
0x1978b  stloc.s  6
0x1978d  br.s     loc_197CA
0x1978f  ldloc.0
0x19790  callvirt instance class Microsoft.Xrm.Sdk.Client.ServiceUrls Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata::get_ServiceUrls()
0x19795  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.ServiceUrls::get_AlternateEndpoint()
0x1979a  ldarg.1
0x1979b  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x197a0  brfalse.s loc_197CA
0x197a2  ldloc.3
0x197a3  ldloc.0
0x197a4  callvirt instance class Microsoft.Xrm.Sdk.Client.ServiceUrls Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata::get_ServiceUrls()
0x197a9  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.ServiceUrls::get_PrimaryEndpoint()
0x197ae  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x197b3  ldstr    aWsdl// "?wsdl"
0x197b8  call     string [mscorlib]System.String::Concat(string, string)
0x197bd  newobj   instance void [System]System.Uri::.ctor(string)
0x197c2  ldloc.0
0x197c3  call     bool Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::TryRetrieveMetadata(class [System.ServiceModel]System.ServiceModel.Description.MetadataExchangeClient mcli, class [System]System.Uri serviceEndpoint, class Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata serviceEndpointMetadata)
0x197c8  stloc.s  6
0x197ca  ldloc.s  6
0x197cc  brfalse.s loc_197D0
0x197ce  rethrow
0x197d0  leave.s  loc_197D2
0x197d2  ldloc.0
0x197d3  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.MetadataSet Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata::get_ServiceMetadata()
0x197d8  ldstr    aStsMetadata// "STS Metadata"
0x197dd  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x197e2  ldarg.0
0x197e3  call     class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.ContractDescription> Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::CreateContractCollection(class [mscorlib]System.Type contract)
0x197e8  stloc.s  4
0x197ea  ldloc.s  4
0x197ec  brfalse  loc_198BE
0x197f1  ldloc.0
0x197f2  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.MetadataSet Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata::get_ServiceMetadata()
0x197f7  newobj   instance void [System.ServiceModel]System.ServiceModel.Description.WsdlImporter::.ctor(class [System.ServiceModel]System.ServiceModel.Description.MetadataSet)
0x197fc  dup
0x197fd  callvirt instance class [System.ServiceModel]System.Collections.Generic.KeyedByTypeCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IWsdlImportExtension> [System.ServiceModel]System.ServiceModel.Description.WsdlImporter::get_WsdlImportExtensions()
0x19802  stloc.s  8
0x19804  call     class [mscorlib]System.Collections.Generic.List`1<class [System.ServiceModel]System.ServiceModel.Description.IPolicyImportExtension> Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::AddSecurityBindingToPolicyImporter(class [System.ServiceModel]System.ServiceModel.Description.WsdlImporter importer)
0x19809  stloc.s  9
0x1980b  ldloc.0
0x1980c  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.MetadataSet Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata::get_ServiceMetadata()
0x19811  ldloc.s  9
0x19813  ldloc.s  8
0x19815  newobj   instance void [System.ServiceModel]System.ServiceModel.Description.WsdlImporter::.ctor(class [System.ServiceModel]System.ServiceModel.Description.MetadataSet, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.ServiceModel]System.ServiceModel.Description.IPolicyImportExtension>, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.ServiceModel]System.ServiceModel.Description.IWsdlImportExtension>)
0x1981a  stloc.s  0xA
0x1981c  ldloc.s  4
0x1981e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.ContractDescription>::GetEnumerator()
0x19823  stloc.s  0xC
0x19825  br.s     loc_19845
0x19827  ldloc.s  0xC
0x19829  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.ServiceModel]System.ServiceModel.Description.ContractDescription>::get_Current()
0x1982e  stloc.s  0xD
0x19830  ldloc.s  0xA
0x19832  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.Xml]System.Xml.XmlQualifiedName, class [System.ServiceModel]System.ServiceModel.Description.ContractDescription> [System.ServiceModel]System.ServiceModel.Description.MetadataImporter::get_KnownContracts()
0x19837  ldloc.s  0xD
0x19839  call     class [System.Xml]System.Xml.XmlQualifiedName Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::GetPortTypeQName(class [System.ServiceModel]System.ServiceModel.Description.ContractDescription contract)
0x1983e  ldloc.s  0xD
0x19840  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.Xml]System.Xml.XmlQualifiedName, class [System.ServiceModel]System.ServiceModel.Description.ContractDescription>::Add(var<u1>, !!T0)
0x19845  ldloc.s  0xC
0x19847  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1984c  brtrue.s loc_19827
0x1984e  leave.s  loc_1985C
0x19850  ldloc.s  0xC
0x19852  brfalse.s loc_1985B
0x19854  ldloc.s  0xC
0x19856  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1985b  endfinally
0x1985c  ldloc.s  0xA
0x1985e  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpointCollection [System.ServiceModel]System.ServiceModel.Description.MetadataImporter::ImportAllEndpoints()
0x19863  stloc.s  0xB
0x19865  ldloc.s  0xA
0x19867  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.MetadataConversionError> [System.ServiceModel]System.ServiceModel.Description.MetadataImporter::get_Errors()
0x1986c  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.MetadataConversionError>::get_Count()
0x19871  ldc.i4.0
0x19872  ble.s    loc_198B1
0x19874  ldloc.s  0xA
0x19876  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.MetadataConversionError> [System.ServiceModel]System.ServiceModel.Description.MetadataImporter::get_Errors()
0x1987b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.MetadataConversionError>::GetEnumerator()
0x19880  stloc.s  0xE
0x19882  br.s     loc_1989A
0x19884  ldloc.s  0xE
0x19886  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.ServiceModel]System.ServiceModel.Description.MetadataConversionError>::get_Current()
0x1988b  stloc.s  0xF
0x1988d  ldloc.0
0x1988e  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.MetadataConversionError> Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata::get_MetadataConversionErrors()
0x19893  ldloc.s  0xF
0x19895  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.MetadataConversionError>::Add(var<u1>)
0x1989a  ldloc.s  0xE
0x1989c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x198a1  brtrue.s loc_19884
0x198a3  leave.s  loc_198B1
0x198a5  ldloc.s  0xE
0x198a7  brfalse.s loc_198B0
0x198a9  ldloc.s  0xE
0x198ab  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x198b0  endfinally
0x198b1  ldloc.0
0x198b2  callvirt instance class Microsoft.Xrm.Sdk.Client.ServiceEndpointDictionary Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata::get_ServiceEndpoints()
0x198b7  ldloc.s  0xB
0x198b9  call     void Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::ParseEndpoints(class Microsoft.Xrm.Sdk.Client.ServiceEndpointDictionary serviceEndpoints, class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpointCollection serviceEndpointCollection)
0x198be  ldloc.0
0x198bf  ret
```
