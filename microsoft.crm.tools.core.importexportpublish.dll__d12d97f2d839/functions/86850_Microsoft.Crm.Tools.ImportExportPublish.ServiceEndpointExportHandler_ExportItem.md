# Microsoft.Crm.Tools.ImportExportPublish.ServiceEndpointExportHandler::ExportItem

- ea: `0x86850`
- end: `0x86a0d`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ServiceEndpointExportHandler::ExportItem`
- size: `445`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x391e0`
- `0x39940`
- `0x39cd0`
- `0x3a780`
- `0x3aa60`
- `0x3b380`
- `0x3b3c0`
- `0x86830`
- `0x86850`
- `0x86a10`

## string_xrefs

- `0x8686c`: `ServiceEndpoint`
- `0x8687c`: `ServiceEndpoint`
- `0x868dc`: `ServiceEndpoint`
- `0x868c2`: `serviceendpointid`
- `0x868e9`: `ServiceEndpointAttributes`
- `0x86933`: `ServiceEndpointProperties`
- `0x86861`: `ServiceEndpoints`

## pseudocode

```c

```

## disassembly

```asm
0x86850  ldarg.0
0x86851  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.ServiceEndpointExportHandler::_solutionComponentSet
0x86856  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x8685b  ldc.i4.0
0x8685c  bgt.s    loc_8685F
0x8685e  ret
0x8685f  nop
0x86860  ldarg.1
0x86861  ldstr    aServiceendpoin_4// "ServiceEndpoints"
0x86866  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x8686b  stloc.0
0x8686c  ldstr    aServiceendpoin// "ServiceEndpoint"
0x86871  ldarg.0
0x86872  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ServiceEndpointExportHandler::_context
0x86877  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8687c  ldstr    aServiceendpoin// "ServiceEndpoint"
0x86881  ldarg.0
0x86882  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ServiceEndpointExportHandler::_context
0x86887  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x8688c  stloc.1
0x8688d  ldloc.1
0x8688e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x86893  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddAllColumns()
0x86898  ldloc.1
0x86899  ldarg.0
0x8689a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ServiceEndpointExportHandler::_context
0x8689f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x868a4  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x868a9  stloc.2
0x868aa  br       loc_869B5
0x868af  ldloc.2
0x868b0  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x868b5  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x868ba  stloc.3
0x868bb  ldarg.0
0x868bc  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.ServiceEndpointExportHandler::_solutionComponentSet
0x868c1  ldloc.3
0x868c2  ldstr    aServiceendpoin_0// "serviceendpointid"
0x868c7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x868cc  unbox.any [mscorlib]System.Guid
0x868d1  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x868d6  brfalse  loc_869B5
0x868db  ldarg.1
0x868dc  ldstr    aServiceendpoin// "ServiceEndpoint"
0x868e1  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x868e6  stloc.s  4
0x868e8  ldarg.0
0x868e9  ldstr    aServiceendpoin_1// "ServiceEndpointAttributes"
0x868ee  ldarg.1
0x868ef  ldloc.s  4
0x868f1  ldloc.3
0x868f2  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x868f7  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlAttributes(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container)
0x868fc  ldloc.3
0x868fd  ldstr    aSolutionid// "solutionid"
0x86902  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x86907  unbox.any [mscorlib]System.Guid
0x8690c  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x86911  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x86916  brtrue.s loc_86920
0x86918  ldarg.0
0x86919  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::_exportDeltaOverride
0x8691e  brfalse.s loc_86984
0x86920  ldloc.3
0x86921  ldstr    aIsmanaged// "ismanaged"
0x86926  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8692b  unbox.any [mscorlib]System.Boolean
0x86930  stloc.s  5
0x86932  ldarg.0
0x86933  ldstr    aServiceendpoin_3// "ServiceEndpointProperties"
0x86938  ldarg.1
0x86939  ldloc.s  4
0x8693b  ldloc.3
0x8693c  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x86941  ldloc.s  5
0x86943  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlProperties(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container, bool managed)
0x86948  ldarg.0
0x86949  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.ServiceEndpointExportHandler::get_ExportToTargetVersionContext()
0x8694e  callvirt instance bool Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::IsTargetVersionSpecified()
0x86953  brtrue.s loc_86961
0x86955  ldarg.0
0x86956  ldarg.1
0x86957  ldloc.3
0x86958  ldloc.s  4
0x8695a  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ServiceEndpointExportHandler::AddNewProperties(class [System.Xml]System.Xml.XmlDocument exportDocument, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, class [System.Xml]System.Xml.XmlNode serviceEndpointNode)
0x8695f  br.s     loc_869AC
0x86961  ldarg.0
0x86962  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.ServiceEndpointExportHandler::get_ExportToTargetVersionContext()
0x86967  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::get_TargetVersion()
0x8696c  ldsfld   class [mscorlib]System.Version [Microsoft.Crm]Microsoft.Crm.CrmVersions::NaosVersion
0x86971  call     bool [mscorlib]System.Version::op_GreaterThanOrEqual(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x86976  brfalse.s loc_869AC
0x86978  ldarg.0
0x86979  ldarg.1
0x8697a  ldloc.3
0x8697b  ldloc.s  4
0x8697d  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ServiceEndpointExportHandler::AddNewProperties(class [System.Xml]System.Xml.XmlDocument exportDocument, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, class [System.Xml]System.Xml.XmlNode serviceEndpointNode)
0x86982  br.s     loc_869AC
0x86984  ldarg.1
0x86985  ldstr    aUnmodified// "unmodified"
0x8698a  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x8698f  stloc.s  6
0x86991  ldloc.s  6
0x86993  ldstr    a1// "1"
0x86998  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x8699d  ldloc.s  4
0x8699f  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x869a4  ldloc.s  6
0x869a6  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x869ab  pop
0x869ac  ldloc.0
0x869ad  ldloc.s  4
0x869af  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x869b4  pop
0x869b5  ldloc.2
0x869b6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x869bb  brtrue   loc_868AF
0x869c0  leave.s  loc_869D6
0x869c2  ldloc.2
0x869c3  isinst   [mscorlib]System.IDisposable
0x869c8  stloc.s  7
0x869ca  ldloc.s  7
0x869cc  brfalse.s loc_869D5
0x869ce  ldloc.s  7
0x869d0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x869d5  endfinally
0x869d6  ldarg.1
0x869d7  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x869dc  ldloc.0
0x869dd  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x869e2  pop
0x869e3  leave.s  loc_869FC
0x869e5  stloc.s  8
0x869e7  ldarg.0
0x869e8  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.ServiceEndpointExportHandler::_tracer
0x869ed  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::ServiceEndpointsExportErrorMessage
0x869f2  ldloc.s  8
0x869f4  ldc.i4.3
0x869f5  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x869fa  rethrow
0x869fc  ldarg.0
0x869fd  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.ServiceEndpointExportHandler::_tracer
0x86a02  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::ServiceEndpointsExportSuccessMessage
0x86a07  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddSuccess(string successMessage)
0x86a0c  ret
```
