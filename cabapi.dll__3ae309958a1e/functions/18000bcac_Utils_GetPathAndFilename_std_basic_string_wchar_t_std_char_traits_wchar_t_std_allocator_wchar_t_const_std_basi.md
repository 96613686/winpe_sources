# Utils::GetPathAndFilename(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *)

- ea: `0x18000bcac`
- end: `0x18000be4f`
- name: `?GetPathAndFilename@Utils@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAV23@1@Z`
- size: `419`
- prototype: `__int64 __fastcall(void **, void **, void **)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180008fd8`
- `0x18000be70`

## callees

- `0x180002e54`
- `0x180002f70`
- `0x180003648`
- `0x18000553c`
- `0x180008414`
- `0x18000a74c`
- `0x18000bcac`
- `0x18000ed80`

## pseudocode

```c
__int64 __fastcall Utils::GetPathAndFilename(void **a1, void **a2, void **a3)
{
  void **v5; // rdi
  __int64 v6; // rdx
  unsigned int v7; // ebx
  void *v9; // rax
  _QWORD *v10; // r14
  __int64 v11; // rax
  unsigned __int64 v12; // rsi
  char *v13; // rbx
  __int64 traits_2_0_unsigned_short; // rax
  __int64 v15; // rax
  unsigned __int64 v16; // r8
  unsigned __int64 v17; // rbx
  bool v18; // cc
  void **v19; // rdx
  void *v20; // rax
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // r8
  __int128 v23; // [rsp+20h] [rbp-58h] BYREF
  __int128 v24; // [rsp+30h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v5 = a1;
  if ( !a2 )
  {
    v6 = 216;
LABEL_3:
    v7 = -2147467261;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\utils.cpp",
      (const char *)v7,
      v23);
    return v7;
  }
  if ( !a3 )
  {
    v6 = 217;
    goto LABEL_3;
  }
  v9 = a1[2];
  if ( !v9 )
  {
    v7 = -2147024809;
    v6 = 218;
    goto LABEL_4;
  }
  if ( (unsigned __int64)a1[3] <= 7 )
    v10 = a1;
  else
    v10 = *a1;
  v11 = (__int64)v9 - 1;
  v12 = -1;
  if ( v11 == -1 )
    v11 = -1;
  v13 = (char *)v10 + 2 * v11 + 2;
  traits_2_0_unsigned_short = anonymous_namespace_::_Finding::_Find_last_impl__anonymous_namespace_::_Finding::_Find_traits_2_0_unsigned_short_(
                                v10,
                                v13);
  if ( (char *)traits_2_0_unsigned_short == v13 || (v15 = (traits_2_0_unsigned_short - (__int64)v10) >> 1, v15 == -1) )
  {
    if ( a3 != v5 )
    {
      v22 = (unsigned __int64)v5[2];
      if ( (unsigned __int64)v5[3] > 7 )
        v5 = (void **)*v5;
      std::wstring::_Assign<wchar_t>(a3, v5, v22);
    }
    std::wstring::_Assign<wchar_t>(a2, &dword_1800180D4, 0);
  }
  else
  {
    v16 = (unsigned __int64)v5[2];
    v17 = v15 + 1;
    if ( v16 >= v15 + 1 )
      v16 = v15 + 1;
    v18 = (unsigned __int64)v5[3] <= 7;
    v23 = 0;
    v24 = 0;
    if ( v18 )
      v19 = v5;
    else
      v19 = (void **)*v5;
    std::wstring::_Construct<1,wchar_t const *>((__int64)&v23, v19, v16);
    std::wstring::operator=((char **)a2, (__int64)&v23);
    std::wstring::~wstring((char **)&v23);
    v20 = v5[2];
    v23 = 0;
    v24 = 0;
    if ( (unsigned __int64)v20 < v17 )
      std::_String_val<std::_Simple_types<wchar_t>>::_Xran();
    v21 = (unsigned __int64)v20 - v17;
    if ( v21 != -1 )
      v12 = v21;
    if ( (unsigned __int64)v5[3] > 7 )
      v5 = (void **)*v5;
    std::wstring::_Construct<1,wchar_t const *>((__int64)&v23, (char *)v5 + 2 * v17, v12);
    std::wstring::operator=((char **)a3, (__int64)&v23);
    std::wstring::~wstring((char **)&v23);
  }
  return 0;
}

```

## disassembly

