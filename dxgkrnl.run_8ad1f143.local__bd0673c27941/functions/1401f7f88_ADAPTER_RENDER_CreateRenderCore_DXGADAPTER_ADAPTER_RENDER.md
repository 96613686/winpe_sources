# ADAPTER_RENDER::CreateRenderCore(DXGADAPTER *,ADAPTER_RENDER * *)

- ea: `0x1401f7f88`
- end: `0x1401f893f`
- name: `?CreateRenderCore@ADAPTER_RENDER@@SAJPEAVDXGADAPTER@@PEAPEAV1@@Z`
- size: `2487`
- prototype: `__int64 __fastcall(struct DXGADAPTER *, struct ADAPTER_RENDER **)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1401c43e0`

## callees

- `0x14001b890`
- `0x14002e110`
- `0x14006730c`
- `0x1401f7770`
- `0x1401f7f88`
- `0x1401f8948`
- `0x1401fa52c`

## import_xrefs

- `watchdog!WdLogSingleEntry4` at `0x1401f8454`
- `watchdog!WdLogSingleEntry4` at `0x1401f8454`
- `watchdog!WdLogSingleEntry2` at `0x1401f88bc`
- `watchdog!WdLogSingleEntry2` at `0x1401f88bc`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401f8152`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401f87d2`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401f8152`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401f87d2`
- `watchdog!WdLogSingleEntry0` at `0x1401f7fb7`
- `watchdog!WdLogSingleEntry0` at `0x1401f8002`
- `watchdog!WdLogSingleEntry0` at `0x1401f8294`
- `watchdog!WdLogSingleEntry0` at `0x1401f82d0`
- `watchdog!WdLogSingleEntry0` at `0x1401f836d`
- `watchdog!WdLogSingleEntry0` at `0x1401f83bc`
- `watchdog!WdLogSingleEntry0` at `0x1401f852c`
- `watchdog!WdLogSingleEntry0` at `0x1401f85b4`
- `watchdog!WdLogSingleEntry0` at `0x1401f85fc`
- `watchdog!WdLogSingleEntry0` at `0x1401f866a`
- `watchdog!WdLogSingleEntry0` at `0x1401f868c`
- `watchdog!WdLogSingleEntry0` at `0x1401f87f7`
- `watchdog!WdLogSingleEntry0` at `0x1401f884c`
- `watchdog!WdLogSingleEntry0` at `0x1401f7fb7`
- `watchdog!WdLogSingleEntry0` at `0x1401f8002`
- `watchdog!WdLogSingleEntry0` at `0x1401f8294`
- `watchdog!WdLogSingleEntry0` at `0x1401f82d0`
- `watchdog!WdLogSingleEntry0` at `0x1401f836d`
- `watchdog!WdLogSingleEntry0` at `0x1401f83bc`
- `watchdog!WdLogSingleEntry0` at `0x1401f852c`
- `watchdog!WdLogSingleEntry0` at `0x1401f85b4`
- `watchdog!WdLogSingleEntry0` at `0x1401f85fc`
- `watchdog!WdLogSingleEntry0` at `0x1401f866a`
- `watchdog!WdLogSingleEntry0` at `0x1401f868c`
- `watchdog!WdLogSingleEntry0` at `0x1401f87f7`
- `watchdog!WdLogSingleEntry0` at `0x1401f884c`
- `watchdog!WdLogSingleEntry1` at `0x1401f8331`
- `watchdog!WdLogSingleEntry1` at `0x1401f840a`
- `watchdog!WdLogSingleEntry1` at `0x1401f8480`
- `watchdog!WdLogSingleEntry1` at `0x1401f84a4`
- `watchdog!WdLogSingleEntry1` at `0x1401f8572`
- `watchdog!WdLogSingleEntry1` at `0x1401f88e6`
- `watchdog!WdLogSingleEntry1` at `0x1401f8331`
- `watchdog!WdLogSingleEntry1` at `0x1401f840a`
- `watchdog!WdLogSingleEntry1` at `0x1401f8480`
- `watchdog!WdLogSingleEntry1` at `0x1401f84a4`
- `watchdog!WdLogSingleEntry1` at `0x1401f8572`
- `watchdog!WdLogSingleEntry1` at `0x1401f88e6`

## string_xrefs

- `0x1401f869d`: `Create, Update, Flip and DestroyOverlay should all be supplied if any one of them is`
- `0x1401f82e1`: `Miniport did not provide RenderKm function but reported PresentationCaps.SupportKernelModeCommandBuffer cap`
- `0x1401f837e`: `Miniport set the NoCacheCoherentApertureMemory cap on non-ARM architecture`
- `0x1401f860d`: `Driver reports WDDM 2.4 driver with IoMmuSecureMode support, but does not support Begin/EndExclusiveAccess DDIs.`

## pseudocode

```c

```
