# WFDDeviceHandleProvisionDiscoveryRequestSendCompletion(_WFD_ROLE *,ulong,_DOT11_PROVISION_DISCOVERY_REQUEST_SEND_COMPLETE_PARAMETERS *)

- ea: `0x140081b44`
- end: `0x140081e29`
- name: `?WFDDeviceHandleProvisionDiscoveryRequestSendCompletion@@YAXPEAU_WFD_ROLE@@KPEAU_DOT11_PROVISION_DISCOVERY_REQUEST_SEND_COMPLETE_PARAMETERS@@@Z`
- size: `741`
- prototype: `void(struct _WFD_ROLE *, unsigned int, struct _DOT11_PROVISION_DISCOVERY_REQUEST_SEND_COMPLETE_PARAMETERS *)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x14007c5b0`

## callees

- `0x14000d22c`
- `0x140020dc0`
- `0x140022f08`
- `0x14003ae2c`
- `0x14007f5cc`
- `0x140081b44`
- `0x140089588`
- `0x14008a1cc`
- `0x14008a780`
- `0x14008ae64`
- `0x14008af58`
- `0x14008c0e8`
- `0x14008c60c`
- `0x14009a3d0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140081c35`
- `ntoskrnl!KeReleaseSpinLock` at `0x140081dfe`
- `ntoskrnl!KeReleaseSpinLock` at `0x140081c35`
- `ntoskrnl!KeReleaseSpinLock` at `0x140081dfe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140081bd3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140081bd3`

## pseudocode

```c

```
