# CTSScpRegister::WaitForOperationCompletion(void)

- ea: `0x18007cc04`
- end: `0x18007cc8b`
- name: `?WaitForOperationCompletion@CTSScpRegister@@AEAAJXZ`
- size: `135`
- prototype: `__int64 __fastcall(CTSScpRegister *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18007b900`
- `0x18007c920`
- `0x18007ca00`

## callees

- `0x18007cc04`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007cc54`
- `KERNEL32!GetLastError` at `0x18007cc54`
- `KERNEL32!ResetEvent` at `0x18007cc3a`
- `KERNEL32!ResetEvent` at `0x18007cc3a`
- `KERNEL32!WaitForSingleObject` at `0x18007cc28`
- `KERNEL32!WaitForSingleObject` at `0x18007cc28`

## pseudocode

```c

```
