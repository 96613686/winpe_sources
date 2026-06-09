# Microsoft.Crm.Common.Repository::Delete

- ea: `0xf00`
- end: `0xf25`
- name: `Microsoft.Crm.Common.Repository::Delete`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0xf00`
- `0x1e50`

## pseudocode

```c

```

## disassembly

```asm
0xf00  ldarg.1
0xf01  box      mvar<u1>
0xf06  brtrue.s loc_F13
0xf08  ldstr    aObj// "obj"
0xf0d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf12  throw
0xf13  ldarg.0
0xf14  call     T0x2B000004
0xf19  callvirt instance class Microsoft.Crm.Common.IDataProvider TypeInformation::get_DataProvider()
0xf1e  ldarg.1
0xf1f  callvirt T0x2B000008
0xf24  ret
```
