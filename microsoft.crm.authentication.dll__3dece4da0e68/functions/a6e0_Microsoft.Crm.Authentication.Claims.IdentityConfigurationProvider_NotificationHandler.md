# Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::NotificationHandler

- ea: `0xa6e0`
- end: `0xa732`
- name: `Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::NotificationHandler`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x8170`
- `0xa310`
- `0xa6e0`
- `0xa8d0`

## pseudocode

```c

```

## disassembly

```asm
0xa6e0  ldc.i4.s 0x35
0xa6e2  ldarg.0
0xa6e3  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs::get_EventId()
0xa6e8  beq.s    loc_A6FE
0xa6ea  ldc.i4.s 0x36
0xa6ec  ldarg.0
0xa6ed  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs::get_EventId()
0xa6f2  beq.s    loc_A6FE
0xa6f4  ldc.i4.s 0x37
0xa6f6  ldarg.0
0xa6f7  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs::get_EventId()
0xa6fc  bne.un.s loc_A709
0xa6fe  call     void Microsoft.Crm.Authentication.Claims.TokenAudienceProvider::ResetConfiguration()
0xa703  call     void Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::ResetConfiguration()
0xa708  ret
0xa709  ldc.i4.s 0x38
0xa70b  ldarg.0
0xa70c  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs::get_EventId()
0xa711  beq.s    loc_A727
0xa713  ldc.i4.s 0x39
0xa715  ldarg.0
0xa716  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs::get_EventId()
0xa71b  beq.s    loc_A727
0xa71d  ldc.i4.s 0x3A
0xa71f  ldarg.0
0xa720  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs::get_EventId()
0xa725  bne.un.s loc_A731
0xa727  call     void Microsoft.Crm.Authentication.Providers.CertificateProvider::Reset()
0xa72c  call     void Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::ResetConfiguration()
0xa731  ret
```
