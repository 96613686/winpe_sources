# Container::Manager::Image::_anonymous_namespace_::ProcessRegistryAdjustment

- ea: `0x14001bb2c`
- end: `0x14001bf56`
- name: `Container::Manager::Image::_anonymous_namespace_::ProcessRegistryAdjustment`
- size: `1066`
- prototype: `__int64 __fastcall(Csl::OfflineHive *this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x14001b938`

## callees

- `0x140002344`
- `0x140006fe4`
- `0x140008f90`
- `0x14000a7a4`
- `0x14000aa58`
- `0x14000d7bc`
- `0x14000d7e4`
- `0x14000d81c`
- `0x140014f44`
- `0x140018320`
- `0x14001bb2c`
- `0x14001dd28`
- `0x140021b64`
- `0x140021c34`
- `0x1400223dc`
- `0x140022aa8`

## pseudocode

```c
__int64 __fastcall Container::Manager::Image::_anonymous_namespace_::ProcessRegistryAdjustment(
        Csl::OfflineHive *this,
        __int64 a2)
{
  Csl::OfflineHive *v3; // r13
  int v4; // edx
  int v5; // edx
  __int64 v6; // rdx
  __m128i si128; // xmm6
  __int64 v9; // r8
  __int64 v10; // rdx
  int MultiStringValue; // eax
  unsigned int KeyRecursive; // ebx
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  char v17; // r12
  char *i; // rbx
  void **v19; // rdi
  __int64 *j; // rsi
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // r13
  __int64 v25; // r12
  __int64 *v26; // rbx
  __int64 *k; // rdi
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rcx
  int v31; // eax
  const unsigned __int16 *v32; // r8
  const unsigned __int16 *v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // [rsp+38h] [rbp-69h] BYREF
  __int64 v39; // [rsp+40h] [rbp-61h]
  __int64 v40; // [rsp+48h] [rbp-59h] BYREF
  __int64 v41; // [rsp+50h] [rbp-51h]
  __m128i v42; // [rsp+58h] [rbp-49h] BYREF
  __int64 v43; // [rsp+68h] [rbp-39h]
  __m128i v44; // [rsp+70h] [rbp-31h] BYREF
  __int64 v45; // [rsp+80h] [rbp-21h]
  void *v46[2]; // [rsp+88h] [rbp-19h] BYREF
  __int16 v47; // [rsp+98h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+5Fh]

  v3 = this;
  v4 = *(_DWORD *)(a2 + 4) - 1;
  if ( !v4 )
  {
    v35 = *(_QWORD *)(a2 + 16);
    v46[0] = &v47;
    v46[1] = &v47;
    v36 = *(_QWORD *)(a2 + 8);
    v47 = 0;
    v41 = (v35 - v36) >> 1;
    v40 = v36;
    if ( Csl::Path::Assign((Csl::Path *)v46, (__int64)&v40) )
    {
      KeyRecursive = Container::Manager::Image::_anonymous_namespace_::CreateKeyRecursive(v3);
      if ( (KeyRecursive & 0x80000000) == 0 )
      {
        KeyRecursive = Container::Manager::Image::_anonymous_namespace_::SetKeyValueInOfflineHive(
                         v3,
                         *(_DWORD *)(a2 + 104));
        if ( (KeyRecursive & 0x80000000) == 0 )
        {
          if ( v46[0] != &v47 )
            operator delete(v46[0], (const struct std::nothrow_t *)&std::nothrow);
          return 0;
        }
        v37 = 373;
      }
      else
      {
        v37 = 366;
      }
    }
    else
    {
      KeyRecursive = -2147024882;
      v37 = 363;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v37,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)KeyRecursive);
    if ( v46[0] != &v47 )
      operator delete(v46[0], (const struct std::nothrow_t *)&std::nothrow);
    return KeyRecursive;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v32 = *(const unsigned __int16 **)(a2 + 40);
    v33 = *(const unsigned __int16 **)(a2 + 8);
    if ( v32 == *(const unsigned __int16 **)(a2 + 48) )
    {
      KeyRecursive = Csl::OfflineHive::DeleteKeyRecursive(this, v33);
      if ( (int)(KeyRecursive + 0x80000000) < 0 || KeyRecursive == -2147024894 )
        return 0;
      v34 = 391;
    }
    else
    {
      KeyRecursive = Csl::OfflineHive::DeleteValue(this, v33, v32);
      if ( (int)(KeyRecursive + 0x80000000) < 0 || KeyRecursive == -2147024894 )
        return 0;
      v34 = 402;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v34,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)KeyRecursive);
    return KeyRecursive;
  }
  if ( v5 != 1 )
  {
    v6 = 494;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v6,
             (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
             (const char *)0x32);
  }
  if ( (unsigned int)(*(_DWORD *)(a2 + 112) - 1) > 1 )
  {
    v6 = 484;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v6,
             (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
             (const char *)0x32);
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v9 = *(_QWORD *)(a2 + 40);
  v10 = *(_QWORD *)(a2 + 8);
  v42 = si128;
  v43 = -1;
  MultiStringValue = Csl::OfflineHive::GetMultiStringValue((int)this, v10, v9, (__int64)&v42);
  KeyRecursive = MultiStringValue;
  if ( MultiStringValue < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A7,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)MultiStringValue);
LABEL_39:
    utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&v42);
    return KeyRecursive;
  }
  v13 = *(_QWORD *)(a2 + 72);
  v14 = *(_QWORD *)(a2 + 80) - v13;
  v45 = -1;
  v39 = v14 >> 1;
  v44 = si128;
  v38 = v13;
  if ( !(unsigned __int8)Csl::StringSplit(&v38, 44, &v44) )
  {
    KeyRecursive = -2147024882;
    v15 = 426;
    v16 = 2147942414LL;
LABEL_38:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)v16);
    utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&v44);
    goto LABEL_39;
  }
  v17 = 0;
  if ( *(_DWORD *)(a2 + 112) == 1 )
  {
    v19 = (void **)v42.m128i_i64[1];
    for ( i = (char *)v42.m128i_i64[0]; i != (char *)v19; i += 32 )
    {
      for ( j = (__int64 *)v44.m128i_i64[0]; j != (__int64 *)v44.m128i_i64[1]; j += 4 )
      {
        v21 = j[1] - *j;
        v38 = *j;
        v22 = *(_QWORD *)i;
        v39 = v21 >> 1;
        v23 = *((_QWORD *)i + 1) - v22;
        v40 = v22;
        v41 = v23 >> 1;
        if ( Csl::StringEqualIgnoreCase((__int64)&v40, (__int64)&v38) )
        {
          v24 = 0;
          v25 = ((char *)v19 - i - 32) >> 5;
          if ( v25 )
          {
            do
            {
              utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
                (__int64)&i[32 * v24],
                (__int64)&i[32 * v24 + 32]);
              ++v24;
            }
            while ( v24 != v25 );
          }
          v19 -= 4;
          if ( *v19 != v19 + 2 )
            operator delete(*v19, (const struct std::nothrow_t *)&std::nothrow);
          v17 = 1;
        }
      }
      v3 = this;
      v42.m128i_i64[1] = (__int64)v19;
    }
  }
  else
  {
    v26 = (__int64 *)v44.m128i_i64[0];
    while ( 2 )
    {
      if ( v26 != (__int64 *)v44.m128i_i64[1] )
      {
        for ( k = (__int64 *)v42.m128i_i64[0]; k != (__int64 *)v42.m128i_i64[1]; k += 4 )
        {
          v28 = v26[1] - *v26;
          v40 = *v26;
          v29 = *k;
          v41 = v28 >> 1;
          v30 = k[1] - v29;
          v38 = v29;
          v39 = v30 >> 1;
          if ( Csl::StringEqualIgnoreCase((__int64)&v38, (__int64)&v40) )
            goto LABEL_33;
        }
        if ( (unsigned __int8)utl::vector<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::emplace_back<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const &,0>(
                                &v42,
                                v26) )
        {
          v17 = 1;
LABEL_33:
          v26 += 4;
          continue;
        }
        KeyRecursive = -2147024882;
        v15 = 464;
        v16 = 2147942414LL;
        goto LABEL_38;
      }
      break;
    }
  }
  if ( v17 )
  {
    v31 = Csl::OfflineHive::SetMultiStringValue(
            v3,
            *(const unsigned __int16 **)(a2 + 8),
            *(const unsigned __int16 **)(a2 + 40),
            &v42);
    KeyRecursive = v31;
    if ( v31 < 0 )
    {
      v16 = (unsigned int)v31;
      v15 = 478;
      goto LABEL_38;
    }
  }
  utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&v44);
  utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&v42);
  return 0;
}

```

