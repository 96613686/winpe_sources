# RtlConvertWin32FilePathToNtFilePath

- ea: `0x1800573a4`
- end: `0x1800576bf`
- name: `RtlConvertWin32FilePathToNtFilePath`
- size: `795`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180057134`

## callees

- `0x18002bf20`
- `0x1800573a4`
- `0x1800576c8`
- `0x1800576ec`
- `0x180057718`
- `0x1800892ec`
- `0x1800894c0`

## string_xrefs

- `0x180057410`: `Not-null check failed: PathIn`
- `0x1800573e8`: `onecore\base\lstring\path.cpp`
- `0x18005742f`: `onecore\base\lstring\path.cpp`
- `0x180057477`: `onecore\base\lstring\path.cpp`
- `0x1800574e3`: `onecore\base\lstring\path.cpp`
- `0x18005755d`: `onecore\base\lstring\path.cpp`
- `0x1800573ff`: `RtlConvertWin32FilePathToNtFilePath`
- `0x180057446`: `RtlConvertWin32FilePathToNtFilePath`
- `0x18005748a`: `RtlConvertWin32FilePathToNtFilePath`
- `0x1800574f6`: `RtlConvertWin32FilePathToNtFilePath`
- `0x180057570`: `RtlConvertWin32FilePathToNtFilePath`
- `0x180057455`: `Not-null check failed: PathOut`
- `0x18005757b`: `(PathIn->Length > 4 * sizeof(WCHAR)) && (PathIn->Buffer[3] == L'\\')`
- `0x180057495`: `PathIn->Length >= 2 * sizeof(WCHAR)`

## pseudocode

```c
__int64 __fastcall RtlConvertWin32FilePathToNtFilePath(unsigned __int64 *a1, _QWORD *a2)
{
  unsigned __int64 v5; // rdx
  __int64 v6; // rcx
  const char *v7; // rax
  _WORD *v8; // rax
  _WORD *v9; // rax
  char v10; // di
  __int16 v11; // r9
  __int128 v12; // xmm0
  const wchar_t *v13; // xmm1_8
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // xmm1_8
  __int64 v17; // rdx
  __int64 v18; // rcx
  int v19; // esi
  __int16 *v20; // rdx
  __int16 *v21; // rcx
  __int16 *v22; // r10
  __int16 *v23; // r9
  __int16 v24; // r8
  __int16 *v25; // rax
  __int64 v26; // xmm2_8
  __int128 v27; // [rsp+20h] [rbp-60h] BYREF
  __int64 v28; // [rsp+30h] [rbp-50h]
  const char *v29; // [rsp+38h] [rbp-48h]
  __int128 v30; // [rsp+40h] [rbp-40h] BYREF
  const wchar_t *v31; // [rsp+50h] [rbp-30h]
  unsigned __int64 v32; // [rsp+58h] [rbp-28h]
  __int64 v33; // [rsp+60h] [rbp-20h]
  _WORD *v34; // [rsp+68h] [rbp-18h]
  int v35; // [rsp+70h] [rbp-10h] BYREF

  v35 = 0;
  if ( a2 )
    *a2 = 0;
  if ( !a1 )
  {
    v28 = 300;
    *(_QWORD *)&v27 = "onecore\\base\\lstring\\path.cpp";
    *((_QWORD *)&v27 + 1) = "RtlConvertWin32FilePathToNtFilePath";
    v29 = "Not-null check failed: PathIn";
    RtlReportErrorOrigination(&v27, a2, 3221225485LL);
    return 3221225485LL;
  }
  if ( !a2 )
  {
    v28 = 301;
    *(_QWORD *)&v27 = "onecore\\base\\lstring\\path.cpp";
    *((_QWORD *)&v27 + 1) = "RtlConvertWin32FilePathToNtFilePath";
    v29 = "Not-null check failed: PathOut";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v35,
             &v27,
             a1);
  }
  v5 = *a1;
  v6 = 4;
  if ( v5 < 4 )
  {
    v28 = 302;
    *(_QWORD *)&v27 = "onecore\\base\\lstring\\path.cpp";
    *((_QWORD *)&v27 + 1) = "RtlConvertWin32FilePathToNtFilePath";
    v7 = "PathIn->Length >= 2 * sizeof(WCHAR)";
LABEL_9:
    v29 = v7;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v35,
             &v27,
             3221225485LL);
  }
  if ( v5 >= 8 )
  {
    v8 = (_WORD *)a1[2];
    if ( *v8 == 92 && v8[1] == 63 && v8[2] == 63 && v8[3] == 92 )
    {
      v28 = 312;
      *(_QWORD *)&v27 = "onecore\\base\\lstring\\path.cpp";
      *((_QWORD *)&v27 + 1) = "RtlConvertWin32FilePathToNtFilePath";
      v29 = 0;
      return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
               &v35,
               &v27,
               3221225485LL);
    }
  }
  v9 = (_WORD *)a1[2];
  v10 = 1;
  if ( *v9 == 92 && v9[1] == 92 )
  {
    if ( v5 >= 6 && ((v11 = v9[2], v11 == 63) || v11 == 46) )
    {
      if ( v5 <= 8 || v9[3] != 92 )
      {
        v28 = 334;
        *(_QWORD *)&v27 = "onecore\\base\\lstring\\path.cpp";
        *((_QWORD *)&v27 + 1) = "RtlConvertWin32FilePathToNtFilePath";
        v7 = "(PathIn->Length > 4 * sizeof(WCHAR)) && (PathIn->Buffer[3] == L'\\\\')";
        goto LABEL_9;
      }
      v12 = g_LUNICODE_STRING__bslash__q__q__bslash_;
      v10 = 0;
      v13 = L"\\??\\";
    }
    else
    {
      v12 = g_LUNICODE_STRING__bslash__q__q__bslash_UNC_bslash_;
      v6 = 2;
      v13 = L"\\??\\UNC\\";
    }
  }
  else
  {
    v12 = g_LUNICODE_STRING__bslash__q__q__bslash_;
    v6 = 0;
    v13 = L"\\??\\";
  }
  v14 = 2 * v6;
  v31 = v13;
  v34 = &v9[(unsigned __int64)v14 / 2];
  v15 = a1[1] - v14;
  v32 = v5 - v14;
  v33 = v15;
  v30 = v12;
  v28 = 0;
  v27 = 0;
  Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(&v27);
  v16 = a2[2];
  v27 = *(_OWORD *)a2;
  v28 = v16;
  *(_OWORD *)a2 = 0;
  a2[2] = 0;
  v19 = RtlConcatenateLUnicodeStrings(v18, v17, &v30, &v27);
  if ( v19 >= 0 )
  {
    if ( v10 )
    {
      v20 = (__int16 *)v28;
      v21 = (__int16 *)v28;
      v22 = (__int16 *)(v28 + v27);
      v23 = 0;
      while ( v20 != v22 )
      {
        v24 = *v20;
        v25 = v21;
        ++v20;
        if ( v24 == 32 )
          v25 = v23;
        v23 = v25;
        if ( v24 == 47 )
        {
          v24 = 92;
        }
        else if ( v24 != 92 )
        {
          goto LABEL_38;
        }
        if ( v25 )
          v21 = v25;
LABEL_38:
        *v21++ = v24;
      }
    }
    v26 = v28;
    *(_OWORD *)a2 = v27;
    v19 = 0;
    v28 = 0;
    a2[2] = v26;
    v27 = 0;
  }
  Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(&v27);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1800573a4  mov     [rsp-18h+arg_0], rbx
