# std::filesystem::path::operator/=(std::filesystem::path const &)

- ea: `0x1800091d8`
- end: `0x1800094a9`
- name: `??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z`
- size: `721`
- prototype: `std::filesystem *__fastcall(std::filesystem *Src, std::filesystem *this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180008f94`

## callees

- `0x18000773c`
- `0x1800079a8`
- `0x180007da4`
- `0x1800091d8`
- `0x18000a468`
- `0x18000aa54`
- `0x18000b134`
- `0x18000d5c0`

## pseudocode

```c
std::filesystem *__fastcall std::filesystem::path::operator/=(std::filesystem *Src, std::filesystem *this)
{
  std::filesystem *v2; // rsi
  std::filesystem *v4; // rcx
  unsigned __int64 v5; // r11
  __int64 v6; // r8
  size_t v7; // r14
  __int64 v8; // rdx
  std::filesystem *v9; // r12
  const unsigned __int16 *root_name_end; // rax
  const unsigned __int16 *v11; // rcx
  std::filesystem *v12; // rbx
  unsigned __int64 v13; // rdx
  std::filesystem *v14; // r11
  const unsigned __int16 *v15; // rbx
  const unsigned __int16 *v16; // rbp
  const unsigned __int16 *v17; // r8
  std::filesystem *v18; // r11
  const unsigned __int16 *v19; // rax
  __int64 v20; // rcx
  const wchar_t *v21; // r11
  __int64 v22; // r14
  const unsigned __int16 *v23; // r13
  unsigned __int64 v24; // rax
  size_t v25; // r8
  std::filesystem *v26; // rbp
  __int64 v27; // rbx
  unsigned __int64 v28; // rbp
  std::filesystem *v29; // rax
  unsigned __int64 v30; // rcx
  std::filesystem *v31; // rax
  __int64 v32; // rcx
  unsigned __int64 v33; // rbx
  bool v34; // cc
  __int64 v35; // rbp
  std::filesystem *v36; // rsi
  unsigned __int64 v38; // [rsp+78h] [rbp+10h]
  unsigned __int64 v39; // [rsp+80h] [rbp+18h]
  const unsigned __int16 *v40; // [rsp+88h] [rbp+20h]

  v2 = this;
  if ( *((_QWORD *)this + 3) <= 7u )
    v4 = this;
  else
    v4 = *(std::filesystem **)this;
  v5 = *((_QWORD *)this + 2);
  v6 = 92;
  v7 = 2 * v5;
  v8 = (__int64)(2 * v5) >> 1;
  if ( v8 < 2 || (*(_DWORD *)v4 & 0xFFFFFFDF) - 3801153 >= 0x1A )
  {
    root_name_end = std::filesystem::_Find_root_name_end(
                      v4,
                      (const unsigned __int16 *const)((char *)v4 + v7),
                      (const unsigned __int16 *const)0x5C);
    if ( v11 == root_name_end )
      goto LABEL_9;
  }
  else if ( v8 < 3 || *((_WORD *)v4 + 2) != 92 && *((_WORD *)v4 + 2) != 47 )
  {
LABEL_9:
    if ( *((_QWORD *)Src + 3) <= 7u )
      v9 = Src;
    else
      v9 = *(std::filesystem **)Src;
    v40 = (const unsigned __int16 *)((char *)v9 + 2 * *((_QWORD *)Src + 2));
    if ( *((_QWORD *)v2 + 3) <= 7u )
      v14 = v2;
    else
      v14 = *(std::filesystem **)v2;
    v15 = (const unsigned __int16 *)((char *)v14 + v7);
    v16 = std::filesystem::_Find_root_name_end(
            v9,
            (const unsigned __int16 *const)v9 + *((_QWORD *)Src + 2),
            (const unsigned __int16 *const)v6);
    v19 = std::filesystem::_Find_root_name_end(v18, v15, v17);
    v22 = (char *)v16 - (char *)v9;
    v23 = v19;
    if ( v21 != v19 )
    {
      v24 = v19 - v21;
      v25 = v22 >> 1;
      v39 = v22 >> 1;
      v38 = v24;
      if ( v24 < v22 >> 1 )
        v25 = v24;
      if ( wmemcmp((const wchar_t *)v9, v21, v25) || v39 < v38 || v39 > v38 )
      {
        if ( Src == v2 )
          return Src;
        v13 = *((_QWORD *)v2 + 2);
        if ( *((_QWORD *)v2 + 3) > 7u )
          v2 = *(std::filesystem **)v2;
        if ( v13 <= *((_QWORD *)Src + 3) )
        {
          if ( *((_QWORD *)Src + 3) <= 7u )
            v26 = Src;
          else
            v26 = *(std::filesystem **)Src;
          v27 = 2 * v13;
          *((_QWORD *)Src + 2) = v13;
          memmove_0(v26, v2, 2 * v13);
          *(_WORD *)((char *)v26 + v27) = 0;
          return Src;
        }
LABEL_21:
        ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
          Src,
          v13,
          v6,
          v2);
        return Src;
      }
    }
    if ( v23 != v15 && (*v23 == 92 || *v23 == 47) )
    {
      v28 = ((char *)v16 - (char *)v9) >> 1;
      if ( *((_QWORD *)Src + 2) < v28 )
        std::_String_val<std::_Simple_types<unsigned short>>::_Xran(v20, 92);
      *((_QWORD *)Src + 2) = v28;
      if ( *((_QWORD *)Src + 3) <= 7u )
        v29 = Src;
      else
        v29 = *(std::filesystem **)Src;
      *((_WORD *)v29 + v28) = 0;
      goto LABEL_59;
    }
    if ( v16 == v40 )
    {
      if ( (__int64)(v22 & 0xFFFFFFFFFFFFFFFEuLL) >= 6 )
        goto LABEL_53;
    }
    else if ( *(v40 - 1) != 92 && *(v40 - 1) != 47 )
    {
LABEL_53:
      v30 = *((_QWORD *)Src + 2);
      if ( v30 >= *((_QWORD *)Src + 3) )
      {
        ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(Src);
      }
      else
      {
        *((_QWORD *)Src + 2) = v30 + 1;
        if ( *((_QWORD *)Src + 3) <= 7u )
          v31 = Src;
        else
          v31 = *(std::filesystem **)Src;
        *(_DWORD *)((char *)v31 + 2 * v30) = 92;
      }
    }
LABEL_59:
    v32 = *((_QWORD *)Src + 2);
    v33 = v15 - v23;
    if ( v33 > *((_QWORD *)Src + 3) - v32 )
    {
      ____Reallocate_grow_by_V_lambda_1___1_____Append_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG_K___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_G_01_AEAAAEAV01_QEBG0_Z_PEBG_K_Z(
        Src,
        v33);
    }
    else
    {
      v34 = *((_QWORD *)Src + 3) <= 7u;
      v35 = v32 + v33;
      *((_QWORD *)Src + 2) = v32 + v33;
      if ( v34 )
        v36 = Src;
      else
        v36 = *(std::filesystem **)Src;
      memmove_0((char *)v36 + 2 * v32, v23, 2 * v33);
      *((_WORD *)v36 + v35) = 0;
    }
    return Src;
  }
  if ( Src == v2 )
    return Src;
  if ( *((_QWORD *)v2 + 3) > 7u )
    v2 = *(std::filesystem **)v2;
  if ( v5 > *((_QWORD *)Src + 3) )
  {
    v13 = v5;
    goto LABEL_21;
  }
  if ( *((_QWORD *)Src + 3) <= 7u )
    v12 = Src;
  else
    v12 = *(std::filesystem **)Src;
  *((_QWORD *)Src + 2) = v5;
  memmove_0(v12, v2, v7);
  *(_WORD *)((char *)v12 + v7) = 0;
  return Src;
}

```

