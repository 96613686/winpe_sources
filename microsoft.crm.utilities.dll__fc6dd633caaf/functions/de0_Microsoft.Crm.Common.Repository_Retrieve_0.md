# Microsoft.Crm.Common.Repository::Retrieve_0

- ea: `0xde0`
- end: `0xdf7`
- name: `Microsoft.Crm.Common.Repository::Retrieve_0`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xde0`

## pseudocode

```c

```

## disassembly

```asm
0xde0  ldarg.1
0xde1  brtrue.s loc_DEE
0xde3  ldstr    aQuery// "query"
0xde8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xded  throw
0xdee  ldarg.0
0xdef  ldarg.1
0xdf0  ldc.i4.1
0xdf1  call     T0x2B000003
0xdf6  ret
```