## disassembly

```asm
0x14001bb2c  mov     rax, rsp
0x14001bb2f  mov     [rax+8], rcx
0x14001bb33  push    rbp
0x14001bb34  push    rbx
0x14001bb35  push    rsi
0x14001bb36  push    rdi
0x14001bb37  push    r12
0x14001bb39  push    r13
0x14001bb3b  push    r14
0x14001bb3d  push    r15
0x14001bb3f  lea     rbp, [rax-5Fh]
0x14001bb43  sub     rsp, 0B8h
0x14001bb4a  mov     r14, rdx
0x14001bb4d  movaps  xmmword ptr [rax-58h], xmm6
0x14001bb51  mov     edx, [rdx+4]
0x14001bb54  mov     r13, rcx
0x14001bb57  sub     edx, 1
0x14001bb5a  jz      loc_14001BE63
0x14001bb60  sub     edx, 1
0x14001bb63  jz      loc_14001BDEB
0x14001bb69  cmp     edx, 1
0x14001bb6c  jz      short loc_14001BB75
0x14001bb6e  mov     edx, 1EEh
0x14001bb73  jmp     short loc_14001BB85
0x14001bb75  mov     eax, [r14+70h]
0x14001bb79  dec     eax
0x14001bb7b  cmp     eax, 1
0x14001bb7e  jbe     short loc_14001BBA0
0x14001bb80  mov     edx, 1E4h; void *
0x14001bb85  mov     rcx, [rbp+5Fh]; this
0x14001bb89  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001bb90  mov     r9d, 32h ; '2'; char *
0x14001bb96  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14001bb9b  jmp     loc_14001BF39
0x14001bba0  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14001bba8  lea     r9, [rbp+57h+var_A0]
0x14001bbac  mov     r8, [r14+28h]
0x14001bbb0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14001bbb4  mov     rdx, [r14+8]
0x14001bbb8  movdqu  [rbp+57h+var_A0], xmm6
0x14001bbbd  mov     [rbp+57h+var_90], rdi
0x14001bbc1  call    ?GetMultiStringValue@OfflineHive@Csl@@QEBAJPEBG0AEAV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z; Csl::OfflineHive::GetMultiStringValue(ushort const *,ushort const *,utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)
0x14001bbc6  xor     r15d, r15d
0x14001bbc9  mov     ebx, eax
0x14001bbcb  test    eax, eax
0x14001bbcd  jns     short loc_14001BBEC
0x14001bbcf  mov     rcx, [rbp+5Fh]; this
0x14001bbd3  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001bbda  mov     r9d, eax; char *
0x14001bbdd  mov     edx, 1A7h; void *
0x14001bbe2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001bbe7  jmp     loc_14001BDC6
0x14001bbec  mov     rax, [r14+48h]
0x14001bbf0  lea     r8, [rbp+57h+var_88]
0x14001bbf4  mov     rcx, [r14+50h]
0x14001bbf8  mov     edx, 2Ch ; ','
0x14001bbfd  sub     rcx, rax
0x14001bc00  mov     [rbp+57h+var_78], rdi
0x14001bc04  sar     rcx, 1
0x14001bc07  mov     [rbp+57h+var_B8], rcx
0x14001bc0b  lea     rcx, [rbp+57h+var_C0]
0x14001bc0f  movdqu  [rbp+57h+var_88], xmm6
0x14001bc14  mov     [rbp+57h+var_C0], rax
0x14001bc18  call    ?StringSplit@Csl@@YA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@GAEAV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@3@@Z; Csl::StringSplit(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &,ushort,utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)
0x14001bc1d  test    al, al
0x14001bc1f  jnz     short loc_14001BC33
0x14001bc21  mov     ebx, 8007000Eh
0x14001bc26  mov     edx, 1AAh
0x14001bc2b  mov     r9d, ebx
0x14001bc2e  jmp     loc_14001BDAD
0x14001bc33  cmp     dword ptr [r14+70h], 1
0x14001bc38  mov     r12b, r15b
0x14001bc3b  jnz     loc_14001BD09
0x14001bc41  mov     rbx, qword ptr [rbp+57h+var_A0]
0x14001bc45  mov     rdi, qword ptr [rbp+57h+var_A0+8]
0x14001bc49  cmp     rbx, rdi
0x14001bc4c  jz      loc_14001BD86
0x14001bc52  mov     rsi, qword ptr [rbp+57h+var_88]
0x14001bc56  cmp     rsi, qword ptr [rbp+57h+var_88+8]
0x14001bc5a  jz      loc_14001BCF8
0x14001bc60  mov     rax, [rsi]
0x14001bc63  lea     rdx, [rbp+57h+var_C0]
0x14001bc67  mov     rcx, [rsi+8]
0x14001bc6b  sub     rcx, rax
0x14001bc6e  mov     [rbp+57h+var_C0], rax
0x14001bc72  mov     rax, [rbx]
0x14001bc75  sar     rcx, 1
0x14001bc78  mov     [rbp+57h+var_B8], rcx
0x14001bc7c  mov     rcx, [rbx+8]
0x14001bc80  sub     rcx, rax
0x14001bc83  mov     [rbp+57h+var_B0], rax
0x14001bc87  sar     rcx, 1
0x14001bc8a  mov     [rbp+57h+var_A8], rcx
0x14001bc8e  lea     rcx, [rbp+57h+var_B0]
0x14001bc92  call    ?StringEqualIgnoreCase@Csl@@YA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@0@Z; Csl::StringEqualIgnoreCase(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &,utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x14001bc97  test    al, al
0x14001bc99  jz      short loc_14001BCEF
0x14001bc9b  mov     r12, rdi
0x14001bc9e  mov     r13, r15
0x14001bca1  sub     r12, rbx
0x14001bca4  sub     r12, 20h ; ' '
0x14001bca8  sar     r12, 5
0x14001bcac  test    r12, r12
0x14001bcaf  jz      short loc_14001BCD0
0x14001bcb1  mov     rax, r13
0x14001bcb4  shl     rax, 5
0x14001bcb8  lea     rdx, [rax+20h]
0x14001bcbc  add     rdx, rbx
0x14001bcbf  lea     rcx, [rax+rbx]
0x14001bcc3  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x14001bcc8  inc     r13
0x14001bccb  cmp     r13, r12
0x14001bcce  jnz     short loc_14001BCB1
0x14001bcd0  sub     rdi, 20h ; ' '
0x14001bcd4  lea     rax, [rdi+10h]
0x14001bcd8  cmp     [rdi], rax
0x14001bcdb  jz      short loc_14001BCEC
0x14001bcdd  mov     rcx, [rdi]; void *
0x14001bce0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001bce7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001bcec  mov     r12b, 1
0x14001bcef  add     rsi, 20h ; ' '
0x14001bcf3  jmp     loc_14001BC56
0x14001bcf8  mov     r13, [rbp+57h+arg_0]
0x14001bcfc  add     rbx, 20h ; ' '
0x14001bd00  mov     qword ptr [rbp+57h+var_A0+8], rdi
0x14001bd04  jmp     loc_14001BC49
0x14001bd09  mov     rbx, qword ptr [rbp+57h+var_88]
0x14001bd0d  cmp     rbx, qword ptr [rbp+57h+var_88+8]
0x14001bd11  jz      short loc_14001BD86
0x14001bd13  mov     rdi, qword ptr [rbp+57h+var_A0]
0x14001bd17  cmp     rdi, qword ptr [rbp+57h+var_A0+8]
0x14001bd1b  jz      short loc_14001BD5E
0x14001bd1d  mov     rax, [rbx]
0x14001bd20  lea     rdx, [rbp+57h+var_B0]
0x14001bd24  mov     rcx, [rbx+8]
0x14001bd28  sub     rcx, rax
0x14001bd2b  mov     [rbp+57h+var_B0], rax
0x14001bd2f  mov     rax, [rdi]
0x14001bd32  sar     rcx, 1
0x14001bd35  mov     [rbp+57h+var_A8], rcx
0x14001bd39  mov     rcx, [rdi+8]
0x14001bd3d  sub     rcx, rax
0x14001bd40  mov     [rbp+57h+var_C0], rax
0x14001bd44  sar     rcx, 1
0x14001bd47  mov     [rbp+57h+var_B8], rcx
0x14001bd4b  lea     rcx, [rbp+57h+var_C0]
0x14001bd4f  call    ?StringEqualIgnoreCase@Csl@@YA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@0@Z; Csl::StringEqualIgnoreCase(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &,utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x14001bd54  test    al, al
0x14001bd56  jnz     short loc_14001BD71
0x14001bd58  add     rdi, 20h ; ' '
0x14001bd5c  jmp     short loc_14001BD17
0x14001bd5e  mov     rdx, rbx
0x14001bd61  lea     rcx, [rbp+57h+var_A0]
0x14001bd65  call    ??$emplace_back@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@$0A@@?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@@Z; utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::emplace_back<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &,0>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x14001bd6a  test    al, al
0x14001bd6c  jz      short loc_14001BD77
0x14001bd6e  mov     r12b, 1
0x14001bd71  add     rbx, 20h ; ' '
0x14001bd75  jmp     short loc_14001BD0D
0x14001bd77  mov     ebx, 8007000Eh
0x14001bd7c  mov     edx, 1D0h
0x14001bd81  mov     r9d, ebx
0x14001bd84  jmp     short loc_14001BDAD
0x14001bd86  test    r12b, r12b
0x14001bd89  jz      short loc_14001BDD4
0x14001bd8b  mov     r8, [r14+28h]
0x14001bd8f  lea     r9, [rbp+57h+var_A0]
0x14001bd93  mov     rdx, [r14+8]
0x14001bd97  mov     rcx, r13
0x14001bd9a  call    ?SetMultiStringValue@OfflineHive@Csl@@QEAAJPEBG0AEBV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z; Csl::OfflineHive::SetMultiStringValue(ushort const *,ushort const *,utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> const &)
0x14001bd9f  mov     ebx, eax
0x14001bda1  test    eax, eax
0x14001bda3  jns     short loc_14001BDD4
0x14001bda5  mov     r9d, eax; char *
0x14001bda8  mov     edx, 1DEh; void *
0x14001bdad  mov     rcx, [rbp+5Fh]; this
0x14001bdb1  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001bdb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001bdbd  lea     rcx, [rbp+57h+var_88]
0x14001bdc1  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x14001bdc6  lea     rcx, [rbp+57h+var_A0]
0x14001bdca  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x14001bdcf  jmp     loc_14001BED8
0x14001bdd4  lea     rcx, [rbp+57h+var_88]
0x14001bdd8  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x14001bddd  lea     rcx, [rbp+57h+var_A0]
0x14001bde1  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x14001bde6  jmp     loc_14001BF37
0x14001bdeb  mov     r8, [r14+28h]; unsigned __int16 *
0x14001bdef  mov     rdx, [r14+8]; unsigned __int16 *
0x14001bdf3  cmp     r8, [r14+30h]
0x14001bdf7  jnz     short loc_14001BE39
0x14001bdf9  call    ?DeleteKeyRecursive@OfflineHive@Csl@@QEAAJPEBG@Z; Csl::OfflineHive::DeleteKeyRecursive(ushort const *)
0x14001bdfe  mov     ebx, eax
0x14001be00  mov     eax, 80000000h
0x14001be05  lea     ecx, [rbx+rax]
0x14001be08  test    eax, ecx
0x14001be0a  jnz     loc_14001BF37
0x14001be10  cmp     ebx, 80070002h
0x14001be16  jz      loc_14001BF37
0x14001be1c  mov     edx, 187h; void *
0x14001be21  mov     rcx, [rbp+5Fh]; this
0x14001be25  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001be2c  mov     r9d, ebx; char *
0x14001be2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001be34  jmp     loc_14001BED8
0x14001be39  call    ?DeleteValue@OfflineHive@Csl@@QEAAJQEBG0@Z; Csl::OfflineHive::DeleteValue(ushort const * const,ushort const * const)
0x14001be3e  mov     ebx, eax
0x14001be40  mov     eax, 80000000h
0x14001be45  lea     ecx, [rbx+rax]
0x14001be48  test    eax, ecx
0x14001be4a  jnz     loc_14001BF37
0x14001be50  cmp     ebx, 80070002h
0x14001be56  jz      loc_14001BF37
0x14001be5c  mov     edx, 192h
0x14001be61  jmp     short loc_14001BE21
0x14001be63  mov     rcx, [r14+10h]
0x14001be67  lea     rax, [rbp+57h+var_60]
0x14001be6b  mov     [rbp+57h+var_70], rax
0x14001be6f  lea     rdx, [rbp+57h+var_B0]
0x14001be73  lea     rax, [rbp+57h+var_60]
0x14001be77  xor     r15d, r15d
0x14001be7a  mov     [rbp+57h+var_68], rax
0x14001be7e  mov     rax, [r14+8]
0x14001be82  sub     rcx, rax
0x14001be85  mov     [rbp+57h+var_60], r15w
0x14001be8a  sar     rcx, 1
0x14001be8d  mov     [rbp+57h+var_A8], rcx
0x14001be91  lea     rcx, [rbp+57h+var_70]; this
0x14001be95  mov     [rbp+57h+var_B0], rax
0x14001be99  call    ?Assign@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Assign(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x14001be9e  test    al, al
0x14001bea0  jnz     short loc_14001BEDC
0x14001bea2  mov     ebx, 8007000Eh
0x14001bea7  mov     edx, 16Bh; void *
0x14001beac  mov     rcx, [rbp+5Fh]; this
0x14001beb0  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001beb7  mov     r9d, ebx; char *
0x14001beba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001bebf  mov     rcx, [rbp+57h+var_70]; void *
0x14001bec3  lea     rax, [rbp+57h+var_60]
0x14001bec7  cmp     rcx, rax
0x14001beca  jz      short loc_14001BED8
0x14001becc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001bed3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001bed8  mov     eax, ebx
0x14001beda  jmp     short loc_14001BF39
0x14001bedc  lea     rdx, [rbp+57h+var_70]
0x14001bee0  mov     rcx, r13; this
0x14001bee3  call    Container__Manager__Image___anonymous_namespace___CreateKeyRecursive
0x14001bee8  mov     ebx, eax
0x14001beea  test    eax, eax
0x14001beec  jns     short loc_14001BEF5
0x14001beee  mov     edx, 16Eh
0x14001bef3  jmp     short loc_14001BEAC
0x14001bef5  mov     eax, [r14+68h]
0x14001bef9  lea     r9, [r14+48h]
0x14001befd  lea     r8, [r14+28h]
0x14001bf01  mov     [rsp+20h], eax; unsigned __int8
0x14001bf05  lea     rdx, [r14+8]
0x14001bf09  mov     rcx, r13; this
0x14001bf0c  call    Container__Manager__Image___anonymous_namespace___SetKeyValueInOfflineHive
0x14001bf11  mov     ebx, eax
0x14001bf13  test    eax, eax
0x14001bf15  jns     short loc_14001BF1E
0x14001bf17  mov     edx, 175h
0x14001bf1c  jmp     short loc_14001BEAC
0x14001bf1e  mov     rcx, [rbp+57h+var_70]; void *
0x14001bf22  lea     rax, [rbp+57h+var_60]
0x14001bf26  cmp     rcx, rax
0x14001bf29  jz      short loc_14001BF37
0x14001bf2b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001bf32  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001bf37  xor     eax, eax
0x14001bf39  movaps  xmm6, [rsp+0F0h+var_58+8]
0x14001bf41  add     rsp, 0B8h
0x14001bf48  pop     r15
0x14001bf4a  pop     r14
0x14001bf4c  pop     r13
0x14001bf4e  pop     r12
0x14001bf50  pop     rdi
0x14001bf51  pop     rsi
0x14001bf52  pop     rbx
0x14001bf53  pop     rbp
0x14001bf54  retn
```
