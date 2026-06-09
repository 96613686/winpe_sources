# Microsoft.Crm.Common.InterfaceService::Set

- ea: `0x8f0`
- end: `0x92d`
- name: `Microsoft.Crm.Common.InterfaceService::Set`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x8f0`
- `0xa30`

## string_xrefs

- `0x905`: `serviceConstructor cannot be null`

## pseudocode

```c

```

## disassembly

```asm
0x8f0  newobj   instance void class <>c__DisplayClass4_0`1<mvar<u1>>::.ctor()
0x8f5  stloc.0
0x8f6  ldloc.0
0x8f7  ldarg.0
0x8f8  stfld    class [mscorlib]System.Func`1<var<u1>> class <>c__DisplayClass4_0`1<mvar<u1>>::serviceConstructor
0x8fd  ldloc.0
0x8fe  ldfld    class [mscorlib]System.Func`1<var<u1>> class <>c__DisplayClass4_0`1<mvar<u1>>::serviceConstructor
0x903  brtrue.s loc_910
0x905  ldstr    aServiceconstru// "serviceConstructor cannot be null"
0x90a  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x90f  throw
0x910  ldtoken  mvar<u1>
0x915  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x91a  ldloc.0
0x91b  ldftn    instance object class <>c__DisplayClass4_0`1<mvar<u1>>::<Set>b__0()
0x921  newobj   instance void class [mscorlib]System.Func`1<object>::.ctor(object, native int)
0x926  ldc.i4.1
0x927  call     void Microsoft.Crm.Common.InterfaceService::Set(class [mscorlib]System.Type interfaceType, class [mscorlib]System.Func`1<object> serviceConstructor, bool overrideExisting)
0x92c  ret
```
