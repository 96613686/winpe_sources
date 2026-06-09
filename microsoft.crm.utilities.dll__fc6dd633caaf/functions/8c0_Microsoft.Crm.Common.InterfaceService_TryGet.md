# Microsoft.Crm.Common.InterfaceService::TryGet

- ea: `0x8c0`
- end: `0x8f0`
- name: `Microsoft.Crm.Common.InterfaceService::TryGet`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x8c0`

## pseudocode

```c

```

## disassembly

```asm
0x8c0  ldtoken  mvar<u1>
0x8c5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8ca  stloc.0
0x8cb  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Lazy`1<object>> Microsoft.Crm.Common.InterfaceService::_services
0x8d0  ldloc.0
0x8d1  ldloca.s 1
0x8d3  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Lazy`1<object>>::TryGetValue(var<u1>, !!T0)
0x8d8  brfalse.s loc_8E6
0x8da  ldloc.1
0x8db  callvirt instance var<u1> class [mscorlib]System.Lazy`1<object>::get_Value()
0x8e0  unbox.any mvar<u1>
0x8e5  ret
0x8e6  ldloca.s 2
0x8e8  initobj  mvar<u1>
0x8ee  ldloc.2
0x8ef  ret
```
