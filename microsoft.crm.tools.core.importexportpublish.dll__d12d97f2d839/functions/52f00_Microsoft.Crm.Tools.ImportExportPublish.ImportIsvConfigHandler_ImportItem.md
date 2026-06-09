# Microsoft.Crm.Tools.ImportExportPublish.ImportIsvConfigHandler::ImportItem

- ea: `0x52f00`
- end: `0x53124`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportIsvConfigHandler::ImportItem`
- size: `548`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x35900`
- `0x50510`
- `0x508f0`
- `0x52f00`
- `0x63db0`
- `0x63df0`

## string_xrefs

- `0x52f81`: `IsvConfig`
- `0x52f34`: `/ImportExportXml/IsvConfig`
- `0x52f22`: `Import IsvConfig is skipped for Build to Build upgrade scenario.`
- `0x52f67`: `prvISVExtensions`
- `0x53029`: `ISV Config import is skipped because there is an existing ISV config row in the database.`
- `0x5303a`: `isvconfigid`
- `0x5305c`: `configxml`
- `0x5307c`: `configxml`

## pseudocode

```c

```

## disassembly

```asm
0x52f00  ldarg.0
0x52f01  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::get_IsBuildToBuildUpgrade()
0x52f06  brfalse.s loc_52F2E
0x52f08  ldarg.0
0x52f09  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportIsvConfigHandler::context
0x52f0e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x52f13  ldc.i4.s 0x11
0x52f15  ldstr    a0_0// "{0}"
0x52f1a  ldc.i4.1
0x52f1b  newarr   [mscorlib]System.Object
0x52f20  dup
0x52f21  ldc.i4.0
0x52f22  ldstr    aImportIsvconfi// "Import IsvConfig is skipped for Build t"...
0x52f27  stelem.ref
0x52f28  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x52f2d  ret
0x52f2e  ldarg.0
0x52f2f  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x52f34  ldstr    aImportexportxm_128// "/ImportExportXml/IsvConfig"
0x52f39  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x52f3e  stloc.0
0x52f3f  ldloc.0
0x52f40  brfalse.s loc_52F4F
0x52f42  ldloc.0
0x52f43  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x52f48  callvirt instance int32 [mscorlib]System.String::get_Length()
0x52f4d  brtrue.s loc_52F50
0x52f4f  ret
0x52f50  nop
0x52f51  ldarg.0
0x52f52  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportIsvConfigHandler::context
0x52f57  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x52f5c  ldarg.0
0x52f5d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportIsvConfigHandler::context
0x52f62  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x52f67  ldstr    aPrvisvextensio// "prvISVExtensions"
0x52f6c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetPrivilege(string)
0x52f71  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x52f76  ldarg.0
0x52f77  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportIsvConfigHandler::context
0x52f7c  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x52f81  ldstr    aIsvconfig// "IsvConfig"
0x52f86  ldarg.0
0x52f87  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportIsvConfigHandler::context
0x52f8c  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x52f91  stloc.1
0x52f92  ldarg.0
0x52f93  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportIsvConfigHandler::context
0x52f98  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x52f9d  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.IsvConfig::.ctor(valuetype [mscorlib]System.Guid)
0x52fa2  stloc.2
0x52fa3  ldloc.2
0x52fa4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x52fa9  ldarg.0
0x52faa  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportIsvConfigHandler::context
0x52faf  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x52fb4  stloc.3
0x52fb5  ldloc.3
0x52fb6  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddPrimaryKey()
0x52fbb  ldloc.2
0x52fbc  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x52fc1  ldarg.0
0x52fc2  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportIsvConfigHandler::context
0x52fc7  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x52fcc  stloc.s  4
0x52fce  ldloc.s  4
0x52fd0  ldstr    aOrganizationid// "organizationid"
0x52fd5  ldc.i4.0
0x52fd6  ldarg.0
0x52fd7  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportIsvConfigHandler::context
0x52fdc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x52fe1  box      [mscorlib]System.Guid
0x52fe6  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x52feb  pop
0x52fec  ldloc.1
0x52fed  ldloc.s  4
0x52fef  ldloc.3
0x52ff0  ldarg.0
0x52ff1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportIsvConfigHandler::context
0x52ff6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x52ffb  stloc.s  5
0x52ffd  ldloc.s  5
0x52fff  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x53004  ldc.i4.0
0x53005  ble.s    loc_5307B
0x53007  ldarg.0
0x53008  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::get_Setup()
0x5300d  brfalse.s loc_53039
0x5300f  ldarg.0
0x53010  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportIsvConfigHandler::context
0x53015  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5301a  ldc.i4.s 0x11
0x5301c  ldstr    a0_0// "{0}"
0x53021  ldc.i4.1
0x53022  newarr   [mscorlib]System.Object
0x53027  dup
0x53028  ldc.i4.0
0x53029  ldstr    aIsvConfigImpor// "ISV Config import is skipped because th"...
0x5302e  stelem.ref
0x5302f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x53034  leave    loc_53123
0x53039  ldloc.2
0x5303a  ldstr    aIsvconfigid// "isvconfigid"
0x5303f  ldloc.s  5
0x53041  ldc.i4.0
0x53042  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x53047  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PrimaryKey()
0x5304c  unbox.any [mscorlib]System.Guid
0x53051  box      [mscorlib]System.Guid
0x53056  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5305b  ldloc.2
0x5305c  ldstr    aConfigxml// "configxml"
0x53061  ldloc.0
0x53062  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x53067  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5306c  ldloc.1
0x5306d  ldloc.2
0x5306e  ldarg.0
0x5306f  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportIsvConfigHandler::context
0x53074  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x53079  br.s     loc_5309A
0x5307b  ldloc.2
0x5307c  ldstr    aConfigxml// "configxml"
0x53081  ldloc.0
0x53082  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x53087  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5308c  ldloc.1
0x5308d  ldloc.2
0x5308e  ldarg.0
0x5308f  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportIsvConfigHandler::context
0x53094  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x53099  pop
0x5309a  leave.s  loc_53112
0x5309c  stloc.s  6
0x5309e  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::IsvBadXml
0x530a3  stloc.s  7
0x530a5  ldarg.0
0x530a6  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportIsvConfigHandler::tracer
0x530ab  ldloc.s  7
0x530ad  ldloc.s  6
0x530af  ldc.i4.3
0x530b0  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x530b5  ldloc.s  7
0x530b7  ldloc.s  6
0x530b9  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportIsvConfigException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x530be  throw
0x530bf  stloc.s  8
0x530c1  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::IsvImportPrivilegeErrorMessage
0x530c6  stloc.s  9
0x530c8  ldarg.0
0x530c9  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportIsvConfigHandler::tracer
0x530ce  ldloc.s  9
0x530d0  ldloc.s  8
0x530d2  ldc.i4.3
0x530d3  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x530d8  ldloc.s  9
0x530da  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::IsvImportPrivilegeErrorMessage
0x530df  ldc.i4   0x80048029
0x530e4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmSecurityException::.ctor(string, int32)
0x530e9  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportIsvConfigException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x530ee  throw
0x530ef  stloc.s  0xA
0x530f1  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::IsvImportErrorMessage
0x530f6  stloc.s  0xB
0x530f8  ldarg.0
0x530f9  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportIsvConfigHandler::tracer
0x530fe  ldloc.s  0xB
0x53100  ldloc.s  0xA
0x53102  ldc.i4.3
0x53103  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x53108  ldloc.s  0xB
0x5310a  ldloc.s  0xA
0x5310c  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportIsvConfigException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x53111  throw
0x53112  ldarg.0
0x53113  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportIsvConfigHandler::tracer
0x53118  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::IsvImportSuccessMessage
0x5311d  ldc.i4.1
0x5311e  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddSuccess(string successMessage, int32 count)
0x53123  ret
```
