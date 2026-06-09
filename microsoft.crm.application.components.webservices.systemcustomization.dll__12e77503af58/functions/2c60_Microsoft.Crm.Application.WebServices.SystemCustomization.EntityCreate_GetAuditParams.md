# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetAuditParams

- ea: `0x2c60`
- end: `0x2cad`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetAuditParams`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x26f0`

## callees

- `0x2b0`
- `0x2c60`

## pseudocode

```c

```

## disassembly

```asm
0x2c60  ldarg.0
0x2c61  ldarg.1
0x2c62  ldstr    aAuditenabled// "auditenabled"
0x2c67  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x2c6c  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_IsAuditEnabled(bool)
0x2c71  ldarg.0
0x2c72  ldarg.1
0x2c73  ldstr    aRetrieveaudite// "retrieveauditenabled"
0x2c78  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x2c7d  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_IsRetrieveAuditEnabled(bool)
0x2c82  leave.s  loc_2C8E
0x2c84  pop
0x2c85  ldarg.0
0x2c86  ldc.i4.0
0x2c87  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_IsRetrieveAuditEnabled(bool)
0x2c8c  leave.s  loc_2C8E
0x2c8e  nop
0x2c8f  ldarg.0
0x2c90  ldarg.1
0x2c91  ldstr    aRetrievemultip// "retrievemultipleauditenabled"
0x2c96  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x2c9b  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_IsRetrieveMultipleAuditEnabled(bool)
0x2ca0  leave.s  loc_2CAC
0x2ca2  pop
0x2ca3  ldarg.0
0x2ca4  ldc.i4.0
0x2ca5  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_IsRetrieveMultipleAuditEnabled(bool)
0x2caa  leave.s  loc_2CAC
0x2cac  ret
```
