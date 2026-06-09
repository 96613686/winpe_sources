# WFDDeviceHandleInvitationRequestSendCompletion(_WFD_ROLE *,ulong,_DOT11_INVITATION_REQUEST_SEND_COMPLETE_PARAMETERS *)

- ea: `0x1400818d8`
- end: `0x140081b3d`
- name: `?WFDDeviceHandleInvitationRequestSendCompletion@@YAXPEAU_WFD_ROLE@@KPEAU_DOT11_INVITATION_REQUEST_SEND_COMPLETE_PARAMETERS@@@Z`
- size: `613`
- prototype: `void __fastcall(struct _WFD_ROLE *, unsigned int, struct _DOT11_INVITATION_REQUEST_SEND_COMPLETE_PARAMETERS *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x14007c310`

## callees

- `0x140020dc0`
- `0x140022f08`
- `0x14003ae2c`
- `0x14007f5cc`
- `0x1400818d8`
- `0x140089588`
- `0x14008a780`
- `0x14008ae64`
- `0x14008af58`
- `0x14008c0e8`
- `0x14008c60c`
- `0x14009a3d0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140081a6c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140081b0a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140081a6c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140081b0a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14008195f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14008195f`

## pseudocode

```c

```
