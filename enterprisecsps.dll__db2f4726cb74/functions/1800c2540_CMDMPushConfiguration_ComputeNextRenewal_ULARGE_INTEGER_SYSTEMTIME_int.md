# CMDMPushConfiguration::ComputeNextRenewal(_ULARGE_INTEGER,_SYSTEMTIME *,int *)

- ea: `0x1800c2540`
- end: `0x1800c2788`
- name: `?ComputeNextRenewal@CMDMPushConfiguration@@AEAAJT_ULARGE_INTEGER@@PEAU_SYSTEMTIME@@PEAH@Z`
- size: `584`
- prototype: `int(CMDMPushConfiguration *__hidden this, union _ULARGE_INTEGER, struct _SYSTEMTIME *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c4590`

## callees

- `0x180008de0`
- `0x18000d4b4`
- `0x18000d4d4`
- `0x1800c2540`
- `0x1800c85c4`
- `0x1800cd54c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800c2571`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800c2571`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800c258d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800c258d`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800c274f`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800c274f`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1800c272e`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1800c272e`

## pseudocode

```c

```
