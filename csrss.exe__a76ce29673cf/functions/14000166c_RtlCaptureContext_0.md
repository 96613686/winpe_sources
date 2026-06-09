# RtlCaptureContext_0

- ea: `0x14000166c`
- end: `0x140001672`
- name: `RtlCaptureContext_0`
- size: `6`
- prototype: `void __stdcall(PCONTEXT ContextRecord)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140001430`

## import_xrefs

- `ntdll!RtlCaptureContext` at `0x14000166c`

## pseudocode

```c
// attributes: thunk
void __stdcall RtlCaptureContext_0(PCONTEXT ContextRecord)
{
  RtlCaptureContext(ContextRecord);
}

```

## disassembly

```asm
0x14000166c  jmp     cs:__imp_RtlCaptureContext
```
