# PcapFolderScan(RtlNameValueArray &,IShellLinkW *,IPersistFile *,ushort const *,ushort const *,ushort const *,uint)

- ea: `0x1800933e4`
- end: `0x180093855`
- name: `?PcapFolderScan@@YAKAEAVRtlNameValueArray@@PEAUIShellLinkW@@PEAUIPersistFile@@PEBG33I@Z`
- size: `1137`
- prototype: `unsigned int __fastcall(struct RtlNameValueArray *, struct IShellLinkW *, struct IPersistFile *, const unsigned __int16 *, const unsigned __int16 *, wchar_t *Source, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180092ab8`
- `0x1800933e4`

## callees

- `0x18000d530`
- `0x180012920`
- `0x180080fe0`
- `0x1800933e4`
- `0x1800f1f10`
- `0x1800f7010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18009350d`
- `msvcrt!wcscat_s` at `0x1800935d1`
- `msvcrt!wcscat_s` at `0x1800935e2`
- `msvcrt!wcscat_s` at `0x18009350d`
- `msvcrt!wcscat_s` at `0x1800935d1`
- `msvcrt!wcscat_s` at `0x1800935e2`
- `msvcrt!wcscpy_s` at `0x1800934f8`
- `msvcrt!wcscpy_s` at `0x1800935bc`
- `msvcrt!wcscpy_s` at `0x1800934f8`
- `msvcrt!wcscpy_s` at `0x1800935bc`
- `msvcrt!_wcsicmp` at `0x1800936dd`
- `msvcrt!_wcsicmp` at `0x1800937a2`
- `msvcrt!_wcsicmp` at `0x1800937dd`
- `msvcrt!_wcsicmp` at `0x1800936dd`
- `msvcrt!_wcsicmp` at `0x1800937a2`
- `msvcrt!_wcsicmp` at `0x1800937dd`
- `ntdll!RtlFreeHeap` at `0x180093665`
- `ntdll!RtlFreeHeap` at `0x180093682`
- `ntdll!RtlFreeHeap` at `0x18009369f`
- `ntdll!RtlFreeHeap` at `0x180093665`
- `ntdll!RtlFreeHeap` at `0x180093682`
- `ntdll!RtlFreeHeap` at `0x18009369f`
- `ntdll!RtlAllocateHeap` at `0x18009344e`
- `ntdll!RtlAllocateHeap` at `0x18009348f`
- `ntdll!RtlAllocateHeap` at `0x1800934d7`
- `ntdll!RtlAllocateHeap` at `0x18009344e`
- `ntdll!RtlAllocateHeap` at `0x18009348f`
- `ntdll!RtlAllocateHeap` at `0x1800934d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009352a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009352a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18009364d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18009364d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800937ef`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800937ef`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180093519`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180093519`

## pseudocode

```c

```
