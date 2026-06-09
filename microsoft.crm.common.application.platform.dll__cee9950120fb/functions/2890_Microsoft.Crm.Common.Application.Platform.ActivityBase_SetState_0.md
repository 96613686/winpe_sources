# Microsoft.Crm.Common.Application.Platform.ActivityBase::SetState_0

- ea: `0x2890`
- end: `0x28b2`
- name: `Microsoft.Crm.Common.Application.Platform.ActivityBase::SetState_0`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2880`

## callees

- `0x2890`

## pseudocode

```c

```

## disassembly

```asm
0x2890  ldarg.2
0x2891  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2896  brfalse.s loc_28A1
0x2898  ldarg.0
0x2899  ldarg.3
0x289a  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::GetStateCodeFromStatusCode(string, int32)
0x289f  starg.s  2
0x28a1  ldarg.0
0x28a2  ldarg.1
0x28a3  ldarg.2
0x28a4  ldarg.3
0x28a5  ldarg.s  4
0x28a7  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.SetStateCommand::.ctor(string, valuetype [mscorlib]System.Guid, string, int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x28ac  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.SetStateCommand::Execute()
0x28b1  ret
```
