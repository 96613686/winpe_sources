# __p___wargv

- ea: `0x140001bb2`
- end: `0x140001bb8`
- name: `__p___wargv`
- size: `6`
- prototype: `wchar_t ***__cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001180`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___p___wargv` at `0x140001bb2`

## pseudocode

```c
// attributes: thunk
wchar_t ***__cdecl _p___wargv()
{
  return _o___p___wargv();
}

```

## disassembly

```asm
0x140001bb2  jmp     cs:__imp__o___p___wargv
```
