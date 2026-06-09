# CCspSimpleRegHelper::GetStringRegValue(HKEY__ *,ushort const *,ushort const *,tagVARIANT *)

- ea: `0x1800fd51c`
- end: `0x1800fd679`
- name: `?GetStringRegValue@CCspSimpleRegHelper@@CAJPEAUHKEY__@@PEBG1PEAUtagVARIANT@@@Z`
- size: `349`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800fd680`

## callees

- `0x1800fd51c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800fd62d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800fd62d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fd650`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fd650`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fd5ab`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fd610`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fd5ab`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fd610`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fd55a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fd55a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800fd65f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800fd65f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800fd5d4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800fd5d4`

## pseudocode

```c

```
