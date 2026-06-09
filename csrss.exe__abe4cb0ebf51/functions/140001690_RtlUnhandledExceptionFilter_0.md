# RtlUnhandledExceptionFilter_0

- ea: `0x140001690`
- end: `0x140001696`
- name: `RtlUnhandledExceptionFilter_0`
- size: `6`
- prototype: `LONG __stdcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140001430`

## import_xrefs

- `ntdll!RtlUnhandledExceptionFilter` at `0x140001690`

## pseudocode

```c
// attributes: thunk
LONG __stdcall RtlUnhandledExceptionFilter_0(struct _EXCEPTION_POINTERS *ExceptionInfo)
{
  return RtlUnhandledExceptionFilter(ExceptionInfo);
}

```

## disassembly

```asm
0x140001690  jmp     cs:__imp_RtlUnhandledExceptionFilter
```
