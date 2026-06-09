# _o___std_exception_copy_0

- ea: `0x180004c66`
- end: `0x180004c6c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180005de4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180004c66`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall o___std_exception_copy_0(__int64 a1)
{
  return _o___std_exception_copy(a1);
}

```

## disassembly

```asm
0x180004c66  jmp     cs:__imp__o___std_exception_copy
```
