# WorkThreadManager::CThread::WaitForThreadUpdate(ulong)

- ea: `0x1800098f0`
- end: `0x180009a24`
- name: `?WaitForThreadUpdate@CThread@WorkThreadManager@@AEAAJK@Z`
- size: `308`
- prototype: `int(WorkThreadManager::CThread *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800098a0`
- `0x18000c994`

## callees

- `0x1800098f0`
- `0x180013498`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180009a03`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180009a03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009948`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009948`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageW` at `0x1800099a2`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageW` at `0x1800099a2`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x180009984`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x1800099c1`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x180009984`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x1800099c1`
- `ext-ms-win-ntuser-message-l1-1-0!TranslateMessage` at `0x180009997`
- `ext-ms-win-ntuser-message-l1-1-0!TranslateMessage` at `0x180009997`
- `ext-ms-win-rtcore-ntuser-synch-ext-l1-1-0!MsgWaitForMultipleObjectsEx` at `0x18000993d`
- `ext-ms-win-rtcore-ntuser-synch-ext-l1-1-0!MsgWaitForMultipleObjectsEx` at `0x18000993d`

## pseudocode

```c

```
