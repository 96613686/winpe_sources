# Microsoft.Crm.Common.Application.Platform.ActivityBase::FixStateCode

- ea: `0x26f0`
- end: `0x270f`
- name: `Microsoft.Crm.Common.Application.Platform.ActivityBase::FixStateCode`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4470`

## callees

- `0x2710`

## pseudocode

```c

```

## disassembly

```asm
0x26f0  ldarg.0
0x26f1  ldarg.2
0x26f2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x26f7  isinst   Microsoft.Crm.Common.Application.Platform.ActivityBase
0x26fc  dup
0x26fd  ldarg.1
0x26fe  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::set_Data(string)
0x2703  dup
0x2704  callvirt instance void Microsoft.Crm.Common.Application.Platform.ActivityBase::FixStateCode()
0x2709  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_Data()
0x270e  ret
```
