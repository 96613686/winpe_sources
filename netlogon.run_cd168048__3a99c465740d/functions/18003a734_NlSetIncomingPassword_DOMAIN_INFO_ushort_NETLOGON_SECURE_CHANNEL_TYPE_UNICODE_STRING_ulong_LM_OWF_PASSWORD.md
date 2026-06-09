# NlSetIncomingPassword(_DOMAIN_INFO *,ushort *,_NETLOGON_SECURE_CHANNEL_TYPE,_UNICODE_STRING *,ulong,_LM_OWF_PASSWORD *)

- ea: `0x18003a734`
- end: `0x18003ad10`
- name: `?NlSetIncomingPassword@@YAJPEAU_DOMAIN_INFO@@PEAGW4_NETLOGON_SECURE_CHANNEL_TYPE@@PEAU_UNICODE_STRING@@KPEAU_LM_OWF_PASSWORD@@@Z`
- size: `1500`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005a400`

## callees

- `0x180007518`
- `0x18000c440`
- `0x18000e910`
- `0x18000f3e4`
- `0x180038cb8`
- `0x18003a734`
- `0x180041944`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003a846`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003a846`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003a8d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003a8d5`
- `LSASRV!LsarQueryTrustedDomainInfoByName` at `0x18003a877`
- `LSASRV!LsarQueryTrustedDomainInfoByName` at `0x18003a877`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x18003acde`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x18003acde`
- `LSASRV!LsarSetTrustedDomainInfoByName` at `0x18003ac45`
- `LSASRV!LsarSetTrustedDomainInfoByName` at `0x18003ac45`
- `ntdll!RtlInitUnicodeString` at `0x18003a7f4`
- `ntdll!RtlInitUnicodeString` at `0x18003a7f4`

## string_xrefs

- `0x18003acb7`: `NlSetIncomingPassword: Cannot change password on local user account %lX\n`
- `0x18003a889`: `NlSetIncomingPassword: %wZ: cannot LsarQueryTrustedDomainInfoByName 0x%lx\n`
- `0x18003ac57`: `NlSetIncomingPassword: %wZ: cannot LsarSetTrustedDomainInfoByName 0x%lx\n`
- `0x18003a7d0`: `NlSetIncomingPassword: %ws: invalid secure channel type: %ld\n`

## pseudocode

```c

```
