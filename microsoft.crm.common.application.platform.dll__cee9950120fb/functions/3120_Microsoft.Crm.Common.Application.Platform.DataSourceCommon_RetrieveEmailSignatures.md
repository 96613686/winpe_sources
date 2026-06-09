# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::RetrieveEmailSignatures

- ea: `0x3120`
- end: `0x3133`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::RetrieveEmailSignatures`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x67e0`

## pseudocode

```c

```

## disassembly

```asm
0x3120  ldarg.0
0x3121  ldarg.1
0x3122  ldarg.2
0x3123  newobj   instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.RetrieveEmailSignaturesCommand::.ctor(valuetype [mscorlib]System.Guid ownerId, string entityName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3128  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.RetrieveMultipleCommand::Execute()
0x312d  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection::Serialize(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection)
0x3132  ret
```
