# Microsoft.Crm.Service.ObjectModel.IncidentService::SetStateForChildRecords

- ea: `0x1da0`
- end: `0x1e87`
- name: `Microsoft.Crm.Service.ObjectModel.IncidentService::SetStateForChildRecords`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1e90`

## callees

- `0x1980`
- `0x1da0`
- `0x2160`

## pseudocode

```c

```

## disassembly

```asm
0x1da0  ldarg.1
0x1da1  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x1da6  stloc.0
0x1da7  br       loc_1E65
0x1dac  ldloc.0
0x1dad  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1db2  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x1db7  stloc.1
0x1db8  ldloc.1
0x1db9  ldstr    aIncidentid// "incidentid"
0x1dbe  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc3  unbox.any [mscorlib]System.Guid
0x1dc8  ldloc.1
0x1dc9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x1dce  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x1dd3  ldarg.s  5
0x1dd5  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1dda  stloc.2
0x1ddb  ldarg.3
0x1ddc  ldc.i4.2
0x1ddd  bne.un.s loc_1DED
0x1ddf  ldarg.0
0x1de0  ldloc.2
0x1de1  ldarg.s  4
0x1de3  ldarg.s  5
0x1de5  call     instance bool Microsoft.Crm.Service.ObjectModel.IncidentService::Cancel(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, int32 status, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1dea  pop
0x1deb  br.s     loc_1E65
0x1ded  ldarg.3
0x1dee  ldc.i4.1
0x1def  bne.un.s loc_1E65
0x1df1  ldarg.s  5
0x1df3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1df8  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.IncidentResolution::.ctor(valuetype [mscorlib]System.Guid)
0x1dfd  stloc.3
0x1dfe  ldloc.3
0x1dff  ldstr    aIncidentid// "incidentid"
0x1e04  ldloc.2
0x1e05  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x1e0a  box      [mscorlib]System.Guid
0x1e0f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1e14  ldloc.3
0x1e15  ldstr    aSubject// "subject"
0x1e1a  ldloc.1
0x1e1b  ldstr    aTitle// "title"
0x1e20  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e25  callvirt instance string [mscorlib]System.Object::ToString()
0x1e2a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1e2f  ldloc.3
0x1e30  ldstr    aActualend// "actualend"
0x1e35  ldarg.2
0x1e36  ldstr    aActualend// "actualend"
0x1e3b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e40  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1e45  ldloc.3
0x1e46  ldstr    aActivityid// "activityid"
0x1e4b  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x1e50  box      [mscorlib]System.Guid
0x1e55  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1e5a  ldarg.0
0x1e5b  ldloc.3
0x1e5c  ldarg.s  4
0x1e5e  ldarg.s  5
0x1e60  call     instance void Microsoft.Crm.Service.ObjectModel.IncidentService::Close(class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.IncidentResolution incidentResolution, int32 status, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1e65  ldloc.0
0x1e66  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1e6b  brtrue   loc_1DAC
0x1e70  leave.s  loc_1E86
0x1e72  ldloc.0
0x1e73  isinst   [mscorlib]System.IDisposable
0x1e78  stloc.s  4
0x1e7a  ldloc.s  4
0x1e7c  brfalse.s loc_1E85
0x1e7e  ldloc.s  4
0x1e80  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e85  endfinally
0x1e86  ret
```
