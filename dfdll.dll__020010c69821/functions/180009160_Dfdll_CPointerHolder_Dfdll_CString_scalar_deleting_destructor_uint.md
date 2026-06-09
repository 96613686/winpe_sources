# Dfdll::CPointerHolder<Dfdll::CString>::`scalar deleting destructor'(uint)

- ea: `0x180009160`
- end: `0x1800091c3`
- name: `??_G?$CPointerHolder@VCString@Dfdll@@@Dfdll@@UEAAPEAXI@Z`
- size: `99`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x180009160`
- `0x180012b30`
- `0x18001efd0`

## pseudocode

```c
_QWORD *__fastcall Dfdll::CPointerHolder<Dfdll::CString>::`scalar deleting destructor'(_QWORD *a1, char a2)
{
  void (__fastcall ***v4)(_QWORD, __int64); // rcx

  *a1 = &Dfdll::CPointerHolder<Dfdll::CString>::`vftable';
  v4 = (void (__fastcall ***)(_QWORD, __int64))a1[1];
  if ( v4 )
    (**v4)(v4, 1);
  a1[1] = 0;
  *a1 = &Dfdll::CObject::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1, (const struct std::nothrow_t *)0x10);
  return a1;
}

```

## disassembly

```asm
0x180009160  mov     [rsp+arg_0], rbx
0x180009165  push    rdi
0x180009166  sub     rsp, 20h
0x18000916a  lea     rax, ??_7?$CPointerHolder@VCString@Dfdll@@@Dfdll@@6B@; const Dfdll::CPointerHolder<Dfdll::CString>::`vftable'
0x180009171  mov     rbx, rcx
0x180009174  mov     [rcx], rax
0x180009177  mov     edi, edx
0x180009179  mov     rcx, [rcx+8]
0x18000917d  test    rcx, rcx
0x180009180  jz      short loc_180009193
0x180009182  mov     rax, [rcx]
0x180009185  mov     edx, 1
0x18000918a  mov     rax, [rax]
0x18000918d  call    cs:__guard_dispatch_icall_fptr
0x180009193  and     qword ptr [rbx+8], 0
0x180009198  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x18000919f  mov     [rbx], rax
0x1800091a2  test    dil, 1
0x1800091a6  jz      short loc_1800091B5
0x1800091a8  mov     edx, 10h; struct std::nothrow_t *
0x1800091ad  mov     rcx, rbx; void *
0x1800091b0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800091b5  mov     rax, rbx
0x1800091b8  mov     rbx, [rsp+28h+arg_0]
0x1800091bd  add     rsp, 20h
0x1800091c1  pop     rdi
0x1800091c2  retn
```
