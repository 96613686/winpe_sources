# __scrt_set_unhandled_exception_filter

- ea: `0x140001820`
- end: `0x14000182e`
- name: `__scrt_set_unhandled_exception_filter`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1400011b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140001827`

## pseudocode

```c
LPTOP_LEVEL_EXCEPTION_FILTER _scrt_set_unhandled_exception_filter()
{
  return SetUnhandledExceptionFilter((LPTOP_LEVEL_EXCEPTION_FILTER)_scrt_unhandled_exception_filter);
}

```

## disassembly

```asm
0x140001820  lea     rcx, __scrt_unhandled_exception_filter
0x140001827  jmp     cs:__imp_SetUnhandledExceptionFilter
```
