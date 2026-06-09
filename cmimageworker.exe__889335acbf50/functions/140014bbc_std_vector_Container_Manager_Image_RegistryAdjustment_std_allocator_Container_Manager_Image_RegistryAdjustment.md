# std::vector<Container::Manager::Image::RegistryAdjustment,std::allocator<Container::Manager::Image::RegistryAdjustment>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)

- ea: `0x140014bbc`
- end: `0x140014d7b`
- name: `??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z`
- size: `447`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1400111d0`

## callees

- `0x140002b2c`
- `0x140002bd4`
- `0x140012e48`
- `0x140014bbc`
- `0x1400153c4`
- `0x14001f5c0`
- `0x14001ffcc`

## pseudocode

```c
__int64 __fastcall std::vector<Container::Manager::Image::RegistryAdjustment>::_Resize_reallocate<std::_Value_init_tag>(
        __int64 *a1)
{
  __int64 v1; // rsi
  unsigned __int64 v3; // rdx
  unsigned __int64 v4; // rcx
  __int64 v5; // rbp
  unsigned __int64 v6; // rdi
  size_t v7; // rcx
  _QWORD *v8; // rbx
  unsigned __int64 v9; // rbp
  char *v10; // rsi
  unsigned __int64 v11; // r12
  __m128i *v12; // rbp
  __m128i *v13; // r15
  __m128i *v14; // r13
  __int64 v15; // r11
  _QWORD *v16; // rcx
  __int64 i; // rdx
  void *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rdx

  v1 = *a1;
  v3 = 0xEEEEEEEEEEEEEEEFuLL * ((a1[2] - *a1) >> 3);
  v4 = v3 >> 1;
  if ( v3 > 0x222222222222222LL - (v3 >> 1) )
    goto LABEL_20;
  v5 = a1[1];
  v6 = v3 + v4;
  if ( !(v3 + v4) )
  {
    v6 = 1;
    v7 = 120;
LABEL_4:
    v8 = operator new(v7);
    goto LABEL_5;
  }
  if ( v6 > 0x222222222222222LL )
    goto LABEL_20;
  v7 = 120 * v6;
  if ( !(120 * v6) )
  {
    v8 = 0;
    goto LABEL_5;
  }
  if ( v7 < 0x1000 )
    goto LABEL_4;
  if ( v7 + 39 < v7 )
LABEL_20:
    __scrt_throw_std_bad_array_new_length();
  v18 = operator new(v7 + 39);
  if ( !v18 )
    __fastfail(5u);
  v8 = (_QWORD *)(((unsigned __int64)v18 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v8 - 1) = v18;
LABEL_5:
  v9 = 0xEEEEEEEEEEEEEEEFuLL * ((v5 - v1) >> 3);
  v10 = (char *)&v8[15 * v9];
  v11 = 1 - v9;
  if ( v9 != 1 )
  {
    v12 = (__m128i *)(v10 + 8);
    v13 = (__m128i *)(v10 + 40);
    v14 = (__m128i *)(v10 + 72);
    do
    {
      memset_0(v10, 0, 0x78u);
      *((_QWORD *)v10 + 13) = 0;
      *v12 = _mm_unpacklo_epi64((__m128i)(unsigned __int64)&v12[1], (__m128i)(unsigned __int64)&v12[1]);
      *((_DWORD *)v10 + 28) = 0;
      v10 += 120;
      v12[1].m128i_i16[0] = 0;
      v13[1].m128i_i16[0] = 0;
      v12 = (__m128i *)((char *)v12 + 120);
      v14[1].m128i_i16[0] = 0;
      *v13 = _mm_unpacklo_epi64((__m128i)(unsigned __int64)&v13[1], (__m128i)(unsigned __int64)&v13[1]);
      v13 = (__m128i *)((char *)v13 + 120);
      *v14 = _mm_unpacklo_epi64((__m128i)(unsigned __int64)&v14[1], (__m128i)(unsigned __int64)&v14[1]);
      v14 = (__m128i *)((char *)v14 + 120);
      --v11;
    }
    while ( v11 );
  }
  std::_Destroy_range<std::allocator<Container::Manager::Image::RegistryAdjustment>>(v10, v10);
  v15 = a1[1];
  v16 = v8;
  for ( i = *a1; i != v15; i = v20 + 120 )
  {
    Container::Manager::Image::RegistryAdjustment::RegistryAdjustment(v16, i);
    v16 = (_QWORD *)(v19 + 120);
  }
  std::_Destroy_range<std::allocator<Container::Manager::Image::RegistryAdjustment>>(v16, v16);
  return std::vector<Container::Manager::Image::RegistryAdjustment>::_Change_array(a1, v8, 1, v6);
}

```

## disassembly

```asm
0x140014bbc  push    rbx
0x140014bbe  push    rbp
0x140014bbf  push    rsi
0x140014bc0  push    rdi
0x140014bc1  push    r12
0x140014bc3  push    r13
0x140014bc5  push    r14
0x140014bc7  push    r15
0x140014bc9  sub     rsp, 28h
0x140014bcd  mov     rsi, [rcx]
0x140014bd0  mov     r14, rcx
0x140014bd3  mov     rdx, [rcx+10h]
0x140014bd7  mov     r12, 0EEEEEEEEEEEEEEEFh
0x140014be1  sub     rdx, rsi
0x140014be4  mov     r8, 222222222222222h
0x140014bee  sar     rdx, 3
0x140014bf2  mov     rax, r8
0x140014bf5  imul    rdx, r12
0x140014bf9  mov     rcx, rdx
0x140014bfc  shr     rcx, 1
0x140014bff  sub     rax, rcx
0x140014c02  cmp     rdx, rax
0x140014c05  ja      loc_140014D75
0x140014c0b  mov     rbp, [r14+8]
0x140014c0f  lea     rdi, [rdx+rcx]
0x140014c13  mov     r15d, 1
0x140014c19  cmp     rdi, r15
0x140014c1c  jnb     loc_140014CE8
0x140014c22  mov     edi, r15d
0x140014c25  lea     ecx, [r15+77h]; Size
0x140014c29  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140014c2e  mov     rbx, rax
0x140014c31  sub     rbp, rsi
0x140014c34  sar     rbp, 3
0x140014c38  imul    rbp, r12
0x140014c3c  mov     r12, r15
0x140014c3f  imul    rsi, rbp, 78h ; 'x'
0x140014c43  add     rsi, rbx
0x140014c46  sub     r12, rbp
0x140014c49  jz      loc_140014CD1
0x140014c4f  lea     rbp, [rsi+8]
0x140014c53  lea     r15, [rsi+28h]
0x140014c57  lea     r13, [rsi+48h]
0x140014c5b  xor     edx, edx; Val
0x140014c5d  mov     rcx, rsi; void *
0x140014c60  lea     r8d, [rdx+78h]; Size
0x140014c64  call    memset_0
0x140014c69  xor     ecx, ecx
0x140014c6b  lea     rax, [rbp+10h]
0x140014c6f  movq    xmm0, rax
0x140014c74  mov     [rsi+68h], rcx
0x140014c78  punpcklqdq xmm0, xmm0
0x140014c7c  lea     rax, [r15+10h]
0x140014c80  movdqu  xmmword ptr [rbp+0], xmm0
0x140014c85  mov     [rsi+70h], ecx
0x140014c88  add     rsi, 78h ; 'x'
0x140014c8c  movq    xmm0, rax
0x140014c91  mov     [rbp+10h], cx
0x140014c95  punpcklqdq xmm0, xmm0
0x140014c99  lea     rax, [r13+10h]
0x140014c9d  mov     [r15+10h], cx
0x140014ca2  lea     rbp, [rbp+78h]
0x140014ca6  mov     [r13+10h], cx
0x140014cab  movdqu  xmmword ptr [r15], xmm0
0x140014cb0  lea     r15, [r15+78h]
0x140014cb4  movq    xmm0, rax
0x140014cb9  punpcklqdq xmm0, xmm0
0x140014cbd  movdqu  xmmword ptr [r13+0], xmm0
0x140014cc3  lea     r13, [r13+78h]
0x140014cc7  sub     r12, 1
0x140014ccb  jnz     short loc_140014C5B
0x140014ccd  lea     r15d, [rcx+1]
0x140014cd1  mov     rdx, rsi
0x140014cd4  mov     rcx, rsi
0x140014cd7  call    ??$_Destroy_range@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@YAXPEAURegistryAdjustment@Image@Manager@Container@@QEAU1234@AEAV?$allocator@URegistryAdjustment@Image@Manager@Container@@@0@@Z; std::_Destroy_range<std::allocator<Container::Manager::Image::RegistryAdjustment>>(Container::Manager::Image::RegistryAdjustment *,Container::Manager::Image::RegistryAdjustment * const,std::allocator<Container::Manager::Image::RegistryAdjustment> &)
0x140014cdc  mov     r11, [r14+8]
0x140014ce0  mov     rcx, rbx
0x140014ce3  mov     rdx, [r14]
0x140014ce6  jmp     short loc_140014D47
0x140014ce8  cmp     rdi, r8
0x140014ceb  ja      loc_140014D75
0x140014cf1  imul    rcx, rdi, 78h ; 'x'
0x140014cf5  test    rcx, rcx
0x140014cf8  jnz     short loc_140014D01
0x140014cfa  xor     ebx, ebx
0x140014cfc  jmp     loc_140014C31
0x140014d01  cmp     rcx, 1000h
0x140014d08  jb      loc_140014C29
0x140014d0e  lea     rax, [rcx+27h]
0x140014d12  cmp     rax, rcx
0x140014d15  jbe     short loc_140014D75
0x140014d17  mov     rcx, rax; Size
0x140014d1a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140014d1f  test    rax, rax
0x140014d22  jnz     short loc_140014D29
0x140014d24  lea     ecx, [rax+5]
0x140014d27  int     29h; Win8: RtlFailFast(ecx)
0x140014d29  lea     rbx, [rax+27h]
0x140014d2d  and     rbx, 0FFFFFFFFFFFFFFE0h
0x140014d31  mov     [rbx-8], rax
0x140014d35  jmp     loc_140014C31
0x140014d3a  call    ??0RegistryAdjustment@Image@Manager@Container@@QEAA@$$QEAU0123@@Z; Container::Manager::Image::RegistryAdjustment::RegistryAdjustment(Container::Manager::Image::RegistryAdjustment &&)
0x140014d3f  add     rcx, 78h ; 'x'
0x140014d43  add     rdx, 78h ; 'x'
0x140014d47  cmp     rdx, r11
0x140014d4a  jnz     short loc_140014D3A
0x140014d4c  mov     rdx, rcx
0x140014d4f  call    ??$_Destroy_range@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@YAXPEAURegistryAdjustment@Image@Manager@Container@@QEAU1234@AEAV?$allocator@URegistryAdjustment@Image@Manager@Container@@@0@@Z; std::_Destroy_range<std::allocator<Container::Manager::Image::RegistryAdjustment>>(Container::Manager::Image::RegistryAdjustment *,Container::Manager::Image::RegistryAdjustment * const,std::allocator<Container::Manager::Image::RegistryAdjustment> &)
0x140014d54  mov     r9, rdi
0x140014d57  mov     r8, r15
0x140014d5a  mov     rdx, rbx
0x140014d5d  mov     rcx, r14
0x140014d60  add     rsp, 28h
0x140014d64  pop     r15
0x140014d66  pop     r14
0x140014d68  pop     r13
0x140014d6a  pop     r12
0x140014d6c  pop     rdi
0x140014d6d  pop     rsi
0x140014d6e  pop     rbp
0x140014d6f  pop     rbx
0x140014d70  jmp     ?_Change_array@?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@AEAAXQEAURegistryAdjustment@Image@Manager@Container@@_K1@Z; std::vector<Container::Manager::Image::RegistryAdjustment>::_Change_array(Container::Manager::Image::RegistryAdjustment * const,unsigned __int64,unsigned __int64)
0x140014d75  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
