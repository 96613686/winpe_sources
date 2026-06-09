# boost::asio::detail::win_iocp_socket_service_base::get_nt_set_info(void)

- ea: `0x18016e338`
- end: `0x18016e3af`
- name: `?get_nt_set_info@win_iocp_socket_service_base@detail@asio@boost@@IEAAP6AJPEAXPEA_K0KK@ZXZ`
- size: `119`
- prototype: `int (*__fastcall(boost::asio::detail::win_iocp_socket_service_base *__hidden this))(void *, unsigned __int64 *, void *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1801708bc`

## callees

- `0x18016e338`
- `0x18032f050`

## import_xrefs

- `KERNEL32!GetModuleHandleA` at `0x18016e369`
- `KERNEL32!GetModuleHandleA` at `0x18016e369`
- `KERNEL32!GetProcAddress` at `0x18016e37e`
- `KERNEL32!GetProcAddress` at `0x18016e37e`

## string_xrefs

- `0x18016e362`: `NTDLL.DLL`

## pseudocode

```c

```
