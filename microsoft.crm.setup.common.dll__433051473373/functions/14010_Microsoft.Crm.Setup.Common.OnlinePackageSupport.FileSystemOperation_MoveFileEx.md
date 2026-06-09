# Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::MoveFileEx

- ea: `0x14010`
- end: `0x1403d`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::MoveFileEx`
- size: `45`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x13970`
- `0x144d0`
- `0x14510`

## callees

- `0x14010`
- `0x17ca0`

## pseudocode

```c

```

## disassembly

```asm
0x14010  ldarg.0
0x14011  ldstr    aExistingfilena// "existingFileName"
0x14016  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1401b  ldarg.2
0x1401c  ldc.i4.4
0x1401d  and
0x1401e  ldc.i4.4
0x1401f  beq.s    loc_1402C
0x14021  ldarg.1
0x14022  ldstr    aNewfilename// "newFileName"
0x14027  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1402c  ldarg.0
0x1402d  ldarg.1
0x1402e  ldarg.2
0x1402f  call     bool NativeMethods::MoveFileEx([hasfieldmarshal] string, string existingFileName, unsigned int32 newFileName)
0x14034  brtrue.s loc_1403C
0x14036  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor()
0x1403b  throw
0x1403c  ret
```
