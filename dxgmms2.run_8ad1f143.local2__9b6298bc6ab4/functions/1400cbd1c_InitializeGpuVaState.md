# InitializeGpuVaState

- ea: `0x1400cbd1c`
- end: `0x1400cc54a`
- name: `InitializeGpuVaState`
- size: `2094`
- prototype: `__int64 __fastcall(struct VIDMM_PHYSICAL_ADAPTER *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x1400cc9ac`

## callees

- `0x1400045ec`
- `0x14003f664`
- `0x140047e0c`
- `0x140048090`
- `0x140049018`
- `0x140057e40`
- `0x1400cbd1c`
- `0x1400cc550`
- `0x1400cc588`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x1400cc4ee`
- `ntoskrnl!IoAllocateMdl` at `0x1400cc4ee`
- `ntoskrnl!MmAllocateMappingAddress` at `0x1400cc47d`
- `ntoskrnl!MmAllocateMappingAddress` at `0x1400cc47d`
- `watchdog!WdLogSingleEntry2` at `0x1400cc49d`
- `watchdog!WdLogSingleEntry2` at `0x1400cc50e`
- `watchdog!WdLogSingleEntry2` at `0x1400cc49d`
- `watchdog!WdLogSingleEntry2` at `0x1400cc50e`
- `watchdog!WdLogSingleEntry0` at `0x1400cbdf3`
- `watchdog!WdLogSingleEntry0` at `0x1400cbe42`
- `watchdog!WdLogSingleEntry0` at `0x1400cc051`
- `watchdog!WdLogSingleEntry0` at `0x1400cc305`
- `watchdog!WdLogSingleEntry0` at `0x1400cbdf3`
- `watchdog!WdLogSingleEntry0` at `0x1400cbe42`
- `watchdog!WdLogSingleEntry0` at `0x1400cc051`
- `watchdog!WdLogSingleEntry0` at `0x1400cc305`
- `watchdog!WdLogSingleEntry1` at `0x1400cbd79`
- `watchdog!WdLogSingleEntry1` at `0x1400cbd79`

## string_xrefs

- `0x1400cc316`: `DXGK_PAGETABLEUPDATE_CPU_VIRTUAL update mode cannot be used when                     page tables are placed in a Cpu Host Aperture segment and max page table level is 2`

## pseudocode

```c

```
