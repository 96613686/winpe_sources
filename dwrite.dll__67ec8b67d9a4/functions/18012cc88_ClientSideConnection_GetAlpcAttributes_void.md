# ClientSideConnection::GetAlpcAttributes(void)

- ea: `0x18012cc88`
- end: `0x18012cd94`
- name: `?GetAlpcAttributes@ClientSideConnection@@AEAAPEAU_ALPC_MESSAGE_ATTRIBUTES@@XZ`
- size: `268`
- prototype: `struct _ALPC_MESSAGE_ATTRIBUTES *__fastcall(ClientSideConnection *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18012cac0`
- `0x18012d230`
- `0x18012d734`
- `0x18022c950`
- `0x18028f248`

## callees

- `0x18012cc88`
- `0x1801f68b0`
- `0x180212f4c`

## import_xrefs

- `ntdll!AlpcGetMessageAttribute` at `0x18012cd49`
- `ntdll!AlpcGetMessageAttribute` at `0x18012cd49`
- `ntdll!AlpcInitializeMessageAttribute` at `0x18012ccc9`
- `ntdll!AlpcInitializeMessageAttribute` at `0x18012cd21`
- `ntdll!AlpcInitializeMessageAttribute` at `0x18012ccc9`
- `ntdll!AlpcInitializeMessageAttribute` at `0x18012cd21`

## pseudocode

```c

```
