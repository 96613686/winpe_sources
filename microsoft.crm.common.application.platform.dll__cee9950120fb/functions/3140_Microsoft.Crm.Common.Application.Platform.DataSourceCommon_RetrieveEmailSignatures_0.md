# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::RetrieveEmailSignatures_0

- ea: `0x3140`
- end: `0x3154`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::RetrieveEmailSignatures_0`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x67f0`

## pseudocode

```c

```

## disassembly

```asm
0x3140  ldarg.0
0x3141  ldarg.1
0x3142  ldarg.2
0x3143  ldarg.3
0x3144  newobj   instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.RetrieveEmailSignaturesCommand::.ctor(int32 languageCode, valuetype [mscorlib]System.Guid ownerId, string entityName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3149  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.RetrieveMultipleCommand::Execute()
0x314e  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection::Serialize(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection)
0x3153  ret
```
