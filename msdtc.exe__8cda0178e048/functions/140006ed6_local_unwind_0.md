# _local_unwind_0

- ea: `0x140006ed6`
- end: `0x140006edc`
- name: `_local_unwind_0`
- size: `6`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1400037ac`
- `0x140006010`

## import_xrefs

- `msvcrt!_local_unwind` at `0x140006ed6`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall local_unwind_0(__int64 a1, __int64 a2)
{
  return _local_unwind(a1, a2);
}

```

## disassembly

```asm
0x140006ed6  jmp     cs:__imp__local_unwind
```
