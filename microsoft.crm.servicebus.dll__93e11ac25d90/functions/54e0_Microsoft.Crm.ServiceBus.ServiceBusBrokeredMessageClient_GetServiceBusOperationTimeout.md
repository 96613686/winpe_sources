# Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::GetServiceBusOperationTimeout

- ea: `0x54e0`
- end: `0x5541`
- name: `Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::GetServiceBusOperationTimeout`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x4e40`

## callees

- `0x54e0`

## string_xrefs

- `0x54e6`: `ServiceBusOperationTimeoutInSecs`
- `0x5523`: `Exception when trying to fetch ServiceBusOperationTimeoutInSecs from registry: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x54e0  ldsfld   valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::MaxValue
0x54e5  stloc.0
0x54e6  ldstr    aServicebusoper// "ServiceBusOperationTimeoutInSecs"
0x54eb  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x54f0  stloc.1
0x54f1  ldloc.1
0x54f2  brfalse.s loc_550A
0x54f4  ldloc.1
0x54f5  isinst   [mscorlib]System.Int32
0x54fa  brfalse.s loc_550A
0x54fc  ldc.i4.0
0x54fd  ldc.i4.0
0x54fe  ldloc.1
0x54ff  unbox.any [mscorlib]System.Int32
0x5504  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x5509  stloc.0
0x550a  leave.s  loc_553F
0x550c  stloc.2
0x550d  ldloc.2
0x550e  ldarg.1
0x550f  ldc.i4.s 0x2F
0x5511  ldstr    a0// "{0}"
0x5516  ldc.i4.1
0x5517  newarr   [mscorlib]System.Object
0x551c  dup
0x551d  ldc.i4.0
0x551e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5523  ldstr    aExceptionWhenT_0// "Exception when trying to fetch ServiceB"...
0x5528  ldc.i4.1
0x5529  newarr   [mscorlib]System.Object
0x552e  dup
0x552f  ldc.i4.0
0x5530  ldloc.2
0x5531  stelem.ref
0x5532  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5537  stelem.ref
0x5538  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x553d  leave.s  loc_553F
0x553f  ldloc.0
0x5540  ret
```