## disassembly

```asm
0x1800091d8  mov     [rsp+arg_0], rbx
0x1800091dd  push    rbp
0x1800091de  push    rsi
0x1800091df  push    rdi
0x1800091e0  push    r12
0x1800091e2  push    r13
0x1800091e4  push    r14
0x1800091e6  push    r15
0x1800091e8  sub     rsp, 30h
0x1800091ec  cmp     qword ptr [rdx+18h], 7
0x1800091f1  mov     rsi, rdx
0x1800091f4  mov     rdi, rcx
0x1800091f7  jbe     short loc_1800091FE
0x1800091f9  mov     rcx, [rdx]
0x1800091fc  jmp     short loc_180009201
0x1800091fe  mov     rcx, rsi; this
0x180009201  mov     r11, [rdx+10h]
0x180009205  mov     r8d, 5Ch ; '\'; unsigned __int16 *
0x18000920b  lea     r14, [r11+r11]
0x18000920f  mov     rdx, r14
0x180009212  sar     rdx, 1
0x180009215  cmp     rdx, 2
0x180009219  jl      short loc_18000924A
0x18000921b  mov     eax, [rcx]
0x18000921d  and     eax, 0FFFFFFDFh
0x180009220  sub     eax, 3A0041h
0x180009225  cmp     eax, 1Ah
0x180009228  jnb     short loc_18000924A
0x18000922a  cmp     rdx, 3
0x18000922e  jl      short loc_18000923E
0x180009230  cmp     [rcx+4], r8w
0x180009235  jz      short loc_180009258
0x180009237  cmp     word ptr [rcx+4], 2Fh ; '/'
0x18000923c  jz      short loc_180009258
0x18000923e  cmp     qword ptr [rdi+18h], 7
0x180009243  jbe     short loc_1800092B2
0x180009245  mov     r12, [rdi]
0x180009248  jmp     short loc_1800092B5
0x18000924a  lea     rdx, [r14+rcx]; unsigned __int16 *
0x18000924e  call    ?_Find_root_name_end@filesystem@std@@YAPEBGQEBG0@Z; std::filesystem::_Find_root_name_end(ushort const * const,ushort const * const)
0x180009253  cmp     rcx, rax
0x180009256  jz      short loc_18000923E
0x180009258  cmp     rdi, rsi
0x18000925b  jz      loc_18000948B
0x180009261  cmp     qword ptr [rsi+18h], 7
0x180009266  jbe     short loc_18000926B
0x180009268  mov     rsi, [rsi]
0x18000926b  cmp     r11, [rdi+18h]
0x18000926f  ja      short loc_18000929F
0x180009271  cmp     qword ptr [rdi+18h], 7
0x180009276  jbe     short loc_18000927D
0x180009278  mov     rbx, [rdi]
0x18000927b  jmp     short loc_180009280
0x18000927d  mov     rbx, rdi
0x180009280  mov     r8, r14; Size
0x180009283  mov     [rdi+10h], r11
0x180009287  mov     rdx, rsi; Src
0x18000928a  mov     rcx, rbx; void *
0x18000928d  call    memmove_0
0x180009292  xor     r15d, r15d
0x180009295  mov     [r14+rbx], r15w
0x18000929a  jmp     loc_18000948B
0x18000929f  mov     rdx, r11
0x1800092a2  mov     r9, rsi
0x1800092a5  mov     rcx, rdi
0x1800092a8  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x1800092ad  jmp     loc_18000948B
0x1800092b2  mov     r12, rdi
0x1800092b5  cmp     qword ptr [rsi+18h], 7
0x1800092ba  mov     rax, [rdi+10h]
0x1800092be  lea     rdx, [r12+rax*2]; unsigned __int16 *
0x1800092c2  mov     [rsp+68h+arg_18], rdx
0x1800092ca  jbe     short loc_1800092D1
0x1800092cc  mov     r11, [rsi]
0x1800092cf  jmp     short loc_1800092D4
0x1800092d1  mov     r11, rsi
0x1800092d4  mov     rcx, r12; this
0x1800092d7  lea     rbx, [r14+r11]
0x1800092db  call    ?_Find_root_name_end@filesystem@std@@YAPEBGQEBG0@Z; std::filesystem::_Find_root_name_end(ushort const * const,ushort const * const)
0x1800092e0  mov     rdx, rbx; unsigned __int16 *
0x1800092e3  mov     rcx, r11; this
0x1800092e6  mov     rbp, rax
0x1800092e9  call    ?_Find_root_name_end@filesystem@std@@YAPEBGQEBG0@Z; std::filesystem::_Find_root_name_end(ushort const * const,ushort const * const)
0x1800092ee  mov     r14, rbp
0x1800092f1  xor     r15d, r15d
0x1800092f4  sub     r14, r12
0x1800092f7  mov     r13, rax
0x1800092fa  cmp     r11, rax
0x1800092fd  jz      loc_180009396
0x180009303  sub     rax, r11
0x180009306  mov     rcx, r14
0x180009309  sar     rcx, 1
0x18000930c  mov     rdx, r11; S2
0x18000930f  sar     rax, 1
0x180009312  mov     r8, rcx
0x180009315  cmp     rax, rcx
0x180009318  mov     [rsp+68h+arg_10], rcx
0x180009320  mov     rcx, r12; S1
0x180009323  mov     [rsp+68h+arg_8], rax
0x180009328  cmovb   r8, rax; N
0x18000932c  call    wmemcmp
0x180009331  test    eax, eax
0x180009333  jnz     short loc_180009346
0x180009335  mov     rax, [rsp+68h+arg_8]
0x18000933a  cmp     [rsp+68h+arg_10], rax
0x180009342  jb      short loc_180009346
0x180009344  jbe     short loc_180009396
0x180009346  cmp     rdi, rsi
0x180009349  jz      loc_18000948B
0x18000934f  cmp     qword ptr [rsi+18h], 7
0x180009354  mov     rdx, [rsi+10h]
0x180009358  jbe     short loc_18000935D
0x18000935a  mov     rsi, [rsi]
0x18000935d  cmp     rdx, [rdi+18h]
0x180009361  ja      loc_1800092A2
0x180009367  cmp     qword ptr [rdi+18h], 7
0x18000936c  jbe     short loc_180009373
0x18000936e  mov     rbp, [rdi]
0x180009371  jmp     short loc_180009376
0x180009373  mov     rbp, rdi
0x180009376  lea     rbx, [rdx+rdx]
0x18000937a  mov     [rdi+10h], rdx
0x18000937e  mov     r8, rbx; Size
0x180009381  mov     rdx, rsi; Src
0x180009384  mov     rcx, rbp; void *
0x180009387  call    memmove_0
0x18000938c  mov     [rbx+rbp], r15w
0x180009391  jmp     loc_18000948B
0x180009396  mov     edx, 5Ch ; '\'
0x18000939b  cmp     r13, rbx
0x18000939e  jz      short loc_1800093D9
0x1800093a0  cmp     [r13+0], dx
0x1800093a5  jz      short loc_1800093AF
0x1800093a7  cmp     word ptr [r13+0], 2Fh ; '/'
0x1800093ad  jnz     short loc_1800093D9
0x1800093af  sub     rbp, r12
0x1800093b2  sar     rbp, 1
0x1800093b5  cmp     [rdi+10h], rbp
0x1800093b9  jb      loc_1800094A3
0x1800093bf  mov     [rdi+10h], rbp
0x1800093c3  cmp     qword ptr [rdi+18h], 7
0x1800093c8  jbe     short loc_1800093CF
0x1800093ca  mov     rax, [rdi]
0x1800093cd  jmp     short loc_1800093D2
0x1800093cf  mov     rax, rdi
0x1800093d2  mov     [rax+rbp*2], r15w
0x1800093d7  jmp     short loc_180009434
0x1800093d9  mov     rax, [rsp+68h+arg_18]
0x1800093e1  cmp     rbp, rax
0x1800093e4  jnz     short loc_1800093F2
0x1800093e6  and     r14, 0FFFFFFFFFFFFFFFEh
0x1800093ea  cmp     r14, 6
0x1800093ee  jl      short loc_180009434
0x1800093f0  jmp     short loc_1800093FF
0x1800093f2  cmp     [rax-2], dx
0x1800093f6  jz      short loc_180009434
0x1800093f8  cmp     word ptr [rax-2], 2Fh ; '/'
0x1800093fd  jz      short loc_180009434
0x1800093ff  mov     rcx, [rdi+10h]
0x180009403  cmp     rcx, [rdi+18h]
0x180009407  jnb     short loc_180009429
0x180009409  lea     rax, [rcx+1]
0x18000940d  mov     [rdi+10h], rax
0x180009411  cmp     qword ptr [rdi+18h], 7
0x180009416  jbe     short loc_18000941D
0x180009418  mov     rax, [rdi]
0x18000941b  jmp     short loc_180009420
0x18000941d  mov     rax, rdi
0x180009420  mov     dword ptr [rax+rcx*2], 5Ch ; '\'
0x180009427  jmp     short loc_180009434
0x180009429  mov     r9d, edx
0x18000942c  mov     rcx, rdi; Src
0x18000942f  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x180009434  mov     rcx, [rdi+10h]
0x180009438  sub     rbx, r13
0x18000943b  mov     rax, [rdi+18h]
0x18000943f  sar     rbx, 1
0x180009442  sub     rax, rcx
0x180009445  cmp     rbx, rax
0x180009448  ja      short loc_180009478
0x18000944a  cmp     qword ptr [rdi+18h], 7
0x18000944f  lea     rbp, [rcx+rbx]
0x180009453  mov     [rdi+10h], rbp
0x180009457  jbe     short loc_18000945E
0x180009459  mov     rsi, [rdi]
0x18000945c  jmp     short loc_180009461
0x18000945e  mov     rsi, rdi
0x180009461  lea     r8, [rbx+rbx]; Size
0x180009465  mov     rdx, r13; Src
0x180009468  lea     rcx, [rsi+rcx*2]; void *
0x18000946c  call    memmove_0
0x180009471  mov     [rsi+rbp*2], r15w
0x180009476  jmp     short loc_18000948B
0x180009478  mov     r9, r13
0x18000947b  mov     [rsp+68h+var_48], rbx; __int64
0x180009480  mov     rdx, rbx
0x180009483  mov     rcx, rdi; Src
0x180009486  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@G@01@AEAAAEAV01@QEBG0@Z@PEBG_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64>(unsigned __int64,`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64)
0x18000948b  mov     rbx, [rsp+68h+arg_0]
0x180009490  mov     rax, rdi
0x180009493  add     rsp, 30h
0x180009497  pop     r15
0x180009499  pop     r14
0x18000949b  pop     r13
0x18000949d  pop     r12
0x18000949f  pop     rdi
0x1800094a0  pop     rsi
0x1800094a1  pop     rbp
0x1800094a2  retn
0x1800094a3  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```
