# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetReadingPaneParams

- ea: `0x2fc0`
- end: `0x2fd2`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetReadingPaneParams`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x26f0`

## callees

- `0x2b0`

## string_xrefs

- `0x2fc2`: `readingpaneenabled`

## pseudocode

```c

```

## disassembly

```asm
0x2fc0  ldarg.0
0x2fc1  ldarg.1
0x2fc2  ldstr    aReadingpaneena// "readingpaneenabled"
0x2fc7  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x2fcc  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_IsReadingPaneEnabled(bool)
0x2fd1  ret
```
