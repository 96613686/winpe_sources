# win_musl::consumption::ZipEndOfCentralDirectoryZip64Consumer::Close(win_musl::ByteReceiverUnique<win_musl::consumption::ZipEndOfCentralDirectoryZip64Consumer,0,IUnknown> &)

- ea: `0x18006be28`
- end: `0x18006c48f`
- name: `?Close@ZipEndOfCentralDirectoryZip64Consumer@consumption@win_musl@@QEAAXAEAV?$ByteReceiverUnique@VZipEndOfCentralDirectoryZip64Consumer@consumption@win_musl@@$0A@UIUnknown@@@3@@Z`
- size: `1639`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18006a5bc`

## callees

- `0x1800124f4`
- `0x18002db70`
- `0x18006be28`
- `0x18006d010`
- `0x18006dda8`
- `0x18006df14`
- `0x1800cd6fc`
- `0x1800d6354`
- `0x180110bcc`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18006c1d1`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18006c1d1`

## string_xrefs

- `0x18006c3b8`: `sizeCentralDirectory`
- `0x18006bfa7`: `diskNumberDirectoryStart`
- `0x18006c314`: `directoryEntriesCountThisDisk`
- `0x18006c3e8`: `offsetCentralDirectory`
- `0x18006bef6`: `win_musl::consumption::ZipEndOfCentralDirectoryZip64Consumer::Close`
- `0x18006c25b`: `win_musl::consumption::ZipEndOfCentralDirectoryZip64Consumer::Close`
- `0x18006bf05`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipendofcentraldirectoryzip64consumer.cpp`
- `0x18006c267`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipendofcentraldirectoryzip64consumer.cpp`
- `0x18006c400`: `invalid end_of_central_directory source value!`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_musl::consumption::ZipEndOfCentralDirectoryZip64Consumer::Close(_QWORD *a1)
{
  __int64 v2; // rcx
  __int128 v3; // xmm6
  __int64 v4; // rax
  __int128 v5; // xmm6
  __int64 v6; // r15
  __int128 v7; // xmm6
  __int64 v8; // rax
  __int64 v9; // r14
  __int128 v10; // xmm6
  __int64 v11; // r15
  __int128 v12; // xmm6
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 v15; // rdx
  int v16; // ecx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 result; // rax
  __int64 v21; // rcx
  __int64 v22; // rcx
  _BYTE v23[8]; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v24; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v25; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+78h] [rbp-90h]
  _QWORD pExceptionObject[3]; // [rsp+88h] [rbp-80h] BYREF
  _DWORD v28[2]; // [rsp+A0h] [rbp-68h] BYREF
  const char *v29; // [rsp+A8h] [rbp-60h]
  _BYTE v30[56]; // [rsp+B0h] [rbp-58h] BYREF
  GUID v31; // [rsp+E8h] [rbp-20h]
  int v32; // [rsp+110h] [rbp+8h]

  v26 = -2;
  v2 = a1[7];
  if ( !v2 || a1[8] - v2 != 52 )
  {
    win_musl::DebugLogHelper("(no filename)", &word_180139126, 143, 1024, -2142171135, L"Wrong number of bytes sent");
    *(_QWORD *)&v25 = "Unexpected HRESULT returned by API";
    exception::exception((exception *)pExceptionObject, (const char *const *)&v25);
    memset_0(v30, 0, 0x68u);
    v29 = "(no filename)";
    v28[1] = 143;
    v32 = -1;
    pExceptionObject[0] = &SplException::THResultException::`vftable';
    v28[0] = -2142171135;
    v31 = GUID_NULL;
    if ( SplException::Functions )
      v32 = SplException::Functions(v28);
    throw (SplException::THResultException *)pExceptionObject;
  }
  *(_QWORD *)&v25 = 52;
  *((_QWORD *)&v25 + 1) = v2;
  v3 = v25;
  v23[0] = 0;
  v24 = v25;
  v4 = win_musl::detail::vector_read<unsigned __int64>(&v24, &v25, v23);
  if ( v23[0] )
  {
    v24 = v3;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipendofcentraldirectoryzip64consumer.cpp",
      154,
      "win_musl::consumption::ZipEndOfCentralDirectoryZip64Consumer::Close",
      "sizeOfThis",
      8,
      &v24);
  }
  a1[10] = v4 - 44;
  v24 = v25;
  win_musl::detail::readThenLog<unsigned short>(
    (unsigned int)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipendofcentraldirector"
                  "yzip64consumer.cpp",
    160,
    (unsigned int)"win_musl::consumption::ZipEndOfCentralDirectoryZip64Consumer::Close",
    (unsigned int)"versionMadeBy",
    (__int64)&v24,
    (__int64)&v25);
  v24 = v25;
  win_musl::detail::readThenLog<unsigned short>(
    (unsigned int)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipendofcentraldirector"
                  "yzip64consumer.cpp",
    164,
    (unsigned int)"win_musl::consumption::ZipEndOfCentralDirectoryZip64Consumer::Close",
    (unsigned int)"versionMinimumExtract",
    (__int64)&v24,
    (__int64)&v25);
  v24 = v25;
  if ( (unsigned int)win_musl::detail::readThenLog<unsigned int>(
                       (unsigned int)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipe"
                                     "ndofcentraldirectoryzip64consumer.cpp",
                       168,
                       (unsigned int)"win_musl::consumption::ZipEndOfCentralDirectoryZip64Consumer::Close",
                       (unsigned int)"diskNumberThis",
                       (__int64)&v24,
                       (__int64)&v25) )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0xACu,
      0x80511008,
      (struct win_musl::TStringEllipseBase *)L"Archive feature not supported: only support single disk archives.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v24 = v25;
  if ( (unsigned int)win_musl::detail::readThenLog<unsigned int>(
                       (unsigned int)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipe"
                                     "ndofcentraldirectoryzip64consumer.cpp",
                       178,
                       (unsigned int)"win_musl::consumption::ZipEndOfCentralDirectoryZip64Consumer::Close",
                       (unsigned int)"diskNumberDirectoryStart",
                       (__int64)&v24,
                       (__int64)&v25) )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0xB6u,
      0x80511008,
      (struct win_musl::TStringEllipseBase *)L"Archive feature not supported: only support single disk archives.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v5 = v25;
  v23[0] = 0;
  v24 = v25;
  v6 = win_musl::detail::vector_read<unsigned __int64>(&v24, &v25, v23);
  if ( v23[0] )
  {
    v24 = v5;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipendofcentraldirectoryzip64consumer.cpp",
      188,
      "win_musl::consumption::ZipEndOfCentralDirectoryZip64Consumer::Close",
      "directoryEntriesCountThisDisk",
      8,
      &v24);
  }
  v7 = v25;
  v23[0] = 0;
  v24 = v25;
  v8 = win_musl::detail::vector_read<unsigned __int64>(&v24, &v25, v23);
  v9 = v8;
  if ( v23[0] )
  {
    v24 = v7;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipendofcentraldirectoryzip64consumer.cpp",
      199,
      "win_musl::consumption::ZipEndOfCentralDirectoryZip64Consumer::Close",
      "countEntries",
      8,
      &v24);
  }
  if ( v6 != v8 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0xD0u,
      0x80511008,
      (struct win_musl::TStringEllipseBase *)L"Archive feature not supported: only support single disk archives.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v10 = v25;
  v23[0] = 0;
  v24 = v25;
  v11 = win_musl::detail::vector_read<unsigned __int64>(&v24, &v25, v23);
  if ( v23[0] )
  {
    v24 = v10;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipendofcentraldirectoryzip64consumer.cpp",
      219,
      "win_musl::consumption::ZipEndOfCentralDirectoryZip64Consumer::Close",
      "sizeCentralDirectory",
      8,
      &v24);
  }
  v12 = v25;
  v23[0] = 0;
  v24 = v25;
  v13 = win_musl::detail::vector_read<unsigned __int64>(&v24, &v25, v23);
  v14 = v13;
  if ( v23[0] )
  {
    v24 = v12;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipendofcentraldirectoryzip64consumer.cpp",
      231,
      "win_musl::consumption::ZipEndOfCentralDirectoryZip64Consumer::Close",
      "offsetCentralDirectory",
      8,
      &v24);
  }
  v15 = a1[3];
  v16 = *(_DWORD *)(v15 + 128);
  if ( !v16 )
  {
    *(_DWORD *)(v15 + 128) = 2;
    *(_QWORD *)(a1[3] + 152LL) = v13;
    *(_QWORD *)(a1[3] + 144LL) = v11;
    *(_QWORD *)(a1[3] + 136LL) = v9;
    *(_DWORD *)(a1[3] + 168LL) = 0;
    result = a1[3];
LABEL_22:
    *(_DWORD *)(result + 172) = 0;
    goto LABEL_23;
  }
  if ( v16 != 1 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x120u,
      0x8000FFFF,
      (struct win_musl::TStringEllipseBase *)L"invalid end_of_central_directory source value!");
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( *(_QWORD *)(v15 + 152) == 0xFFFFFFFFLL )
    *(_QWORD *)(v15 + 152) = v13;
  v17 = a1[3];
  if ( *(_QWORD *)(v17 + 144) == 0xFFFFFFFFLL )
    *(_QWORD *)(v17 + 144) = v11;
  v18 = a1[3];
  if ( *(_QWORD *)(v18 + 136) == 0xFFFF )
    *(_QWORD *)(v18 + 136) = v9;
  v19 = a1[3];
  if ( *(_DWORD *)(v19 + 168) == 0xFFFF )
    *(_DWORD *)(v19 + 168) = 0;
  result = a1[3];
  if ( *(_DWORD *)(result + 172) == 0xFFFF )
    goto LABEL_22;
