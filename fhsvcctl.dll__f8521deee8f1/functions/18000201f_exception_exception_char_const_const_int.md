# exception::exception(char const * const &,int)

- ea: `0x18000201f`
- end: `0x180002025`
- name: `??0exception@@QEAA@AEBQEBDH@Z_0`
- size: `6`
- prototype: `exception *__fastcall(exception *this, const char *const *, int)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001f30`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18000201f`

## pseudocode

```c
// attributes: thunk
exception *__fastcall exception::exception(exception *this, const char *const *a2, int a3)
{
  return __imp_??0exception@@QEAA@AEBQEBDH@Z(this, a2, a3);
}

```

## disassembly

```asm
0x18000201f  jmp     cs:__imp_??0exception@@QEAA@AEBQEBDH@Z
```
