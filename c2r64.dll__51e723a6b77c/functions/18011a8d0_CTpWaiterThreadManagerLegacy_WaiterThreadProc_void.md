# CTpWaiterThreadManagerLegacy::WaiterThreadProc(void *)

- ea: `0x18011a8d0`
- end: `0x18011ae94`
- name: `?WaiterThreadProc@CTpWaiterThreadManagerLegacy@@CAKPEAX@Z`
- size: `1476`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, installer_update`

## callees

- `0x1800264b4`
- `0x18002d8d4`
- `0x18002d96c`
- `0x180052cd0`
- `0x1801148a0`
- `0x180119bec`
- `0x18011a598`
- `0x18011a8d0`
- `0x18011afb0`
- `0x18011b10c`
- `0x180146090`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x18011aba9`
- `KERNEL32!GetTickCount64` at `0x18011ad7e`
- `KERNEL32!GetTickCount64` at `0x18011aba9`
- `KERNEL32!GetTickCount64` at `0x18011ad7e`
- `KERNEL32!WaitForSingleObject` at `0x18011ad17`
- `KERNEL32!WaitForSingleObject` at `0x18011ad17`
- `ADVAPI32!RevertToSelf` at `0x18011a9b2`
- `ADVAPI32!RevertToSelf` at `0x18011a9b2`
- `USER32!MsgWaitForMultipleObjects` at `0x18011abe8`
- `USER32!MsgWaitForMultipleObjects` at `0x18011abe8`
- `USER32!TranslateMessage` at `0x18011acb6`
- `USER32!TranslateMessage` at `0x18011acb6`
- `USER32!DispatchMessageW` at `0x18011acc0`
- `USER32!DispatchMessageW` at `0x18011acc0`
- `USER32!PeekMessageW` at `0x18011acd6`
- `USER32!PeekMessageW` at `0x18011acd6`

## pseudocode

```c

```
