# PROTOCOL_BINDING_ENTRY::QueryIsIpScoped(sockaddr *,PROTOCOL_BINDING_TABLE *,int *,IP_LIST_ENTRY * *)

- ea: `0x180059394`
- end: `0x1800594eb`
- name: `?QueryIsIpScoped@PROTOCOL_BINDING_ENTRY@@QEAAJPEAUsockaddr@@PEAVPROTOCOL_BINDING_TABLE@@PEAHPEAPEAVIP_LIST_ENTRY@@@Z`
- size: `343`
- prototype: `__int64 __usercall@<rax>(PROTOCOL_BINDING_ENTRY *__hidden this@<rcx>, SOCKADDR *pSockaddr@<rdx>, struct PROTOCOL_BINDING_TABLE *@<r8>, int *@<r9>, struct IP_LIST_ENTRY **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180057b64`

## callees

- `0x180059300`
- `0x180059394`
- `0x18006101a`
- `0x180061060`

## import_xrefs

- `WS2_32!GetNameInfoW` at `0x18005942e`
- `WS2_32!GetNameInfoW` at `0x18005942e`
- `WS2_32!__imp_WSAGetLastError` at `0x180059438`
- `WS2_32!__imp_WSAGetLastError` at `0x180059438`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800594c7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800594c7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180059461`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180059461`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180059476`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180059498`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180059476`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180059498`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800593f7`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800593f7`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x18005948c`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x18005948c`

## pseudocode

```c

```
