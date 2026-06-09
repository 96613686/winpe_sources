# CTrustedSignalsVault::SetEnrollment(void *,ushort const *)

- ea: `0x180137e24`
- end: `0x18013829e`
- name: `?SetEnrollment@CTrustedSignalsVault@@SAJPEAXPEBG@Z`
- size: `1146`
- prototype: `__int64 __fastcall(PSID Sid, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801375a8`

## callees

- `0x1800b0ec8`
- `0x1800b86d0`
- `0x1800bfa20`
- `0x1800bfa40`
- `0x180133cf8`
- `0x1801376b4`
- `0x1801378e4`
- `0x18013790c`
- `0x180137944`
- `0x18013798c`
- `0x180137b8c`
- `0x180137e24`
- `0x1801382a4`
- `0x1801382d0`
- `0x1801383e8`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180137f67`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180137f67`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180137ec8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801381e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180138266`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180137ec8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801381e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180138266`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18013805f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18013805f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180137f4d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180137f4d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180138198`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180138198`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultAddItem` at `0x1801380f1`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultAddItem` at `0x1801380f1`

## string_xrefs

- `0x180137ea5`: `onecoreuap\shell\auth\credprovcommon\conveniencelogonenrollment\trustedsignalsvault.cpp`
- `0x180137f09`: `onecoreuap\shell\auth\credprovcommon\conveniencelogonenrollment\trustedsignalsvault.cpp`
- `0x180137f7e`: `onecoreuap\shell\auth\credprovcommon\conveniencelogonenrollment\trustedsignalsvault.cpp`
- `0x180137fd4`: `onecoreuap\shell\auth\credprovcommon\conveniencelogonenrollment\trustedsignalsvault.cpp`
- `0x180138108`: `onecoreuap\shell\auth\credprovcommon\conveniencelogonenrollment\trustedsignalsvault.cpp`
- `0x1801381ba`: `onecoreuap\shell\auth\credprovcommon\conveniencelogonenrollment\trustedsignalsvault.cpp`
- `0x180138223`: `onecoreuap\shell\auth\credprovcommon\conveniencelogonenrollment\trustedsignalsvault.cpp`

## pseudocode

