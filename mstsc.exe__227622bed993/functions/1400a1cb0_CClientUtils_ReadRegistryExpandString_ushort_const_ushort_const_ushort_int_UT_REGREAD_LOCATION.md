# CClientUtils::ReadRegistryExpandString(ushort const *,ushort const *,ushort * *,int *,UT_REGREAD_LOCATION)

- ea: `0x1400a1cb0`
- end: `0x1400a1f71`
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
- `0x14009f8f4`
- `0x14009ffc8`
- `0x1400a19d0`
- `0x1400a1cb0`
- `0x140111220`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x1400a1e68`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1400a1e95`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1400a1e68`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1400a1e95`
- `KERNEL32!LocalAlloc` at `0x1400a1e7b`
- `KERNEL32!LocalAlloc` at `0x1400a1e7b`
- `ADVAPI32!RegCloseKey` at `0x1400a1eb9`
- `ADVAPI32!RegCloseKey` at `0x1400a1eb9`

## string_xrefs

- `0x1400a1d54`: `Unable to get AppContainer registry location.`

## pseudocode

```c

```
