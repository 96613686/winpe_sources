# std::filesystem::filesystem_error::_Pretty_message(std::basic_string_view<char,std::char_traits<char>>,std::filesystem::path const &,std::filesystem::path const &)

- ea: `0x1800042a4`
- end: `0x180004480`
- name: `?_Pretty_message@filesystem_error@filesystem@std@@CA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@V?$basic_string_view@DU?$char_traits@D@std@@@3@AEBVpath@23@1@Z`
- size: `476`
- prototype: `_QWORD *__fastcall(_QWORD *Src, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180009824`

## callees

- `0x1800042a4`
- `0x180004488`
- `0x180004670`
- `0x180005020`
- `0x180008c68`
- `0x1800091a0`
- `0x180009340`
- `0x180009a30`

## pseudocode

```c
_QWORD *__fastcall std::filesystem::filesystem_error::_Pretty_message(_QWORD *Src, __int64 a2, _QWORD *a3, _QWORD *a4)
{
  UINT v8; // r14d
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  __int64 v11; // rbx
  unsigned __int64 v12; // rcx
  _QWORD *v13; // rax
  _QWORD *v15; // [rsp+30h] [rbp-29h] BYREF
  __int64 v16; // [rsp+38h] [rbp-21h]
  _QWORD *v17; // [rsp+40h] [rbp-19h]
  _QWORD v18[2]; // [rsp+48h] [rbp-11h] BYREF
  __int64 v19; // [rsp+58h] [rbp-1h]
  _QWORD Srca[3]; // [rsp+68h] [rbp+Fh] BYREF

  v17 = Src;
  *(_OWORD *)Src = 0;
  Src[2] = 0;
  Src[3] = 15;
  *(_BYTE *)Src = 0;
  v8 = _std_fs_code_page(Src);
  if ( a3[3] <= 7u )
    v9 = a3;
  else
    v9 = (_QWORD *)*a3;
  v15 = v9;
  v16 = a3[2];
  std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(
    Srca,
    v8,
    (__int64)&v15);
  if ( a4[3] <= 7u )
    v10 = a4;
  else
    v10 = (_QWORD *)*a4;
  v15 = v10;
  v16 = a4[2];
  std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(
    v18,
    v8,
    (__int64)&v15);
  if ( Src[3] < (unsigned __int64)(v19 != 0 ? 4 : 0) + 4 + v19 + *(_QWORD *)(a2 + 8) + Srca[2] )
  {
    v11 = Src[2];
    ____Reallocate_grow_by_V_lambda_1___1__reserve___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAX_K_Z___V___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__reserve_01_QEAAX0_Z__Z(Src);
    Src[2] = v11;
  }
  std::string::_Append<char>(Src);
  std::string::_Append<char>(Src);
  std::string::_Append<char>(Src);
  if ( v19 )
  {
    std::string::_Append<char>(Src);
    std::string::_Append<char>(Src);
  }
  v12 = Src[2];
  if ( v12 >= Src[3] )
  {
    ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
  }
  else
  {
    Src[2] = v12 + 1;
    if ( Src[3] <= 0xFu )
      v13 = Src;
    else
      v13 = (_QWORD *)*Src;
    *(_WORD *)((char *)v13 + v12) = 34;
  }
  std::string::~string((__int64)v18);
  std::string::~string((__int64)Srca);
  return Src;
}

```

## disassembly