```c
__int64 __fastcall CTrustedSignalsVault::SetEnrollment(PSID Sid, const unsigned __int16 *a2)
{
  __int64 v2; // rbx
  __int64 v3; // r9
  int v5; // edi
  _BYTE *v6; // rcx
  unsigned __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rbx
  const char *v11; // r9
  int LastError; // eax
  __int64 v13; // rbx
  int v14; // eax
  __int64 v15; // rbx
  unsigned int v16; // eax
  __int64 v17; // rbx
  _BYTE *v18; // rax
  __int64 i; // rbx
  BOOL v20; // ebx
  const char *v21; // r9
  unsigned int v22; // ebx
  HLOCAL v23; // rcx
  int v24; // eax
  HLOCAL v25; // rcx
  unsigned int v26; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v28; // [rsp+38h] [rbp-C8h] BYREF
  void *v29; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v30; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME FileTime; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v32[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v33; // [rsp+68h] [rbp-98h]
  int v34; // [rsp+6Ch] [rbp-94h]
  HLOCAL v35; // [rsp+70h] [rbp-90h]
  _QWORD v36[4]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v37; // [rsp+98h] [rbp-68h] BYREF
  __int128 v38; // [rsp+A8h] [rbp-58h]
  _BYTE v39[56]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v40; // [rsp+F0h] [rbp-10h] BYREF
  const wchar_t *v41; // [rsp+100h] [rbp+0h]
  _QWORD *v42; // [rsp+108h] [rbp+8h]
  __int128 *v43; // [rsp+110h] [rbp+10h]
  _QWORD *v44; // [rsp+118h] [rbp+18h]
  __int64 v45; // [rsp+120h] [rbp+20h]
  struct _FILETIME v46; // [rsp+128h] [rbp+28h]
  __int64 v47; // [rsp+130h] [rbp+30h]
  __int64 v48; // [rsp+138h] [rbp+38h]
  struct _SYSTEMTIME SystemTime; // [rsp+140h] [rbp+40h] BYREF
  char v50; // [rsp+150h] [rbp+50h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v50 = 1;
  v2 = -1;
  hMem = 0;
  *(_QWORD *)&SystemTime.wHour = 0;
  v3 = -1;
  *(_QWORD *)&SystemTime.wYear = &hMem;
  do
    ++v3;
  while ( a2[v3] );
  v5 = _AllocStringWorker<CTLocalAllocPolicy>(Sid, a2, a2);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&SystemTime);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecoreuap\\shell\\auth\\credprovcommon\\conveniencelogonenrollment\\trustedsignalsvault.cpp",
      (const char *)(unsigned int)v5,
      v26);
LABEL_5:
    v6 = hMem;
    goto LABEL_6;
  }
  v8 = -1;
  v28 = 0;
  do
    ++v8;
  while ( *((_WORD *)hMem + v8) );
  v9 = ULongLongToULong(v8, &v28);
  v5 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E,
      (unsigned int)"onecoreuap\\shell\\auth\\credprovcommon\\conveniencelogonenrollment\\trustedsignalsvault.cpp",
      (const char *)(unsigned int)v9,
      v26);
    v6 = hMem;
    do
      ++v2;
    while ( *((_WORD *)hMem + v2) );
    v10 = 2 * v2;
    if ( v10 )
    {
      do
      {
        *v6++ = 0;
        --v10;
      }
      while ( v10 );
      goto LABEL_5;
    }
LABEL_6:
    hMem = 0;
    if ( v6 )
      LocalFree(v6);
    return (unsigned int)v5;
  }
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  FileTime = 0;
  if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x64,
                  (unsigned int)"onecoreuap\\shell\\auth\\credprovcommon\\conveniencelogonenrollment\\trustedsignalsvault.cpp",
                  v11);
    v6 = hMem;
    v5 = LastError;
    do
      ++v2;
    while ( *((_WORD *)hMem + v2) );
    v13 = 2 * v2;
    if ( v13 )
    {
      do
      {
        *v6++ = 0;
        --v13;
      }
      while ( v13 );
      goto LABEL_5;
    }
    goto LABEL_6;
  }
  v29 = 0;
  v14 = OpenVault(&v29);
  v5 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecoreuap\\shell\\auth\\credprovcommon\\conveniencelogonenrollment\\trustedsignalsvault.cpp",
      (const char *)(unsigned int)v14,
      v26);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_VaultCloseVault_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v29);
    v6 = hMem;
    do
      ++v2;
    while ( *((_WORD *)hMem + v2) );
    v15 = 2 * v2;
    if ( v15 )
    {
      do
      {
        *v6++ = 0;
        --v15;
      }
      while ( v15 );
      goto LABEL_5;
    }
    goto LABEL_6;
  }
  v36[0] = 1;
  v36[1] = 7;
  v37 = 0;
  LODWORD(v37) = 2;
  DWORD2(v37) = 8;
  v36[3] = 0;
  v36[2] = L"Trusted Signals Vault Resource";
  v38 = 0;
  LODWORD(v38) = GetLengthSid(Sid);
  *((_QWORD *)&v38 + 1) = Sid;
  v32[0] = 3;
  v32[1] = 8;
  v34 = 0;
  v33 = 2 * v28 + 2;
  v35 = hMem;
  v41 = L"Trusted Signals Credential";
  v42 = v36;
  v43 = &v37;
  v44 = v32;
  v46 = FileTime;
  v40 = c_guidTrustedSignalsVaultSchema;
  v45 = 0;
  v47 = 0;
  v48 = 0;
  v16 = VaultAddItem(v29, &v40, 0, 0);
  if ( v16 )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x8A,
           (unsigned int)"onecoreuap\\shell\\auth\\credprovcommon\\conveniencelogonenrollment\\trustedsignalsvault.cpp",
           (const char *)v16,
           0);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_VaultCloseVault_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v29);
    v6 = hMem;
    do
      ++v2;
    while ( *((_WORD *)hMem + v2) );
    v17 = 2 * v2;
    if ( v17 )
    {
      do
      {
        *v6++ = 0;
        --v17;
      }
      while ( v17 );
      goto LABEL_5;
    }
    goto LABEL_6;
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_VaultCloseVault_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v29);
  v18 = hMem;
  do
    ++v2;
  while ( *((_WORD *)hMem + v2) );
  for ( i = 2 * v2; i; --i )
    *v18++ = 0;
  v30 = 0;
  *(_QWORD *)&SystemTime.wYear = &v30;
  *(_QWORD *)&SystemTime.wHour = 0;
  v50 = 1;
  v20 = ConvertSidToStringSidW(Sid, (LPWSTR *)&SystemTime.wHour);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&SystemTime);
  if ( !v20 )
  {
    v22 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x8E,
            (unsigned int)"onecoreuap\\shell\\auth\\credprovcommon\\conveniencelogonenrollment\\trustedsignalsvault.cpp",
            v21);
LABEL_41:
    wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
      &v30,
      0);
    v23 = hMem;
    hMem = 0;
    if ( v23 )
      LocalFree(v23);
    return v22;
  }
  CConvenienceLogonEnrollmentData::CConvenienceLogonEnrollmentData(
    (CConvenienceLogonEnrollmentData *)v39,
    v30,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\TrustedSignals");
  v24 = CConvenienceLogonEnrollmentData::Create((CConvenienceLogonEnrollmentData *)v39);
  v22 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x91,
      (unsigned int)"onecoreuap\\shell\\auth\\credprovcommon\\conveniencelogonenrollment\\trustedsignalsvault.cpp",
      (const char *)(unsigned int)v24,
      0);
    CConvenienceLogonEnrollmentData::~CConvenienceLogonEnrollmentData((CConvenienceLogonEnrollmentData *)v39);
    goto LABEL_41;
  }
  CConvenienceLogonEnrollmentData::~CConvenienceLogonEnrollmentData((CConvenienceLogonEnrollmentData *)v39);
  wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v30, 0);
  v25 = hMem;
  hMem = 0;
  if ( v25 )
    LocalFree(v25);
  return 0;
}

```

