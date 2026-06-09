# RtlConvertWin32FilePathToNtFilePath

- ea: `0x1800573a4`
- end: `0x1800576a4`
- name: `RtlConvertWin32FilePathToNtFilePath`
- size: `768`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180057134`

## callees

- `0x180011ecc`
- `0x180011ef8`
- `0x18002c0d0`
- `0x1800573a4`
- `0x180089cfc`
- `0x180089ed0`

## string_xrefs

- `0x1800573e8`: `onecore\base\lstring\path.cpp`
- `0x180057428`: `onecore\base\lstring\path.cpp`
- `0x18005745c`: `onecore\base\lstring\path.cpp`
- `0x1800574c8`: `onecore\base\lstring\path.cpp`
- `0x180057542`: `onecore\base\lstring\path.cpp`
- `0x180057406`: `Not-null check failed: PathIn`
- `0x180057446`: `Not-null check failed: PathOut`
- `0x18005747a`: `PathIn->Length >= 2 * sizeof(WCHAR)`
- `0x180057560`: `(PathIn->Length > 4 * sizeof(WCHAR)) && (PathIn->Buffer[3] == L'\\')`
- `0x1800573fb`: `RtlConvertWin32FilePathToNtFilePath`
- `0x18005743b`: `RtlConvertWin32FilePathToNtFilePath`
- `0x18005746f`: `RtlConvertWin32FilePathToNtFilePath`
- `0x1800574db`: `RtlConvertWin32FilePathToNtFilePath`
- `0x180057555`: `RtlConvertWin32FilePathToNtFilePath`

## pseudocode

```c
__int64 __fastcall RtlConvertWin32FilePathToNtFilePath(unsigned __int64 *a1, _QWORD *a2)
{
  const char *v4; // rax
  unsigned __int64 v6; // rdx
  __int64 v7; // rcx
  const char *v8; // rax
  _WORD *v9; // rax
  _WORD *v10; // rax
  char v11; // di
  __int16 v12; // r9
  __int128 v13; // xmm0
  const wchar_t *v14; // xmm1_8
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // xmm1_8
  __int64 v18; // rdx
  __int64 v19; // rcx
  int v20; // esi
  __int16 *v21; // rdx
  __int16 *v22; // rcx
  __int16 *v23; // r10
  __int16 *v24; // r9
  __int16 v25; // r8
  __int16 *v26; // rax
  __int64 v27; // xmm2_8
  __int128 v28; // [rsp+20h] [rbp-60h] BYREF
  __int64 v29; // [rsp+30h] [rbp-50h]
  const char *v30; // [rsp+38h] [rbp-48h]
  __int128 v31; // [rsp+40h] [rbp-40h] BYREF
  const wchar_t *v32; // [rsp+50h] [rbp-30h]
  unsigned __int64 v33; // [rsp+58h] [rbp-28h]
  __int64 v34; // [rsp+60h] [rbp-20h]
  _WORD *v35; // [rsp+68h] [rbp-18h]
  int v36; // [rsp+70h] [rbp-10h] BYREF

  v36 = 0;
  if ( a2 )
    *a2 = 0;
  if ( !a1 )
  {
    v29 = 300;
    *(_QWORD *)&v28 = "onecore\\base\\lstring\\path.cpp";
    *((_QWORD *)&v28 + 1) = "RtlConvertWin32FilePathToNtFilePath";
    v4 = "Not-null check failed: PathIn";
LABEL_5:
    v30 = v4;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v36,
             &v28,
             a1);
  }
  if ( !a2 )
  {
    v29 = 301;
    *(_QWORD *)&v28 = "onecore\\base\\lstring\\path.cpp";
    *((_QWORD *)&v28 + 1) = "RtlConvertWin32FilePathToNtFilePath";
    v4 = "Not-null check failed: PathOut";
    goto LABEL_5;
  }
  v6 = *a1;
  v7 = 4;
  if ( v6 < 4 )
  {
    v29 = 302;
    *(_QWORD *)&v28 = "onecore\\base\\lstring\\path.cpp";
    *((_QWORD *)&v28 + 1) = "RtlConvertWin32FilePathToNtFilePath";
    v8 = "PathIn->Length >= 2 * sizeof(WCHAR)";
LABEL_10:
    v30 = v8;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v36,
             &v28,
             3221225485LL);
  }
  if ( v6 >= 8 )
  {
    v9 = (_WORD *)a1[2];
    if ( *v9 == 92 && v9[1] == 63 && v9[2] == 63 && v9[3] == 92 )
    {
      v29 = 312;
      *(_QWORD *)&v28 = "onecore\\base\\lstring\\path.cpp";
      *((_QWORD *)&v28 + 1) = "RtlConvertWin32FilePathToNtFilePath";
      v30 = 0;
      return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
               &v36,
               &v28,
               3221225485LL);
    }
  }
  v10 = (_WORD *)a1[2];
  v11 = 1;
  if ( *v10 == 92 && v10[1] == 92 )
  {
    if ( v6 >= 6 && ((v12 = v10[2], v12 == 63) || v12 == 46) )
    {
      if ( v6 <= 8 || v10[3] != 92 )
      {
        v29 = 334;
        *(_QWORD *)&v28 = "onecore\\base\\lstring\\path.cpp";
        *((_QWORD *)&v28 + 1) = "RtlConvertWin32FilePathToNtFilePath";
        v8 = "(PathIn->Length > 4 * sizeof(WCHAR)) && (PathIn->Buffer[3] == L'\\\\')";
        goto LABEL_10;
      }
      v13 = g_LUNICODE_STRING__bslash__q__q__bslash_;
      v11 = 0;
      v14 = L"\\??\\";
    }
    else
    {
      v13 = g_LUNICODE_STRING__bslash__q__q__bslash_UNC_bslash_;
      v7 = 2;
      v14 = L"\\??\\UNC\\";
    }
  }
  else
  {
    v13 = g_LUNICODE_STRING__bslash__q__q__bslash_;
    v7 = 0;
    v14 = L"\\??\\";
  }
  v15 = 2 * v7;
  v32 = v14;
  v35 = &v10[(unsigned __int64)v15 / 2];
  v16 = a1[1] - v15;
  v33 = v6 - v15;
  v34 = v16;
  v31 = v13;
  v29 = 0;
  v28 = 0;
  Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(&v28);
  v17 = a2[2];
  v28 = *(_OWORD *)a2;
  v29 = v17;
  *(_OWORD *)a2 = 0;
  a2[2] = 0;
  v20 = RtlConcatenateLUnicodeStrings(v19, v18, &v31, &v28);
  if ( v20 >= 0 )
  {
    if ( v11 )
    {
      v21 = (__int16 *)v29;
      v22 = (__int16 *)v29;
      v23 = (__int16 *)(v29 + v28);
      v24 = 0;
      while ( v21 != v23 )
      {
        v25 = *v21;
        v26 = v22;
        ++v21;
        if ( v25 == 32 )
          v26 = v24;
        v24 = v26;
        if ( v25 == 47 )
        {
          v25 = 92;
        }
        else if ( v25 != 92 )
        {
          goto LABEL_39;
        }
        if ( v26 )
          v22 = v26;
LABEL_39:
        *v22++ = v25;
      }
    }
    v27 = v29;
    *(_OWORD *)a2 = v28;
    v20 = 0;
    v29 = 0;
    a2[2] = v27;
    v28 = 0;
  }
  Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(&v28);
  return (unsigned int)v20;
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
0x1800573e6  jnz     short loc_180057423
0x1800573e8  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x1800573ef  mov     [rbp+var_50], 12Ch
0x1800573f7  mov     qword ptr [rbp+var_60], rax
0x1800573fb  lea     rax, aRtlconvertwin3; "RtlConvertWin32FilePathToNtFilePath"
0x180057402  mov     qword ptr [rbp+var_60+8], rax
0x180057406  lea     rax, aNotNullCheckFa_0; "Not-null check failed: PathIn"
0x18005740d  lea     rdx, [rbp+var_60]
0x180057411  mov     [rbp+var_48], rax
0x180057415  lea     rcx, [rbp+var_10]
0x180057419  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005741e  jmp     loc_18005767F
0x180057423  test    rbx, rbx
0x180057426  jnz     short loc_18005744F
0x180057428  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18005742f  mov     [rbp+var_50], 12Dh
0x180057437  mov     qword ptr [rbp+var_60], rax
0x18005743b  lea     rax, aRtlconvertwin3; "RtlConvertWin32FilePathToNtFilePath"
0x180057442  mov     qword ptr [rbp+var_60+8], rax
0x180057446  lea     rax, aNotNullCheckFa; "Not-null check failed: PathOut"
0x18005744d  jmp     short loc_18005740D
0x18005744f  mov     rdx, [rcx]
0x180057452  mov     ecx, 4
0x180057457  cmp     rdx, rcx
0x18005745a  jnb     short loc_18005749D
0x18005745c  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180057463  mov     [rbp+var_50], 12Eh
0x18005746b  mov     qword ptr [rbp+var_60], rax
0x18005746f  lea     rax, aRtlconvertwin3; "RtlConvertWin32FilePathToNtFilePath"
0x180057476  mov     qword ptr [rbp+var_60+8], rax
0x18005747a  lea     rax, aPathinLength2S; "PathIn->Length >= 2 * sizeof(WCHAR)"
0x180057481  mov     [rbp+var_48], rax
0x180057485  mov     r8d, 0C000000Dh
0x18005748b  lea     rdx, [rbp+var_60]
0x18005748f  lea     rcx, [rbp+var_10]
0x180057493  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180057498  jmp     loc_18005767F
0x18005749d  mov     r15d, 5Ch ; '\'
0x1800574a3  cmp     rdx, 8
0x1800574a7  jb      short loc_1800574F0
0x1800574a9  mov     rax, [r8+10h]
0x1800574ad  cmp     [rax], r15w
0x1800574b1  jnz     short loc_1800574F0
0x1800574b3  cmp     word ptr [rax+2], 3Fh ; '?'
0x1800574b8  jnz     short loc_1800574F0
0x1800574ba  cmp     word ptr [rax+4], 3Fh ; '?'
0x1800574bf  jnz     short loc_1800574F0
0x1800574c1  cmp     [rax+6], r15w
0x1800574c6  jnz     short loc_1800574F0
0x1800574c8  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x1800574cf  mov     [rbp+var_50], 138h
0x1800574d7  mov     qword ptr [rbp+var_60], rax
0x1800574db  lea     rax, aRtlconvertwin3; "RtlConvertWin32FilePathToNtFilePath"
0x1800574e2  mov     qword ptr [rbp+var_60+8], rax
0x1800574e6  mov     [rbp+var_48], 0
0x1800574ee  jmp     short loc_180057485
0x1800574f0  mov     rax, [r8+10h]
0x1800574f4  mov     dil, 1
0x1800574f7  cmp     [rax], r15w
0x1800574fb  jnz     loc_180057582
0x180057501  cmp     [rax+2], r15w
0x180057506  jnz     short loc_180057582
0x180057508  cmp     rdx, 6
0x18005750c  jb      short loc_18005756C
0x18005750e  movzx   r9d, word ptr [rax+4]
0x180057513  cmp     r9w, 3Fh ; '?'
0x180057518  jz      short loc_180057521
0x18005751a  cmp     r9w, 2Eh ; '.'
0x18005751f  jnz     short loc_18005756C
0x180057521  cmp     rdx, 8
0x180057525  jbe     short loc_180057542
0x180057527  cmp     [rax+6], r15w
0x18005752c  jnz     short loc_180057542
0x18005752e  movups  xmm0, cs:g_LUNICODE_STRING__bslash__q__q__bslash_
0x180057535  xor     dil, dil
0x180057538  movsd   xmm1, cs:off_180031970; "\\??\\"
0x180057540  jmp     short loc_180057593
0x180057542  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180057549  mov     [rbp+var_50], 14Eh
0x180057551  mov     qword ptr [rbp+var_60], rax
0x180057555  lea     rax, aRtlconvertwin3; "RtlConvertWin32FilePathToNtFilePath"
0x18005755c  mov     qword ptr [rbp+var_60+8], rax
0x180057560  lea     rax, aPathinLength4S; "(PathIn->Length > 4 * sizeof(WCHAR)) &&"...
0x180057567  jmp     loc_180057481
0x18005756c  movups  xmm0, cs:g_LUNICODE_STRING__bslash__q__q__bslash_UNC_bslash_
0x180057573  mov     ecx, 2
0x180057578  movsd   xmm1, cs:off_180031988; "\\??\\UNC\\"
0x180057580  jmp     short loc_180057593
0x180057582  movups  xmm0, cs:g_LUNICODE_STRING__bslash__q__q__bslash_
0x180057589  xor     ecx, ecx
0x18005758b  movsd   xmm1, cs:off_180031970; "\\??\\"
0x180057593  add     rcx, rcx
0x180057596  movsd   [rbp+var_30], xmm1
0x18005759b  add     rax, rcx
0x18005759e  sub     rdx, rcx
0x1800575a1  mov     [rbp+var_18], rax
0x1800575a5  mov     rax, [r8+8]
0x1800575a9  sub     rax, rcx
0x1800575ac  mov     [rbp+var_28], rdx
0x1800575b0  mov     [rbp+var_20], rax
0x1800575b4  lea     rcx, [rbp+var_60]
0x1800575b8  movups  [rbp+var_40], xmm0
0x1800575bc  xor     eax, eax
0x1800575be  xorps   xmm0, xmm0
0x1800575c1  mov     [rbp+var_50], rax
0x1800575c5  movups  [rbp+var_60], xmm0
0x1800575c9  call    ?Close@?$AutoString@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(void)
0x1800575ce  movups  xmm0, xmmword ptr [rbx]
0x1800575d1  lea     r9, [rbp+var_60]
0x1800575d5  xor     eax, eax
0x1800575d7  movsd   xmm1, qword ptr [rbx+10h]
0x1800575dc  lea     r8, [rbp+var_40]
0x1800575e0  movups  [rbp+var_60], xmm0
0x1800575e4  xorps   xmm0, xmm0
0x1800575e7  movsd   [rbp+var_50], xmm1
0x1800575ec  movups  xmmword ptr [rbx], xmm0
0x1800575ef  mov     [rbx+10h], rax
0x1800575f3  call    RtlConcatenateLUnicodeStrings
0x1800575f8  mov     esi, eax
0x1800575fa  test    eax, eax
0x1800575fc  js      short loc_180057674
0x1800575fe  test    dil, dil
0x180057601  jz      short loc_180057654
0x180057603  mov     rdx, [rbp+var_50]
0x180057607  mov     r10, qword ptr [rbp+var_60]
0x18005760b  mov     rcx, rdx
0x18005760e  add     r10, rdx
0x180057611  xor     r9d, r9d
0x180057614  jmp     short loc_18005764F
0x180057616  movzx   r8d, word ptr [rdx]
0x18005761a  mov     rax, rcx
0x18005761d  add     rdx, 2
0x180057621  cmp     r8w, 20h ; ' '
0x180057626  cmovz   rax, r9
0x18005762a  mov     r9, rax
0x18005762d  cmp     r8w, 2Fh ; '/'
0x180057632  jnz     short loc_18005763A
0x180057634  movzx   r8d, r15w
0x180057638  jmp     short loc_180057640
0x18005763a  cmp     r8w, r15w
0x18005763e  jnz     short loc_180057647
0x180057640  test    rax, rax
0x180057643  cmovnz  rcx, rax
0x180057647  mov     [rcx], r8w
0x18005764b  add     rcx, 2
0x18005764f  cmp     rdx, r10
0x180057652  jnz     short loc_180057616
0x180057654  movups  xmm1, [rbp+var_60]
0x180057658  xor     eax, eax
0x18005765a  movsd   xmm2, [rbp+var_50]
0x18005765f  xorps   xmm0, xmm0
0x180057662  movups  xmmword ptr [rbx], xmm1
0x180057665  xor     esi, esi
0x180057667  mov     [rbp+var_50], rax
0x18005766b  movsd   qword ptr [rbx+10h], xmm2
0x180057670  movups  [rbp+var_60], xmm0
0x180057674  lea     rcx, [rbp+var_60]
0x180057678  call    ?Close@?$AutoString@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(void)
0x18005767d  mov     eax, esi
0x18005767f  mov     rcx, [rbp+var_8]
0x180057683  xor     rcx, rsp; StackCookie
0x180057686  call    __security_check_cookie
0x18005768b  lea     r11, [rsp+80h+var_s0]
0x180057693  mov     rbx, [r11+20h]
0x180057697  mov     rsi, [r11+30h]
0x18005769b  mov     rsp, r11
0x18005769e  pop     r15
0x1800576a0  pop     rdi
0x1800576a1  pop     rbp
0x1800576a2  retn
```
