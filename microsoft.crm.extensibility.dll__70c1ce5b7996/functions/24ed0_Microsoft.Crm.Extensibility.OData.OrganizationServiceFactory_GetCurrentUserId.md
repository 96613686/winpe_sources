# Microsoft.Crm.Extensibility.OData.OrganizationServiceFactory::GetCurrentUserId

- ea: `0x24ed0`
- end: `0x24edb`
- name: `Microsoft.Crm.Extensibility.OData.OrganizationServiceFactory::GetCurrentUserId`
- size: `11`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xe670`
- `0xe780`
- `0xe890`
- `0x1d750`
- `0x21690`
- `0x2e290`
- `0x2fac0`
- `0x2feb0`
- `0x30050`
- `0x30870`
- `0x30ed0`
- `0x31020`
- `0x31100`
- `0x311c0`

## callees

- `0x24f70`

## pseudocode

```c

```

## disassembly

```asm
0x24ed0  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth Microsoft.Crm.Extensibility.OData.OrganizationServiceFactory::GetCurrentUserAuth()
0x24ed5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_UserId()
0x24eda  ret
```
