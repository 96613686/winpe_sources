# FsLibGetAddressRangesForVolumeExtents

- ea: `0x140058780`
- end: `0x140058b97`
- name: `FsLibGetAddressRangesForVolumeExtents`
- size: `1047`
- prototype: `__int64 __fastcall(const void *, __int64, _DWORD *, unsigned int, _DWORD *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400d07b4`
- `0x14011af98`

## callees

- `0x140058780`
- `0x1400b4238`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140058802`
- `ntoskrnl!DbgPrintEx` at `0x140058851`
- `ntoskrnl!DbgPrintEx` at `0x140058884`
- `ntoskrnl!DbgPrintEx` at `0x140058905`
- `ntoskrnl!DbgPrintEx` at `0x14005897d`
- `ntoskrnl!DbgPrintEx` at `0x1400589f9`
- `ntoskrnl!DbgPrintEx` at `0x140058a9a`
- `ntoskrnl!DbgPrintEx` at `0x140058ae4`
- `ntoskrnl!DbgPrintEx` at `0x140058b1c`
- `ntoskrnl!DbgPrintEx` at `0x140058b40`
- `ntoskrnl!DbgPrintEx` at `0x140058b67`
- `ntoskrnl!DbgPrintEx` at `0x140058802`
- `ntoskrnl!DbgPrintEx` at `0x140058851`
- `ntoskrnl!DbgPrintEx` at `0x140058884`
- `ntoskrnl!DbgPrintEx` at `0x140058905`
- `ntoskrnl!DbgPrintEx` at `0x14005897d`
- `ntoskrnl!DbgPrintEx` at `0x1400589f9`
- `ntoskrnl!DbgPrintEx` at `0x140058a9a`
- `ntoskrnl!DbgPrintEx` at `0x140058ae4`
- `ntoskrnl!DbgPrintEx` at `0x140058b1c`
- `ntoskrnl!DbgPrintEx` at `0x140058b40`
- `ntoskrnl!DbgPrintEx` at `0x140058b67`

## string_xrefs

- `0x1400587e9`: `FsLibGetAddressRangesForVolumeExtents: Begin DeviceObject: %p, Irp: %p, DsmBuffer: %p SizeOfDsm: 0x%x,ExtentsDescriptor: %p, SizeOfExtentsDescriptor: 0x%x, MaxRuns: 0x%x\n`
- `0x140058a89`: `FsLibGetAddressRangesForVolumeExtents: StartAddress: 0x%I64x, Length: 0x%I64x, BasePage: 0x%I64x, PageCount: 0x%I64x, ExtentsDescriptorIndex: 0x%x\n`

## pseudocode

```c

```
