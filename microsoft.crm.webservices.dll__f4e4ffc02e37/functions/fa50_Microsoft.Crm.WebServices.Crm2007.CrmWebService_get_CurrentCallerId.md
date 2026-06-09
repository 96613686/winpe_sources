# Microsoft.Crm.WebServices.Crm2007.CrmWebService::get_CurrentCallerId

- ea: `0xfa50`
- end: `0xfa7e`
- name: `Microsoft.Crm.WebServices.Crm2007.CrmWebService::get_CurrentCallerId`
- size: `46`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xaa70`
- `0xaab0`
- `0xaaf0`
- `0xab30`
- `0xab80`
- `0xabd0`
- `0xac10`
- `0xacf0`

## callees

- `0xfa10`
- `0xfa50`

## pseudocode

```c

```

## disassembly

```asm
0xfa50  ldarg.0
0xfa51  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmAuthenticationToken Microsoft.Crm.WebServices.Crm2007.CrmWebService::get_AuthenticationToken()
0xfa56  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmAuthenticationToken::get_CallerId()
0xfa5b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xfa60  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xfa65  brfalse.s loc_FA73
0xfa67  ldarg.0
0xfa68  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmAuthenticationToken Microsoft.Crm.WebServices.Crm2007.CrmWebService::get_AuthenticationToken()
0xfa6d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmAuthenticationToken::get_CallerId()
0xfa72  ret
0xfa73  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetCallerAndBusinessGuids()
0xfa78  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_UserId()
0xfa7d  ret
```
