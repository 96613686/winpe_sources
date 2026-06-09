# DSSCopyFromSharedFile(ushort const *,ushort const *)

- ea: `0x18000ca4c`
- end: `0x18000ceac`
- name: `?DSSCopyFromSharedFile@@YAJPEBG0@Z`
- size: `1120`
- prototype: `__int64 __fastcall(DSUtils *, wchar_t *Str)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180007220`

## callees

- `0x1800041a0`
- `0x180006cb0`
- `0x180006e2c`
- `0x180006f78`
- `0x18000be00`
- `0x18000bf80`
- `0x18000c704`
- `0x18000c728`
- `0x18000c93c`
- `0x18000ca4c`
- `0x18000da68`
- `0x18000ddb8`
- `0x18000dee8`
- `0x18000e674`
- `0x18000f068`
- `0x18000f120`
- `0x18000f1a0`
- `0x1800125c4`
- `0x1800198f8`
- `0x180019e70`
- `0x18001a498`
- `0x18001a6f0`
- `0x18001a7cc`
- `0x18001a93c`
- `0x18001aa74`
- `0x18001ab08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cdbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cdbc`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000cc83`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000cd81`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000cdae`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000cc83`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000cd81`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000cdae`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18000ce4c`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18000ce4c`

## string_xrefs

- `0x18000cbbb`: `The sharer does not authorize read permission on the shared file %d`
- `0x18000cbcc`: `DSSCopyFromSharedFile`
- `0x18000cdf5`: `DSSCopyFromSharedFile`
- `0x18000cde9`: `Failed to copy file for token: %s, sourcefile: %s. hr=0x%x`

## pseudocode

