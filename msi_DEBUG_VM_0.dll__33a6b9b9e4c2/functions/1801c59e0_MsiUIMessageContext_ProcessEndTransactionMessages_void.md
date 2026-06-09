# MsiUIMessageContext::ProcessEndTransactionMessages(void *)

- ea: `0x1801c59e0`
- end: `0x1801c5baa`
- name: `?ProcessEndTransactionMessages@MsiUIMessageContext@@QEAAKPEAX@Z`
- size: `458`
- prototype: `unsigned int __fastcall(MsiUIMessageContext *__hidden this, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1801c59d0`

## callees

- `0x18000a150`
- `0x180025a18`
- `0x18009b23c`
- `0x18009bc00`
- `0x1801c59e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801c5b44`
- `KERNEL32!GetLastError` at `0x1801c5b44`
- `KERNEL32!SetEvent` at `0x1801c5ac4`
- `KERNEL32!SetEvent` at `0x1801c5ac4`
- `USER32!MsgWaitForMultipleObjects` at `0x1801c5a2f`
- `USER32!MsgWaitForMultipleObjects` at `0x1801c5a2f`
- `USER32!PeekMessageW` at `0x1801c5b31`
- `USER32!PeekMessageW` at `0x1801c5b31`
- `USER32!TranslateMessage` at `0x1801c5b0f`
- `USER32!TranslateMessage` at `0x1801c5b0f`
- `USER32!DispatchMessageW` at `0x1801c5b1a`
- `USER32!DispatchMessageW` at `0x1801c5b1a`
- `USER32!IsDialogMessageW` at `0x1801c5b00`
- `USER32!IsDialogMessageW` at `0x1801c5b00`

## string_xrefs

- `0x1801c5a61`: `Invalid event trigger in wait for engine thread`
- `0x1801c5b63`: `Wait Failed in MsiUIMessageContext::ProcessEndTransactionMessages. GetLastError returned %d.`

## pseudocode

```c

```
