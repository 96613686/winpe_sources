# boost::asio::detail::select_reactor::start_op(int,unsigned __int64,boost::asio::detail::select_reactor::per_descriptor_data &,boost::asio::detail::reactor_op *,bool,bool,void (*)(boost::asio::detail::win_iocp_operation *,bool,void const *),void const *)

- ea: `0x1801726bc`
- end: `0x18017276c`
- name: `?start_op@select_reactor@detail@asio@boost@@QEAAXH_KAEAUper_descriptor_data@1234@PEAVreactor_op@234@_N3P6AXPEAVwin_iocp_operation@234@3PEBX@Z5@Z`
- size: `176`
- prototype: `void __fastcall(boost::asio::detail::select_reactor *__hidden this, int, unsigned __int64, struct boost::asio::detail::select_reactor::per_descriptor_data *, struct boost::asio::detail::reactor_op *, bool, bool, void (*)(struct boost::asio::detail::win_iocp_operation *, bool, const void *), const void *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1801723ec`

## callees

- `0x18016dd7c`
- `0x18016eea8`
- `0x1801726bc`
- `0x18032f050`
- `0x180375c40`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1801726ee`
- `KERNEL32!EnterCriticalSection` at `0x1801726ee`
- `KERNEL32!LeaveCriticalSection` at `0x180172765`

## pseudocode

```c

```
