# Container::Manager::Image::_anonymous_namespace_::CreateKeyRecursive

- ea: `0x140018320`
- end: `0x140018582`
- name: `Container::Manager::Image::_anonymous_namespace_::CreateKeyRecursive`
- size: `610`
- prototype: `__int64 __fastcall(Csl::OfflineHive *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x14001bb2c`

## callees

- `0x140002344`
- `0x140006fe4`
- `0x140008f90`
- `0x14000a9b8`
- `0x14000d81c`
- `0x140018320`
- `0x140021a0c`
- `0x1400227a4`

## pseudocode

```c
__int64 __fastcall Container::Manager::Image::_anonymous_namespace_::CreateKeyRecursive(
        Csl::OfflineHive *this,
        __int64 a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  const unsigned __int16 *v7; // rax
  __int64 v8; // r12
  unsigned int v9; // esi
  unsigned __int64 v10; // rdi
  unsigned int v11; // r14d
  __int64 v12; // rcx
  const unsigned __int16 *v13; // rax
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r9
  __int64 v18; // rcx
  const unsigned __int16 *v19; // rax
  __int64 v20; // rcx
  const unsigned __int16 *v21; // [rsp+20h] [rbp-50h] BYREF
  __int64 v22; // [rsp+28h] [rbp-48h]
  __m128i si128; // [rsp+30h] [rbp-40h] BYREF
  __int64 v24; // [rsp+40h] [rbp-30h]
  unsigned __int16 *v25[2]; // [rsp+48h] [rbp-28h] BYREF
  _WORD v26[12]; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  bool v28; // [rsp+A8h] [rbp+38h] BYREF

  v28 = 0;
  v4 = Csl::OfflineHive::KeyExists(this, *(const unsigned __int16 **)a2, &v28);
  v5 = v4;
  if ( v4 >= 0 )
  {
    if ( v28 )
      return 0;
    v7 = *(const unsigned __int16 **)a2;
    v22 = (__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 1;
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    v24 = -1;
    v21 = v7;
    if ( (unsigned __int8)Csl::StringSplit(&v21, 92, &si128) )
    {
      v8 = si128.m128i_i64[0];
      v9 = 0;
      v25[0] = v26;
      v10 = (si128.m128i_i64[1] - si128.m128i_i64[0]) >> 5;
      v25[1] = v26;
      v11 = 0;
      v26[0] = 0;
      if ( v10 )
      {
        while ( 1 )
        {
          v12 = 32LL * v11;
          v13 = *(const unsigned __int16 **)(v12 + v8);
          v14 = *(_QWORD *)(v12 + v8 + 8) - (_QWORD)v13;
          v21 = v13;
          v22 = v14 >> 1;
          if ( !Csl::Path::Append((Csl::Path *)v25, &v21) )
            break;
          v15 = Csl::OfflineHive::KeyExists(this, v25[0], &v28);
          v5 = v15;
          if ( v15 < 0 )
          {
            v16 = 295;
            goto LABEL_16;
          }
          ++v11;
          if ( !v28 )
          {
            v9 = v11;
            goto LABEL_12;
          }
          if ( v11 >= v10 )
            goto LABEL_12;
        }
        v16 = 293;
LABEL_31:
        v5 = -2147024882;
        v17 = 2147942414LL;
      }
      else
      {
LABEL_12:
        v28 = 0;
        v15 = Csl::OfflineHive::CreateKey(this, v25[0], &v28);
        v5 = v15;
        if ( v15 >= 0 )
        {
          while ( v9 < v10 )
          {
            v18 = 32LL * v9;
            v19 = *(const unsigned __int16 **)(v18 + v8);
            v20 = *(_QWORD *)(v18 + v8 + 8) - (_QWORD)v19;
            v21 = v19;
            v22 = v20 >> 1;
            if ( !Csl::Path::Append((Csl::Path *)v25, &v21) )
            {
              v16 = 319;
              goto LABEL_31;
            }
            v28 = 0;
            v15 = Csl::OfflineHive::CreateKey(this, v25[0], &v28);
            v5 = v15;
            if ( v15 < 0 )
            {
              v16 = 321;
              goto LABEL_16;
            }
            ++v9;
          }
          if ( v25[0] != v26 )
            operator delete(v25[0], (const struct std::nothrow_t *)&std::nothrow);
          v5 = 0;
          goto LABEL_27;
        }
        v16 = 314;
LABEL_16:
        v17 = (unsigned int)v15;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
        (const char *)v17);
      if ( v25[0] != v26 )
        operator delete(v25[0], (const struct std::nothrow_t *)&std::nothrow);
    }
    else
    {
      v5 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11E,
        (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
        (const char *)0x8007000ELL);
    }
LABEL_27:
    utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&si128);
    return v5;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x115,
    (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
    (const char *)(unsigned int)v4);
  return v5;
}

```

