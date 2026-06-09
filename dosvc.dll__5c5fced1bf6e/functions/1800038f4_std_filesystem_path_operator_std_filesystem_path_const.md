# std::filesystem::path::operator/=(std::filesystem::path const &)

- ea: `0x1800038f4`
- end: `0x180003b62`
- name: `??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z`
- size: `622`
- prototype: `std::filesystem *__fastcall(std::filesystem *Src, std::filesystem *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003700`

## callees

- `0x1800038f4`
- `0x180003eb0`
- `0x1800041c4`
- `0x180008e20`
- `0x180008fb8`
- `0x18000a310`
- `0x18000a368`
- `0x18000a6e0`

## pseudocode

```c
std::filesystem *__fastcall std::filesystem::path::operator/=(
        std::filesystem *Src,
        std::filesystem *this,
        const unsigned __int16 *a3)
{
  std::filesystem *v3; // rsi
  std::filesystem *v5; // rcx
  unsigned __int64 v6; // r11
  size_t v7; // r14
  __int64 v8; // rdx
  std::filesystem *v9; // r12
  const unsigned __int16 *root_name_end; // rax
  const unsigned __int16 *v11; // rcx
  std::filesystem *v12; // rbx
  unsigned __int64 v13; // rdx
  __int64 v14; // rax
  const unsigned __int16 *v15; // rbp
  std::filesystem *v16; // r11
  const unsigned __int16 *v17; // r14
  const unsigned __int16 *v18; // rbx
  const unsigned __int16 *v19; // r8
  std::filesystem *v20; // r11
  const unsigned __int16 *v21; // rax
  const wchar_t *v22; // r11
  const unsigned __int16 *v23; // r15
  unsigned __int64 v24; // rax
  unsigned __int64 v25; // rbp
  size_t v26; // r8
  std::filesystem *v27; // rbp
  __int64 v28; // rbx
  __int64 v29; // rcx
  unsigned __int64 v30; // r14
  bool v31; // cc
  __int64 v32; // rsi
  std::filesystem *v33; // rbx
  unsigned __int64 v35; // [rsp+78h] [rbp+10h]
  const unsigned __int16 *v36; // [rsp+80h] [rbp+18h]

  v3 = this;
  if ( *((_QWORD *)this + 3) <= 7u )
    v5 = this;
  else
    v5 = *(std::filesystem **)this;
  v6 = *((_QWORD *)this + 2);
  v7 = 2 * v6;
  v8 = (__int64)(2 * v6) >> 1;
  if ( v8 < 2 || (*(_DWORD *)v5 & 0xFFFFFFDF) - 3801153 >= 0x1A )
  {
    root_name_end = std::filesystem::_Find_root_name_end(v5, (const unsigned __int16 *const)((char *)v5 + v7), a3);
    if ( v11 == root_name_end )
    {
LABEL_9:
      if ( *((_QWORD *)Src + 3) <= 7u )
        v9 = Src;
      else
        v9 = *(std::filesystem **)Src;
      v14 = *((_QWORD *)Src + 2);
      v15 = (const unsigned __int16 *)((char *)v9 + 2 * v14);
      v36 = v15;
      if ( *((_QWORD *)v3 + 3) <= 7u )
        v16 = v3;
      else
        v16 = *(std::filesystem **)v3;
      v17 = (const unsigned __int16 *)((char *)v16 + v7);
      v18 = std::filesystem::_Find_root_name_end(v9, (const unsigned __int16 *const)v9 + v14, a3);
      v21 = std::filesystem::_Find_root_name_end(v20, v17, v19);
      v23 = v21;
      if ( v22 != v21 )
      {
        v24 = v21 - v22;
        v25 = ((char *)v18 - (char *)v9) >> 1;
        v35 = v24;
        v26 = v25;
        if ( v24 < v25 )
          v26 = v24;
        if ( wmemcmp((const wchar_t *)v9, v22, v26) || v25 < v35 || v25 > v35 )
        {
          if ( Src == v3 )
            return Src;
          v13 = *((_QWORD *)v3 + 2);
          if ( *((_QWORD *)v3 + 3) > 7u )
            v3 = *(std::filesystem **)v3;
          if ( v13 <= *((_QWORD *)Src + 3) )
          {
            if ( *((_QWORD *)Src + 3) <= 7u )
              v27 = Src;
            else
              v27 = *(std::filesystem **)Src;
            v28 = 2 * v13;
            *((_QWORD *)Src + 2) = v13;
            memmove_0(v27, v3, 2 * v13);
            *(_WORD *)((char *)v27 + v28) = 0;
            return Src;
          }
LABEL_21:
          ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
            Src,
            v13,
            a3,
            v3);
          return Src;
        }
        v15 = v36;
      }
      if ( v23 != v17 && (*v23 == 92 || *v23 == 47) )
      {
        std::wstring::erase(Src, ((char *)v18 - (char *)v9) >> 1);
        goto LABEL_51;
      }
      if ( v18 == v15 )
      {
        if ( (__int64)(((char *)v18 - (char *)v9) & 0xFFFFFFFFFFFFFFFEuLL) < 6 )
          goto LABEL_51;
      }
      else if ( *(v15 - 1) == 92 || *(v15 - 1) == 47 )
      {
LABEL_51:
        v29 = *((_QWORD *)Src + 2);
        v30 = v17 - v23;
        if ( v30 > *((_QWORD *)Src + 3) - v29 )
        {
          ____Reallocate_grow_by_V_lambda_1___1_____Append_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG_K___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_G_01_AEAAAEAV01_QEBG0_Z_PEBG_K_Z(
            Src,
            v30);
        }
        else
        {
          v31 = *((_QWORD *)Src + 3) <= 7u;
          v32 = v30 + v29;
          *((_QWORD *)Src + 2) = v30 + v29;
          if ( v31 )
            v33 = Src;
          else
            v33 = *(std::filesystem **)Src;
          memmove_0((char *)v33 + 2 * v29, v23, 2 * v30);
          *((_WORD *)v33 + v32) = 0;
        }
        return Src;
      }
      std::wstring::push_back(Src);
      goto LABEL_51;
    }
  }
  else if ( v8 < 3 || *((_WORD *)v5 + 2) != 92 && *((_WORD *)v5 + 2) != 47 )
  {
    goto LABEL_9;
  }
  if ( Src == v3 )
    return Src;
  if ( *((_QWORD *)v3 + 3) > 7u )
    v3 = *(std::filesystem **)v3;
  if ( v6 > *((_QWORD *)Src + 3) )
  {
    v13 = v6;
    goto LABEL_21;
  }
  if ( *((_QWORD *)Src + 3) <= 7u )
    v12 = Src;
  else
    v12 = *(std::filesystem **)Src;
  *((_QWORD *)Src + 2) = v6;
  memmove_0(v12, v3, v7);
  *(_WORD *)((char *)v12 + v7) = 0;
  return Src;
}

```

