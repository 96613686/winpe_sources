# LsapLogonSessionDelete(_SecHandle *,void *,ulong)

- ea: `0x18000ce90`
- end: `0x18000d39b`
- name: `?LsapLogonSessionDelete@@YAXPEAU_SecHandle@@PEAXK@Z`
- size: `1291`
- prototype: `void(struct _SecHandle *, void *, unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000c300`
- `0x18000ce90`
- `0x180011278`
- `0x180016f70`
- `0x1800284d4`
- `0x18004091c`
- `0x180058750`
- `0x18005e770`
- `0x18005faf0`
- `0x180081e94`
- `0x180089860`
- `0x18008dcd8`
- `0x1800bc040`
- `0x1800bc2c4`
- `0x18014d010`

## import_xrefs

- `LSAADT!__imp_LsapAuditFailed` at `0x18000d33c`
- `LSAADT!__imp_LsapAuditFailed` at `0x18000d33c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18000d284`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18000d284`
- `ntdll!RtlFreeHeap` at `0x18000cfb5`
- `ntdll!RtlFreeHeap` at `0x18000cfb5`
- `ntdll!RtlDeleteResource` at `0x18000d14e`
- `ntdll!RtlDeleteResource` at `0x18000d14e`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000cf1f`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000cf7d`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000cf1f`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000cf7d`
- `ntdll!RtlReleaseResource` at `0x18000cf58`
- `ntdll!RtlReleaseResource` at `0x18000cfe5`
- `ntdll!RtlReleaseResource` at `0x18000cf58`
- `ntdll!RtlReleaseResource` at `0x18000cfe5`
- `ntdll!NtClose` at `0x18000d102`
- `ntdll!NtClose` at `0x18000d11a`
- `ntdll!NtClose` at `0x18000d102`
- `ntdll!NtClose` at `0x18000d11a`
- `ntdll!RtlDeleteCriticalSection` at `0x18000d161`
- `ntdll!RtlDeleteCriticalSection` at `0x18000d161`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x18000d237`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x18000d237`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtAuditLogoff` at `0x18000d266`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtAuditLogoff` at `0x18000d266`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtLogoffPerUserAuditing` at `0x18000d1da`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtLogoffPerUserAuditing` at `0x18000d1da`

## pseudocode

```c

```
