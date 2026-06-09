# PollDisplayChildrenForAdapter(_D3DKMT_POLLDISPLAYCHILDREN const *,uint,_DXGK_DISPLAY_SCENARIO_CONTEXT *)

- ea: `0x1403eefcc`
- end: `0x1403ef4d3`
- name: `?PollDisplayChildrenForAdapter@@YAJPEBU_D3DKMT_POLLDISPLAYCHILDREN@@IPEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@@Z`
- size: `1287`
- prototype: `__int64 __fastcall(const struct _D3DKMT_POLLDISPLAYCHILDREN *, unsigned int, struct _DXGK_DISPLAY_SCENARIO_CONTEXT *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1403eecb0`

## callees

- `0x1400157bc`
- `0x140015940`
- `0x14001b9c0`
- `0x14001ca40`
- `0x14001f258`
- `0x14002ddf0`
- `0x14002ee60`
- `0x1400a0bd0`
- `0x1402a369c`
- `0x1402caa88`
- `0x1402f3234`
- `0x1402f5684`
- `0x14032a5c4`
- `0x1403eefcc`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1403ef016`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403ef048`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403ef016`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403ef048`
- `ntoskrnl!ObfDereferenceObject` at `0x1403ef27b`
- `ntoskrnl!ObfDereferenceObject` at `0x1403ef2b0`
- `ntoskrnl!ObfDereferenceObject` at `0x1403ef27b`
- `ntoskrnl!ObfDereferenceObject` at `0x1403ef2b0`
- `ntoskrnl!ObfReferenceObject` at `0x1403ef11b`
- `ntoskrnl!ObfReferenceObject` at `0x1403ef11b`
- `ntoskrnl!ExGetPreviousMode` at `0x1403ef2d6`
- `ntoskrnl!ExGetPreviousMode` at `0x1403ef2d6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403ef2fa`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403ef2fa`
- `watchdog!WdLogSingleEntry2` at `0x1403ef032`
- `watchdog!WdLogSingleEntry2` at `0x1403ef032`
- `watchdog!WdLogSingleEntry3` at `0x1403ef0c6`
- `watchdog!WdLogSingleEntry3` at `0x1403ef0c6`
- `watchdog!WdLogSingleEntry0` at `0x1403ef16b`
- `watchdog!WdLogSingleEntry0` at `0x1403ef314`
- `watchdog!WdLogSingleEntry0` at `0x1403ef16b`
- `watchdog!WdLogSingleEntry0` at `0x1403ef314`
- `watchdog!WdLogSingleEntry1` at `0x1403ef1b7`
- `watchdog!WdLogSingleEntry1` at `0x1403ef226`
- `watchdog!WdLogSingleEntry1` at `0x1403ef367`
- `watchdog!WdLogSingleEntry1` at `0x1403ef3f2`
- `watchdog!WdLogSingleEntry1` at `0x1403ef449`
- `watchdog!WdLogSingleEntry1` at `0x1403ef1b7`
- `watchdog!WdLogSingleEntry1` at `0x1403ef226`
- `watchdog!WdLogSingleEntry1` at `0x1403ef367`
- `watchdog!WdLogSingleEntry1` at `0x1403ef3f2`
- `watchdog!WdLogSingleEntry1` at `0x1403ef449`

## string_xrefs

- `0x1403ef467`: `Failed in acquiring adapter core access lock, (Status == 0x%I64x)!`

## pseudocode

```c

```
