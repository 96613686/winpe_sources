# Microsoft.Crm.Sdk.CrmServiceInternal::ConvertToSdkEntity

- ea: `0xc40`
- end: `0xc5a`
- name: `Microsoft.Crm.Sdk.CrmServiceInternal::ConvertToSdkEntity`
- size: `26`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x680`
- `0x760`

## pseudocode

```c

```

## disassembly

```asm
0xc40  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ConversionContextFactory [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ConversionContextFactory::get_Instance()
0xc45  ldarg.2
0xc46  ldc.i4.0
0xc47  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ConversionContextFactory::CreateInstance(valuetype [mscorlib]System.Guid, int32)
0xc4c  stloc.0
0xc4d  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.DynamicEntityToEntityConverter::.ctor()
0xc52  ldloc.0
0xc53  ldarg.1
0xc54  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.DynamicEntityToEntityConverter::Convert(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity)
0xc59  ret
```
