# Microsoft.Crm.Common.InterfaceService::Set_0

- ea: `0xa30`
- end: `0xae4`
- name: `Microsoft.Crm.Common.InterfaceService::Set_0`
- size: `180`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8f0`
- `0x930`
- `0x970`

## callees

- `0xa30`

## string_xrefs

- `0xa47`: `serviceConstructor cannot be null`

## pseudocode

```c

```

## disassembly

```asm
0xa30  ldarg.0
0xa31  ldnull
0xa32  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xa37  brfalse.s loc_A44
0xa39  ldstr    aInterfacetypeC// "interfaceType cannot be null"
0xa3e  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xa43  throw
0xa44  ldarg.1
0xa45  brtrue.s loc_A52
0xa47  ldstr    aServiceconstru// "serviceConstructor cannot be null"
0xa4c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xa51  throw
0xa52  ldarg.0
0xa53  callvirt instance bool [mscorlib]System.Type::get_IsInterface()
0xa58  brtrue.s loc_A75
0xa5a  ldstr    aType// "Type ["
0xa5f  ldarg.0
0xa60  callvirt instance string [mscorlib]System.Type::get_FullName()
0xa65  ldstr    aMustBeAnInterf// "] must be an interface"
0xa6a  call     string [mscorlib]System.String::Concat(string, string, string)
0xa6f  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xa74  throw
0xa75  ldarg.0
0xa76  callvirt instance class [mscorlib]System.Type[] [mscorlib]System.Type::GetInterfaces()
0xa7b  ldsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Type, bool> <>c::<>9__7_0
0xa80  dup
0xa81  brtrue.s loc_A9A
0xa83  pop
0xa84  ldsfld   class <>c <>c::<>9
0xa89  ldftn    instance bool <>c::<Set>b__7_0(class [mscorlib]System.Type x)
0xa8f  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Type, bool>::.ctor(object, native int)
0xa94  dup
0xa95  stsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Type, bool> <>c::<>9__7_0
0xa9a  call     T0x2B000002
0xa9f  brfalse.s loc_ABC
0xaa1  ldstr    aType// "Type ["
0xaa6  ldarg.0
0xaa7  callvirt instance string [mscorlib]System.Type::get_FullName()
0xaac  ldstr    aCannotBeIdispo// "] cannot be IDisposable"
0xab1  call     string [mscorlib]System.String::Concat(string, string, string)
0xab6  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xabb  throw
0xabc  ldarg.2
0xabd  brfalse.s loc_AD1
0xabf  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Lazy`1<object>> Microsoft.Crm.Common.InterfaceService::_services
0xac4  ldarg.0
0xac5  ldarg.1
0xac6  newobj   instance void class [mscorlib]System.Lazy`1<object>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0xacb  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Lazy`1<object>>::set_Item(var<u1>, !!T0)
0xad0  ret
0xad1  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Lazy`1<object>> Microsoft.Crm.Common.InterfaceService::_services
0xad6  ldarg.0
0xad7  ldarg.1
0xad8  newobj   instance void class [mscorlib]System.Lazy`1<object>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0xadd  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Lazy`1<object>>::TryAdd(var<u1>, !!T0)
0xae2  pop
0xae3  ret
```
