# boost::asio::detail::win_iocp_socket_service_base::restart_accept_op(unsigned __int64,boost::asio::detail::socket_holder &,int,int,int,void *,ulong,long *,boost::asio::detail::win_iocp_operation *)

- ea: `0x180181290`
- end: `0x180181404`
- name: `?restart_accept_op@win_iocp_socket_service_base@detail@asio@boost@@QEAAX_KAEAVsocket_holder@234@HHHPEAXKPEAJPEAVwin_iocp_operation@234@@Z`
- size: `372`
- prototype: `void __fastcall(boost::asio::detail::win_iocp_socket_service_base *__hidden this, unsigned __int64, struct boost::asio::detail::socket_holder *, int, int, int, PVOID lpOutputBuffer, DWORD, int *, LPOVERLAPPED)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180180930`

## callees

- `0x18016f9fc`
- `0x18016fa94`
- `0x1801722a0`
- `0x180181024`
- `0x180181224`
- `0x180181290`
- `0x1802e0673`
- `0x18032f050`
- `0x18032f0b0`

## import_xrefs

- `WS2_32!__imp_WSAGetLastError` at `0x18018139a`
- `WS2_32!__imp_WSAGetLastError` at `0x18018139a`
- `KERNEL32!CancelIoEx` at `0x1801813d4`
- `KERNEL32!CancelIoEx` at `0x1801813d4`

## pseudocode

```c

```
