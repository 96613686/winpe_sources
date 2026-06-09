# NegInitialize(unsigned __int64,_SECPKG_PARAMETERS *,_LSA_SECPKG_FUNCTION_TABLE *)

- ea: `0x1800d6250`
- end: `0x1800d6603`
- name: `?NegInitialize@@YAJ_KPEAU_SECPKG_PARAMETERS@@PEAU_LSA_SECPKG_FUNCTION_TABLE@@@Z`
- size: `947`
- prototype: `__int64 __fastcall(unsigned __int64, struct _SECPKG_PARAMETERS *, struct _LSA_SECPKG_FUNCTION_TABLE *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180016e18`
- `0x180084f40`
- `0x1800d6250`
- `0x1801078b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d65a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d65a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d658c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d658c`
- `ntdll!NtAllocateLocallyUniqueId` at `0x1800d65c5`
- `ntdll!NtAllocateLocallyUniqueId` at `0x1800d65c5`
- `ntdll!RtlGetNtProductType` at `0x1800d64f0`
- `ntdll!RtlGetNtProductType` at `0x1800d64f0`
- `ntdll!RtlInitializeResource` at `0x1800d634c`
- `ntdll!RtlInitializeResource` at `0x1800d638f`
- `ntdll!RtlInitializeResource` at `0x1800d634c`
- `ntdll!RtlInitializeResource` at `0x1800d638f`
- `ntdll!RtlInitString` at `0x1800d65df`
- `ntdll!RtlInitString` at `0x1800d65df`
- `ntdll!RtlInitializeCriticalSection` at `0x1800d6277`
- `ntdll!RtlInitializeCriticalSection` at `0x1800d62fb`
- `ntdll!RtlInitializeCriticalSection` at `0x1800d6316`
- `ntdll!RtlInitializeCriticalSection` at `0x1800d6277`
- `ntdll!RtlInitializeCriticalSection` at `0x1800d62fb`
- `ntdll!RtlInitializeCriticalSection` at `0x1800d6316`
- `ntdll!RtlInitUnicodeString` at `0x1800d6338`
- `ntdll!RtlInitUnicodeString` at `0x1800d6338`
- `MSASN1!ASN1_CreateModule` at `0x1800d6558`
- `MSASN1!ASN1_CreateModule` at `0x1800d6558`

## pseudocode

```c

```
