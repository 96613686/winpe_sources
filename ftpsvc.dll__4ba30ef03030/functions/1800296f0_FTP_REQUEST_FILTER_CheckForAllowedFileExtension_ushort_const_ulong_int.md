# FTP_REQUEST_FILTER::CheckForAllowedFileExtension(ushort const *,ulong,int *)

- ea: `0x1800296f0`
- end: `0x18002989b`
- name: `?CheckForAllowedFileExtension@FTP_REQUEST_FILTER@@QEAAJPEBGKPEAH@Z`
- size: `427`
- prototype: `__int64 __fastcall(FTP_REQUEST_FILTER *this, wchar_t *, __int64, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000e5cc`
- `0x180010370`

## callees

- `0x1800296f0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180029740`
- `msvcrt!wcsrchr` at `0x180029756`
- `msvcrt!wcsrchr` at `0x180029740`
- `msvcrt!wcsrchr` at `0x180029756`
- `msvcrt!_wcsicmp` at `0x180029786`
- `msvcrt!_wcsicmp` at `0x1800297d7`
- `msvcrt!_wcsicmp` at `0x180029786`
- `msvcrt!_wcsicmp` at `0x1800297d7`
- `iisutil!PuDbgPrint` at `0x18002983e`
- `iisutil!PuDbgPrint` at `0x18002987b`
- `iisutil!PuDbgPrint` at `0x18002983e`
- `iisutil!PuDbgPrint` at `0x18002987b`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x18002970a`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x18002971c`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x18002976e`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x1800297c3`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x18002970a`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x18002971c`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x18002976e`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x1800297c3`

## string_xrefs

- `0x180029856`: `Found denied file extension '%S'.\n`
- `0x180029825`: `FTP_REQUEST_FILTER::CheckForAllowedFileExtension`
- `0x180029862`: `FTP_REQUEST_FILTER::CheckForAllowedFileExtension`
- `0x180029819`: `File extension '%S' is not specifically allowed and will be rejected.\n`

## pseudocode

```c

```
