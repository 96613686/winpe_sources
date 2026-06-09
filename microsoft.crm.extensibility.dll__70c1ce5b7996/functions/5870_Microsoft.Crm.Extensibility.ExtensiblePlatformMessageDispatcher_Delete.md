# Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::Delete

- ea: `0x5870`
- end: `0x591b`
- name: `Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::Delete`
- size: `171`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x5870`
- `0x6120`
- `0x6140`
- `0x6160`

## string_xrefs

- `0x5872`: `Delete`
- `0x58de`: `Delete`
- `0x58e3`: `Delete`

## pseudocode

```c

```

## disassembly

```asm
0x5870  ldc.i4.1
0x5871  stloc.0
0x5872  ldstr    aDelete// "Delete"
0x5877  ldarg.1
0x5878  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x587d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x5882  ldc.i4.0
0x5883  stloc.3
0x5884  ldloca.s 3
0x5886  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Extensibility.EntityName
0x588c  callvirt instance string [mscorlib]System.Object::ToString()
0x5891  ldloc.0
0x5892  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MessageProcessorKey::.ctor(string, string, string, int32)
0x5897  stloc.1
0x5898  ldarg.0
0x5899  ldloc.1
0x589a  ldarg.2
0x589b  call     instance bool Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::IsPipelineDefined(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MessageProcessorKey key, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x58a0  brtrue.s loc_58B0
0x58a2  ldarg.0
0x58a3  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IPlatformMessageDispatcher Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::_backupDispatcher
0x58a8  ldarg.1
0x58a9  ldarg.2
0x58aa  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IPlatformMessageDispatcher::Delete(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x58af  ret
0x58b0  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection::.ctor()
0x58b5  stloc.2
0x58b6  ldloc.2
0x58b7  ldstr    aTarget// "Target"
0x58bc  ldarg.1
0x58bd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x58c2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x58c7  ldarg.1
0x58c8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x58cd  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x58d2  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x58d7  ldarg.0
0x58d8  ldarg.2
0x58d9  call     instance class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::GetInternalServiceFactoryFromContext(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x58de  ldstr    aDelete// "Delete"
0x58e3  ldstr    aDelete// "Delete"
0x58e8  ldc.i4.0
0x58e9  ldarg.1
0x58ea  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x58ef  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0x58f4  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_ObjectTypeCode()
0x58f9  ldc.i4.0
0x58fa  ldloc.2
0x58fb  ldloc.0
0x58fc  ldarg.2
0x58fd  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::.ctor(class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory, string, string, int32, int32, int32, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5902  stloc.s  4
0x5904  ldarg.0
0x5905  ldloc.s  4
0x5907  call     instance void Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::Execute(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext pluginContext)
0x590c  leave.s  loc_591A
0x590e  ldloc.s  4
0x5910  brfalse.s loc_5919
0x5912  ldloc.s  4
0x5914  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5919  endfinally
0x591a  ret
```
