# WFDDeviceHandleInvitationRequestSendCompletion(_WFD_ROLE *,ulong,_DOT11_INVITATION_REQUEST_SEND_COMPLETE_PARAMETERS *)

- ea: `0x140083108`
- end: `0x14008336d`
- name: `?WFDDeviceHandleInvitationRequestSendCompletion@@YAXPEAU_WFD_ROLE@@KPEAU_DOT11_INVITATION_REQUEST_SEND_COMPLETE_PARAMETERS@@@Z`
- size: `613`
- prototype: `void __fastcall(struct _WFD_ROLE *, unsigned int, struct _DOT11_INVITATION_REQUEST_SEND_COMPLETE_PARAMETERS *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x14007db40`

## callees

- `0x140020dc0`
- `0x140022f08`
- `0x14003b04c`
- `0x140080dfc`
- `0x140083108`
- `0x14008adb8`
- `0x14008bfb0`
- `0x14008c694`
- `0x14008c788`
- `0x14008d918`
- `0x14008de3c`
- `0x14009bbb0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14008329c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008333a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008329c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008333a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14008318f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14008318f`

## pseudocode

```c

```
