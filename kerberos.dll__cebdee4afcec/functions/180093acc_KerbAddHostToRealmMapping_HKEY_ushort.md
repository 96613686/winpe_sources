# KerbAddHostToRealmMapping(HKEY__ *,ushort *)

- ea: `0x180093acc`
- end: `0x180093e31`
- name: `?KerbAddHostToRealmMapping@@YAEPEAUHKEY__@@PEAG@Z`
- size: `869`
- prototype: `unsigned __int8 __fastcall(HKEY hKey, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x180094410`

## callees

- `0x1800069a0`
- `0x180007e80`
- `0x1800093f0`
- `0x180070680`
- `0x1800744cf`
- `0x18008b70c`
- `0x180093acc`
- `0x1800f1ea0`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180093b53`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180093c4b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180093b53`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180093c4b`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180093d32`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180093d32`
- `ntdll!RtlInitUnicodeString` at `0x180093b31`
- `ntdll!RtlInitUnicodeString` at `0x180093ca4`
- `ntdll!RtlInitUnicodeString` at `0x180093b31`
- `ntdll!RtlInitUnicodeString` at `0x180093ca4`

## string_xrefs

- `0x180093b5f`: `Wrong registry type \n`

## pseudocode

```c

```