## disassembly

```asm
0x1800038f4  mov     [rsp+arg_0], rbx
0x1800038f9  push    rbp
0x1800038fa  push    rsi
0x1800038fb  push    rdi
0x1800038fc  push    r12
0x1800038fe  push    r13
0x180003900  push    r14
0x180003902  push    r15
0x180003904  sub     rsp, 30h
0x180003908  cmp     qword ptr [rdx+18h], 7
0x18000390d  mov     rsi, rdx
0x180003910  mov     rdi, rcx
0x180003913  jbe     short loc_18000391A
0x180003915  mov     rcx, [rdx]
0x180003918  jmp     short loc_18000391D
0x18000391a  mov     rcx, rsi; this
0x18000391d  mov     r11, [rdx+10h]
0x180003921  lea     r14, [r11+r11]
0x180003925  mov     rdx, r14
0x180003928  sar     rdx, 1
0x18000392b  cmp     rdx, 2
0x18000392f  jl      short loc_180003960
0x180003931  mov     eax, [rcx]
0x180003933  and     eax, 0FFFFFFDFh
0x180003936  sub     eax, 3A0041h
0x18000393b  cmp     eax, 1Ah
0x18000393e  jnb     short loc_180003960
0x180003940  cmp     rdx, 3
0x180003944  jl      short loc_180003954
0x180003946  cmp     word ptr [rcx+4], 5Ch ; '\'
0x18000394b  jz      short loc_18000396E
0x18000394d  cmp     word ptr [rcx+4], 2Fh ; '/'
0x180003952  jz      short loc_18000396E
0x180003954  cmp     qword ptr [rdi+18h], 7
0x180003959  jbe     short loc_1800039C8
0x18000395b  mov     r12, [rdi]
0x18000395e  jmp     short loc_1800039CB
0x180003960  lea     rdx, [r14+rcx]; unsigned __int16 *
0x180003964  call    ?_Find_root_name_end@filesystem@std@@YAPEBGQEBG0@Z; std::filesystem::_Find_root_name_end(ushort const * const,ushort const * const)
0x180003969  cmp     rcx, rax
0x18000396c  jz      short loc_180003954
0x18000396e  cmp     rdi, rsi
0x180003971  jz      loc_180003B4A
0x180003977  cmp     qword ptr [rsi+18h], 7
0x18000397c  jbe     short loc_180003981
0x18000397e  mov     rsi, [rsi]
0x180003981  cmp     r11, [rdi+18h]
0x180003985  ja      short loc_1800039B5
0x180003987  cmp     qword ptr [rdi+18h], 7
0x18000398c  jbe     short loc_180003993
0x18000398e  mov     rbx, [rdi]
0x180003991  jmp     short loc_180003996
0x180003993  mov     rbx, rdi
0x180003996  mov     r8, r14; Size
0x180003999  mov     [rdi+10h], r11
0x18000399d  mov     rdx, rsi; Src
0x1800039a0  mov     rcx, rbx; void *
0x1800039a3  call    memmove_0
0x1800039a8  xor     r13d, r13d
0x1800039ab  mov     [r14+rbx], r13w
0x1800039b0  jmp     loc_180003B4A
0x1800039b5  mov     rdx, r11
0x1800039b8  mov     r9, rsi
0x1800039bb  mov     rcx, rdi
0x1800039be  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x1800039c3  jmp     loc_180003B4A
0x1800039c8  mov     r12, rdi
0x1800039cb  cmp     qword ptr [rsi+18h], 7
0x1800039d0  mov     rax, [rdi+10h]
0x1800039d4  lea     rbp, [r12+rax*2]
0x1800039d8  mov     [rsp+68h+arg_10], rbp
0x1800039e0  jbe     short loc_1800039E7
0x1800039e2  mov     r11, [rsi]
0x1800039e5  jmp     short loc_1800039EA
0x1800039e7  mov     r11, rsi
0x1800039ea  mov     rdx, rbp; unsigned __int16 *
0x1800039ed  mov     rcx, r12; this
0x1800039f0  add     r14, r11
0x1800039f3  call    ?_Find_root_name_end@filesystem@std@@YAPEBGQEBG0@Z; std::filesystem::_Find_root_name_end(ushort const * const,ushort const * const)
0x1800039f8  mov     rdx, r14; unsigned __int16 *
0x1800039fb  mov     rcx, r11; this
0x1800039fe  mov     rbx, rax
0x180003a01  call    ?_Find_root_name_end@filesystem@std@@YAPEBGQEBG0@Z; std::filesystem::_Find_root_name_end(ushort const * const,ushort const * const)
0x180003a06  xor     r13d, r13d
0x180003a09  mov     r15, rax
0x180003a0c  cmp     r11, rax
0x180003a0f  jz      loc_180003AA3
0x180003a15  sub     rax, r11
0x180003a18  mov     rbp, rbx
0x180003a1b  sar     rax, 1
0x180003a1e  sub     rbp, r12
0x180003a21  sar     rbp, 1
0x180003a24  mov     rdx, r11; S2
0x180003a27  cmp     rax, rbp
0x180003a2a  mov     [rsp+68h+arg_8], rax
0x180003a2f  mov     r8, rbp
0x180003a32  mov     rcx, r12; S1
0x180003a35  cmovb   r8, rax; N
0x180003a39  call    wmemcmp
0x180003a3e  test    eax, eax
0x180003a40  jnz     short loc_180003A4B
0x180003a42  cmp     rbp, [rsp+68h+arg_8]
0x180003a47  jb      short loc_180003A4B
0x180003a49  jbe     short loc_180003A9B
0x180003a4b  cmp     rdi, rsi
0x180003a4e  jz      loc_180003B4A
0x180003a54  cmp     qword ptr [rsi+18h], 7
0x180003a59  mov     rdx, [rsi+10h]
0x180003a5d  jbe     short loc_180003A62
0x180003a5f  mov     rsi, [rsi]
0x180003a62  cmp     rdx, [rdi+18h]
0x180003a66  ja      loc_1800039B8
0x180003a6c  cmp     qword ptr [rdi+18h], 7
0x180003a71  jbe     short loc_180003A78
0x180003a73  mov     rbp, [rdi]
0x180003a76  jmp     short loc_180003A7B
0x180003a78  mov     rbp, rdi
0x180003a7b  lea     rbx, [rdx+rdx]
0x180003a7f  mov     [rdi+10h], rdx
0x180003a83  mov     r8, rbx; Size
0x180003a86  mov     rdx, rsi; Src
0x180003a89  mov     rcx, rbp; void *
0x180003a8c  call    memmove_0
0x180003a91  mov     [rbx+rbp], r13w
0x180003a96  jmp     loc_180003B4A
0x180003a9b  mov     rbp, [rsp+68h+arg_10]
0x180003aa3  cmp     r15, r14
0x180003aa6  jz      short loc_180003AC9
0x180003aa8  cmp     word ptr [r15], 5Ch ; '\'
0x180003aad  jz      short loc_180003AB6
0x180003aaf  cmp     word ptr [r15], 2Fh ; '/'
0x180003ab4  jnz     short loc_180003AC9
0x180003ab6  sub     rbx, r12
0x180003ab9  mov     rcx, rdi
0x180003abc  sar     rbx, 1
0x180003abf  mov     rdx, rbx
0x180003ac2  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K@Z; std::wstring::erase(unsigned __int64)
0x180003ac7  jmp     short loc_180003AF3
0x180003ac9  cmp     rbx, rbp
0x180003acc  jnz     short loc_180003ADD
0x180003ace  sub     rbx, r12
0x180003ad1  and     rbx, 0FFFFFFFFFFFFFFFEh
0x180003ad5  cmp     rbx, 6
0x180003ad9  jge     short loc_180003AEB
0x180003adb  jmp     short loc_180003AF3
0x180003add  cmp     word ptr [rbp-2], 5Ch ; '\'
0x180003ae2  jz      short loc_180003AF3
0x180003ae4  cmp     word ptr [rbp-2], 2Fh ; '/'
0x180003ae9  jz      short loc_180003AF3
0x180003aeb  mov     rcx, rdi
0x180003aee  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x180003af3  mov     rcx, [rdi+10h]
0x180003af7  sub     r14, r15
0x180003afa  mov     rax, [rdi+18h]
0x180003afe  sar     r14, 1
0x180003b01  sub     rax, rcx
0x180003b04  cmp     r14, rax
0x180003b07  ja      short loc_180003B37
0x180003b09  cmp     qword ptr [rdi+18h], 7
0x180003b0e  lea     rsi, [r14+rcx]
0x180003b12  mov     [rdi+10h], rsi
0x180003b16  jbe     short loc_180003B1D
0x180003b18  mov     rbx, [rdi]
0x180003b1b  jmp     short loc_180003B20
0x180003b1d  mov     rbx, rdi
0x180003b20  lea     r8, [r14+r14]; Size
0x180003b24  mov     rdx, r15; Src
0x180003b27  lea     rcx, [rbx+rcx*2]; void *
0x180003b2b  call    memmove_0
0x180003b30  mov     [rbx+rsi*2], r13w
0x180003b35  jmp     short loc_180003B4A
0x180003b37  mov     r9, r15
0x180003b3a  mov     [rsp+68h+var_48], r14; __int64
0x180003b3f  mov     rdx, r14
0x180003b42  mov     rcx, rdi; Src
0x180003b45  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@G@01@AEAAAEAV01@QEBG0@Z@PEBG_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64>(unsigned __int64,`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64)
0x180003b4a  mov     rbx, [rsp+68h+arg_0]
0x180003b4f  mov     rax, rdi
0x180003b52  add     rsp, 30h
0x180003b56  pop     r15
0x180003b58  pop     r14
0x180003b5a  pop     r13
0x180003b5c  pop     r12
0x180003b5e  pop     rdi
0x180003b5f  pop     rsi
0x180003b60  pop     rbp
0x180003b61  retn
```
