# Win32LiveSystemProvider::GetOsInfo(ulong *,ulong *,ulong *,ulong *,ushort *,ushort *,ushort *)

- ea: `0x1803ff640`
- end: `0x1803ff7fe`
- name: `?GetOsInfo@Win32LiveSystemProvider@@UEAAJPEAK000PEAG11@Z`
- size: `446`
- prototype: `__int64 __fastcall(Win32LiveSystemProvider *__hidden this, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18040dd20`

## callees

- `0x1800f0f40`
- `0x180159964`
- `0x1803ff640`
- `0x1804da4c0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_strlwr_s` at `0x1803ff79a`
- `api-ms-win-crt-string-l1-1-0!_strlwr_s` at `0x1803ff79a`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExA` at `0x1803ff77e`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExA` at `0x1803ff77e`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x1803ff7c5`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x1803ff7c5`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExA` at `0x1803ff724`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExA` at `0x1803ff724`
- `ntdll!RtlGetVersion` at `0x1803ff6b4`
- `ntdll!RtlGetVersion` at `0x1803ff6b4`

## pseudocode

```c

```
