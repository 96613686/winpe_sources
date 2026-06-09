# DSSCreateSharedFileTokenEx

- ea: `0x18000f740`
- end: `0x18000fbb9`
- name: `DSSCreateSharedFileTokenEx`
- size: `1145`
- prototype: `__int64 __fastcall(__int64, wchar_t *, __int64, int, char, _QWORD *)`
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180007300`

## callees

- `0x180002ac8`
- `0x1800041a0`
- `0x180006cb0`
- `0x180006f78`
- `0x18000be3c`
- `0x18000bf80`
- `0x18000c040`
- `0x18000c65c`
- `0x18000c6d8`
- `0x18000c728`
- `0x18000c758`
- `0x18000c774`
- `0x18000c93c`
- `0x18000e364`
- `0x18000f218`
- `0x18000f384`
- `0x18000f740`
- `0x18000fbd8`
- `0x180011914`
- `0x180011b38`
- `0x180011bdc`
- `0x1800125c4`
- `0x1800129fc`
- `0x180012c70`
- `0x18001384c`
- `0x180013bf0`
- `0x1800163ec`
- `0x1800198f8`
- `0x18001a498`
- `0x18001abbc`
- `0x18001afe8`
- `0x18001b340`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f838`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f838`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000f825`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000f825`

## string_xrefs

- `0x18000f87d`: `Shared filepath %s is invalid!`
- `0x18000f88f`: `DSSCreateSharedFileTokenEx`
- `0x18000fa4d`: `DSSCreateSharedFileTokenEx`
- `0x18000fb2f`: `DSSCreateSharedFileTokenEx`
- `0x18000fa3b`: `Service does not have permission to access file %s`
- `0x18000fb19`: `Failed to create token for file: %s. hr=0x%x`
- `0x18000fa9f`: `SharingTokenManager::AddSharingToken`
- `0x18000f84e`: `Failed to get attributes for filepath %s. hr=0x%x`

## pseudocode

```c
__int64 __fastcall DSSCreateSharedFileTokenEx(__int64 a1, wchar_t *a2, __int64 a3, int a4, char a5, _QWORD *a6)
{
  struct _GUID v6; // xmm0
  int ClientSid; // ebx
  const unsigned __int16 *v10; // rax
  unsigned __int16 **v11; // r8
  WCHAR *v12; // rsi
  DWORD FileAttributesW; // eax
  const unsigned __int16 *v14; // rdx
  DSLogger *v15; // rbx
  signed int LastError; // eax
  DSLogger *v17; // rax
  int IsFileEncrypted; // r12d
  __int64 v19; // rcx
  int v20; // eax
  SharedFileToken *v21; // rax
  SharedFileToken *v22; // rax
  unsigned int *v23; // rdi
  DSLogger *v24; // rax
  _DWORD *v25; // rax
  int v26; // r8d
  unsigned int v27; // r8d
  unsigned int v28; // r9d
  DSLogger *v29; // rax
  const unsigned __int16 *v30; // rax
  const unsigned __int16 **v31; // r8
  PVOID v32; // rax
  DSLogger *v33; // rax
  enum _DS_TOKEN_USAGE_TYPE *v35; // [rsp+20h] [rbp-E0h]
  enum _DS_TOKEN_LIFETIME_TYPE *v36; // [rsp+28h] [rbp-D8h]
  PVOID P; // [rsp+50h] [rbp-B0h] BYREF
  int v38; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v40; // [rsp+70h] [rbp-90h]
  SqmHelper *v41[4]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v42[24]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v43[4]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v44[8]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v45[24]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int16 *v46[4]; // [rsp+F0h] [rbp-10h] BYREF
  DSUtils *v47[4]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v48[32]; // [rsp+130h] [rbp+30h] BYREF
  struct _GUID v49; // [rsp+150h] [rbp+50h] BYREF
  struct _GUID v50; // [rsp+160h] [rbp+60h] BYREF

  v6 = 0;
  v40 = a6;
  v38 = a4;
  v49 = 0;
  lpFileName[0] = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v47);
  P = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v41);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v48);
  *(double *)&v6.Data1 = utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v46);
  v50 = v6;
  ShareAccessControl::ShareAccessControl((ShareAccessControl *)v44);
  utl::list<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::list<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>(v42);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v43);
  if ( !dword_18002B2D0 )
  {
    ClientSid = -1055719422;
    goto LABEL_35;
  }
  v10 = (const unsigned __int16 *)tlx::replace<tlx::handle_traits<void *,void * (*)(void *),&void * LocalFree(void *),0>>(lpFileName);
  ClientSid = DSUtils::CanonicalAndValidateFilePath(a2, v10, v11);
  if ( ClientSid < 0 )
    goto LABEL_35;
  v12 = (WCHAR *)lpFileName[0];
  if ( !lpFileName[0] )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  FileAttributesW = GetFileAttributesW(v12);
  if ( FileAttributesW == -1 )
  {
    v15 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    DSLogger::LogInformation(
      v15,
      L"DSUtils::FileExists",
      0xF6u,
      L"Failed to get attributes for filepath %s. hr=0x%x",
      v12,
      LastError);
    goto LABEL_11;
  }
  if ( (FileAttributesW & 0xA1) == 0 )
  {
LABEL_11:
    v17 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    DSLogger::LogError(v17, L"DSSCreateSharedFileTokenEx", 0x1B7u, L"Shared filepath %s is invalid!", a2);
    ClientSid = -1055719416;
    goto LABEL_35;
  }
  IsFileEncrypted = DSUtils::IsFileEncrypted(v12, v14);
  ClientSid = PolicyChecker::CheckFilePermission((DSUtils *)v12, 1, (__int64)v46, (__int64)v43);
  if ( ClientSid < 0 )
    goto LABEL_35;
  ClientSid = PolicyChecker::GetClientSid(v41);
  if ( ClientSid < 0 )
    goto LABEL_35;
  ClientSid = PolicyChecker::GetProductId((const unsigned __int16 *)v41[0], &v50);
  if ( ClientSid < 0 )
    goto LABEL_35;
  ClientSid = ResolveTargets(v19, (int *)(a3 + 8), (__int64)v42);
  if ( ClientSid < 0 )
    goto LABEL_35;
  ClientSid = ShareAccessControl::Initialize(v44, a3, a3 + 4, v42);
  if ( ClientSid < 0 )
    goto LABEL_35;
  if ( !IsFileEncrypted )
  {
    v20 = PolicyChecker::CheckFilePermission((DSUtils *)v12, 0, 0, 0);
    ClientSid = v20;
    if ( v20 == -2147023636 || v20 == -2147024891 )
    {
      v24 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
      DSLogger::LogError(
        v24,
        L"DSSCreateSharedFileTokenEx",
        0x1E5u,
        L"Service does not have permission to access file %s",
        a2);
      ClientSid = -1055719421;
      goto LABEL_36;
    }
    if ( v20 < 0 )
      goto LABEL_35;
  }
  ClientSid = SharingToken::GenerateTokenId(&v49);
  if ( ClientSid < 0 )
    goto LABEL_35;
  v21 = (SharedFileToken *)operator new(0xF8u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v21 || (v22 = SharedFileToken::SharedFileToken(v21), (v23 = (unsigned int *)v22) == 0) )
  {
    ClientSid = -2147024882;
    goto LABEL_35;
  }
  ClientSid = SharedFileToken::Initialize(
                v22,
                &v49,
                (const unsigned __int16 *)v41[0],
                &v50,
                (const enum _DS_TOKEN_USAGE_TYPE *)&a5,
                (const enum _DS_TOKEN_LIFETIME_TYPE *)&v38,
                (const struct ShareAccessControl *)v44,
                v46[0],
                v12,
                v43[0]);
  if ( ClientSid < 0 )
  {
LABEL_25:
    tlx::_delete<DbEnumFilter>(v23);
    goto LABEL_35;
  }
  v25 = (_DWORD *)tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::get();
  if ( !*v25 )
  {
    ClientSid = -1055719422;
LABEL_30:
    v29 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    LODWORD(v35) = ClientSid;
    DSLogger::LogError(v29, L"SharingTokenManager::AddSharingToken", 0x58u, L"hr=0x%x.", v35);
    goto LABEL_25;
  }
  ClientSid = SharingTokenDatabase::CreateToken((SharingTokenDatabase *)(v25 + 2), (struct SharingToken *)v23, v26);
  if ( ClientSid < 0 )
    goto LABEL_30;
  SqmHelper::LogSqmTokenUsage(v41[0], (const unsigned __int16 *)v23[21], v27, v28);
  tlx::_delete<DbEnumFilter>(v23);
  ClientSid = SharingToken::ConvertTokenIdToString(&v49, v47);
  if ( ClientSid >= 0 )
  {
    v30 = (const unsigned __int16 *)tlx::replace<unsigned short,&void tlx::_delete_array<unsigned short>(unsigned short *)>(&P);
    ClientSid = DSUtils::AssignStringForRpc(v47[0], v30, v31);
    if ( ClientSid >= 0 )
    {
      v32 = P;
      P = 0;
      *v40 = v32;
      goto LABEL_36;
    }
  }
