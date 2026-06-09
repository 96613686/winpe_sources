# Microsoft.Crm.Asynchronous.EntityKeyIndexCreateOperation::DeleteIndex

- ea: `0x28a0`
- end: `0x28bf`
- name: `Microsoft.Crm.Asynchronous.EntityKeyIndexCreateOperation::DeleteIndex`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2780`

## callees

- `0x28a0`

## pseudocode

```c

```

## disassembly

```asm
0x28a0  ldarg.1
0x28a1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x28a6  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x28ab  brfalse.s loc_28BE
0x28ad  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexAndConstraintManagementService [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexAndConstraintManagementService::get_Instance()
0x28b2  ldarg.1
0x28b3  ldarg.2
0x28b4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x28b9  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IndexAndConstraintManagementService::DropIndexAndDeleteIndexManagementData(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x28be  ret
```
