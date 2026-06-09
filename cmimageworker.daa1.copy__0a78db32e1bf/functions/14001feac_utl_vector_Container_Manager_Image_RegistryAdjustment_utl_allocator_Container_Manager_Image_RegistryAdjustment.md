# utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>::_SetCapacity(unsigned __int64)

- ea: `0x14001feac`
- end: `0x14001ffa3`
- name: `?_SetCapacity@?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@utl@@@utl@@AEAA_N_K@Z`
- size: `247`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x1400113ec`
- `0x1400150dc`

## callees

- `0x140002344`
- `0x140002b8c`
- `0x1400140a0`
- `0x1400153c4`
- `0x14001feac`

## pseudocode

```c
char __fastcall utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>::_SetCapacity(
        __int64 *a1,
        unsigned __int64 a2)
{
  __int64 v3; // rsi
  __int64 v4; // rcx
  char *v5; // rdi
  __int64 v6; // r14
  char *v7; // r15
  __int64 v8; // r11
  unsigned __int64 v9; // rbp
  char v10; // si
  __int64 v11; // r11
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r8
  char *v15; // rbp

  if ( a2 > 0x222222222222222LL )
    return 0;
  v3 = 120 * a2;
  v5 = (char *)operator new(120 * a2, (const struct std::nothrow_t *)&std::nothrow);
  if ( ((unsigned __int64)(v5 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    return 0;
  v6 = *a1;
  v7 = &v5[v3];
  v8 = 0;
  v9 = 0xEEEEEEEEEEEEEEEFuLL * ((a1[1] - *a1) >> 3);
  v10 = 1;
  if ( v9 )
  {
    do
    {
      Container::Manager::Image::RegistryAdjustment::RegistryAdjustment((__int64)&v5[120 * v8], 120 * v8 + v6);
      v8 = v11 + 1;
    }
    while ( v8 != v9 );
  }
  utl::_RangeDestroyApc<utl::allocator<Container::Manager::Image::RegistryAdjustment>>(v4, (__int64)v5, 0);
  v13 = *a1;
  v14 = 0xEEEEEEEEEEEEEEEFuLL * ((a1[1] - *a1) >> 3);
  v15 = &v5[8 * ((a1[1] - *a1) >> 3)];
  if ( *a1 != -1 )
  {
    a1[1] = v13;
    utl::_RangeDestroyApc<utl::allocator<Container::Manager::Image::RegistryAdjustment>>(v12, v13, v14);
    operator delete((void *)*a1, (const struct std::nothrow_t *)&std::nothrow);
  }
  *a1 = (__int64)v5;
  a1[1] = (__int64)v15;
  a1[2] = (__int64)v7;
  return v10;
}

```

## disassembly

```asm
0x14001feac  push    rbx
0x14001feae  push    rbp
0x14001feaf  push    rsi
0x14001feb0  push    rdi
0x14001feb1  push    r12
0x14001feb3  push    r14
0x14001feb5  push    r15
0x14001feb7  sub     rsp, 20h
0x14001febb  mov     rax, 222222222222222h
0x14001fec5  mov     rbx, rcx
0x14001fec8  cmp     rdx, rax
0x14001fecb  ja      loc_14001FF8A
0x14001fed1  imul    rsi, rdx, 78h ; 'x'
0x14001fed5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001fedc  mov     rcx, rsi; unsigned __int64
0x14001fedf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14001fee4  mov     rdi, rax
0x14001fee7  inc     rax
0x14001feea  test    rax, 0FFFFFFFFFFFFFFFEh
0x14001fef0  jz      loc_14001FF8A
0x14001fef6  mov     r14, [rbx]
0x14001fef9  lea     r15, [rsi+rdi]
0x14001fefd  mov     rbp, [rbx+8]
0x14001ff01  xor     r11d, r11d
0x14001ff04  sub     rbp, r14
0x14001ff07  mov     r12, 0EEEEEEEEEEEEEEEFh
0x14001ff11  sar     rbp, 3
0x14001ff15  imul    rbp, r12
0x14001ff19  lea     esi, [r11+1]
0x14001ff1d  test    rbp, rbp
0x14001ff20  jz      short loc_14001FF3B
0x14001ff22  imul    rax, r11, 78h ; 'x'
0x14001ff26  lea     rdx, [rax+r14]
0x14001ff2a  lea     rcx, [rax+rdi]
0x14001ff2e  call    ??0RegistryAdjustment@Image@Manager@Container@@QEAA@$$QEAU0123@@Z; Container::Manager::Image::RegistryAdjustment::RegistryAdjustment(Container::Manager::Image::RegistryAdjustment &&)
0x14001ff33  add     r11, rsi
0x14001ff36  cmp     r11, rbp
0x14001ff39  jnz     short loc_14001FF22
0x14001ff3b  xor     r8d, r8d
0x14001ff3e  mov     rdx, rdi
0x14001ff41  call    ??$_RangeDestroyApc@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@utl@@@utl@@YAXAEAV?$allocator@URegistryAdjustment@Image@Manager@Container@@@0@PEAURegistryAdjustment@Image@Manager@Container@@_K@Z; utl::_RangeDestroyApc<utl::allocator<Container::Manager::Image::RegistryAdjustment>>(utl::allocator<Container::Manager::Image::RegistryAdjustment> &,Container::Manager::Image::RegistryAdjustment *,unsigned __int64)
0x14001ff46  mov     rdx, [rbx]
0x14001ff49  mov     r8, [rbx+8]
0x14001ff4d  sub     r8, rdx
0x14001ff50  sar     r8, 3
0x14001ff54  imul    r8, r12
0x14001ff58  imul    rbp, r8, 78h ; 'x'
0x14001ff5c  add     rbp, rdi
0x14001ff5f  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x14001ff63  jz      short loc_14001FF7D
0x14001ff65  mov     [rbx+8], rdx
0x14001ff69  call    ??$_RangeDestroyApc@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@utl@@@utl@@YAXAEAV?$allocator@URegistryAdjustment@Image@Manager@Container@@@0@PEAURegistryAdjustment@Image@Manager@Container@@_K@Z; utl::_RangeDestroyApc<utl::allocator<Container::Manager::Image::RegistryAdjustment>>(utl::allocator<Container::Manager::Image::RegistryAdjustment> &,Container::Manager::Image::RegistryAdjustment *,unsigned __int64)
0x14001ff6e  mov     rcx, [rbx]; void *
0x14001ff71  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001ff78  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001ff7d  mov     [rbx], rdi
0x14001ff80  mov     [rbx+8], rbp
0x14001ff84  mov     [rbx+10h], r15
0x14001ff88  jmp     short loc_14001FF90
0x14001ff8a  xor     r11d, r11d
0x14001ff8d  mov     sil, r11b
0x14001ff90  mov     al, sil
0x14001ff93  add     rsp, 20h
0x14001ff97  pop     r15
0x14001ff99  pop     r14
0x14001ff9b  pop     r12
0x14001ff9d  pop     rdi
0x14001ff9e  pop     rsi
0x14001ff9f  pop     rbp
0x14001ffa0  pop     rbx
0x14001ffa1  retn
```
