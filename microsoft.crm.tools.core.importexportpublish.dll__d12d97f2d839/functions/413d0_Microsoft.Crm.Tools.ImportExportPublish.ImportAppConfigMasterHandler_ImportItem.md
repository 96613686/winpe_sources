# Microsoft.Crm.Tools.ImportExportPublish.ImportAppConfigMasterHandler::ImportItem

- ea: `0x413d0`
- end: `0x414a8`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportAppConfigMasterHandler::ImportItem`
- size: `216`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x35e50`
- `0x413d0`
- `0x46410`
- `0x464d0`
- `0x63db0`
- `0x63df0`

## string_xrefs

- `0x413d6`: `/ImportExportXml/AppConfigMasters`
- `0x413ed`: `AppConfigMaster`
- `0x4142d`: `AppConfigMaster`

## pseudocode

```c

```

## disassembly

```asm
0x413d0  ldarg.0
0x413d1  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::_doc
0x413d6  ldstr    aImportexportxm_111// "/ImportExportXml/AppConfigMasters"
0x413db  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x413e0  stloc.0
0x413e1  ldloc.0
0x413e2  brtrue.s loc_413E5
0x413e4  ret
0x413e5  nop
0x413e6  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigMasterService::.ctor()
0x413eb  stloc.1
0x413ec  ldloc.0
0x413ed  ldstr    aAppconfigmaste_0// "AppConfigMaster"
0x413f2  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x413f7  stloc.2
0x413f8  ldloc.2
0x413f9  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x413fe  stloc.3
0x413ff  br.s     loc_41447
0x41401  ldloc.3
0x41402  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x41407  castclass [System.Xml]System.Xml.XmlNode
0x4140c  stloc.s  4
0x4140e  ldarg.0
0x4140f  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::_context
0x41414  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x41419  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppConfigMaster::.ctor(valuetype [mscorlib]System.Guid)
0x4141e  stloc.s  5
0x41420  ldarg.0
0x41421  ldloc.s  4
0x41423  ldloc.s  5
0x41425  ldc.i4.1
0x41426  newarr   [mscorlib]System.String
0x4142b  dup
0x4142c  ldc.i4.0
0x4142d  ldstr    aAppconfigmaste_0// "AppConfigMaster"
0x41432  stelem.ref
0x41433  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::InitializeEntity(class [System.Xml]System.Xml.XmlNode entityNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, string[] excludedNodes)
0x41438  ldarg.0
0x41439  ldloc.1
0x4143a  ldloc.s  5
0x4143c  ldarg.0
0x4143d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::_context
0x41442  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::EnsureEntityExisted(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject service, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x41447  ldloc.3
0x41448  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4144d  brtrue.s loc_41401
0x4144f  leave.s  loc_41465
0x41451  ldloc.3
0x41452  isinst   [mscorlib]System.IDisposable
0x41457  stloc.s  6
0x41459  ldloc.s  6
0x4145b  brfalse.s loc_41464
0x4145d  ldloc.s  6
0x4145f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x41464  endfinally
0x41465  leave.s  loc_41471
0x41467  ldloc.2
0x41468  brfalse.s loc_41470
0x4146a  ldloc.2
0x4146b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x41470  endfinally
0x41471  ldarg.0
0x41472  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::_tracer
0x41477  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::AppConfigMasterImportSuccessMessage
0x4147c  ldc.i4.1
0x4147d  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddSuccess(string successMessage, int32 count)
0x41482  leave.s  loc_414A7
0x41484  stloc.s  7
0x41486  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::AppConfigMasterImportErrorMessage
0x4148b  stloc.s  8
0x4148d  ldarg.0
0x4148e  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::_tracer
0x41493  ldloc.s  8
0x41495  ldloc.s  7
0x41497  ldc.i4.1
0x41498  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x4149d  ldloc.s  8
0x4149f  ldloc.s  7
0x414a1  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportGenericEntitiesException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x414a6  throw
0x414a7  ret
```
