# _seh_filter_exe

- ea: `0x140001c36`
- end: `0x140001c3c`
- name: `_seh_filter_exe`
- size: `6`
- prototype: `int __cdecl(unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001180`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__seh_filter_exe` at `0x140001c36`

## pseudocode

```c
// attributes: thunk
int __cdecl seh_filter_exe(unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)
{
  return _o__seh_filter_exe(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x140001c36  jmp     cs:__imp__o__seh_filter_exe
```
