# MsiUIMessageContext::ProcessEndTransactionMessages(void *)

- ea: `0x1801ce0a0`
- end: `0x1801ce29c`
- name: `?ProcessEndTransactionMessages@MsiUIMessageContext@@QEAAKPEAX@Z`
- size: `508`
- prototype: `unsigned int __fastcall(MsiUIMessageContext *__hidden this, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1801ce090`

## callees

- `0x18000919c`
- `0x180009c38`
- `0x18000c4bc`
- `0x180027634`
- `0x1801ce0a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801ce22f`
- `KERNEL32!GetLastError` at `0x1801ce22f`
- `KERNEL32!SetEvent` at `0x1801ce18d`
- `KERNEL32!SetEvent` at `0x1801ce18d`
- `USER32!MsgWaitForMultipleObjects` at `0x1801ce0ef`
- `USER32!MsgWaitForMultipleObjects` at `0x1801ce0ef`
- `USER32!PeekMessageW` at `0x1801ce216`
- `USER32!PeekMessageW` at `0x1801ce216`
- `USER32!TranslateMessage` at `0x1801ce1e8`
- `USER32!TranslateMessage` at `0x1801ce1e8`
- `USER32!DispatchMessageW` at `0x1801ce1f9`
- `USER32!DispatchMessageW` at `0x1801ce1f9`
- `USER32!IsDialogMessageW` at `0x1801ce1d3`
- `USER32!IsDialogMessageW` at `0x1801ce1d3`

## string_xrefs

- `0x1801ce127`: `Invalid event trigger in wait for engine thread`
- `0x1801ce254`: `Wait Failed in MsiUIMessageContext::ProcessEndTransactionMessages. GetLastError returned %d.`

## pseudocode

```c

```
