# __seh_filter_dll

- ea: `0x1001346f`
- end: `0x10013475`
- name: `__seh_filter_dll`
- size: `6`
- prototype: `int __cdecl(unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x10012d4d`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__seh_filter_dll` at `0x1001346f`

## pseudocode

```c
// attributes: thunk
int __cdecl _seh_filter_dll(unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)
{
  return __o__seh_filter_dll(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x1001346f  jmp     ds:__imp___o__seh_filter_dll
```
