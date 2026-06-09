# CdplIntIsAppInitiatedProtectionAllowed(ushort const *,ulong,bool *)

- ea: `0x1800d2b2c`
- end: `0x1800d304c`
- name: `?CdplIntIsAppInitiatedProtectionAllowed@@YAJPEBGKPEA_N@Z`
- size: `1312`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned int, bool *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001268c`

## callees

- `0x180001a7c`
- `0x180002874`
- `0x180005045`
- `0x18000b10c`
- `0x18000b12c`
- `0x18000dc8c`
- `0x18000ef44`
- `0x1800233d4`
- `0x180045f68`
- `0x1800d24a4`
- `0x1800d2ab8`
- `0x1800d2ad8`
- `0x1800d2b2c`
- `0x1800d30f0`
- `0x1800d3bb8`
- `0x1800dddf0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800d2e8d`
- `msvcrt!_wcsnicmp` at `0x1800d2eb8`
- `msvcrt!_wcsnicmp` at `0x1800d2eed`
- `msvcrt!_wcsnicmp` at `0x1800d2e8d`
- `msvcrt!_wcsnicmp` at `0x1800d2eb8`
- `msvcrt!_wcsnicmp` at `0x1800d2eed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d2dc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d2dc1`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800d2b86`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800d2c30`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800d2b86`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800d2c30`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800d2c5b`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800d2c5b`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x1800d2d18`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x1800d2d18`
- `ntdll!RtlQueryPackageClaims` at `0x1800d2cec`
- `ntdll!RtlQueryPackageClaims` at `0x1800d2cec`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x1800d2d4c`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x1800d2d4c`
- `api-ms-win-appmodel-state-l1-2-0!GetStateRootFolder` at `0x1800d2d95`
- `api-ms-win-appmodel-state-l1-2-0!GetStateRootFolder` at `0x1800d2e39`
- `api-ms-win-appmodel-state-l1-2-0!GetStateRootFolder` at `0x1800d2d95`
- `api-ms-win-appmodel-state-l1-2-0!GetStateRootFolder` at `0x1800d2e39`

## string_xrefs

- `0x1800d2b97`: `onecoreuap\ds\security\efs\edpprotectiontypelib\edpprotectiontypelib.cpp`
- `0x1800d2bc5`: `onecoreuap\ds\security\efs\edpprotectiontypelib\edpprotectiontypelib.cpp`
- `0x1800d2c02`: `onecoreuap\ds\security\efs\edpprotectiontypelib\edpprotectiontypelib.cpp`
- `0x1800d2c41`: `onecoreuap\ds\security\efs\edpprotectiontypelib\edpprotectiontypelib.cpp`
- `0x1800d2d2c`: `onecoreuap\ds\security\efs\edpprotectiontypelib\edpprotectiontypelib.cpp`
- `0x1800d2d62`: `onecoreuap\ds\security\efs\edpprotectiontypelib\edpprotectiontypelib.cpp`
- `0x1800d2da9`: `onecoreuap\ds\security\efs\edpprotectiontypelib\edpprotectiontypelib.cpp`
- `0x1800d2e0e`: `onecoreuap\ds\security\efs\edpprotectiontypelib\edpprotectiontypelib.cpp`
- `0x1800d2e4a`: `onecoreuap\ds\security\efs\edpprotectiontypelib\edpprotectiontypelib.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CdplIntIsAppInitiatedProtectionAllowed(WCHAR *lpFileName, int a2, bool *a3)
{
  const WCHAR *v4; // rdi
  DWORD FullPathNameW; // eax
  const char *v6; // r9
  unsigned int LastError; // ebx
  DWORD v8; // ebx
  WCHAR *v9; // r14
  __int64 v10; // rdx
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  DWORD v13; // eax
  const char *v14; // r9
  int v15; // eax
  HRESULT v16; // eax
  __int64 v17; // rsi
  unsigned int v18; // eax
  __int64 v19; // rax
  const char *v20; // r9
  __int64 v21; // rbx
  __int64 v22; // rdx
  __int64 v23; // rdx
  unsigned int v24; // ecx
  wchar_t *v25; // r13
  __int64 v26; // rdx
  const char *v27; // r9
  bool v28; // r12
  __int64 v29; // rsi
  int v30; // edi
  wchar_t *v31; // rax
  unsigned int v32; // ebx
  int v33; // eax
  const wchar_t *v34; // rdx
  size_t v35; // r8
  size_t v36; // rax
  bool v37; // bl
  int IsFilePathOnRemovableVolume; // eax
  const struct _tlgProvider_t *v39; // rax
  __int64 v40; // rdx
  const struct _tlgProvider_t *v41; // r8
  int v42; // r9d
  __int64 v43; // rdx
  int v45; // [rsp+20h] [rbp-E0h]
  bool v46; // [rsp+40h] [rbp-C0h] BYREF
  bool v47; // [rsp+41h] [rbp-BFh] BYREF
  _DWORD MaxCount[3]; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v49; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *String1; // [rsp+58h] [rbp-A8h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+60h] [rbp-A0h] BYREF
  int v52; // [rsp+64h] [rbp-9Ch]
  wchar_t *v53; // [rsp+68h] [rbp-98h] BYREF
  WCHAR *v54; // [rsp+70h] [rbp-90h] BYREF
  __int64 v55; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v56[336]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t packageFullName[14]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v58[228]; // [rsp+1ECh] [rbp+ECh] BYREF
  WCHAR packageFamilyName[72]; // [rsp+2D0h] [rbp+1D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+2A8h]

  v52 = a2;
  v4 = lpFileName;
  v54 = lpFileName;
  *a3 = 0;
  EfsTelemetry::GetDplIsAllowedStatus::GetDplIsAllowedStatus((EfsTelemetry::GetDplIsAllowedStatus *)v56);
  FullPathNameW = GetFullPathNameW(v4, 0, 0, 0);
  if ( !FullPathNameW )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xDC,
                  (unsigned int)"onecoreuap\\ds\\security\\efs\\edpprotectiontypelib\\edpprotectiontypelib.cpp",
                  v6);
    goto LABEL_59;
  }
  v8 = FullPathNameW + 1;
  if ( FullPathNameW + 1 < FullPathNameW )
  {
    LastError = -2147024362;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDE,
      (unsigned int)"onecoreuap\\ds\\security\\efs\\edpprotectiontypelib\\edpprotectiontypelib.cpp",
      (const char *)0x80070216LL,
      v45);
    goto LABEL_59;
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &MaxCount[1],
    0,
    v8);
  v9 = *(WCHAR **)&MaxCount[1];
  if ( !*(_QWORD *)&MaxCount[1] )
  {
    LastError = -2147024882;
    v10 = 224;
LABEL_7:
    v11 = LastError;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\ds\\security\\efs\\edpprotectiontypelib\\edpprotectiontypelib.cpp",
      (const char *)v11,
      v45);
