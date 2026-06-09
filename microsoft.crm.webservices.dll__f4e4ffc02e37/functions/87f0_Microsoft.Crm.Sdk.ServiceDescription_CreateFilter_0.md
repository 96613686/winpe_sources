# Microsoft.Crm.Sdk.ServiceDescription::CreateFilter_0

- ea: `0x87f0`
- end: `0x880e`
- name: `Microsoft.Crm.Sdk.ServiceDescription::CreateFilter_0`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8770`

## callees

- `0x87c0`

## pseudocode

```c

```

## disassembly

```asm
0x87f0  ldarg.0
0x87f1  callvirt instance int32 [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType::get_PrimaryObjectTypeCode()
0x87f6  ldarg.0
0x87f7  callvirt instance int32 [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType::get_SecondaryObjectTypeCode()
0x87fc  ldarg.0
0x87fd  callvirt instance int32 [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType::get_Availability()
0x8802  ldarg.0
0x8803  callvirt instance bool [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType::get_IsVisible()
0x8808  call     class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType Microsoft.Crm.Sdk.ServiceDescription::CreateFilter(int32 primaryObjectTypeCode, int32 secondaryObjectTypeCode, int32 availability, bool isVisible)
0x880d  ret
```
