# Microsoft.Crm.Service.Application.Components.EntityPageHeaders.QueueConfigHeader::AddDefaultMailboxVariable

- ea: `0xc5a0`
- end: `0xc5d6`
- name: `Microsoft.Crm.Service.Application.Components.EntityPageHeaders.QueueConfigHeader::AddDefaultMailboxVariable`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xc580`

## callees

- `0xc5a0`

## pseudocode

```c

```

## disassembly

```asm
0xc5a0  ldstr    asc_15D82// ""
0xc5a5  stloc.0
0xc5a6  ldarg.2
0xc5a7  ldstr    aDefaultmailbox// "defaultmailbox"
0xc5ac  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xc5b1  brfalse.s loc_C5C9
0xc5b3  ldarg.2
0xc5b4  ldstr    aDefaultmailbox// "defaultmailbox"
0xc5b9  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xc5be  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0xc5c3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0xc5c8  stloc.0
0xc5c9  ldarg.1
0xc5ca  ldstr    aDefaultmailbox_0// "DefaultMailboxId"
0xc5cf  ldloc.0
0xc5d0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xc5d5  ret
```
