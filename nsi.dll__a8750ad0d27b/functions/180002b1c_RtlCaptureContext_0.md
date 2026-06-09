# RtlCaptureContext_0

- ea: `0x180002b1c`
- end: `0x180002b22`
- name: `RtlCaptureContext_0`
- size: `6`
- prototype: `void __stdcall(PCONTEXT ContextRecord)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800028e0`

## import_xrefs

- `ntdll!RtlCaptureContext` at `0x180002b1c`

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
0x180002b1c  jmp     cs:__imp_RtlCaptureContext
```
