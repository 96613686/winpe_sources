# BuildNormalizedBinding(sockaddr const *,ushort const *,STRU *,ulong *)

- ea: `0x18002aac4`
- end: `0x18002ac8c`
- name: `?BuildNormalizedBinding@@YAJPEBUsockaddr@@PEBGPEAVSTRU@@PEAK@Z`
- size: `456`
- prototype: `signed int __fastcall(SOCKADDR *pSockaddr, const unsigned __int16 *, struct STRU *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path`

## callers

- `0x18000c1f4`
- `0x180045730`

## callees

- `0x18002aac4`
- `0x18004700f`
- `0x180047050`

## import_xrefs

- `msvcrt!_itow` at `0x18002abbb`
- `msvcrt!_itow` at `0x18002abbb`
- `msvcrt!wcschr` at `0x18002ac2e`
- `msvcrt!wcschr` at `0x18002ac2e`
- `WS2_32!GetNameInfoW` at `0x18002ab4a`
- `WS2_32!GetNameInfoW` at `0x18002ab4a`
- `WS2_32!__imp_ntohs` at `0x18002aba7`
- `WS2_32!__imp_ntohs` at `0x18002aba7`
- `WS2_32!__imp_WSAGetLastError` at `0x18002ab58`
- `WS2_32!__imp_WSAGetLastError` at `0x18002ab58`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002ac84`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002ac84`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002abdb`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002ac02`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002ac5a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002abdb`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002ac02`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002ac5a`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x18002abc9`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x18002abed`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x18002ac48`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x18002ac6c`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x18002abc9`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x18002abed`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x18002ac48`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x18002ac6c`

## pseudocode

```c

```
