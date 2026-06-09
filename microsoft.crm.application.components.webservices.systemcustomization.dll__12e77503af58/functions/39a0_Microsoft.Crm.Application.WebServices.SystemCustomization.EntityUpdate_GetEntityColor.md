# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetEntityColor

- ea: `0x39a0`
- end: `0x39bc`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetEntityColor`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3450`

## callees

- `0x200`

## pseudocode

```c

```

## disassembly

```asm
0x39a0  ldarg.0
0x39a1  ldarg.1
0x39a2  ldstr    aEntitycolor// "entitycolor"
0x39a7  ldsfld   string [mscorlib]System.String::Empty
0x39ac  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x39b1  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::ValidateAndAppendHashToColorValue(string)
0x39b6  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_EntityColor(string)
0x39bb  ret
```
