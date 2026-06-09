# utl::vector<Container::Manager::Image::CommandAdjustment,utl::allocator<Container::Manager::Image::CommandAdjustment>>::_SetCapacity(unsigned __int64)

- ea: `0x14001f9f8`
- end: `0x14001fb89`
- name: `?_SetCapacity@?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@utl@@@utl@@AEAA_N_K@Z`
- size: `401`
- prototype: `char __fastcall(__int64 *, unsigned __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140010448`
- `0x140014ffc`

## callees

- `0x140002b8c`
- `0x14001f9f8`
- `0x1400200b4`

## pseudocode

```c
char __fastcall utl::vector<Container::Manager::Image::CommandAdjustment,utl::allocator<Container::Manager::Image::CommandAdjustment>>::_SetCapacity(
        __int64 *a1,
        unsigned __int64 a2,
        __int64 a3)
{
  __int64 v4; // rbx
  _DWORD *v5; // rdi
  char *v6; // r14
  char v7; // bp
  __int64 v8; // r9
  __int64 v9; // r8
  unsigned __int64 v10; // rcx
  __int64 v11; // rbx
  _OWORD *v12; // r11
  _QWORD *v13; // r10
  _OWORD *v14; // r15
  __int64 v15; // rax
  char *v16; // rbx
  __m128i si128; // [rsp+20h] [rbp-58h] BYREF
  __int64 v19; // [rsp+30h] [rbp-48h]

  if ( a2 > 0x666666666666666LL )
  {
    v5 = 0;
    v4 = 10 * a2;
  }
  else
  {
    v4 = 10 * a2;
    v5 = operator new(40 * a2, (const struct std::nothrow_t *)&std::nothrow);
  }
  si128.m128i_i64[0] = (__int64)v5;
  if ( !v5 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    v19 = -1;
LABEL_7:
    v7 = 0;
    goto LABEL_14;
  }
  si128.m128i_i64[1] = (__int64)v5;
  v6 = (char *)&v5[v4];
  v19 = (__int64)&v5[v4];
  if ( v5 == (_DWORD *)-1LL )
    goto LABEL_7;
  v8 = *a1;
  v9 = 0;
  v10 = 0xCCCCCCCCCCCCCCCDuLL * ((a1[1] - *a1) >> 3);
  v7 = 1;
  if ( v10 )
  {
    do
    {
      v11 = 5 * v9;
      a2 = v8 + 8 + 40 * v9;
      v5[10 * v9] = *(_DWORD *)(v8 + 40 * v9);
      v12 = (_OWORD *)(a2 + 16);
      v13 = &v5[10 * v9 + 2];
      v14 = v13 + 2;
      if ( *(_QWORD *)a2 == a2 + 16 )
      {
        *v13 = v14;
        v13[1] = (char *)v13 + 2 * ((__int64)(*(_QWORD *)(a2 + 8) - a2 - 16) >> 1) + 16;
        *v14 = *v12;
      }
      else
      {
        *v13 = *(_QWORD *)a2;
        v13[1] = *(_QWORD *)(a2 + 8);
        *(_QWORD *)v14 = *(_QWORD *)v12;
      }
      ++v9;
      v15 = v8 + 24 + 8 * v11;
      *(_QWORD *)a2 = v15;
      *(_QWORD *)(a2 + 8) = v15;
      *(_WORD *)v12 = 0;
    }
    while ( v9 != v10 );
  }
  v16 = (char *)&v5[2 * ((a1[1] - *a1) >> 3)];
  utl::vector<Container::Manager::Image::CommandAdjustment,utl::allocator<Container::Manager::Image::CommandAdjustment>>::_Uninit(
    a1,
    a2,
    v9);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  *a1 = (__int64)v5;
  a1[1] = (__int64)v16;
  a1[2] = (__int64)v6;
  v19 = -1;
LABEL_14:
  utl::vector<Container::Manager::Image::CommandAdjustment,utl::allocator<Container::Manager::Image::CommandAdjustment>>::_Uninit(
    &si128,
    a2,
    a3);
  return v7;
}

```

## disassembly