```asm
0x18000bcac  mov     [rsp+arg_18], rbx
0x18000bcb1  push    rbp
0x18000bcb2  push    rsi
0x18000bcb3  push    rdi
0x18000bcb4  push    r14
0x18000bcb6  push    r15
0x18000bcb8  sub     rsp, 50h
0x18000bcbc  mov     rbp, r8
0x18000bcbf  mov     r15, rdx
0x18000bcc2  mov     rdi, rcx
0x18000bcc5  test    rdx, rdx
0x18000bcc8  jnz     short loc_18000BCEF
0x18000bcca  mov     edx, 0D8h; void *
0x18000bccf  mov     ebx, 80004003h
0x18000bcd4  mov     rcx, [rsp+78h]; this
0x18000bcd9  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\mobile\\cabapi\\pri"...
0x18000bce0  mov     r9d, ebx; char *
0x18000bce3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bce8  mov     eax, ebx
0x18000bcea  jmp     loc_18000BE35
0x18000bcef  test    rbp, rbp
0x18000bcf2  jnz     short loc_18000BCFB
0x18000bcf4  mov     edx, 0D9h
0x18000bcf9  jmp     short loc_18000BCCF
0x18000bcfb  mov     rax, [rcx+10h]
0x18000bcff  test    rax, rax
0x18000bd02  jnz     short loc_18000BD10
0x18000bd04  mov     ebx, 80070057h
0x18000bd09  mov     edx, 0DAh
0x18000bd0e  jmp     short loc_18000BCD4
0x18000bd10  cmp     qword ptr [rcx+18h], 7
0x18000bd15  jbe     short loc_18000BD1C
0x18000bd17  mov     r14, [rcx]
0x18000bd1a  jmp     short loc_18000BD1F
0x18000bd1c  mov     r14, rdi
0x18000bd1f  dec     rax
0x18000bd22  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000bd26  cmp     rax, rsi
0x18000bd29  mov     rcx, r14
0x18000bd2c  cmovnb  rax, rsi
0x18000bd30  inc     rax
0x18000bd33  lea     rbx, [r14+rax*2]
0x18000bd37  mov     rdx, rbx
0x18000bd3a  call    _anonymous_namespace____Finding___Find_last_impl__anonymous_namespace____Finding___Find_traits_2_0_unsigned_short_
0x18000bd3f  cmp     rax, rbx
0x18000bd42  jz      loc_18000BE03
0x18000bd48  sub     rax, r14
0x18000bd4b  sar     rax, 1
0x18000bd4e  cmp     rax, rsi
0x18000bd51  jz      loc_18000BE03
0x18000bd57  mov     r8, [rdi+10h]
0x18000bd5b  lea     rbx, [rax+1]
0x18000bd5f  cmp     r8, rbx
0x18000bd62  xorps   xmm0, xmm0
0x18000bd65  xorps   xmm1, xmm1
0x18000bd68  cmovnb  r8, rbx
0x18000bd6c  cmp     qword ptr [rdi+18h], 7
0x18000bd71  movups  [rsp+78h+var_58], xmm0
0x18000bd76  movdqu  [rsp+78h+var_48], xmm1
0x18000bd7c  jbe     short loc_18000BD83
0x18000bd7e  mov     rdx, [rdi]
0x18000bd81  jmp     short loc_18000BD86
0x18000bd83  mov     rdx, rdi
0x18000bd86  lea     rcx, [rsp+78h+var_58]
0x18000bd8b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000bd90  lea     rdx, [rsp+78h+var_58]
0x18000bd95  mov     rcx, r15
0x18000bd98  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000bd9d  lea     rcx, [rsp+78h+var_58]
0x18000bda2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000bda7  mov     rax, [rdi+10h]
0x18000bdab  xorps   xmm0, xmm0
0x18000bdae  xorps   xmm1, xmm1
0x18000bdb1  movups  [rsp+78h+var_58], xmm0
0x18000bdb6  movdqu  [rsp+78h+var_48], xmm1
0x18000bdbc  cmp     rax, rbx
0x18000bdbf  jb      loc_18000BE49
0x18000bdc5  sub     rax, rbx
0x18000bdc8  cmp     rax, rsi
0x18000bdcb  cmovb   rsi, rax
0x18000bdcf  cmp     qword ptr [rdi+18h], 7
0x18000bdd4  jbe     short loc_18000BDD9
0x18000bdd6  mov     rdi, [rdi]
0x18000bdd9  lea     rdx, [rdi+rbx*2]
0x18000bddd  mov     r8, rsi
0x18000bde0  lea     rcx, [rsp+78h+var_58]
0x18000bde5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000bdea  lea     rdx, [rsp+78h+var_58]
0x18000bdef  mov     rcx, rbp
0x18000bdf2  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000bdf7  lea     rcx, [rsp+78h+var_58]
0x18000bdfc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000be01  jmp     short loc_18000BE33
0x18000be03  cmp     rbp, rdi
0x18000be06  jz      short loc_18000BE21
0x18000be08  cmp     qword ptr [rdi+18h], 7
0x18000be0d  mov     r8, [rdi+10h]
0x18000be11  jbe     short loc_18000BE16
0x18000be13  mov     rdi, [rdi]
0x18000be16  mov     rdx, rdi
0x18000be19  mov     rcx, rbp
0x18000be1c  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18000be21  xor     r8d, r8d
0x18000be24  lea     rdx, dword_1800180D4
0x18000be2b  mov     rcx, r15
0x18000be2e  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18000be33  xor     eax, eax
0x18000be35  mov     rbx, [rsp+78h+arg_18]
0x18000be3d  add     rsp, 50h
0x18000be41  pop     r15
0x18000be43  pop     r14
0x18000be45  pop     rdi
0x18000be46  pop     rsi
0x18000be47  pop     rbp
0x18000be48  retn
0x18000be49  call    ?_Xran@?$_String_val@U?$_Simple_types@_W@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Xran(void)
```
