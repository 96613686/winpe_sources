# std::bad_alloc::bad_alloc(char const *)

- ea: `0x18001117c`
- end: `0x1800111ac`
- name: `??0bad_alloc@std@@QEAA@PEBD@Z`
- size: `48`
- prototype: `std::bad_alloc *__fastcall(std::bad_alloc *this, const char *)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x18000ce20`
- `0x1800110a4`
- `0x180013114`
- `0x180013390`
- `0x180017374`
- `0x180017428`
- `0x180017fe0`
- `0x1800180ec`
- `0x18001884c`
- `0x180019b1c`
- `0x180019e70`
- `0x18001a24c`
- `0x18001b428`
- `0x18001c4b8`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180011193`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180011193`

## pseudocode

```c
std::bad_alloc *__fastcall std::bad_alloc::bad_alloc(std::bad_alloc *this, const char *a2)
{
  const char *v4; // [rsp+20h] [rbp-18h] BYREF

  v4 = 0;
  exception::exception(this, &v4);
  *(_QWORD *)this = &std::bad_alloc::`vftable';
  return this;
}

```

## disassembly

```asm
0x18001117c  push    rbx
0x18001117e  sub     rsp, 30h
0x180011182  mov     rbx, rcx
0x180011185  mov     [rsp+38h+var_18], 0
0x18001118e  lea     rdx, [rsp+38h+var_18]
0x180011193  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x180011199  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x1800111a0  mov     [rbx], rax
0x1800111a3  mov     rax, rbx
0x1800111a6  add     rsp, 30h
0x1800111aa  pop     rbx
0x1800111ab  retn
```
