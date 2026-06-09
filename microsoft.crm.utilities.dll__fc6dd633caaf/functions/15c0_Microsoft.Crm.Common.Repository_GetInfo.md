# Microsoft.Crm.Common.Repository::GetInfo

- ea: `0x15c0`
- end: `0x15fc`
- name: `Microsoft.Crm.Common.Repository::GetInfo`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x15c0`

## pseudocode

```c

```

## disassembly

```asm
0x15c0  ldtoken  mvar<u1>
0x15c5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15ca  stloc.0
0x15cb  ldarg.0
0x15cc  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, class TypeInformation> Microsoft.Crm.Common.Repository::_typeInformation
0x15d1  ldloc.0
0x15d2  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, class TypeInformation>::ContainsKey(var<u1>)
0x15d7  brtrue.s loc_15EF
0x15d9  ldstr    aUnknownTypeEnc// "Unknown type encountered : "
0x15de  ldloc.0
0x15df  callvirt instance string [mscorlib]System.Type::get_FullName()
0x15e4  call     string [mscorlib]System.String::Concat(string, string)
0x15e9  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x15ee  throw
0x15ef  ldarg.0
0x15f0  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, class TypeInformation> Microsoft.Crm.Common.Repository::_typeInformation
0x15f5  ldloc.0
0x15f6  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, class TypeInformation>::get_Item(void)
0x15fb  ret
```
