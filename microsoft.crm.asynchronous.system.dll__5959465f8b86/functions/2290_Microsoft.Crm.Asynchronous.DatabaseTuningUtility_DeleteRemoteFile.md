# Microsoft.Crm.Asynchronous.DatabaseTuningUtility::DeleteRemoteFile

- ea: `0x2290`
- end: `0x22b5`
- name: `Microsoft.Crm.Asynchronous.DatabaseTuningUtility::DeleteRemoteFile`
- size: `37`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1e50`
- `0x5de0`

## callees

- `0x2290`
- `0x22c0`

## string_xrefs

- `0x2299`: `Failed to delete remote trace '`

## pseudocode

```c

```

## disassembly

```asm
0x2290  ldarg.0
0x2291  ldarg.1
0x2292  call     bool Microsoft.Crm.Asynchronous.DatabaseTuningUtility::TryDeleteRemoteFile(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection connection, string fileName)
0x2297  brtrue.s loc_22B4
0x2299  ldstr    aFailedToDelete// "Failed to delete remote trace '"
0x229e  ldarg.1
0x229f  ldstr    asc_13E24// "'"
0x22a4  call     string [mscorlib]System.String::Concat(string, string, string)
0x22a9  ldc.i4   0x80040216
0x22ae  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x22b3  throw
0x22b4  ret
```
