# std::vector<Container::Manager::Image::RegistryAdjustment,std::allocator<Container::Manager::Image::RegistryAdjustment>>::_Change_array(Container::Manager::Image::RegistryAdjustment * const,unsigned __int64,unsigned __int64)

- ea: `0x14001f5c0`
- end: `0x14001f658`
- name: `?_Change_array@?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@AEAAXQEAURegistryAdjustment@Image@Manager@Container@@_K1@Z`
- size: `152`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x1400133e4`
- `0x140013ee8`
- `0x140014bbc`

## callees

- `0x140002344`
- `0x140012e48`
- `0x14001f5c0`

## pseudocode

```c
__int64 __fastcall std::vector<Container::Manager::Image::RegistryAdjustment>::_Change_array(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  char *v6; // rcx
  char *v9; // r10
  const struct std::nothrow_t *v10; // rdx
  char *v11; // rcx
  __int64 result; // rax

  v6 = *(char **)a1;
  if ( v6 )
  {
    std::_Destroy_range<std::allocator<Container::Manager::Image::RegistryAdjustment>>(v6, *(_QWORD **)(a1 + 8));
    v9 = *(char **)a1;
    v10 = (const struct std::nothrow_t *)(8 * ((__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3));
    if ( (unsigned __int64)v10 < 0x1000 )
    {
      v11 = *(char **)a1;
    }
    else
    {
      v11 = (char *)*((_QWORD *)v9 - 1);
      if ( (unsigned __int64)(v9 - v11 - 8) > 0x1F )
        __fastfail(5u);
      v10 = (const struct std::nothrow_t *)((char *)v10 + 39);
    }
    operator delete(v11, v10);
  }
  *(_QWORD *)a1 = a2;
  *(_QWORD *)(a1 + 8) = a2 + 120 * a3;
  result = a2 + 120 * a4;
  *(_QWORD *)(a1 + 16) = result;
  return result;
}

```

## disassembly

```asm
0x14001f5c0  push    rbx
0x14001f5c2  push    rbp
0x14001f5c3  push    rsi
0x14001f5c4  push    rdi
0x14001f5c5  sub     rsp, 28h
0x14001f5c9  mov     rbx, rcx
0x14001f5cc  mov     rsi, r9
0x14001f5cf  mov     rcx, [rcx]
0x14001f5d2  mov     rbp, r8
0x14001f5d5  mov     rdi, rdx
0x14001f5d8  test    rcx, rcx
0x14001f5db  jz      short loc_14001F635
0x14001f5dd  mov     rdx, [rbx+8]
0x14001f5e1  call    ??$_Destroy_range@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@YAXPEAURegistryAdjustment@Image@Manager@Container@@QEAU1234@AEAV?$allocator@URegistryAdjustment@Image@Manager@Container@@@0@@Z; std::_Destroy_range<std::allocator<Container::Manager::Image::RegistryAdjustment>>(Container::Manager::Image::RegistryAdjustment *,Container::Manager::Image::RegistryAdjustment * const,std::allocator<Container::Manager::Image::RegistryAdjustment> &)
0x14001f5e6  mov     r10, [rbx]
0x14001f5e9  mov     rcx, 0EEEEEEEEEEEEEEEFh
0x14001f5f3  mov     rax, [rbx+10h]
0x14001f5f7  sub     rax, r10
0x14001f5fa  sar     rax, 3
0x14001f5fe  imul    rax, rcx
0x14001f602  imul    rdx, rax, 78h ; 'x'; struct std::nothrow_t *
0x14001f606  cmp     rdx, 1000h
0x14001f60d  jb      short loc_14001F62D
0x14001f60f  mov     rcx, [r10-8]
0x14001f613  sub     r10, rcx
0x14001f616  sub     r10, 8
0x14001f61a  cmp     r10, 1Fh
0x14001f61e  ja      short loc_14001F626
0x14001f620  add     rdx, 27h ; '''
0x14001f624  jmp     short loc_14001F630
0x14001f626  mov     ecx, 5
0x14001f62b  int     29h; Win8: RtlFailFast(ecx)
0x14001f62d  mov     rcx, r10; void *
0x14001f630  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001f635  imul    rax, rbp, 78h ; 'x'
0x14001f639  mov     [rbx], rdi
0x14001f63c  add     rax, rdi
0x14001f63f  mov     [rbx+8], rax
0x14001f643  imul    rax, rsi, 78h ; 'x'
0x14001f647  add     rax, rdi
0x14001f64a  mov     [rbx+10h], rax
0x14001f64e  add     rsp, 28h
0x14001f652  pop     rdi
0x14001f653  pop     rsi
0x14001f654  pop     rbp
0x14001f655  pop     rbx
0x14001f656  retn
```
