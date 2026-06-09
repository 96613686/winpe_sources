# CClientUtils::ReadRegistryExpandString(ushort const *,ushort const *,ushort * *,int *,UT_REGREAD_LOCATION)

- ea: `0x1400a3e20`
- end: `0x1400a40e1`
- name: `?ReadRegistryExpandString@CClientUtils@@UEAAHPEBG0PEAPEAGPEAHW4UT_REGREAD_LOCATION@@@Z`
- size: `705`
- prototype: `int __high(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, int *, enum UT_REGREAD_LOCATION)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000d078`
- `0x1400a1a64`
- `0x1400a2138`
- `0x1400a3b40`
- `0x1400a3e20`
- `0x140113390`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x1400a3fd8`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1400a4005`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1400a3fd8`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1400a4005`
- `KERNEL32!LocalAlloc` at `0x1400a3feb`
- `KERNEL32!LocalAlloc` at `0x1400a3feb`
- `ADVAPI32!RegCloseKey` at `0x1400a4029`
- `ADVAPI32!RegCloseKey` at `0x1400a4029`

## string_xrefs

- `0x1400a3ec4`: `Unable to get AppContainer registry location.`

## pseudocode

```c

```
