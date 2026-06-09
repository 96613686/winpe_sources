# KerbAddAuthzDataForTGS(_KERB_CREDENTIAL *,_KERB_CREDMAN_CRED *,PKERB_AUTHORIZATION_DATA_s * *)

- ea: `0x18003d3f0`
- end: `0x18003d7c3`
- name: `?KerbAddAuthzDataForTGS@@YAJPEAU_KERB_CREDENTIAL@@PEAU_KERB_CREDMAN_CRED@@PEAPEAUPKERB_AUTHORIZATION_DATA_s@@@Z`
- size: `979`
- prototype: `__int64 __fastcall(struct _KERB_CREDENTIAL *, struct _KERB_CREDMAN_CRED *, struct PKERB_AUTHORIZATION_DATA_s **)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, service_task`

## callers

- `0x18003eb80`
- `0x1800566a8`

## callees

- `0x1800077d0`
- `0x180007e00`
- `0x18000efd0`
- `0x180010e90`
- `0x180011150`
- `0x1800113f0`
- `0x18003d3f0`
- `0x18003de10`
- `0x18007108c`
- `0x1800744cf`
- `0x18008b70c`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003d513`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003d5f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003d650`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003d513`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003d5f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003d650`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d760`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d784`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d760`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d784`

## string_xrefs

- `0x18003d477`: `KerbGetServiceTicket not supported authz data\n`

## pseudocode

```c

```
