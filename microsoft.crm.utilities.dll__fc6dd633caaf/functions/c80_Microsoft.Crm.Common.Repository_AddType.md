# Microsoft.Crm.Common.Repository::AddType

- ea: `0xc80`
- end: `0xcde`
- name: `Microsoft.Crm.Common.Repository::AddType`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0xc80`
- `0x1e20`
- `0x1e40`
- `0x1e60`
- `0x1e70`

## string_xrefs

- `0xca9`: `cachePolicy`

## pseudocode

```c

```

## disassembly

```asm
0xc80  ldarg.1
0xc81  ldnull
0xc82  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xc87  brfalse.s loc_C94
0xc89  ldstr    aObjecttype// "objectType"
0xc8e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xc93  throw
0xc94  ldarg.3
0xc95  brtrue.s loc_CA2
0xc97  ldstr    aDataprovider// "dataProvider"
0xc9c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xca1  throw
0xca2  ldarg.2
0xca3  brfalse.s loc_CB4
0xca5  ldarg.s  4
0xca7  brtrue.s loc_CB4
0xca9  ldstr    aCachepolicy// "cachePolicy"
0xcae  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xcb3  throw
0xcb4  newobj   instance void TypeInformation::.ctor()
0xcb9  stloc.0
0xcba  ldloc.0
0xcbb  ldarg.2
0xcbc  callvirt instance void TypeInformation::set_CacheProvider(class Microsoft.Crm.Common.ICacheProvider value)
0xcc1  ldloc.0
0xcc2  ldarg.s  4
0xcc4  callvirt instance void TypeInformation::set_CachePolicy(class Microsoft.Crm.Common.CachePolicy value)
0xcc9  ldloc.0
0xcca  ldarg.3
0xccb  callvirt instance void TypeInformation::set_DataProvider(class Microsoft.Crm.Common.IDataProvider value)
0xcd0  ldarg.0
0xcd1  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, class TypeInformation> Microsoft.Crm.Common.Repository::_typeInformation
0xcd6  ldarg.1
0xcd7  ldloc.0
0xcd8  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, class TypeInformation>::set_Item(var<u1>, !!T0)
0xcdd  ret
```
