# _initterm_e_0

- ea: `0x140001b82`
- end: `0x140001b88`
- name: `_initterm_e_0`
- size: `6`
- prototype: `int __cdecl(_PIFV *First, _PIFV *Last)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001180`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_initterm_e` at `0x140001b82`

## pseudocode

```c
// attributes: thunk
int __cdecl initterm_e_0(_PIFV *First, _PIFV *Last)
{
  return _initterm_e(First, Last);
}

```

## disassembly

```asm
0x140001b82  jmp     cs:__imp__initterm_e
```
