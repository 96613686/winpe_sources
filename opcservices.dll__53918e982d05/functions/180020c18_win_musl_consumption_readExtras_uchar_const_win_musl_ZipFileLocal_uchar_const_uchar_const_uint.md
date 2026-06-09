# win_musl::consumption::readExtras<uchar const *>(win_musl::ZipFileLocal *,uchar const *,uchar const *,uint *)

- ea: `0x180020c18`
- end: `0x180020ecb`
- name: `??$readExtras@PEBE@consumption@win_musl@@YAXPEAVZipFileLocal@1@PEBE1PEAI@Z`
- size: `691`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18008cac0`

## callees

- `0x18001faac`
- `0x180020c18`
- `0x180021d74`
- `0x18002db70`
- `0x18006dda8`
- `0x18008e438`
- `0x18008e6dc`
- `0x18008e708`
- `0x180097a84`
- `0x1800cd6fc`
- `0x1801178f0`

## string_xrefs

- `0x180020d09`: `onecore\internal\printscan\inc\private\lib\external\win7.zipio\ZipModelReaders.inl`
- `0x180020d43`: `onecore\internal\printscan\inc\private\lib\external\win7.zipio\ZipModelReaders.inl`
- `0x180020e5e`: `onecore\internal\printscan\inc\private\lib\external\win7.zipio\ZipModelReaders.inl`
- `0x180020cf8`: `win_musl::consumption::readExtras`
- `0x180020d38`: `win_musl::consumption::readExtras`
- `0x180020e4f`: `win_musl::consumption::readExtras`

## pseudocode

```c
__int64 __fastcall win_musl::consumption::readExtras<unsigned char const *>(
        _QWORD *a1,
        char *a2,
        __int64 a3,
        _DWORD *a4)
{
  __int64 v6; // rcx
  _BYTE *v9; // rdx
  unsigned __int64 v10; // rdx
  _QWORD *v11; // r8
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rcx
  __int64 result; // rax
  __int16 Then; // bx
  unsigned __int16 v16; // ax
  __int64 v17; // r12
  unsigned __int64 v18; // rsi
  unsigned __int64 v19; // rax
  __int64 v20; // rbx
  __int64 v21; // rax
  unsigned __int64 v22; // rax
  __int64 v23; // r8
  __int64 v24; // r9
  unsigned __int64 v25; // rdx
  __int128 v26; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v27; // [rsp+50h] [rbp-B0h] BYREF
  int v28; // [rsp+52h] [rbp-AEh]
  __int16 v29; // [rsp+56h] [rbp-AAh]
  int v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+5Ch] [rbp-A4h]
  __int64 v32; // [rsp+60h] [rbp-A0h]
  _DWORD v33[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v34; // [rsp+78h] [rbp-88h]
  __int128 v35; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+90h] [rbp-70h] BYREF

  v6 = (__int64)(a1 + 7);
  v9 = *(_BYTE **)(v6 + 8);
  if ( v9 != *(_BYTE **)(v6 + 16) )
    *(_QWORD *)(v6 + 16) = v9;
  std::vector<unsigned char>::_Insert<unsigned char const *>(v6, v9, a2, a3);
  v10 = a1[8];
  v11 = a1 + 9;
  if ( v10 )
    v12 = *v11 - v10;
  else
    LODWORD(v12) = 0;
  v26 = (unsigned int)v12;
  v13 = 0;
  if ( v10 && *v11 != v10 )
  {
    *((_QWORD *)&v26 + 1) = v10;
    v13 = v10;
  }
  for ( result = (unsigned int)v26; ; *(_QWORD *)&v26 = (unsigned int)result )
  {
    *((_QWORD *)&v26 + 1) = v13;
    if ( !(_DWORD)result || !v13 )
      break;
    v35 = v26;
    Then = win_musl::detail::readThenLog<unsigned short>(
             (unsigned int)"onecore\\internal\\printscan\\inc\\private\\lib\\external\\win7.zipio\\ZipModelReaders.inl",
             65,
             (unsigned int)"win_musl::consumption::readExtras",
             (unsigned int)"type",
             (__int64)&v35,
             (__int64)&v26);
    v35 = v26;
    v16 = win_musl::detail::readThenLog<unsigned short>(
            (unsigned int)"onecore\\internal\\printscan\\inc\\private\\lib\\external\\win7.zipio\\ZipModelReaders.inl",
            69,
            (unsigned int)"win_musl::consumption::readExtras",
            (unsigned int)"size",
            (__int64)&v35,
            (__int64)&v26);
    v17 = v16;
    if ( v16 > (unsigned int)v26 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x4Cu,
        0x80511002,
        (struct win_musl::TStringEllipseBase *)L"Unexpected size of extra field. Archive may be corrupted.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v18 = *((_QWORD *)&v26 + 1);
    v29 = 0;
    v31 = DWORD1(v26);
    v28 = 0;
    v27 = Then;
    v32 = *((_QWORD *)&v26 + 1);
    v30 = v16;
    if ( Then == 1 )
    {
      v33[0] = v16;
      v33[1] = DWORD1(v26);
      v34 = *((_QWORD *)&v26 + 1);
      win_musl::consumption::readZip64Extra(
        a1,
        (const struct __MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0008 *)v33,
        a4);
    }
    else
    {
      v20 = a1[13];
      v21 = std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(a1 + 11);
      v22 = std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::capacity(a1 + 11, v21);
      if ( v25 >= v22 )
      {
        std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::_Insert_n(a1 + 11, v20, v23, &v27);
      }
      else
      {
        std::_Uninit_fill_n<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,unsigned __int64,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001,std::allocator<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>>(
          v20,
          v24,
          &v27);
        a1[13] = v20 + 24;
      }
    }
    if ( (_DWORD)v26 && v18 && (v13 = v18 + v17, v19 = v18 + (unsigned int)v26, v19 != v18 + v17) )
    {
      if ( v18 > v13 || v13 > v19 )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x65u,
          0x80070057,
          (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (extraCursor), new_begin e"
                                                  "xpression (dd::vector_begin(extraCursor) + size)");
        throw (SplException::THResultException *)pExceptionObject;
      }
      result = (unsigned int)(v19 - v13);
    }
    else
    {
      result = 0;
      v13 = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180020c18  push    rbp
0x180020c1a  push    rbx
0x180020c1b  push    rsi
0x180020c1c  push    rdi
0x180020c1d  push    r12
0x180020c1f  push    r13
0x180020c21  push    r14
0x180020c23  lea     rbp, [rsp-40h]
0x180020c28  sub     rsp, 140h
0x180020c2f  mov     rax, cs:__security_cookie
0x180020c36  xor     rax, rsp
0x180020c39  mov     [rbp+70h+var_40], rax
0x180020c3d  mov     r14, rcx
0x180020c40  mov     r13, r9
0x180020c43  add     rcx, 38h ; '8'
0x180020c47  mov     r9, r8
0x180020c4a  mov     r8, rdx
0x180020c4d  mov     rdx, [rcx+8]
0x180020c51  cmp     rdx, [rcx+10h]
0x180020c55  jz      short loc_180020C5B
0x180020c57  mov     [rcx+10h], rdx
0x180020c5b  call    ??$_Insert@PEBE@?$vector@EV?$allocator@E@std@@@std@@QEAAXV?$_Vector_iterator@EV?$allocator@E@std@@@1@PEBE1Uforward_iterator_tag@1@@Z; std::vector<uchar>::_Insert<uchar const *>(std::_Vector_iterator<uchar>,uchar const *,uchar const *,std::forward_iterator_tag)
0x180020c60  mov     rdx, [r14+40h]
0x180020c64  lea     rdi, [r14+58h]
0x180020c68  lea     r8, [r14+48h]
0x180020c6c  test    rdx, rdx
0x180020c6f  jz      short loc_180020CD5
0x180020c71  mov     rax, [r8]
0x180020c74  sub     rax, rdx
0x180020c77  mov     dword ptr [rsp+170h+var_130], eax
0x180020c7b  xor     ecx, ecx
0x180020c7d  xor     eax, eax
0x180020c7f  mov     dword ptr [rsp+170h+var_130+4], eax
0x180020c83  mov     qword ptr [rsp+170h+var_130+8], rax
0x180020c88  test    rdx, rdx
0x180020c8b  jz      short loc_180020C9A
0x180020c8d  cmp     [r8], rdx
0x180020c90  jz      short loc_180020C9A
0x180020c92  mov     qword ptr [rsp+170h+var_130+8], rdx
0x180020c97  mov     rcx, rdx
0x180020c9a  movaps  xmm0, [rsp+170h+var_130]
0x180020c9f  movdqa  [rsp+170h+var_130], xmm0
0x180020ca5  mov     eax, dword ptr [rsp+170h+var_130]
0x180020ca9  mov     qword ptr [rsp+170h+var_130+8], rcx
0x180020cae  test    eax, eax
0x180020cb0  jz      short loc_180020CB7
0x180020cb2  test    rcx, rcx
0x180020cb5  jnz     short loc_180020CD9
0x180020cb7  mov     rcx, [rbp+70h+var_40]
0x180020cbb  xor     rcx, rsp; StackCookie
0x180020cbe  call    __security_check_cookie
0x180020cc3  add     rsp, 140h
0x180020cca  pop     r14
0x180020ccc  pop     r13
0x180020cce  pop     r12
0x180020cd0  pop     rdi
0x180020cd1  pop     rsi
0x180020cd2  pop     rbx
0x180020cd3  pop     rbp
0x180020cd4  retn
0x180020cd5  xor     eax, eax
0x180020cd7  jmp     short loc_180020C77
0x180020cd9  movaps  xmm0, [rsp+170h+var_130]
0x180020cde  lea     rax, [rsp+170h+var_130]
0x180020ce3  mov     qword ptr [rsp+170h+var_148], rax
0x180020ce8  lea     r9, aType_1; "type"
0x180020cef  lea     rax, [rbp+70h+var_F0]
0x180020cf3  movdqa  [rbp+70h+var_F0], xmm0
0x180020cf8  lea     r8, aWinMuslConsump_6; "win_musl::consumption::readExtras"
0x180020cff  mov     qword ptr [rsp+170h+var_150], rax
0x180020d04  mov     edx, 41h ; 'A'
0x180020d09  lea     rcx, aOnecoreInterna_1; "onecore\\internal\\printscan\\inc\\priv"...
0x180020d10  call    ??$readThenLog@G@detail@win_musl@@YAGPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<ushort>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x180020d15  movaps  xmm0, [rsp+170h+var_130]
0x180020d1a  lea     r9, aSize_1; "size"
0x180020d21  movzx   ebx, ax
0x180020d24  movdqa  [rbp+70h+var_F0], xmm0
0x180020d29  lea     rax, [rsp+170h+var_130]
0x180020d2e  mov     edx, 45h ; 'E'
0x180020d33  mov     qword ptr [rsp+170h+var_148], rax
0x180020d38  lea     r8, aWinMuslConsump_6; "win_musl::consumption::readExtras"
0x180020d3f  lea     rax, [rbp+70h+var_F0]
0x180020d43  lea     rcx, aOnecoreInterna_1; "onecore\\internal\\printscan\\inc\\priv"...
0x180020d4a  mov     qword ptr [rsp+170h+var_150], rax
0x180020d4f  call    ??$readThenLog@G@detail@win_musl@@YAGPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<ushort>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x180020d54  movzx   r12d, ax
0x180020d58  mov     edx, r12d
0x180020d5b  cmp     r12d, dword ptr [rsp+170h+var_130]
0x180020d60  ja      loc_180020E87
0x180020d66  mov     rsi, qword ptr [rsp+170h+var_130+8]
0x180020d6b  xor     ecx, ecx
0x180020d6d  mov     r9d, 1
0x180020d73  mov     [rsp+170h+var_11A], cx
0x180020d78  mov     ecx, dword ptr [rsp+170h+var_130+4]
0x180020d7c  mov     [rsp+170h+var_114], ecx
0x180020d80  mov     [rsp+170h+var_11E], 0
0x180020d88  mov     [rsp+170h+var_120], bx
0x180020d8d  mov     [rsp+170h+var_110], rsi
0x180020d92  mov     [rsp+170h+var_118], edx
0x180020d96  cmp     r9w, bx
0x180020d9a  jnz     short loc_180020DF0
0x180020d9c  mov     [rsp+170h+var_100], edx
0x180020da0  mov     r8, r13
0x180020da3  mov     [rsp+170h+var_FC], ecx
0x180020da7  lea     rdx, [rsp+170h+var_100]
0x180020dac  mov     rcx, r14
0x180020daf  mov     [rsp+170h+var_F8], rsi
0x180020db4  call    ?readZip64Extra@consumption@win_musl@@YAXPEAVZipFileLocal@2@U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAI@Z; win_musl::consumption::readZip64Extra(win_musl::ZipFileLocal *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,uint *)
0x180020db9  cmp     dword ptr [rsp+170h+var_130], 0
0x180020dbe  jz      short loc_180020E26
0x180020dc0  test    rsi, rsi
0x180020dc3  jz      short loc_180020E26
0x180020dc5  mov     eax, dword ptr [rsp+170h+var_130]
0x180020dc9  lea     rcx, [rsi+r12]
0x180020dcd  add     rax, rsi
0x180020dd0  cmp     rax, rcx
0x180020dd3  jz      short loc_180020E26
0x180020dd5  cmp     rsi, rcx
0x180020dd8  ja      short loc_180020E43
0x180020dda  cmp     rcx, rax
0x180020ddd  ja      short loc_180020E43
0x180020ddf  sub     eax, ecx
0x180020de1  xor     edx, edx
0x180020de3  mov     dword ptr [rsp+170h+var_130], eax
0x180020de7  mov     dword ptr [rsp+170h+var_130+4], edx
0x180020deb  jmp     loc_180020CA9
0x180020df0  mov     rbx, [rdi+10h]
0x180020df4  mov     rcx, rdi
0x180020df7  call    ?size@?$vector@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@V?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@std@@@std@@QEBA_KXZ; std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(void)
0x180020dfc  mov     rcx, rdi
0x180020dff  mov     rdx, rax
0x180020e02  call    ?capacity@?$vector@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@V?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@std@@@std@@QEBA_KXZ; std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::capacity(void)
0x180020e07  cmp     rdx, rax
0x180020e0a  jnb     short loc_180020E2E
0x180020e0c  lea     r8, [rsp+170h+var_120]
0x180020e11  mov     rdx, r9
0x180020e14  mov     rcx, rbx
0x180020e17  call    ??$_Uninit_fill_n@PEAU__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@_KU1@V?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@std@@@std@@YAXPEAU__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@_KAEBU1@AEAV?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z; std::_Uninit_fill_n<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,unsigned __int64,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001,std::allocator<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>>(__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,unsigned __int64,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 const &,std::allocator<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)
0x180020e1c  add     rbx, 18h
0x180020e20  mov     [rdi+10h], rbx
0x180020e24  jmp     short loc_180020DB9
0x180020e26  xor     eax, eax
0x180020e28  xor     edx, edx
0x180020e2a  xor     ecx, ecx
0x180020e2c  jmp     short loc_180020DE3
0x180020e2e  lea     r9, [rsp+170h+var_120]
0x180020e33  mov     rdx, rbx
0x180020e36  mov     rcx, rdi
0x180020e39  call    ?_Insert_n@?$vector@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@V?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@std@@@std@@IEAAXV?$_Vector_iterator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@V?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@std@@@2@_KAEBU__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@Z; std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::_Insert_n(std::_Vector_iterator<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>,unsigned __int64,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 const &)
0x180020e3e  jmp     loc_180020DB9
0x180020e43  lea     rax, aNewBeginIsOutO_1; "new_begin is out-of-range: vector expre"...
0x180020e4a  mov     [rsp+170h+var_140], rax; struct win_musl::TStringEllipseBase *
0x180020e4f  lea     r9, aWinMuslConsump_6; "win_musl::consumption::readExtras"
0x180020e56  mov     [rsp+170h+var_148], 80070057h; unsigned int
0x180020e5e  lea     r8, aOnecoreInterna_1; "onecore\\internal\\printscan\\inc\\priv"...
0x180020e65  lea     rcx, [rbp+70h+pExceptionObject]; this
0x180020e69  mov     [rsp+170h+var_150], 65h ; 'e'; unsigned int
0x180020e71  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180020e76  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180020e7d  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x180020e81  call    _CxxThrowException_0
0x180020e87  lea     rax, aUnexpectedSize; "Unexpected size of extra field. Archive"...
0x180020e8e  mov     [rsp+170h+var_140], rax; struct win_musl::TStringEllipseBase *
0x180020e93  lea     r9, word_180139126
0x180020e9a  mov     [rsp+170h+var_148], 80511002h; unsigned int
0x180020ea2  lea     r8, aNoFilename; "(no filename)"
0x180020ea9  lea     rcx, [rbp+70h+pExceptionObject]; this
0x180020ead  mov     [rsp+170h+var_150], 4Ch ; 'L'; unsigned int
0x180020eb5  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180020eba  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180020ec1  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x180020ec5  call    _CxxThrowException_0
```
