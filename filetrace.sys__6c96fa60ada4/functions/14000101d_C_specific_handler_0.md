# __C_specific_handler_0

- ea: `0x14000101d`
- end: `0x140001024`
- name: `__C_specific_handler_0`
- size: `7`
- prototype: `EXCEPTION_DISPOSITION __cdecl(struct _EXCEPTION_RECORD *ExceptionRecord, void *EstablisherFrame, struct _CONTEXT *ContextRecord, struct _DISPATCHER_CONTEXT *DispatcherContext)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, installer_update`

## callers

- `0x1400033e4`

## import_xrefs

- `ntoskrnl!__C_specific_handler` at `0x14000101d`

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
0x14000101d  jmp     cs:__imp___C_specific_handler
```
