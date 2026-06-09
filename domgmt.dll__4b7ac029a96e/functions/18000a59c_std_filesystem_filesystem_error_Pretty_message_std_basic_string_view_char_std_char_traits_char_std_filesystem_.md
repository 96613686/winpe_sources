# std::filesystem::filesystem_error::_Pretty_message(std::basic_string_view<char,std::char_traits<char>>,std::filesystem::path const &,std::filesystem::path const &)

- ea: `0x18000a59c`
- end: `0x18000a8ca`
- name: `?_Pretty_message@filesystem_error@filesystem@std@@CA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@V?$basic_string_view@DU?$char_traits@D@std@@@3@AEBVpath@23@1@Z`
- size: `814`
- prototype: `_QWORD *__fastcall(_QWORD *Src, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180008988`

## callees

- `0x1800011f4`
- `0x180001ba0`
- `0x1800075dc`
- `0x180007834`
- `0x180007c50`
- `0x180007ec0`
- `0x180008d20`
- `0x18000a59c`
- `0x18000d5c0`

## pseudocode

```c
_QWORD *__fastcall std::filesystem::filesystem_error::_Pretty_message(_QWORD *Src, __int64 a2, _QWORD *a3, _QWORD *a4)
{
  UINT v8; // r14d
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  size_t v11; // rsi
  __int64 v12; // rbx
  __int64 v13; // rbx
  _QWORD *v14; // r14
  __int64 v15; // rbx
  _QWORD *v16; // rsi
  size_t v17; // rbx
  void **v18; // r9
  __int64 v19; // rsi
  _QWORD *v20; // r14
  __int64 v21; // rcx
  char *v22; // rax
  size_t v23; // rsi
  void **v24; // r9
  __int64 v25; // rcx
  _QWORD *v26; // rax
  char *v27; // rbx
  unsigned __int64 v28; // rcx
  _QWORD *v29; // rax
  _QWORD *v31; // [rsp+40h] [rbp-29h] BYREF
  __int64 v32; // [rsp+48h] [rbp-21h]
  _QWORD *v33; // [rsp+50h] [rbp-19h]
  void *v34[2]; // [rsp+58h] [rbp-11h] BYREF
  size_t v35; // [rsp+68h] [rbp-1h]
  unsigned __int64 v36; // [rsp+70h] [rbp+7h]
  void *Srca[2]; // [rsp+78h] [rbp+Fh] BYREF
  size_t Size; // [rsp+88h] [rbp+1Fh]
  unsigned __int64 v39; // [rsp+90h] [rbp+27h]

  v33 = Src;
  *(_OWORD *)Src = 0;
  Src[2] = 0;
  Src[3] = 15;
  *(_BYTE *)Src = 0;
  v8 = _std_fs_code_page();
  if ( a3[3] <= 7u )
    v9 = a3;
  else
    v9 = (_QWORD *)*a3;
  v31 = v9;
  v32 = a3[2];
  std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(
    Srca,
    v8,
    (__int64)&v31);
  if ( a4[3] <= 7u )
    v10 = a4;
  else
    v10 = (_QWORD *)*a4;
  v31 = v10;
  v32 = a4[2];
  std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(
    v34,
    v8,
    (__int64)&v31);
  v11 = *(_QWORD *)(a2 + 8);
  if ( Src[3] < v11 + v35 + Size + (v35 != 0 ? 8LL : 4LL) )
  {
    v12 = Src[2];
    ____Reallocate_grow_by_V_lambda_1___1__reserve___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAX_K_Z___V___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__reserve_01_QEAAX0_Z__Z(Src);
    Src[2] = v12;
  }
  v13 = Src[2];
  if ( v11 > Src[3] - v13 )
  {
    ____Reallocate_grow_by_V_lambda_1___1_____Append_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV23_QEBD_K_Z_PEBD_K___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_D_01_AEAAAEAV01_QEBD0_Z_PEBD_K_Z(
      Src,
      v11);
  }
  else
  {
    Src[2] = v13 + v11;
    if ( Src[3] <= 0xFu )
      v14 = Src;
    else
      v14 = (_QWORD *)*Src;
    memmove_0((char *)v14 + v13, *(const void **)a2, v11);
    *((_BYTE *)v14 + v13 + v11) = 0;
  }
  v15 = Src[2];
  if ( (unsigned __int64)(Src[3] - v15) < 3 )
  {
    ____Reallocate_grow_by_V_lambda_1___1_____Append_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV23_QEBD_K_Z_PEBD_K___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_D_01_AEAAAEAV01_QEBD0_Z_PEBD_K_Z(
      Src,
      3u);
  }
  else
  {
    Src[2] = v15 + 3;
    if ( Src[3] <= 0xFu )
      v16 = Src;
    else
      v16 = (_QWORD *)*Src;
    memmove_0((char *)v16 + v15, ": \"", 3u);
    *((_BYTE *)v16 + v15 + 3) = 0;
  }
  v17 = Size;
  v18 = Srca;
  if ( v39 > 0xF )
    v18 = (void **)Srca[0];
  v19 = Src[2];
  if ( Size > Src[3] - v19 )
  {
    ____Reallocate_grow_by_V_lambda_1___1_____Append_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV23_QEBD_K_Z_PEBD_K___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_D_01_AEAAAEAV01_QEBD0_Z_PEBD_K_Z(
      Src,
      Size);
  }
  else
  {
    Src[2] = Size + v19;
    if ( Src[3] <= 0xFu )
      v20 = Src;
    else
      v20 = (_QWORD *)*Src;
    memmove_0((char *)v20 + v19, v18, v17);
    *((_BYTE *)v20 + v17 + v19) = 0;
  }
  if ( v35 )
  {
    v21 = Src[2];
    if ( (unsigned __int64)(Src[3] - v21) < 4 )
    {
      ____Reallocate_grow_by_V_lambda_1___1_____Append_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV23_QEBD_K_Z_PEBD_K___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_D_01_AEAAAEAV01_QEBD0_Z_PEBD_K_Z(
        Src,
        4u);
    }
    else
    {
      Src[2] = v21 + 4;
      if ( Src[3] <= 0xFu )
        v22 = (char *)Src;
      else
        v22 = (char *)*Src;
      strcpy(&v22[v21], "\", \"");
    }
    v23 = v35;
    v24 = v34;
    if ( v36 > 0xF )
      v24 = (void **)v34[0];
    v25 = Src[2];
    if ( v35 > Src[3] - v25 )
    {
      ____Reallocate_grow_by_V_lambda_1___1_____Append_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV23_QEBD_K_Z_PEBD_K___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_D_01_AEAAAEAV01_QEBD0_Z_PEBD_K_Z(
        Src,
        v35);
    }
    else
    {
      Src[2] = v35 + v25;
      if ( Src[3] <= 0xFu )
        v26 = Src;
      else
        v26 = (_QWORD *)*Src;
      v27 = (char *)v26 + v25;
      memmove_0((char *)v26 + v25, v24, v23);
      v27[v23] = 0;
    }
  }
  v28 = Src[2];
  if ( v28 >= Src[3] )
  {
    ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
  }
  else
  {
    Src[2] = v28 + 1;
    if ( Src[3] <= 0xFu )
      v29 = Src;
    else
      v29 = (_QWORD *)*Src;
    *(_WORD *)((char *)v29 + v28) = 34;
  }
  std::string::~string((char **)v34);
  std::string::~string((char **)Srca);
  return Src;
}

```