LABEL_9:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(
      &MaxCount[1],
      v12);
    goto LABEL_59;
  }
  v13 = GetFullPathNameW(v4, v8, *(LPWSTR *)&MaxCount[1], 0);
  if ( !v13 )
  {
    v15 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0xE2,
            (unsigned int)"onecoreuap\\ds\\security\\efs\\edpprotectiontypelib\\edpprotectiontypelib.cpp",
            v14);
LABEL_12:
    LastError = v15;
    goto LABEL_9;
  }
  v16 = PathCchRemoveFileSpec(v9, v13);
  LastError = v16;
  if ( v16 < 0 )
  {
    v11 = (unsigned int)v16;
    v10 = 230;
    goto LABEL_8;
  }
  v17 = -1;
  do
    ++v17;
  while ( v9[v17] );
  *(_DWORD *)&v9[v17] = 92;
  wcscpy(packageFullName, L"<NoPkageId>");
  memset_0(v58, 0, sizeof(v58));
  v55 = 256;
  v45 = 0;
  if ( (unsigned int)RtlQueryPackageClaims(-6, packageFullName, &v55) == -1073741275 )
  {
LABEL_50:
    v47 = 0;
    v46 = 0;
    IsFilePathOnRemovableVolume = EfsIsFilePathOnRemovableVolume(v4, 0, &v47, &v46);
    LastError = IsFilePathOnRemovableVolume;
    if ( IsFilePathOnRemovableVolume < 0 )
    {
      v11 = (unsigned int)IsFilePathOnRemovableVolume;
      v10 = 330;
      goto LABEL_8;
    }
    if ( v47 )
    {
      LastError = -2147024809;
      v10 = 331;
      goto LABEL_7;
    }
    v37 = !v46;
    goto LABEL_55;
  }
  packageFamilyNameLength = 65;
  v18 = PackageFamilyNameFromFullName(packageFullName, &packageFamilyNameLength, packageFamilyName);
  if ( v18 )
  {
    v15 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xFC,
            (unsigned int)"onecoreuap\\ds\\security\\efs\\edpprotectiontypelib\\edpprotectiontypelib.cpp",
            (const char *)v18,
            0);
    goto LABEL_12;
  }
  v19 = OpenStateExplicit(-6, packageFamilyName);
  v21 = v19;
  v49 = v19;
  if ( !v19 )
  {
    v22 = 256;
LABEL_22:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v22,
                  (unsigned int)"onecoreuap\\ds\\security\\efs\\edpprotectiontypelib\\edpprotectiontypelib.cpp",
                  v20);
