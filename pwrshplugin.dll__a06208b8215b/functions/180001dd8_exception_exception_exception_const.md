# exception::exception(exception const &)

- ea: `0x180001dd8`
- end: `0x180001dde`
- name: `??0exception@@QEAA@AEBV0@@Z_0`
- size: `6`
- prototype: `exception *__fastcall(exception *this, const struct exception *)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800010d0`
- `0x180001140`
- `0x18000748c`
- `0x1800075b0`
- `0x1800076f4`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBV0@@Z` at `0x180001dd8`

## pseudocode

```c
// attributes: thunk
exception *__fastcall exception::exception(exception *this, const struct exception *a2)
{
  return __imp_??0exception@@QEAA@AEBV0@@Z(this, a2);
}

```

## disassembly

```asm
0x180001dd8  jmp     cs:__imp_??0exception@@QEAA@AEBV0@@Z
```
