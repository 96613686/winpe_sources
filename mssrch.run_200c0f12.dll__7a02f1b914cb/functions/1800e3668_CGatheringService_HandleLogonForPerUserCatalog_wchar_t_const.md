# CGatheringService::HandleLogonForPerUserCatalog(wchar_t const *)

- ea: `0x1800e3668`
- end: `0x1800e3d84`
- name: `?HandleLogonForPerUserCatalog@CGatheringService@@QEAAJPEB_W@Z`
- size: `1820`
- prototype: `int(CGatheringService *__hidden this, const wchar_t *)`
- caller_count: `2`
- callee_count: `34`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800f7dc8`
- `0x18017afdc`

## callees

- `0x18000bf8c`
- `0x180012120`
- `0x18001b470`
- `0x18001d8a0`
- `0x1800269b0`
- `0x180056610`
- `0x180056b90`
- `0x18005edc4`
- `0x18007d088`
- `0x18008fde0`
- `0x1800a3a38`
- `0x1800b2d2c`
- `0x1800b837c`
- `0x1800ce1f8`
- `0x1800cff10`
- `0x1800e1320`
- `0x1800e2374`
- `0x1800e3668`
- `0x1800e4710`
- `0x1800e4730`
- `0x1800e487c`
- `0x1800e61a8`
- `0x1800ead20`
- `0x1800f89d0`
- `0x180109ebc`
- `0x180117204`
- `0x1801244c0`
- `0x18013dd98`
- `0x18013fd18`
- `0x180180e98`
- `0x18018310c`
- `0x18020a67c`
- `0x180214574`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e3a0a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e3aa8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e3a0a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e3aa8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e3af6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e3b41`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e3b8f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e3af6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e3b41`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e3b8f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800e370c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800e370c`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x1800e37da`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x1800e37da`

## string_xrefs

