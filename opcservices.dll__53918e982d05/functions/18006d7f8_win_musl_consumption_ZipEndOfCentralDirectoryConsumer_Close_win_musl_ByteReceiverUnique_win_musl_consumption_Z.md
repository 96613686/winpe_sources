# win_musl::consumption::ZipEndOfCentralDirectoryConsumer::Close(win_musl::ByteReceiverUnique<win_musl::consumption::ZipEndOfCentralDirectoryConsumer,0,IUnknown> &)

- ea: `0x18006d7f8`
- end: `0x18006dda2`
- name: `?Close@ZipEndOfCentralDirectoryConsumer@consumption@win_musl@@QEAAXAEAV?$ByteReceiverUnique@VZipEndOfCentralDirectoryConsumer@consumption@win_musl@@$0A@UIUnknown@@@3@@Z`
- size: `1450`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18006f154`

## callees

- `0x1800124f4`
- `0x18002db70`
- `0x180032934`
- `0x18006d7f8`
- `0x18006dda8`
- `0x18006df14`
- `0x18006e07c`
- `0x1800cbaf4`
- `0x1800cd6fc`
- `0x1800d6354`
- `0x180114a58`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18006db05`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18006db05`

## string_xrefs

- `0x18006d895`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipendofcentraldirectoryconsumer.cpp`
- `0x18006d9a5`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipendofcentraldirectoryconsumer.cpp`
- `0x18006d9e1`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipendofcentraldirectoryconsumer.cpp`
- `0x18006da22`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipendofcentraldirectoryconsumer.cpp`
- `0x18006d886`: `win_musl::consumption::ZipEndOfCentralDirectoryConsumer::Close`
- `0x18006da16`: `win_musl::consumption::ZipEndOfCentralDirectoryConsumer::Close`
- `0x18006d996`: `sizeCentralDirectory`
- `0x18006da0f`: `_bytesNeededComment`
- `0x18006d8d6`: `diskNumberDirectoryStart`
- `0x18006d919`: `directoryEntriesCountThisDisk`
- `0x18006d9d2`: `offsetCentralDirectory`
- `0x18006dd15`: `invalid end_of_central_directory source value!`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall win_musl::consumption::ZipEndOfCentralDirectoryConsumer::Close(
        win_musl::consumption::ZipEndOfCentralDirectoryConsumer *this)
{
  __int64 v2; // rcx
  unsigned __int16 Then; // ax
  int v4; // r14d
  unsigned __int16 v5; // ax
  int v6; // esi
  __int16 v7; // bx
  unsigned __int16 v8; // ax
  __int64 v9; // r15
  __int64 v10; // rbx
  __int64 v11; // r12
  __int64 v12; // rdx
  int v13; // ecx
  __int128 v14; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v15; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v16; // [rsp+60h] [rbp-A0h]
  _QWORD pExceptionObject[3]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v18[2]; // [rsp+88h] [rbp-78h] BYREF
  const char *v19; // [rsp+90h] [rbp-70h]
  _BYTE v20[56]; // [rsp+98h] [rbp-68h] BYREF
  GUID v21; // [rsp+D0h] [rbp-30h]
  int v22; // [rsp+F8h] [rbp-8h]

  v16 = -2;
  v2 = *((_QWORD *)this + 8);
  if ( !v2 || *((_QWORD *)this + 9) - v2 != 18 )
  {
    win_musl::DebugLogHelper("(no filename)", &word_180139126, 158, 1024, -2142171135, L"Wrong number of bytes sent");
    *(_QWORD *)&v14 = "Unexpected HRESULT returned by API";
    exception::exception((exception *)pExceptionObject, (const char *const *)&v14);
    memset_0(v20, 0, 0x68u);
    v19 = "(no filename)";
    v18[1] = 158;
    v22 = -1;
    pExceptionObject[0] = &SplException::THResultException::`vftable';
    v18[0] = -2142171135;
    v21 = GUID_NULL;
    if ( SplException::Functions )
      v22 = SplException::Functions(v18);
    throw (SplException::THResultException *)pExceptionObject;
  }
  *(_QWORD *)&v14 = 18;
  *((_QWORD *)&v14 + 1) = v2;
  v15 = v14;
  Then = win_musl::detail::readThenLog<unsigned short>(
           (unsigned int)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipendofcentrald"
                         "irectoryconsumer.cpp",
           168,
           (unsigned int)"win_musl::consumption::ZipEndOfCentralDirectoryConsumer::Close",
           (unsigned int)"diskNumberThis",
           (__int64)&v15,
           (__int64)&v14);
  v4 = Then;
  if ( Then && Then != 0xFFFF )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0xACu,
      0x80511008,
      (struct win_musl::TStringEllipseBase *)L"Archive feature not supported: only support single disk archives.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v15 = v14;
  v5 = win_musl::detail::readThenLog<unsigned short>(
         (unsigned int)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipendofcentraldir"
                       "ectoryconsumer.cpp",
         178,
         (unsigned int)"win_musl::consumption::ZipEndOfCentralDirectoryConsumer::Close",
         (unsigned int)"diskNumberDirectoryStart",
         (__int64)&v15,
         (__int64)&v14);
  v6 = v5;
  if ( v5 && v5 != 0xFFFF )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0xB6u,
      0x80511008,
      (struct win_musl::TStringEllipseBase *)L"Archive feature not supported: only support single disk archives.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v15 = v14;
  v7 = win_musl::detail::readThenLog<unsigned short>(
         (unsigned int)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipendofcentraldir"
                       "ectoryconsumer.cpp",
         188,
         (unsigned int)"win_musl::consumption::ZipEndOfCentralDirectoryConsumer::Close",
         (unsigned int)"directoryEntriesCountThisDisk",
         (__int64)&v15,
         (__int64)&v14);
  v15 = v14;
  v8 = win_musl::detail::readThenLog<unsigned short>(
         (unsigned int)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipendofcentraldir"
                       "ectoryconsumer.cpp",
         193,
         (unsigned int)"win_musl::consumption::ZipEndOfCentralDirectoryConsumer::Close",
         (unsigned int)"countEntries",
         (__int64)&v15,
         (__int64)&v14);
  v9 = v8;
  if ( v7 != v8 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0xC5u,
      0x80511008,
      (struct win_musl::TStringEllipseBase *)L"Archive feature not supported: only support single disk archives.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v15 = v14;
  v10 = (unsigned int)win_musl::detail::readThenLog<unsigned int>(
                        (unsigned int)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zip"
                                      "endofcentraldirectoryconsumer.cpp",
                        202,
                        (unsigned int)"win_musl::consumption::ZipEndOfCentralDirectoryConsumer::Close",
                        (unsigned int)"sizeCentralDirectory",
                        (__int64)&v15,
                        (__int64)&v14);
  v15 = v14;
  v11 = (unsigned int)win_musl::detail::readThenLog<unsigned int>(
                        (unsigned int)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zip"
                                      "endofcentraldirectoryconsumer.cpp",
                        208,
                        (unsigned int)"win_musl::consumption::ZipEndOfCentralDirectoryConsumer::Close",
                        (unsigned int)"offsetCentralDirectory",
                        (__int64)&v15,
                        (__int64)&v14);
  v15 = v14;
  *((_WORD *)this + 44) = win_musl::detail::readThenLog<unsigned short>(
                            (unsigned int)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\"
                                          "zipendofcentraldirectoryconsumer.cpp",
                            211,
                            (unsigned int)"win_musl::consumption::ZipEndOfCentralDirectoryConsumer::Close",
                            (unsigned int)"_bytesNeededComment",
                            (__int64)&v15,
                            (__int64)&v14);
  v12 = *((_QWORD *)this + 4);
  v13 = *(_DWORD *)(v12 + 128);
  if ( !v13 )
  {
    *(_DWORD *)(v12 + 128) = 1;
    *(_QWORD *)(*((_QWORD *)this + 4) + 152LL) = v11;
    *(_QWORD *)(*((_QWORD *)this + 4) + 144LL) = v10;
    *(_QWORD *)(*((_QWORD *)this + 4) + 136LL) = v9;
    *(_DWORD *)(*((_QWORD *)this + 4) + 168LL) = v4;
LABEL_8:
    *(_DWORD *)(*((_QWORD *)this + 4) + 172LL) = v6;
    goto LABEL_9;
  }
  if ( v13 != 2 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x110u,
      0x8000FFFF,
      (struct win_musl::TStringEllipseBase *)L"invalid end_of_central_directory source value!");
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( (_DWORD)v11 != -1 )
    *(_QWORD *)(v12 + 152) = v11;
  if ( (_DWORD)v10 != -1 )
    *(_QWORD *)(*((_QWORD *)this + 4) + 144LL) = v10;
  if ( (_WORD)v9 != 0xFFFF )
    *(_QWORD *)(*((_QWORD *)this + 4) + 136LL) = v9;
  if ( (_WORD)v4 != 0xFFFF )
    *(_DWORD *)(*((_QWORD *)this + 4) + 168LL) = v4;
  if ( (_WORD)v6 != 0xFFFF )
    goto LABEL_8;
LABEL_9:
  if ( *((_WORD *)this + 44) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0 )
      WPP_SF_ID(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        12,
        WPP_37a605dc7fd83120dddcbd48d857a9dd_Traceguids,
        *((_QWORD *)this + 6),
        *((unsigned __int16 *)this + 44));
    *(_QWORD *)&v15 = *((_QWORD *)this + 6);
    *((_QWORD *)&v15 + 1) = v15 + *((unsigned __int16 *)this + 44);
    win_dox::ByteCollection::CreateSenderOfRange(*((_QWORD *)this + 4) + 104LL, &v14, &v15);
    win_musl::consumption::ZipEndOfCentralDirectoryConsumer::ProcessCommentByteSender(
      this,
      (struct win_dox::ByteSender *)&v14);
    *(_QWORD *)&v14 = &win_dox::OpcRelationshipSender::`vftable';
    if ( *((_QWORD *)&v14 + 1) )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v14 + 1) + 16LL))(*((_QWORD *)&v14 + 1));
  }
  else
  {
    win_musl::consumption::ZipEndOfCentralDirectoryConsumer::ReportComment(this);
  }
}

```

## disassembly

```asm
0x18006d7f8  push    rbp
0x18006d7fa  push    rbx
0x18006d7fb  push    rsi
0x18006d7fc  push    rdi
0x18006d7fd  push    r12
0x18006d7ff  push    r13
0x18006d801  push    r14
0x18006d803  push    r15
0x18006d805  lea     rbp, [rsp-28h]
0x18006d80a  sub     rsp, 128h
0x18006d811  mov     [rsp+160h+var_100], 0FFFFFFFFFFFFFFFEh
0x18006d81a  mov     rax, cs:__security_cookie
0x18006d821  xor     rax, rsp
0x18006d824  mov     [rbp+60h+var_50], rax
0x18006d828  mov     rdi, rcx
0x18006d82b  xor     r13d, r13d
0x18006d82e  mov     rcx, [rcx+40h]
0x18006d832  test    rcx, rcx
0x18006d835  jz      loc_18006DAB7
0x18006d83b  mov     rax, [rdi+48h]
0x18006d83f  sub     rax, rcx
0x18006d842  cmp     rax, 12h
0x18006d846  jnz     loc_18006DAB7
0x18006d84c  mov     dword ptr [rsp+160h+var_120], eax
0x18006d850  xor     eax, eax
0x18006d852  mov     dword ptr [rsp+160h+var_120+4], eax
0x18006d856  mov     qword ptr [rsp+160h+var_120+8], rcx
0x18006d85b  movaps  xmm0, [rsp+160h+var_120]
0x18006d860  movaps  [rsp+160h+var_120], xmm0
0x18006d865  movdqa  [rsp+160h+var_110], xmm0
0x18006d86b  lea     rax, [rsp+160h+var_120]
0x18006d870  mov     qword ptr [rsp+160h+var_138], rax
0x18006d875  lea     rax, [rsp+160h+var_110]
0x18006d87a  mov     qword ptr [rsp+160h+var_140], rax
0x18006d87f  lea     r9, aDisknumberthis; "diskNumberThis"
0x18006d886  lea     r12, aWinMuslConsump_9; "win_musl::consumption::ZipEndOfCentralD"...
0x18006d88d  mov     r8, r12
0x18006d890  mov     edx, 0A8h
0x18006d895  lea     r15, aOnecorePrintsc_5; "onecore\\printscan\\dox\\opc\\zipio_lca"...
0x18006d89c  mov     rcx, r15
0x18006d89f  call    ??$readThenLog@G@detail@win_musl@@YAGPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<ushort>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x18006d8a4  movzx   r14d, ax
0x18006d8a8  mov     ebx, 0FFFFh
0x18006d8ad  cmp     r13w, r14w
0x18006d8b1  jnz     loc_18006DBD3
0x18006d8b7  movaps  xmm0, [rsp+160h+var_120]
0x18006d8bc  movdqa  [rsp+160h+var_110], xmm0
0x18006d8c2  lea     rax, [rsp+160h+var_120]
0x18006d8c7  mov     qword ptr [rsp+160h+var_138], rax
0x18006d8cc  lea     rax, [rsp+160h+var_110]
0x18006d8d1  mov     qword ptr [rsp+160h+var_140], rax
0x18006d8d6  lea     r9, aDisknumberdire; "diskNumberDirectoryStart"
0x18006d8dd  mov     r8, r12
0x18006d8e0  mov     edx, 0B2h
0x18006d8e5  mov     rcx, r15
0x18006d8e8  call    ??$readThenLog@G@detail@win_musl@@YAGPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<ushort>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x18006d8ed  movzx   esi, ax
0x18006d8f0  cmp     r13w, si
0x18006d8f4  jnz     loc_18006DC23
0x18006d8fa  movaps  xmm0, [rsp+160h+var_120]
0x18006d8ff  movdqa  [rsp+160h+var_110], xmm0
0x18006d905  lea     rax, [rsp+160h+var_120]
0x18006d90a  mov     qword ptr [rsp+160h+var_138], rax
0x18006d90f  lea     rax, [rsp+160h+var_110]
0x18006d914  mov     qword ptr [rsp+160h+var_140], rax
0x18006d919  lea     r9, aDirectoryentri; "directoryEntriesCountThisDisk"
0x18006d920  mov     r8, r12
0x18006d923  mov     edx, 0BCh
0x18006d928  mov     rcx, r15
0x18006d92b  call    ??$readThenLog@G@detail@win_musl@@YAGPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<ushort>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x18006d930  movzx   ebx, ax
0x18006d933  movaps  xmm0, [rsp+160h+var_120]
0x18006d938  movdqa  [rsp+160h+var_110], xmm0
0x18006d93e  lea     rax, [rsp+160h+var_120]
0x18006d943  mov     qword ptr [rsp+160h+var_138], rax
0x18006d948  lea     rax, [rsp+160h+var_110]
0x18006d94d  mov     qword ptr [rsp+160h+var_140], rax
0x18006d952  lea     r9, aCountentries; "countEntries"
0x18006d959  mov     r8, r12
0x18006d95c  mov     edx, 0C1h
0x18006d961  mov     rcx, r15
0x18006d964  call    ??$readThenLog@G@detail@win_musl@@YAGPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<ushort>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x18006d969  movzx   r15d, ax
0x18006d96d  cmp     bx, r15w
0x18006d971  jnz     loc_18006DC72
0x18006d977  movaps  xmm0, [rsp+160h+var_120]
0x18006d97c  movdqa  [rsp+160h+var_110], xmm0
0x18006d982  lea     rax, [rsp+160h+var_120]
0x18006d987  mov     qword ptr [rsp+160h+var_138], rax
0x18006d98c  lea     rax, [rsp+160h+var_110]
0x18006d991  mov     qword ptr [rsp+160h+var_140], rax
0x18006d996  lea     r9, aSizecentraldir; "sizeCentralDirectory"
0x18006d99d  mov     r8, r12
0x18006d9a0  mov     edx, 0CAh
0x18006d9a5  lea     rcx, aOnecorePrintsc_5; "onecore\\printscan\\dox\\opc\\zipio_lca"...
0x18006d9ac  call    ??$readThenLog@I@detail@win_musl@@YAIPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<uint>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x18006d9b1  mov     ebx, eax
0x18006d9b3  movaps  xmm0, [rsp+160h+var_120]
0x18006d9b8  movdqa  [rsp+160h+var_110], xmm0
0x18006d9be  lea     rax, [rsp+160h+var_120]
0x18006d9c3  mov     qword ptr [rsp+160h+var_138], rax
0x18006d9c8  lea     rax, [rsp+160h+var_110]
0x18006d9cd  mov     qword ptr [rsp+160h+var_140], rax
0x18006d9d2  lea     r9, aOffsetcentrald; "offsetCentralDirectory"
0x18006d9d9  mov     r8, r12
0x18006d9dc  mov     edx, 0D0h
0x18006d9e1  lea     rcx, aOnecorePrintsc_5; "onecore\\printscan\\dox\\opc\\zipio_lca"...
0x18006d9e8  call    ??$readThenLog@I@detail@win_musl@@YAIPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<uint>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x18006d9ed  mov     r12d, eax
0x18006d9f0  movaps  xmm0, [rsp+160h+var_120]
0x18006d9f5  movdqa  [rsp+160h+var_110], xmm0
0x18006d9fb  lea     rax, [rsp+160h+var_120]
0x18006da00  mov     qword ptr [rsp+160h+var_138], rax
0x18006da05  lea     rax, [rsp+160h+var_110]
0x18006da0a  mov     qword ptr [rsp+160h+var_140], rax
0x18006da0f  lea     r9, aBytesneededcom; "_bytesNeededComment"
0x18006da16  lea     r8, aWinMuslConsump_9; "win_musl::consumption::ZipEndOfCentralD"...
0x18006da1d  mov     edx, 0D3h
0x18006da22  lea     rcx, aOnecorePrintsc_5; "onecore\\printscan\\dox\\opc\\zipio_lca"...
0x18006da29  call    ??$readThenLog@G@detail@win_musl@@YAGPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<ushort>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x18006da2e  mov     [rdi+58h], ax
0x18006da32  mov     rdx, [rdi+20h]
0x18006da36  mov     ecx, [rdx+80h]
0x18006da3c  test    ecx, ecx
0x18006da3e  jnz     loc_18006DCB8
0x18006da44  mov     dword ptr [rdx+80h], 1
0x18006da4e  mov     rax, [rdi+20h]
0x18006da52  mov     [rax+98h], r12
0x18006da59  mov     rax, [rdi+20h]
0x18006da5d  mov     [rax+90h], rbx
0x18006da64  mov     rax, [rdi+20h]
0x18006da68  mov     [rax+88h], r15
0x18006da6f  mov     rax, [rdi+20h]
0x18006da73  mov     [rax+0A8h], r14d
0x18006da7a  mov     rax, [rdi+20h]
0x18006da7e  mov     [rax+0ACh], esi
0x18006da84  cmp     [rdi+58h], r13w
0x18006da89  jnz     loc_18006DD5B
0x18006da8f  mov     rcx, rdi; this
0x18006da92  call    ?ReportComment@ZipEndOfCentralDirectoryConsumer@consumption@win_musl@@AEAAXXZ; win_musl::consumption::ZipEndOfCentralDirectoryConsumer::ReportComment(void)
0x18006da97  mov     rcx, [rbp+60h+var_50]
0x18006da9b  xor     rcx, rsp; StackCookie
0x18006da9e  call    __security_check_cookie
0x18006daa3  add     rsp, 128h
0x18006daaa  pop     r15
0x18006daac  pop     r14
0x18006daae  pop     r13
0x18006dab0  pop     r12
0x18006dab2  pop     rdi
0x18006dab3  pop     rsi
0x18006dab4  pop     rbx
0x18006dab5  pop     rbp
0x18006dab6  retn
0x18006dab7  lea     rax, aWrongNumberOfB; "Wrong number of bytes sent"
0x18006dabe  mov     qword ptr [rsp+160h+var_138], rax
0x18006dac3  mov     [rsp+160h+var_140], 80511001h
0x18006dacb  mov     edi, 9Eh
0x18006dad0  mov     r9d, 400h
0x18006dad6  mov     r8d, edi
0x18006dad9  lea     rdx, word_180139126
0x18006dae0  lea     rbx, aNoFilename; "(no filename)"
0x18006dae7  mov     rcx, rbx
0x18006daea  call    ?DebugLogHelper@win_musl@@YAXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z; win_musl::DebugLogHelper(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *)
0x18006daef  lea     rax, aUnexpectedHres; "Unexpected HRESULT returned by API"
0x18006daf6  mov     qword ptr [rsp+160h+var_120], rax
0x18006dafb  lea     rdx, [rsp+160h+var_120]
0x18006db00  lea     rcx, [rsp+160h+pExceptionObject]
0x18006db05  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18006db0b  xor     edx, edx; Val
0x18006db0d  lea     r8d, [rdi-36h]; Size
0x18006db11  lea     rcx, [rbp+60h+var_C8]; void *
0x18006db15  call    memset_0
0x18006db1a  mov     [rbp+60h+var_D0], rbx
0x18006db1e  mov     [rbp+60h+var_D4], edi
0x18006db21  or      ecx, 0FFFFFFFFh
0x18006db24  mov     [rbp+60h+var_68], ecx
0x18006db27  lea     rax, ??_7THResultException@SplException@@6B@; const SplException::THResultException::`vftable'
0x18006db2e  mov     [rsp+160h+pExceptionObject], rax
0x18006db33  mov     [rbp+60h+var_D8], 80511001h
0x18006db3a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006db41  movdqu  [rbp+60h+var_90], xmm0
0x18006db46  mov     rax, cs:?Functions@SplException@@3UExceptionTableFunctions@1@A; SplException::ExceptionTableFunctions SplException::Functions
0x18006db4d  test    rax, rax
0x18006db50  jz      short loc_18006DB5E
0x18006db52  lea     rcx, [rbp+60h+var_D8]
0x18006db56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006db5b  mov     [rbp+60h+var_68], eax
0x18006db5e  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18006db65  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x18006db6a  call    _CxxThrowException_0
0x18006db70  mov     rdx, [rdi+30h]
0x18006db74  mov     qword ptr [rsp+160h+var_110], rdx
0x18006db79  movzx   eax, word ptr [rdi+58h]
0x18006db7d  add     rax, rdx
0x18006db80  mov     qword ptr [rsp+160h+var_110+8], rax
0x18006db85  mov     rcx, [rdi+20h]
0x18006db89  add     rcx, 68h ; 'h'
0x18006db8d  lea     r8, [rsp+160h+var_110]
0x18006db92  lea     rdx, [rsp+160h+var_120]
0x18006db97  call    ?CreateSenderOfRange@ByteCollection@win_dox@@QEBA?AVByteSender@2@AEBU?$range@_K@2@@Z; win_dox::ByteCollection::CreateSenderOfRange(win_dox::range<unsigned __int64> const &)
0x18006db9c  nop
0x18006db9d  lea     rdx, [rsp+160h+var_120]; struct win_dox::ByteSender *
0x18006dba2  mov     rcx, rdi; this
0x18006dba5  call    ?ProcessCommentByteSender@ZipEndOfCentralDirectoryConsumer@consumption@win_musl@@AEAAXAEAVByteSender@win_dox@@@Z; win_musl::consumption::ZipEndOfCentralDirectoryConsumer::ProcessCommentByteSender(win_dox::ByteSender &)
0x18006dbaa  nop
0x18006dbab  lea     rax, ??_7OpcRelationshipSender@win_dox@@6B@; const win_dox::OpcRelationshipSender::`vftable'
0x18006dbb2  mov     qword ptr [rsp+160h+var_120], rax
0x18006dbb7  mov     rcx, qword ptr [rsp+160h+var_120+8]
0x18006dbbc  test    rcx, rcx
0x18006dbbf  jz      short loc_18006DBCE
0x18006dbc1  mov     rax, [rcx]
0x18006dbc4  mov     rax, [rax+10h]
0x18006dbc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dbcd  nop
0x18006dbce  jmp     loc_18006DA97
0x18006dbd3  cmp     bx, r14w
0x18006dbd7  jz      loc_18006D8B7
0x18006dbdd  lea     rax, aArchiveFeature; "Archive feature not supported: only sup"...
0x18006dbe4  mov     [rsp+160h+var_130], rax; struct win_musl::TStringEllipseBase *
0x18006dbe9  mov     [rsp+160h+var_138], 80511008h; unsigned int
0x18006dbf1  mov     [rsp+160h+var_140], 0ACh; unsigned int
0x18006dbf9  lea     r9, word_180139126
0x18006dc00  lea     r8, aNoFilename; "(no filename)"
0x18006dc07  lea     rcx, [rsp+160h+pExceptionObject]; this
0x18006dc0c  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18006dc11  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18006dc18  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x18006dc1d  call    _CxxThrowException_0
0x18006dc23  cmp     bx, si
0x18006dc26  jz      loc_18006D8FA
0x18006dc2c  lea     rax, aArchiveFeature; "Archive feature not supported: only sup"...
0x18006dc33  mov     [rsp+160h+var_130], rax; struct win_musl::TStringEllipseBase *
0x18006dc38  mov     [rsp+160h+var_138], 80511008h; unsigned int
0x18006dc40  mov     [rsp+160h+var_140], 0B6h; unsigned int
0x18006dc48  lea     r9, word_180139126
0x18006dc4f  lea     r8, aNoFilename; "(no filename)"
0x18006dc56  lea     rcx, [rsp+160h+pExceptionObject]; this
0x18006dc5b  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18006dc60  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18006dc67  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x18006dc6c  call    _CxxThrowException_0
0x18006dc72  lea     rax, aArchiveFeature; "Archive feature not supported: only sup"...
0x18006dc79  mov     [rsp+160h+var_130], rax; struct win_musl::TStringEllipseBase *
0x18006dc7e  mov     [rsp+160h+var_138], 80511008h; unsigned int
0x18006dc86  mov     [rsp+160h+var_140], 0C5h; unsigned int
0x18006dc8e  lea     r9, word_180139126
0x18006dc95  lea     r8, aNoFilename; "(no filename)"
0x18006dc9c  lea     rcx, [rsp+160h+pExceptionObject]; this
0x18006dca1  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18006dca6  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18006dcad  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x18006dcb2  call    _CxxThrowException_0
0x18006dcb8  sub     ecx, 1
0x18006dcbb  jz      short loc_18006DD15
0x18006dcbd  cmp     ecx, 1
0x18006dcc0  jnz     short loc_18006DD15
0x18006dcc2  or      ecx, 0FFFFFFFFh
0x18006dcc5  cmp     r12d, ecx
0x18006dcc8  jz      short loc_18006DCD1
0x18006dcca  mov     [rdx+98h], r12
0x18006dcd1  cmp     ebx, ecx
0x18006dcd3  jz      short loc_18006DCE0
0x18006dcd5  mov     rax, [rdi+20h]
0x18006dcd9  mov     [rax+90h], rbx
0x18006dce0  mov     edx, 0FFFFh
0x18006dce5  cmp     r15w, dx
0x18006dce9  jz      short loc_18006DCF6
0x18006dceb  mov     rax, [rdi+20h]
0x18006dcef  mov     [rax+88h], r15
0x18006dcf6  cmp     r14w, dx
0x18006dcfa  jz      short loc_18006DD07
0x18006dcfc  mov     rax, [rdi+20h]
0x18006dd00  mov     [rax+0A8h], r14d
0x18006dd07  cmp     si, dx
0x18006dd0a  jz      loc_18006DA84
0x18006dd10  jmp     loc_18006DA7A
0x18006dd15  lea     rax, aInvalidEndOfCe; "invalid end_of_central_directory source"...
0x18006dd1c  mov     [rsp+160h+var_130], rax; struct win_musl::TStringEllipseBase *
0x18006dd21  mov     [rsp+160h+var_138], 8000FFFFh; unsigned int
0x18006dd29  mov     [rsp+160h+var_140], 110h; unsigned int
0x18006dd31  lea     r9, word_180139126
0x18006dd38  lea     r8, aNoFilename; "(no filename)"
0x18006dd3f  lea     rcx, [rsp+160h+pExceptionObject]; this
0x18006dd44  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18006dd49  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18006dd50  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x18006dd55  call    _CxxThrowException_0
0x18006dd5b  lea     rax, WPP_GLOBAL_Control
0x18006dd62  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dd69  cmp     rcx, rax
0x18006dd6c  jz      loc_18006DB70
0x18006dd72  test    byte ptr [rcx+44h], 10h
0x18006dd76  jz      loc_18006DB70
0x18006dd7c  movzx   eax, word ptr [rdi+58h]
0x18006dd80  mov     edx, 0Ch
0x18006dd85  mov     [rsp+160h+var_140], eax
0x18006dd89  mov     r9, [rdi+30h]
0x18006dd8d  lea     r8, WPP_37a605dc7fd83120dddcbd48d857a9dd_Traceguids
0x18006dd94  mov     rcx, [rcx+38h]
0x18006dd98  call    WPP_SF_ID
  ... truncated ...
```
