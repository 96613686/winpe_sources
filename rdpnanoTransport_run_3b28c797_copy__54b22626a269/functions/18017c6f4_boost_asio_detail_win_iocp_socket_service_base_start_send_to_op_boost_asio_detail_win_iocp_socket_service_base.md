# boost::asio::detail::win_iocp_socket_service_base::start_send_to_op(boost::asio::detail::win_iocp_socket_service_base::base_implementation_type &,_WSABUF *,unsigned __int64,void const *,int,int,boost::asio::detail::win_iocp_operation *)

- ea: `0x18017c6f4`
- end: `0x18017c7e2`
- name: `?start_send_to_op@win_iocp_socket_service_base@detail@asio@boost@@IEAAXAEAUbase_implementation_type@1234@PEAU_WSABUF@@_KPEBXHHPEAVwin_iocp_operation@234@@Z`
- size: `238`
- prototype: `void __fastcall(boost::asio::detail::win_iocp_socket_service_base *__hidden this, struct boost::asio::detail::win_iocp_socket_service_base::base_implementation_type *, struct _WSABUF *, unsigned __int64, struct sockaddr *, int, DWORD, LPWSAOVERLAPPED)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180175594`

## callees

- `0x18016f9fc`
- `0x18016fa94`
- `0x18017c6f4`
- `0x18032f050`
- `0x18032f0b0`

## import_xrefs

- `WS2_32!WSASendTo` at `0x18017c785`
- `WS2_32!WSASendTo` at `0x18017c785`
- `WS2_32!__imp_WSAGetLastError` at `0x18017c78d`
- `WS2_32!__imp_WSAGetLastError` at `0x18017c78d`

## pseudocode

```c

```