0x1800573a9  mov     [rsp-18h+arg_10], rsi
0x1800573ae  push    rbp
0x1800573af  push    rdi
0x1800573b0  push    r15
0x1800573b2  mov     rbp, rsp
0x1800573b5  sub     rsp, 80h
0x1800573bc  mov     rax, cs:__security_cookie
0x1800573c3  xor     rax, rsp
0x1800573c6  mov     [rbp+var_8], rax
0x1800573ca  mov     [rbp+var_10], 0
0x1800573d1  mov     rbx, rdx
0x1800573d4  mov     r8, rcx
0x1800573d7  test    rdx, rdx
0x1800573da  jz      short loc_1800573E3
0x1800573dc  mov     qword ptr [rdx], 0
0x1800573e3  test    r8, r8
0x1800573e6  jnz     short loc_18005742A
0x1800573e8  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x1800573ef  mov     [rbp+var_50], 12Ch
0x1800573f7  mov     qword ptr [rbp+var_60], rax
0x1800573fb  lea     rcx, [rbp+var_60]
0x1800573ff  lea     rax, aRtlconvertwin3; "RtlConvertWin32FilePathToNtFilePath"
0x180057406  mov     r8d, 0C000000Dh
0x18005740c  mov     qword ptr [rbp+var_60+8], rax
0x180057410  lea     rax, aNotNullCheckFa_0; "Not-null check failed: PathIn"
0x180057417  mov     [rbp+var_48], rax
0x18005741b  call    RtlReportErrorOrigination
0x180057420  mov     eax, 0C000000Dh
0x180057425  jmp     loc_18005769A
0x18005742a  test    rbx, rbx
0x18005742d  jnz     short loc_18005746A
0x18005742f  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180057436  mov     [rbp+var_50], 12Dh
0x18005743e  mov     qword ptr [rbp+var_60], rax
0x180057442  lea     rdx, [rbp+var_60]
0x180057446  lea     rax, aRtlconvertwin3; "RtlConvertWin32FilePathToNtFilePath"
0x18005744d  mov     qword ptr [rbp+var_60+8], rax
0x180057451  lea     rcx, [rbp+var_10]
0x180057455  lea     rax, aNotNullCheckFa; "Not-null check failed: PathOut"
0x18005745c  mov     [rbp+var_48], rax
0x180057460  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180057465  jmp     loc_18005769A
0x18005746a  mov     rdx, [rcx]
0x18005746d  mov     ecx, 4
0x180057472  cmp     rdx, rcx
0x180057475  jnb     short loc_1800574B8
0x180057477  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18005747e  mov     [rbp+var_50], 12Eh
0x180057486  mov     qword ptr [rbp+var_60], rax
0x18005748a  lea     rax, aRtlconvertwin3; "RtlConvertWin32FilePathToNtFilePath"
0x180057491  mov     qword ptr [rbp+var_60+8], rax
0x180057495  lea     rax, aPathinLength2S; "PathIn->Length >= 2 * sizeof(WCHAR)"
0x18005749c  mov     [rbp+var_48], rax
0x1800574a0  mov     r8d, 0C000000Dh
0x1800574a6  lea     rdx, [rbp+var_60]
0x1800574aa  lea     rcx, [rbp+var_10]
0x1800574ae  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800574b3  jmp     loc_18005769A
0x1800574b8  mov     r15d, 5Ch ; '\'
0x1800574be  cmp     rdx, 8
0x1800574c2  jb      short loc_18005750B
0x1800574c4  mov     rax, [r8+10h]
0x1800574c8  cmp     [rax], r15w
0x1800574cc  jnz     short loc_18005750B
0x1800574ce  cmp     word ptr [rax+2], 3Fh ; '?'
0x1800574d3  jnz     short loc_18005750B
0x1800574d5  cmp     word ptr [rax+4], 3Fh ; '?'
0x1800574da  jnz     short loc_18005750B
0x1800574dc  cmp     [rax+6], r15w
0x1800574e1  jnz     short loc_18005750B
0x1800574e3  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x1800574ea  mov     [rbp+var_50], 138h
0x1800574f2  mov     qword ptr [rbp+var_60], rax
0x1800574f6  lea     rax, aRtlconvertwin3; "RtlConvertWin32FilePathToNtFilePath"
0x1800574fd  mov     qword ptr [rbp+var_60+8], rax
0x180057501  mov     [rbp+var_48], 0
0x180057509  jmp     short loc_1800574A0
0x18005750b  mov     rax, [r8+10h]
0x18005750f  mov     dil, 1
0x180057512  cmp     [rax], r15w
0x180057516  jnz     loc_18005759D
0x18005751c  cmp     [rax+2], r15w
0x180057521  jnz     short loc_18005759D
0x180057523  cmp     rdx, 6
0x180057527  jb      short loc_180057587
0x180057529  movzx   r9d, word ptr [rax+4]
0x18005752e  cmp     r9w, 3Fh ; '?'
0x180057533  jz      short loc_18005753C
0x180057535  cmp     r9w, 2Eh ; '.'
0x18005753a  jnz     short loc_180057587
0x18005753c  cmp     rdx, 8
0x180057540  jbe     short loc_18005755D
0x180057542  cmp     [rax+6], r15w
0x180057547  jnz     short loc_18005755D
0x180057549  movups  xmm0, cs:g_LUNICODE_STRING__bslash__q__q__bslash_
0x180057550  xor     dil, dil
0x180057553  movsd   xmm1, cs:off_180031980; "\\??\\"
0x18005755b  jmp     short loc_1800575AE
0x18005755d  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180057564  mov     [rbp+var_50], 14Eh
0x18005756c  mov     qword ptr [rbp+var_60], rax
0x180057570  lea     rax, aRtlconvertwin3; "RtlConvertWin32FilePathToNtFilePath"
0x180057577  mov     qword ptr [rbp+var_60+8], rax
0x18005757b  lea     rax, aPathinLength4S; "(PathIn->Length > 4 * sizeof(WCHAR)) &&"...
0x180057582  jmp     loc_18005749C
0x180057587  movups  xmm0, cs:g_LUNICODE_STRING__bslash__q__q__bslash_UNC_bslash_
0x18005758e  mov     ecx, 2
0x180057593  movsd   xmm1, cs:off_180031998; "\\??\\UNC\\"
0x18005759b  jmp     short loc_1800575AE
0x18005759d  movups  xmm0, cs:g_LUNICODE_STRING__bslash__q__q__bslash_
0x1800575a4  xor     ecx, ecx
0x1800575a6  movsd   xmm1, cs:off_180031980; "\\??\\"
0x1800575ae  add     rcx, rcx
0x1800575b1  movsd   [rbp+var_30], xmm1
0x1800575b6  add     rax, rcx
0x1800575b9  sub     rdx, rcx
0x1800575bc  mov     [rbp+var_18], rax
0x1800575c0  mov     rax, [r8+8]
0x1800575c4  sub     rax, rcx
0x1800575c7  mov     [rbp+var_28], rdx
0x1800575cb  mov     [rbp+var_20], rax
0x1800575cf  lea     rcx, [rbp+var_60]
0x1800575d3  movups  [rbp+var_40], xmm0
0x1800575d7  xor     eax, eax
0x1800575d9  xorps   xmm0, xmm0
0x1800575dc  mov     [rbp+var_50], rax
0x1800575e0  movups  [rbp+var_60], xmm0
0x1800575e4  call    ?Close@?$AutoString@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(void)
0x1800575e9  movups  xmm0, xmmword ptr [rbx]
0x1800575ec  lea     r9, [rbp+var_60]
0x1800575f0  xor     eax, eax
0x1800575f2  movsd   xmm1, qword ptr [rbx+10h]
0x1800575f7  lea     r8, [rbp+var_40]
0x1800575fb  movups  [rbp+var_60], xmm0
0x1800575ff  xorps   xmm0, xmm0
0x180057602  movsd   [rbp+var_50], xmm1
0x180057607  movups  xmmword ptr [rbx], xmm0
0x18005760a  mov     [rbx+10h], rax
0x18005760e  call    RtlConcatenateLUnicodeStrings
0x180057613  mov     esi, eax
0x180057615  test    eax, eax
0x180057617  js      short loc_18005768F
0x180057619  test    dil, dil
0x18005761c  jz      short loc_18005766F
0x18005761e  mov     rdx, [rbp+var_50]
0x180057622  mov     r10, qword ptr [rbp+var_60]
0x180057626  mov     rcx, rdx
0x180057629  add     r10, rdx
0x18005762c  xor     r9d, r9d
0x18005762f  jmp     short loc_18005766A
0x180057631  movzx   r8d, word ptr [rdx]
0x180057635  mov     rax, rcx
0x180057638  add     rdx, 2
0x18005763c  cmp     r8w, 20h ; ' '
0x180057641  cmovz   rax, r9
0x180057645  mov     r9, rax
0x180057648  cmp     r8w, 2Fh ; '/'
0x18005764d  jnz     short loc_180057655
0x18005764f  movzx   r8d, r15w
0x180057653  jmp     short loc_18005765B
0x180057655  cmp     r8w, r15w
0x180057659  jnz     short loc_180057662
0x18005765b  test    rax, rax
0x18005765e  cmovnz  rcx, rax
0x180057662  mov     [rcx], r8w
0x180057666  add     rcx, 2
0x18005766a  cmp     rdx, r10
0x18005766d  jnz     short loc_180057631
0x18005766f  movups  xmm1, [rbp+var_60]
0x180057673  xor     eax, eax
0x180057675  movsd   xmm2, [rbp+var_50]
0x18005767a  xorps   xmm0, xmm0
0x18005767d  movups  xmmword ptr [rbx], xmm1
0x180057680  xor     esi, esi
0x180057682  mov     [rbp+var_50], rax
0x180057686  movsd   qword ptr [rbx+10h], xmm2
0x18005768b  movups  [rbp+var_60], xmm0
0x18005768f  lea     rcx, [rbp+var_60]
0x180057693  call    ?Close@?$AutoString@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(void)
0x180057698  mov     eax, esi
0x18005769a  mov     rcx, [rbp+var_8]
0x18005769e  xor     rcx, rsp; StackCookie
0x1800576a1  call    __security_check_cookie
0x1800576a6  lea     r11, [rsp+80h+var_s0]
0x1800576ae  mov     rbx, [r11+20h]
0x1800576b2  mov     rsi, [r11+30h]
0x1800576b6  mov     rsp, r11
0x1800576b9  pop     r15
0x1800576bb  pop     rdi
0x1800576bc  pop     rbp
0x1800576bd  retn
```