LABEL_35:
  v33 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
  LODWORD(v36) = ClientSid;
  DSLogger::LogError(
    v33,
    L"DSSCreateSharedFileTokenEx",
    0x21Au,
    L"Failed to create token for file: %s. hr=0x%x",
    a2,
    v36);
LABEL_36:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v43);
  utl::list<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::clear(v42);
  utl::list<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::clear(v45);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v46);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v48);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v41);
  if ( P )
    Common::GlobalHeap::Free(P);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v47);
  tlx::auto_xxx<void *,void * (*)(void *),&void * LocalFree(void *),0>::_Delete(lpFileName);
  return (unsigned int)ClientSid;
}

```

## disassembly

```asm
0x18000f740  push    rbp
0x18000f742  push    rbx
0x18000f743  push    rsi
0x18000f744  push    rdi
0x18000f745  push    r12
0x18000f747  push    r13
0x18000f749  push    r14
0x18000f74b  push    r15
0x18000f74d  lea     rbp, [rsp-88h]
0x18000f755  sub     rsp, 188h
0x18000f75c  mov     rax, cs:__security_cookie
0x18000f763  xor     rax, rsp
0x18000f766  mov     [rbp+0C0h+var_50], rax
0x18000f76a  mov     rax, [rbp+0C0h+arg_28]
0x18000f771  mov     r13d, ecx
0x18000f774  xorps   xmm0, xmm0
0x18000f777  mov     [rsp+1C0h+var_150], rax
0x18000f77c  lea     rcx, [rbp+0C0h+var_B0]
0x18000f780  mov     [rsp+1C0h+var_168], r9d
0x18000f785  movups  xmmword ptr [rbp+0C0h+var_70.Data1], xmm0
0x18000f789  mov     rdi, r8
0x18000f78c  mov     [rsp+1C0h+lpFileName], 0
0x18000f795  mov     r15, rdx
0x18000f798  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18000f79d  lea     rcx, [rsp+1C0h+var_148]
0x18000f7a2  mov     [rsp+1C0h+P], 0
0x18000f7ab  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18000f7b0  lea     rcx, [rbp+0C0h+var_90]
0x18000f7b4  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18000f7b9  lea     rcx, [rbp+0C0h+var_D0]
0x18000f7bd  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18000f7c2  lea     rcx, [rbp+0C0h+var_F0]; this
0x18000f7c6  movups  xmmword ptr [rbp+0C0h+var_60.Data1], xmm0
0x18000f7ca  call    ??0ShareAccessControl@@QEAA@XZ; ShareAccessControl::ShareAccessControl(void)
0x18000f7cf  lea     rcx, [rbp+0C0h+var_128]
0x18000f7d3  call    ??0?$list@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAA@XZ; utl::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>(void)
0x18000f7d8  lea     rcx, [rbp+0C0h+var_110]
0x18000f7dc  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18000f7e1  cmp     cs:dword_18002B2D0, 0
0x18000f7e8  jnz     short loc_18000F7F4
0x18000f7ea  mov     ebx, 0C1130002h
0x18000f7ef  jmp     loc_18000FB14
0x18000f7f4  lea     rcx, [rsp+1C0h+lpFileName]
0x18000f7f9  call    ??$replace@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,void * (*)(void *),&LocalFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&LocalFree(void *),0>> &)
0x18000f7fe  mov     rdx, rax; unsigned __int16 *
0x18000f801  mov     rcx, r15; Str
0x18000f804  call    ?CanonicalAndValidateFilePath@DSUtils@@YAJPEBGPEAPEAG@Z; DSUtils::CanonicalAndValidateFilePath(ushort const *,ushort * *)
0x18000f809  mov     ebx, eax
0x18000f80b  test    eax, eax
0x18000f80d  js      loc_18000FB14
0x18000f813  mov     rsi, [rsp+1C0h+lpFileName]
0x18000f818  test    rsi, rsi
0x18000f81b  jnz     short loc_18000F822
0x18000f81d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000f822  mov     rcx, rsi; lpFileName
0x18000f825  call    cs:__imp_GetFileAttributesW
0x18000f82b  cmp     eax, 0FFFFFFFFh
0x18000f82e  jnz     short loc_18000F871
0x18000f830  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000f835  mov     rbx, rax
0x18000f838  call    cs:__imp_GetLastError
0x18000f83e  test    eax, eax
0x18000f840  jle     short loc_18000F84A
0x18000f842  movzx   eax, ax
0x18000f845  or      eax, 80070000h
0x18000f84a  mov     dword ptr [rsp+1C0h+var_198], eax
0x18000f84e  lea     r9, aFailedToGetAtt; "Failed to get attributes for filepath %"...
0x18000f855  mov     r8d, 0F6h; unsigned int
0x18000f85b  mov     [rsp+1C0h+var_1A0], rsi
0x18000f860  lea     rdx, aDsutilsFileexi; "DSUtils::FileExists"
0x18000f867  mov     rcx, rbx; this
0x18000f86a  call    ?LogInformation@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogInformation(ushort const *,ulong,ushort const *,...)
0x18000f86f  jmp     short loc_18000F878
0x18000f871  test    eax, 0A1h
0x18000f876  jnz     short loc_18000F8A8
0x18000f878  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000f87d  lea     r9, aSharedFilepath; "Shared filepath %s is invalid!"
0x18000f884  mov     [rsp+1C0h+var_1A0], r15
0x18000f889  mov     r8d, 1B7h; unsigned int
0x18000f88f  lea     rdx, aDsscreateshare_1; "DSSCreateSharedFileTokenEx"
0x18000f896  mov     rcx, rax; this
0x18000f899  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000f89e  mov     ebx, 0C1130008h
0x18000f8a3  jmp     loc_18000FB14
0x18000f8a8  mov     rcx, rsi; lpFileName
0x18000f8ab  call    ?IsFileEncrypted@DSUtils@@YAHPEBG@Z; DSUtils::IsFileEncrypted(ushort const *)
0x18000f8b0  mov     edx, [rdi]
0x18000f8b2  lea     r14, [rdi+4]
0x18000f8b6  mov     r8d, [r14]
0x18000f8b9  mov     r12d, eax
0x18000f8bc  lea     rax, [rbp+0C0h+var_110]
0x18000f8c0  mov     r9d, r13d
0x18000f8c3  mov     [rsp+1C0h+var_190], rax; __int64
0x18000f8c8  mov     rcx, rsi; this
0x18000f8cb  lea     rax, [rbp+0C0h+var_D0]
0x18000f8cf  mov     [rsp+1C0h+var_198], rax; __int64
0x18000f8d4  mov     dword ptr [rsp+1C0h+var_1A0], 1; int
0x18000f8dc  call    ?CheckFilePermission@PolicyChecker@@SAJPEBGW4_DS_SHARE_PERMISSION@@W4_DS_SHARE_MODE@@HHPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@3@Z; PolicyChecker::CheckFilePermission(ushort const *,_DS_SHARE_PERMISSION,_DS_SHARE_MODE,int,int,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x18000f8e1  mov     ebx, eax
0x18000f8e3  test    eax, eax
0x18000f8e5  js      loc_18000FB14
0x18000f8eb  lea     rcx, [rsp+1C0h+var_148]
0x18000f8f0  call    ?GetClientSid@PolicyChecker@@SAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; PolicyChecker::GetClientSid(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18000f8f5  mov     ebx, eax
0x18000f8f7  test    eax, eax
0x18000f8f9  js      loc_18000FB14
0x18000f8ff  mov     rcx, [rsp+1C0h+var_148]; unsigned __int16 *
0x18000f904  lea     rdx, [rbp+0C0h+var_60]; struct _GUID *
0x18000f908  call    ?GetProductId@PolicyChecker@@SAJPEBGAEAU_GUID@@@Z; PolicyChecker::GetProductId(ushort const *,_GUID &)
0x18000f90d  mov     ebx, eax
0x18000f90f  test    eax, eax
0x18000f911  js      loc_18000FB14
0x18000f917  lea     rdx, [rdi+8]
0x18000f91b  lea     r8, [rbp+0C0h+var_128]
0x18000f91f  call    ResolveTargets
0x18000f924  mov     ebx, eax
0x18000f926  test    eax, eax
0x18000f928  js      loc_18000FB14
0x18000f92e  lea     r9, [rbp+0C0h+var_128]
0x18000f932  mov     r8, r14
0x18000f935  mov     rdx, rdi
0x18000f938  lea     rcx, [rbp+0C0h+var_F0]
0x18000f93c  call    ?Initialize@ShareAccessControl@@QEAAJAEBW4_DS_SHARE_PERMISSION@@AEBW4_DS_SHARE_MODE@@AEBV?$list@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@@Z; ShareAccessControl::Initialize(_DS_SHARE_PERMISSION const &,_DS_SHARE_MODE const &,utl::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>> const &)
0x18000f941  mov     ebx, eax
0x18000f943  test    eax, eax
0x18000f945  js      loc_18000FB14
0x18000f94b  test    r12d, r12d
0x18000f94e  jnz     short loc_18000F997
0x18000f950  mov     r8d, [r14]
0x18000f953  xor     r9d, r9d
0x18000f956  mov     edx, [rdi]
0x18000f958  mov     rcx, rsi; this
0x18000f95b  mov     [rsp+1C0h+var_190], 0; __int64
0x18000f964  mov     [rsp+1C0h+var_198], 0; __int64
0x18000f96d  mov     dword ptr [rsp+1C0h+var_1A0], r12d; int
0x18000f972  call    ?CheckFilePermission@PolicyChecker@@SAJPEBGW4_DS_SHARE_PERMISSION@@W4_DS_SHARE_MODE@@HHPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@3@Z; PolicyChecker::CheckFilePermission(ushort const *,_DS_SHARE_PERMISSION,_DS_SHARE_MODE,int,int,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x18000f977  mov     ebx, eax
0x18000f979  cmp     eax, 800704ECh
0x18000f97e  jz      loc_18000FA36
0x18000f984  cmp     eax, 80070005h
0x18000f989  jz      loc_18000FA36
0x18000f98f  test    eax, eax
0x18000f991  js      loc_18000FB14
0x18000f997  lea     rcx, [rbp+0C0h+var_70]; struct _GUID *
0x18000f99b  call    ?GenerateTokenId@SharingToken@@SAJAEAU_GUID@@@Z; SharingToken::GenerateTokenId(_GUID &)
0x18000f9a0  mov     ebx, eax
0x18000f9a2  test    eax, eax
0x18000f9a4  js      loc_18000FB14
0x18000f9aa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f9b1  mov     ecx, 0F8h; unsigned __int64
0x18000f9b6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000f9bb  test    rax, rax
0x18000f9be  jz      loc_18000FB0F
0x18000f9c4  mov     rcx, rax; this
0x18000f9c7  call    ??0SharedFileToken@@QEAA@XZ; SharedFileToken::SharedFileToken(void)
0x18000f9cc  mov     rdi, rax
0x18000f9cf  test    rax, rax
0x18000f9d2  jz      loc_18000FB0F
0x18000f9d8  mov     rcx, [rbp+0C0h+var_110]
0x18000f9dc  lea     rax, [rbp+0C0h+var_F0]
0x18000f9e0  mov     rdx, [rbp+0C0h+var_D0]
0x18000f9e4  lea     r9, [rbp+0C0h+var_60]; struct _GUID *
0x18000f9e8  mov     r8, [rsp+1C0h+var_148]; unsigned __int16 *
0x18000f9ed  mov     [rsp+1C0h+var_178], rcx; unsigned __int16 *
0x18000f9f2  mov     rcx, rdi; this
0x18000f9f5  mov     [rsp+1C0h+var_180], rsi; unsigned __int16 *
0x18000f9fa  mov     [rsp+1C0h+var_188], rdx; unsigned __int16 *
0x18000f9ff  lea     rdx, [rbp+0C0h+var_70]; struct _GUID *
0x18000fa03  mov     [rsp+1C0h+var_190], rax; struct ShareAccessControl *
0x18000fa08  lea     rax, [rsp+1C0h+var_168]
0x18000fa0d  mov     [rsp+1C0h+var_198], rax; enum _DS_TOKEN_LIFETIME_TYPE *
0x18000fa12  lea     rax, [rbp+0C0h+arg_20]
0x18000fa19  mov     [rsp+1C0h+var_1A0], rax; enum _DS_TOKEN_USAGE_TYPE *
0x18000fa1e  call    ?Initialize@SharedFileToken@@QEAAJAEBU_GUID@@PEBG0AEBW4_DS_TOKEN_USAGE_TYPE@@AEBW4_DS_TOKEN_LIFETIME_TYPE@@AEBVShareAccessControl@@111@Z; SharedFileToken::Initialize(_GUID const &,ushort const *,_GUID const &,_DS_TOKEN_USAGE_TYPE const &,_DS_TOKEN_LIFETIME_TYPE const &,ShareAccessControl const &,ushort const *,ushort const *,ushort const *)
0x18000fa23  mov     ebx, eax
0x18000fa25  test    eax, eax
0x18000fa27  jns     short loc_18000FA66
0x18000fa29  mov     rcx, rdi
0x18000fa2c  call    ??$_delete@VDbEnumFilter@@@tlx@@YAXPEAVDbEnumFilter@@@Z; tlx::_delete<DbEnumFilter>(DbEnumFilter *)
0x18000fa31  jmp     loc_18000FB14
0x18000fa36  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000fa3b  lea     r9, aServiceDoesNot; "Service does not have permission to acc"...
0x18000fa42  mov     [rsp+1C0h+var_1A0], r15
0x18000fa47  mov     r8d, 1E5h; unsigned int
0x18000fa4d  lea     rdx, aDsscreateshare_1; "DSSCreateSharedFileTokenEx"
0x18000fa54  mov     rcx, rax; this
0x18000fa57  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000fa5c  mov     ebx, 0C1130003h
0x18000fa61  jmp     loc_18000FB3E
0x18000fa66  call    ?get@?$_LazyImpl@VSharingTokenManager@@V?$lazy_construct@VSharingTokenManager@@@tlx@@V?$static_lazy@VSharingTokenManager@@$0A@V?$lazy_construct@VSharingTokenManager@@@tlx@@@3@@tlx@@QEAAAEAVSharingTokenManager@@XZ; tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::get(void)
0x18000fa6b  cmp     dword ptr [rax], 0
0x18000fa6e  jnz     short loc_18000FA77
0x18000fa70  mov     ebx, 0C1130002h
0x18000fa75  jmp     short loc_18000FA89
0x18000fa77  lea     rcx, [rax+8]; this
0x18000fa7b  mov     rdx, rdi; struct SharingToken *
0x18000fa7e  call    ?CreateToken@SharingTokenDatabase@@QEAAJPEAVSharingToken@@H@Z; SharingTokenDatabase::CreateToken(SharingToken *,int)
0x18000fa83  mov     ebx, eax
0x18000fa85  test    eax, eax
0x18000fa87  jns     short loc_18000FAB3
0x18000fa89  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000fa8e  lea     r9, aHr0xX; "hr=0x%x."
0x18000fa95  mov     dword ptr [rsp+1C0h+var_1A0], ebx
0x18000fa99  mov     r8d, 58h ; 'X'; unsigned int
0x18000fa9f  lea     rdx, aSharingtokenma_3; "SharingTokenManager::AddSharingToken"
0x18000faa6  mov     rcx, rax; this
0x18000faa9  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000faae  jmp     loc_18000FA29
0x18000fab3  mov     edx, [rdi+54h]; unsigned __int16 *
0x18000fab6  mov     rcx, [rsp+1C0h+var_148]; this
0x18000fabb  call    ?LogSqmTokenUsage@SqmHelper@@YAXPEBGKK@Z; SqmHelper::LogSqmTokenUsage(ushort const *,ulong,ulong)
0x18000fac0  mov     rcx, rdi
0x18000fac3  call    ??$_delete@VDbEnumFilter@@@tlx@@YAXPEAVDbEnumFilter@@@Z; tlx::_delete<DbEnumFilter>(DbEnumFilter *)
0x18000fac8  lea     rdx, [rbp+0C0h+var_B0]
0x18000facc  lea     rcx, [rbp+0C0h+var_70]
0x18000fad0  call    ?ConvertTokenIdToString@SharingToken@@SAJAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; SharingToken::ConvertTokenIdToString(_GUID const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18000fad5  mov     ebx, eax
0x18000fad7  test    eax, eax
0x18000fad9  js      short loc_18000FB14
0x18000fadb  lea     rcx, [rsp+1C0h+P]
0x18000fae0  call    ??$replace@G$1??$_delete_array@G@tlx@@YAXPEAG@Z@tlx@@YAPEAPEAGAEAV?$auto_array_ptr@G$1??$_delete_array@G@tlx@@YAXPEAG@Z@0@@Z; tlx::replace<ushort,&tlx::_delete_array<ushort>(ushort *)>(tlx::auto_array_ptr<ushort,&tlx::_delete_array<ushort>(ushort *)> &)
0x18000fae5  mov     rcx, [rbp+0C0h+var_B0]; this
0x18000fae9  mov     rdx, rax; unsigned __int16 *
0x18000faec  call    ?AssignStringForRpc@DSUtils@@YAJPEBGPEAPEBG@Z; DSUtils::AssignStringForRpc(ushort const *,ushort const * *)
0x18000faf1  mov     ebx, eax
0x18000faf3  test    eax, eax
0x18000faf5  js      short loc_18000FB14
0x18000faf7  mov     rax, [rsp+1C0h+P]
0x18000fafc  mov     rcx, [rsp+1C0h+var_150]
0x18000fb01  mov     [rsp+1C0h+P], 0
0x18000fb0a  mov     [rcx], rax
0x18000fb0d  jmp     short loc_18000FB3E
0x18000fb0f  mov     ebx, 8007000Eh
0x18000fb14  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000fb19  lea     r9, aFailedToCreate_0; "Failed to create token for file: %s. hr"...
0x18000fb20  mov     dword ptr [rsp+1C0h+var_198], ebx
0x18000fb24  mov     r8d, 21Ah; unsigned int
0x18000fb2a  mov     [rsp+1C0h+var_1A0], r15
0x18000fb2f  lea     rdx, aDsscreateshare_1; "DSSCreateSharedFileTokenEx"
0x18000fb36  mov     rcx, rax; this
0x18000fb39  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000fb3e  lea     rcx, [rbp+0C0h+var_110]
0x18000fb42  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000fb47  lea     rcx, [rbp+0C0h+var_128]
0x18000fb4b  call    ?clear@?$list@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAAXXZ; utl::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::clear(void)
0x18000fb50  lea     rcx, [rbp+0C0h+var_E8]
0x18000fb54  call    ?clear@?$list@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAAXXZ; utl::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::clear(void)
0x18000fb59  lea     rcx, [rbp+0C0h+var_D0]
0x18000fb5d  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000fb62  lea     rcx, [rbp+0C0h+var_90]
0x18000fb66  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000fb6b  lea     rcx, [rsp+1C0h+var_148]
0x18000fb70  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000fb75  mov     rcx, [rsp+1C0h+P]; P
0x18000fb7a  test    rcx, rcx
0x18000fb7d  jz      short loc_18000FB84
0x18000fb7f  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18000fb84  lea     rcx, [rbp+0C0h+var_B0]
0x18000fb88  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000fb8d  lea     rcx, [rsp+1C0h+lpFileName]
0x18000fb92  call    ?_Delete@?$auto_xxx@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,void * (*)(void *),&LocalFree(void *),0>::_Delete(void)
0x18000fb97  mov     eax, ebx
0x18000fb99  mov     rcx, [rbp+0C0h+var_50]
0x18000fb9d  xor     rcx, rsp; StackCookie
0x18000fba0  call    __security_check_cookie
0x18000fba5  add     rsp, 188h
0x18000fbac  pop     r15
0x18000fbae  pop     r14
0x18000fbb0  pop     r13
0x18000fbb2  pop     r12
0x18000fbb4  pop     rdi
0x18000fbb5  pop     rsi
0x18000fbb6  pop     rbx
0x18000fbb7  pop     rbp
0x18000fbb8  retn
```
