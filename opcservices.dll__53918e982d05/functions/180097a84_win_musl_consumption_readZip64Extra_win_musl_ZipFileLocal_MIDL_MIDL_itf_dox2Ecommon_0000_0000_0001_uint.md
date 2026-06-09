# win_musl::consumption::readZip64Extra(win_musl::ZipFileLocal *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,uint *)

- ea: `0x180097a84`
- end: `0x180097e6d`
- name: `?readZip64Extra@consumption@win_musl@@YAXPEAVZipFileLocal@2@U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAI@Z`
- size: `1001`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001d7d8`
- `0x180020c18`

## callees

- `0x18002d9bc`
- `0x18002db70`
- `0x18006bc18`
- `0x18006d010`
- `0x18006df14`
- `0x180097a84`
- `0x1800cd6fc`
- `0x180110bcc`
- `0x1801178f0`

## string_xrefs

- `0x180097b5e`: `win_musl::consumption::readZip64Extra`
- `0x180097c50`: `win_musl::consumption::readZip64Extra`
- `0x180097d42`: `win_musl::consumption::readZip64Extra`
- `0x180097dd7`: `win_musl::consumption::readZip64Extra`
- `0x180097b72`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x180097c67`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x180097d59`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x180097dee`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x180097c49`: `compressedSize64`
- `0x180097b57`: `uncompressedSize64`
- `0x180097bf6`: `Local extra field format error: Both original and compressed file sizes must be included.`
- `0x180097ce8`: `Local extra field format error: Both original and compressed file sizes must be included.`

## pseudocode

```c
__int64 __fastcall win_musl::consumption::readZip64Extra(
        _QWORD *a1,
        const struct __MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0008 *a2,
        _DWORD *a3)
{
  _QWORD *v3; // rsi
  const struct __MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0008 *v7; // rdx
  __int128 v8; // xmm6
  __int64 v9; // rax
  __int64 result; // rax
  _BYTE v11[8]; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v12; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+68h] [rbp-A0h] BYREF

  v3 = a1 + 19;
  if ( win_musl::get_value((win_musl *)(a1 + 19), a2) == 0xFFFFFFFF )
  {
    if ( *(_DWORD *)a2 < 8u )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xEEu,
        0x80511002,
        (struct win_musl::TStringEllipseBase *)L"Unexpected size of extra field. Archive may be corrupted.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v8 = *(_OWORD *)a2;
    v12 = *(_OWORD *)a2;
    v11[0] = 0;
    v9 = win_musl::detail::vector_read<unsigned __int64>(&v12, a2, v11);
    if ( v11[0] )
    {
      v12 = v8;
      win_musl::detail::ThrowReadError(
        "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipmodelreaders.cpp",
        242,
        "win_musl::consumption::readZip64Extra",
        "uncompressedSize64",
        8,
        &v12);
    }
    *v3 = 3;
    v3[1] = v9;
  }
  else if ( !a3 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0xFCu,
      0x80511002,
      (struct win_musl::TStringEllipseBase *)L"Local extra field format error: Both original and compressed file sizes must be included.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  result = win_musl::get_value((win_musl *)(a1 + 21), v7);
  if ( result != 0xFFFFFFFFLL )
  {
    if ( !a3 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x119u,
        0x80511002,
        (struct win_musl::TStringEllipseBase *)L"Local extra field format error: Both original and compressed file sizes m"
                                                "ust be included.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    goto LABEL_13;
  }
  if ( *(_DWORD *)a2 < 8u )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x10Bu,
      0x80511002,
      (struct win_musl::TStringEllipseBase *)L"Unexpected size of extra field. Archive may be corrupted.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v12 = *(_OWORD *)a2;
  result = win_musl::detail::readThenLog<unsigned __int64>(
             (unsigned int)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipmodelreaders.cpp",
             271,
             (unsigned int)"win_musl::consumption::readZip64Extra",
             (unsigned int)"compressedSize64",
             (__int64)&v12,
             (__int64)a2);
  a1[21] = 3;
  a1[22] = result;
  if ( a3 )
  {
LABEL_13:
    if ( a1[23] == 0xFFFFFFFFLL )
    {
      if ( *(_DWORD *)a2 < 8u )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x126u,
          0x80511002,
          (struct win_musl::TStringEllipseBase *)L"Unexpected size of extra field. Archive may be corrupted.");
        throw (SplException::THResultException *)pExceptionObject;
      }
      v12 = *(_OWORD *)a2;
      result = win_musl::detail::readThenLog<unsigned __int64>(
                 (unsigned int)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipmodelreaders.cpp",
                 297,
                 (unsigned int)"win_musl::consumption::readZip64Extra",
                 (unsigned int)"entry->header.header_offset",
                 (__int64)&v12,
                 (__int64)a2);
      a1[23] = result;
    }
    if ( *a3 == 0xFFFF )
    {
      if ( *(_DWORD *)a2 < 4u )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x134u,
          0x80511002,
          (struct win_musl::TStringEllipseBase *)L"Unexpected size of extra field. Archive may be corrupted.");
        throw (SplException::THResultException *)pExceptionObject;
      }
      v12 = *(_OWORD *)a2;
      result = win_musl::detail::readThenLog<unsigned int>(
                 (unsigned int)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipmodelreaders.cpp",
                 312,
                 (unsigned int)"win_musl::consumption::readZip64Extra",
                 (unsigned int)"diskStart",
                 (__int64)&v12,
                 (__int64)a2);
      *a3 = result;
    }
  }
  if ( *(_DWORD *)a2 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x142u,
      0x80511002,
      (struct win_musl::TStringEllipseBase *)L"Unexpected size of extra field. Archive may be corrupted.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180097a84  mov     rax, rsp
0x180097a87  push    rbp
0x180097a88  push    rbx
0x180097a89  push    rsi
0x180097a8a  push    rdi
0x180097a8b  push    r13
0x180097a8d  push    r14
0x180097a8f  push    r15
0x180097a91  lea     rbp, [rax-58h]
0x180097a95  sub     rsp, 120h
0x180097a9c  movaps  xmmword ptr [rax-48h], xmm6
0x180097aa0  mov     rax, cs:__security_cookie
0x180097aa7  xor     rax, rsp
0x180097aaa  mov     [rbp+50h+var_50], rax
0x180097aae  lea     rsi, [rcx+98h]
0x180097ab5  mov     r14, rcx
0x180097ab8  mov     rcx, rsi; this
0x180097abb  mov     rdi, r8
0x180097abe  mov     rbx, rdx
0x180097ac1  call    ?get_value@win_musl@@YA_KAEBU__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0008@@@Z; win_musl::get_value(__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0008 const &)
0x180097ac6  mov     r13d, 0FFFFFFFFh
0x180097acc  cmp     rax, r13
0x180097acf  jnz     loc_180097BF1
0x180097ad5  cmp     dword ptr [rbx], 8
0x180097ad8  jnb     short loc_180097B20
0x180097ada  lea     rax, aUnexpectedSize; "Unexpected size of extra field. Archive"...
0x180097ae1  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x180097ae6  lea     r9, word_180139126
0x180097aed  mov     [rsp+150h+var_128], 80511002h; unsigned int
0x180097af5  lea     r8, aNoFilename; "(no filename)"
0x180097afc  lea     rcx, [rsp+150h+pExceptionObject]; this
0x180097b01  mov     [rsp+150h+var_130], 0EEh; unsigned int
0x180097b09  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180097b0e  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180097b15  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x180097b1a  call    _CxxThrowException_0
0x180097b20  movaps  xmm6, xmmword ptr [rbx]
0x180097b23  lea     r8, [rsp+150h+var_110]
0x180097b28  mov     rdx, rbx
0x180097b2b  movdqa  [rsp+150h+var_108+8], xmm6
0x180097b31  lea     rcx, [rsp+150h+var_108+8]
0x180097b36  mov     [rsp+150h+var_110], 0
0x180097b3b  call    ??$vector_read@_K@detail@win_musl@@YA_KU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@PEA_NW4Enum@ByteOrderOption@01@@Z; win_musl::detail::vector_read<unsigned __int64>(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,bool *,win_musl::detail::ByteOrderOption::Enum)
0x180097b40  cmp     [rsp+150h+var_110], 0
0x180097b45  jz      short loc_180097B7F
0x180097b47  lea     rax, [rsp+150h+var_108+8]
0x180097b4c  movdqa  [rsp+150h+var_108+8], xmm6
0x180097b52  mov     qword ptr [rsp+150h+var_128], rax
0x180097b57  lea     r9, aUncompressedsi; "uncompressedSize64"
0x180097b5e  lea     r8, aWinMuslConsump_4; "win_musl::consumption::readZip64Extra"
0x180097b65  mov     [rsp+150h+var_130], 8
0x180097b6d  mov     edx, 0F2h
0x180097b72  lea     rcx, aOnecorePrintsc_2; "onecore\\printscan\\dox\\opc\\zipio_lca"...
0x180097b79  call    ?ThrowReadError@detail@win_musl@@YAXPEBDK00IU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@@Z; win_musl::detail::ThrowReadError(char const *,ulong,char const *,char const *,uint,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001)
0x180097b7f  mov     qword ptr [rsi], 3
0x180097b86  mov     [rsi+8], rax
0x180097b8a  lea     rsi, [r14+0A8h]
0x180097b91  mov     rcx, rsi; this
0x180097b94  call    ?get_value@win_musl@@YA_KAEBU__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0008@@@Z; win_musl::get_value(__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0008 const &)
0x180097b99  cmp     rax, r13
0x180097b9c  jnz     loc_180097CE3
0x180097ba2  cmp     dword ptr [rbx], 8
0x180097ba5  jnb     loc_180097C3C
0x180097bab  lea     rax, aUnexpectedSize; "Unexpected size of extra field. Archive"...
0x180097bb2  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x180097bb7  lea     r9, word_180139126
0x180097bbe  mov     [rsp+150h+var_128], 80511002h; unsigned int
0x180097bc6  lea     r8, aNoFilename; "(no filename)"
0x180097bcd  lea     rcx, [rsp+150h+pExceptionObject]; this
0x180097bd2  mov     [rsp+150h+var_130], 10Bh; unsigned int
0x180097bda  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180097bdf  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180097be6  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x180097beb  call    _CxxThrowException_0
0x180097bf1  test    rdi, rdi
0x180097bf4  jnz     short loc_180097B8A
0x180097bf6  lea     rax, aLocalExtraFiel; "Local extra field format error: Both or"...
0x180097bfd  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x180097c02  lea     r9, word_180139126
0x180097c09  mov     [rsp+150h+var_128], 80511002h; unsigned int
0x180097c11  lea     r8, aNoFilename; "(no filename)"
0x180097c18  lea     rcx, [rsp+150h+pExceptionObject]; this
0x180097c1d  mov     [rsp+150h+var_130], 0FCh; unsigned int
0x180097c25  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180097c2a  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180097c31  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x180097c36  call    _CxxThrowException_0
0x180097c3c  movaps  xmm0, xmmword ptr [rbx]
0x180097c3f  lea     rax, [rsp+150h+var_108+8]
0x180097c44  mov     qword ptr [rsp+150h+var_128], rbx
0x180097c49  lea     r9, aCompressedsize; "compressedSize64"
0x180097c50  lea     r8, aWinMuslConsump_4; "win_musl::consumption::readZip64Extra"
0x180097c57  movdqa  [rsp+150h+var_108+8], xmm0
0x180097c5d  mov     edx, 10Fh
0x180097c62  mov     qword ptr [rsp+150h+var_130], rax
0x180097c67  lea     rcx, aOnecorePrintsc_2; "onecore\\printscan\\dox\\opc\\zipio_lca"...
0x180097c6e  call    ??$readThenLog@_K@detail@win_musl@@YA_KPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<unsigned __int64>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x180097c73  mov     qword ptr [rsi], 3
0x180097c7a  mov     [rsi+8], rax
0x180097c7e  test    rdi, rdi
0x180097c81  jz      loc_180097DFC
0x180097c87  cmp     [r14+0B8h], r13
0x180097c8e  jnz     loc_180097D6C
0x180097c94  cmp     dword ptr [rbx], 8
0x180097c97  jnb     loc_180097D2E
0x180097c9d  lea     rax, aUnexpectedSize; "Unexpected size of extra field. Archive"...
0x180097ca4  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x180097ca9  lea     r9, word_180139126
0x180097cb0  mov     [rsp+150h+var_128], 80511002h; unsigned int
0x180097cb8  lea     r8, aNoFilename; "(no filename)"
0x180097cbf  lea     rcx, [rsp+150h+pExceptionObject]; this
0x180097cc4  mov     [rsp+150h+var_130], 126h; unsigned int
0x180097ccc  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180097cd1  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180097cd8  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x180097cdd  call    _CxxThrowException_0
0x180097ce3  test    rdi, rdi
0x180097ce6  jnz     short loc_180097C87
0x180097ce8  lea     rax, aLocalExtraFiel; "Local extra field format error: Both or"...
0x180097cef  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x180097cf4  lea     r9, word_180139126
0x180097cfb  mov     [rsp+150h+var_128], 80511002h; unsigned int
0x180097d03  lea     r8, aNoFilename; "(no filename)"
0x180097d0a  lea     rcx, [rsp+150h+pExceptionObject]; this
0x180097d0f  mov     [rsp+150h+var_130], 119h; unsigned int
0x180097d17  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180097d1c  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180097d23  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x180097d28  call    _CxxThrowException_0
0x180097d2e  movaps  xmm0, xmmword ptr [rbx]
0x180097d31  lea     rax, [rsp+150h+var_108+8]
0x180097d36  mov     qword ptr [rsp+150h+var_128], rbx
0x180097d3b  lea     r9, aEntryHeaderHea_0; "entry->header.header_offset"
0x180097d42  lea     r8, aWinMuslConsump_4; "win_musl::consumption::readZip64Extra"
0x180097d49  movdqa  [rsp+150h+var_108+8], xmm0
0x180097d4f  mov     edx, 129h
0x180097d54  mov     qword ptr [rsp+150h+var_130], rax
0x180097d59  lea     rcx, aOnecorePrintsc_2; "onecore\\printscan\\dox\\opc\\zipio_lca"...
0x180097d60  call    ??$readThenLog@_K@detail@win_musl@@YA_KPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<unsigned __int64>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x180097d65  mov     [r14+0B8h], rax
0x180097d6c  cmp     dword ptr [rdi], 0FFFFh
0x180097d72  jnz     loc_180097DFC
0x180097d78  cmp     dword ptr [rbx], 4
0x180097d7b  jnb     short loc_180097DC3
0x180097d7d  lea     rax, aUnexpectedSize; "Unexpected size of extra field. Archive"...
0x180097d84  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x180097d89  lea     r9, word_180139126
0x180097d90  mov     [rsp+150h+var_128], 80511002h; unsigned int
0x180097d98  lea     r8, aNoFilename; "(no filename)"
0x180097d9f  lea     rcx, [rsp+150h+pExceptionObject]; this
0x180097da4  mov     [rsp+150h+var_130], 134h; unsigned int
0x180097dac  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180097db1  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180097db8  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x180097dbd  call    _CxxThrowException_0
0x180097dc3  movaps  xmm0, xmmword ptr [rbx]
0x180097dc6  lea     rax, [rsp+150h+var_108+8]
0x180097dcb  mov     qword ptr [rsp+150h+var_128], rbx
0x180097dd0  lea     r9, aDiskstart; "diskStart"
0x180097dd7  lea     r8, aWinMuslConsump_4; "win_musl::consumption::readZip64Extra"
0x180097dde  movdqa  [rsp+150h+var_108+8], xmm0
0x180097de4  mov     edx, 138h
0x180097de9  mov     qword ptr [rsp+150h+var_130], rax
0x180097dee  lea     rcx, aOnecorePrintsc_2; "onecore\\printscan\\dox\\opc\\zipio_lca"...
0x180097df5  call    ??$readThenLog@I@detail@win_musl@@YAIPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<uint>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x180097dfa  mov     [rdi], eax
0x180097dfc  cmp     dword ptr [rbx], 0
0x180097dff  jz      short loc_180097E47
0x180097e01  lea     rax, aUnexpectedSize; "Unexpected size of extra field. Archive"...
0x180097e08  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x180097e0d  lea     r9, word_180139126
0x180097e14  mov     [rsp+150h+var_128], 80511002h; unsigned int
0x180097e1c  lea     r8, aNoFilename; "(no filename)"
0x180097e23  lea     rcx, [rsp+150h+pExceptionObject]; this
0x180097e28  mov     [rsp+150h+var_130], 142h; unsigned int
0x180097e30  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180097e35  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180097e3c  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x180097e41  call    _CxxThrowException_0
0x180097e47  mov     rcx, [rbp+50h+var_50]
0x180097e4b  xor     rcx, rsp; StackCookie
0x180097e4e  call    __security_check_cookie
0x180097e53  movaps  xmm6, [rsp+150h+var_48+8]
0x180097e5b  add     rsp, 120h
0x180097e62  pop     r15
0x180097e64  pop     r14
0x180097e66  pop     r13
0x180097e68  pop     rdi
0x180097e69  pop     rsi
0x180097e6a  pop     rbx
0x180097e6b  pop     rbp
0x180097e6c  retn
```
