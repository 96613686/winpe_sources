# VIDMM_DIRTY_BITPLANE::CreateVidMmDirtyBitplane(VIDMM_GLOBAL *,DXGK_DIRTY_BITPLANE *,unsigned __int64,VIDMM_DIRTY_BITPLANE * *)

- ea: `0x140049a90`
- end: `0x140049f06`
- name: `?CreateVidMmDirtyBitplane@VIDMM_DIRTY_BITPLANE@@SAJPEAVVIDMM_GLOBAL@@PEAVDXGK_DIRTY_BITPLANE@@_KPEAPEAV1@@Z`
- size: `1142`
- prototype: `__int64 __fastcall(struct VIDMM_GLOBAL *this, PRTL_BITMAP BitMapHeader, unsigned __int64, struct VIDMM_DIRTY_BITPLANE **)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1400b3680`

## callees

- `0x1400037a0`
- `0x140030ae0`
- `0x140031178`
- `0x1400391bc`
- `0x140049a90`
- `0x140058ac0`
- `0x1400aae14`
- `0x1400c3064`
- `0x1400dfe1c`
- `0x1400e9900`
- `0x1400ea1dc`
- `0x140103068`

## import_xrefs

- `ntoskrnl!RtlNumberOfSetBitsInRange` at `0x140049ba9`
- `ntoskrnl!RtlNumberOfSetBitsInRange` at `0x140049ba9`
- `ntoskrnl!RtlFindNextForwardRunClear` at `0x140049c6b`
- `ntoskrnl!RtlFindNextForwardRunClear` at `0x140049c6b`
- `ntoskrnl!RtlTestBit` at `0x140049c40`
- `ntoskrnl!RtlTestBit` at `0x140049c40`
- `watchdog!WdLogSingleEntry0` at `0x140049c0c`
- `watchdog!WdLogSingleEntry0` at `0x140049d14`
- `watchdog!WdLogSingleEntry0` at `0x140049d71`
- `watchdog!WdLogSingleEntry0` at `0x140049df6`
- `watchdog!WdLogSingleEntry0` at `0x140049e6a`
- `watchdog!WdLogSingleEntry0` at `0x140049ecd`
- `watchdog!WdLogSingleEntry0` at `0x140049c0c`
- `watchdog!WdLogSingleEntry0` at `0x140049d14`
- `watchdog!WdLogSingleEntry0` at `0x140049d71`
- `watchdog!WdLogSingleEntry0` at `0x140049df6`
- `watchdog!WdLogSingleEntry0` at `0x140049e6a`
- `watchdog!WdLogSingleEntry0` at `0x140049ecd`
- `watchdog!WdLogSingleEntry1` at `0x140049ada`
- `watchdog!WdLogSingleEntry1` at `0x140049ada`

## pseudocode

```c

```
