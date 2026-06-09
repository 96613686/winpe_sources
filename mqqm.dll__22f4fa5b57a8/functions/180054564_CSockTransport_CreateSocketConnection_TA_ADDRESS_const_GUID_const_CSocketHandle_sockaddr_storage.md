# CSockTransport::CreateSocketConnection(_TA_ADDRESS const *,_GUID const *,CSocketHandle &,sockaddr_storage &)

- ea: `0x180054564`
- end: `0x180054723`
- name: `?CreateSocketConnection@CSockTransport@@AEAAJPEBU_TA_ADDRESS@@PEBU_GUID@@AEAVCSocketHandle@@AEAUsockaddr_storage@@@Z`
- size: `447`
- prototype: `__int64 __usercall@<rax>(CSockTransport *__hidden this@<rcx>, const struct _TA_ADDRESS *@<rdx>, const struct _GUID *@<r8>, struct CSocketHandle *@<r9>, struct sockaddr_storage *)`
- caller_count: `3`
- callee_count: `13`
- tags: ``

## callers

- `0x180053eb8`
- `0x180054054`
- `0x180054240`

## callees

- `0x18000f35c`
- `0x18002c61c`
- `0x18002c6c8`
- `0x18003469c`
- `0x1800355cc`
- `0x18004c1c4`
- `0x18004c810`
- `0x18004e654`
- `0x180054564`
- `0x180056088`
- `0x180059090`
- `0x180059b48`
- `0x1800d012c`

## import_xrefs

- `msvcrt!free` at `0x180054703`
- `msvcrt!free` at `0x180054703`
- `WSOCK32!__imp_bind` at `0x18005462e`
- `WSOCK32!__imp_bind` at `0x18005462e`
- `WSOCK32!__imp_htons` at `0x1800545b9`
- `WSOCK32!__imp_htons` at `0x1800545b9`
- `WSOCK32!__imp_WSAGetLastError` at `0x18005463d`
- `WSOCK32!__imp_WSAGetLastError` at `0x18005463d`

## pseudocode

```c

```