- `0x1800e37cc`: `SetupCompletedSuccessfully`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CGatheringService::HandleLogonForPerUserCatalog(CGatherApplicationCollection **this, wchar_t *a2)
{
  int DataRootForPerUserCatalog; // eax
  DWORD FileAttributesW; // eax
  char v6; // di
  HKEY *v7; // rax
  const wchar_t *v8; // rcx
  unsigned int v9; // r9d
  const wchar_t *v10; // r8
  int v11; // eax
  bool v12; // sf
  LSTATUS v13; // eax
  bool v14; // sf
  int v15; // eax
  int v16; // r14d
  const char *v17; // r9
  int v18; // eax
  const wchar_t *v19; // rdx
  int v20; // eax
  int UserCatalog; // eax
  unsigned int v22; // edx
  const wchar_t *v23; // rdx
  int v24; // r8d
  unsigned int v25; // r9d
  HKEY *phkResult; // rax
  const WCHAR *v27; // rdx
  unsigned int Key; // eax
  HKEY *v29; // rax
  const WCHAR *v30; // rdx
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  int v35; // eax
  const wchar_t *v36; // rdx
  int v37; // eax
  int v38; // eax
  int v39; // eax
  __int64 result; // rax
  int pvData; // [rsp+20h] [rbp-228h]
  BYTE *pvDataa; // [rsp+20h] [rbp-228h]
  unsigned int pvDatab; // [rsp+20h] [rbp-228h]
  unsigned int pvDatac; // [rsp+20h] [rbp-228h]
  unsigned int pvDatad; // [rsp+20h] [rbp-228h]
  unsigned int pvDatae; // [rsp+20h] [rbp-228h]
  BYTE Data[8]; // [rsp+50h] [rbp-1F8h] BYREF
  DWORD pdwType[2]; // [rsp+58h] [rbp-1F0h] BYREF
  DWORD pcbData[2]; // [rsp+60h] [rbp-1E8h] BYREF
  HKEY hkey; // [rsp+68h] [rbp-1E0h] BYREF
  ReIndexPatternInfo *v51; // [rsp+70h] [rbp-1D8h] BYREF
  __int128 v52; // [rsp+78h] [rbp-1D0h]
  LPCWSTR lpSubKey[3]; // [rsp+88h] [rbp-1C0h] BYREF
  unsigned __int64 v54; // [rsp+A0h] [rbp-1A8h]
  _QWORD Src[5]; // [rsp+A8h] [rbp-1A0h] BYREF
  const int *v56; // [rsp+D0h] [rbp-178h] BYREF
  LPCWSTR lpFileName; // [rsp+D8h] [rbp-170h]
  __int64 v58; // [rsp+E0h] [rbp-168h]
  __int16 v59; // [rsp+E8h] [rbp-160h] BYREF
  _BYTE v60[8]; // [rsp+170h] [rbp-D8h] BYREF
  wchar_t *v61; // [rsp+178h] [rbp-D0h]
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  PerUserCatalogNameForCorruption::SetCatalog(a2);
  try
  {
    lpFileName = (LPCWSTR)&v59;
    v58 = 65;
    v59 = 0;
    v56 = &CCICommonPathString::`vftable';
    DataRootForPerUserCatalog = GetDataRootForPerUserCatalog(a2, (struct CLMString *)&v56);
    if ( DataRootForPerUserCatalog < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9AA,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
        (const char *)(unsigned int)DataRootForPerUserCatalog,
        pvData);
    FileAttributesW = GetFileAttributesW(lpFileName);
    if ( FileAttributesW == -1 || (v6 = 1, (FileAttributesW & 0x10) == 0) )
      v6 = 0;
    hkey = 0;
    std::wstring::wstring(Src, a2);
    std::wstring::_Append<wchar_t>(Src);
    v7 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hkey);
    v10 = (const wchar_t *)Src;
    if ( Src[3] > 7u )
      v10 = (const wchar_t *)Src[0];
    v11 = WSearchRegOpenKeyEx(v8, HKEY_USERS, v10, v9, 0xF003Fu, v7);
    v12 = v11 < 0;
    if ( v11 > 0 )
      v12 = 1;
    if ( !v12 )
    {
      *(_DWORD *)Data = 0;
      pcbData[0] = 4;
      pdwType[0] = 4;
      v13 = SHGetValueW(hkey, 0, L"SetupCompletedSuccessfully", pdwType, Data, pcbData);
      v14 = v13 < 0;
      if ( v13 > 0 )
        v14 = 1;
      if ( !v14 )
      {
        if ( !v6 || (v6 = 1, *(_DWORD *)Data != 1) )
          v6 = 0;
      }
    }
    *(_DWORD *)Data = 0;
    std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>(&v51);
    if ( v6 )
    {
      pvDataa = Data;
      v15 = CGatheringService::CheckPerUserCatalogCompatibility(this, a2, lpFileName, &v51);
      v16 = *(_DWORD *)Data;
      if ( v15 < 0 || *(_DWORD *)Data == 1 )
      {
        wil::make_bstr_nothrow(pdwType, a2);
        if ( !*(_QWORD *)pdwType )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0x9D6,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
            v17);
        v18 = (*(__int64 (__fastcall **)(CGatherApplicationCollection *))(*(_QWORD *)this[47] + 88LL))(this[47]);
        if ( v18 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x9D8,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
            (const char *)(unsigned int)v18,
            (int)Data);
        v6 = 0;
        wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(pdwType);
      }
      if ( v6 )
      {
        ETWLog::Log(L"[SrchGatherSvc] Logon for user %s as loading catalog", a2);
        if ( v16 == 2 )
        {
          v20 = PropertySchemaInspection::SetupPerUserCatalog(a2, v19);
          if ( v20 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x9EC,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
              (const char *)(unsigned int)v20,
              (int)Data);
        }
        else if ( v16 == 4 )
        {
          ETWLog::Log(L"[SrchGatherSvc] Index for user %s is marked for inplace rebuild.", a2);
        }
        UserCatalog = CGatherApplicationCollection::LoadUserCatalog(this[47], a2);
        if ( UserCatalog < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x9F5,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
            (const char *)(unsigned int)UserCatalog,
            (int)Data);
LABEL_57:
        v39 = MarkPerUserCatalogSetupCompleteness(a2, v22);
        if ( v39 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xA3B,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
            (const char *)(unsigned int)v39,
            (int)pvDataa);
        if ( v51 )
        {
          std::_Destroy_range<std::allocator<CPhMultiArch::MachineWithAumid>>(v51);
          std::_Deallocate<16>(v51, 8 * ((__int64)(*((_QWORD *)&v52 + 1) - (_QWORD)v51) >> 3));
          v51 = 0;
          v52 = 0;
        }
        ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)Src);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        TLMString<64,64,32767>::~TLMString<64,64,32767>(&v56);
        PerUserCatalogNameForCorruption::SetCatalog(0);
        return 0;
      }
    }
    else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55683212>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_55683212>::GetImpl'::`2'::impl) )
    {
      CGatheringService::SetBulkIndexingStateFromReason(this, 1000);
    }
    ETWLog::Log(L"[SrchGatherSvc] Logon for user %s as creating catalog", a2);
    FSOp::DelNode((FSOp *)lpFileName, v23, v24, v25);
    std::wstring::wstring(lpSubKey, a2);
    std::wstring::_Append<wchar_t>(lpSubKey);
    *(_QWORD *)pcbData = 0;
    phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(pcbData);
    v27 = (const WCHAR *)lpSubKey;
    if ( v54 > 7 )
      v27 = lpSubKey[0];
    Key = RegCreateKeyExW(HKEY_USERS, v27, 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
    if ( Key )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xA0C,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
        (const char *)Key,
        pvDatab);
    std::wstring::assign(lpSubKey, a2);
    std::wstring::_Append<wchar_t>(lpSubKey);
    *(_QWORD *)pdwType = 0;
    v29 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(pdwType);
    v30 = (const WCHAR *)lpSubKey;
    if ( v54 > 7 )
      v30 = lpSubKey[0];
    v31 = RegCreateKeyExW(HKEY_USERS, v30, 0, 0, 0, 0xF003Fu, 0, v29, 0);
    if ( v31 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xA1B,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
        (const char *)v31,
        pvDatac);
    *(_DWORD *)Data = 67239936;
    v32 = RegSetValueExW(*(HKEY *)pdwType, L"RegVersion", 0, 4u, Data, 4u);
    if ( v32 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xA1F,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
        (const char *)v32,
        pvDatad);
    *(_DWORD *)Data = 0;
    v33 = RegSetValueExW(*(HKEY *)pdwType, L"DebugTranFiles", 0, 4u, Data, 4u);
    if ( v33 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xA23,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
        (const char *)v33,
        pvDatae);
    *(_DWORD *)Data = 1;
    v34 = RegSetValueExW(*(HKEY *)pdwType, L"LowDiskMinimumMBytes", 0, 4u, Data, 4u);
    if ( v34 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xA2C,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
        (const char *)v34,
        (unsigned int)pvDataa);
    v35 = WriteCatalogVersion(a2);
    if ( v35 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA2E,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
        (const char *)(unsigned int)v35,
        (int)pvDataa);
    v37 = PropertySchemaInspection::SetupPerUserCatalog(a2, v36);
    if ( v37 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA2F,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
        (const char *)(unsigned int)v37,
        (int)pvDataa);
    TLMString<64,64,32767>::TLMString<64,64,32767>(v60, &v56);
    AppendBackSlashIf((struct CLMString *)v60);
    CLMString::Append((CLMString *)v60, a2, 0xFFFFFFFF);
    v38 = CGatherApplicationCollection::CreateUserCatalog(this[47], a2, v61);
    if ( v38 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA36,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
        (const char *)(unsigned int)v38,
        (int)pvDataa);
    TLMString<64,64,32767>::~TLMString<64,64,32767>(v60);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(pdwType);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(pcbData);
    ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)lpSubKey);
    goto LABEL_57;
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      2621,
      "onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx");
  }
  return result;
}

