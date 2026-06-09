# registry_access_error::registry_access_error(long)

- ea: `0x1800232dc`
- end: `0x18002331a`
- name: `??0registry_access_error@@QEAA@J@Z`
- size: `62`
- prototype: `registry_access_error *__fastcall(registry_access_error *__hidden this, int)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180023434`
- `0x18002392c`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x1800232f8`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x1800232f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800232dc  mov     [rsp+arg_0], rbx
0x1800232e1  push    rdi
0x1800232e2  sub     rsp, 20h
0x1800232e6  mov     ebx, edx
0x1800232e8  mov     rdi, rcx
0x1800232eb  mov     r8d, 1
0x1800232f1  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x1800232f8  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x1800232fe  nop
0x1800232ff  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180023306  mov     [rdi], rax
0x180023309  mov     [rdi+18h], ebx
0x18002330c  mov     rax, rdi
0x18002330f  mov     rbx, [rsp+28h+arg_0]
0x180023314  add     rsp, 20h
0x180023318  pop     rdi
0x180023319  retn
```
