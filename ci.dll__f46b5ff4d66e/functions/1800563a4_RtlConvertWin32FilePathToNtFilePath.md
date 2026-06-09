# RtlConvertWin32FilePathToNtFilePath

- ea: `0x1800563a4`
- end: `0x1800566bf`
- name: `RtlConvertWin32FilePathToNtFilePath`
- size: `795`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180056134`

## callees

- `0x18002bef0`
- `0x1800563a4`
- `0x1800566c8`
- `0x1800566ec`
- `0x180056718`
- `0x180087cbc`
- `0x180087e90`

## string_xrefs

- `0x180056410`: `Not-null check failed: PathIn`
- `0x1800563e8`: `onecore\base\lstring\path.cpp`
- `0x18005642f`: `onecore\base\lstring\path.cpp`
- `0x180056477`: `onecore\base\lstring\path.cpp`
- `0x1800564e3`: `onecore\base\lstring\path.cpp`
- `0x18005655d`: `onecore\base\lstring\path.cpp`
- `0x1800563ff`: `RtlConvertWin32FilePathToNtFilePath`
- `0x180056446`: `RtlConvertWin32FilePathToNtFilePath`
- `0x18005648a`: `RtlConvertWin32FilePathToNtFilePath`
- `0x1800564f6`: `RtlConvertWin32FilePathToNtFilePath`
- `0x180056570`: `RtlConvertWin32FilePathToNtFilePath`
- `0x180056455`: `Not-null check failed: PathOut`
- `0x180056495`: `PathIn->Length >= 2 * sizeof(WCHAR)`
- `0x18005657b`: `(PathIn->Length > 4 * sizeof(WCHAR)) && (PathIn->Buffer[3] == L'\\')`

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
0x1800563a4  mov     [rsp-18h+arg_0], rbx
0x1800563a9  mov     [rsp-18h+arg_10], rsi
0x1800563ae  push    rbp
0x1800563af  push    rdi
0x1800563b0  push    r15
0x1800563b2  mov     rbp, rsp
0x1800563b5  sub     rsp, 80h
0x1800563bc  mov     rax, cs:__security_cookie
0x1800563c3  xor     rax, rsp
0x1800563c6  mov     [rbp+var_8], rax
0x1800563ca  mov     [rbp+var_10], 0
0x1800563d1  mov     rbx, rdx
0x1800563d4  mov     r8, rcx
0x1800563d7  test    rdx, rdx
0x1800563da  jz      short loc_1800563E3
0x1800563dc  mov     qword ptr [rdx], 0
0x1800563e3  test    r8, r8
0x1800563e6  jnz     short loc_18005642A
0x1800563e8  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x1800563ef  mov     [rbp+var_50], 12Ch
0x1800563f7  mov     qword ptr [rbp+var_60], rax
0x1800563fb  lea     rcx, [rbp+var_60]
0x1800563ff  lea     rax, aRtlconvertwin3; "RtlConvertWin32FilePathToNtFilePath"
0x180056406  mov     r8d, 0C000000Dh
0x18005640c  mov     qword ptr [rbp+var_60+8], rax
0x180056410  lea     rax, aNotNullCheckFa_0; "Not-null check failed: PathIn"
0x180056417  mov     [rbp+var_48], rax
0x18005641b  call    RtlReportErrorOrigination
0x180056420  mov     eax, 0C000000Dh
0x180056425  jmp     loc_18005669A
0x18005642a  test    rbx, rbx
0x18005642d  jnz     short loc_18005646A
0x18005642f  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180056436  mov     [rbp+var_50], 12Dh
0x18005643e  mov     qword ptr [rbp+var_60], rax
0x180056442  lea     rdx, [rbp+var_60]
0x180056446  lea     rax, aRtlconvertwin3; "RtlConvertWin32FilePathToNtFilePath"
0x18005644d  mov     qword ptr [rbp+var_60+8], rax
0x180056451  lea     rcx, [rbp+var_10]
0x180056455  lea     rax, aNotNullCheckFa; "Not-null check failed: PathOut"
0x18005645c  mov     [rbp+var_48], rax
0x180056460  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180056465  jmp     loc_18005669A
0x18005646a  mov     rdx, [rcx]
0x18005646d  mov     ecx, 4
0x180056472  cmp     rdx, rcx
0x180056475  jnb     short loc_1800564B8
0x180056477  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18005647e  mov     [rbp+var_50], 12Eh
0x180056486  mov     qword ptr [rbp+var_60], rax
0x18005648a  lea     rax, aRtlconvertwin3; "RtlConvertWin32FilePathToNtFilePath"
0x180056491  mov     qword ptr [rbp+var_60+8], rax
0x180056495  lea     rax, aPathinLength2S; "PathIn->Length >= 2 * sizeof(WCHAR)"
0x18005649c  mov     [rbp+var_48], rax
0x1800564a0  mov     r8d, 0C000000Dh
0x1800564a6  lea     rdx, [rbp+var_60]
0x1800564aa  lea     rcx, [rbp+var_10]
0x1800564ae  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800564b3  jmp     loc_18005669A
0x1800564b8  mov     r15d, 5Ch ; '\'
0x1800564be  cmp     rdx, 8
0x1800564c2  jb      short loc_18005650B
0x1800564c4  mov     rax, [r8+10h]
0x1800564c8  cmp     [rax], r15w
0x1800564cc  jnz     short loc_18005650B
0x1800564ce  cmp     word ptr [rax+2], 3Fh ; '?'
0x1800564d3  jnz     short loc_18005650B
0x1800564d5  cmp     word ptr [rax+4], 3Fh ; '?'
0x1800564da  jnz     short loc_18005650B
0x1800564dc  cmp     [rax+6], r15w
0x1800564e1  jnz     short loc_18005650B
0x1800564e3  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x1800564ea  mov     [rbp+var_50], 138h
0x1800564f2  mov     qword ptr [rbp+var_60], rax
0x1800564f6  lea     rax, aRtlconvertwin3; "RtlConvertWin32FilePathToNtFilePath"
0x1800564fd  mov     qword ptr [rbp+var_60+8], rax
0x180056501  mov     [rbp+var_48], 0
0x180056509  jmp     short loc_1800564A0
0x18005650b  mov     rax, [r8+10h]
0x18005650f  mov     dil, 1
0x180056512  cmp     [rax], r15w
0x180056516  jnz     loc_18005659D
0x18005651c  cmp     [rax+2], r15w
0x180056521  jnz     short loc_18005659D
0x180056523  cmp     rdx, 6
0x180056527  jb      short loc_180056587
0x180056529  movzx   r9d, word ptr [rax+4]
0x18005652e  cmp     r9w, 3Fh ; '?'
0x180056533  jz      short loc_18005653C
0x180056535  cmp     r9w, 2Eh ; '.'
0x18005653a  jnz     short loc_180056587
0x18005653c  cmp     rdx, 8
0x180056540  jbe     short loc_18005655D
0x180056542  cmp     [rax+6], r15w
0x180056547  jnz     short loc_18005655D
0x180056549  movups  xmm0, cs:g_LUNICODE_STRING__bslash__q__q__bslash_
0x180056550  xor     dil, dil
0x180056553  movsd   xmm1, cs:off_1800318D0; "\\??\\"
0x18005655b  jmp     short loc_1800565AE
0x18005655d  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180056564  mov     [rbp+var_50], 14Eh
0x18005656c  mov     qword ptr [rbp+var_60], rax
0x180056570  lea     rax, aRtlconvertwin3; "RtlConvertWin32FilePathToNtFilePath"
0x180056577  mov     qword ptr [rbp+var_60+8], rax
0x18005657b  lea     rax, aPathinLength4S; "(PathIn->Length > 4 * sizeof(WCHAR)) &&"...
0x180056582  jmp     loc_18005649C
0x180056587  movups  xmm0, cs:g_LUNICODE_STRING__bslash__q__q__bslash_UNC_bslash_
0x18005658e  mov     ecx, 2
0x180056593  movsd   xmm1, cs:off_1800318E8; "\\??\\UNC\\"
0x18005659b  jmp     short loc_1800565AE
0x18005659d  movups  xmm0, cs:g_LUNICODE_STRING__bslash__q__q__bslash_
0x1800565a4  xor     ecx, ecx
0x1800565a6  movsd   xmm1, cs:off_1800318D0; "\\??\\"
0x1800565ae  add     rcx, rcx
0x1800565b1  movsd   [rbp+var_30], xmm1
0x1800565b6  add     rax, rcx
0x1800565b9  sub     rdx, rcx
0x1800565bc  mov     [rbp+var_18], rax
0x1800565c0  mov     rax, [r8+8]
0x1800565c4  sub     rax, rcx
0x1800565c7  mov     [rbp+var_28], rdx
0x1800565cb  mov     [rbp+var_20], rax
0x1800565cf  lea     rcx, [rbp+var_60]
0x1800565d3  movups  [rbp+var_40], xmm0
0x1800565d7  xor     eax, eax
0x1800565d9  xorps   xmm0, xmm0
0x1800565dc  mov     [rbp+var_50], rax
0x1800565e0  movups  [rbp+var_60], xmm0
0x1800565e4  call    ?Close@?$AutoString@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(void)
0x1800565e9  movups  xmm0, xmmword ptr [rbx]
0x1800565ec  lea     r9, [rbp+var_60]
0x1800565f0  xor     eax, eax
0x1800565f2  movsd   xmm1, qword ptr [rbx+10h]
0x1800565f7  lea     r8, [rbp+var_40]
0x1800565fb  movups  [rbp+var_60], xmm0
0x1800565ff  xorps   xmm0, xmm0
0x180056602  movsd   [rbp+var_50], xmm1
0x180056607  movups  xmmword ptr [rbx], xmm0
0x18005660a  mov     [rbx+10h], rax
0x18005660e  call    RtlConcatenateLUnicodeStrings
0x180056613  mov     esi, eax
0x180056615  test    eax, eax
0x180056617  js      short loc_18005668F
0x180056619  test    dil, dil
0x18005661c  jz      short loc_18005666F
0x18005661e  mov     rdx, [rbp+var_50]
0x180056622  mov     r10, qword ptr [rbp+var_60]
0x180056626  mov     rcx, rdx
0x180056629  add     r10, rdx
0x18005662c  xor     r9d, r9d
0x18005662f  jmp     short loc_18005666A
0x180056631  movzx   r8d, word ptr [rdx]
0x180056635  mov     rax, rcx
0x180056638  add     rdx, 2
0x18005663c  cmp     r8w, 20h ; ' '
0x180056641  cmovz   rax, r9
0x180056645  mov     r9, rax
0x180056648  cmp     r8w, 2Fh ; '/'
0x18005664d  jnz     short loc_180056655
0x18005664f  movzx   r8d, r15w
0x180056653  jmp     short loc_18005665B
0x180056655  cmp     r8w, r15w
0x180056659  jnz     short loc_180056662
0x18005665b  test    rax, rax
0x18005665e  cmovnz  rcx, rax
0x180056662  mov     [rcx], r8w
0x180056666  add     rcx, 2
0x18005666a  cmp     rdx, r10
0x18005666d  jnz     short loc_180056631
0x18005666f  movups  xmm1, [rbp+var_60]
0x180056673  xor     eax, eax
0x180056675  movsd   xmm2, [rbp+var_50]
0x18005667a  xorps   xmm0, xmm0
0x18005667d  movups  xmmword ptr [rbx], xmm1
0x180056680  xor     esi, esi
0x180056682  mov     [rbp+var_50], rax
0x180056686  movsd   qword ptr [rbx+10h], xmm2
0x18005668b  movups  [rbp+var_60], xmm0
0x18005668f  lea     rcx, [rbp+var_60]
0x180056693  call    ?Close@?$AutoString@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(void)
0x180056698  mov     eax, esi
0x18005669a  mov     rcx, [rbp+var_8]
0x18005669e  xor     rcx, rsp; StackCookie
0x1800566a1  call    __security_check_cookie
0x1800566a6  lea     r11, [rsp+80h+var_s0]
0x1800566ae  mov     rbx, [r11+20h]
0x1800566b2  mov     rsi, [r11+30h]
0x1800566b6  mov     rsp, r11
0x1800566b9  pop     r15
0x1800566bb  pop     rdi
0x1800566bc  pop     rbp
0x1800566bd  retn
```
