# InitializeGpuVaState

- ea: `0x1400d1c2c`
- end: `0x1400d23db`
- name: `InitializeGpuVaState`
- size: `1967`
- prototype: `__int64 __fastcall(struct VIDMM_PHYSICAL_ADAPTER *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1400d283c`

## callees

- `0x140004268`
- `0x14003dfe0`
- `0x140049678`
- `0x1400496a0`
- `0x140058710`
- `0x1400d1c2c`
- `0x1400d23e4`
- `0x1400d241c`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x1400d237f`
- `ntoskrnl!IoAllocateMdl` at `0x1400d237f`
- `ntoskrnl!MmAllocateMappingAddress` at `0x1400d230e`
- `ntoskrnl!MmAllocateMappingAddress` at `0x1400d230e`
- `watchdog!WdLogSingleEntry2` at `0x1400d232e`
- `watchdog!WdLogSingleEntry2` at `0x1400d239f`
- `watchdog!WdLogSingleEntry2` at `0x1400d232e`
- `watchdog!WdLogSingleEntry2` at `0x1400d239f`
- `watchdog!WdLogSingleEntry0` at `0x1400d1cf2`
- `watchdog!WdLogSingleEntry0` at `0x1400d1d3c`
- `watchdog!WdLogSingleEntry0` at `0x1400d1f38`
- `watchdog!WdLogSingleEntry0` at `0x1400d2183`
- `watchdog!WdLogSingleEntry0` at `0x1400d1cf2`
- `watchdog!WdLogSingleEntry0` at `0x1400d1d3c`
- `watchdog!WdLogSingleEntry0` at `0x1400d1f38`
- `watchdog!WdLogSingleEntry0` at `0x1400d2183`
- `watchdog!WdLogSingleEntry1` at `0x1400d1c89`
- `watchdog!WdLogSingleEntry1` at `0x1400d1c89`

## string_xrefs

- `0x1400d2194`: `DXGK_PAGETABLEUPDATE_CPU_VIRTUAL update mode cannot be used when                     page tables are placed in a Cpu Host Aperture segment and max page table level is 2`

## pseudocode

```c

```
