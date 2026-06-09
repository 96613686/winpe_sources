# Microsoft.Crm.Common.Repository::.ctor

- ea: `0x1960`
- end: `0x1983`
- name: `Microsoft.Crm.Common.Repository::.ctor`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1960  ldarg.0
0x1961  ldc.i4.8
0x1962  ldc.i4.s 0xB
0x1964  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, class TypeInformation>::.ctor(int32, int32)
0x1969  stfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, class TypeInformation> Microsoft.Crm.Common.Repository::_typeInformation
0x196e  ldarg.0
0x196f  ldc.i4.8
0x1970  ldc.i4.s 0xB
0x1972  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, string>::.ctor(int32, int32)
0x1977  stfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, string> Microsoft.Crm.Common.Repository::_primaryKeyName
0x197c  ldarg.0
0x197d  call     instance void [mscorlib]System.Object::.ctor()
0x1982  ret
```
