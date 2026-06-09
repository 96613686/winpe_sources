# FltpCallDriver

- ea: `0x180003380`
- end: `0x180003451`
- name: `FltpCallDriver`
- size: `209`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x180002880`
- `0x180002a40`
- `0x1800231b4`
- `0x180056940`
- `0x18006e150`
- `0x18006ee20`
- `0x18006fb60`
- `0x180070c80`
- `0x180076240`
- `0x180076fd0`
- `0x1800784c0`

## callees

- `0x180003380`
- `0x180009f20`

## import_xrefs

- `ntoskrnl!IoGetStackLimits` at `0x1800033ab`
- `ntoskrnl!IoGetStackLimits` at `0x1800033ab`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x180003415`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x180003415`
- `ntoskrnl!IofCallDriver` at `0x1800033cf`
- `ntoskrnl!IofCallDriver` at `0x1800033cf`

## pseudocode

```c

```
