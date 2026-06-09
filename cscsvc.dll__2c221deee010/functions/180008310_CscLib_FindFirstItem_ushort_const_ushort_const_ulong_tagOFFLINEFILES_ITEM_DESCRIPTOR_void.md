# CscLib_FindFirstItem(ushort const *,ushort const *,ulong,tagOFFLINEFILES_ITEM_DESCRIPTOR *,void * *)

- ea: `0x180008310`
- end: `0x180008977`
- name: `?CscLib_FindFirstItem@@YAJPEBG0KPEAUtagOFFLINEFILES_ITEM_DESCRIPTOR@@PEAPEAX@Z`
- size: `1639`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, PCWSTR@<rdx>, unsigned int@<r8d>, struct tagOFFLINEFILES_ITEM_DESCRIPTOR *@<r9>, void **)`
- caller_count: `8`
- callee_count: `17`
- tags: `loader_planting`

## callers

- `0x180008100`
- `0x180008f40`
- `0x180044fc0`
- `0x180045ad0`
- `0x18004612c`
- `0x18004b5e0`
- `0x180059ea0`
- `0x180069a60`

## callees

- `0x1800068b0`
- `0x180007280`
- `0x180007b40`
- `0x180007db0`
- `0x180008310`
- `0x1800094c0`
- `0x18000a6c8`
- `0x180022844`
- `0x1800286e8`
- `0x1800329ac`
- `0x1800391b8`
- `0x180039610`
- `0x180039fb4`
- `0x18003c4e8`
- `0x18003c698`
- `0x18006d234`
- `0x180087614`

## import_xrefs

- `ntdll!RtlpEnsureBufferSize` at `0x1800087f6`
- `ntdll!RtlpEnsureBufferSize` at `0x1800087f6`
- `ntdll!RtlDuplicateUnicodeString` at `0x180008468`
- `ntdll!RtlDuplicateUnicodeString` at `0x180008468`
- `ntdll!RtlInitUnicodeString` at `0x18000837c`
- `ntdll!RtlInitUnicodeString` at `0x1800083a5`
- `ntdll!RtlInitUnicodeString` at `0x1800087bf`
- `ntdll!RtlInitUnicodeString` at `0x18000837c`
- `ntdll!RtlInitUnicodeString` at `0x1800083a5`
- `ntdll!RtlInitUnicodeString` at `0x1800087bf`
- `KERNEL32!LocalAlloc` at `0x18000842b`
- `KERNEL32!LocalAlloc` at `0x18000842b`

## pseudocode

```c

```
