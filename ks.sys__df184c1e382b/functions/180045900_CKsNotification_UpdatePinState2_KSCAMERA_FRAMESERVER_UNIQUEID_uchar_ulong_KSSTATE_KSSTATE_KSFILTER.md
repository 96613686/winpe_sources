# CKsNotification::UpdatePinState2(_KSCAMERA_FRAMESERVER_UNIQUEID *,uchar,ulong,KSSTATE,KSSTATE,_KSFILTER *)

- ea: `0x180045900`
- end: `0x180045a32`
- name: `?UpdatePinState2@CKsNotification@@UEAAJPEAU_KSCAMERA_FRAMESERVER_UNIQUEID@@EKW4KSSTATE@@1PEAU_KSFILTER@@@Z`
- size: `306`
- prototype: `__int64 __fastcall(CKsNotification *this, struct _KSCAMERA_FRAMESERVER_UNIQUEID *, char, unsigned int, enum KSSTATE, enum KSSTATE, struct _KSFILTER *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18000b7bc`
- `0x180019cb0`
- `0x180045900`
- `0x180059298`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x180045a13`
- `ntoskrnl!KeReleaseMutex` at `0x180045a13`
- `ntoskrnl!KeWaitForSingleObject` at `0x18004596b`
- `ntoskrnl!KeWaitForSingleObject` at `0x18004596b`

## pseudocode

```c

```
