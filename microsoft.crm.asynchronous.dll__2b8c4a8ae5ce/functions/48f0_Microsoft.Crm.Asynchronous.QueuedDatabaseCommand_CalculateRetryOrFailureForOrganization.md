# Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::CalculateRetryOrFailureForOrganization

- ea: `0x48f0`
- end: `0x49bc`
- name: `Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::CalculateRetryOrFailureForOrganization`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x4710`

## callees

- `0x2650`
- `0x45b0`
- `0x48f0`

## pseudocode

```c

```

## disassembly

```asm
0x48f0  ldc.i4.2
0x48f1  stloc.0
0x48f2  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x48f7  ldarg.0
0x48f8  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::get_Configuration()
0x48fd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x4902  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::GetOrganizationScaleGroupId(valuetype [mscorlib]System.Guid)
0x4907  call     class [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.ScaleGroupInfoProvider::get_Instance()
0x490c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider::GetScaleGroupId()
0x4911  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4916  brfalse.s loc_491C
0x4918  ldc.i4.2
0x4919  stloc.0
0x491a  br.s     loc_4977
0x491c  ldarg.1
0x491d  ldc.i4.1
0x491e  ldc.i4   0xC0004406
0x4923  conv.u8
0x4924  ldc.i4.3
0x4925  newarr   [mscorlib]System.Object
0x492a  dup
0x492b  ldc.i4.0
0x492c  call     string [mscorlib]System.Environment::get_MachineName()
0x4931  stelem.ref
0x4932  dup
0x4933  ldc.i4.1
0x4934  ldarg.0
0x4935  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::get_Configuration()
0x493a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x493f  box      [mscorlib]System.Guid
0x4944  stelem.ref
0x4945  dup
0x4946  ldc.i4.2
0x4947  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x494c  ldstr    aOrganization0I// "Organization '{0}' is no longer in this"...
0x4951  ldc.i4.1
0x4952  newarr   [mscorlib]System.Object
0x4957  dup
0x4958  ldc.i4.0
0x4959  ldarg.0
0x495a  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::get_Configuration()
0x495f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x4964  box      [mscorlib]System.Guid
0x4969  stelem.ref
0x496a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x496f  stelem.ref
0x4970  callvirt instance void Microsoft.Crm.Asynchronous.AsyncManagerBase::LogEvent(valuetype [System]System.Diagnostics.EventLogEntryType eventType, int64 eventId, object[] parameters)
0x4975  ldc.i4.1
0x4976  stloc.0
0x4977  leave.s  loc_49BA
0x4979  stloc.1
0x497a  ldarg.1
0x497b  ldc.i4.1
0x497c  ldc.i4   0xC0004406
0x4981  conv.u8
0x4982  ldc.i4.3
0x4983  newarr   [mscorlib]System.Object
0x4988  dup
0x4989  ldc.i4.0
0x498a  call     string [mscorlib]System.Environment::get_MachineName()
0x498f  stelem.ref
0x4990  dup
0x4991  ldc.i4.1
0x4992  ldarg.0
0x4993  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::get_Configuration()
0x4998  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x499d  box      [mscorlib]System.Guid
0x49a2  stelem.ref
0x49a3  dup
0x49a4  ldc.i4.2
0x49a5  ldloc.1
0x49a6  callvirt instance string [mscorlib]System.Object::ToString()
0x49ab  stelem.ref
0x49ac  callvirt instance void Microsoft.Crm.Asynchronous.AsyncManagerBase::LogEvent(valuetype [System]System.Diagnostics.EventLogEntryType eventType, int64 eventId, object[] parameters)
0x49b1  ldc.i4.1
0x49b2  stloc.0
0x49b3  leave.s  loc_49BA
0x49b5  pop
0x49b6  ldc.i4.2
0x49b7  stloc.0
0x49b8  leave.s  loc_49BA
0x49ba  ldloc.0
0x49bb  ret
```
