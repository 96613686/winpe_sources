# Microsoft.Crm.Tools.Unzip.UnzipToolException::.ctor

- ea: `0x290`
- end: `0x29e`
- name: `Microsoft.Crm.Tools.Unzip.UnzipToolException::.ctor`
- size: `14`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x400`
- `0x680`
- `0x6f0`
- `0xa20`
- `0xbe0`

## pseudocode

```c

```

## disassembly

```asm
0x290  ldarg.0
0x291  call     instance void [mscorlib]System.Exception::.ctor()
0x296  ldarg.0
0x297  ldarg.1
0x298  stfld    int32 Microsoft.Crm.Tools.Unzip.UnzipToolException::errorCode
0x29d  ret
```
