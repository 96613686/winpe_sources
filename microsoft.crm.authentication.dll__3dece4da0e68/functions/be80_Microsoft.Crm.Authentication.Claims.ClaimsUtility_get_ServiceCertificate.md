# Microsoft.Crm.Authentication.Claims.ClaimsUtility::get_ServiceCertificate

- ea: `0xbe80`
- end: `0xbe8b`
- name: `Microsoft.Crm.Authentication.Claims.ClaimsUtility::get_ServiceCertificate`
- size: `11`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x9c40`
- `0xa2e0`
- `0xb070`

## pseudocode

```c

```

## disassembly

```asm
0xbe80  call     class [Microsoft.Crm.Core]Microsoft.Crm.IAuthManagementInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.AuthManagementInfoProvider::get_Instance()
0xbe85  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.IAuthManagementInfoProvider::GetServiceCertificate()
0xbe8a  ret
```
