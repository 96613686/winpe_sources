# Microsoft.Crm.ServiceBus.ServiceBusService::IsKnownType

- ea: `0x1310`
- end: `0x134a`
- name: `Microsoft.Crm.ServiceBus.ServiceBusService::IsKnownType`
- size: `58`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1190`
- `0x12b0`

## callees

- `0x1310`

## pseudocode

```c

```

## disassembly

```asm
0x1310  ldc.i4.0
0x1311  stloc.0
0x1312  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type> Microsoft.Crm.ServiceBus.ServiceBusService::knownTypes
0x1317  brtrue.s loc_1328
0x1319  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.KnownTypesProvider::RetrieveKnownValueTypes()
0x131e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x1323  stsfld   class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type> Microsoft.Crm.ServiceBus.ServiceBusService::knownTypes
0x1328  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type> Microsoft.Crm.ServiceBus.ServiceBusService::knownTypes
0x132d  ldarg.0
0x132e  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::Contains(var<u1>)
0x1333  stloc.0
0x1334  ldarg.0
0x1335  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ConcurrencyBehavior
0x133a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x133f  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0x1344  brfalse.s loc_1348
0x1346  ldc.i4.0
0x1347  stloc.0
0x1348  ldloc.0
0x1349  ret
```