```c
__int64 __fastcall DSSCopyFromSharedFile(DSUtils *a1, wchar_t *Str)
{
  unsigned __int16 *v2; // r14
  wchar_t *v3; // rbx
  const unsigned __int16 *v4; // rdx
  __int64 v5; // rcx
  void *v6; // r8
  void *v7; // r9
  bool v8; // di
  int AuthorizedSharingToken; // esi
  const unsigned __int16 *v10; // rax
  unsigned __int16 **v11; // r8
  DSUtils *v12; // rbx
  unsigned int v13; // eax
  const unsigned __int16 *v14; // rdx
  unsigned int v15; // r8d
  unsigned int v16; // r9d
  int v17; // eax
  utl::_RefCountBase *v18; // r14
  int v19; // esi
  DSLogger *v20; // rax
  unsigned int v21; // eax
  bool v22; // zf
  int v23; // ebx
  void *v24; // r13
  __int64 v25; // r12
  __int64 v26; // r15
  __int64 v27; // r9
  __int64 v28; // rdi
  __int64 v29; // r9
  __int64 v30; // rsi
  __int64 v31; // r9
  __int64 v32; // r14
  __int64 v33; // r8
  __int64 v34; // r9
  DSLogger *v35; // rax
  void *v37; // [rsp+20h] [rbp-79h]
  void *v38; // [rsp+20h] [rbp-79h]
  void **v39; // [rsp+28h] [rbp-71h]
  void **v40; // [rsp+28h] [rbp-71h]
  __int64 v41; // [rsp+30h] [rbp-69h]
  unsigned __int16 *v42; // [rsp+40h] [rbp-59h] BYREF
  HANDLE hFile; // [rsp+48h] [rbp-51h] BYREF
  DSUtils *v44; // [rsp+50h] [rbp-49h] BYREF
  utl::_RefCountBase *v45[2]; // [rsp+58h] [rbp-41h] BYREF
  LPCWSTR lpFileName; // [rsp+68h] [rbp-31h]
  void *v47[4]; // [rsp+70h] [rbp-29h] BYREF
  __int64 v48[12]; // [rsp+90h] [rbp-9h] BYREF
  bool FileInformation; // [rsp+110h] [rbp+77h] BYREF
  void *v52; // [rsp+118h] [rbp+7Fh] BYREF

  v2 = (unsigned __int16 *)a1;
  v42 = (unsigned __int16 *)-1LL;
  v44 = 0;
  hFile = (HANDLE)-1LL;
  *(_OWORD *)v45 = 0;
  v3 = Str;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v48);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v47);
  v8 = 0;
  if ( !dword_18002B2D0 )
  {
    AuthorizedSharingToken = -1055719422;
    goto LABEL_41;
  }
  v10 = (const unsigned __int16 *)tlx::replace<tlx::handle_traits<void *,void * (*)(void *),&void * LocalFree(void *),0>>(&v44);
  AuthorizedSharingToken = DSUtils::CanonicalAndValidateFilePath(v3, v10, v11);
  if ( AuthorizedSharingToken < 0 )
  {
LABEL_41:
    while ( 1 )
    {
      v35 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                          v5,
                          v4,
                          v6,
                          v7);
      LODWORD(v41) = AuthorizedSharingToken;
      DSLogger::LogError(
        v35,
        L"DSSCopyFromSharedFile",
        0x3AFu,
        L"Failed to copy file for token: %s, sourcefile: %s. hr=0x%x",
        v2,
        v3,
        v41);
      if ( !v8 )
        break;
      LODWORD(v52) = 0;
      AuthorizedSharingToken = AutoImpersonate<1>::ImpersonateClient(&v52);
      if ( AuthorizedSharingToken >= 0 )
      {
        FileInformation = 1;
        SetFileInformationByHandle(hFile, FileDispositionInfo, &FileInformation, 1u);
        AutoImpersonate<1>::RevertToSelf(&v52);
        break;
      }
      AutoImpersonate<1>::RevertToSelf(&v52);
    }
  }
  else
  {
    v12 = v44;
    lpFileName = (LPCWSTR)v44;
    LODWORD(v52) = 0;
    AuthorizedSharingToken = AutoImpersonate<1>::ImpersonateClient(&v52);
    if ( AuthorizedSharingToken < 0 )
    {
      AutoImpersonate<1>::RevertToSelf(&v52);
LABEL_40:
      v3 = Str;
      goto LABEL_41;
    }
    v13 = tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),-1>(&hFile);
    v17 = DSUtils::OpenFileAlways(v12, v14, v15, v16, v13, v39);
    AuthorizedSharingToken = 0;
    v8 = v17 == -2147024894;
    if ( v17 != -2147024894 )
      AuthorizedSharingToken = v17;
    FileInformation = v17 == -2147024894;
    AutoImpersonate<1>::RevertToSelf(&v52);
    if ( AuthorizedSharingToken < 0 )
      goto LABEL_40;
    AuthorizedSharingToken = PolicyChecker::CheckFilePermission(v12, 0, (__int64)v47, (__int64)v48);
    if ( AuthorizedSharingToken < 0 )
      goto LABEL_40;
    AuthorizedSharingToken = GetAuthorizedSharingToken(v2);
    if ( AuthorizedSharingToken < 0 )
      goto LABEL_40;
    LODWORD(v52) = 0;
    AuthorizedSharingToken = ValidateUsage(v45, &v52);
    if ( AuthorizedSharingToken < 0 )
      goto LABEL_40;
    v18 = v45[0];
    v19 = *((_DWORD *)v45[0] + 30);
    if ( (v19 & 0xFFFFFFFD) != 0 )
    {
      v20 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                          v5,
                          v4,
                          v6,
                          v7);
      LODWORD(v37) = v19;
      DSLogger::LogError(
        v20,
        L"DSSCopyFromSharedFile",
        0x365u,
        L"The sharer does not authorize read permission on the shared file %d",
        v37);
      AuthorizedSharingToken = -2147024891;
LABEL_39:
      v2 = (unsigned __int16 *)a1;
      goto LABEL_40;
    }
    if ( !*((_QWORD *)v45[0] + 23) )
    {
      AuthorizedSharingToken = -1055719420;
      goto LABEL_39;
    }
    v21 = tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),-1>(&v42);
    AuthorizedSharingToken = DSUtils::OpenFile(
                               *((DSUtils **)v18 + 23),
                               (const unsigned __int16 *)0xC0000000LL,
                               3u,
                               0,
                               v21,
                               v40);
    if ( AuthorizedSharingToken < 0 )
      goto LABEL_39;
    AuthorizedSharingToken = DSUtils::VerifyPathFromHandle(*((wchar_t **)v18 + 23), v42, v6);
    if ( AuthorizedSharingToken < 0 )
      goto LABEL_39;
    AuthorizedSharingToken = DSUtils::VerifyFileIdFromHandle(*((wchar_t **)v18 + 27), v42, v6);
    if ( AuthorizedSharingToken < 0 )
      goto LABEL_39;
    if ( (unsigned int)DSUtils::IsFileEncrypted(*((LPCWSTR *)v18 + 23), v4) )
    {
      LODWORD(v52) = 0;
      AuthorizedSharingToken = AutoImpersonate<2>::ImpersonateCallingUserWithEnterpriseContext(&v52);
      if ( AuthorizedSharingToken < 0 )
      {
        v22 = (_DWORD)v52 == 0;
LABEL_21:
        if ( !v22 && !RevertToSelf() )
          GetLastError();
        goto LABEL_39;
      }
      v23 = (int)v52;
    }
    else
    {
      AuthorizedSharingToken = PolicyChecker::CheckFilePermission(v12, 0, 0, 0);
      if ( AuthorizedSharingToken < 0 )
        goto LABEL_39;
      v23 = 0;
    }
    v52 = 0;
    Common::GlobalHeap::Alloc(0x80u, &v52);
    v7 = v52;
    if ( !v52 )
    {
      AuthorizedSharingToken = -1055719419;
      v22 = v23 == 0;
      goto LABEL_21;
    }
    v24 = v47[0];
    v25 = v48[0];
    v26 = *((_QWORD *)v18 + 23);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v52);
    v28 = v27 + 32;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v27 + 32);
    v30 = v29 + 64;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v29 + 64);
    v32 = v31 + 96;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v31 + 96);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(v34, v33);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(v28, v26);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(v30, v25);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(v32, v24);
    v2 = (unsigned __int16 *)a1;
    AuthorizedSharingToken = DSUtils::CopyFileWithProgress(a1, v42, hFile, v52, v38);
    if ( AuthorizedSharingToken < 0
      || (AuthorizedSharingToken = DSUtils::SetFileAttributesToNormal(lpFileName, v4), AuthorizedSharingToken < 0) )
    {
      if ( v23 && !RevertToSelf() )
        GetLastError();
      v8 = FileInformation;
      goto LABEL_40;
    }
    if ( v23 && !RevertToSelf() )
      GetLastError();
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v47);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v48);
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),-1>::_Delete(&hFile);
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),-1>::_Delete(&v42);
  if ( v45[1] )
    utl::_RefCountBase::_DecStrong(v45[1]);
  tlx::auto_xxx<void *,void * (*)(void *),&void * LocalFree(void *),0>::_Delete(&v44);
  return (unsigned int)AuthorizedSharingToken;
}

```

