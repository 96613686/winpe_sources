# getEapTlsUserPropertiesPlap(ulong,_EAP_CONFIG_INPUT_FIELD_ARRAY const *,_EAPTLS_CONN_PROPERTIES *,_EAPTLS_USER_PROPERTIES * *)

- ea: `0x18005bc70`
- end: `0x18005c05b`
- name: `?getEapTlsUserPropertiesPlap@@YAKKPEBU_EAP_CONFIG_INPUT_FIELD_ARRAY@@PEAU_EAPTLS_CONN_PROPERTIES@@PEAPEAU_EAPTLS_USER_PROPERTIES@@@Z`
- size: `1003`
- prototype: `unsigned int __fastcall(unsigned int, const struct _EAP_CONFIG_INPUT_FIELD_ARRAY *, struct _EAPTLS_CONN_PROPERTIES *, struct _EAPTLS_USER_PROPERTIES **)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005363c`
- `0x18005388c`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180038e4c`
- `0x180039540`
- `0x18005acb0`
- `0x18005bc70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bda1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bdef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005be42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005beec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bda1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bdef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005be42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005beec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005bddb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005bead`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005bddb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005bead`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bfe9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bff8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bfe9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bff8`
- `api-ms-win-security-credentials-l1-1-0!CredProtectW` at `0x18005bd8a`
- `api-ms-win-security-credentials-l1-1-0!CredProtectW` at `0x18005be32`
- `api-ms-win-security-credentials-l1-1-0!CredProtectW` at `0x18005bd8a`
- `api-ms-win-security-credentials-l1-1-0!CredProtectW` at `0x18005be32`
- `ext-ms-win-rastlsext-eap-l1-1-0!RasTlsExt_FreeMemory` at `0x18005c011`
- `ext-ms-win-rastlsext-eap-l1-1-0!RasTlsExt_FreeMemory` at `0x18005c011`
- `ext-ms-win-rastlsext-eap-l1-1-0!RasTlsExt_PackUserBlob` at `0x18005be89`
- `ext-ms-win-rastlsext-eap-l1-1-0!RasTlsExt_PackUserBlob` at `0x18005be89`

## pseudocode

```c

```
