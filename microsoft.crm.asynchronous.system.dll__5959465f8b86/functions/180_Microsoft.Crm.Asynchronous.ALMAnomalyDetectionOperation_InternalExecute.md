# Microsoft.Crm.Asynchronous.ALMAnomalyDetectionOperation::InternalExecute

- ea: `0x180`
- end: `0x20e`
- name: `Microsoft.Crm.Asynchronous.ALMAnomalyDetectionOperation::InternalExecute`
- size: `142`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180`
- `0x380`
- `0x3d0`

## string_xrefs

- `0x19c`: `Start finding anomalies created by solution import/uninstall for org {0}`

## pseudocode

```c

```

## disassembly

```asm
0x180  ldarg.1
0x181  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0x186  ldc.i4.s 0x49
0x188  ceq
0x18a  ldstr    aOperationTypeM// "Operation type must be 'ALM Anomaly Det"...
0x18f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x194  ldarg.1
0x195  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x19a  ldc.i4.s 0x15
0x19c  ldstr    aStartFindingAn// "Start finding anomalies created by solu"...
0x1a1  ldc.i4.1
0x1a2  newarr   [mscorlib]System.Object
0x1a7  dup
0x1a8  ldc.i4.0
0x1a9  ldarg.0
0x1aa  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x1af  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x1b4  box      [mscorlib]System.Guid
0x1b9  stelem.ref
0x1ba  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1bf  ldarg.1
0x1c0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x1c5  newobj   instance void Microsoft.Crm.Asynchronous.ALMAnomalyDetectionJob::.ctor(valuetype [mscorlib]System.Guid organizationId)
0x1ca  stloc.0
0x1cb  ldloc.0
0x1cc  callvirt instance void Microsoft.Crm.Asynchronous.ALMAnomalyDetectionJob::Run()
0x1d1  ldarg.1
0x1d2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x1d7  ldc.i4.s 0x15
0x1d9  ldstr    aAlmanomalyDete// "ALMAnomaly Detection Job ran sucessfull"...
0x1de  ldc.i4.1
0x1df  newarr   [mscorlib]System.Object
0x1e4  dup
0x1e5  ldc.i4.0
0x1e6  ldarg.0
0x1e7  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x1ec  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x1f1  box      [mscorlib]System.Guid
0x1f6  stelem.ref
0x1f7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1fc  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor()
0x201  stloc.1
0x202  leave.s  loc_20C
0x204  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(class [mscorlib]System.Exception)
0x209  stloc.1
0x20a  leave.s  loc_20C
0x20c  ldloc.1
0x20d  ret
```
