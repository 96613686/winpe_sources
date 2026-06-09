# CNetAPI32::GetTrustedDomainsNT(CHStringArray &)

- ea: `0x18006ab10`
- end: `0x18006ae0d`
- name: `?GetTrustedDomainsNT@CNetAPI32@@QEAAHAEAVCHStringArray@@@Z`
- size: `765`
- prototype: `__int64 __fastcall(CNetAPI32 *__hidden this, struct CHStringArray *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d4e98`

## callees

- `0x1800212d8`
- `0x180021360`
- `0x18005e690`
- `0x18006ab10`
- `0x180080e0c`
- `0x1800f2d9c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18006ab75`
- `ntdll!RtlNtStatusToDosError` at `0x18006acd0`
- `ntdll!RtlNtStatusToDosError` at `0x18006ab75`
- `ntdll!RtlNtStatusToDosError` at `0x18006acd0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006ab7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006adec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006ab7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006adec`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18006ac0e`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18006ac0e`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18006abc4`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18006acf8`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18006ad65`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18006abc4`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18006acf8`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18006ad65`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x18006ad36`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x18006ad36`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x18006abba`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x18006acee`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x18006ad27`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x18006abba`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x18006acee`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x18006ad27`
- `framedynos!?Add@CHStringArray@@QEAAHPEBG@Z` at `0x18006abd0`
- `framedynos!?Add@CHStringArray@@QEAAHPEBG@Z` at `0x18006ad04`
- `framedynos!?Add@CHStringArray@@QEAAHPEBG@Z` at `0x18006abd0`
- `framedynos!?Add@CHStringArray@@QEAAHPEBG@Z` at `0x18006ad04`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18006abdf`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18006ac75`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18006ad10`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18006ad42`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18006abdf`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18006ac75`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18006ad10`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18006ad42`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18006ac62`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18006acb0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18006ad9e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18006ac62`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18006acb0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18006ad9e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18006ab65`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18006ab65`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18006ab95`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18006ac2a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18006ab95`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18006ac2a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18006abeb`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18006ac4d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18006ad51`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18006abeb`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18006ac4d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18006ad51`

## pseudocode

```c

```
