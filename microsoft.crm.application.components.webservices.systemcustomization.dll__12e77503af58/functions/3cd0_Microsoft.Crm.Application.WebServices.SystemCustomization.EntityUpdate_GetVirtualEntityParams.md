# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetVirtualEntityParams

- ea: `0x3cd0`
- end: `0x3d17`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetVirtualEntityParams`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3450`

## callees

- `0x190`
- `0x330`
- `0x3cd0`

## pseudocode

```c

```

## disassembly

```asm
0x3cd0  ldarg.1
0x3cd1  ldstr    aDataproviderid// "dataproviderid"
0x3cd6  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3cdb  brfalse.s loc_3CF3
0x3cdd  ldarg.0
0x3cde  ldarg.1
0x3cdf  ldstr    aDataproviderid// "dataproviderid"
0x3ce4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid(string name)
0x3ce9  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x3cee  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_DataProviderId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x3cf3  ldarg.1
0x3cf4  ldstr    aDatasourceid// "datasourceid"
0x3cf9  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3cfe  brfalse.s loc_3D16
0x3d00  ldarg.0
0x3d01  ldarg.1
0x3d02  ldstr    aDatasourceid// "datasourceid"
0x3d07  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid(string name)
0x3d0c  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x3d11  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_DataSourceId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x3d16  ret
```
