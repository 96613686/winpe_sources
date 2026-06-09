# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeEmailMessage::ValidateMessage

- ea: `0x301a0`
- end: `0x301d3`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeEmailMessage::ValidateMessage`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x301a0`
- `0x30440`
- `0x30450`
- `0x4e480`

## string_xrefs

- `0x301bb`: `Server-Side Synchronization (Incoming): Items Suspected`
- `0x301c5`: `Server-Side Synchronization (Incoming): Items Suspected Throughput`

## pseudocode

```c

```

## disassembly

```asm
0x301a0  ldarg.0
0x301a1  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeEmailMessage::get_HasAttachments()
0x301a6  brfalse.s loc_301B8
0x301a8  ldarg.0
0x301a9  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Asynchronous.EmailConnector.AttachmentType> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeEmailMessage::get_AttachmentTypes()
0x301ae  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Asynchronous.EmailConnector.AttachmentType>::get_Count()
0x301b3  ldc.i4.1
0x301b4  ceq
0x301b6  br.s     loc_301B9
0x301b8  ldc.i4.0
0x301b9  brtrue.s loc_301D1
0x301bb  ldstr    aServerSideSync_4// "Server-Side Synchronization (Incoming):"...
0x301c0  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x301c5  ldstr    aServerSideSync_5// "Server-Side Synchronization (Incoming):"...
0x301ca  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x301cf  ldc.i4.0
0x301d0  ret
0x301d1  ldc.i4.1
0x301d2  ret
```
