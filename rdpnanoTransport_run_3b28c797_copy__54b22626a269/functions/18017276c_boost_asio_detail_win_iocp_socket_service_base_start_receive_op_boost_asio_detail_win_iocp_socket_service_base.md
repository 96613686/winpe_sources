# boost::asio::detail::win_iocp_socket_service_base::start_receive_op(boost::asio::detail::win_iocp_socket_service_base::base_implementation_type &,_WSABUF *,unsigned __int64,int,bool,boost::asio::detail::win_iocp_operation *)

- ea: `0x18017276c`
- end: `0x180172874`
- name: `?start_receive_op@win_iocp_socket_service_base@detail@asio@boost@@IEAAXAEAUbase_implementation_type@1234@PEAU_WSABUF@@_KH_NPEAVwin_iocp_operation@234@@Z`
- size: `264`
- prototype: `void __fastcall(boost::asio::detail::win_iocp_socket_service_base *__hidden this, struct boost::asio::detail::win_iocp_socket_service_base::base_implementation_type *, struct _WSABUF *, unsigned __int64, int, bool, LPWSAOVERLAPPED)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18015e128`

## callees

- `0x18016f9fc`
- `0x18016fa94`
- `0x18017276c`
- `0x18032f050`
- `0x18032f0b0`

## import_xrefs

- `WS2_32!WSARecv` at `0x18017280b`
- `WS2_32!WSARecv` at `0x18017280b`
- `WS2_32!__imp_WSAGetLastError` at `0x180172813`
- `WS2_32!__imp_WSAGetLastError` at `0x180172813`

## pseudocode

```c

```
