# Microsoft.Crm.Sdk.ServiceDescription::ExtractEntities

- ea: `0x8ba0`
- end: `0x8be3`
- name: `Microsoft.Crm.Sdk.ServiceDescription::ExtractEntities`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x8e90`

## callees

- `0x86c0`
- `0x8ba0`

## pseudocode

```c

```

## disassembly

```asm
0x8ba0  ldc.i4.2
0x8ba1  newarr   [mscorlib]System.String
0x8ba6  stloc.0
0x8ba7  ldarg.1
0x8ba8  callvirt instance int32 [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType::get_PrimaryObjectTypeCode()
0x8bad  ldc.i4.0
0x8bae  ble.s    loc_8BC4
0x8bb0  ldloc.0
0x8bb1  ldc.i4.0
0x8bb2  ldarg.0
0x8bb3  ldarg.1
0x8bb4  callvirt instance int32 [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType::get_PrimaryObjectTypeCode()
0x8bb9  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Sdk.ServiceDescription::GetEntityByObjectTypeCode(int32 objectTypeCode)
0x8bbe  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x8bc3  stelem.ref
0x8bc4  ldarg.1
0x8bc5  callvirt instance int32 [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType::get_SecondaryObjectTypeCode()
0x8bca  ldc.i4.0
0x8bcb  ble.s    loc_8BE1
0x8bcd  ldloc.0
0x8bce  ldc.i4.1
0x8bcf  ldarg.0
0x8bd0  ldarg.1
0x8bd1  callvirt instance int32 [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType::get_SecondaryObjectTypeCode()
0x8bd6  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Sdk.ServiceDescription::GetEntityByObjectTypeCode(int32 objectTypeCode)
0x8bdb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x8be0  stelem.ref
0x8be1  ldloc.0
0x8be2  ret
```
