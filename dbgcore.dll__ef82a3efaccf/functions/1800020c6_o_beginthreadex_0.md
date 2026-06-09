# _o__beginthreadex_0

- ea: `0x1800020c6`
- end: `0x1800020cc`
- name: `_o__beginthreadex_0`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18001e114`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800020c6`

## pseudocode

```c
// attributes: thunk
__int64 o__beginthreadex_0()
{
  return _o__beginthreadex();
}

```

## disassembly

```asm
0x1800020c6  jmp     cs:__imp__o__beginthreadex
```
