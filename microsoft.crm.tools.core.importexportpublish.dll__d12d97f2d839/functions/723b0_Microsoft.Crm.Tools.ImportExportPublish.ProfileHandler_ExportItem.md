# Microsoft.Crm.Tools.ImportExportPublish.ProfileHandler::ExportItem

- ea: `0x723b0`
- end: `0x725bf`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ProfileHandler::ExportItem`
- size: `527`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x391e0`
- `0x39930`
- `0x39cd0`
- `0x3b380`
- `0x3b3c0`
- `0x723b0`

## string_xrefs

- `0x723b1`: `FieldSecurityProfile`
- `0x72411`: `fieldsecurityprofileid`
- `0x72448`: `fieldsecurityprofileid`
- `0x723da`: `FieldSecurityProfiles`

## pseudocode

```c

```

## disassembly

```asm
0x723b0  ldarg.1
0x723b1  ldstr    aFieldsecurityp// "FieldSecurityProfile"
0x723b6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x723bb  stloc.0
0x723bc  ldarg.0
0x723bd  ldstr    aProfileattribu// "ProfileAttributes"
0x723c2  ldarg.1
0x723c3  ldloc.0
0x723c4  ldarg.0
0x723c5  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Tools.ImportExportPublish.ProfileHandler::_profile
0x723ca  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x723cf  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlAttributes(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container)
0x723d4  ldarg.1
0x723d5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x723da  ldstr    aFieldsecurityp_1// "FieldSecurityProfiles"
0x723df  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x723e4  ldloc.0
0x723e5  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x723ea  pop
0x723eb  ldarg.0
0x723ec  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Tools.ImportExportPublish.ProfileHandler::_profile
0x723f1  ldstr    aSolutionid// "solutionid"
0x723f6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x723fb  unbox.any [mscorlib]System.Guid
0x72400  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x72405  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x7240a  stloc.1
0x7240b  ldarg.0
0x7240c  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Tools.ImportExportPublish.ProfileHandler::_profile
0x72411  ldstr    aFieldsecurityp_0// "fieldsecurityprofileid"
0x72416  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x7241b  unbox.any [mscorlib]System.Guid
0x72420  stloc.2
0x72421  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FieldPermissionService::.ctor()
0x72426  ldstr    aFieldpermissio// "FieldPermission"
0x7242b  ldarg.0
0x7242c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ProfileHandler::context
0x72431  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x72436  stloc.3
0x72437  ldloc.3
0x72438  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x7243d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddAllColumns()
0x72442  ldloc.3
0x72443  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x72448  ldstr    aFieldsecurityp_0// "fieldsecurityprofileid"
0x7244d  ldc.i4.0
0x7244e  ldloc.2
0x7244f  box      [mscorlib]System.Guid
0x72454  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x72459  pop
0x7245a  ldloc.3
0x7245b  ldarg.0
0x7245c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ProfileHandler::context
0x72461  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x72466  stloc.s  4
0x72468  ldarg.1
0x72469  ldstr    aFieldpermissio_3// "FieldPermissions"
0x7246e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x72473  stloc.s  5
0x72475  ldloc.s  4
0x72477  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x7247c  stloc.s  6
0x7247e  br       loc_72524
0x72483  ldloc.s  6
0x72485  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x7248a  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x7248f  stloc.s  7
0x72491  ldloc.1
0x72492  ldloc.s  7
0x72494  ldstr    aSolutionid// "solutionid"
0x72499  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x7249e  unbox.any [mscorlib]System.Guid
0x724a3  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x724a8  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x724ad  or
0x724ae  stloc.1
0x724af  ldarg.1
0x724b0  ldstr    aFieldpermissio// "FieldPermission"
0x724b5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x724ba  stloc.s  8
0x724bc  ldloc.s  5
0x724be  ldloc.s  8
0x724c0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x724c5  pop
0x724c6  ldarg.0
0x724c7  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.ProfileHandler::_cache
0x724cc  ldloc.s  7
0x724ce  ldstr    aEntityname_0// "entityname"
0x724d3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x724d8  unbox.any [mscorlib]System.Int32
0x724dd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x724e2  stloc.s  9
0x724e4  ldarg.1
0x724e5  ldc.i4.1
0x724e6  ldstr    aEntityname// "EntityName"
0x724eb  ldsfld   string [mscorlib]System.String::Empty
0x724f0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x724f5  stloc.s  0xA
0x724f7  ldloc.s  0xA
0x724f9  ldloc.s  9
0x724fb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x72500  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x72505  ldloc.s  8
0x72507  ldloc.s  0xA
0x72509  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x7250e  pop
0x7250f  ldarg.0
0x72510  ldstr    aPermissionprop// "PermissionProperties"
0x72515  ldarg.1
0x72516  ldloc.s  8
0x72518  ldloc.s  7
0x7251a  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x7251f  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlProperties(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container)
0x72524  ldloc.s  6
0x72526  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7252b  brtrue   loc_72483
0x72530  leave.s  loc_72547
0x72532  ldloc.s  6
0x72534  isinst   [mscorlib]System.IDisposable
0x72539  stloc.s  0xB
0x7253b  ldloc.s  0xB
0x7253d  brfalse.s loc_72546
0x7253f  ldloc.s  0xB
0x72541  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x72546  endfinally
0x72547  ldloc.1
0x72548  ldloc.s  4
0x7254a  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x7254f  ldc.i4.0
0x72550  ceq
0x72552  or
0x72553  stloc.1
0x72554  ldloc.1
0x72555  brtrue.s loc_7255F
0x72557  ldarg.0
0x72558  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::_exportDeltaOverride
0x7255d  brfalse.s loc_7256A
0x7255f  ldloc.0
0x72560  ldloc.s  5
0x72562  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x72567  pop
0x72568  br.s     loc_72591
0x7256a  ldarg.1
0x7256b  ldstr    aUnmodified// "unmodified"
0x72570  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x72575  stloc.s  0xC
0x72577  ldloc.s  0xC
0x72579  ldstr    a1// "1"
0x7257e  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x72583  ldloc.0
0x72584  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x72589  ldloc.s  0xC
0x7258b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x72590  pop
0x72591  leave.s  loc_725AE
0x72593  stloc.s  0xD
0x72595  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::ProfileExportErrorMessage
0x7259a  stloc.s  0xE
0x7259c  ldarg.0
0x7259d  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.ProfileHandler::tracer
0x725a2  ldloc.s  0xE
0x725a4  ldloc.s  0xD
0x725a6  ldc.i4.3
0x725a7  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x725ac  rethrow
0x725ae  ldarg.0
0x725af  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.ProfileHandler::tracer
0x725b4  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::ProfileExportSuccessMessage
0x725b9  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddSuccess(string successMessage)
0x725be  ret
```
