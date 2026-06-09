# Microsoft.Xrm.Async.Bridges.FromCommon.Args::IsNotNull

- ea: `0xa70`
- end: `0xa8b`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.Args::IsNotNull`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xa70`

## pseudocode

```c

```

## disassembly

```asm
0xa70  ldarg.0
0xa71  callvirt instance var<u1> class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<mvar<u1>>::get_Value()
0xa76  box      mvar<u1>
0xa7b  brtrue.s loc_A89
0xa7d  ldarg.0
0xa7e  callvirt instance string class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<mvar<u1>>::get_Name()
0xa83  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa88  throw
0xa89  ldarg.0
0xa8a  ret
```