## disassembly

```asm
0x18000a59c  mov     [rsp-8+arg_10], rbx
0x18000a5a1  push    rbp
0x18000a5a2  push    rsi
0x18000a5a3  push    rdi
0x18000a5a4  push    r14
0x18000a5a6  push    r15
0x18000a5a8  lea     rbp, [rsp-37h]
0x18000a5ad  sub     rsp, 0A0h
0x18000a5b4  mov     rax, cs:__security_cookie
0x18000a5bb  xor     rax, rsp
0x18000a5be  mov     [rbp+57h+var_28], rax
0x18000a5c2  mov     rsi, r9
0x18000a5c5  mov     rbx, r8
0x18000a5c8  mov     r15, rdx
0x18000a5cb  mov     rdi, rcx
0x18000a5ce  mov     [rbp+57h+var_70], rcx
0x18000a5d2  mov     [rbp+57h+var_90], 0
0x18000a5d9  xorps   xmm0, xmm0
0x18000a5dc  movups  xmmword ptr [rcx], xmm0
0x18000a5df  mov     qword ptr [rcx+10h], 0
0x18000a5e7  mov     qword ptr [rcx+18h], 0Fh
0x18000a5ef  mov     byte ptr [rcx], 0
0x18000a5f2  mov     [rbp+57h+var_90], 1
0x18000a5f9  call    __std_fs_code_page
0x18000a5fe  mov     r14d, eax
0x18000a601  cmp     qword ptr [rbx+18h], 7
0x18000a606  jbe     short loc_18000A60D
0x18000a608  mov     rax, [rbx]
0x18000a60b  jmp     short loc_18000A610
0x18000a60d  mov     rax, rbx
0x18000a610  mov     [rbp+57h+var_80], rax
0x18000a614  mov     rax, [rbx+10h]
0x18000a618  mov     [rbp+57h+var_78], rax
0x18000a61c  lea     r8, [rbp+57h+var_80]
0x18000a620  mov     edx, r14d; CodePage
0x18000a623  lea     rcx, [rbp+57h+Src]; Src
0x18000a627  call    ??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@D@1@@Z; std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::basic_string_view<ushort>,std::allocator<char> const &)
0x18000a62c  nop
0x18000a62d  cmp     qword ptr [rsi+18h], 7
0x18000a632  jbe     short loc_18000A639
0x18000a634  mov     rax, [rsi]
0x18000a637  jmp     short loc_18000A63C
0x18000a639  mov     rax, rsi
0x18000a63c  mov     [rbp+57h+var_80], rax
0x18000a640  mov     rax, [rsi+10h]
0x18000a644  mov     [rbp+57h+var_78], rax
0x18000a648  lea     r8, [rbp+57h+var_80]
0x18000a64c  mov     edx, r14d; CodePage
0x18000a64f  lea     rcx, [rbp+57h+var_68]; Src
0x18000a653  call    ??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@D@1@@Z; std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::basic_string_view<ushort>,std::allocator<char> const &)
0x18000a658  nop
0x18000a659  mov     rax, [rbp+57h+var_58]
0x18000a65d  neg     rax
0x18000a660  sbb     rcx, rcx
0x18000a663  and     ecx, 4
0x18000a666  lea     rdx, [rcx+4]
0x18000a66a  mov     rsi, [r15+8]
0x18000a66e  add     rdx, [rbp+57h+Size]
0x18000a672  add     rdx, [rbp+57h+var_58]
0x18000a676  add     rdx, rsi
0x18000a679  cmp     [rdi+18h], rdx
0x18000a67d  jnb     short loc_18000A692
0x18000a67f  mov     rbx, [rdi+10h]
0x18000a683  sub     rdx, rbx
0x18000a686  mov     rcx, rdi; Src
0x18000a689  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??reserve@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K@Z@$$V@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??reserve@01@QEAAX0@Z@@Z; std::string::_Reallocate_grow_by<`std::string::reserve(unsigned __int64)'::`2'::_lambda_1_,>(unsigned __int64,`std::string::reserve(unsigned __int64)'::`2'::_lambda_1_)
0x18000a68e  mov     [rdi+10h], rbx
0x18000a692  mov     rbx, [rdi+10h]
0x18000a696  mov     rax, [rdi+18h]
0x18000a69a  sub     rax, rbx
0x18000a69d  cmp     rsi, rax
0x18000a6a0  ja      short loc_18000A6D2
0x18000a6a2  lea     rax, [rbx+rsi]
0x18000a6a6  mov     [rdi+10h], rax
0x18000a6aa  cmp     qword ptr [rdi+18h], 0Fh
0x18000a6af  jbe     short loc_18000A6B6
0x18000a6b1  mov     r14, [rdi]
0x18000a6b4  jmp     short loc_18000A6B9
0x18000a6b6  mov     r14, rdi
0x18000a6b9  lea     rcx, [r14+rbx]; void *
0x18000a6bd  mov     r8, rsi; Size
0x18000a6c0  mov     rdx, [r15]; Src
0x18000a6c3  call    memmove_0
0x18000a6c8  lea     rax, [r14+rbx]
0x18000a6cc  mov     byte ptr [rax+rsi], 0
0x18000a6d0  jmp     short loc_18000A6E5
0x18000a6d2  mov     [rsp+0C0h+var_A0], rsi; Size
0x18000a6d7  mov     r9, [r15]
0x18000a6da  mov     rdx, rsi
0x18000a6dd  mov     rcx, rdi; Src
0x18000a6e0  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV23@QEBD_K@Z@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@D@01@AEAAAEAV01@QEBD0@Z@PEBD_K@Z; std::string::_Reallocate_grow_by<`std::string::_Append<char>(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *,unsigned __int64>(unsigned __int64,`std::string::_Append<char>(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *,unsigned __int64)
0x18000a6e5  mov     rbx, [rdi+10h]
0x18000a6e9  mov     rax, [rdi+18h]
0x18000a6ed  sub     rax, rbx
0x18000a6f0  mov     edx, 3
0x18000a6f5  cmp     rax, rdx
0x18000a6f8  jb      short loc_18000A72B
0x18000a6fa  lea     rax, [rbx+3]
0x18000a6fe  mov     [rdi+10h], rax
0x18000a702  cmp     qword ptr [rdi+18h], 0Fh
0x18000a707  jbe     short loc_18000A70E
0x18000a709  mov     rsi, [rdi]
0x18000a70c  jmp     short loc_18000A711
0x18000a70e  mov     rsi, rdi
0x18000a711  lea     rcx, [rsi+rbx]; void *
0x18000a715  mov     r8, rdx; Size
0x18000a718  lea     rdx, asc_180010878; ": \""
0x18000a71f  call    memmove_0
0x18000a724  mov     byte ptr [rsi+rbx+3], 0
0x18000a729  jmp     short loc_18000A73F
0x18000a72b  mov     [rsp+0C0h+var_A0], rdx; Size
0x18000a730  lea     r9, asc_180010878; ": \""
0x18000a737  mov     rcx, rdi; Src
0x18000a73a  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV23@QEBD_K@Z@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@D@01@AEAAAEAV01@QEBD0@Z@PEBD_K@Z; std::string::_Reallocate_grow_by<`std::string::_Append<char>(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *,unsigned __int64>(unsigned __int64,`std::string::_Append<char>(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *,unsigned __int64)
0x18000a73f  mov     rbx, [rbp+57h+Size]
0x18000a743  lea     r9, [rbp+57h+Src]
0x18000a747  cmp     [rbp+57h+var_30], 0Fh
0x18000a74c  cmova   r9, [rbp+57h+Src]
0x18000a751  mov     rsi, [rdi+10h]
0x18000a755  mov     rax, [rdi+18h]
0x18000a759  sub     rax, rsi
0x18000a75c  cmp     rbx, rax
0x18000a75f  ja      short loc_18000A791
0x18000a761  lea     rax, [rbx+rsi]
0x18000a765  mov     [rdi+10h], rax
0x18000a769  cmp     qword ptr [rdi+18h], 0Fh
0x18000a76e  jbe     short loc_18000A775
0x18000a770  mov     r14, [rdi]
0x18000a773  jmp     short loc_18000A778
0x18000a775  mov     r14, rdi
0x18000a778  lea     rcx, [r14+rsi]; void *
0x18000a77c  mov     r8, rbx; Size
0x18000a77f  mov     rdx, r9; Src
0x18000a782  call    memmove_0
0x18000a787  lea     rax, [rbx+r14]
0x18000a78b  mov     byte ptr [rax+rsi], 0
0x18000a78f  jmp     short loc_18000A7A1
0x18000a791  mov     [rsp+0C0h+var_A0], rbx; Size
0x18000a796  mov     rdx, rbx
0x18000a799  mov     rcx, rdi; Src
0x18000a79c  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV23@QEBD_K@Z@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@D@01@AEAAAEAV01@QEBD0@Z@PEBD_K@Z; std::string::_Reallocate_grow_by<`std::string::_Append<char>(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *,unsigned __int64>(unsigned __int64,`std::string::_Append<char>(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *,unsigned __int64)
0x18000a7a1  cmp     [rbp+57h+var_58], 0
0x18000a7a6  jz      loc_18000A85B
0x18000a7ac  mov     rcx, [rdi+10h]
0x18000a7b0  mov     rax, [rdi+18h]
0x18000a7b4  sub     rax, rcx
0x18000a7b7  mov     edx, 4
0x18000a7bc  cmp     rax, rdx
0x18000a7bf  jb      short loc_18000A7E6
0x18000a7c1  lea     rax, [rcx+4]
0x18000a7c5  mov     [rdi+10h], rax
0x18000a7c9  cmp     qword ptr [rdi+18h], 0Fh
0x18000a7ce  jbe     short loc_18000A7D5
0x18000a7d0  mov     rax, [rdi]
0x18000a7d3  jmp     short loc_18000A7D8
0x18000a7d5  mov     rax, rdi
0x18000a7d8  mov     dword ptr [rax+rcx], 22202C22h
0x18000a7df  mov     byte ptr [rax+rcx+4], 0
0x18000a7e4  jmp     short loc_18000A7FA
0x18000a7e6  mov     [rsp+0C0h+var_A0], rdx; Size
0x18000a7eb  lea     r9, asc_18001087C; "\", \""
0x18000a7f2  mov     rcx, rdi; Src
0x18000a7f5  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV23@QEBD_K@Z@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@D@01@AEAAAEAV01@QEBD0@Z@PEBD_K@Z; std::string::_Reallocate_grow_by<`std::string::_Append<char>(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *,unsigned __int64>(unsigned __int64,`std::string::_Append<char>(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *,unsigned __int64)
0x18000a7fa  mov     rsi, [rbp+57h+var_58]
0x18000a7fe  lea     r9, [rbp+57h+var_68]
0x18000a802  cmp     [rbp+57h+var_50], 0Fh
0x18000a807  cmova   r9, [rbp+57h+var_68]
0x18000a80c  mov     rcx, [rdi+10h]
0x18000a810  mov     rax, [rdi+18h]
0x18000a814  sub     rax, rcx
0x18000a817  cmp     rsi, rax
0x18000a81a  ja      short loc_18000A84B
0x18000a81c  lea     rax, [rsi+rcx]
0x18000a820  mov     [rdi+10h], rax
0x18000a824  cmp     qword ptr [rdi+18h], 0Fh
0x18000a829  jbe     short loc_18000A830
0x18000a82b  mov     rax, [rdi]
0x18000a82e  jmp     short loc_18000A833
0x18000a830  mov     rax, rdi
0x18000a833  lea     rbx, [rax+rcx]
0x18000a837  mov     r8, rsi; Size
0x18000a83a  mov     rdx, r9; Src
0x18000a83d  mov     rcx, rbx; void *
0x18000a840  call    memmove_0
0x18000a845  mov     byte ptr [rsi+rbx], 0
0x18000a849  jmp     short loc_18000A85B
0x18000a84b  mov     [rsp+0C0h+var_A0], rsi; Size
0x18000a850  mov     rdx, rsi
0x18000a853  mov     rcx, rdi; Src
0x18000a856  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV23@QEBD_K@Z@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@D@01@AEAAAEAV01@QEBD0@Z@PEBD_K@Z; std::string::_Reallocate_grow_by<`std::string::_Append<char>(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *,unsigned __int64>(unsigned __int64,`std::string::_Append<char>(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *,unsigned __int64)
0x18000a85b  mov     rcx, [rdi+10h]
0x18000a85f  cmp     rcx, [rdi+18h]
0x18000a863  jnb     short loc_18000A884
0x18000a865  lea     rax, [rcx+1]
0x18000a869  mov     [rdi+10h], rax
0x18000a86d  cmp     qword ptr [rdi+18h], 0Fh
0x18000a872  jbe     short loc_18000A879
0x18000a874  mov     rax, [rdi]
0x18000a877  jmp     short loc_18000A87C
0x18000a879  mov     rax, rdi
0x18000a87c  mov     word ptr [rax+rcx], 22h ; '"'
0x18000a882  jmp     short loc_18000A890
0x18000a884  mov     r9b, 22h ; '"'
0x18000a887  mov     rcx, rdi; Src
0x18000a88a  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x18000a88f  nop
0x18000a890  lea     rcx, [rbp+57h+var_68]
0x18000a894  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000a899  nop
0x18000a89a  lea     rcx, [rbp+57h+Src]
0x18000a89e  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000a8a3  mov     rax, rdi
0x18000a8a6  mov     rcx, [rbp+57h+var_28]
0x18000a8aa  xor     rcx, rsp; StackCookie
0x18000a8ad  call    __security_check_cookie
0x18000a8b2  mov     rbx, [rsp+0C0h+arg_10]
0x18000a8ba  add     rsp, 0A0h
0x18000a8c1  pop     r15
0x18000a8c3  pop     r14
0x18000a8c5  pop     rdi
0x18000a8c6  pop     rsi
0x18000a8c7  pop     rbp
0x18000a8c8  retn
```
