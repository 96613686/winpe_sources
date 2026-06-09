# EdpCredSvcInitialize(long (*)(ushort const *,ushort const *),long (*)(ushort const *,int *,ushort * *,int *),ulong (*)(ulong *,uchar * *),long (*)(void *,int *))

- ea: `0x1800837d0`
- end: `0x180083b20`
- name: `?EdpCredSvcInitialize@@YAJP6AJPEBG0@ZP6AJ0PEAHPEAPEAG2@ZP6AKPEAKPEAPEAE@ZP6AJPEAX2@Z@Z`
- size: `848`
- prototype: `__int64 __fastcall(int (*)(const unsigned __int16 *, const unsigned __int16 *), int (*)(const unsigned __int16 *, int *, unsigned __int16 **, int *), unsigned int (*)(unsigned int *, unsigned __int8 **), int (*)(void *, int *))`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180028d3c`

## callees

- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800837d0`
- `0x180083b28`
- `0x180083fb8`
- `0x1800940f4`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180083903`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180083903`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180083879`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180083960`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180083879`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180083960`
- `ntdll!RtlIsMultiSessionSku` at `0x180083993`
- `ntdll!RtlIsMultiSessionSku` at `0x180083ac2`
- `ntdll!RtlIsMultiSessionSku` at `0x180083993`
- `ntdll!RtlIsMultiSessionSku` at `0x180083ac2`
- `ext-ms-win-security-efs-l1-1-0!EdpPlatform_RegisterUserSessionNotification` at `0x180083a08`
- `ext-ms-win-security-efs-l1-1-0!EdpPlatform_RegisterUserSessionNotification` at `0x180083a08`

## string_xrefs

- `0x180083869`: `SYSTEM\CurrentControlSet\Services\EFS\Parameters`
- `0x180083949`: `SYSTEM\CurrentControlSet\Services\EFS\Parameters`

## pseudocode

```c

```