## disassembly

```asm
0x18000ca4c  mov     [rsp-8+arg_8], rdx
0x18000ca51  mov     [rsp-8+arg_0], rcx
0x18000ca56  push    rbp
0x18000ca57  push    rbx
0x18000ca58  push    rsi
0x18000ca59  push    rdi
0x18000ca5a  push    r12
0x18000ca5c  push    r13
0x18000ca5e  push    r14
0x18000ca60  push    r15
0x18000ca62  lea     rbp, [rsp-1Fh]
0x18000ca67  sub     rsp, 0B8h
0x18000ca6e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ca72  mov     r14, rcx
0x18000ca75  xor     r15d, r15d
0x18000ca78  mov     [rbp+57h+var_B0], rax
0x18000ca7c  xorps   xmm0, xmm0
0x18000ca7f  mov     [rbp+57h+var_A0], r15
0x18000ca83  lea     rcx, [rbp+57h+var_60]
0x18000ca87  mov     [rbp+57h+hFile], rax
0x18000ca8b  movdqu  xmmword ptr [rbp+57h+var_98], xmm0
0x18000ca90  mov     rbx, rdx
0x18000ca93  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18000ca98  lea     rcx, [rbp+57h+var_80]
0x18000ca9c  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18000caa1  cmp     cs:dword_18002B2D0, r15d
0x18000caa8  mov     dil, r15b
0x18000caab  jnz     short loc_18000CAB7
0x18000caad  mov     esi, 0C1130002h
0x18000cab2  jmp     loc_18000CDE0
0x18000cab7  lea     rcx, [rbp+57h+var_A0]
0x18000cabb  call    ??$replace@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,void * (*)(void *),&LocalFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&LocalFree(void *),0>> &)
0x18000cac0  mov     rdx, rax; unsigned __int16 *
0x18000cac3  mov     rcx, rbx; Str
0x18000cac6  call    ?CanonicalAndValidateFilePath@DSUtils@@YAJPEBGPEAPEAG@Z; DSUtils::CanonicalAndValidateFilePath(ushort const *,ushort * *)
0x18000cacb  mov     esi, eax
0x18000cacd  test    eax, eax
0x18000cacf  js      loc_18000CDE0
0x18000cad5  mov     rbx, [rbp+57h+var_A0]
0x18000cad9  lea     rcx, [rbp+57h+arg_18]
0x18000cadd  mov     [rbp+57h+lpFileName], rbx
0x18000cae1  mov     dword ptr [rbp+57h+arg_18], r15d
0x18000cae5  call    ?ImpersonateClient@?$AutoImpersonate@$00@@QEAAJXZ; AutoImpersonate<1>::ImpersonateClient(void)
0x18000caea  mov     esi, eax
0x18000caec  test    eax, eax
0x18000caee  jns     short loc_18000CAFE
0x18000caf0  lea     rcx, [rbp+57h+arg_18]
0x18000caf4  call    ?RevertToSelf@?$AutoImpersonate@$00@@QEAAJXZ; AutoImpersonate<1>::RevertToSelf(void)
0x18000caf9  jmp     loc_18000CDDC
0x18000cafe  lea     rcx, [rbp+57h+hFile]
0x18000cb02  call    ??$replace@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@0@@Z; tlx::replace<void *,int (*)(void *),&CloseHandle(void *),-1>(tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),-1> &)
0x18000cb07  mov     rcx, rbx; this
0x18000cb0a  mov     [rsp+0F0h+var_D0], rax; unsigned int
0x18000cb0f  call    ?OpenFileAlways@DSUtils@@YAJPEBGKKKPEAPEAX@Z; DSUtils::OpenFileAlways(ushort const *,ulong,ulong,ulong,void * *)
0x18000cb14  mov     ecx, 80070002h
0x18000cb19  mov     esi, r15d
0x18000cb1c  cmp     eax, ecx
0x18000cb1e  lea     rcx, [rbp+57h+arg_18]
0x18000cb22  setz    dil
0x18000cb26  cmovnz  esi, eax
0x18000cb29  mov     [rbp+57h+FileInformation], dil
0x18000cb2d  call    ?RevertToSelf@?$AutoImpersonate@$00@@QEAAJXZ; AutoImpersonate<1>::RevertToSelf(void)
0x18000cb32  test    esi, esi
0x18000cb34  js      loc_18000CDDC
0x18000cb3a  mov     r9d, 1
0x18000cb40  lea     rax, [rbp+57h+var_60]
0x18000cb44  mov     [rsp+0F0h+var_C0], rax; __int64
0x18000cb49  mov     edx, r9d
0x18000cb4c  lea     rax, [rbp+57h+var_80]
0x18000cb50  mov     rcx, rbx; this
0x18000cb53  mov     [rsp+0F0h+var_C8], rax; void **
0x18000cb58  lea     r12d, [r9+6]
0x18000cb5c  mov     dword ptr [rsp+0F0h+var_D0], r15d; int
0x18000cb61  mov     r8d, r12d
0x18000cb64  call    ?CheckFilePermission@PolicyChecker@@SAJPEBGW4_DS_SHARE_PERMISSION@@W4_DS_SHARE_MODE@@HHPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@3@Z; PolicyChecker::CheckFilePermission(ushort const *,_DS_SHARE_PERMISSION,_DS_SHARE_MODE,int,int,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x18000cb69  mov     esi, eax
0x18000cb6b  test    eax, eax
0x18000cb6d  js      loc_18000CDDC
0x18000cb73  lea     r8, [rbp+57h+var_98]
0x18000cb77  xor     edx, edx
0x18000cb79  mov     rcx, r14; unsigned __int16 *
0x18000cb7c  call    GetAuthorizedSharingToken
0x18000cb81  mov     esi, eax
0x18000cb83  test    eax, eax
0x18000cb85  js      loc_18000CDDC
0x18000cb8b  lea     rdx, [rbp+57h+arg_18]
0x18000cb8f  mov     dword ptr [rbp+57h+arg_18], r15d
0x18000cb93  lea     rcx, [rbp+57h+var_98]
0x18000cb97  call    ValidateUsage
0x18000cb9c  mov     esi, eax
0x18000cb9e  test    eax, eax
0x18000cba0  js      loc_18000CDDC
0x18000cba6  mov     r14, [rbp+57h+var_98]
0x18000cbaa  mov     esi, [r14+78h]
0x18000cbae  test    esi, 0FFFFFFFDh
0x18000cbb4  jz      short loc_18000CBE5
0x18000cbb6  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000cbbb  lea     r9, aTheSharerDoesN; "The sharer does not authorize read perm"...
0x18000cbc2  mov     dword ptr [rsp+0F0h+var_D0], esi
0x18000cbc6  mov     r8d, 365h; unsigned int
0x18000cbcc  lea     rdx, aDsscopyfromsha_0; "DSSCopyFromSharedFile"
0x18000cbd3  mov     rcx, rax; this
0x18000cbd6  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000cbdb  mov     esi, 80070005h
0x18000cbe0  jmp     loc_18000CDD8
0x18000cbe5  cmp     [r14+0B8h], r15
0x18000cbec  jz      loc_18000CDD3
0x18000cbf2  lea     rcx, [rbp+57h+var_B0]
0x18000cbf6  call    ??$replace@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@0@@Z; tlx::replace<void *,int (*)(void *),&CloseHandle(void *),-1>(tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),-1> &)
0x18000cbfb  mov     rcx, [r14+0B8h]; this
0x18000cc02  xor     r9d, r9d; unsigned int
0x18000cc05  mov     edx, 0C0000000h; unsigned __int16 *
0x18000cc0a  mov     [rsp+0F0h+var_D0], rax; unsigned int
0x18000cc0f  lea     r8d, [r9+3]; unsigned int
0x18000cc13  call    ?OpenFile@DSUtils@@YAJPEBGKKKPEAPEAX@Z; DSUtils::OpenFile(ushort const *,ulong,ulong,ulong,void * *)
0x18000cc18  mov     esi, eax
0x18000cc1a  test    eax, eax
0x18000cc1c  js      loc_18000CDD8
0x18000cc22  mov     rdx, [rbp+57h+var_B0]; unsigned __int16 *
0x18000cc26  mov     rcx, [r14+0B8h]; String2
0x18000cc2d  call    ?VerifyPathFromHandle@DSUtils@@YAJPEBGPEAX@Z; DSUtils::VerifyPathFromHandle(ushort const *,void *)
0x18000cc32  mov     esi, eax
0x18000cc34  test    eax, eax
0x18000cc36  js      loc_18000CDD8
0x18000cc3c  mov     rdx, [rbp+57h+var_B0]; unsigned __int16 *
0x18000cc40  mov     rcx, [r14+0D8h]; String2
0x18000cc47  call    ?VerifyFileIdFromHandle@DSUtils@@YAJPEBGPEAX@Z; DSUtils::VerifyFileIdFromHandle(ushort const *,void *)
0x18000cc4c  mov     esi, eax
0x18000cc4e  test    eax, eax
0x18000cc50  js      loc_18000CDD8
0x18000cc56  mov     rcx, [r14+0B8h]; lpFileName
0x18000cc5d  call    ?IsFileEncrypted@DSUtils@@YAHPEBG@Z; DSUtils::IsFileEncrypted(ushort const *)
0x18000cc62  test    eax, eax
0x18000cc64  jz      short loc_18000CCA1
0x18000cc66  lea     rcx, [rbp+57h+arg_18]
0x18000cc6a  mov     dword ptr [rbp+57h+arg_18], r15d
0x18000cc6e  call    ?ImpersonateCallingUserWithEnterpriseContext@?$AutoImpersonate@$01@@QEAAJXZ; AutoImpersonate<2>::ImpersonateCallingUserWithEnterpriseContext(void)
0x18000cc73  mov     esi, eax
0x18000cc75  test    eax, eax
0x18000cc77  jns     short loc_18000CC9C
0x18000cc79  cmp     dword ptr [rbp+57h+arg_18], r15d
0x18000cc7d  jz      loc_18000CDD8
0x18000cc83  call    cs:__imp_RevertToSelf
0x18000cc89  test    eax, eax
0x18000cc8b  jnz     loc_18000CDD8
0x18000cc91  call    cs:__imp_GetLastError
0x18000cc97  jmp     loc_18000CDD8
0x18000cc9c  mov     ebx, dword ptr [rbp+57h+arg_18]
0x18000cc9f  jmp     short loc_18000CCCF
0x18000cca1  xor     r9d, r9d
0x18000cca4  mov     [rsp+0F0h+var_C0], r15; __int64
0x18000cca9  mov     [rsp+0F0h+var_C8], r15; __int64
0x18000ccae  mov     r8d, r12d
0x18000ccb1  mov     rcx, rbx; this
0x18000ccb4  mov     dword ptr [rsp+0F0h+var_D0], r15d; void *
0x18000ccb9  lea     edx, [r9+1]
0x18000ccbd  call    ?CheckFilePermission@PolicyChecker@@SAJPEBGW4_DS_SHARE_PERMISSION@@W4_DS_SHARE_MODE@@HHPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@3@Z; PolicyChecker::CheckFilePermission(ushort const *,_DS_SHARE_PERMISSION,_DS_SHARE_MODE,int,int,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x18000ccc2  mov     esi, eax
0x18000ccc4  test    eax, eax
0x18000ccc6  js      loc_18000CDD8
0x18000cccc  mov     ebx, r15d
0x18000cccf  lea     rdx, [rbp+57h+arg_18]; void **
0x18000ccd3  mov     [rbp+57h+arg_18], r15
0x18000ccd7  mov     ecx, 80h; unsigned __int64
0x18000ccdc  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x18000cce1  mov     r9, [rbp+57h+arg_18]
0x18000cce5  test    r9, r9
0x18000cce8  jz      loc_18000CDC7
0x18000ccee  mov     r13, [rbp+57h+var_80]
0x18000ccf2  mov     rcx, r9
0x18000ccf5  mov     r12, [rbp+57h+var_60]
0x18000ccf9  mov     r15, [r14+0B8h]
0x18000cd00  mov     r8, [r14+0D8h]
0x18000cd07  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18000cd0c  lea     rdi, [r9+20h]
0x18000cd10  mov     rcx, rdi
0x18000cd13  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18000cd18  lea     rsi, [r9+40h]
0x18000cd1c  mov     rcx, rsi
0x18000cd1f  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18000cd24  lea     r14, [r9+60h]
0x18000cd28  mov     rcx, r14
0x18000cd2b  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18000cd30  mov     rdx, r8
0x18000cd33  mov     rcx, r9
0x18000cd36  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18000cd3b  mov     rdx, r15
0x18000cd3e  mov     rcx, rdi
0x18000cd41  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18000cd46  mov     rdx, r12
0x18000cd49  mov     rcx, rsi
0x18000cd4c  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18000cd51  mov     rdx, r13
0x18000cd54  mov     rcx, r14
0x18000cd57  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18000cd5c  mov     r14, [rbp+57h+arg_0]
0x18000cd60  mov     r9, [rbp+57h+arg_18]; void *
0x18000cd64  mov     rcx, r14; this
0x18000cd67  mov     r8, [rbp+57h+hFile]; void *
0x18000cd6b  mov     rdx, [rbp+57h+var_B0]; unsigned __int16 *
0x18000cd6f  call    ?CopyFileWithProgress@DSUtils@@YAJPEBGPEAX11@Z; DSUtils::CopyFileWithProgress(ushort const *,void *,void *,void *)
0x18000cd74  xor     r15d, r15d
0x18000cd77  mov     esi, eax
0x18000cd79  test    eax, eax
0x18000cd7b  jns     short loc_18000CD97
0x18000cd7d  test    ebx, ebx
0x18000cd7f  jz      short loc_18000CD91
0x18000cd81  call    cs:__imp_RevertToSelf
0x18000cd87  test    eax, eax
0x18000cd89  jnz     short loc_18000CD91
0x18000cd8b  call    cs:__imp_GetLastError
0x18000cd91  mov     dil, [rbp+57h+FileInformation]
0x18000cd95  jmp     short loc_18000CDDC
0x18000cd97  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18000cd9b  call    ?SetFileAttributesToNormal@DSUtils@@YAJPEBG@Z; DSUtils::SetFileAttributesToNormal(ushort const *)
0x18000cda0  mov     esi, eax
0x18000cda2  test    eax, eax
0x18000cda4  js      short loc_18000CD7D
0x18000cda6  test    ebx, ebx
0x18000cda8  jz      loc_18000CE5B
0x18000cdae  call    cs:__imp_RevertToSelf
0x18000cdb4  test    eax, eax
0x18000cdb6  jnz     loc_18000CE5B
0x18000cdbc  call    cs:__imp_GetLastError
0x18000cdc2  jmp     loc_18000CE5B
0x18000cdc7  mov     esi, 0C1130005h
0x18000cdcc  test    ebx, ebx
0x18000cdce  jmp     loc_18000CC7D
0x18000cdd3  mov     esi, 0C1130004h
0x18000cdd8  mov     r14, [rbp+57h+arg_0]
0x18000cddc  mov     rbx, [rbp+57h+arg_8]
0x18000cde0  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000cde5  mov     dword ptr [rsp+0F0h+var_C0], esi
0x18000cde9  lea     r9, aFailedToCopyFi; "Failed to copy file for token: %s, sour"...
0x18000cdf0  mov     [rsp+0F0h+var_C8], rbx
0x18000cdf5  lea     rdx, aDsscopyfromsha_0; "DSSCopyFromSharedFile"
0x18000cdfc  mov     r8d, 3AFh; unsigned int
0x18000ce02  mov     [rsp+0F0h+var_D0], r14
0x18000ce07  mov     rcx, rax; this
0x18000ce0a  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000ce0f  test    dil, dil
0x18000ce12  jz      short loc_18000CE5B
0x18000ce14  test    esi, esi
0x18000ce16  jns     short loc_18000CE5B
0x18000ce18  lea     rcx, [rbp+57h+arg_18]
0x18000ce1c  mov     dword ptr [rbp+57h+arg_18], r15d
0x18000ce20  call    ?ImpersonateClient@?$AutoImpersonate@$00@@QEAAJXZ; AutoImpersonate<1>::ImpersonateClient(void)
0x18000ce25  mov     esi, eax
0x18000ce27  test    eax, eax
0x18000ce29  jns     short loc_18000CE36
0x18000ce2b  lea     rcx, [rbp+57h+arg_18]
0x18000ce2f  call    ?RevertToSelf@?$AutoImpersonate@$00@@QEAAJXZ; AutoImpersonate<1>::RevertToSelf(void)
0x18000ce34  jmp     short loc_18000CDE0
0x18000ce36  mov     rcx, [rbp+57h+hFile]; hFile
0x18000ce3a  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x18000ce3e  mov     r9d, 1; dwBufferSize
0x18000ce44  mov     [rbp+57h+FileInformation], 1
0x18000ce48  lea     edx, [r9+3]; FileInformationClass
0x18000ce4c  call    cs:__imp_SetFileInformationByHandle
0x18000ce52  lea     rcx, [rbp+57h+arg_18]
0x18000ce56  call    ?RevertToSelf@?$AutoImpersonate@$00@@QEAAJXZ; AutoImpersonate<1>::RevertToSelf(void)
0x18000ce5b  lea     rcx, [rbp+57h+var_80]
0x18000ce5f  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000ce64  lea     rcx, [rbp+57h+var_60]
0x18000ce68  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000ce6d  lea     rcx, [rbp+57h+hFile]
0x18000ce71  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),-1>::_Delete(void)
0x18000ce76  lea     rcx, [rbp+57h+var_B0]
0x18000ce7a  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),-1>::_Delete(void)
0x18000ce7f  mov     rcx, [rbp+57h+var_98+8]; this
0x18000ce83  test    rcx, rcx
0x18000ce86  jz      short loc_18000CE8D
0x18000ce88  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18000ce8d  lea     rcx, [rbp+57h+var_A0]
0x18000ce91  call    ?_Delete@?$auto_xxx@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,void * (*)(void *),&LocalFree(void *),0>::_Delete(void)
0x18000ce96  mov     eax, esi
0x18000ce98  add     rsp, 0B8h
0x18000ce9f  pop     r15
0x18000cea1  pop     r14
0x18000cea3  pop     r13
0x18000cea5  pop     r12
0x18000cea7  pop     rdi
0x18000cea8  pop     rsi
0x18000cea9  pop     rbx
0x18000ceaa  pop     rbp
0x18000ceab  retn
```
