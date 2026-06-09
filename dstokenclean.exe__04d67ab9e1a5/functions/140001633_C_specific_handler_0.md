# __C_specific_handler_0

- ea: `0x140001633`
- end: `0x140001639`
- name: `__C_specific_handler_0`
- size: `6`
- prototype: `EXCEPTION_DISPOSITION __cdecl(struct _EXCEPTION_RECORD *ExceptionRecord, void *EstablisherFrame, struct _CONTEXT *ContextRecord, struct _DISPATCHER_CONTEXT *DispatcherContext)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, installer_update`

## import_xrefs

- `msvcrt!__C_specific_handler` at `0x140001633`

## pseudocode

```c
// attributes: thunk
EXCEPTION_DISPOSITION __cdecl _C_specific_handler_0(
        struct _EXCEPTION_RECORD *ExceptionRecord,
        void *EstablisherFrame,
        struct _CONTEXT *ContextRecord,
        struct _DISPATCHER_CONTEXT *DispatcherContext)
{
  return __C_specific_handler(ExceptionRecord, EstablisherFrame, ContextRecord, DispatcherContext);
}

```

## disassembly

```asm
0x140001633  jmp     cs:__imp___C_specific_handler
```
