# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetPartyListInfo

- ea: `0x18e0`
- end: `0x18f2`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetPartyListInfo`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x430`

## callees

- `0x18b0`

## pseudocode

```c

```

## disassembly

```asm
0x18e0  ldarg.0
0x18e1  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetLookupInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMD)
0x18e6  dup
0x18e7  ldstr    aPartylist// "partylist"
0x18ec  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::set_TypeName(string)
0x18f1  ret
```
