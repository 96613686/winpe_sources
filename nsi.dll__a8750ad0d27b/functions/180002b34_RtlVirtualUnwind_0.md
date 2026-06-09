# RtlVirtualUnwind_0

- ea: `0x180002b34`
- end: `0x180002b3a`
- name: `RtlVirtualUnwind_0`
- size: `6`
- prototype: `PEXCEPTION_ROUTINE __stdcall(ULONG HandlerType, ULONG64 ImageBase, ULONG64 ControlPc, PRUNTIME_FUNCTION FunctionEntry, PCONTEXT ContextRecord, PVOID *HandlerData, PULONG64 EstablisherFrame, PKNONVOLATILE_CONTEXT_POINTERS ContextPointers)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800028e0`

## import_xrefs

- `ntdll!RtlVirtualUnwind` at `0x180002b34`

## pseudocode

```c
// attributes: thunk
PEXCEPTION_ROUTINE __stdcall RtlVirtualUnwind_0(ULONG HandlerType, ULONG64 ImageBase, ULONG64 ControlPc, PRUNTIME_FUNCTION FunctionEntry, PCONTEXT ContextRecord, PVOID *HandlerData, PULONG64 EstablisherFrame, PKNONVOLATILE_CONTEXT_POINTERS ContextPointers)
{
  return RtlVirtualUnwind(
           HandlerType,
           ImageBase,
           ControlPc,
           FunctionEntry,
           ContextRecord,
           HandlerData,
           EstablisherFrame,
           ContextPointers);
}

```

## disassembly

```asm
0x180002b34  jmp     cs:__imp_RtlVirtualUnwind
```