## disassembly

```asm
0x140018320  mov     [rsp-28h+arg_0], rbx
0x140018325  mov     [rsp-28h+arg_10], rsi
0x14001832a  push    rbp
0x14001832b  push    rdi
0x14001832c  push    r12
0x14001832e  push    r14
0x140018330  push    r15
0x140018332  mov     rbp, rsp
0x140018335  sub     rsp, 70h
0x140018339  mov     rdi, rdx
0x14001833c  mov     [rbp+arg_8], 0
0x140018340  mov     rdx, [rdx]; unsigned __int16 *
0x140018343  lea     r8, [rbp+arg_8]; bool *
0x140018347  mov     r15, rcx
0x14001834a  call    ?KeyExists@OfflineHive@Csl@@QEBAJPEBGAEA_N@Z; Csl::OfflineHive::KeyExists(ushort const *,bool &)
0x14001834f  mov     ebx, eax
0x140018351  test    eax, eax
0x140018353  jns     short loc_140018372
0x140018355  mov     rcx, [rbp+28h]; this
0x140018359  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140018360  mov     r9d, eax; char *
0x140018363  mov     edx, 115h; void *
0x140018368  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001836d  jmp     loc_14001854A
0x140018372  cmp     [rbp+arg_8], 0
0x140018376  jz      short loc_14001837F
0x140018378  xor     eax, eax
0x14001837a  jmp     loc_14001854C
0x14001837f  mov     rax, [rdi]
0x140018382  lea     r8, [rbp+var_40]
0x140018386  mov     rcx, [rdi+8]
0x14001838a  mov     edx, 5Ch ; '\'
0x14001838f  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140018397  sub     rcx, rax
0x14001839a  sar     rcx, 1
0x14001839d  mov     [rbp+var_48], rcx
0x1400183a1  lea     rcx, [rbp+var_50]
0x1400183a5  movdqu  [rbp+var_40], xmm0
0x1400183aa  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFFh
0x1400183b2  mov     [rbp+var_50], rax
0x1400183b6  call    ?StringSplit@Csl@@YA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@GAEAV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@3@@Z; Csl::StringSplit(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &,ushort,utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)
0x1400183bb  test    al, al
0x1400183bd  jnz     short loc_1400183E1
0x1400183bf  mov     rcx, [rbp+28h]; this
0x1400183c3  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x1400183ca  mov     ebx, 8007000Eh
0x1400183cf  mov     edx, 11Eh; void *
0x1400183d4  mov     r9d, ebx; char *
0x1400183d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400183dc  jmp     loc_140018541
0x1400183e1  mov     rdi, qword ptr [rbp+var_40+8]
0x1400183e5  lea     rax, [rbp+var_18]
0x1400183e9  mov     r12, qword ptr [rbp+var_40]
0x1400183ed  xor     esi, esi
0x1400183ef  mov     [rbp+var_28], rax
0x1400183f3  sub     rdi, r12
0x1400183f6  lea     rax, [rbp+var_18]
0x1400183fa  sar     rdi, 5
0x1400183fe  mov     [rbp+var_20], rax
0x140018402  xor     r14d, r14d
0x140018405  xor     eax, eax
0x140018407  mov     [rbp+var_18], ax
0x14001840b  test    rdi, rdi
0x14001840e  jz      short loc_14001846A
0x140018410  mov     ecx, r14d
0x140018413  lea     rdx, [rbp+var_50]
0x140018417  shl     rcx, 5
0x14001841b  mov     rax, [rcx+r12]
0x14001841f  mov     rcx, [rcx+r12+8]
0x140018424  sub     rcx, rax
0x140018427  mov     [rbp+var_50], rax
0x14001842b  sar     rcx, 1
0x14001842e  mov     [rbp+var_48], rcx
0x140018432  lea     rcx, [rbp+var_28]; this
0x140018436  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x14001843b  test    al, al
0x14001843d  jz      loc_1400184CB
0x140018443  mov     rdx, [rbp+var_28]; unsigned __int16 *
0x140018447  lea     r8, [rbp+arg_8]; bool *
0x14001844b  mov     rcx, r15; this
0x14001844e  call    ?KeyExists@OfflineHive@Csl@@QEBAJPEBGAEA_N@Z; Csl::OfflineHive::KeyExists(ushort const *,bool &)
0x140018453  mov     ebx, eax
0x140018455  test    eax, eax
0x140018457  js      short loc_140018494
0x140018459  inc     r14d
0x14001845c  cmp     [rbp+arg_8], sil
0x140018460  jz      short loc_14001848F
0x140018462  mov     eax, r14d
0x140018465  cmp     rax, rdi
0x140018468  jb      short loc_140018410
0x14001846a  mov     rdx, [rbp+var_28]; unsigned __int16 *
0x14001846e  lea     r8, [rbp+arg_8]; bool *
0x140018472  mov     rcx, r15; this
0x140018475  mov     [rbp+arg_8], 0
0x140018479  call    ?CreateKey@OfflineHive@Csl@@QEAAJQEBGAEA_N@Z; Csl::OfflineHive::CreateKey(ushort const * const,bool &)
0x14001847e  mov     ebx, eax
0x140018480  test    eax, eax
0x140018482  jns     loc_14001851F
0x140018488  mov     edx, 13Ah
0x14001848d  jmp     short loc_140018499
0x14001848f  mov     esi, r14d
0x140018492  jmp     short loc_14001846A
0x140018494  mov     edx, 127h; void *
0x140018499  mov     r9d, eax; char *
0x14001849c  mov     rcx, [rbp+28h]; this
0x1400184a0  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x1400184a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400184ac  mov     rcx, [rbp+var_28]; void *
0x1400184b0  lea     rax, [rbp+var_18]
0x1400184b4  cmp     rcx, rax
0x1400184b7  jz      loc_140018541
0x1400184bd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400184c4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400184c9  jmp     short loc_140018541
0x1400184cb  mov     edx, 125h
0x1400184d0  jmp     loc_140018575
0x1400184d5  mov     ecx, esi
0x1400184d7  lea     rdx, [rbp+var_50]
0x1400184db  shl     rcx, 5
0x1400184df  mov     rax, [rcx+r12]
0x1400184e3  mov     rcx, [rcx+r12+8]
0x1400184e8  sub     rcx, rax
0x1400184eb  mov     [rbp+var_50], rax
0x1400184ef  sar     rcx, 1
0x1400184f2  mov     [rbp+var_48], rcx
0x1400184f6  lea     rcx, [rbp+var_28]; this
0x1400184fa  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x1400184ff  test    al, al
0x140018501  jz      short loc_140018570
0x140018503  mov     rdx, [rbp+var_28]; unsigned __int16 *
0x140018507  lea     r8, [rbp+arg_8]; bool *
0x14001850b  mov     rcx, r15; this
0x14001850e  mov     [rbp+arg_8], 0
0x140018512  call    ?CreateKey@OfflineHive@Csl@@QEAAJQEBGAEA_N@Z; Csl::OfflineHive::CreateKey(ushort const * const,bool &)
0x140018517  mov     ebx, eax
0x140018519  test    eax, eax
0x14001851b  js      short loc_140018566
0x14001851d  inc     esi
0x14001851f  mov     eax, esi
0x140018521  cmp     rax, rdi
0x140018524  jb      short loc_1400184D5
0x140018526  mov     rcx, [rbp+var_28]; void *
0x14001852a  lea     rax, [rbp+var_18]
0x14001852e  cmp     rcx, rax
0x140018531  jz      short loc_14001853F
0x140018533  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001853a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001853f  xor     ebx, ebx
0x140018541  lea     rcx, [rbp+var_40]
0x140018545  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x14001854a  mov     eax, ebx
0x14001854c  lea     r11, [rsp+70h+var_s0]
0x140018551  mov     rbx, [r11+30h]
0x140018555  mov     rsi, [r11+40h]
0x140018559  mov     rsp, r11
0x14001855c  pop     r15
0x14001855e  pop     r14
0x140018560  pop     r12
0x140018562  pop     rdi
0x140018563  pop     rbp
0x140018564  retn
0x140018566  mov     edx, 141h
0x14001856b  jmp     loc_140018499
0x140018570  mov     edx, 13Fh
0x140018575  mov     ebx, 8007000Eh
0x14001857a  mov     r9d, ebx
0x14001857d  jmp     loc_14001849C
```
