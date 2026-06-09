# boost::asio::detail::service_registry::do_use_service(boost::asio::execution_context::service::key const &,boost::asio::execution_context::service * (*)(boost::asio::execution_context &,void *),void *)

- ea: `0x18016dc24`
- end: `0x18016dd7b`
- name: `?do_use_service@service_registry@detail@asio@boost@@AEAAPEAVservice@execution_context@34@AEBUkey@5634@P6APEAV5634@AEAV634@PEAX@Z2@Z`
- size: `343`
- prototype: `struct boost::asio::execution_context::service *__fastcall(boost::asio::detail::service_registry *__hidden this, const struct boost::asio::execution_context::service::key *, struct boost::asio::execution_context::service *(*)(struct boost::asio::execution_context *, void *), void *)`
- caller_count: `9`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1801616e8`
- `0x180161738`
- `0x180161788`
- `0x1801617d0`
- `0x180161818`
- `0x180161860`
- `0x180176340`
- `0x180176390`
- `0x18017dd3c`

## callees

- `0x18016dc24`
- `0x18032f050`
- `0x1803319b8`
- `0x180375c40`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18016dc57`
- `KERNEL32!EnterCriticalSection` at `0x18016dcde`
- `KERNEL32!EnterCriticalSection` at `0x18016dc57`
- `KERNEL32!EnterCriticalSection` at `0x18016dcde`
- `KERNEL32!LeaveCriticalSection` at `0x18016dcb4`
- `KERNEL32!LeaveCriticalSection` at `0x18016dd57`
- `KERNEL32!LeaveCriticalSection` at `0x18016dcb4`
- `KERNEL32!LeaveCriticalSection` at `0x18016dd57`

## pseudocode

```c

```
