# std::bad_alloc::bad_alloc(char const *)

- ea: `0x180006950`
- end: `0x180006980`
- name: `??0bad_alloc@std@@QEAA@PEBD@Z`
- size: `48`
- prototype: `std::bad_alloc *__fastcall(std::bad_alloc *this, const char *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180008b58`
- `0x180009fd8`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180006967`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180006967`

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
0x180006950  push    rbx
0x180006952  sub     rsp, 30h
0x180006956  mov     rbx, rcx
0x180006959  mov     [rsp+38h+var_18], 0
0x180006962  lea     rdx, [rsp+38h+var_18]
0x180006967  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18000696d  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180006974  mov     [rbx], rax
0x180006977  mov     rax, rbx
0x18000697a  add     rsp, 30h
0x18000697e  pop     rbx
0x18000697f  retn
```
