# _crt_atexit

- ea: `0x140001bee`
- end: `0x140001bf4`
- name: `_crt_atexit`
- size: `6`
- prototype: `int __cdecl(_PVFV Function)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001574`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__crt_atexit` at `0x140001bee`

## pseudocode

```c
// attributes: thunk
int __cdecl crt_atexit(_PVFV Function)
{
  return _o__crt_atexit(Function);
}

```

## disassembly

```asm
0x140001bee  jmp     cs:__imp__o__crt_atexit
```
