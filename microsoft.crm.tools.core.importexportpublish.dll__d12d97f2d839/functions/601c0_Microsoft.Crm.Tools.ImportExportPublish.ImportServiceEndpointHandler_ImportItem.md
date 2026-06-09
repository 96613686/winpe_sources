# Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::ImportItem

- ea: `0x601c0`
- end: `0x6042f`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::ImportItem`
- size: `623`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x35f30`
- `0x508e0`
- `0x601c0`
- `0x60430`
- `0x604f0`
- `0x60560`
- `0x60590`
- `0x63db0`
- `0x63df0`
- `0x686f0`

## string_xrefs

- `0x60240`: `ServiceEndpoint`
- `0x60252`: `ServiceEndpoint`
- `0x60282`: `ServiceEndpointId`
- `0x601cb`: `ServiceEndpoints`
- `0x601f6`: `StoreName`
- `0x60230`: `ImportServiceEndpointHandler.ImportItem`

## pseudocode

```c

```

## disassembly

```asm
0x601c0  ldarg.0
0x601c1  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x601c6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x601cb  ldstr    aServiceendpoin_4// "ServiceEndpoints"
0x601d0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x601d5  stloc.0
0x601d6  ldloc.0
0x601d7  brtrue.s loc_601DE
0x601d9  leave    loc_6042E
0x601de  ldc.i4.5
0x601df  newarr   [mscorlib]System.String
0x601e4  dup
0x601e5  ldc.i4.0
0x601e6  ldstr    aName_1// "Name"
0x601eb  stelem.ref
0x601ec  dup
0x601ed  ldc.i4.1
0x601ee  ldstr    aCertificatedat// "CertificateData"
0x601f3  stelem.ref
0x601f4  dup
0x601f5  ldc.i4.2
0x601f6  ldstr    aStorename// "StoreName"
0x601fb  stelem.ref
0x601fc  dup
0x601fd  ldc.i4.3
0x601fe  ldstr    aStorelocation// "StoreLocation"
0x60203  stelem.ref
0x60204  dup
0x60205  ldc.i4.4
0x60206  ldstr    aStorefindtype// "StoreFindType"
0x6020b  stelem.ref
0x6020c  stloc.1
0x6020d  call     class [Microsoft.Crm.Core]Microsoft.Crm.IAuthManagementInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.AuthManagementInfoProvider::get_Instance()
0x60212  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x60217  ldstr    aAppfabricissue// "AppFabricIssuer"
0x6021c  ldloc.1
0x6021d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.IAuthManagementInfoProvider::GetCertificates(valuetype [mscorlib]System.Guid, string, string[])
0x60222  stloc.2
0x60223  ldarg.0
0x60224  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::_context
0x60229  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x6022e  ldc.i4.s 0x11
0x60230  ldstr    aImportservicee// "ImportServiceEndpointHandler.ImportItem"
0x60235  ldc.i4.0
0x60236  newarr   [mscorlib]System.Object
0x6023b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x60240  ldstr    aServiceendpoin// "ServiceEndpoint"
0x60245  ldarg.0
0x60246  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::_context
0x6024b  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x60250  stloc.3
0x60251  ldloc.0
0x60252  ldstr    aServiceendpoin// "ServiceEndpoint"
0x60257  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x6025c  stloc.s  4
0x6025e  ldloc.s  4
0x60260  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x60265  stloc.s  5
0x60267  br       loc_603BC
0x6026c  ldloc.s  5
0x6026e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x60273  castclass [System.Xml]System.Xml.XmlNode
0x60278  stloc.s  6
0x6027a  ldarg.0
0x6027b  ldloc.s  6
0x6027d  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x60282  ldstr    aServiceendpoin_2// "ServiceEndpointId"
0x60287  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x6028c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x60291  stfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::_serviceEndpointName
0x60296  ldarg.0
0x60297  ldc.i4.1
0x60298  stfld    int32 Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::_authType
0x6029d  ldloc.s  6
0x6029f  ldstr    aAuthtype// "AuthType"
0x602a4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x602a9  brfalse.s loc_602CC
0x602ab  ldarg.0
0x602ac  ldloc.s  6
0x602ae  ldstr    aAuthtype// "AuthType"
0x602b3  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x602b8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x602bd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x602c2  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x602c7  stfld    int32 Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::_authType
0x602cc  ldc.i4.s 0x5F
0x602ce  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ImportExportDependencyHelperFactory::RetrieveHelper(int32)
0x602d3  ldarg.0
0x602d4  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x602d9  ldsfld   string [mscorlib]System.String::Empty
0x602de  ldarg.0
0x602df  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::_serviceEndpointName
0x602e4  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x602e9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x602ee  ldarg.0
0x602ef  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::_context
0x602f4  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper::CheckForRootComponent(class [System.Xml]System.Xml.XmlDocument, string, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x602f9  ldarg.0
0x602fa  ldloc.s  6
0x602fc  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::IsUnmodified(class [System.Xml]System.Xml.XmlNode node)
0x60301  brfalse.s loc_6032A
0x60303  ldarg.0
0x60304  ldloc.s  6
0x60306  ldloc.3
0x60307  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::AddUnmodified(class [System.Xml]System.Xml.XmlNode node, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject service)
0x6030c  ldarg.0
0x6030d  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::_parent
0x60312  ldarg.0
0x60313  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetParameterXPath()
0x60318  ldstr    aSuccess// "success"
0x6031d  ldnull
0x6031e  ldc.i4.1
0x6031f  ldc.i4.0
0x60320  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::UpdateProgress(string path, string result, class [mscorlib]System.Exception ex, bool isProcessed, [opt] int32 errorCode)
0x60325  br       loc_603BC
0x6032a  ldarg.0
0x6032b  ldloc.s  6
0x6032d  call     instance class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ServiceEndpoint Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::GetServiceEndpointFromXmlNode(class [System.Xml]System.Xml.XmlNode node)
0x60332  stloc.s  7
0x60334  ldarg.0
0x60335  ldloc.s  7
0x60337  ldloc.3
0x60338  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::CreateOrUpdate(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ServiceEndpoint serviceEndpoint, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject service)
0x6033d  ldarg.0
0x6033e  ldfld    int32 Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::_authType
0x60343  ldc.i4.1
0x60344  beq.s    loc_60370
0x60346  ldarg.0
0x60347  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::_parent
0x6034c  ldarg.0
0x6034d  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetParameterXPath()
0x60352  ldstr    aWarning// "warning"
0x60357  ldc.i4   0x80081112
0x6035c  ldc.i4.0
0x6035d  newarr   [mscorlib]System.Object
0x60362  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x60367  ldc.i4.0
0x60368  ldc.i4.0
0x60369  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::UpdateProgress(string path, string result, class [mscorlib]System.Exception ex, bool isProcessed, [opt] int32 errorCode)
0x6036e  br.s     loc_603A3
0x60370  ldloc.2
0x60371  brfalse.s loc_6037B
0x60373  ldloc.2
0x60374  callvirt instance int32 class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Count()
0x60379  brtrue.s loc_603A3
0x6037b  ldarg.0
0x6037c  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::_parent
0x60381  ldarg.0
0x60382  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetParameterXPath()
0x60387  ldstr    aWarning// "warning"
0x6038c  ldc.i4   0x80044176
0x60391  ldc.i4.0
0x60392  newarr   [mscorlib]System.Object
0x60397  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x6039c  ldc.i4.0
0x6039d  ldc.i4.0
0x6039e  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::UpdateProgress(string path, string result, class [mscorlib]System.Exception ex, bool isProcessed, [opt] int32 errorCode)
0x603a3  ldarg.0
0x603a4  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::_parent
0x603a9  ldarg.0
0x603aa  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetParameterXPath()
0x603af  ldstr    aSuccess// "success"
0x603b4  ldnull
0x603b5  ldc.i4.1
0x603b6  ldc.i4.0
0x603b7  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::UpdateProgress(string path, string result, class [mscorlib]System.Exception ex, bool isProcessed, [opt] int32 errorCode)
0x603bc  ldloc.s  5
0x603be  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x603c3  brtrue   loc_6026C
0x603c8  leave.s  loc_603DF
0x603ca  ldloc.s  5
0x603cc  isinst   [mscorlib]System.IDisposable
0x603d1  stloc.s  8
0x603d3  ldloc.s  8
0x603d5  brfalse.s loc_603DE
0x603d7  ldloc.s  8
0x603d9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x603de  endfinally
0x603df  leave.s  loc_603ED
0x603e1  ldloc.s  4
0x603e3  brfalse.s loc_603EC
0x603e5  ldloc.s  4
0x603e7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x603ec  endfinally
0x603ed  ldarg.0
0x603ee  ldsfld   string [mscorlib]System.String::Empty
0x603f3  stfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::_serviceEndpointName
0x603f8  leave.s  loc_6041D
0x603fa  stloc.s  9
0x603fc  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::ServiceEndpointsImportErrorMessage
0x60401  stloc.s  0xA
0x60403  ldarg.0
0x60404  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::_tracer
0x60409  ldloc.s  0xA
0x6040b  ldloc.s  9
0x6040d  ldc.i4.3
0x6040e  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x60413  ldloc.s  0xA
0x60415  ldloc.s  9
0x60417  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportReportsException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x6041c  throw
0x6041d  ldarg.0
0x6041e  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::_tracer
0x60423  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::ServiceEndpointsImportSuccessMessage
0x60428  ldc.i4.1
0x60429  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddSuccess(string successMessage, int32 count)
0x6042e  ret
```
