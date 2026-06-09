# std::vector<Container::Manager::Image::RegistryAdjustment,std::allocator<Container::Manager::Image::RegistryAdjustment>>::~vector<Container::Manager::Image::RegistryAdjustment,std::allocator<Container::Manager::Image::RegistryAdjustment>>(void)

- ea: `0x140015b08`
- end: `0x140015b92`
- name: `??1?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@QEAA@XZ`
- size: `138`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x1400113ec`
- `0x14002f047`

## callees

- `0x140002344`
- `0x140012e48`
- `0x140015b08`

## pseudocode

```c
void __fastcall std::vector<Container::Manager::Image::RegistryAdjustment>::~vector<Container::Manager::Image::RegistryAdjustment>(
        __int64 a1)
{
  char *v2; // rcx
  char *v3; // rdx
  const struct std::nothrow_t *v4; // r8
  char *v5; // rcx

  v2 = *(char **)a1;
  if ( v2 )
  {
    std::_Destroy_range<std::allocator<Container::Manager::Image::RegistryAdjustment>>(v2, *(_QWORD **)(a1 + 8));
    v3 = *(char **)a1;
    v4 = (const struct std::nothrow_t *)(8 * ((__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3));
    if ( (unsigned __int64)v4 < 0x1000 )
    {
      v5 = *(char **)a1;
    }
    else
    {
      v5 = (char *)*((_QWORD *)v3 - 1);
      if ( (unsigned __int64)(v3 - v5 - 8) > 0x1F )
        __fastfail(5u);
      v4 = (const struct std::nothrow_t *)((char *)v4 + 39);
    }
    operator delete(v5, v4);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x140015b08  push    rbx
0x140015b0a  sub     rsp, 20h
0x140015b0e  mov     rbx, rcx
0x140015b11  mov     rcx, [rcx]
0x140015b14  test    rcx, rcx
0x140015b17  jz      short loc_140015B8B
0x140015b19  mov     rdx, [rbx+8]
0x140015b1d  call    ??$_Destroy_range@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@YAXPEAURegistryAdjustment@Image@Manager@Container@@QEAU1234@AEAV?$allocator@URegistryAdjustment@Image@Manager@Container@@@0@@Z; std::_Destroy_range<std::allocator<Container::Manager::Image::RegistryAdjustment>>(Container::Manager::Image::RegistryAdjustment *,Container::Manager::Image::RegistryAdjustment * const,std::allocator<Container::Manager::Image::RegistryAdjustment> &)
0x140015b22  mov     rdx, [rbx]
0x140015b25  mov     rcx, 0EEEEEEEEEEEEEEEFh
0x140015b2f  mov     rax, [rbx+10h]
0x140015b33  sub     rax, rdx
0x140015b36  sar     rax, 3
0x140015b3a  imul    rax, rcx
0x140015b3e  imul    r8, rax, 78h ; 'x'
0x140015b42  cmp     r8, 1000h
0x140015b49  jb      short loc_140015B69
0x140015b4b  mov     rcx, [rdx-8]
0x140015b4f  sub     rdx, rcx
0x140015b52  sub     rdx, 8
0x140015b56  cmp     rdx, 1Fh
0x140015b5a  ja      short loc_140015B62
0x140015b5c  add     r8, 27h ; '''
0x140015b60  jmp     short loc_140015B6C
0x140015b62  mov     ecx, 5
0x140015b67  int     29h; Win8: RtlFailFast(ecx)
0x140015b69  mov     rcx, rdx; void *
0x140015b6c  mov     rdx, r8; struct std::nothrow_t *
0x140015b6f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140015b74  mov     qword ptr [rbx], 0
0x140015b7b  mov     qword ptr [rbx+8], 0
0x140015b83  mov     qword ptr [rbx+10h], 0
0x140015b8b  add     rsp, 20h
0x140015b8f  pop     rbx
0x140015b90  retn
```
