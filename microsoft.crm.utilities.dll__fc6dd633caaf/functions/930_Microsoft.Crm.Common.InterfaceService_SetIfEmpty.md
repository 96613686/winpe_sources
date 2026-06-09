# Microsoft.Crm.Common.InterfaceService::SetIfEmpty

- ea: `0x930`
- end: `0x96d`
- name: `Microsoft.Crm.Common.InterfaceService::SetIfEmpty`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x930`
- `0xa30`

## string_xrefs

- `0x945`: `serviceConstructor cannot be null`

## pseudocode

```c

```

## disassembly

```asm
0x930  newobj   instance void class <>c__DisplayClass5_0`1<mvar<u1>>::.ctor()
0x935  stloc.0
0x936  ldloc.0
0x937  ldarg.0
0x938  stfld    class [mscorlib]System.Func`1<var<u1>> class <>c__DisplayClass5_0`1<mvar<u1>>::serviceConstructor
0x93d  ldloc.0
0x93e  ldfld    class [mscorlib]System.Func`1<var<u1>> class <>c__DisplayClass5_0`1<mvar<u1>>::serviceConstructor
0x943  brtrue.s loc_950
0x945  ldstr    aServiceconstru// "serviceConstructor cannot be null"
0x94a  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x94f  throw
0x950  ldtoken  mvar<u1>
0x955  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x95a  ldloc.0
0x95b  ldftn    instance object class <>c__DisplayClass5_0`1<mvar<u1>>::<SetIfEmpty>b__0()
0x961  newobj   instance void class [mscorlib]System.Func`1<object>::.ctor(object, native int)
0x966  ldc.i4.0
0x967  call     void Microsoft.Crm.Common.InterfaceService::Set(class [mscorlib]System.Type interfaceType, class [mscorlib]System.Func`1<object> serviceConstructor, bool overrideExisting)
0x96c  ret
```
