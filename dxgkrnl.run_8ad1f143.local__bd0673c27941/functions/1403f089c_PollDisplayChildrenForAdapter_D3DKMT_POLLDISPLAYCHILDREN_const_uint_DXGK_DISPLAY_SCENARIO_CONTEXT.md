# PollDisplayChildrenForAdapter(_D3DKMT_POLLDISPLAYCHILDREN const *,uint,_DXGK_DISPLAY_SCENARIO_CONTEXT *)

- ea: `0x1403f089c`
- end: `0x1403f0da3`
- name: `?PollDisplayChildrenForAdapter@@YAJPEBU_D3DKMT_POLLDISPLAYCHILDREN@@IPEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@@Z`
- size: `1287`
- prototype: `__int64 __fastcall(const struct _D3DKMT_POLLDISPLAYCHILDREN *, unsigned int, struct _DXGK_DISPLAY_SCENARIO_CONTEXT *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1403f0580`

## callees

- `0x1400155fc`
- `0x140015780`
- `0x14001b890`
- `0x14001c910`
- `0x14001f088`
- `0x14002dc20`
- `0x14002ec90`
- `0x1400a0100`
- `0x14029ccec`
- `0x1402c4038`
- `0x1402ec784`
- `0x1402eebd4`
- `0x140323854`
- `0x1403f089c`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1403f08e6`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403f0918`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403f08e6`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403f0918`
- `ntoskrnl!ObfDereferenceObject` at `0x1403f0b4b`
- `ntoskrnl!ObfDereferenceObject` at `0x1403f0b80`
- `ntoskrnl!ObfDereferenceObject` at `0x1403f0b4b`
- `ntoskrnl!ObfDereferenceObject` at `0x1403f0b80`
- `ntoskrnl!ObfReferenceObject` at `0x1403f09eb`
- `ntoskrnl!ObfReferenceObject` at `0x1403f09eb`
- `ntoskrnl!ExGetPreviousMode` at `0x1403f0ba6`
- `ntoskrnl!ExGetPreviousMode` at `0x1403f0ba6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403f0bca`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403f0bca`
- `watchdog!WdLogSingleEntry2` at `0x1403f0902`
- `watchdog!WdLogSingleEntry2` at `0x1403f0902`
- `watchdog!WdLogSingleEntry3` at `0x1403f0996`
- `watchdog!WdLogSingleEntry3` at `0x1403f0996`
- `watchdog!WdLogSingleEntry0` at `0x1403f0a3b`
- `watchdog!WdLogSingleEntry0` at `0x1403f0be4`
- `watchdog!WdLogSingleEntry0` at `0x1403f0a3b`
- `watchdog!WdLogSingleEntry0` at `0x1403f0be4`
- `watchdog!WdLogSingleEntry1` at `0x1403f0a87`
- `watchdog!WdLogSingleEntry1` at `0x1403f0af6`
- `watchdog!WdLogSingleEntry1` at `0x1403f0c37`
- `watchdog!WdLogSingleEntry1` at `0x1403f0cc2`
- `watchdog!WdLogSingleEntry1` at `0x1403f0d19`
- `watchdog!WdLogSingleEntry1` at `0x1403f0a87`
- `watchdog!WdLogSingleEntry1` at `0x1403f0af6`
- `watchdog!WdLogSingleEntry1` at `0x1403f0c37`
- `watchdog!WdLogSingleEntry1` at `0x1403f0cc2`
- `watchdog!WdLogSingleEntry1` at `0x1403f0d19`

## string_xrefs

- `0x1403f0d37`: `Failed in acquiring adapter core access lock, (Status == 0x%I64x)!`

## pseudocode

```c

```
