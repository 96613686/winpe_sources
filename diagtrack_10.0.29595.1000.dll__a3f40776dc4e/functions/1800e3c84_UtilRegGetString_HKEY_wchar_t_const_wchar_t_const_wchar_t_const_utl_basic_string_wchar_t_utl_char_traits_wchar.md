# UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)

- ea: `0x1800e3c84`
- end: `0x1800e3ef9`
- name: `?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z`
- size: `629`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, LPCWSTR lpValue@<r8>, __int64, char, char)`
- caller_count: `7`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800e183c`
- `0x1800e2438`
- `0x1800e2aa8`
- `0x1800e5c1c`
- `0x1800e6260`
- `0x180191a0c`
- `0x18019c878`

## callees

- `0x1800e2674`
- `0x1800e3c84`
- `0x1800e3f00`
- `0x1800e4410`
- `0x1800e4454`
- `0x1800e4c98`
- `0x18020afa4`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800e3dcd`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800e3dcd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e3d13`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e3d13`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e3cee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e3e34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e3ee2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e3cee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e3e34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e3ee2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e3d57`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e3db3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e3d57`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e3db3`

## pseudocode

```c

```
