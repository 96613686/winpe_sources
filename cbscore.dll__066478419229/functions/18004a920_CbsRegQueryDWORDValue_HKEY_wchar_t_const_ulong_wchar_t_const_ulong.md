# CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)

- ea: `0x18004a920`
- end: `0x18004b091`
- name: `?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z`
- size: `1905`
- prototype: `int(HKEY, const wchar_t *, unsigned int, const wchar_t *, unsigned int *)`
- caller_count: `43`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x1800310d8`
- `0x18004a864`
- `0x180051dd4`
- `0x18005b7e4`
- `0x18009d010`
- `0x1800bcda0`
- `0x1800be2e0`
- `0x1800c294c`
- `0x1800c5960`
- `0x1800d56c8`
- `0x1800e1850`
- `0x1800e8698`
- `0x1800eda48`
- `0x1800f3f0c`
- `0x1800f7290`
- `0x1800f8048`
- `0x1800f87b0`
- `0x1800faf90`
- `0x1800fb80c`
- `0x1800feaa8`
- `0x1801128f0`
- `0x1801129c0`
- `0x180112ed8`
- `0x180122190`
- `0x180123cf0`
- `0x180126880`
- `0x180129734`
- `0x180129968`
- `0x180138b94`
- `0x18014aaac`
- `0x18017b938`
- `0x180186630`
- `0x18018c9fc`
- `0x1801968ac`
- `0x1801baf74`
- `0x1801c2c30`
- `0x1801cdfc8`
- `0x1801da358`
- `0x1801daec8`
- `0x1801deba0`
- `0x1801e69bc`
- `0x1801efae0`
- `0x18029c6cc`

## callees

- `0x180033338`
- `0x1800441fc`
- `0x18004a494`
- `0x18004a920`
- `0x180050f18`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800aa20c`
- `0x1800eb920`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aadf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ace8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ad76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004af76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b04c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aadf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ace8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ad76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004af76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b04c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004ad35`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004ad35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004aacb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004acd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ad66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004af66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b03c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004aacb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004acd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ad66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004af66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b03c`
- `ntdll!RtlRaiseStatus` at `0x18004ab9a`
- `ntdll!RtlRaiseStatus` at `0x18004abdb`
- `ntdll!RtlRaiseStatus` at `0x18004ac4a`
- `ntdll!RtlRaiseStatus` at `0x18004ae34`
- `ntdll!RtlRaiseStatus` at `0x18004ae75`
- `ntdll!RtlRaiseStatus` at `0x18004aee4`
- `ntdll!RtlRaiseStatus` at `0x18004ab9a`
- `ntdll!RtlRaiseStatus` at `0x18004abdb`
- `ntdll!RtlRaiseStatus` at `0x18004ac4a`
- `ntdll!RtlRaiseStatus` at `0x18004ae34`
- `ntdll!RtlRaiseStatus` at `0x18004ae75`
- `ntdll!RtlRaiseStatus` at `0x18004aee4`
- `ntdll!RtlLeaveCriticalSection` at `0x18004ab84`
- `ntdll!RtlLeaveCriticalSection` at `0x18004abc9`
- `ntdll!RtlLeaveCriticalSection` at `0x18004ac38`
- `ntdll!RtlLeaveCriticalSection` at `0x18004ae1e`
- `ntdll!RtlLeaveCriticalSection` at `0x18004ae63`
- `ntdll!RtlLeaveCriticalSection` at `0x18004aed2`
- `ntdll!RtlLeaveCriticalSection` at `0x18004ab84`
- `ntdll!RtlLeaveCriticalSection` at `0x18004abc9`
- `ntdll!RtlLeaveCriticalSection` at `0x18004ac38`
- `ntdll!RtlLeaveCriticalSection` at `0x18004ae1e`
- `ntdll!RtlLeaveCriticalSection` at `0x18004ae63`
- `ntdll!RtlLeaveCriticalSection` at `0x18004aed2`
- `ntdll!RtlEnterCriticalSection` at `0x18004ab18`
- `ntdll!RtlEnterCriticalSection` at `0x18004adb2`
- `ntdll!RtlEnterCriticalSection` at `0x18004ab18`
- `ntdll!RtlEnterCriticalSection` at `0x18004adb2`

## string_xrefs

- `0x18004ac0d`: `Failed to open the registry root: n/a, key: {}.`
- `0x18004aea7`: `Failed to query registry value: {}`
- `0x18004afad`: `Registry value is not a DWORD type.`

## pseudocode

```c

```
