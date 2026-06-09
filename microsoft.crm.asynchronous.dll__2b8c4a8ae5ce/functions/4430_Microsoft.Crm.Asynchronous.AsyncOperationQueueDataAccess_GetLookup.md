# Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::GetLookup

- ea: `0x4430`
- end: `0x4459`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::GetLookup`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x16b90`

## callees

- `0x4430`
- `0x4490`

## pseudocode

```c

```

## disassembly

```asm
0x4430  ldnull
0x4431  stloc.0
0x4432  ldarg.1
0x4433  brfalse.s loc_4457
0x4435  ldarg.1
0x4436  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x443b  beq.s    loc_4457
0x443d  ldarg.0
0x443e  ldarg.3
0x443f  call     instance string Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::GetEntityLogicalNameFromObjectTypeCode(int32 objectTypeCode)
0x4444  ldarg.1
0x4445  unbox.any [mscorlib]System.Guid
0x444a  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup::.ctor(string, valuetype [mscorlib]System.Guid)
0x444f  stloc.0
0x4450  ldloc.0
0x4451  ldarg.2
0x4452  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::set_name(string)
0x4457  ldloc.0
0x4458  ret
```
