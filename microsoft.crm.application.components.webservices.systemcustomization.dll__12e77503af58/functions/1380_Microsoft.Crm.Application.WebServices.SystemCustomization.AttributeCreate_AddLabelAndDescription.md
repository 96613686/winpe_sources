# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::AddLabelAndDescription

- ea: `0x1380`
- end: `0x13d5`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::AddLabelAndDescription`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1000`

## callees

- `0x1380`

## pseudocode

```c

```

## disassembly

```asm
0x1380  ldarg.2
0x1381  brfalse.s loc_13AA
0x1383  ldarg.0
0x1384  ldarg.s  4
0x1386  ldarg.2
0x1387  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x138c  ldarg.2
0x138d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_ObjectId()
0x1392  ldarg.2
0x1393  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_ObjectColumnName()
0x1398  ldarg.2
0x1399  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_TypeCode()
0x139e  ldarg.s  5
0x13a0  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, valuetype [mscorlib]System.Guid, string, int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x13a5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x13aa  ldarg.3
0x13ab  brfalse.s loc_13D4
0x13ad  ldarg.1
0x13ae  ldarg.s  4
0x13b0  ldarg.3
0x13b1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x13b6  ldarg.3
0x13b7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_ObjectId()
0x13bc  ldarg.3
0x13bd  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_ObjectColumnName()
0x13c2  ldarg.3
0x13c3  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_TypeCode()
0x13c8  ldarg.s  5
0x13ca  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, valuetype [mscorlib]System.Guid, string, int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x13cf  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x13d4  ret
```
