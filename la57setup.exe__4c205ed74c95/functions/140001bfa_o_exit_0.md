# _o__exit_0

- ea: `0x140001bfa`
- end: `0x140001c00`
- name: `_o__exit_0`
- size: `6`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001180`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__exit` at `0x140001bfa`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall o__exit_0(__int64 a1)
{
  return _o__exit(a1);
}

```

## disassembly

```asm
0x140001bfa  jmp     cs:__imp__o__exit
```