LABEL_23:
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v49);
    goto LABEL_9;
  }
  MaxCount[0] = 0;
  if ( (unsigned int)GetStateRootFolder(v19, 0, MaxCount) )
  {
    LastError = -2147418113;
    v23 = 258;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecoreuap\\ds\\security\\efs\\edpprotectiontypelib\\edpprotectiontypelib.cpp",
      (const char *)LastError,
      0);
    goto LABEL_23;
  }
  if ( GetLastError() != 122 )
  {
    v22 = 259;
    goto LABEL_22;
  }
  v24 = MaxCount[0] + 1;
  if ( (unsigned int)(MaxCount[0] + 1) < MaxCount[0] )
  {
    MaxCount[0] = -1;
    LastError = -2147024362;
    v23 = 268;
    goto LABEL_26;
  }
  ++MaxCount[0];
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &String1,
    0,
    v24);
  v25 = String1;
  if ( !String1 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10E,
      (unsigned int)"onecoreuap\\ds\\security\\efs\\edpprotectiontypelib\\edpprotectiontypelib.cpp",
      (const char *)0x8007000ELL,
      0);
LABEL_32:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(
      &String1,
      v26);
    goto LABEL_23;
  }
  if ( !(unsigned int)GetStateRootFolder(v21, String1, MaxCount) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x10F,
                  (unsigned int)"onecoreuap\\ds\\security\\efs\\edpprotectiontypelib\\edpprotectiontypelib.cpp",
                  v27);
    goto LABEL_32;
  }
  v28 = 0;
  v29 = v17 + 1;
  v25[MaxCount[0] - 1] = 92;
  v25[MaxCount[0]] = 0;
  v30 = _wcsnicmp(v9, L"\\\\?\\", 4u);
  v31 = v9 + 4;
  if ( v30 )
    v31 = v9;
  v53 = v31;
  v32 = MaxCount[0];
  v33 = _wcsnicmp(v25, L"\\\\?\\", 4u);
  v34 = v25 + 4;
  if ( v33 )
    v34 = v25;
  v35 = v32 - 4;
  if ( v33 )
    v35 = v32;
  v36 = v29 - 4;
  if ( v30 )
    v36 = v29;
  v37 = 1;
  if ( v36 >= v35 )
    v28 = _wcsnicmp(v53, v34, v35) == 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(
    &String1,
    v34);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v49);
  if ( !v28 )
  {
    if ( v52 == 2 )
    {
      v37 = 0;
      goto LABEL_55;
    }
    v4 = v54;
    goto LABEL_50;
  }
