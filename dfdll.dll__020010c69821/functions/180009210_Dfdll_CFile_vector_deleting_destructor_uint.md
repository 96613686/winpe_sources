# Dfdll::CFile::`vector deleting destructor'(uint)

- ea: `0x180009210`
- end: `0x180009269`
- name: `??_ECFile@Dfdll@@UEAAPEAXI@Z`
- size: `89`
- prototype: `void *__fastcall(Dfdll::CFile *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x180009210`
- `0x180012b30`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180009233`
- `KERNEL32!CloseHandle` at `0x180009233`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Dfdll::CFile *__fastcall Dfdll::CFile::`vector deleting destructor'(Dfdll::CFile *this, char a2)
{
  void *v4; // rcx

  *(_QWORD *)this = &Dfdll::CFile::`vftable';
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 != (void *)-1LL )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 1) = -1;
  }
  *(_QWORD *)this = &Dfdll::CObject::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x10);
  return this;
}

```

## disassembly

```asm
0x180009210  mov     [rsp+arg_0], rbx
0x180009215  push    rdi
0x180009216  sub     rsp, 20h
0x18000921a  mov     edi, edx
0x18000921c  mov     rbx, rcx
0x18000921f  lea     rax, ??_7CFile@Dfdll@@6B@; const Dfdll::CFile::`vftable'
0x180009226  mov     [rcx], rax
0x180009229  mov     rcx, [rcx+8]; hObject
0x18000922d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180009231  jz      short loc_18000923E
0x180009233  call    cs:__imp_CloseHandle
0x180009239  or      qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x18000923e  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180009245  mov     [rbx], rax
0x180009248  test    dil, 1
0x18000924c  jz      short loc_18000925B
0x18000924e  mov     edx, 10h; struct std::nothrow_t *
0x180009253  mov     rcx, rbx; void *
0x180009256  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000925b  mov     rax, rbx
0x18000925e  mov     rbx, [rsp+28h+arg_0]
0x180009263  add     rsp, 20h
0x180009267  pop     rdi
0x180009268  retn
```
