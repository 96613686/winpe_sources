# ___dllonexit

- ea: `0x1004dc33`
- end: `0x1004dc39`
- name: `___dllonexit`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1004d662`

## import_xrefs

- `msvcrt!__dllonexit` at `0x1004dc33`

## pseudocode

```c
// attributes: thunk
int __dllonexit()
{
  return ___dllonexit();
}

```

## disassembly

```asm
0x1004dc33  jmp     ds:__imp____dllonexit
```