LABEL_23:
  v21 = a1[4];
  if ( v21 && dword_1801C4FE0 != -1 )
  {
    result = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v21 + 40LL))(v21, a1[10] + a1[5], v14);
    v22 = a1[4];
    a1[4] = 0;
    if ( v22 )
      return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  return result;
}

```

## disassembly

```asm
0x18006be28  mov     rax, rsp
0x18006be2b  push    rbp
0x18006be2c  push    rdi
0x18006be2d  push    r12
0x18006be2f  push    r14
0x18006be31  push    r15
0x18006be33  lea     rbp, [rax-68h]
0x18006be37  sub     rsp, 140h
0x18006be3e  mov     [rsp+160h+var_F0], 0FFFFFFFFFFFFFFFEh
0x18006be47  mov     [rax+10h], rbx
0x18006be4b  mov     [rax+18h], rsi
0x18006be4f  movaps  xmmword ptr [rax-38h], xmm6
0x18006be53  mov     rax, cs:__security_cookie
0x18006be5a  xor     rax, rsp
0x18006be5d  mov     [rbp+60h+var_40], rax
0x18006be61  mov     rbx, rcx
0x18006be64  xor     r12d, r12d
0x18006be67  mov     rcx, [rcx+38h]
0x18006be6b  test    rcx, rcx
0x18006be6e  jz      loc_18006C184
0x18006be74  mov     rax, [rbx+40h]
0x18006be78  sub     rax, rcx
0x18006be7b  cmp     rax, 34h ; '4'
0x18006be7f  jnz     loc_18006C184
0x18006be85  mov     dword ptr [rsp+160h+var_108+8], eax
0x18006be89  xor     eax, eax
0x18006be8b  mov     dword ptr [rsp+160h+var_108+0Ch], eax
0x18006be8f  mov     [rsp+160h+var_F8], rcx
0x18006be94  movaps  xmm6, [rsp+160h+var_108+8]
0x18006be99  movaps  [rsp+160h+var_108+8], xmm6
0x18006be9e  mov     [rsp+160h+var_120], r12b
0x18006bea3  movdqa  [rsp+160h+var_118+8], xmm6
0x18006bea9  lea     r8, [rsp+160h+var_120]
0x18006beae  lea     rdx, [rsp+160h+var_108+8]
0x18006beb3  lea     rcx, [rsp+160h+var_118+8]
0x18006beb8  call    ??$vector_read@_K@detail@win_musl@@YA_KU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@PEA_NW4Enum@ByteOrderOption@01@@Z; win_musl::detail::vector_read<unsigned __int64>(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,bool *,win_musl::detail::ByteOrderOption::Enum)
0x18006bebd  cmp     [rsp+160h+var_120], r12b
0x18006bec2  jnz     loc_18006C23C
0x18006bec8  add     rax, 0FFFFFFFFFFFFFFD4h
0x18006becc  mov     [rbx+50h], rax
0x18006bed0  movaps  xmm0, [rsp+160h+var_108+8]
0x18006bed5  movdqa  [rsp+160h+var_118+8], xmm0
0x18006bedb  lea     rax, [rsp+160h+var_108+8]
0x18006bee0  mov     qword ptr [rsp+160h+var_138], rax
0x18006bee5  lea     rax, [rsp+160h+var_118+8]
0x18006beea  mov     qword ptr [rsp+160h+var_140], rax
0x18006beef  lea     r9, aVersionmadeby; "versionMadeBy"
0x18006bef6  lea     rdi, aWinMuslConsump; "win_musl::consumption::ZipEndOfCentralD"...
0x18006befd  mov     r8, rdi
0x18006bf00  mov     edx, 0A0h
0x18006bf05  lea     rsi, aOnecorePrintsc_8; "onecore\\printscan\\dox\\opc\\zipio_lca"...
0x18006bf0c  mov     rcx, rsi
0x18006bf0f  call    ??$readThenLog@G@detail@win_musl@@YAGPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<ushort>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x18006bf14  movaps  xmm0, [rsp+160h+var_108+8]
0x18006bf19  movdqa  [rsp+160h+var_118+8], xmm0
0x18006bf1f  lea     rax, [rsp+160h+var_108+8]
0x18006bf24  mov     qword ptr [rsp+160h+var_138], rax
0x18006bf29  lea     rax, [rsp+160h+var_118+8]
0x18006bf2e  mov     qword ptr [rsp+160h+var_140], rax
0x18006bf33  lea     r9, aVersionminimum; "versionMinimumExtract"
0x18006bf3a  mov     r8, rdi
0x18006bf3d  mov     edx, 0A4h
0x18006bf42  mov     rcx, rsi
0x18006bf45  call    ??$readThenLog@G@detail@win_musl@@YAGPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<ushort>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x18006bf4a  movaps  xmm0, [rsp+160h+var_108+8]
0x18006bf4f  movdqa  [rsp+160h+var_118+8], xmm0
0x18006bf55  lea     rax, [rsp+160h+var_108+8]
0x18006bf5a  mov     qword ptr [rsp+160h+var_138], rax
0x18006bf5f  lea     rax, [rsp+160h+var_118+8]
0x18006bf64  mov     qword ptr [rsp+160h+var_140], rax
0x18006bf69  lea     r9, aDisknumberthis; "diskNumberThis"
0x18006bf70  mov     r8, rdi
0x18006bf73  mov     edx, 0A8h
0x18006bf78  mov     rcx, rsi
0x18006bf7b  call    ??$readThenLog@I@detail@win_musl@@YAIPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<uint>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x18006bf80  test    eax, eax
0x18006bf82  jnz     loc_18006C274
0x18006bf88  movaps  xmm0, [rsp+160h+var_108+8]
0x18006bf8d  movdqa  [rsp+160h+var_118+8], xmm0
0x18006bf93  lea     rax, [rsp+160h+var_108+8]
0x18006bf98  mov     qword ptr [rsp+160h+var_138], rax
0x18006bf9d  lea     rax, [rsp+160h+var_118+8]
0x18006bfa2  mov     qword ptr [rsp+160h+var_140], rax
0x18006bfa7  lea     r9, aDisknumberdire; "diskNumberDirectoryStart"
0x18006bfae  mov     r8, rdi
0x18006bfb1  mov     edx, 0B2h
0x18006bfb6  mov     rcx, rsi
0x18006bfb9  call    ??$readThenLog@I@detail@win_musl@@YAIPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<uint>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x18006bfbe  test    eax, eax
0x18006bfc0  jnz     loc_18006C2B8
0x18006bfc6  movaps  xmm6, [rsp+160h+var_108+8]
0x18006bfcb  mov     [rsp+160h+var_120], r12b
0x18006bfd0  movdqa  [rsp+160h+var_118+8], xmm6
0x18006bfd6  lea     r8, [rsp+160h+var_120]
0x18006bfdb  lea     rdx, [rsp+160h+var_108+8]
0x18006bfe0  lea     rcx, [rsp+160h+var_118+8]
0x18006bfe5  call    ??$vector_read@_K@detail@win_musl@@YA_KU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@PEA_NW4Enum@ByteOrderOption@01@@Z; win_musl::detail::vector_read<unsigned __int64>(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,bool *,win_musl::detail::ByteOrderOption::Enum)
0x18006bfea  mov     r15, rax
0x18006bfed  cmp     [rsp+160h+var_120], r12b
0x18006bff2  jnz     loc_18006C2FC
0x18006bff8  movaps  xmm6, [rsp+160h+var_108+8]
0x18006bffd  mov     [rsp+160h+var_120], r12b
0x18006c002  movdqa  [rsp+160h+var_118+8], xmm6
0x18006c008  lea     r8, [rsp+160h+var_120]
0x18006c00d  lea     rdx, [rsp+160h+var_108+8]
0x18006c012  lea     rcx, [rsp+160h+var_118+8]
0x18006c017  call    ??$vector_read@_K@detail@win_musl@@YA_KU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@PEA_NW4Enum@ByteOrderOption@01@@Z; win_musl::detail::vector_read<unsigned __int64>(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,bool *,win_musl::detail::ByteOrderOption::Enum)
0x18006c01c  mov     r14, rax
0x18006c01f  cmp     [rsp+160h+var_120], r12b
0x18006c024  jnz     loc_18006C32C
0x18006c02a  cmp     r15, rax
0x18006c02d  jnz     loc_18006C35C
0x18006c033  movaps  xmm6, [rsp+160h+var_108+8]
0x18006c038  mov     [rsp+160h+var_120], r12b
0x18006c03d  movdqa  [rsp+160h+var_118+8], xmm6
0x18006c043  lea     r8, [rsp+160h+var_120]
0x18006c048  lea     rdx, [rsp+160h+var_108+8]
0x18006c04d  lea     rcx, [rsp+160h+var_118+8]
0x18006c052  call    ??$vector_read@_K@detail@win_musl@@YA_KU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@PEA_NW4Enum@ByteOrderOption@01@@Z; win_musl::detail::vector_read<unsigned __int64>(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,bool *,win_musl::detail::ByteOrderOption::Enum)
0x18006c057  mov     r15, rax
0x18006c05a  cmp     [rsp+160h+var_120], r12b
0x18006c05f  jnz     loc_18006C3A0
0x18006c065  movaps  xmm6, [rsp+160h+var_108+8]
0x18006c06a  mov     [rsp+160h+var_120], r12b
0x18006c06f  movdqa  [rsp+160h+var_118+8], xmm6
0x18006c075  lea     r8, [rsp+160h+var_120]
0x18006c07a  lea     rdx, [rsp+160h+var_108+8]
0x18006c07f  lea     rcx, [rsp+160h+var_118+8]
0x18006c084  call    ??$vector_read@_K@detail@win_musl@@YA_KU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@PEA_NW4Enum@ByteOrderOption@01@@Z; win_musl::detail::vector_read<unsigned __int64>(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,bool *,win_musl::detail::ByteOrderOption::Enum)
0x18006c089  mov     r8, rax
0x18006c08c  cmp     [rsp+160h+var_120], r12b
0x18006c091  jnz     loc_18006C3D0
0x18006c097  mov     rdx, [rbx+18h]
0x18006c09b  mov     ecx, [rdx+80h]
0x18006c0a1  test    ecx, ecx
0x18006c0a3  jz      loc_18006C450
0x18006c0a9  cmp     ecx, 1
0x18006c0ac  jnz     loc_18006C400
0x18006c0b2  mov     eax, 0FFFFFFFFh
0x18006c0b7  cmp     [rdx+98h], rax
0x18006c0be  jnz     short loc_18006C0C7
0x18006c0c0  mov     [rdx+98h], r8
0x18006c0c7  mov     rcx, [rbx+18h]
0x18006c0cb  cmp     [rcx+90h], rax
0x18006c0d2  jnz     short loc_18006C0DB
0x18006c0d4  mov     [rcx+90h], r15
0x18006c0db  mov     rax, [rbx+18h]
0x18006c0df  mov     ecx, 0FFFFh
0x18006c0e4  cmp     [rax+88h], rcx
0x18006c0eb  jnz     short loc_18006C0F4
0x18006c0ed  mov     [rax+88h], r14
0x18006c0f4  mov     rax, [rbx+18h]
0x18006c0f8  cmp     [rax+0A8h], ecx
0x18006c0fe  jz      loc_18006C444
0x18006c104  mov     rax, [rbx+18h]
0x18006c108  cmp     [rax+0ACh], ecx
0x18006c10e  jnz     short loc_18006C117
0x18006c110  mov     [rax+0ACh], r12d
0x18006c117  mov     rcx, [rbx+20h]
0x18006c11b  test    rcx, rcx
0x18006c11e  jz      short loc_18006C157
0x18006c120  cmp     cs:dword_1801C4FE0, 0FFFFFFFFh
0x18006c127  jz      short loc_18006C157
0x18006c129  mov     rax, [rcx]
0x18006c12c  mov     rdx, [rbx+28h]
0x18006c130  add     rdx, [rbx+50h]
0x18006c134  mov     rax, [rax+28h]
0x18006c138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c13d  mov     rcx, [rbx+20h]
0x18006c141  mov     [rbx+20h], r12
0x18006c145  test    rcx, rcx
0x18006c148  jz      short loc_18006C157
0x18006c14a  mov     rax, [rcx]
0x18006c14d  mov     rax, [rax+10h]
0x18006c151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c156  nop
0x18006c157  mov     rcx, [rbp+60h+var_40]
0x18006c15b  xor     rcx, rsp; StackCookie
0x18006c15e  call    __security_check_cookie
0x18006c163  lea     r11, [rsp+160h+var_20]
0x18006c16b  mov     rbx, [r11+38h]
0x18006c16f  mov     rsi, [r11+40h]
0x18006c173  movaps  xmm6, xmmword ptr [r11-10h]
0x18006c178  mov     rsp, r11
0x18006c17b  pop     r15
0x18006c17d  pop     r14
0x18006c17f  pop     r12
0x18006c181  pop     rdi
0x18006c182  pop     rbp
0x18006c183  retn
0x18006c184  lea     rax, aWrongNumberOfB; "Wrong number of bytes sent"
0x18006c18b  mov     qword ptr [rsp+160h+var_138], rax
0x18006c190  mov     [rsp+160h+var_140], 80511001h
0x18006c198  mov     edi, 8Fh
0x18006c19d  mov     r9d, 400h
0x18006c1a3  mov     r8d, edi
0x18006c1a6  lea     rdx, word_180139126
0x18006c1ad  lea     rbx, aNoFilename; "(no filename)"
0x18006c1b4  mov     rcx, rbx
0x18006c1b7  call    ?DebugLogHelper@win_musl@@YAXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z; win_musl::DebugLogHelper(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *)
0x18006c1bc  lea     rax, aUnexpectedHres; "Unexpected HRESULT returned by API"
0x18006c1c3  mov     qword ptr [rsp+160h+var_108+8], rax
0x18006c1c8  lea     rdx, [rsp+160h+var_108+8]
0x18006c1cd  lea     rcx, [rbp+60h+pExceptionObject]
0x18006c1d1  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18006c1d7  xor     edx, edx; Val
0x18006c1d9  lea     r8d, [rdi-27h]; Size
0x18006c1dd  lea     rcx, [rbp+60h+var_B8]; void *
0x18006c1e1  call    memset_0
0x18006c1e6  mov     [rbp+60h+var_C0], rbx
0x18006c1ea  mov     [rbp+60h+var_C4], edi
0x18006c1ed  mov     eax, 0FFFFFFFFh
0x18006c1f2  mov     [rbp+60h+var_58], eax
0x18006c1f5  lea     rax, ??_7THResultException@SplException@@6B@; const SplException::THResultException::`vftable'
0x18006c1fc  mov     [rbp+60h+pExceptionObject], rax
0x18006c200  mov     [rbp+60h+var_C8], 80511001h
0x18006c207  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006c20e  movdqu  [rbp+60h+var_80], xmm0
0x18006c213  mov     rax, cs:?Functions@SplException@@3UExceptionTableFunctions@1@A; SplException::ExceptionTableFunctions SplException::Functions
0x18006c21a  test    rax, rax
0x18006c21d  jz      short loc_18006C22B
0x18006c21f  lea     rcx, [rbp+60h+var_C8]
0x18006c223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c228  mov     [rbp+60h+var_58], eax
0x18006c22b  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18006c232  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x18006c236  call    _CxxThrowException_0
0x18006c23c  movdqa  [rsp+160h+var_118+8], xmm6
0x18006c242  lea     rax, [rsp+160h+var_118+8]
0x18006c247  mov     qword ptr [rsp+160h+var_138], rax
0x18006c24c  mov     [rsp+160h+var_140], 8
0x18006c254  lea     r9, aSizeofthis; "sizeOfThis"
0x18006c25b  lea     r8, aWinMuslConsump; "win_musl::consumption::ZipEndOfCentralD"...
0x18006c262  mov     edx, 9Ah
0x18006c267  lea     rcx, aOnecorePrintsc_8; "onecore\\printscan\\dox\\opc\\zipio_lca"...
0x18006c26e  call    ?ThrowReadError@detail@win_musl@@YAXPEBDK00IU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@@Z; win_musl::detail::ThrowReadError(char const *,ulong,char const *,char const *,uint,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001)
0x18006c274  lea     rax, aArchiveFeature; "Archive feature not supported: only sup"...
0x18006c27b  mov     [rsp+160h+var_130], rax; struct win_musl::TStringEllipseBase *
0x18006c280  mov     [rsp+160h+var_138], 80511008h; unsigned int
0x18006c288  mov     [rsp+160h+var_140], 0ACh; unsigned int
0x18006c290  lea     r9, word_180139126
0x18006c297  lea     r8, aNoFilename; "(no filename)"
0x18006c29e  lea     rcx, [rbp+60h+pExceptionObject]; this
0x18006c2a2  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18006c2a7  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18006c2ae  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x18006c2b2  call    _CxxThrowException_0
0x18006c2b8  lea     rax, aArchiveFeature; "Archive feature not supported: only sup"...
0x18006c2bf  mov     [rsp+160h+var_130], rax; struct win_musl::TStringEllipseBase *
0x18006c2c4  mov     [rsp+160h+var_138], 80511008h; unsigned int
0x18006c2cc  mov     [rsp+160h+var_140], 0B6h; unsigned int
0x18006c2d4  lea     r9, word_180139126
0x18006c2db  lea     r8, aNoFilename; "(no filename)"
0x18006c2e2  lea     rcx, [rbp+60h+pExceptionObject]; this
0x18006c2e6  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18006c2eb  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18006c2f2  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x18006c2f6  call    _CxxThrowException_0
0x18006c2fc  movdqa  [rsp+160h+var_118+8], xmm6
0x18006c302  lea     rax, [rsp+160h+var_118+8]
0x18006c307  mov     qword ptr [rsp+160h+var_138], rax
0x18006c30c  mov     [rsp+160h+var_140], 8
0x18006c314  lea     r9, aDirectoryentri; "directoryEntriesCountThisDisk"
0x18006c31b  mov     r8, rdi
0x18006c31e  mov     edx, 0BCh
0x18006c323  mov     rcx, rsi
0x18006c326  call    ?ThrowReadError@detail@win_musl@@YAXPEBDK00IU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@@Z; win_musl::detail::ThrowReadError(char const *,ulong,char const *,char const *,uint,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001)
0x18006c32c  movdqa  [rsp+160h+var_118+8], xmm6
0x18006c332  lea     rax, [rsp+160h+var_118+8]
0x18006c337  mov     qword ptr [rsp+160h+var_138], rax
0x18006c33c  mov     [rsp+160h+var_140], 8
0x18006c344  lea     r9, aCountentries; "countEntries"
0x18006c34b  mov     r8, rdi
0x18006c34e  mov     edx, 0C7h
0x18006c353  mov     rcx, rsi
0x18006c356  call    ?ThrowReadError@detail@win_musl@@YAXPEBDK00IU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@@Z; win_musl::detail::ThrowReadError(char const *,ulong,char const *,char const *,uint,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001)
0x18006c35c  lea     rax, aArchiveFeature; "Archive feature not supported: only sup"...
0x18006c363  mov     [rsp+160h+var_130], rax; struct win_musl::TStringEllipseBase *
0x18006c368  mov     [rsp+160h+var_138], 80511008h; unsigned int
0x18006c370  mov     [rsp+160h+var_140], 0D0h; unsigned int
0x18006c378  lea     r9, word_180139126
0x18006c37f  lea     r8, aNoFilename; "(no filename)"
0x18006c386  lea     rcx, [rbp+60h+pExceptionObject]; this
0x18006c38a  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18006c38f  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18006c396  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x18006c39a  call    _CxxThrowException_0
0x18006c3a0  movdqa  [rsp+160h+var_118+8], xmm6
0x18006c3a6  lea     rax, [rsp+160h+var_118+8]
0x18006c3ab  mov     qword ptr [rsp+160h+var_138], rax
0x18006c3b0  mov     [rsp+160h+var_140], 8
0x18006c3b8  lea     r9, aSizecentraldir; "sizeCentralDirectory"
0x18006c3bf  mov     r8, rdi
0x18006c3c2  mov     edx, 0DBh
0x18006c3c7  mov     rcx, rsi
0x18006c3ca  call    ?ThrowReadError@detail@win_musl@@YAXPEBDK00IU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@@Z; win_musl::detail::ThrowReadError(char const *,ulong,char const *,char const *,uint,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001)
0x18006c3d0  movdqa  [rsp+160h+var_118+8], xmm6
0x18006c3d6  lea     rax, [rsp+160h+var_118+8]
0x18006c3db  mov     qword ptr [rsp+160h+var_138], rax
0x18006c3e0  mov     [rsp+160h+var_140], 8
  ... truncated ...
```
