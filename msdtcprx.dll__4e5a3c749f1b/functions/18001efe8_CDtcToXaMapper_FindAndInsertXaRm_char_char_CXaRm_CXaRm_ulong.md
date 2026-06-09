# CDtcToXaMapper::FindAndInsertXaRm(char *,char *,CXaRm *,CXaRm * *,ulong *)

- ea: `0x18001efe8`
- end: `0x18001f18c`
- name: `?FindAndInsertXaRm@CDtcToXaMapper@@AEAAXPEAD0PEAVCXaRm@@PEAPEAV2@PEAK@Z`
- size: `420`
- prototype: `void(CDtcToXaMapper *__hidden this, char *, char *, struct CXaRm *, struct CXaRm **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001ebc8`

## callees

- `0x18000d5f4`
- `0x18000f364`
- `0x18001bfec`
- `0x18001efe8`
- `0x180085010`

## import_xrefs

- `msvcrt!_mbscmp` at `0x18001f0bc`
- `msvcrt!_mbscmp` at `0x18001f0d1`
- `msvcrt!_mbscmp` at `0x18001f0bc`
- `msvcrt!_mbscmp` at `0x18001f0d1`

## string_xrefs

- `0x18001f03a`: `CDtcToXaMapper::FindAndInsertXaRm (com\complus\dtc\dtc\msdtcprx\src\idtctoxamapper.cpp@512): Invalid parameter o_ppXarm`
- `0x18001f053`: `CDtcToXaMapper::FindAndInsertXaRm (com\complus\dtc\dtc\msdtcprx\src\idtctoxamapper.cpp@515): Invalid parameter o_pdwCookie`
- `0x18001f116`: `CDtcToXaMapper::FindAndInsertXaRm (com\complus\dtc\dtc\msdtcprx\src\idtctoxamapper.cpp@533): m_HashTable is in an invalid state`
- `0x18001f157`: `CDtcToXaMapper::FindAndInsertXaRm (com\complus\dtc\dtc\msdtcprx\src\idtctoxamapper.cpp@559): m_HashTable is in an invalid state`

## pseudocode

```c

```
