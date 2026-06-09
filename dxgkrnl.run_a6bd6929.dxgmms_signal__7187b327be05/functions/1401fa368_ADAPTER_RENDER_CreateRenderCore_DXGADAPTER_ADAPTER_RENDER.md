# ADAPTER_RENDER::CreateRenderCore(DXGADAPTER *,ADAPTER_RENDER * *)

- ea: `0x1401fa368`
- end: `0x1401fad1f`
- name: `?CreateRenderCore@ADAPTER_RENDER@@SAJPEAVDXGADAPTER@@PEAPEAV1@@Z`
- size: `2487`
- prototype: `__int64 __fastcall(struct DXGADAPTER *, struct ADAPTER_RENDER **)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1401c6fe0`

## callees

- `0x14001b9c0`
- `0x14002e2e0`
- `0x14006772c`
- `0x1401f9b50`
- `0x1401fa368`
- `0x1401fad28`
- `0x1401fc90c`

## import_xrefs

- `watchdog!WdLogSingleEntry4` at `0x1401fa834`
- `watchdog!WdLogSingleEntry4` at `0x1401fa834`
- `watchdog!WdLogSingleEntry2` at `0x1401fac9c`
- `watchdog!WdLogSingleEntry2` at `0x1401fac9c`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401fa532`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401fabb2`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401fa532`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401fabb2`
- `watchdog!WdLogSingleEntry0` at `0x1401fa397`
- `watchdog!WdLogSingleEntry0` at `0x1401fa3e2`
- `watchdog!WdLogSingleEntry0` at `0x1401fa674`
- `watchdog!WdLogSingleEntry0` at `0x1401fa6b0`
- `watchdog!WdLogSingleEntry0` at `0x1401fa74d`
- `watchdog!WdLogSingleEntry0` at `0x1401fa79c`
- `watchdog!WdLogSingleEntry0` at `0x1401fa90c`
- `watchdog!WdLogSingleEntry0` at `0x1401fa994`
- `watchdog!WdLogSingleEntry0` at `0x1401fa9dc`
- `watchdog!WdLogSingleEntry0` at `0x1401faa4a`
- `watchdog!WdLogSingleEntry0` at `0x1401faa6c`
- `watchdog!WdLogSingleEntry0` at `0x1401fabd7`
- `watchdog!WdLogSingleEntry0` at `0x1401fac2c`
- `watchdog!WdLogSingleEntry0` at `0x1401fa397`
- `watchdog!WdLogSingleEntry0` at `0x1401fa3e2`
- `watchdog!WdLogSingleEntry0` at `0x1401fa674`
- `watchdog!WdLogSingleEntry0` at `0x1401fa6b0`
- `watchdog!WdLogSingleEntry0` at `0x1401fa74d`
- `watchdog!WdLogSingleEntry0` at `0x1401fa79c`
- `watchdog!WdLogSingleEntry0` at `0x1401fa90c`
- `watchdog!WdLogSingleEntry0` at `0x1401fa994`
- `watchdog!WdLogSingleEntry0` at `0x1401fa9dc`
- `watchdog!WdLogSingleEntry0` at `0x1401faa4a`
- `watchdog!WdLogSingleEntry0` at `0x1401faa6c`
- `watchdog!WdLogSingleEntry0` at `0x1401fabd7`
- `watchdog!WdLogSingleEntry0` at `0x1401fac2c`
- `watchdog!WdLogSingleEntry1` at `0x1401fa711`
- `watchdog!WdLogSingleEntry1` at `0x1401fa7ea`
- `watchdog!WdLogSingleEntry1` at `0x1401fa860`
- `watchdog!WdLogSingleEntry1` at `0x1401fa884`
- `watchdog!WdLogSingleEntry1` at `0x1401fa952`
- `watchdog!WdLogSingleEntry1` at `0x1401facc6`
- `watchdog!WdLogSingleEntry1` at `0x1401fa711`
- `watchdog!WdLogSingleEntry1` at `0x1401fa7ea`
- `watchdog!WdLogSingleEntry1` at `0x1401fa860`
- `watchdog!WdLogSingleEntry1` at `0x1401fa884`
- `watchdog!WdLogSingleEntry1` at `0x1401fa952`
- `watchdog!WdLogSingleEntry1` at `0x1401facc6`

## string_xrefs

- `0x1401faa7d`: `Create, Update, Flip and DestroyOverlay should all be supplied if any one of them is`
- `0x1401fa6c1`: `Miniport did not provide RenderKm function but reported PresentationCaps.SupportKernelModeCommandBuffer cap`
- `0x1401fa75e`: `Miniport set the NoCacheCoherentApertureMemory cap on non-ARM architecture`
- `0x1401fa9ed`: `Driver reports WDDM 2.4 driver with IoMmuSecureMode support, but does not support Begin/EndExclusiveAccess DDIs.`

## pseudocode

```c

```
