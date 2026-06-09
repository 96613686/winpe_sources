# Microsoft.Crm.Common.Repository::RetrieveSkipCache_0

- ea: `0xe00`
- end: `0xe17`
- name: `Microsoft.Crm.Common.Repository::RetrieveSkipCache_0`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xe00`

## pseudocode

```c

```

## disassembly

```asm
0xe00  ldarg.1
0xe01  brtrue.s loc_E0E
0xe03  ldstr    aQuery// "query"
0xe08  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xe0d  throw
0xe0e  ldarg.0
0xe0f  ldarg.1
0xe10  ldc.i4.0
0xe11  call     T0x2B000003
0xe16  ret
```
