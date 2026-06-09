# _o__cexit_0

- ea: `0x140001bca`
- end: `0x140001bd0`
- name: `_o__cexit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001180`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__cexit` at `0x140001bca`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall o__cexit_0(__int64 a1)
{
  return _o__cexit(a1);
}

```

## disassembly

```asm
0x140001bca  jmp     cs:__imp__o__cexit
```
