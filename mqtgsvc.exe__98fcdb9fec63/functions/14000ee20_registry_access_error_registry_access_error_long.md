# registry_access_error::registry_access_error(long)

- ea: `0x14000ee20`
- end: `0x14000ee5e`
- name: `??0registry_access_error@@QEAA@J@Z`
- size: `62`
- prototype: `registry_access_error *__fastcall(registry_access_error *__hidden this, int)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x14000f0a4`
- `0x14000f61c`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x14000ee3c`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x14000ee3c`

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
0x14000ee20  mov     [rsp+arg_0], rbx
0x14000ee25  push    rdi
0x14000ee26  sub     rsp, 20h
0x14000ee2a  mov     ebx, edx
0x14000ee2c  mov     rdi, rcx
0x14000ee2f  mov     r8d, 1
0x14000ee35  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x14000ee3c  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x14000ee42  nop
0x14000ee43  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x14000ee4a  mov     [rdi], rax
0x14000ee4d  mov     [rdi+18h], ebx
0x14000ee50  mov     rax, rdi
0x14000ee53  mov     rbx, [rsp+28h+arg_0]
0x14000ee58  add     rsp, 20h
0x14000ee5c  pop     rdi
0x14000ee5d  retn
```
