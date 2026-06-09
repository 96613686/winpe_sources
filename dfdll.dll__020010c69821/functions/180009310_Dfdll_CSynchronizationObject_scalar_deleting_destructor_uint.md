# Dfdll::CSynchronizationObject::`scalar deleting destructor'(uint)

- ea: `0x180009310`
- end: `0x180009382`
- name: `??_GCSynchronizationObject@Dfdll@@UEAAPEAXI@Z`
- size: `114`
- prototype: `void *__fastcall(Dfdll::CSynchronizationObject *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x180009310`
- `0x180012b30`
- `0x18001efd0`

## pseudocode

```c
Dfdll::CSynchronizationObject *__fastcall Dfdll::CSynchronizationObject::`scalar deleting destructor'(
        Dfdll::CSynchronizationObject *this,
        char a2)
{
  void (__fastcall ***v4)(_QWORD, __int64); // rcx

  *(_QWORD *)this = &Dfdll::CSynchronizationObject::`vftable';
  *((_QWORD *)this + 1) = &Dfdll::CPointerHolder<Dfdll::CString>::`vftable';
  v4 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 2);
  if ( v4 )
    (**v4)(v4, 1);
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 1) = &Dfdll::CObject::`vftable';
  *(_QWORD *)this = &Dfdll::CObject::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x18);
  return this;
}

```

## disassembly

```asm
0x180009310  mov     [rsp+arg_0], rbx
0x180009315  push    rdi
0x180009316  sub     rsp, 20h
0x18000931a  lea     rax, ??_7CSynchronizationObject@Dfdll@@6B@; const Dfdll::CSynchronizationObject::`vftable'
0x180009321  mov     rbx, rcx
0x180009324  mov     [rcx], rax
0x180009327  mov     edi, edx
0x180009329  lea     rax, ??_7?$CPointerHolder@VCString@Dfdll@@@Dfdll@@6B@; const Dfdll::CPointerHolder<Dfdll::CString>::`vftable'
0x180009330  mov     [rcx+8], rax
0x180009334  mov     rcx, [rcx+10h]
0x180009338  test    rcx, rcx
0x18000933b  jz      short loc_18000934E
0x18000933d  mov     rax, [rcx]
0x180009340  mov     edx, 1
0x180009345  mov     rax, [rax]
0x180009348  call    cs:__guard_dispatch_icall_fptr
0x18000934e  and     qword ptr [rbx+10h], 0
0x180009353  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x18000935a  mov     [rbx+8], rax
0x18000935e  mov     [rbx], rax
0x180009361  test    dil, 1
0x180009365  jz      short loc_180009374
0x180009367  mov     edx, 18h; struct std::nothrow_t *
0x18000936c  mov     rcx, rbx; void *
0x18000936f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009374  mov     rax, rbx
0x180009377  mov     rbx, [rsp+28h+arg_0]
0x18000937c  add     rsp, 20h
0x180009380  pop     rdi
0x180009381  retn
```
