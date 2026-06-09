# registry_access_error::registry_access_error(long)

- ea: `0x180014f54`
- end: `0x180014f92`
- name: `??0registry_access_error@@QEAA@J@Z`
- size: `62`
- prototype: `registry_access_error *__fastcall(registry_access_error *__hidden this, int)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1800151dc`
- `0x180015748`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180014f70`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180014f70`

## pseudocode

```c
registry_access_error *__fastcall registry_access_error::registry_access_error(registry_access_error *this, int a2)
{
  exception::exception(this, &std::_bad_alloc_Message, 1);
  *(_QWORD *)this = &std::bad_alloc::`vftable';
  *((_DWORD *)this + 6) = a2;
  return this;
}

```

## disassembly

```asm
0x180014f54  mov     [rsp+arg_0], rbx
0x180014f59  push    rdi
0x180014f5a  sub     rsp, 20h
0x180014f5e  mov     ebx, edx
0x180014f60  mov     rdi, rcx
0x180014f63  mov     r8d, 1
0x180014f69  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x180014f70  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x180014f76  nop
0x180014f77  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180014f7e  mov     [rdi], rax
0x180014f81  mov     [rdi+18h], ebx
0x180014f84  mov     rax, rdi
0x180014f87  mov     rbx, [rsp+28h+arg_0]
0x180014f8c  add     rsp, 20h
0x180014f90  pop     rdi
0x180014f91  retn
```
