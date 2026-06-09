# DXG_HOST_VIRTUALGPU_VMBUS::VmBusCreateAllocation(DXGADAPTER_VMBUS_PACKET *)

- ea: `0x1403f80d0`
- end: `0x1403f8bc1`
- name: `?VmBusCreateAllocation@DXG_HOST_VIRTUALGPU_VMBUS@@SAEPEAUDXGADAPTER_VMBUS_PACKET@@@Z`
- size: `2801`
- prototype: `unsigned __int8 __fastcall(struct DXGADAPTER_VMBUS_PACKET *)`
- caller_count: `0`
- callee_count: `26`
- tags: `authz_impersonation`

## callees

- `0x140009030`
- `0x14000d7d0`
- `0x140015970`
- `0x140017fb8`
- `0x14001b890`
- `0x14001bd70`
- `0x14001c660`
- `0x14001d070`
- `0x14001f120`
- `0x14002ed70`
- `0x14003bd5c`
- `0x14003c1e8`
- `0x140046914`
- `0x1400491a8`
- `0x14004ce64`
- `0x1400530e8`
- `0x1400a0100`
- `0x1400a0240`
- `0x1400a0540`
- `0x14027df58`
- `0x140323854`
- `0x140327c10`
- `0x140329000`
- `0x140340858`
- `0x1403760ec`
- `0x1403f80d0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403f8743`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403f8a9d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403f8743`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403f8a9d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403f8a91`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403f8a91`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1403f8737`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1403f8737`
- `watchdog!WdLogSingleEntry0` at `0x1403f812e`
- `watchdog!WdLogSingleEntry0` at `0x1403f8158`
- `watchdog!WdLogSingleEntry0` at `0x1403f81ad`
- `watchdog!WdLogSingleEntry0` at `0x1403f81dc`
- `watchdog!WdLogSingleEntry0` at `0x1403f8207`
- `watchdog!WdLogSingleEntry0` at `0x1403f824d`
- `watchdog!WdLogSingleEntry0` at `0x1403f82ac`
- `watchdog!WdLogSingleEntry0` at `0x1403f8307`
- `watchdog!WdLogSingleEntry0` at `0x1403f8384`
- `watchdog!WdLogSingleEntry0` at `0x1403f8433`
- `watchdog!WdLogSingleEntry0` at `0x1403f8510`
- `watchdog!WdLogSingleEntry0` at `0x1403f856e`
- `watchdog!WdLogSingleEntry0` at `0x1403f85e4`
- `watchdog!WdLogSingleEntry0` at `0x1403f86ce`
- `watchdog!WdLogSingleEntry0` at `0x1403f8b55`
- `watchdog!WdLogSingleEntry0` at `0x1403f812e`
- `watchdog!WdLogSingleEntry0` at `0x1403f8158`
- `watchdog!WdLogSingleEntry0` at `0x1403f81ad`
- `watchdog!WdLogSingleEntry0` at `0x1403f81dc`
- `watchdog!WdLogSingleEntry0` at `0x1403f8207`
- `watchdog!WdLogSingleEntry0` at `0x1403f824d`
- `watchdog!WdLogSingleEntry0` at `0x1403f82ac`
- `watchdog!WdLogSingleEntry0` at `0x1403f8307`
- `watchdog!WdLogSingleEntry0` at `0x1403f8384`
- `watchdog!WdLogSingleEntry0` at `0x1403f8433`
- `watchdog!WdLogSingleEntry0` at `0x1403f8510`
- `watchdog!WdLogSingleEntry0` at `0x1403f856e`
- `watchdog!WdLogSingleEntry0` at `0x1403f85e4`
- `watchdog!WdLogSingleEntry0` at `0x1403f86ce`
- `watchdog!WdLogSingleEntry0` at `0x1403f8b55`
- `watchdog!WdLogSingleEntry1` at `0x1403f89cb`
- `watchdog!WdLogSingleEntry1` at `0x1403f8aea`
- `watchdog!WdLogSingleEntry1` at `0x1403f89cb`
- `watchdog!WdLogSingleEntry1` at `0x1403f8aea`

## string_xrefs

- `0x1403f8169`: `OpenCrossAdapter is not supported`
- `0x1403f8afb`: `Failed to create allocation: 0x%I64x`
- `0x1403f89e8`: `Failed to make staging allocation resident. Returning 0x%I64x`

## pseudocode

```c

```