LABEL_55:
  *a3 = v37;
  v39 = EfsTraceLoggingProvider::Provider();
  v41 = v39;
  if ( *(_DWORD *)v39 > 5u && (unsigned __int8)tlgKeywordOn(v39, 0x600000000000LL) )
  {
    v54 = packageFullName;
    v46 = *a3;
    v53 = (wchar_t *)0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v41,
      (unsigned int)&word_180103C5E,
      (_DWORD)v41,
      v42,
      (__int64)&v53,
      (__int64)&v46,
      (__int64)&v54);
  }
  wil::ActivityBase<EfsTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v56,
    v40,
    v41);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(
    &MaxCount[1],
    v43);
  LastError = 0;
LABEL_59:
  EfsTelemetry::GetDplIsAllowedStatus::~GetDplIsAllowedStatus((EfsTelemetry::GetDplIsAllowedStatus *)v56);
  return LastError;
}

```

## disassembly

```asm
0x1800d2b2c  mov     [rsp-8+arg_8], rbx
0x1800d2b31  push    rbp
0x1800d2b32  push    rsi
0x1800d2b33  push    rdi
0x1800d2b34  push    r12
0x1800d2b36  push    r13
0x1800d2b38  push    r14
0x1800d2b3a  push    r15
0x1800d2b3c  lea     rbp, [rsp-270h]
0x1800d2b44  sub     rsp, 370h
0x1800d2b4b  mov     rax, cs:__security_cookie
0x1800d2b52  xor     rax, rsp
0x1800d2b55  mov     [rbp+2A0h+var_40], rax
0x1800d2b5c  mov     r15, r8
0x1800d2b5f  mov     [rsp+3A0h+var_33C], edx
0x1800d2b63  mov     rdi, rcx
0x1800d2b66  mov     [rsp+3A0h+var_330], rcx
0x1800d2b6b  xor     r13d, r13d
0x1800d2b6e  mov     [r8], r13b
0x1800d2b71  lea     rcx, [rbp+2A0h+var_320]; this
0x1800d2b75  call    ??$?0$$V@GetDplIsAllowedStatus@EfsTelemetry@@AEAA@U?$integral_constant@D$0A@@wistd@@@Z; EfsTelemetry::GetDplIsAllowedStatus::GetDplIsAllowedStatus(wistd::integral_constant<char,0>)
0x1800d2b7a  nop
0x1800d2b7b  xor     r9d, r9d; lpFilePart
0x1800d2b7e  xor     r8d, r8d; lpBuffer
0x1800d2b81  xor     edx, edx; nBufferLength
0x1800d2b83  mov     rcx, rdi; lpFileName
0x1800d2b86  call    cs:__imp_GetFullPathNameW
0x1800d2b8c  test    eax, eax
0x1800d2b8e  jnz     short loc_1800D2BAF
0x1800d2b90  mov     rcx, [rbp+2A8h]; this
0x1800d2b97  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\efs\\edpprote"...
0x1800d2b9e  mov     edx, 0DCh; void *
0x1800d2ba3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d2ba8  mov     ebx, eax
0x1800d2baa  jmp     loc_1800D3017
0x1800d2baf  lea     ebx, [rax+1]
0x1800d2bb2  cmp     ebx, eax
0x1800d2bb4  jnb     short loc_1800D2BDB
0x1800d2bb6  mov     rcx, [rbp+2A8h]; this
0x1800d2bbd  mov     ebx, 80070216h
0x1800d2bc2  mov     r9d, ebx; char *
0x1800d2bc5  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\efs\\edpprote"...
0x1800d2bcc  mov     edx, 0DEh; void *
0x1800d2bd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d2bd6  jmp     loc_1800D3017
0x1800d2bdb  mov     r8d, ebx
0x1800d2bde  xor     edx, edx
0x1800d2be0  lea     rcx, [rsp+3A0h+MaxCount+4]
0x1800d2be5  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800d2bea  nop
0x1800d2beb  mov     r14, qword ptr [rsp+3A0h+MaxCount+4]
0x1800d2bf0  test    r14, r14
0x1800d2bf3  jnz     short loc_1800D2C25
0x1800d2bf5  mov     ebx, 8007000Eh
0x1800d2bfa  mov     edx, 0E0h; void *
0x1800d2bff  mov     r9d, ebx; char *
0x1800d2c02  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\efs\\edpprote"...
0x1800d2c09  mov     rcx, [rbp+2A8h]; this
0x1800d2c10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d2c15  nop
0x1800d2c16  lea     rcx, [rsp+3A0h+MaxCount+4]
0x1800d2c1b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d2c20  jmp     loc_1800D3017
0x1800d2c25  xor     r9d, r9d; lpFilePart
0x1800d2c28  mov     r8, r14; lpBuffer
0x1800d2c2b  mov     edx, ebx; nBufferLength
0x1800d2c2d  mov     rcx, rdi; lpFileName
0x1800d2c30  call    cs:__imp_GetFullPathNameW
0x1800d2c36  test    eax, eax
0x1800d2c38  jnz     short loc_1800D2C56
0x1800d2c3a  mov     rcx, [rbp+2A8h]; this
0x1800d2c41  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\efs\\edpprote"...
0x1800d2c48  mov     edx, 0E2h; void *
0x1800d2c4d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d2c52  mov     ebx, eax
0x1800d2c54  jmp     short loc_1800D2C16
0x1800d2c56  mov     edx, eax; cchPath
0x1800d2c58  mov     rcx, r14; pszPath
0x1800d2c5b  call    cs:__imp_PathCchRemoveFileSpec
0x1800d2c61  mov     ebx, eax
0x1800d2c63  test    eax, eax
0x1800d2c65  jns     short loc_1800D2C71
0x1800d2c67  mov     r9d, eax
0x1800d2c6a  mov     edx, 0E6h
0x1800d2c6f  jmp     short loc_1800D2C02
0x1800d2c71  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800d2c75  inc     rsi
0x1800d2c78  cmp     [r14+rsi*2], r13w
0x1800d2c7d  jnz     short loc_1800D2C75
0x1800d2c7f  mov     dword ptr [r14+rsi*2], 5Ch ; '\'
0x1800d2c87  movups  xmm0, xmmword ptr cs:aNopackageid; "<NoPackageId>"
0x1800d2c8e  movaps  xmmword ptr [rbp+2A0h+packageFullName], xmm0
0x1800d2c95  movups  xmm1, xmmword ptr cs:aNopackageid+0Ch; "kageId>"
0x1800d2c9c  movups  xmmword ptr [rbp+2A0h+packageFullName+0Ch], xmm1
0x1800d2ca3  xor     edx, edx; Val
0x1800d2ca5  mov     r8d, 0E4h; Size
0x1800d2cab  lea     rcx, [rbp+2A0h+var_1B4]; void *
0x1800d2cb2  call    memset_0
0x1800d2cb7  mov     r12d, 100h
0x1800d2cbd  mov     [rsp+3A0h+var_328], r12
0x1800d2cc2  mov     [rsp+3A0h+var_368], r13
0x1800d2cc7  mov     [rsp+3A0h+var_370], r13
0x1800d2ccc  mov     [rsp+3A0h+var_378], r13
0x1800d2cd1  mov     qword ptr [rsp+3A0h+var_380], r13; int
0x1800d2cd6  xor     r9d, r9d
0x1800d2cd9  lea     r8, [rsp+3A0h+var_328]
0x1800d2cde  lea     rdx, [rbp+2A0h+packageFullName]
0x1800d2ce5  lea     rbx, [r9-6]
0x1800d2ce9  mov     rcx, rbx
0x1800d2cec  call    cs:__imp_RtlQueryPackageClaims
0x1800d2cf2  cmp     eax, 0C0000225h
0x1800d2cf7  jz      loc_1800D2F3E
0x1800d2cfd  mov     [rsp+3A0h+packageFamilyNameLength], 41h ; 'A'
0x1800d2d05  lea     r8, [rbp+2A0h+packageFamilyName]; packageFamilyName
0x1800d2d0c  lea     rdx, [rsp+3A0h+packageFamilyNameLength]; packageFamilyNameLength
0x1800d2d11  lea     rcx, [rbp+2A0h+packageFullName]; packageFullName
0x1800d2d18  call    cs:__imp_PackageFamilyNameFromFullName
0x1800d2d1e  test    eax, eax
0x1800d2d20  jz      short loc_1800D2D42
0x1800d2d22  mov     rcx, [rbp+2A8h]; this
0x1800d2d29  mov     r9d, eax; char *
0x1800d2d2c  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\efs\\edpprote"...
0x1800d2d33  lea     edx, [r12-4]; void *
0x1800d2d38  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800d2d3d  jmp     loc_1800D2C52
0x1800d2d42  lea     rdx, [rbp+2A0h+packageFamilyName]
0x1800d2d49  mov     rcx, rbx
0x1800d2d4c  call    cs:__imp_OpenStateExplicit
0x1800d2d52  mov     rbx, rax
0x1800d2d55  mov     [rsp+3A0h+var_350], rax
0x1800d2d5a  test    rax, rax
0x1800d2d5d  jnz     short loc_1800D2D86
0x1800d2d5f  mov     edx, r12d; void *
0x1800d2d62  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\efs\\edpprote"...
0x1800d2d69  mov     rcx, [rbp+2A8h]; this
0x1800d2d70  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d2d75  mov     ebx, eax
0x1800d2d77  lea     rcx, [rsp+3A0h+var_350]
0x1800d2d7c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800d2d81  jmp     loc_1800D2C16
0x1800d2d86  mov     dword ptr [rsp+3A0h+MaxCount], r13d
0x1800d2d8b  lea     r8, [rsp+3A0h+MaxCount]
0x1800d2d90  xor     edx, edx
0x1800d2d92  mov     rcx, rbx
0x1800d2d95  call    cs:__imp_GetStateRootFolder
0x1800d2d9b  test    eax, eax
0x1800d2d9d  jz      short loc_1800D2DC1
0x1800d2d9f  mov     ebx, 8000FFFFh
0x1800d2da4  mov     edx, 102h; void *
0x1800d2da9  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\efs\\edpprote"...
0x1800d2db0  mov     r9d, ebx; char *
0x1800d2db3  mov     rcx, [rbp+2A8h]; this
0x1800d2dba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d2dbf  jmp     short loc_1800D2D77
0x1800d2dc1  call    cs:__imp_GetLastError
0x1800d2dc7  cmp     eax, 7Ah ; 'z'
0x1800d2dca  jz      short loc_1800D2DD3
0x1800d2dcc  mov     edx, 103h
0x1800d2dd1  jmp     short loc_1800D2D62
0x1800d2dd3  mov     eax, dword ptr [rsp+3A0h+MaxCount]
0x1800d2dd7  lea     ecx, [rax+1]
0x1800d2dda  cmp     ecx, eax
0x1800d2ddc  jb      loc_1800D2F22
0x1800d2de2  mov     dword ptr [rsp+3A0h+MaxCount], ecx
0x1800d2de6  mov     r8d, ecx
0x1800d2de9  xor     edx, edx
0x1800d2deb  lea     rcx, [rsp+3A0h+String1]
0x1800d2df0  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800d2df5  mov     r13, [rsp+3A0h+String1]
0x1800d2dfa  test    r13, r13
0x1800d2dfd  jnz     short loc_1800D2E2E
0x1800d2dff  mov     rcx, [rbp+2A8h]; this
0x1800d2e06  mov     ebx, 8007000Eh
0x1800d2e0b  mov     r9d, ebx; char *
0x1800d2e0e  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\efs\\edpprote"...
0x1800d2e15  mov     edx, 10Eh; void *
0x1800d2e1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d2e1f  lea     rcx, [rsp+3A0h+String1]
0x1800d2e24  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d2e29  jmp     loc_1800D2D77
0x1800d2e2e  lea     r8, [rsp+3A0h+MaxCount]
0x1800d2e33  mov     rdx, r13
0x1800d2e36  mov     rcx, rbx
0x1800d2e39  call    cs:__imp_GetStateRootFolder
0x1800d2e3f  test    eax, eax
0x1800d2e41  jnz     short loc_1800D2E5F
0x1800d2e43  mov     rcx, [rbp+2A8h]; this
0x1800d2e4a  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\efs\\edpprote"...
0x1800d2e51  mov     edx, 10Fh; void *
0x1800d2e56  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d2e5b  mov     ebx, eax
0x1800d2e5d  jmp     short loc_1800D2E1F
0x1800d2e5f  xor     r12b, r12b
0x1800d2e62  inc     rsi
0x1800d2e65  mov     eax, dword ptr [rsp+3A0h+MaxCount]
0x1800d2e69  dec     eax
0x1800d2e6b  mov     word ptr [r13+rax*2+0], 5Ch ; '\'
0x1800d2e73  mov     ecx, dword ptr [rsp+3A0h+MaxCount]
0x1800d2e77  xor     eax, eax
0x1800d2e79  mov     [r13+rcx*2+0], ax
0x1800d2e7f  lea     r8d, [rax+4]; MaxCount
0x1800d2e83  lea     rdx, asc_1800F4DB0; "\\\\?\\"
0x1800d2e8a  mov     rcx, r14; String1
0x1800d2e8d  call    cs:__imp__wcsnicmp
0x1800d2e93  mov     edi, eax
0x1800d2e95  lea     rax, [r14+8]
0x1800d2e99  test    edi, edi
0x1800d2e9b  cmovnz  rax, r14
0x1800d2e9f  mov     [rsp+3A0h+var_338], rax
0x1800d2ea4  mov     ebx, dword ptr [rsp+3A0h+MaxCount]
0x1800d2ea8  mov     r8d, 4; MaxCount
0x1800d2eae  lea     rdx, asc_1800F4DB0; "\\\\?\\"
0x1800d2eb5  mov     rcx, r13; String1
0x1800d2eb8  call    cs:__imp__wcsnicmp
0x1800d2ebe  lea     rdx, [r13+8]
0x1800d2ec2  test    eax, eax
0x1800d2ec4  cmovnz  rdx, r13; String2
0x1800d2ec8  lea     r8d, [rbx-4]
0x1800d2ecc  xor     r13d, r13d
0x1800d2ecf  test    eax, eax
0x1800d2ed1  cmovnz  r8d, ebx; MaxCount
0x1800d2ed5  lea     rax, [rsi-4]
0x1800d2ed9  test    edi, edi
0x1800d2edb  cmovnz  rax, rsi
0x1800d2edf  lea     ebx, [r13+1]
0x1800d2ee3  cmp     rax, r8
0x1800d2ee6  jb      short loc_1800D2EFD
0x1800d2ee8  mov     rcx, [rsp+3A0h+var_338]; String1
0x1800d2eed  call    cs:__imp__wcsnicmp
0x1800d2ef3  movzx   r12d, r12b
0x1800d2ef7  test    eax, eax
0x1800d2ef9  cmovz   r12d, ebx
0x1800d2efd  lea     rcx, [rsp+3A0h+String1]
0x1800d2f02  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d2f07  lea     rcx, [rsp+3A0h+var_350]
0x1800d2f0c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800d2f11  test    r12b, r12b
0x1800d2f14  jnz     short loc_1800D2F8D
0x1800d2f16  cmp     [rsp+3A0h+var_33C], 2
0x1800d2f1b  jnz     short loc_1800D2F39
0x1800d2f1d  mov     bl, r13b
0x1800d2f20  jmp     short loc_1800D2F8D
0x1800d2f22  mov     dword ptr [rsp+3A0h+MaxCount], 0FFFFFFFFh
0x1800d2f2a  mov     ebx, 80070216h
0x1800d2f2f  mov     edx, 10Ch
0x1800d2f34  jmp     loc_1800D2DA9
0x1800d2f39  mov     rdi, [rsp+3A0h+var_330]
0x1800d2f3e  mov     [rsp+3A0h+var_35F], r13b
0x1800d2f43  mov     [rsp+3A0h+var_360], r13b
0x1800d2f48  lea     r9, [rsp+3A0h+var_360]; bool *
0x1800d2f4d  lea     r8, [rsp+3A0h+var_35F]; bool *
0x1800d2f52  xor     edx, edx; bool
0x1800d2f54  mov     rcx, rdi; pszPath
0x1800d2f57  call    ?EfsIsFilePathOnRemovableVolume@@YAJPEBG_NPEA_N2@Z; EfsIsFilePathOnRemovableVolume(ushort const *,bool,bool *,bool *)
0x1800d2f5c  mov     ebx, eax
0x1800d2f5e  test    eax, eax
0x1800d2f60  jns     short loc_1800D2F6F
0x1800d2f62  mov     r9d, eax
0x1800d2f65  mov     edx, 14Ah
0x1800d2f6a  jmp     loc_1800D2C02
0x1800d2f6f  cmp     [rsp+3A0h+var_35F], r13b
0x1800d2f74  jz      short loc_1800D2F85
0x1800d2f76  mov     ebx, 80070057h
0x1800d2f7b  mov     edx, 14Bh
0x1800d2f80  jmp     loc_1800D2BFF
0x1800d2f85  cmp     [rsp+3A0h+var_360], r13b
0x1800d2f8a  setz    bl
0x1800d2f8d  mov     rax, r15
0x1800d2f90  mov     [rax], bl
0x1800d2f92  call    ?Provider@EfsTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; EfsTraceLoggingProvider::Provider(void)
0x1800d2f97  mov     r8, rax
0x1800d2f9a  mov     ecx, [rax]
0x1800d2f9c  cmp     ecx, 5
0x1800d2f9f  jbe     short loc_1800D3000
0x1800d2fa1  mov     rdx, 600000000000h
0x1800d2fab  mov     rcx, rax
0x1800d2fae  call    _tlgKeywordOn
0x1800d2fb3  test    al, al
0x1800d2fb5  jz      short loc_1800D3000
0x1800d2fb7  lea     rax, [rbp+2A0h+packageFullName]
0x1800d2fbe  mov     [rsp+3A0h+var_330], rax
0x1800d2fc3  mov     al, [r15]
0x1800d2fc6  mov     [rsp+3A0h+var_360], al
0x1800d2fca  mov     [rsp+3A0h+var_338], 1000000h
0x1800d2fd3  lea     rax, [rsp+3A0h+var_330]
0x1800d2fd8  mov     [rsp+3A0h+var_370], rax
0x1800d2fdd  lea     rax, [rsp+3A0h+var_360]
0x1800d2fe2  mov     [rsp+3A0h+var_378], rax
0x1800d2fe7  lea     rax, [rsp+3A0h+var_338]
0x1800d2fec  mov     qword ptr [rsp+3A0h+var_380], rax
0x1800d2ff1  lea     rdx, word_180103C5E
0x1800d2ff8  mov     rcx, r8
0x1800d2ffb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x1800d3000  lea     rcx, [rbp+2A0h+var_320]
0x1800d3004  call    ?Stop@?$ActivityBase@VEfsTraceLoggingProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<EfsTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800d3009  nop
0x1800d300a  lea     rcx, [rsp+3A0h+MaxCount+4]
0x1800d300f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d3014  mov     ebx, r13d
0x1800d3017  lea     rcx, [rbp+2A0h+var_320]; this
  ... truncated ...
```
