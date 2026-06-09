# Microsoft.Crm.Common.Application.Platform.List::CreateListActivity

- ea: `0x4390`
- end: `0x4462`
- name: `Microsoft.Crm.Common.Application.Platform.List::CreateListActivity`
- size: `210`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4390`
- `0x4470`

## string_xrefs

- `0x439a`: `CreateListActivity with formXml={0}, ownerOption={1}, postWorkFlowEvent={2}`
- `0x43f7`: `CreateListEmail list active = {0}`

## pseudocode

```c

```

## disassembly

```asm
0x4390  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x4395  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x439a  ldstr    aCreatelistacti// "CreateListActivity with formXml={0}, ow"...
0x439f  ldc.i4.3
0x43a0  newarr   [mscorlib]System.Object
0x43a5  dup
0x43a6  ldc.i4.0
0x43a7  ldarg.2
0x43a8  stelem.ref
0x43a9  dup
0x43aa  ldc.i4.1
0x43ab  ldarg.s  5
0x43ad  box      [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropagationOwnershipOptions
0x43b2  stelem.ref
0x43b3  dup
0x43b4  ldc.i4.2
0x43b5  ldarg.s  8
0x43b7  box      [mscorlib]System.Boolean
0x43bc  stelem.ref
0x43bd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x43c2  ldarg.0
0x43c3  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x43c8  ldarg.1
0x43c9  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x43ce  ldc.i4.1
0x43cf  newarr   [mscorlib]System.String
0x43d4  dup
0x43d5  ldc.i4.0
0x43d6  ldstr    aStatecode// "statecode"
0x43db  stelem.ref
0x43dc  ldarg.0
0x43dd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x43e2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x43e7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x43ec  stloc.0
0x43ed  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x43f2  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x43f7  ldstr    aCreatelistemai// "CreateListEmail list active = {0}"
0x43fc  ldc.i4.1
0x43fd  newarr   [mscorlib]System.Object
0x4402  dup
0x4403  ldc.i4.0
0x4404  ldloc.0
0x4405  ldstr    aStatecode// "statecode"
0x440a  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x440f  castclass [mscorlib]System.String
0x4414  stelem.ref
0x4415  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x441a  ldtoken  [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.ListState
0x441f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4424  ldloc.0
0x4425  ldstr    aStatecode// "statecode"
0x442a  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x442f  castclass [mscorlib]System.String
0x4434  ldc.i4.1
0x4435  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string, bool)
0x443a  unbox.any [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.ListState
0x443f  brtrue.s loc_445C
0x4441  ldarg.0
0x4442  ldarg.1
0x4443  ldstr    asc_882E// ""
0x4448  ldarg.2
0x4449  ldarg.3
0x444a  ldarg.s  4
0x444c  ldarg.s  5
0x444e  ldarg.s  6
0x4450  ldarg.s  7
0x4452  ldarg.s  8
0x4454  ldarg.s  9
0x4456  call     instance string Microsoft.Crm.Common.Application.Platform.List::CreateActivities(string listId, string friendlyName, string activityXml, int32 activityObjectTypeCode, string templateId, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropagationOwnershipOptions ownershipOption, valuetype [mscorlib]System.Guid ownerId, int32 ownerType, bool postWorkflowEvent, valuetype [mscorlib]System.Guid queueId)
0x445b  ret
0x445c  ldsfld   string [mscorlib]System.String::Empty
0x4461  ret
```
