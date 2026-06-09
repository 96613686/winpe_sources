# std::bad_alloc::bad_alloc(char const *)

- ea: `0x180002f58`
- end: `0x180002f88`
- name: `??0bad_alloc@std@@QEAA@PEBD@Z`
- size: `48`
- prototype: `std::bad_alloc *__fastcall(std::bad_alloc *this, const char *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180006418`
- `0x18000a77c`
- `0x18000b26c`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180002f6f`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180002f6f`

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
0x180002f58  push    rbx
0x180002f5a  sub     rsp, 30h
0x180002f5e  mov     rbx, rcx
0x180002f61  mov     [rsp+38h+var_18], 0
0x180002f6a  lea     rdx, [rsp+38h+var_18]
0x180002f6f  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x180002f75  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180002f7c  mov     [rbx], rax
0x180002f7f  mov     rax, rbx
0x180002f82  add     rsp, 30h
0x180002f86  pop     rbx
0x180002f87  retn
```