```asm
0x14001f9f8  push    rbx
0x14001f9fa  push    rbp
0x14001f9fb  push    rsi
0x14001f9fc  push    rdi
0x14001f9fd  push    r12
0x14001f9ff  push    r14
0x14001fa01  push    r15
0x14001fa03  sub     rsp, 40h
0x14001fa07  mov     rax, 666666666666666h
0x14001fa11  lea     rbx, [rdx+rdx*4]
0x14001fa15  mov     rsi, rcx
0x14001fa18  cmp     rdx, rax
0x14001fa1b  ja      short loc_14001FA35
0x14001fa1d  shl     rbx, 3
0x14001fa21  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001fa28  mov     rcx, rbx; unsigned __int64
0x14001fa2b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14001fa30  mov     rdi, rax
0x14001fa33  jmp     short loc_14001FA3B
0x14001fa35  xor     edi, edi
0x14001fa37  shl     rbx, 3
0x14001fa3b  mov     qword ptr [rsp+78h+var_58], rdi
0x14001fa40  test    rdi, rdi
0x14001fa43  jnz     short loc_14001FA5E
0x14001fa45  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14001fa4d  movdqu  [rsp+78h+var_58], xmm0
0x14001fa53  mov     [rsp+78h+var_48], 0FFFFFFFFFFFFFFFFh
0x14001fa5c  jmp     short loc_14001FA72
0x14001fa5e  mov     qword ptr [rsp+78h+var_58+8], rdi
0x14001fa63  lea     r14, [rbx+rdi]
0x14001fa67  mov     [rsp+78h+var_48], r14
0x14001fa6c  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14001fa70  jnz     short loc_14001FA7A
0x14001fa72  xor     bpl, bpl
0x14001fa75  jmp     loc_14001FB6C
0x14001fa7a  mov     r9, [rsi]
0x14001fa7d  xor     r8d, r8d
0x14001fa80  mov     rcx, [rsi+8]
0x14001fa84  mov     r12, 0CCCCCCCCCCCCCCCDh
0x14001fa8e  sub     rcx, r9
0x14001fa91  sar     rcx, 3
0x14001fa95  imul    rcx, r12
0x14001fa99  lea     ebp, [r8+1]
0x14001fa9d  test    rcx, rcx
0x14001faa0  jz      loc_14001FB2B
0x14001faa6  lea     rbx, [r8+r8*4]
0x14001faaa  mov     eax, [r9+rbx*8]
0x14001faae  lea     rdx, [r9+8]
0x14001fab2  lea     rdx, [rdx+rbx*8]
0x14001fab6  mov     [rdi+rbx*8], eax
0x14001fab9  mov     rax, [rdx]
0x14001fabc  lea     r10, [rbx+1]
0x14001fac0  lea     r11, [rdx+10h]
0x14001fac4  lea     r10, [rdi+r10*8]
0x14001fac8  lea     r15, [r10+10h]
0x14001facc  cmp     rax, r11
0x14001facf  jnz     short loc_14001FAF9
0x14001fad1  mov     [r10], r15
0x14001fad4  mov     rax, [rdx+8]
0x14001fad8  sub     rax, rdx
0x14001fadb  sub     rax, 10h
0x14001fadf  sar     rax, 1
0x14001fae2  add     rax, 8
0x14001fae6  lea     rax, [r10+rax*2]
0x14001faea  mov     [r10+8], rax
0x14001faee  movups  xmm0, xmmword ptr [r11]
0x14001faf2  movdqu  xmmword ptr [r15], xmm0
0x14001faf7  jmp     short loc_14001FB0A
0x14001faf9  mov     [r10], rax
0x14001fafc  mov     rax, [rdx+8]
0x14001fb00  mov     [r10+8], rax
0x14001fb04  mov     rax, [r11]
0x14001fb07  mov     [r15], rax
0x14001fb0a  lea     rax, [r9+18h]
0x14001fb0e  add     r8, rbp
0x14001fb11  lea     rax, [rax+rbx*8]
0x14001fb15  mov     [rdx], rax
0x14001fb18  mov     [rdx+8], rax
0x14001fb1c  xor     eax, eax
0x14001fb1e  mov     [r11], ax
0x14001fb22  cmp     r8, rcx
0x14001fb25  jnz     loc_14001FAA6
0x14001fb2b  mov     rax, [rsi+8]
0x14001fb2f  mov     rcx, rsi
0x14001fb32  sub     rax, [rsi]
0x14001fb35  sar     rax, 3
0x14001fb39  imul    rax, r12
0x14001fb3d  lea     rax, [rax+rax*4]
0x14001fb41  lea     rbx, [rdi+rax*8]
0x14001fb45  call    ?_Uninit@?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@utl@@@utl@@AEAAXXZ; utl::vector<Container::Manager::Image::CommandAdjustment,utl::allocator<Container::Manager::Image::CommandAdjustment>>::_Uninit(void)
0x14001fb4a  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14001fb52  movdqu  [rsp+78h+var_58], xmm0
0x14001fb58  mov     [rsi], rdi
0x14001fb5b  mov     [rsi+8], rbx
0x14001fb5f  mov     [rsi+10h], r14
0x14001fb63  mov     [rsp+78h+var_48], 0FFFFFFFFFFFFFFFFh
0x14001fb6c  lea     rcx, [rsp+78h+var_58]
0x14001fb71  call    ?_Uninit@?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@utl@@@utl@@AEAAXXZ; utl::vector<Container::Manager::Image::CommandAdjustment,utl::allocator<Container::Manager::Image::CommandAdjustment>>::_Uninit(void)
0x14001fb76  mov     al, bpl
0x14001fb79  add     rsp, 40h
0x14001fb7d  pop     r15
0x14001fb7f  pop     r14
0x14001fb81  pop     r12
0x14001fb83  pop     rdi
0x14001fb84  pop     rsi
0x14001fb85  pop     rbp
0x14001fb86  pop     rbx
0x14001fb87  retn
```
