# Microsoft.Crm.Reporting.ReportServer::DeleteItem

- ea: `0x4a20`
- end: `0x4a8c`
- name: `Microsoft.Crm.Reporting.ReportServer::DeleteItem`
- size: `108`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x5950`
- `0x7fc0`

## callees

- `0x4970`
- `0x4a20`
- `0x4c20`
- `0x9290`

## string_xrefs

- `0x4a3b`: `Calling ReportingService.DeleteItem on: {0}.`
- `0x4a71`: `DeleteItem`

## pseudocode

```c

```

## disassembly

```asm
0x4a20  newobj   instance void <>c__DisplayClass27_0::.ctor()
0x4a25  stloc.0
0x4a26  ldloc.0
0x4a27  ldarg.0
0x4a28  stfld    class Microsoft.Crm.Reporting.ReportServer <>c__DisplayClass27_0::<>4__this
0x4a2d  ldloc.0
0x4a2e  ldarg.1
0x4a2f  stfld    string <>c__DisplayClass27_0::path
0x4a34  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x4a39  ldc.i4.s 0x20
0x4a3b  ldstr    aCallingReporti// "Calling ReportingService.DeleteItem on:"...
0x4a40  ldc.i4.1
0x4a41  newarr   [mscorlib]System.Object
0x4a46  dup
0x4a47  ldc.i4.0
0x4a48  ldloc.0
0x4a49  ldfld    string <>c__DisplayClass27_0::path
0x4a4e  stelem.ref
0x4a4f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4a54  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0x4a59  stloc.1
0x4a5a  ldarg.0
0x4a5b  ldloc.0
0x4a5c  ldftn    instance void <>c__DisplayClass27_0::<DeleteItem>b__0()
0x4a62  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x4a67  call     instance void Microsoft.Crm.Reporting.ReportServer::RetryReportsAction(class [mscorlib]System.Action action)
0x4a6c  leave.s  loc_4A8B
0x4a6e  stloc.2
0x4a6f  ldarg.0
0x4a70  ldloc.2
0x4a71  ldstr    aDeleteitem// "DeleteItem"
0x4a76  ldc.i4   0x80048317
0x4a7b  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x4a80  throw
0x4a81  ldloc.1
0x4a82  brfalse.s loc_4A8A
0x4a84  ldloc.1
0x4a85  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4a8a  endfinally
0x4a8b  ret
```
