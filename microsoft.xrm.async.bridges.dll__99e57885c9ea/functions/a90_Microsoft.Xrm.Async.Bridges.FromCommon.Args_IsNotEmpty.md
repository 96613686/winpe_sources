# Microsoft.Xrm.Async.Bridges.FromCommon.Args::IsNotEmpty

- ea: `0xa90`
- end: `0xab0`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.Args::IsNotEmpty`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb20`

## callees

- `0xa90`

## pseudocode

```c

```

## disassembly

```asm
0xa90  ldarg.0
0xa91  callvirt instance var<u1> class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<valuetype [mscorlib]System.Guid>::get_Value()
0xa96  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa9b  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xaa0  brfalse.s loc_AAE
0xaa2  ldarg.0
0xaa3  callvirt instance string class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<valuetype [mscorlib]System.Guid>::get_Name()
0xaa8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xaad  throw
0xaae  ldarg.0
0xaaf  ret
```
