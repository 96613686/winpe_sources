# Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::GetEntityNameReference

- ea: `0x4460`
- end: `0x4481`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::GetEntityNameReference`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x16b90`

## callees

- `0x4460`
- `0x4490`

## pseudocode

```c

```

## disassembly

```asm
0x4460  ldnull
0x4461  stloc.0
0x4462  ldarg.1
0x4463  brfalse.s loc_447F
0x4465  ldarg.1
0x4466  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x446b  beq.s    loc_447F
0x446d  ldarg.0
0x446e  ldarg.1
0x446f  unbox.any [mscorlib]System.Int32
0x4474  call     instance string Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::GetEntityLogicalNameFromObjectTypeCode(int32 objectTypeCode)
0x4479  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference::.ctor(string)
0x447e  stloc.0
0x447f  ldloc.0
0x4480  ret
```
