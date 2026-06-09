# RtlUnhandledExceptionFilter_0

- ea: `0x180002b40`
- end: `0x180002b46`
- name: `RtlUnhandledExceptionFilter_0`
- size: `6`
- prototype: `LONG __stdcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800028e0`

## import_xrefs

- `ntdll!RtlUnhandledExceptionFilter` at `0x180002b40`

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
0x180002b40  jmp     cs:__imp_RtlUnhandledExceptionFilter
```
