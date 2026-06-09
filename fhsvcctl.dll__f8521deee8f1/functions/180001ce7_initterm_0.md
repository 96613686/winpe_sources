# _initterm_0

- ea: `0x180001ce7`
- end: `0x180001ced`
- name: `_initterm_0`
- size: `6`
- prototype: `void __cdecl(_PVFV *First, _PVFV *Last)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001640`

## import_xrefs

- `msvcrt!_initterm` at `0x180001ce7`

## pseudocode

```c
// attributes: thunk
void __cdecl initterm_0(_PVFV *First, _PVFV *Last)
{
  _initterm(First, Last);
}

```

## disassembly

```asm
0x180001ce7  jmp     cs:__imp__initterm
```
