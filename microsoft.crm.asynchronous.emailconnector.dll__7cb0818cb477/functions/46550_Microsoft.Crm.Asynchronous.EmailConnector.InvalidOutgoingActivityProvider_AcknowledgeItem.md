# Microsoft.Crm.Asynchronous.EmailConnector.InvalidOutgoingActivityProvider::AcknowledgeItem

- ea: `0x46550`
- end: `0x465a8`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.InvalidOutgoingActivityProvider::AcknowledgeItem`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0xa740`
- `0x420e0`
- `0x46550`
- `0x4e480`

## string_xrefs

- `0x4658c`: `Server-Side Synchronization (Outgoing): Items Failed`
- `0x46596`: `Server-Side Synchronization (Outgoing): Items Failed Throughput`

## pseudocode

```c

```

## disassembly

```asm
0x46550  ldarg.1
0x46551  brfalse.s loc_4655E
0x46553  ldarg.1
0x46554  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::get_Entity()
0x46559  ldnull
0x4655a  cgt.un
0x4655c  br.s     loc_4655F
0x4655e  ldc.i4.0
0x4655f  ldstr    aOutgoingActivi_0// "Outgoing activity cannot be null."
0x46564  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x46569  ldarg.1
0x4656a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::get_Entity()
0x4656f  call     valuetype [mscorlib]System.Nullable`1<int32> Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::GetActivityTypeCode(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity activity)
0x46574  stloc.0
0x46575  ldloca.s 0
0x46577  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x4657c  brfalse.s loc_465A0
0x4657e  ldc.i4   0x106A
0x46583  ldloca.s 0
0x46585  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x4658a  bne.un.s loc_465A0
0x4658c  ldstr    aServerSideSync_15// "Server-Side Synchronization (Outgoing):"...
0x46591  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x46596  ldstr    aServerSideSync_16// "Server-Side Synchronization (Outgoing):"...
0x4659b  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x465a0  ldarg.0
0x465a1  ldarg.1
0x465a2  call     instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionResult class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IInvalidActivityProviderContext>::AcknowledgeItem(class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity)
0x465a7  ret
```
