# _o___std_exception_copy_0

- ea: `0x1400039ae`
- end: `0x1400039b4`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x140006330`
- `0x14000c3c0`
- `0x14000c410`
- `0x14000dea4`
- `0x14000e080`
- `0x14000e0c4`
- `0x14000e130`
- `0x14001eaa8`
- `0x14001eb14`
- `0x14001eb64`
- `0x14001ebc0`
- `0x14001ec04`
- `0x14003841c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1400039ae`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_copy_0()
{
  return _o___std_exception_copy();
}

```

## disassembly

```asm
0x1400039ae  jmp     cs:__imp__o___std_exception_copy
```
