# win_musl::consumption::ZipEndOfCentralDirectoryZip64LocatorConsumer::Close(win_musl::ByteReceiverUnique<win_musl::consumption::ZipEndOfCentralDirectoryZip64LocatorConsumer,0,IUnknown> &)

- ea: `0x18006e1e8`
- end: `0x18006e452`
- name: `?Close@ZipEndOfCentralDirectoryZip64LocatorConsumer@consumption@win_musl@@QEAAXAEAV?$ByteReceiverUnique@VZipEndOfCentralDirectoryZip64LocatorConsumer@consumption@win_musl@@$0A@UIUnknown@@@3@@Z`
- size: `618`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006f330`

## callees

- `0x180002f10`
- `0x18002db70`
- `0x18006d010`
- `0x18006df14`
- `0x18006e1e8`
- `0x1800cd6fc`
- `0x180110bcc`
- `0x1801178f0`
- `0x18012a010`

## string_xrefs

- `0x18006e248`: `diskNumberDirectoryStart`
- `0x18006e25e`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipendofcentraldirectoryzip64locatorconsumer.cpp`
- `0x18006e2fa`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipendofcentraldirectoryzip64locatorconsumer.cpp`
- `0x18006e236`: `win_musl::consumption::ZipEndOfCentralDirectoryZip64LocatorConsumer::Close`
- `0x18006e319`: `_context->end_of_central_directory.offsetZip64EndOfCentralDirectory`
- `0x18006e28b`: `Number of the disk with the start of the zip64 end of central directory must be 0 - only support single disk archives.`

## pseudocode

```c
__int64 __fastcall win_musl::consumption::ZipEndOfCentralDirectoryZip64LocatorConsumer::Close(_QWORD *a1)
{
  __int64 v2; // rcx
  __int128 v3; // xmm6
  __int64 v4; // rdx
  __int64 v5; // rax
  __int64 result; // rax
  __int64 v7; // rcx
  _BYTE v8[8]; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v9; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v10; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+78h] [rbp-90h] BYREF

  v2 = a1[7];
  if ( !v2 || a1[8] - v2 != 16 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x87u,
      0x80511001,
      (struct win_musl::TStringEllipseBase *)L"Wrong number of bytes sent");
    throw (SplException::THResultException *)pExceptionObject;
  }
  *(_QWORD *)&v9 = 16;
  *((_QWORD *)&v9 + 1) = v2;
  v10 = v9;
  if ( (unsigned int)win_musl::detail::readThenLog<unsigned int>(
                       (__int64)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipendofc"
                                "entraldirectoryzip64locatorconsumer.cpp",
                       146,
                       (__int64)"win_musl::consumption::ZipEndOfCentralDirectoryZip64LocatorConsumer::Close",
                       (__int64)"diskNumberDirectoryStart",
                       (unsigned int *)&v10,
                       (__int64)&v9) )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x99u,
      0x80511008,
      (struct win_musl::TStringEllipseBase *)L"Number of the disk with the start of the zip64 end of central directory mus"
                                              "t be 0 - only support single disk archives.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v3 = v9;
  v10 = v9;
  v8[0] = 0;
  v4 = win_musl::detail::vector_read<unsigned __int64>(&v10, &v9, v8);
  if ( v8[0] )
  {
    v10 = v3;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipendofcentraldirectoryzip64locatorconsumer.cpp",
      164,
      "win_musl::consumption::ZipEndOfCentralDirectoryZip64LocatorConsumer::Close",
      "_context->end_of_central_directory.offsetZip64EndOfCentralDirectory",
      8,
      &v10);
  }
  v5 = a1[3];
  v10 = v9;
  *(_QWORD *)(v5 + 160) = v4;
  result = win_musl::detail::readThenLog<unsigned int>(
             (__int64)"onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipendofcentraldire"
                      "ctoryzip64locatorconsumer.cpp",
             168,
             (__int64)"win_musl::consumption::ZipEndOfCentralDirectoryZip64LocatorConsumer::Close",
             (__int64)"diskNumberTotal",
             (unsigned int *)&v10,
             (__int64)&v9);
  if ( (_DWORD)result != 1 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0xAEu,
      0x80511008,
      (struct win_musl::TStringEllipseBase *)L"Total number of disks must be 1 - only support single disk archives.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v7 = a1[4];
  if ( v7 )
  {
    if ( dword_1801C4FE0 != -1 )
    {
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 40LL))(v7, a1[5]);
      return win_scope::detail::scope_helper<win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *,win_scope::const_policies<win_scope::types_6<win_scope::close_com,win_scope::convert_normal,win_scope::acquire_com,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_com>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::reset(
               a1 + 4,
               0);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18006e1e8  mov     rax, rsp
0x18006e1eb  mov     [rax+10h], rbx
0x18006e1ef  mov     [rax+18h], rdi
0x18006e1f3  push    rbp
0x18006e1f4  lea     rbp, [rax-38h]
0x18006e1f8  sub     rsp, 130h
0x18006e1ff  movaps  xmmword ptr [rax-18h], xmm6
0x18006e203  mov     rax, cs:__security_cookie
0x18006e20a  xor     rax, rsp
0x18006e20d  mov     [rbp+30h+var_20], rax
0x18006e211  mov     rbx, rcx
0x18006e214  mov     rcx, [rcx+38h]
0x18006e218  test    rcx, rcx
0x18006e21b  jz      loc_18006E40C
0x18006e221  mov     rax, [rbx+40h]
0x18006e225  sub     rax, rcx
0x18006e228  cmp     rax, 10h
0x18006e22c  jnz     loc_18006E40C
0x18006e232  mov     dword ptr [rsp+130h+var_E8+8], eax
0x18006e236  lea     rdi, aWinMuslConsump_5; "win_musl::consumption::ZipEndOfCentralD"...
0x18006e23d  xor     eax, eax
0x18006e23f  mov     qword ptr [rsp+130h+var_D8], rcx
0x18006e244  mov     dword ptr [rsp+130h+var_E8+0Ch], eax
0x18006e248  lea     r9, aDisknumberdire; "diskNumberDirectoryStart"
0x18006e24f  movaps  xmm0, [rsp+130h+var_E8+8]
0x18006e254  lea     rax, [rsp+130h+var_E8+8]
0x18006e259  mov     qword ptr [rsp+130h+var_108], rax
0x18006e25e  lea     rcx, aOnecorePrintsc_9; "onecore\\printscan\\dox\\opc\\zipio_lca"...
0x18006e265  lea     rax, [rsp+130h+var_D8+8]
0x18006e26a  movaps  [rsp+130h+var_E8+8], xmm0
0x18006e26f  mov     r8, rdi
0x18006e272  mov     qword ptr [rsp+130h+var_110], rax
0x18006e277  mov     edx, 92h
0x18006e27c  movdqa  xmmword ptr [rsp+130h+var_D8+8], xmm0
0x18006e282  call    ??$readThenLog@I@detail@win_musl@@YAIPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<uint>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x18006e287  test    eax, eax
0x18006e289  jz      short loc_18006E2D1
0x18006e28b  lea     rax, aNumberOfTheDis; "Number of the disk with the start of th"...
0x18006e292  mov     [rsp+130h+var_100], rax; struct win_musl::TStringEllipseBase *
0x18006e297  lea     r9, word_180139126
0x18006e29e  mov     [rsp+130h+var_108], 80511008h; unsigned int
0x18006e2a6  lea     r8, aNoFilename; "(no filename)"
0x18006e2ad  lea     rcx, [rsp+130h+pExceptionObject]; this
0x18006e2b2  mov     [rsp+130h+var_110], 99h; unsigned int
0x18006e2ba  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18006e2bf  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18006e2c6  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x18006e2cb  call    _CxxThrowException_0
0x18006e2d1  movaps  xmm6, [rsp+130h+var_E8+8]
0x18006e2d6  lea     r8, [rsp+130h+var_F0]
0x18006e2db  lea     rdx, [rsp+130h+var_E8+8]
0x18006e2e0  movdqa  xmmword ptr [rsp+130h+var_D8+8], xmm6
0x18006e2e6  lea     rcx, [rsp+130h+var_D8+8]
0x18006e2eb  mov     [rsp+130h+var_F0], 0
0x18006e2f0  call    ??$vector_read@_K@detail@win_musl@@YA_KU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@PEA_NW4Enum@ByteOrderOption@01@@Z; win_musl::detail::vector_read<unsigned __int64>(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,bool *,win_musl::detail::ByteOrderOption::Enum)
0x18006e2f5  cmp     [rsp+130h+var_F0], 0
0x18006e2fa  lea     rcx, aOnecorePrintsc_9; "onecore\\printscan\\dox\\opc\\zipio_lca"...
0x18006e301  mov     rdx, rax
0x18006e304  mov     r8, rdi
0x18006e307  jz      short loc_18006E333
0x18006e309  lea     rax, [rsp+130h+var_D8+8]
0x18006e30e  movdqa  xmmword ptr [rsp+130h+var_D8+8], xmm6
0x18006e314  mov     qword ptr [rsp+130h+var_108], rax
0x18006e319  lea     r9, aContextEndOfCe; "_context->end_of_central_directory.offs"...
0x18006e320  mov     edx, 0A4h
0x18006e325  mov     [rsp+130h+var_110], 8
0x18006e32d  call    ?ThrowReadError@detail@win_musl@@YAXPEBDK00IU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@@Z; win_musl::detail::ThrowReadError(char const *,ulong,char const *,char const *,uint,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001)
0x18006e333  mov     rax, [rbx+18h]
0x18006e337  lea     r9, aDisknumbertota; "diskNumberTotal"
0x18006e33e  movaps  xmm0, [rsp+130h+var_E8+8]
0x18006e343  movdqa  xmmword ptr [rsp+130h+var_D8+8], xmm0
0x18006e349  mov     [rax+0A0h], rdx
0x18006e350  lea     rax, [rsp+130h+var_E8+8]
0x18006e355  mov     qword ptr [rsp+130h+var_108], rax
0x18006e35a  mov     edx, 0A8h
0x18006e35f  lea     rax, [rsp+130h+var_D8+8]
0x18006e364  mov     qword ptr [rsp+130h+var_110], rax
0x18006e369  call    ??$readThenLog@I@detail@win_musl@@YAIPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<uint>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x18006e36e  cmp     eax, 1
0x18006e371  jz      short loc_18006E3B9
0x18006e373  lea     rax, aTotalNumberOfD; "Total number of disks must be 1 - only "...
0x18006e37a  mov     [rsp+130h+var_100], rax; struct win_musl::TStringEllipseBase *
0x18006e37f  lea     r9, word_180139126
0x18006e386  mov     [rsp+130h+var_108], 80511008h; unsigned int
0x18006e38e  lea     r8, aNoFilename; "(no filename)"
0x18006e395  lea     rcx, [rsp+130h+pExceptionObject]; this
0x18006e39a  mov     [rsp+130h+var_110], 0AEh; unsigned int
0x18006e3a2  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18006e3a7  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18006e3ae  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x18006e3b3  call    _CxxThrowException_0
0x18006e3b9  mov     rcx, [rbx+20h]
0x18006e3bd  test    rcx, rcx
0x18006e3c0  jz      short loc_18006E3E6
0x18006e3c2  cmp     cs:dword_1801C4FE0, 0FFFFFFFFh
0x18006e3c9  jz      short loc_18006E3E6
0x18006e3cb  mov     rax, [rcx]
0x18006e3ce  mov     rdx, [rbx+28h]
0x18006e3d2  mov     rax, [rax+28h]
0x18006e3d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e3db  xor     edx, edx
0x18006e3dd  lea     rcx, [rbx+20h]
0x18006e3e1  call    ?reset@?$scope_helper@PEAV?$ByteReceiverUnique@VZipLocalConsumer@consumption@win_musl@@$00UIUnknown@@@win_musl@@U?$const_policies@U?$types_6@Uclose_com@win_scope@@Uconvert_normal@2@Uacquire_com@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Usafe_types_com@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAV?$ByteReceiverUnique@VZipLocalConsumer@consumption@win_musl@@$00UIUnknown@@@win_musl@@U?$const_policies@U?$types_6@Uclose_com@win_scope@@Uconvert_normal@2@Uacquire_com@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Usafe_types_com@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@3@PEAV?$ByteReceiverUnique@VZipLocalConsumer@consumption@win_musl@@$00UIUnknown@@@win_musl@@@Z; win_scope::detail::scope_helper<win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *,win_scope::const_policies<win_scope::types_6<win_scope::close_com,win_scope::convert_normal,win_scope::acquire_com,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_com>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::reset(win_scope::scope<win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *,win_scope::const_policies<win_scope::types_6<win_scope::close_com,win_scope::convert_normal,win_scope::acquire_com,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_com>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> &,win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *)
0x18006e3e6  mov     rcx, [rbp+30h+var_20]
0x18006e3ea  xor     rcx, rsp; StackCookie
0x18006e3ed  call    __security_check_cookie
0x18006e3f2  lea     r11, [rsp+130h+var_s0]
0x18006e3fa  mov     rbx, [r11+18h]
0x18006e3fe  mov     rdi, [r11+20h]
0x18006e402  movaps  xmm6, xmmword ptr [r11-10h]
0x18006e407  mov     rsp, r11
0x18006e40a  pop     rbp
0x18006e40b  retn
0x18006e40c  lea     rax, aWrongNumberOfB; "Wrong number of bytes sent"
0x18006e413  mov     [rsp+130h+var_100], rax; struct win_musl::TStringEllipseBase *
0x18006e418  lea     r9, word_180139126
0x18006e41f  mov     [rsp+130h+var_108], 80511001h; unsigned int
0x18006e427  lea     r8, aNoFilename; "(no filename)"
0x18006e42e  lea     rcx, [rsp+130h+pExceptionObject]; this
0x18006e433  mov     [rsp+130h+var_110], 87h; unsigned int
0x18006e43b  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18006e440  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18006e447  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x18006e44c  call    _CxxThrowException_0
```
