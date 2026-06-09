# Microsoft.Xrm.Async.Bridges.FromCommon.Args::IsOfType

- ea: `0xad0`
- end: `0xb1c`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.Args::IsOfType`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xad0`

## pseudocode

```c

```

## disassembly

```asm
0xad0  ldarg.0
0xad1  callvirt instance var<u1> class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<object>::get_Value()
0xad6  isinst   mvar<u1>
0xadb  brfalse.s loc_AF4
0xadd  ldarg.0
0xade  callvirt instance var<u1> class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<object>::get_Value()
0xae3  unbox.any mvar<u1>
0xae8  ldarg.0
0xae9  callvirt instance string class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<object>::get_Name()
0xaee  newobj   instance void class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<mvar<u1>>::.ctor(var<u1>, !!T0)
0xaf3  ret
0xaf4  ldstr    aTheObject0IsNo// "The object '{0}' is not a valid {1}."
0xaf9  ldarg.0
0xafa  callvirt instance var<u1> class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<object>::get_Value()
0xaff  ldtoken  mvar<u1>
0xb04  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb09  call     string [mscorlib]System.String::Format(string, object, object)
0xb0e  stloc.0
0xb0f  ldarg.0
0xb10  callvirt instance string class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<object>::get_Name()
0xb15  ldloc.0
0xb16  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, string)
0xb1b  throw
```
