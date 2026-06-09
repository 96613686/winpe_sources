# Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::AddUnmodified

- ea: `0x604f0`
- end: `0x60560`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::AddUnmodified`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x601c0`

## callees

- `0x508e0`
- `0x50c30`
- `0x50fd0`
- `0x52050`
- `0x604f0`

## string_xrefs

- `0x60513`: `ServiceEndpoint`
- `0x60518`: `serviceendpointid`
- `0x604f8`: `ServiceEndpointId`

## pseudocode

```c

```

## disassembly

```asm
0x604f0  ldloca.s 0
0x604f2  ldarg.1
0x604f3  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x604f8  ldstr    aServiceendpoin_2// "ServiceEndpointId"
0x604fd  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x60502  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x60507  call     instance void [mscorlib]System.Guid::.ctor(string)
0x6050c  ldarg.0
0x6050d  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::_importHelper
0x60512  ldarg.2
0x60513  ldstr    aServiceendpoin// "ServiceEndpoint"
0x60518  ldstr    aServiceendpoin_0// "serviceendpointid"
0x6051d  ldloc.0
0x6051e  ldarg.0
0x6051f  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointHandler::_context
0x60524  ldc.i4.0
0x60525  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::TryGetEntity(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject service, string platformName, string idColumnName, valuetype [mscorlib]System.Guid primaryId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] bool retrieveDeleted)
0x6052a  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ServiceEndpoint
0x6052f  brfalse.s loc_60532
0x60531  ret
0x60532  ldarg.0
0x60533  ldc.i4.s 0x5F
0x60535  ldloc.0
0x60536  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::RemoveFromRootComponentsList(int32 componentType, valuetype [mscorlib]System.Guid objectId)
0x6053b  ldc.i4   0x8004847C
0x60540  ldc.i4.0
0x60541  newarr   [mscorlib]System.Object
0x60546  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x6054b  stloc.1
0x6054c  ldarg.0
0x6054d  ldarg.0
0x6054e  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetParameterXPath()
0x60553  ldstr    aWarning// "warning"
0x60558  ldloc.1
0x60559  ldc.i4.1
0x6055a  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::UpdateProgress(string path, string result, class [mscorlib]System.Exception ex, bool isProcessed)
0x6055f  ret
```
