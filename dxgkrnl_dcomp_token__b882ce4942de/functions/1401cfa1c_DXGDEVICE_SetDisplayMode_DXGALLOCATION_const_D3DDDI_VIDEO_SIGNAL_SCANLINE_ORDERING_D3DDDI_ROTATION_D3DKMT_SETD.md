# DXGDEVICE::SetDisplayMode(DXGALLOCATION const *,_D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING,_D3DDDI_ROTATION,_D3DKMT_SETDISPLAYMODE_FLAGS,uint *,_DXGK_DISPLAY_SCENARIO_CONTEXT *)

- ea: `0x1401cfa1c`
- end: `0x1401d05b0`
- name: `?SetDisplayMode@DXGDEVICE@@QEAAJPEBVDXGALLOCATION@@W4_D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING@@W4_D3DDDI_ROTATION@@U_D3DKMT_SETDISPLAYMODE_FLAGS@@PEAIPEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@@Z`
- size: `2964`
- prototype: `__int64 __usercall@<rax>(DXGDEVICE *__hidden this@<rcx>, const struct DXGALLOCATION *@<rdx>, enum _D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING@<r8d>, enum _D3DDDI_ROTATION@<r9d>, struct _D3DKMT_SETDISPLAYMODE_FLAGS, unsigned int *, struct _DXGK_DISPLAY_SCENARIO_CONTEXT *)`
- caller_count: `1`
- callee_count: `34`
- tags: `broker_com_uri`

## callers

- `0x14018b0a0`

## callees

- `0x140012380`
- `0x14001b890`
- `0x14001bc50`
- `0x140021c80`
- `0x140044b74`
- `0x140047960`
- `0x14004d2a4`
- `0x14004f3ec`
- `0x14004f5e4`
- `0x140053308`
- `0x140053454`
- `0x14006f2d0`
- `0x140071030`
- `0x14007112c`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0540`
- `0x14018c1d4`
- `0x1401912f0`
- `0x1401b4f98`
- `0x1401cfa1c`
- `0x1401d9798`
- `0x14026586c`
- `0x1402c7438`
- `0x1402c7778`
- `0x1402cd744`
- `0x1402cd8bc`
- `0x1402d8af8`
- `0x140323854`
- `0x1403330ac`
- `0x140340858`
- `0x14037ba5c`
- `0x1403cb2d4`
- `0x1403eba20`

## import_xrefs

- `watchdog!WdLogSingleEntry2` at `0x1401cffbd`
- `watchdog!WdLogSingleEntry2` at `0x1401cffbd`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401cfccb`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401cfccb`
- `watchdog!WdLogSingleEntry3` at `0x1401cfc86`
- `watchdog!WdLogSingleEntry3` at `0x1401cfe9a`
- `watchdog!WdLogSingleEntry3` at `0x1401cfc86`
- `watchdog!WdLogSingleEntry3` at `0x1401cfe9a`
- `watchdog!WdLogSingleEntry0` at `0x1401cfa9e`
- `watchdog!WdLogSingleEntry0` at `0x1401cfb19`
- `watchdog!WdLogSingleEntry0` at `0x1401cfa9e`
- `watchdog!WdLogSingleEntry0` at `0x1401cfb19`
- `watchdog!WdLogSingleEntry5` at `0x1401cfc00`
- `watchdog!WdLogSingleEntry5` at `0x1401cfe15`
- `watchdog!WdLogSingleEntry5` at `0x1401d007e`
- `watchdog!WdLogSingleEntry5` at `0x1401d0155`
- `watchdog!WdLogSingleEntry5` at `0x1401d01b9`
- `watchdog!WdLogSingleEntry5` at `0x1401d0200`
- `watchdog!WdLogSingleEntry5` at `0x1401d0246`
- `watchdog!WdLogSingleEntry5` at `0x1401d03f4`
- `watchdog!WdLogSingleEntry5` at `0x1401d0487`
- `watchdog!WdLogSingleEntry5` at `0x1401cfc00`
- `watchdog!WdLogSingleEntry5` at `0x1401cfe15`
- `watchdog!WdLogSingleEntry5` at `0x1401d007e`
- `watchdog!WdLogSingleEntry5` at `0x1401d0155`
- `watchdog!WdLogSingleEntry5` at `0x1401d01b9`
- `watchdog!WdLogSingleEntry5` at `0x1401d0200`
- `watchdog!WdLogSingleEntry5` at `0x1401d0246`
- `watchdog!WdLogSingleEntry5` at `0x1401d03f4`
- `watchdog!WdLogSingleEntry5` at `0x1401d0487`
- `watchdog!WdLogSingleEntry1` at `0x1401cfd3a`
- `watchdog!WdLogSingleEntry1` at `0x1401d0536`
- `watchdog!WdLogSingleEntry1` at `0x1401cfd3a`
- `watchdog!WdLogSingleEntry1` at `0x1401d0536`

## string_xrefs

- `0x1401d0255`: `0x%I64x failed to create functional VidPN based on the active VidPN with source 0x%I64x enabled with %I64d x %I64d x %I64d.`
- `0x1401d0547`: `Failed call to DmmCacheDisplayModeChangeRequest (status = 0x%I64x)`
- `0x1401d0405`: `NTSTATUS=0x%I64x DXGADAPTER 0x%I64x DXGADAPTER::CommitVidPn failed VidPnSourceId 0x%I64x DXGALLOCATION 0x%I64x 0x%I64x 0x%I64x`

## pseudocode

```c

```
