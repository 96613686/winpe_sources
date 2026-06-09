# CDplUser::ProcessRecoveryPolicy(int)

- ea: `0x1800b7880`
- end: `0x1800b8179`
- name: `?ProcessRecoveryPolicy@CDplUser@@AEAAJH@Z`
- size: `2297`
- prototype: `__int64 __fastcall(CDplUser *__hidden this, int)`
- caller_count: `4`
- callee_count: `20`
- tags: `registry_config`

## callers

- `0x18008fb78`
- `0x180095334`
- `0x1800b6bc0`
- `0x1800ba574`

## callees

- `0x180005045`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x180087d4c`
- `0x180088170`
- `0x180089d38`
- `0x180097238`
- `0x1800a4840`
- `0x1800a849c`
- `0x1800aa3ec`
- `0x1800af128`
- `0x1800b39fc`
- `0x1800b5a5c`
- `0x1800b62c0`
- `0x1800b7880`
- `0x1800bd7a8`
- `0x1800bd810`
- `0x1800d5af8`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7d0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7d0a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800b7cd9`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800b8112`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800b7cd9`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800b8112`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1800b7cfb`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1800b7cfb`

## string_xrefs

- `0x1800b7db4`: `Lost recovery file. Will schedule worker to re-create it`
- `0x1800b7e17`: `Recovery file is empty. Will schedule worker to re-create it`
- `0x1800b7e41`: `Recovery file is not encrypted. Will schedule worker to re-create it`

## pseudocode

```c

```
