# NlSetIncomingPassword(_DOMAIN_INFO *,ushort *,_NETLOGON_SECURE_CHANNEL_TYPE,_UNICODE_STRING *,ulong,_LM_OWF_PASSWORD *)

- ea: `0x180038510`
- end: `0x180038ac7`
- name: `?NlSetIncomingPassword@@YAJPEAU_DOMAIN_INFO@@PEAGW4_NETLOGON_SECURE_CHANNEL_TYPE@@PEAU_UNICODE_STRING@@KPEAU_LM_OWF_PASSWORD@@@Z`
- size: `1463`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180056644`

## callees

- `0x180007278`
- `0x18000bd98`
- `0x18000e270`
- `0x18000ed34`
- `0x180036b78`
- `0x180038510`
- `0x18003f054`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003861c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003861c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003869f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003869f`
- `LSASRV!LsarQueryTrustedDomainInfoByName` at `0x180038647`
- `LSASRV!LsarQueryTrustedDomainInfoByName` at `0x180038647`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180038a9c`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180038a9c`
- `LSASRV!LsarSetTrustedDomainInfoByName` at `0x180038a09`
- `LSASRV!LsarSetTrustedDomainInfoByName` at `0x180038a09`
- `ntdll!RtlInitUnicodeString` at `0x1800385d0`
- `ntdll!RtlInitUnicodeString` at `0x1800385d0`

## string_xrefs

- `0x180038a75`: `NlSetIncomingPassword: Cannot change password on local user account %lX\n`
- `0x180038653`: `NlSetIncomingPassword: %wZ: cannot LsarQueryTrustedDomainInfoByName 0x%lx\n`
- `0x180038a15`: `NlSetIncomingPassword: %wZ: cannot LsarSetTrustedDomainInfoByName 0x%lx\n`
- `0x1800385ac`: `NlSetIncomingPassword: %ws: invalid secure channel type: %ld\n`

## pseudocode

```c

```
