# Microsoft.Crm.Common.Application.Platform.List::CreateActivities

- ea: `0x4470`
- end: `0x4530`
- name: `Microsoft.Crm.Common.Application.Platform.List::CreateActivities`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4390`

## callees

- `0x26f0`
- `0x4470`
- `0x4550`

## string_xrefs

- `0x447a`: `CreateActivities with friendlyName={0}, activityXml={1}, activityObjectTypeCode={2}, templateId={3}, ownerOption={4}, postWorkFlowEvent={5}`

## pseudocode

```c

```

## disassembly

```asm
0x4470  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x4475  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x447a  ldstr    aCreateactiviti// "CreateActivities with friendlyName={0},"...
0x447f  ldc.i4.6
0x4480  newarr   [mscorlib]System.Object
0x4485  dup
0x4486  ldc.i4.0
0x4487  ldarg.2
0x4488  stelem.ref
0x4489  dup
0x448a  ldc.i4.1
0x448b  ldarg.3
0x448c  stelem.ref
0x448d  dup
0x448e  ldc.i4.2
0x448f  ldarg.s  4
0x4491  box      [mscorlib]System.Int32
0x4496  stelem.ref
0x4497  dup
0x4498  ldc.i4.3
0x4499  ldarg.s  5
0x449b  stelem.ref
0x449c  dup
0x449d  ldc.i4.4
0x449e  ldarg.s  6
0x44a0  box      [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropagationOwnershipOptions
0x44a5  stelem.ref
0x44a6  dup
0x44a7  ldc.i4.5
0x44a8  ldarg.s  9
0x44aa  box      [mscorlib]System.Boolean
0x44af  stelem.ref
0x44b0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x44b5  ldarg.s  4
0x44b7  ldc.i4   0x1069
0x44bc  bne.un.s loc_44E8
0x44be  ldarg.s  4
0x44c0  ldarg.0
0x44c1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x44c6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x44cb  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x44d0  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x44d5  ldarg.3
0x44d6  ldarg.0
0x44d7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x44dc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x44e1  call     string Microsoft.Crm.Common.Application.Platform.ActivityBase::FixStateCode(string entityName, string entityXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x44e6  starg.s  3
0x44e8  ldarg.0
0x44e9  ldarg.1
0x44ea  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x44ef  ldarg.2
0x44f0  ldarg.3
0x44f1  ldarg.s  4
0x44f3  ldarg.s  5
0x44f5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x44fa  brtrue.s loc_4505
0x44fc  ldarg.s  5
0x44fe  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4503  br.s     loc_450A
0x4505  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x450a  ldarg.s  6
0x450c  ldarg.s  7
0x450e  ldarg.s  8
0x4510  ldc.i4.0
0x4511  ldarg.s  0xA
0x4513  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Common.Application.Platform.List::ListCreateActivities(valuetype [mscorlib]System.Guid listId, string friendlyName, string activityXml, int32 activityObjectTypeCode, valuetype [mscorlib]System.Guid templateId, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropagationOwnershipOptions ownershipOption, valuetype [mscorlib]System.Guid ownerId, int32 ownerType, bool sendEmail, valuetype [mscorlib]System.Guid queueId)
0x4518  stloc.0
0x4519  ldloca.s 0
0x451b  ldstr    aB_1// "B"
0x4520  call     instance string [mscorlib]System.Guid::ToString(string)
0x4525  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x452a  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x452f  ret
```
