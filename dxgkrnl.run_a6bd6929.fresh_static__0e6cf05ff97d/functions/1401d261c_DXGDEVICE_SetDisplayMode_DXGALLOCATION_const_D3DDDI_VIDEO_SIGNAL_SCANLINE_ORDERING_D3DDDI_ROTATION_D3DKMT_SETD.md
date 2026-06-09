# DXGDEVICE::SetDisplayMode(DXGALLOCATION const *,_D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING,_D3DDDI_ROTATION,_D3DKMT_SETDISPLAYMODE_FLAGS,uint *,_DXGK_DISPLAY_SCENARIO_CONTEXT *)

- ea: `0x1401d261c`
- end: `0x1401d31b0`
- name: `?SetDisplayMode@DXGDEVICE@@QEAAJPEBVDXGALLOCATION@@W4_D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING@@W4_D3DDDI_ROTATION@@U_D3DKMT_SETDISPLAYMODE_FLAGS@@PEAIPEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@@Z`
- size: `2964`
- prototype: `__int64 __usercall@<rax>(DXGDEVICE *__hidden this@<rcx>, const struct DXGALLOCATION *@<rdx>, enum _D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING@<r8d>, enum _D3DDDI_ROTATION@<r9d>, struct _D3DKMT_SETDISPLAYMODE_FLAGS, unsigned int *, struct _DXGK_DISPLAY_SCENARIO_CONTEXT *)`
- caller_count: `1`
- callee_count: `34`
- tags: `broker_com_uri`

## callers

- `0x14018f0a0`

## callees

- `0x140012540`
- `0x14001b9c0`
- `0x14001bd80`
- `0x140021e50`
- `0x140044dd4`
- `0x140047b60`
- `0x14004d4a4`
- `0x14004f5ec`
- `0x14004f7e4`
- `0x140053558`
- `0x140053634`
- `0x14006f880`
- `0x1400715e0`
- `0x1400716dc`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a1000`
- `0x1401901d4`
- `0x1401952f0`
- `0x1401b7b98`
- `0x1401d261c`
- `0x1401dbb04`
- `0x14026ae2c`
- `0x1402cde88`
- `0x1402ce1c8`
- `0x1402d41ec`
- `0x1402d4364`
- `0x1402df5a8`
- `0x14032a5c4`
- `0x140339acc`
- `0x1403833dc`
- `0x140393f58`
- `0x1403cb370`
- `0x1403ebee0`

## import_xrefs

- `watchdog!WdLogSingleEntry2` at `0x1401d2bbd`
- `watchdog!WdLogSingleEntry2` at `0x1401d2bbd`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401d28cb`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401d28cb`
- `watchdog!WdLogSingleEntry3` at `0x1401d2886`
- `watchdog!WdLogSingleEntry3` at `0x1401d2a9a`
- `watchdog!WdLogSingleEntry3` at `0x1401d2886`
- `watchdog!WdLogSingleEntry3` at `0x1401d2a9a`
- `watchdog!WdLogSingleEntry0` at `0x1401d269e`
- `watchdog!WdLogSingleEntry0` at `0x1401d2719`
- `watchdog!WdLogSingleEntry0` at `0x1401d269e`
- `watchdog!WdLogSingleEntry0` at `0x1401d2719`
- `watchdog!WdLogSingleEntry5` at `0x1401d2800`
- `watchdog!WdLogSingleEntry5` at `0x1401d2a15`
- `watchdog!WdLogSingleEntry5` at `0x1401d2c7e`
- `watchdog!WdLogSingleEntry5` at `0x1401d2d55`
- `watchdog!WdLogSingleEntry5` at `0x1401d2db9`
- `watchdog!WdLogSingleEntry5` at `0x1401d2e00`
- `watchdog!WdLogSingleEntry5` at `0x1401d2e46`
- `watchdog!WdLogSingleEntry5` at `0x1401d2ff4`
- `watchdog!WdLogSingleEntry5` at `0x1401d3087`
- `watchdog!WdLogSingleEntry5` at `0x1401d2800`
- `watchdog!WdLogSingleEntry5` at `0x1401d2a15`
- `watchdog!WdLogSingleEntry5` at `0x1401d2c7e`
- `watchdog!WdLogSingleEntry5` at `0x1401d2d55`
- `watchdog!WdLogSingleEntry5` at `0x1401d2db9`
- `watchdog!WdLogSingleEntry5` at `0x1401d2e00`
- `watchdog!WdLogSingleEntry5` at `0x1401d2e46`
- `watchdog!WdLogSingleEntry5` at `0x1401d2ff4`
- `watchdog!WdLogSingleEntry5` at `0x1401d3087`
- `watchdog!WdLogSingleEntry1` at `0x1401d293a`
- `watchdog!WdLogSingleEntry1` at `0x1401d3136`
- `watchdog!WdLogSingleEntry1` at `0x1401d293a`
- `watchdog!WdLogSingleEntry1` at `0x1401d3136`

## string_xrefs

- `0x1401d2e55`: `0x%I64x failed to create functional VidPN based on the active VidPN with source 0x%I64x enabled with %I64d x %I64d x %I64d.`
- `0x1401d3147`: `Failed call to DmmCacheDisplayModeChangeRequest (status = 0x%I64x)`
- `0x1401d3005`: `NTSTATUS=0x%I64x DXGADAPTER 0x%I64x DXGADAPTER::CommitVidPn failed VidPnSourceId 0x%I64x DXGALLOCATION 0x%I64x 0x%I64x 0x%I64x`

## pseudocode

```c

```
