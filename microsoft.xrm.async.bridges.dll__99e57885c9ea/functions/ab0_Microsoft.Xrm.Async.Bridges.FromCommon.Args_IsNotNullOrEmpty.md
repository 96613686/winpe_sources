# Microsoft.Xrm.Async.Bridges.FromCommon.Args::IsNotNullOrEmpty

- ea: `0xab0`
- end: `0xacb`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.Args::IsNotNullOrEmpty`
- size: `27`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10f0`
- `0x1780`
- `0x1810`
- `0x1880`
- `0x18d0`
- `0x1d20`
- `0x2290`
- `0x22f0`
- `0x39e0`

## callees

- `0xab0`

## pseudocode

```c

```

## disassembly

```asm
0xab0  ldarg.0
0xab1  callvirt instance var<u1> class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string>::get_Value()
0xab6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xabb  brfalse.s loc_AC9
0xabd  ldarg.0
0xabe  callvirt instance string class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string>::get_Name()
0xac3  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xac8  throw
0xac9  ldarg.0
0xaca  ret
```
