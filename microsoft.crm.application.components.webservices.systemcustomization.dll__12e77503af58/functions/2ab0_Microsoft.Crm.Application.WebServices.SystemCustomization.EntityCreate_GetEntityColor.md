# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetEntityColor

- ea: `0x2ab0`
- end: `0x2acc`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetEntityColor`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x26f0`

## callees

- `0x200`

## pseudocode

```c

```

## disassembly

```asm
0x2ab0  ldarg.0
0x2ab1  ldarg.1
0x2ab2  ldstr    aEntitycolor// "entitycolor"
0x2ab7  ldsfld   string [mscorlib]System.String::Empty
0x2abc  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x2ac1  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::ValidateAndAppendHashToColorValue(string)
0x2ac6  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_EntityColor(string)
0x2acb  ret
```
