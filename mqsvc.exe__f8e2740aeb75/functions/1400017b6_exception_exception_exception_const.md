# exception::exception(exception const &)

- ea: `0x1400017b6`
- end: `0x1400017bc`
- name: `??0exception@@QEAA@AEBV0@@Z_0`
- size: `6`
- prototype: `exception *__fastcall(exception *this, const struct exception *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBV0@@Z` at `0x1400017b6`

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
0x1400017b6  jmp     cs:__imp_??0exception@@QEAA@AEBV0@@Z
```
