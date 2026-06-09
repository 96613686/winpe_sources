# TcpWSA::ReadDone(SNI_Packet * *,SNI_Packet * *,ulong,ulong)

- ea: `0x180180b70`
- end: `0x18018131b`
- name: `?ReadDone@TcpWSA@@UEAAKPEAPEAVSNI_Packet@@0KK@Z`
- size: `1963`
- prototype: `unsigned int __usercall@<eax>(TcpWSA *__hidden this@<rcx>, struct SNI_Packet **@<rdx>, struct SNI_Packet **@<r8>, unsigned int@<r9d>, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x1800030c0`
- `0x180003250`
- `0x180003d80`
- `0x18015a6f0`
- `0x18015a880`
- `0x18017ee40`
- `0x18017f380`
- `0x180180b70`
- `0x1801ad6a0`

## import_xrefs

- `WS2_32!WSARecv` at `0x1801810e7`
- `WS2_32!WSARecv` at `0x1801810e7`
- `WS2_32!WSAGetOverlappedResult` at `0x180180e32`
- `WS2_32!WSAGetOverlappedResult` at `0x180180e32`
- `WS2_32!__imp_WSAGetLastError` at `0x180180e3c`
- `WS2_32!__imp_WSAGetLastError` at `0x1801810f2`
- `WS2_32!__imp_WSAGetLastError` at `0x180180e3c`
- `WS2_32!__imp_WSAGetLastError` at `0x1801810f2`

## pseudocode

```c

```
