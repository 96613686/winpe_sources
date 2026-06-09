# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetAuditParams

- ea: `0x3c10`
- end: `0x3c81`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetAuditParams`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3450`

## callees

- `0x190`
- `0x2b0`
- `0x3c10`

## pseudocode

```c

```

## disassembly

```asm
0x3c10  ldarg.1
0x3c11  ldstr    aAuditenabled// "auditenabled"
0x3c16  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3c1b  brfalse.s loc_3C44
0x3c1d  ldarg.0
0x3c1e  ldarg.1
0x3c1f  ldstr    aAuditenabled// "auditenabled"
0x3c24  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x3c29  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsAuditEnabled(bool)
0x3c2e  ldarg.0
0x3c2f  callvirt instance bool [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsAuditEnabled()
0x3c34  brtrue.s loc_3C44
0x3c36  ldarg.0
0x3c37  ldc.i4.0
0x3c38  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsRetrieveMultipleAuditEnabled(bool)
0x3c3d  ldarg.0
0x3c3e  ldc.i4.0
0x3c3f  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsRetrieveAuditEnabled(bool)
0x3c44  ldarg.1
0x3c45  ldstr    aRetrieveaudite// "retrieveauditenabled"
0x3c4a  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3c4f  brfalse.s loc_3C62
0x3c51  ldarg.0
0x3c52  ldarg.1
0x3c53  ldstr    aRetrieveaudite// "retrieveauditenabled"
0x3c58  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x3c5d  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsRetrieveAuditEnabled(bool)
0x3c62  ldarg.1
0x3c63  ldstr    aRetrievemultip// "retrievemultipleauditenabled"
0x3c68  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3c6d  brfalse.s loc_3C80
0x3c6f  ldarg.0
0x3c70  ldarg.1
0x3c71  ldstr    aRetrievemultip// "retrievemultipleauditenabled"
0x3c76  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x3c7b  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsRetrieveMultipleAuditEnabled(bool)
0x3c80  ret
```