```asm
0x1800042a4  mov     [rsp-8+arg_10], rbx
0x1800042a9  push    rbp
0x1800042aa  push    rsi
0x1800042ab  push    rdi
0x1800042ac  push    r14
0x1800042ae  push    r15
0x1800042b0  lea     rbp, [rsp-37h]
0x1800042b5  sub     rsp, 90h
0x1800042bc  mov     rax, cs:__security_cookie
0x1800042c3  xor     rax, rsp
0x1800042c6  mov     [rbp+57h+var_28], rax
0x1800042ca  mov     rsi, r9
0x1800042cd  mov     rbx, r8
0x1800042d0  mov     r15, rdx
0x1800042d3  mov     rdi, rcx
0x1800042d6  mov     [rbp+57h+var_70], rcx
0x1800042da  mov     [rbp+57h+var_90], 0
0x1800042e1  xorps   xmm0, xmm0
0x1800042e4  movups  xmmword ptr [rcx], xmm0
0x1800042e7  mov     qword ptr [rcx+10h], 0
0x1800042ef  mov     qword ptr [rcx+18h], 0Fh
0x1800042f7  mov     byte ptr [rcx], 0
0x1800042fa  mov     [rbp+57h+var_90], 1
0x180004301  call    __std_fs_code_page
0x180004306  mov     r14d, eax
0x180004309  cmp     qword ptr [rbx+18h], 7
0x18000430e  jbe     short loc_180004315
0x180004310  mov     rax, [rbx]
0x180004313  jmp     short loc_180004318
0x180004315  mov     rax, rbx
0x180004318  mov     [rbp+57h+var_80], rax
0x18000431c  mov     rax, [rbx+10h]
0x180004320  mov     [rbp+57h+var_78], rax
0x180004324  lea     r8, [rbp+57h+var_80]
0x180004328  mov     edx, r14d; CodePage
0x18000432b  lea     rcx, [rbp+57h+Src]; Src
0x18000432f  call    ??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@D@1@@Z; std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::basic_string_view<ushort>,std::allocator<char> const &)
0x180004334  nop
0x180004335  cmp     qword ptr [rsi+18h], 7
0x18000433a  jbe     short loc_180004341
0x18000433c  mov     rax, [rsi]
0x18000433f  jmp     short loc_180004344
0x180004341  mov     rax, rsi
0x180004344  mov     [rbp+57h+var_80], rax
0x180004348  mov     rax, [rsi+10h]
0x18000434c  mov     [rbp+57h+var_78], rax
0x180004350  lea     r8, [rbp+57h+var_80]
0x180004354  mov     edx, r14d; CodePage
0x180004357  lea     rcx, [rbp+57h+var_68]; Src
0x18000435b  call    ??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@D@1@@Z; std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::basic_string_view<ushort>,std::allocator<char> const &)
0x180004360  nop
0x180004361  mov     rax, [rbp+57h+var_58]
0x180004365  neg     rax
0x180004368  sbb     r9, r9
0x18000436b  and     r9d, 4
0x18000436f  add     r9, 4
0x180004373  mov     rsi, [r15+8]
0x180004377  mov     rdx, [rbp+57h+var_38]
0x18000437b  add     rdx, rsi
0x18000437e  add     rdx, [rbp+57h+var_58]
0x180004382  add     rdx, r9
0x180004385  cmp     [rdi+18h], rdx
0x180004389  jnb     short loc_18000439E
0x18000438b  mov     rbx, [rdi+10h]
0x18000438f  sub     rdx, rbx
0x180004392  mov     rcx, rdi; Src
0x180004395  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??reserve@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K@Z@$$V@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??reserve@01@QEAAX0@Z@@Z; std::string::_Reallocate_grow_by<`std::string::reserve(unsigned __int64)'::`2'::_lambda_1_,>(unsigned __int64,`std::string::reserve(unsigned __int64)'::`2'::_lambda_1_)
0x18000439a  mov     [rdi+10h], rbx
0x18000439e  mov     r8, rsi
0x1800043a1  mov     rdx, [r15]
0x1800043a4  mov     rcx, rdi; Src
0x1800043a7  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x1800043ac  mov     r8d, 3
0x1800043b2  lea     rdx, asc_18000D4C0; ": \""
0x1800043b9  mov     rcx, rdi; Src
0x1800043bc  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x1800043c1  lea     rdx, [rbp+57h+Src]
0x1800043c5  cmp     [rbp+57h+var_30], 0Fh
0x1800043ca  cmova   rdx, [rbp+57h+Src]
0x1800043cf  mov     r8, [rbp+57h+var_38]
0x1800043d3  mov     rcx, rdi; Src
0x1800043d6  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x1800043db  cmp     [rbp+57h+var_58], 0
0x1800043e0  jz      short loc_180004411
0x1800043e2  mov     r8d, 4
0x1800043e8  lea     rdx, asc_18000D4C4; "\", \""
0x1800043ef  mov     rcx, rdi; Src
0x1800043f2  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x1800043f7  lea     rdx, [rbp+57h+var_68]
0x1800043fb  cmp     [rbp+57h+var_50], 0Fh
0x180004400  cmova   rdx, [rbp+57h+var_68]
0x180004405  mov     r8, [rbp+57h+var_58]
0x180004409  mov     rcx, rdi; Src
0x18000440c  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x180004411  mov     rcx, [rdi+10h]
0x180004415  cmp     rcx, [rdi+18h]
0x180004419  jnb     short loc_18000443A
0x18000441b  lea     rax, [rcx+1]
0x18000441f  mov     [rdi+10h], rax
0x180004423  cmp     qword ptr [rdi+18h], 0Fh
0x180004428  jbe     short loc_18000442F
0x18000442a  mov     rax, [rdi]
0x18000442d  jmp     short loc_180004432
0x18000442f  mov     rax, rdi
0x180004432  mov     word ptr [rcx+rax], 22h ; '"'
0x180004438  jmp     short loc_180004446
0x18000443a  mov     r9b, 22h ; '"'
0x18000443d  mov     rcx, rdi; Src
0x180004440  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x180004445  nop
0x180004446  lea     rcx, [rbp+57h+var_68]
0x18000444a  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000444f  nop
0x180004450  lea     rcx, [rbp+57h+Src]
0x180004454  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180004459  mov     rax, rdi
0x18000445c  mov     rcx, [rbp+57h+var_28]
0x180004460  xor     rcx, rsp; StackCookie
0x180004463  call    __security_check_cookie
0x180004468  mov     rbx, [rsp+0B0h+arg_10]
0x180004470  add     rsp, 90h
0x180004477  pop     r15
0x180004479  pop     r14
0x18000447b  pop     rdi
0x18000447c  pop     rsi
0x18000447d  pop     rbp
0x18000447e  retn
```