```

## disassembly

```asm
0x1800e3668  mov     [rsp+arg_10], rbx
0x1800e366d  push    rsi
0x1800e366e  push    rdi
0x1800e366f  push    r12
0x1800e3671  push    r14
0x1800e3673  push    r15
0x1800e3675  sub     rsp, 220h
0x1800e367c  mov     rax, cs:__security_cookie
0x1800e3683  xor     rax, rsp
0x1800e3686  mov     [rsp+248h+var_30], rax
0x1800e368e  mov     rbx, rdx
0x1800e3691  mov     r15, rcx
0x1800e3694  mov     rcx, rdx; lpTlsValue
0x1800e3697  call    PerUserCatalogNameForCorruption__SetCatalog
0x1800e369c  nop
0x1800e369d  lea     rax, [rsp+248h+var_160]
0x1800e36a5  mov     [rsp+248h+lpFileName], rax
0x1800e36ad  mov     [rsp+248h+var_168], 41h ; 'A'
0x1800e36b9  xor     r12d, r12d
0x1800e36bc  mov     [rsp+248h+var_160], r12w
0x1800e36c5  lea     rax, ??_7CCICommonPathString@@6B@; const CCICommonPathString::`vftable'
0x1800e36cc  mov     [rsp+248h+var_178], rax
0x1800e36d4  lea     rdx, [rsp+248h+var_178]; struct CLMString *
0x1800e36dc  mov     rcx, rbx; wchar_t *
0x1800e36df  call    ?GetDataRootForPerUserCatalog@@YAJPEB_WAEAV?$TLMString@$0EA@$0EA@$0HPPP@@@@Z; GetDataRootForPerUserCatalog(wchar_t const *,TLMString<64,64,32767> &)
0x1800e36e4  mov     rcx, [rsp+248h]; this
0x1800e36ec  test    eax, eax
0x1800e36ee  jns     short loc_1800E3704
0x1800e36f0  mov     r9d, eax; char *
0x1800e36f3  lea     r8, aOnecoreuapBase_133; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e36fa  mov     edx, 9AAh; void *
0x1800e36ff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e3704  mov     rcx, [rsp+248h+lpFileName]; lpFileName
0x1800e370c  call    cs:__imp_GetFileAttributesW
0x1800e3712  cmp     eax, 0FFFFFFFFh
0x1800e3715  jz      short loc_1800E371E
0x1800e3717  test    al, 10h
0x1800e3719  mov     dil, 1
0x1800e371c  jnz     short loc_1800E3721
0x1800e371e  mov     dil, r12b
0x1800e3721  mov     [rsp+248h+hkey], r12
0x1800e3726  mov     rdx, rbx
0x1800e3729  lea     rcx, [rsp+248h+Src]
0x1800e3731  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800e3736  nop
0x1800e3737  mov     r8d, 22h ; '"'
0x1800e373d  lea     rdx, aSoftwareMicros_14; "\\SOFTWARE\\Microsoft\\Windows Search"
0x1800e3744  lea     rcx, [rsp+248h+Src]; Src
0x1800e374c  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800e3751  lea     rcx, [rsp+248h+hkey]
0x1800e3756  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800e375b  lea     r8, [rsp+248h+Src]
0x1800e3763  cmp     [rsp+248h+var_188], 7
0x1800e376c  cmova   r8, [rsp+248h+Src]; wchar_t *
0x1800e3775  mov     [rsp+248h+pcbData], rax; HKEY *
0x1800e377a  mov     dword ptr [rsp+248h+pvData], 0F003Fh; unsigned int
0x1800e3782  mov     r14, 0FFFFFFFF80000003h
0x1800e3789  mov     rdx, r14; HKEY
0x1800e378c  call    ?WSearchRegOpenKeyEx@@YAJPEB_WPEAUHKEY__@@0KKPEAPEAU1@@Z; WSearchRegOpenKeyEx(wchar_t const *,HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x1800e3791  test    eax, eax
0x1800e3793  jle     short loc_1800E379F
0x1800e3795  movzx   eax, ax
0x1800e3798  or      eax, 80070000h
0x1800e379d  test    eax, eax
0x1800e379f  mov     esi, 4
0x1800e37a4  js      short loc_1800E3802
0x1800e37a6  mov     dword ptr [rsp+248h+Data], r12d
0x1800e37ab  mov     [rsp+248h+var_1E8], esi
0x1800e37af  mov     [rsp+248h+pdwType], esi
0x1800e37b3  lea     rax, [rsp+248h+var_1E8]
0x1800e37b8  mov     [rsp+248h+pcbData], rax; pcbData
0x1800e37bd  lea     rax, [rsp+248h+Data]
0x1800e37c2  mov     [rsp+248h+pvData], rax; pvData
0x1800e37c7  lea     r9, [rsp+248h+pdwType]; pdwType
0x1800e37cc  lea     r8, pszValue; "SetupCompletedSuccessfully"
0x1800e37d3  xor     edx, edx; pszSubKey
0x1800e37d5  mov     rcx, [rsp+248h+hkey]; hkey
0x1800e37da  call    cs:__imp_SHGetValueW
0x1800e37e0  test    eax, eax
0x1800e37e2  jle     short loc_1800E37EE
0x1800e37e4  movzx   eax, ax
0x1800e37e7  or      eax, 80070000h
0x1800e37ec  test    eax, eax
0x1800e37ee  js      short loc_1800E3802
0x1800e37f0  test    dil, dil
0x1800e37f3  jz      short loc_1800E37FF
0x1800e37f5  cmp     dword ptr [rsp+248h+Data], 1
0x1800e37fa  mov     dil, 1
0x1800e37fd  jz      short loc_1800E3802
0x1800e37ff  mov     dil, r12b
0x1800e3802  mov     dword ptr [rsp+248h+Data], r12d
0x1800e3807  lea     rcx, [rsp+248h+var_1D8]; void *
0x1800e380c  call    ??0?$vector@Uunique_ptr_bytes_buffer@@V?$allocator@Uunique_ptr_bytes_buffer@@@std@@@std@@QEAA@XZ; std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>(void)
0x1800e3811  nop
0x1800e3812  test    dil, dil
0x1800e3815  jz      loc_1800E394F
0x1800e381b  lea     rax, [rsp+248h+Data]
0x1800e3820  mov     [rsp+248h+pvData], rax; int
0x1800e3825  lea     r9, [rsp+248h+var_1D8]
0x1800e382a  mov     r8, [rsp+248h+lpFileName]
0x1800e3832  mov     rdx, rbx
0x1800e3835  mov     rcx, r15
0x1800e3838  call    ?CheckPerUserCatalogCompatibility@CGatheringService@@AEAAJPEB_W0PEAV?$vector@VReIndexPatternInfo@@V?$allocator@VReIndexPatternInfo@@@std@@@std@@PEAW4INDEXER_SETUP_ACTIONS@@@Z; CGatheringService::CheckPerUserCatalogCompatibility(wchar_t const *,wchar_t const *,std::vector<ReIndexPatternInfo> *,INDEXER_SETUP_ACTIONS *)
0x1800e383d  mov     r14d, dword ptr [rsp+248h+Data]
0x1800e3842  test    eax, eax
0x1800e3844  js      short loc_1800E384C
0x1800e3846  cmp     r14d, 1
0x1800e384a  jnz     short loc_1800E38BD
0x1800e384c  mov     rdx, rbx
0x1800e384f  lea     rcx, [rsp+248h+pdwType]
0x1800e3854  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr_nothrow(wchar_t const *)
0x1800e3859  nop
0x1800e385a  mov     rcx, [rsp+248h]; this
0x1800e3862  mov     rdx, qword ptr [rsp+248h+pdwType]
0x1800e3867  test    rdx, rdx
0x1800e386a  jnz     short loc_1800E387D
0x1800e386c  lea     r8, aOnecoreuapBase_133; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e3873  mov     edx, 9D6h; void *
0x1800e3878  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800e387d  mov     rcx, [r15+178h]
0x1800e3884  mov     rax, [rcx]
0x1800e3887  mov     rax, [rax+58h]
0x1800e388b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3890  mov     rcx, [rsp+248h]; this
0x1800e3898  test    eax, eax
0x1800e389a  jns     short loc_1800E38B0
0x1800e389c  mov     r9d, eax; char *
0x1800e389f  lea     r8, aOnecoreuapBase_133; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e38a6  mov     edx, 9D8h; void *
0x1800e38ab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e38b0  mov     dil, r12b
0x1800e38b3  lea     rcx, [rsp+248h+pdwType]
0x1800e38b8  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1800e38bd  test    dil, dil
0x1800e38c0  jz      loc_1800E396E
0x1800e38c6  mov     rdx, rbx
0x1800e38c9  lea     rcx, aSrchgathersvcL_2; "[SrchGatherSvc] Logon for user %s as lo"...
0x1800e38d0  call    ?Log@ETWLog@@SAXPEB_WZZ; ETWLog::Log(wchar_t const *,...)
0x1800e38d5  cmp     r14d, 2
0x1800e38d9  jnz     short loc_1800E3903
0x1800e38db  mov     rcx, rbx; this
0x1800e38de  call    ?SetupPerUserCatalog@PropertySchemaInspection@@YAJPEB_W@Z; PropertySchemaInspection::SetupPerUserCatalog(wchar_t const *)
0x1800e38e3  mov     rcx, [rsp+248h]; this
0x1800e38eb  test    eax, eax
0x1800e38ed  jns     short loc_1800E3917
0x1800e38ef  mov     r9d, eax; char *
0x1800e38f2  lea     r8, aOnecoreuapBase_133; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e38f9  mov     edx, 9ECh; void *
0x1800e38fe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e3903  cmp     r14d, esi
0x1800e3906  jnz     short loc_1800E3917
0x1800e3908  mov     rdx, rbx
0x1800e390b  lea     rcx, aSrchgathersvcI_3; "[SrchGatherSvc] Index for user %s is ma"...
0x1800e3912  call    ?Log@ETWLog@@SAXPEB_WZZ; ETWLog::Log(wchar_t const *,...)
0x1800e3917  lea     r8, [rsp+248h+var_1D8]
0x1800e391c  mov     rdx, rbx; wchar_t *
0x1800e391f  mov     rcx, [r15+178h]; this
0x1800e3926  call    ?LoadUserCatalog@CGatherApplicationCollection@@QEAAJPEB_WPEBV?$vector@VReIndexPatternInfo@@V?$allocator@VReIndexPatternInfo@@@std@@@std@@@Z; CGatherApplicationCollection::LoadUserCatalog(wchar_t const *,std::vector<ReIndexPatternInfo> const *)
0x1800e392b  mov     rcx, [rsp+248h]; this
0x1800e3933  test    eax, eax
0x1800e3935  jns     loc_1800E3CA5
0x1800e393b  mov     r9d, eax; char *
0x1800e393e  lea     r8, aOnecoreuapBase_133; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e3945  mov     edx, 9F5h; void *
0x1800e394a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e394f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55683212@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55683212@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55683212> `wil::Feature<__WilFeatureTraits_Feature_55683212>::GetImpl(void)'::`2'::impl
0x1800e3956  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55683212@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55683212>::__private_IsEnabled(void)
0x1800e395b  test    al, al
0x1800e395d  jz      short loc_1800E3975
0x1800e395f  mov     edx, 3E8h
0x1800e3964  mov     rcx, r15
0x1800e3967  call    ?SetBulkIndexingStateFromReason@CGatheringService@@QEAAJW4INDEXER_BULK_INDEXING_REASON@@@Z; CGatheringService::SetBulkIndexingStateFromReason(INDEXER_BULK_INDEXING_REASON)
0x1800e396c  jmp     short loc_1800E3975
0x1800e396e  mov     r14, 0FFFFFFFF80000003h
0x1800e3975  mov     rdx, rbx
0x1800e3978  lea     rcx, aSrchgathersvcL_1; "[SrchGatherSvc] Logon for user %s as cr"...
0x1800e397f  call    ?Log@ETWLog@@SAXPEB_WZZ; ETWLog::Log(wchar_t const *,...)
0x1800e3984  mov     rcx, [rsp+248h+lpFileName]; this
0x1800e398c  call    ?DelNode@FSOp@@YAHPEB_WHK@Z; FSOp::DelNode(wchar_t const *,int,ulong)
0x1800e3991  mov     rdx, rbx
0x1800e3994  lea     rcx, [rsp+248h+lpSubKey]
0x1800e399c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800e39a1  nop
0x1800e39a2  mov     r8d, 41h ; 'A'
0x1800e39a8  lea     rdx, aSoftwareMicros_25; "\\Software\\Microsoft\\Windows Search\\"...
0x1800e39af  lea     rcx, [rsp+248h+lpSubKey]; Src
0x1800e39b7  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800e39bc  mov     qword ptr [rsp+248h+var_1E8], r12
0x1800e39c1  lea     rcx, [rsp+248h+var_1E8]
0x1800e39c6  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800e39cb  lea     rdx, [rsp+248h+lpSubKey]
0x1800e39d3  cmp     [rsp+248h+var_1A8], 7
0x1800e39dc  cmova   rdx, [rsp+248h+lpSubKey]; lpSubKey
0x1800e39e5  mov     [rsp+248h+lpdwDisposition], r12; lpdwDisposition
0x1800e39ea  mov     [rsp+248h+phkResult], rax; phkResult
0x1800e39ef  mov     [rsp+248h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800e39f4  mov     dword ptr [rsp+248h+pcbData], 0F003Fh; samDesired
0x1800e39fc  mov     dword ptr [rsp+248h+pvData], r12d; unsigned int
0x1800e3a01  xor     r9d, r9d; lpClass
0x1800e3a04  xor     r8d, r8d; Reserved
0x1800e3a07  mov     rcx, r14; hKey
0x1800e3a0a  call    cs:__imp_RegCreateKeyExW
0x1800e3a10  mov     rcx, [rsp+248h]; this
0x1800e3a18  test    eax, eax
0x1800e3a1a  jz      short loc_1800E3A30
0x1800e3a1c  mov     r9d, eax; char *
0x1800e3a1f  lea     r8, aOnecoreuapBase_133; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e3a26  mov     edx, 0A0Ch; void *
0x1800e3a2b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800e3a30  mov     rdx, rbx
0x1800e3a33  lea     rcx, [rsp+248h+lpSubKey]
0x1800e3a3b  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800e3a40  mov     r8d, 29h ; ')'
0x1800e3a46  lea     rdx, aSoftwareMicros_11; "\\Software\\Microsoft\\Windows Search\\"...
0x1800e3a4d  lea     rcx, [rsp+248h+lpSubKey]; Src
0x1800e3a55  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800e3a5a  mov     qword ptr [rsp+248h+pdwType], r12
0x1800e3a5f  lea     rcx, [rsp+248h+pdwType]
0x1800e3a64  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800e3a69  lea     rdx, [rsp+248h+lpSubKey]
0x1800e3a71  cmp     [rsp+248h+var_1A8], 7
0x1800e3a7a  cmova   rdx, [rsp+248h+lpSubKey]; lpSubKey
0x1800e3a83  mov     [rsp+248h+lpdwDisposition], r12; lpdwDisposition
0x1800e3a88  mov     [rsp+248h+phkResult], rax; phkResult
0x1800e3a8d  mov     [rsp+248h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800e3a92  mov     dword ptr [rsp+248h+pcbData], 0F003Fh; samDesired
0x1800e3a9a  mov     dword ptr [rsp+248h+pvData], r12d; unsigned int
0x1800e3a9f  xor     r9d, r9d; lpClass
0x1800e3aa2  xor     r8d, r8d; Reserved
0x1800e3aa5  mov     rcx, r14; hKey
0x1800e3aa8  call    cs:__imp_RegCreateKeyExW
0x1800e3aae  mov     rcx, [rsp+248h]; this
0x1800e3ab6  test    eax, eax
0x1800e3ab8  jz      short loc_1800E3ACE
0x1800e3aba  mov     r9d, eax; char *
0x1800e3abd  lea     r8, aOnecoreuapBase_133; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e3ac4  mov     edx, 0A1Bh; void *
0x1800e3ac9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800e3ace  mov     dword ptr [rsp+248h+Data], 4020000h
0x1800e3ad6  mov     dword ptr [rsp+248h+pcbData], esi; cbData
0x1800e3ada  lea     rax, [rsp+248h+Data]
0x1800e3adf  mov     [rsp+248h+pvData], rax; unsigned int
0x1800e3ae4  mov     r9d, esi; dwType
0x1800e3ae7  xor     r8d, r8d; Reserved
0x1800e3aea  lea     rdx, aRegversion; "RegVersion"
0x1800e3af1  mov     rcx, qword ptr [rsp+248h+pdwType]; hKey
0x1800e3af6  call    cs:__imp_RegSetValueExW
0x1800e3afc  mov     rcx, [rsp+248h]; this
0x1800e3b04  test    eax, eax
0x1800e3b06  jz      short loc_1800E3B1C
0x1800e3b08  mov     r9d, eax; char *
0x1800e3b0b  lea     r8, aOnecoreuapBase_133; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e3b12  mov     edx, 0A1Fh; void *
0x1800e3b17  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800e3b1c  mov     dword ptr [rsp+248h+Data], r12d
0x1800e3b21  mov     dword ptr [rsp+248h+pcbData], esi; cbData
0x1800e3b25  lea     rax, [rsp+248h+Data]
0x1800e3b2a  mov     [rsp+248h+pvData], rax; unsigned int
0x1800e3b2f  mov     r9d, esi; dwType
0x1800e3b32  xor     r8d, r8d; Reserved
0x1800e3b35  lea     rdx, aDebugtranfiles; "DebugTranFiles"
0x1800e3b3c  mov     rcx, qword ptr [rsp+248h+pdwType]; hKey
0x1800e3b41  call    cs:__imp_RegSetValueExW
0x1800e3b47  mov     rcx, [rsp+248h]; this
0x1800e3b4f  test    eax, eax
0x1800e3b51  jz      short loc_1800E3B67
0x1800e3b53  mov     r9d, eax; char *
0x1800e3b56  lea     r8, aOnecoreuapBase_133; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e3b5d  mov     edx, 0A23h; void *
0x1800e3b62  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800e3b67  mov     dword ptr [rsp+248h+Data], 1
0x1800e3b6f  mov     dword ptr [rsp+248h+pcbData], esi; cbData
0x1800e3b73  lea     rax, [rsp+248h+Data]
0x1800e3b78  mov     [rsp+248h+pvData], rax; int
0x1800e3b7d  mov     r9d, esi; dwType
0x1800e3b80  xor     r8d, r8d; Reserved
0x1800e3b83  lea     rdx, aLowdiskminimum; "LowDiskMinimumMBytes"
0x1800e3b8a  mov     rcx, qword ptr [rsp+248h+pdwType]; hKey
0x1800e3b8f  call    cs:__imp_RegSetValueExW
0x1800e3b95  mov     rcx, [rsp+248h]; this
0x1800e3b9d  test    eax, eax
0x1800e3b9f  jz      short loc_1800E3BB5
0x1800e3ba1  mov     r9d, eax; char *
0x1800e3ba4  lea     r8, aOnecoreuapBase_133; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e3bab  mov     edx, 0A2Ch; void *
0x1800e3bb0  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800e3bb5  mov     rcx, rbx; wchar_t *
0x1800e3bb8  call    ?WriteCatalogVersion@@YAJPEB_W@Z; WriteCatalogVersion(wchar_t const *)
0x1800e3bbd  mov     rcx, [rsp+248h]; this
0x1800e3bc5  test    eax, eax
0x1800e3bc7  jns     short loc_1800E3BDD
0x1800e3bc9  mov     r9d, eax; char *
0x1800e3bcc  lea     r8, aOnecoreuapBase_133; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e3bd3  mov     edx, 0A2Eh; void *
0x1800e3bd8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e3bdd  mov     rcx, rbx; this
0x1800e3be0  call    ?SetupPerUserCatalog@PropertySchemaInspection@@YAJPEB_W@Z; PropertySchemaInspection::SetupPerUserCatalog(wchar_t const *)
0x1800e3be5  mov     rcx, [rsp+248h]; this
0x1800e3bed  test    eax, eax
0x1800e3bef  jns     short loc_1800E3C05
  ... truncated ...
```
