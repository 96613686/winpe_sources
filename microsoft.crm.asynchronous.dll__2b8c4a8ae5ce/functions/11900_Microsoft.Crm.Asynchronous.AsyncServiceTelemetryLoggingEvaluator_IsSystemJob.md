# Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator::IsSystemJob

- ea: `0x11900`
- end: `0x1191d`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator::IsSystemJob`
- size: `29`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x110e0`
- `0x118d0`

## callees

- `0x11900`
- `0x11920`
- `0x121f0`

## pseudocode

```c

```

## disassembly

```asm
0x11900  ldarg.0
0x11901  ldarg.1
0x11902  call     instance bool Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator::HasFixedId(class Microsoft.Crm.Asynchronous.IAsyncEvent asyncEvent)
0x11907  brtrue.s loc_1191B
0x11909  ldarg.0
0x1190a  ldfld    class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator::_systemJobTypes
0x1190f  ldarg.1
0x11910  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncEvent::get_OperationType()
0x11915  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<int32>::Contains(var<u1>)
0x1191a  ret
0x1191b  ldc.i4.1
0x1191c  ret
```
