# KerbReportActionToString(_NETLOGON_VALIDATION_TICKET_LOGON * const)

- ea: `0x180092710`
- end: `0x18009296d`
- name: `?KerbReportActionToString@@YAPEAGQEAU_NETLOGON_VALIDATION_TICKET_LOGON@@@Z`
- size: `605`
- prototype: `unsigned __int16 *__fastcall(struct _NETLOGON_VALIDATION_TICKET_LOGON *const)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800bd7d0`

## callees

- `0x1800093f0`
- `0x180070680`
- `0x180092710`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18009291d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180092933`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180092949`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18009291d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180092933`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180092949`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180092906`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180092906`

## string_xrefs

- `0x180092743`: `User SIDs were filtered\n`
- `0x18009278c`: `Device SIDs were filtered\n`
- `0x1800927c9`: `Compound identity was removed due to SID filtering disallowing the device's identity\n`
- `0x180092857`: `Compound identity was removed due to SID filtering disallowing the device's domain name\n`

## pseudocode

```c

```