## disassembly

```asm
0x180137e24  mov     rax, rsp
0x180137e27  mov     [rax+18h], rbx
0x180137e2b  mov     [rax+20h], rsi
0x180137e2f  push    rbp
0x180137e30  push    rdi
0x180137e31  push    r14
0x180137e33  lea     rbp, [rsp-70h]
0x180137e38  sub     rsp, 170h
0x180137e3f  movaps  xmmword ptr [rax-28h], xmm6
0x180137e43  mov     rax, cs:__security_cookie
0x180137e4a  xor     rax, rsp
0x180137e4d  mov     [rbp+80h+var_28], rax
0x180137e51  xor     r14d, r14d
0x180137e54  mov     [rbp+80h+var_30], 1
0x180137e58  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180137e5c  mov     [rsp+180h+hMem], r14
0x180137e61  lea     rax, [rsp+180h+hMem]
0x180137e66  mov     qword ptr [rbp+80h+SystemTime.wHour], r14
0x180137e6a  mov     r9, rbx
0x180137e6d  mov     qword ptr [rbp+80h+SystemTime.wYear], rax
0x180137e71  mov     rsi, rcx
0x180137e74  inc     r9
0x180137e77  cmp     [rdx+r9*2], r14w
0x180137e7c  jnz     short loc_180137E74
0x180137e7e  lea     rax, [rbp+80h+SystemTime.wHour]
0x180137e82  mov     r8, rdx
0x180137e85  mov     [rsp+180h+var_158], rax
0x180137e8a  call    ??$_AllocStringWorker@VCTLocalAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTLocalAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180137e8f  lea     rcx, [rbp+80h+SystemTime]
0x180137e93  mov     edi, eax
0x180137e95  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180137e9a  test    edi, edi
0x180137e9c  jns     short loc_180137EDB
0x180137e9e  mov     rcx, [rbp+88h]; this
0x180137ea5  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\auth\\credprovcommon"...
0x180137eac  mov     r9d, edi; char *
0x180137eaf  mov     edx, 55h ; 'U'; void *
0x180137eb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137eb9  mov     rcx, [rsp+180h+hMem]; hMem
0x180137ebe  mov     [rsp+180h+hMem], r14
0x180137ec3  test    rcx, rcx
0x180137ec6  jz      short loc_180137ED4
0x180137ec8  call    cs:__imp_LocalFree
0x180137ecf  nop     dword ptr [rax+rax+00h]
0x180137ed4  mov     eax, edi
0x180137ed6  jmp     loc_180138274
0x180137edb  mov     rax, [rsp+180h+hMem]
0x180137ee0  mov     rcx, rbx
0x180137ee3  mov     [rsp+180h+var_148], r14d
0x180137ee8  inc     rcx; unsigned __int64
0x180137eeb  cmp     [rax+rcx*2], r14w
0x180137ef0  jnz     short loc_180137EE8
0x180137ef2  lea     rdx, [rsp+180h+var_148]; unsigned int *
0x180137ef7  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180137efc  mov     edi, eax
0x180137efe  test    eax, eax
0x180137f00  jns     short loc_180137F42
0x180137f02  mov     rcx, [rbp+88h]; this
0x180137f09  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\auth\\credprovcommon"...
0x180137f10  mov     r9d, eax; char *
0x180137f13  mov     edx, 5Eh ; '^'; void *
0x180137f18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137f1d  mov     rcx, [rsp+180h+hMem]
0x180137f22  inc     rbx
0x180137f25  cmp     [rcx+rbx*2], r14w
0x180137f2a  jnz     short loc_180137F22
0x180137f2c  add     rbx, rbx
0x180137f2f  jz      short loc_180137EBE
0x180137f31  mov     [rcx], r14b
0x180137f34  inc     rcx
0x180137f37  sub     rbx, 1
0x180137f3b  jnz     short loc_180137F31
0x180137f3d  jmp     loc_180137EB9
0x180137f42  xorps   xmm0, xmm0
0x180137f45  lea     rcx, [rbp+80h+SystemTime]; lpSystemTime
0x180137f49  movups  xmmword ptr [rbp+80h+SystemTime.wYear], xmm0
0x180137f4d  call    cs:__imp_GetSystemTime
0x180137f54  nop     dword ptr [rax+rax+00h]
0x180137f59  lea     rdx, [rsp+180h+FileTime]; lpFileTime
0x180137f5e  mov     qword ptr [rsp+180h+FileTime.dwLowDateTime], r14
0x180137f63  lea     rcx, [rbp+80h+SystemTime]; lpSystemTime
0x180137f67  call    cs:__imp_SystemTimeToFileTime
0x180137f6e  nop     dword ptr [rax+rax+00h]
0x180137f73  test    eax, eax
0x180137f75  jnz     short loc_180137FB8
0x180137f77  mov     rcx, [rbp+88h]; this
0x180137f7e  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\auth\\credprovcommon"...
0x180137f85  lea     edx, [rax+64h]; void *
0x180137f88  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180137f8d  mov     rcx, [rsp+180h+hMem]
0x180137f92  mov     edi, eax
0x180137f94  inc     rbx
0x180137f97  cmp     [rcx+rbx*2], r14w
0x180137f9c  jnz     short loc_180137F94
0x180137f9e  add     rbx, rbx
0x180137fa1  jz      loc_180137EBE
0x180137fa7  mov     [rcx], r14b
0x180137faa  inc     rcx
0x180137fad  sub     rbx, 1
0x180137fb1  jnz     short loc_180137FA7
0x180137fb3  jmp     loc_180137EB9
0x180137fb8  lea     rcx, [rsp+180h+var_140]; void **
0x180137fbd  mov     [rsp+180h+var_140], r14
0x180137fc2  call    ?OpenVault@@YAJPEAPEAX@Z; OpenVault(void * *)
0x180137fc7  mov     edi, eax
0x180137fc9  test    eax, eax
0x180137fcb  jns     short loc_18013801B
0x180137fcd  mov     rcx, [rbp+88h]; this
0x180137fd4  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\auth\\credprovcommon"...
0x180137fdb  mov     r9d, eax; char *
0x180137fde  mov     edx, 67h ; 'g'; void *
0x180137fe3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137fe8  lea     rcx, [rsp+180h+var_140]
0x180137fed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?VaultCloseVault@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180137ff2  mov     rcx, [rsp+180h+hMem]
0x180137ff7  inc     rbx
0x180137ffa  cmp     [rcx+rbx*2], r14w
0x180137fff  jnz     short loc_180137FF7
0x180138001  add     rbx, rbx
0x180138004  jz      loc_180137EBE
0x18013800a  mov     [rcx], r14b
0x18013800d  inc     rcx
0x180138010  sub     rbx, 1
0x180138014  jnz     short loc_18013800A
0x180138016  jmp     loc_180137EB9
0x18013801b  movups  xmm6, cs:c_guidTrustedSignalsVaultSchema
0x180138022  mov     [rsp+180h+var_108], 1
0x18013802b  lea     rax, aTrustedSignals_1; "Trusted Signals Vault Resource"
0x180138032  xorps   xmm0, xmm0
0x180138035  mov     [rbp+80h+var_100], 7
0x18013803d  movups  [rbp+80h+var_E8], xmm0
0x180138041  mov     edi, 8
0x180138046  mov     dword ptr [rbp+80h+var_E8], 2
0x18013804d  mov     rcx, rsi; pSid
0x180138050  mov     dword ptr [rbp+80h+var_E8+8], edi
0x180138053  mov     [rbp+80h+var_F0], r14
0x180138057  mov     [rbp+80h+var_F8], rax
0x18013805b  movups  [rbp+80h+var_D8], xmm0
0x18013805f  call    cs:__imp_GetLengthSid
0x180138066  nop     dword ptr [rax+rax+00h]
0x18013806b  mov     rcx, [rsp+180h+var_140]
0x180138070  lea     rdx, [rbp+80h+var_90]
0x180138074  mov     dword ptr [rbp+80h+var_D8], eax
0x180138077  xor     r9d, r9d
0x18013807a  mov     eax, [rsp+180h+var_148]
0x18013807e  xor     r8d, r8d
0x180138081  mov     qword ptr [rbp+80h+var_D8+8], rsi
0x180138085  mov     [rsp+180h+var_128], 3
0x18013808e  mov     [rsp+180h+var_120], rdi
0x180138093  lea     eax, ds:2[rax*2]
0x18013809a  mov     [rsp+180h+var_114], r14d
0x18013809f  mov     [rsp+180h+var_118], eax
0x1801380a3  mov     rax, [rsp+180h+hMem]
0x1801380a8  mov     [rsp+180h+var_110], rax
0x1801380ad  lea     rax, aTrustedSignals_0; "Trusted Signals Credential"
0x1801380b4  mov     [rbp+80h+var_80], rax
0x1801380b8  lea     rax, [rsp+180h+var_108]
0x1801380bd  mov     [rbp+80h+var_78], rax
0x1801380c1  lea     rax, [rbp+80h+var_E8]
0x1801380c5  mov     [rbp+80h+var_70], rax
0x1801380c9  lea     rax, [rsp+180h+var_128]
0x1801380ce  mov     [rbp+80h+var_68], rax
0x1801380d2  mov     rax, qword ptr [rsp+180h+FileTime.dwLowDateTime]
0x1801380d7  mov     [rbp+80h+var_58], rax
0x1801380db  movdqu  [rbp+80h+var_90], xmm6
0x1801380e0  mov     [rbp+80h+var_60], r14
0x1801380e4  mov     [rbp+80h+var_50], r14
0x1801380e8  mov     [rbp+80h+var_48], r14
0x1801380ec  mov     [rsp+180h+var_160], r14d; int
0x1801380f1  call    cs:__imp_VaultAddItem
0x1801380f8  nop     dword ptr [rax+rax+00h]
0x1801380fd  test    eax, eax
0x1801380ff  jz      short loc_180138151
0x180138101  mov     rcx, [rbp+88h]; this
0x180138108  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\auth\\credprovcommon"...
0x18013810f  mov     r9d, eax; char *
0x180138112  mov     edx, 8Ah; void *
0x180138117  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18013811c  lea     rcx, [rsp+180h+var_140]
0x180138121  mov     edi, eax
0x180138123  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?VaultCloseVault@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180138128  mov     rcx, [rsp+180h+hMem]
0x18013812d  inc     rbx
0x180138130  cmp     [rcx+rbx*2], r14w
0x180138135  jnz     short loc_18013812D
0x180138137  add     rbx, rbx
0x18013813a  jz      loc_180137EBE
0x180138140  mov     [rcx], r14b
0x180138143  inc     rcx
0x180138146  sub     rbx, 1
0x18013814a  jnz     short loc_180138140
0x18013814c  jmp     loc_180137EB9
0x180138151  lea     rcx, [rsp+180h+var_140]
0x180138156  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?VaultCloseVault@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18013815b  mov     rax, [rsp+180h+hMem]
0x180138160  inc     rbx
0x180138163  cmp     [rax+rbx*2], r14w
0x180138168  jnz     short loc_180138160
0x18013816a  add     rbx, rbx
0x18013816d  jz      short loc_18013817B
0x18013816f  mov     [rax], r14b
0x180138172  inc     rax
0x180138175  sub     rbx, 1
0x180138179  jnz     short loc_18013816F
0x18013817b  lea     rax, [rsp+180h+var_138]
0x180138180  mov     [rsp+180h+var_138], r14
0x180138185  lea     rdx, [rbp+80h+SystemTime.wHour]; StringSid
0x180138189  mov     qword ptr [rbp+80h+SystemTime.wYear], rax
0x18013818d  mov     rcx, rsi; Sid
0x180138190  mov     qword ptr [rbp+80h+SystemTime.wHour], r14
0x180138194  mov     [rbp+80h+var_30], 1
0x180138198  call    cs:__imp_ConvertSidToStringSidW
0x18013819f  nop     dword ptr [rax+rax+00h]
0x1801381a4  lea     rcx, [rbp+80h+SystemTime]
0x1801381a8  mov     ebx, eax
0x1801381aa  call    ??1?$out_param_t@V?$unique_ptr@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1801381af  test    ebx, ebx
0x1801381b1  jnz     short loc_1801381F8
0x1801381b3  mov     rcx, [rbp+88h]; this
0x1801381ba  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\auth\\credprovcommon"...
0x1801381c1  mov     edx, 8Eh; void *
0x1801381c6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801381cb  mov     ebx, eax
0x1801381cd  xor     edx, edx
0x1801381cf  lea     rcx, [rsp+180h+var_138]
0x1801381d4  call    ?reset@?$unique_ptr@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAG@Z; wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(ushort *)
0x1801381d9  mov     rcx, [rsp+180h+hMem]; hMem
0x1801381de  mov     [rsp+180h+hMem], r14
0x1801381e3  test    rcx, rcx
0x1801381e6  jz      short loc_1801381F4
0x1801381e8  call    cs:__imp_LocalFree
0x1801381ef  nop     dword ptr [rax+rax+00h]
0x1801381f4  mov     eax, ebx
0x1801381f6  jmp     short loc_180138274
0x1801381f8  mov     rdx, [rsp+180h+var_138]; unsigned __int16 *
0x1801381fd  lea     r8, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180138204  lea     rcx, [rbp+80h+var_C8]; this
0x180138208  call    ??0CConvenienceLogonEnrollmentData@@QEAA@PEBG0@Z; CConvenienceLogonEnrollmentData::CConvenienceLogonEnrollmentData(ushort const *,ushort const *)
0x18013820d  lea     rcx, [rbp+80h+var_C8]; this
0x180138211  call    ?Create@CConvenienceLogonEnrollmentData@@QEAAJXZ; CConvenienceLogonEnrollmentData::Create(void)
0x180138216  mov     ebx, eax
0x180138218  test    eax, eax
0x18013821a  jns     short loc_180138242
0x18013821c  mov     rcx, [rbp+88h]; this
0x180138223  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\auth\\credprovcommon"...
0x18013822a  mov     r9d, eax; char *
0x18013822d  mov     edx, 91h; void *
0x180138232  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180138237  lea     rcx, [rbp+80h+var_C8]; this
0x18013823b  call    ??1CConvenienceLogonEnrollmentData@@UEAA@XZ; CConvenienceLogonEnrollmentData::~CConvenienceLogonEnrollmentData(void)
0x180138240  jmp     short loc_1801381CD
0x180138242  lea     rcx, [rbp+80h+var_C8]; this
0x180138246  call    ??1CConvenienceLogonEnrollmentData@@UEAA@XZ; CConvenienceLogonEnrollmentData::~CConvenienceLogonEnrollmentData(void)
0x18013824b  xor     edx, edx
0x18013824d  lea     rcx, [rsp+180h+var_138]
0x180138252  call    ?reset@?$unique_ptr@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAG@Z; wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(ushort *)
0x180138257  mov     rcx, [rsp+180h+hMem]; hMem
0x18013825c  mov     [rsp+180h+hMem], r14
0x180138261  test    rcx, rcx
0x180138264  jz      short loc_180138272
0x180138266  call    cs:__imp_LocalFree
0x18013826d  nop     dword ptr [rax+rax+00h]
0x180138272  xor     eax, eax
0x180138274  mov     rcx, [rbp+80h+var_28]
0x180138278  xor     rcx, rsp; StackCookie
0x18013827b  call    __security_check_cookie
0x180138280  lea     r11, [rsp+180h+var_10]
0x180138288  mov     rbx, [r11+30h]
0x18013828c  mov     rsi, [r11+38h]
0x180138290  movaps  xmm6, xmmword ptr [r11-10h]
0x180138295  mov     rsp, r11
0x180138298  pop     r14
0x18013829a  pop     rdi
0x18013829b  pop     rbp
0x18013829c  retn
```
