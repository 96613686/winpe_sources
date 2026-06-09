# Microsoft.Crm.Common.Application.Platform.ServiceCommands.RetrieveEmailSignaturesCommand::GetOwnerId

- ea: `0x68e0`
- end: `0x6915`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.RetrieveEmailSignaturesCommand::GetOwnerId`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x67f0`

## pseudocode

```c

```

## disassembly

```asm
0x68e0  ldsfld   string [mscorlib]System.String::Empty
0x68e5  pop
0x68e6  ldarg.1
0x68e7  ldarg.2
0x68e8  ldc.i4.1
0x68e9  newarr   [mscorlib]System.String
0x68ee  dup
0x68ef  ldc.i4.0
0x68f0  ldstr    aOwnerid// "ownerid"
0x68f5  stelem.ref
0x68f6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x68fb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6900  ldstr    aOwnerid// "ownerid"
0x6905  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x690a  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x690f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x6914  ret
```
