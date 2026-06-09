# Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::Parse

- ea: `0x2620`
- end: `0x263c`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::Parse`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x2620`
- `0x2640`

## pseudocode

```c

```

## disassembly

```asm
0x2620  ldarg.0
0x2621  ldloca.s 0
0x2623  call     bool Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::TryParse(string connectionString, [out] class Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString& value)
0x2628  brfalse.s loc_262C
0x262a  ldloc.0
0x262b  ret
0x262c  ldstr    aTheConnectionS// "The connection string is not valid."
0x2631  ldstr    aConnectionstri_0// "connectionString"
0x2636  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x263b  throw
```
