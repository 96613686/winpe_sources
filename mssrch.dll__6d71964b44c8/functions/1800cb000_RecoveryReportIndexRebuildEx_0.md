# RecoveryReportIndexRebuildEx_0

- ea: `0x1800cb000`
- end: `0x1800cb4e8`
- name: `RecoveryReportIndexRebuildEx_0`
- size: `1256`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18014256c`
- `0x1801429c0`

## callees

- `0x18000ee60`
- `0x18000f880`
- `0x180012120`
- `0x18002751c`
- `0x180052460`
- `0x180056b90`
- `0x18005e788`
- `0x18009491c`
- `0x1800a3a38`
- `0x1800b827c`
- `0x1800b837c`
- `0x1800cb000`
- `0x1800cccec`
- `0x1800ccd20`
- `0x1800ccda4`
- `0x1800d0214`
- `0x1800e1320`
- `0x1800e4710`
- `0x18010839c`
- `0x1801244c0`
- `0x1801249ec`
- `0x18013dd98`
- `0x180141a94`
- `0x1801422c0`
- `0x180142870`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800cb33a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800cb33a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cb472`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cb472`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cb1f1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cb1f1`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800cb089`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800cb089`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1800cb23e`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1800cb467`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1800cb23e`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1800cb467`

## string_xrefs

- `0x1800cb230`: `SetupCompletedSuccessfully`
- `0x1800cb206`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`
- `0x1800cb253`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`
- `0x1800cb2ee`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall RecoveryReportIndexRebuildEx_0(int a1, struct CEventLog *a2, __int64 a3, __int64 a4, int a5, int a6)
{
  int v8; // edx
  int v9; // r8d
  char v10; // r15
  const wchar_t *v11; // rcx
  unsigned int v12; // r9d
  const wchar_t *Catalog; // rsi
  const size_t *v14; // rdx
  int v15; // edx
  HKEY *phkResult; // rax
  const WCHAR *v17; // rdx
  unsigned int Key; // eax
  unsigned int v19; // eax
  __int64 v20; // rax
  unsigned __int64 v21; // rdi
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // kr10_8
  wchar_t *v24; // rax
  unsigned int v25; // edi
  __int64 v26; // r9
  __int64 v27; // rdx
  int v28; // eax
  void *v29; // r11
  int v31; // eax
  bool v32; // sf
  const char *v33; // rax
  unsigned int dwOptions; // [rsp+20h] [rbp-A28h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-A28h]
  HKEY hkey; // [rsp+50h] [rbp-9F8h] BYREF
  int pvData; // [rsp+58h] [rbp-9F0h] BYREF
  HANDLE v38[2]; // [rsp+60h] [rbp-9E8h] BYREF
  int v39; // [rsp+70h] [rbp-9D8h] BYREF
  __int64 v40; // [rsp+78h] [rbp-9D0h]
  LPCWSTR lpSubKey[4]; // [rsp+80h] [rbp-9C8h] BYREF
  _BYTE v42[8]; // [rsp+A0h] [rbp-9A8h] BYREF
  _BYTE v43[160]; // [rsp+A8h] [rbp-9A0h] BYREF
  _BYTE v44[2248]; // [rsp+148h] [rbp-900h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A48h] [rbp+0h]

  v39 = 0;
  v40 = -1;
  CImpersonateSystem::MakePrivileged((CImpersonateSystem *)&v39);
  if ( a1 == 3 )
  {
    v10 = 1;
    LogIndexCorruptionEx((_DWORD)a2, v8, v9, a5, a6);
  }
  else
  {
    v10 = 0;
  }
  InitOnceExecuteOnce(
    &g_initOnceOnPerUserCatalogCheck,
    _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( g_isPerUserCatalogEnabled && PerUserCatalogNameForCorruption::GetCatalog() )
  {
    Catalog = (const wchar_t *)PerUserCatalogNameForCorruption::GetCatalog();
    v38[0] = (HANDLE)Catalog;
    if ( a2 )
    {
      CSearchEventEntry::CSearchEventEntry((CSearchEventEntry *)v42, a2);
      v14 = &cchOriginalDestLength;
      if ( Catalog )
        v14 = (const size_t *)Catalog;
      CLMString::operator=(v43, v14);
      CLMString::operator=(v44, &cchOriginalDestLength);
      v15 = -1073473535;
      if ( !v10 )
        v15 = a6;
      CSearchEventEntry::SetError((CSearchEventEntry *)v42, v15);
      if ( v10 )
      {
        CSearchEventEntry::ReportError((CSearchEventEntry *)v42, 0xC0001B80, L"The catalog is corrupt", 0);
      }
      else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54644696>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54644696>::GetImpl'::`2'::impl) )
      {
        CSearchEventEntry::ReportError((CSearchEventEntry *)v42, 0xC0001B83, L"The index must be rebuilt.", 0);
      }
      else
      {
        CSearchEventEntry::ReportError((CSearchEventEntry *)v42, 0xC0001B83, L"The index must be rebuilt.");
      }
      CSearchEventEntry::~CSearchEventEntry((CSearchEventEntry *)v42);
    }
    try
    {
      std::wstring::wstring(lpSubKey, Catalog);
      std::wstring::_Append<wchar_t>(lpSubKey);
      hkey = 0;
      phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hkey);
      v17 = (const WCHAR *)lpSubKey;
      if ( lpSubKey[3] > (LPCWSTR)7 )
        v17 = lpSubKey[0];
      Key = RegCreateKeyExW(HKEY_USERS, v17, 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
      if ( Key )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xF7,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h",
          (const char *)Key,
          dwOptions);
      pvData = 0;
      v19 = SHSetValueW(hkey, 0, L"SetupCompletedSuccessfully", 4u, &pvData, 4u);
      if ( v19 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xFB,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h",
          (const char *)v19,
          dwOptionsa);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)lpSubKey);
    }
    catch ( ... )
    {
      indexer::result::details::result_from_caught_exception<1>(
        retaddr,
        253,
        "onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h");
    }
    v20 = -1;
    do
      ++v20;
    while ( Catalog[v20] );
    v21 = v20 + 1;
    v23 = v20 + 1;
    v22 = 2 * (v20 + 1);
    if ( !is_mul_ok(v23, 2u) )
      v22 = -1;
    v24 = (wchar_t *)operator new[](v22, (const struct std::nothrow_t *)&std::nothrow);
    hkey = (HKEY)v24;
    if ( !v24 )
    {
      v25 = -2147024882;
      v26 = 2147942414LL;
      v27 = 257;
LABEL_32:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v27,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h",
        (const char *)v26,
        dwOptionsa);
      std::unique_ptr<enum gsl::byte [0]>::~unique_ptr<enum gsl::byte [0]>(&hkey);
      CImpersonateSystem::~CImpersonateSystem((CImpersonateSystem *)&v39);
      return v25;
    }
    v28 = StringCchCopyW(v24, v21, Catalog);
    v25 = v28;
    if ( v28 < 0 )
    {
      v26 = (unsigned int)v28;
      v27 = 259;
      goto LABEL_32;
    }
    hkey = 0;
    v38[0] = CreateThread(0, 0, ResetUserCatalog, v29, 0, 0);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v38);
    std::unique_ptr<enum gsl::byte [0]>::~unique_ptr<enum gsl::byte [0]>(&hkey);
  }
  else
  {
    if ( !v10 && a2 )
    {
      CSearchEventEntry::CSearchEventEntry((CSearchEventEntry *)v42, a2);
      CLMString::operator=(v43, &cchOriginalDestLength);
      CLMString::operator=(v44, &cchOriginalDestLength);
      CSearchEventEntry::SetError((CSearchEventEntry *)v42, a6);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54644696>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54644696>::GetImpl'::`2'::impl) )
        CSearchEventEntry::ReportError((CSearchEventEntry *)v42, 0xC0001B83, L"The index must be rebuilt.", 0);
      else
        CSearchEventEntry::ReportError((CSearchEventEntry *)v42, 0xC0001B83, L"The index must be rebuilt.");
      CSearchEventEntry::~CSearchEventEntry((CSearchEventEntry *)v42);
    }
    hkey = 0;
    v31 = WSearchRegOpenKeyEx(v11, HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Search", v12, 0xF003Fu, &hkey);
    v32 = v31 < 0;
    if ( v31 > 0 )
      v32 = 1;
    if ( !v32 )
    {
      pvData = a1;
      SHSetValueW(hkey, 0, L"RebuildIndex", 4u, &pvData, 4u);
      RegCloseKey(hkey);
    }
    if ( !g_fStopLogged )
    {
      v33 = L"The catalog is corrupt";
      if ( !v10 )
        v33 = L"The index must be rebuilt.";
      ShutdownSelf(a2, (__int64)v33);
      g_fStopLogged = 1;
    }
  }
  CImpersonateSystem::~CImpersonateSystem((CImpersonateSystem *)&v39);
  return 0;
}

```

## disassembly

```asm
0x1800cb000  mov     [rsp+arg_8], rbx
0x1800cb005  mov     [rsp+arg_10], rsi
0x1800cb00a  push    rdi
0x1800cb00b  push    r12
0x1800cb00d  push    r13
0x1800cb00f  push    r14
0x1800cb011  push    r15
0x1800cb013  sub     rsp, 0A20h
0x1800cb01a  mov     rax, cs:__security_cookie
0x1800cb021  xor     rax, rsp
0x1800cb024  mov     [rsp+0A48h+var_38], rax
0x1800cb02c  mov     r14, rdx
0x1800cb02f  mov     esi, ecx
0x1800cb031  mov     r13d, [rsp+0A48h+arg_28]
0x1800cb039  xor     ebx, ebx
0x1800cb03b  mov     [rsp+0A48h+var_9D8], ebx
0x1800cb03f  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800cb043  mov     [rsp+0A48h+var_9D0], r12
0x1800cb048  lea     rcx, [rsp+0A48h+var_9D8]; this
0x1800cb04d  call    ?MakePrivileged@CImpersonateSystem@@AEAAXXZ; CImpersonateSystem::MakePrivileged(void)
0x1800cb052  nop
0x1800cb053  cmp     esi, 3
0x1800cb056  jnz     short loc_1800CB072
0x1800cb058  mov     r15b, 1
0x1800cb05b  mov     [rsp+0A48h+dwOptions], r13d
0x1800cb060  mov     r9d, [rsp+0A48h+arg_20]
0x1800cb068  mov     rcx, r14
0x1800cb06b  call    LogIndexCorruptionEx
0x1800cb070  jmp     short loc_1800CB075
0x1800cb072  mov     r15b, bl
0x1800cb075  xor     r9d, r9d; Context
0x1800cb078  xor     r8d, r8d; Parameter
0x1800cb07b  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800cb082  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x1800cb089  call    cs:__imp_InitOnceExecuteOnce
0x1800cb08f  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, bl; bool g_isPerUserCatalogEnabled
0x1800cb095  jz      loc_1800CB35E
0x1800cb09b  call    PerUserCatalogNameForCorruption__GetCatalog
0x1800cb0a0  test    rax, rax
0x1800cb0a3  jz      loc_1800CB35E
0x1800cb0a9  call    PerUserCatalogNameForCorruption__GetCatalog
0x1800cb0ae  mov     rsi, rax
0x1800cb0b1  mov     [rsp+0A48h+var_9E8], rax
0x1800cb0b6  test    r14, r14
0x1800cb0b9  jz      loc_1800CB175
0x1800cb0bf  mov     rdx, r14; struct CEventLog *
0x1800cb0c2  lea     rcx, [rsp+0A48h+var_9A8]; this
0x1800cb0ca  call    ??0CSearchEventEntry@@QEAA@PEAVCEventLog@@@Z; CSearchEventEntry::CSearchEventEntry(CEventLog *)
0x1800cb0cf  nop
0x1800cb0d0  lea     rdx, cchOriginalDestLength
0x1800cb0d7  test    rsi, rsi
0x1800cb0da  cmovnz  rdx, rsi
0x1800cb0de  lea     rcx, [rsp+0A48h+var_9A0]
0x1800cb0e6  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800cb0eb  lea     rdx, cchOriginalDestLength
0x1800cb0f2  lea     rcx, [rsp+0A48h+var_900]
0x1800cb0fa  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800cb0ff  mov     edx, 0C0041801h
0x1800cb104  test    r15b, r15b
0x1800cb107  cmovz   edx, r13d; int
0x1800cb10b  lea     rcx, [rsp+0A48h+var_9A8]; this
0x1800cb113  call    ?SetError@CSearchEventEntry@@QEAAXJ@Z; CSearchEventEntry::SetError(long)
0x1800cb118  test    r15b, r15b
0x1800cb11b  jz      short loc_1800CB133
0x1800cb11d  lea     r8, aTheCatalogIsCo; "The catalog is corrupt"
0x1800cb124  mov     edx, 0C0001B80h
0x1800cb129  lea     rcx, [rsp+0A48h+var_9A8]
0x1800cb131  jmp     short loc_1800CB157
0x1800cb133  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_54644696@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_54644696@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_54644696> `wil::Feature<__WilFeatureTraits_Feature_54644696>::GetImpl(void)'::`2'::impl
0x1800cb13a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_54644696@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_54644696>::__private_IsEnabled(void)
0x1800cb13f  lea     r8, aTheIndexMustBe; "The index must be rebuilt."
0x1800cb146  mov     edx, 0C0001B83h; unsigned int
0x1800cb14b  lea     rcx, [rsp+0A48h+var_9A8]; this
0x1800cb153  test    al, al
0x1800cb155  jz      short loc_1800CB161
0x1800cb157  xor     r9d, r9d
0x1800cb15a  call    ?ReportError@CSearchEventEntry@@QEAAXKZZ; CSearchEventEntry::ReportError(ulong,...)
0x1800cb15f  jmp     short loc_1800CB167
0x1800cb161  call    ?ReportError@CSearchEventEntry@@QEAAXKZZ; CSearchEventEntry::ReportError(ulong,...)
0x1800cb166  nop
0x1800cb167  lea     rcx, [rsp+0A48h+var_9A8]; this
0x1800cb16f  call    ??1CSearchEventEntry@@QEAA@XZ; CSearchEventEntry::~CSearchEventEntry(void)
0x1800cb174  nop
0x1800cb175  mov     rdx, rsi
0x1800cb178  lea     rcx, [rsp+0A48h+lpSubKey]
0x1800cb180  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800cb185  nop
0x1800cb186  mov     r8d, 22h ; '"'
0x1800cb18c  lea     rdx, aSoftwareMicros_14; "\\SOFTWARE\\Microsoft\\Windows Search"
0x1800cb193  lea     rcx, [rsp+0A48h+lpSubKey]; Src
0x1800cb19b  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800cb1a0  mov     [rsp+0A48h+hkey], rbx
0x1800cb1a5  lea     rcx, [rsp+0A48h+hkey]
0x1800cb1aa  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800cb1af  lea     rdx, [rsp+0A48h+lpSubKey]
0x1800cb1b7  cmp     [rsp+0A48h+var_9B0], 7
0x1800cb1c0  cmova   rdx, [rsp+0A48h+lpSubKey]; lpSubKey
0x1800cb1c9  mov     [rsp+0A48h+lpdwDisposition], rbx; lpdwDisposition
0x1800cb1ce  mov     [rsp+0A48h+phkResult], rax; phkResult
0x1800cb1d3  mov     [rsp+0A48h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1800cb1d8  mov     [rsp+0A48h+samDesired], 0F003Fh; samDesired
0x1800cb1e0  mov     [rsp+0A48h+dwOptions], ebx; unsigned int
0x1800cb1e4  xor     r9d, r9d; lpClass
0x1800cb1e7  xor     r8d, r8d; Reserved
0x1800cb1ea  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800cb1f1  call    cs:__imp_RegCreateKeyExW
0x1800cb1f7  mov     rcx, [rsp+0A48h]; this
0x1800cb1ff  test    eax, eax
0x1800cb201  jz      short loc_1800CB217
0x1800cb203  mov     r9d, eax; char *
0x1800cb206  lea     r8, aOnecoreuapBase_145; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800cb20d  mov     edx, 0F7h; void *
0x1800cb212  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800cb217  mov     [rsp+0A48h+pvData], ebx
0x1800cb21b  mov     r9d, 4; dwType
0x1800cb221  mov     [rsp+0A48h+samDesired], r9d; cbData
0x1800cb226  lea     rax, [rsp+0A48h+pvData]
0x1800cb22b  mov     qword ptr [rsp+0A48h+dwOptions], rax; unsigned int
0x1800cb230  lea     r8, pszValue; "SetupCompletedSuccessfully"
0x1800cb237  xor     edx, edx; pszSubKey
0x1800cb239  mov     rcx, [rsp+0A48h+hkey]; hkey
0x1800cb23e  call    cs:__imp_SHSetValueW
0x1800cb244  mov     rcx, [rsp+0A48h]; this
0x1800cb24c  test    eax, eax
0x1800cb24e  jz      short loc_1800CB265
0x1800cb250  mov     r9d, eax; char *
0x1800cb253  lea     r8, aOnecoreuapBase_145; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800cb25a  mov     edx, 0FBh; void *
0x1800cb25f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800cb265  lea     rcx, [rsp+0A48h+hkey]
0x1800cb26a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cb26f  nop
0x1800cb270  lea     rcx, [rsp+0A48h+lpSubKey]; this
0x1800cb278  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x1800cb27d  nop
0x1800cb27e  jmp     short loc_1800CB28B
0x1800cb280  xor     ebx, ebx
0x1800cb282  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800cb286  mov     rsi, [rsp+0A48h+var_9E8]
0x1800cb28b  mov     rax, r12
0x1800cb28e  inc     rax
0x1800cb291  cmp     [rsi+rax*2], bx
0x1800cb295  jnz     short loc_1800CB28E
0x1800cb297  lea     rdi, [rax+1]
0x1800cb29b  mov     eax, 2
0x1800cb2a0  mul     rdi
0x1800cb2a3  cmovb   rax, r12
0x1800cb2a7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800cb2ae  mov     rcx, rax; unsigned __int64
0x1800cb2b1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800cb2b6  mov     r11, rax
0x1800cb2b9  mov     [rsp+0A48h+hkey], rax
0x1800cb2be  test    rax, rax
0x1800cb2c1  jnz     short loc_1800CB2D2
0x1800cb2c3  mov     edi, 8007000Eh
0x1800cb2c8  mov     r9d, edi
0x1800cb2cb  mov     edx, 101h
0x1800cb2d0  jmp     short loc_1800CB2EE
0x1800cb2d2  mov     r8, rsi; wchar_t *
0x1800cb2d5  mov     rdx, rdi; unsigned __int64
0x1800cb2d8  mov     rcx, r11; wchar_t *
0x1800cb2db  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800cb2e0  mov     edi, eax
0x1800cb2e2  test    eax, eax
0x1800cb2e4  jns     short loc_1800CB31E
0x1800cb2e6  mov     r9d, eax; char *
0x1800cb2e9  mov     edx, 103h; void *
0x1800cb2ee  lea     r8, aOnecoreuapBase_145; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800cb2f5  mov     rcx, [rsp+0A48h]; this
0x1800cb2fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cb302  lea     rcx, [rsp+0A48h+hkey]
0x1800cb307  call    ??1?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAA@XZ; std::unique_ptr<gsl::byte [0]>::~unique_ptr<gsl::byte [0]>(void)
0x1800cb30c  nop
0x1800cb30d  lea     rcx, [rsp+0A48h+var_9D8]; this
0x1800cb312  call    ??1CImpersonateSystem@@QEAA@XZ; CImpersonateSystem::~CImpersonateSystem(void)
0x1800cb317  mov     eax, edi
0x1800cb319  jmp     loc_1800CB4BB
0x1800cb31e  mov     [rsp+0A48h+hkey], rbx
0x1800cb323  mov     qword ptr [rsp+0A48h+samDesired], rbx; lpThreadId
0x1800cb328  mov     [rsp+0A48h+dwOptions], ebx; dwCreationFlags
0x1800cb32c  mov     r9, r11; lpParameter
0x1800cb32f  lea     r8, ResetUserCatalog; lpStartAddress
0x1800cb336  xor     edx, edx; dwStackSize
0x1800cb338  xor     ecx, ecx; lpThreadAttributes
0x1800cb33a  call    cs:__imp_CreateThread
0x1800cb340  mov     [rsp+0A48h+var_9E8], rax
0x1800cb345  lea     rcx, [rsp+0A48h+var_9E8]
0x1800cb34a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800cb34f  lea     rcx, [rsp+0A48h+hkey]
0x1800cb354  call    ??1?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAA@XZ; std::unique_ptr<gsl::byte [0]>::~unique_ptr<gsl::byte [0]>(void)
0x1800cb359  jmp     loc_1800CB4AF
0x1800cb35e  test    r15b, r15b
0x1800cb361  jnz     loc_1800CB3FF
0x1800cb367  test    r14, r14
0x1800cb36a  jz      loc_1800CB3FF
0x1800cb370  mov     rdx, r14; struct CEventLog *
0x1800cb373  lea     rcx, [rsp+0A48h+var_9A8]; this
0x1800cb37b  call    ??0CSearchEventEntry@@QEAA@PEAVCEventLog@@@Z; CSearchEventEntry::CSearchEventEntry(CEventLog *)
0x1800cb380  nop
0x1800cb381  lea     rdx, cchOriginalDestLength
0x1800cb388  lea     rcx, [rsp+0A48h+var_9A0]
0x1800cb390  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800cb395  lea     rdx, cchOriginalDestLength
0x1800cb39c  lea     rcx, [rsp+0A48h+var_900]
0x1800cb3a4  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800cb3a9  mov     edx, r13d; int
0x1800cb3ac  lea     rcx, [rsp+0A48h+var_9A8]; this
0x1800cb3b4  call    ?SetError@CSearchEventEntry@@QEAAXJ@Z; CSearchEventEntry::SetError(long)
0x1800cb3b9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_54644696@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_54644696@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_54644696> `wil::Feature<__WilFeatureTraits_Feature_54644696>::GetImpl(void)'::`2'::impl
0x1800cb3c0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_54644696@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_54644696>::__private_IsEnabled(void)
0x1800cb3c5  lea     rdi, aTheIndexMustBe; "The index must be rebuilt."
0x1800cb3cc  mov     edx, 0C0001B83h; unsigned int
0x1800cb3d1  lea     rcx, [rsp+0A48h+var_9A8]; this
0x1800cb3d9  mov     r8, rdi
0x1800cb3dc  test    al, al
0x1800cb3de  jz      short loc_1800CB3EA
0x1800cb3e0  xor     r9d, r9d
0x1800cb3e3  call    ?ReportError@CSearchEventEntry@@QEAAXKZZ; CSearchEventEntry::ReportError(ulong,...)
0x1800cb3e8  jmp     short loc_1800CB3F0
0x1800cb3ea  call    ?ReportError@CSearchEventEntry@@QEAAXKZZ; CSearchEventEntry::ReportError(ulong,...)
0x1800cb3ef  nop
0x1800cb3f0  lea     rcx, [rsp+0A48h+var_9A8]; this
0x1800cb3f8  call    ??1CSearchEventEntry@@QEAA@XZ; CSearchEventEntry::~CSearchEventEntry(void)
0x1800cb3fd  jmp     short loc_1800CB406
0x1800cb3ff  lea     rdi, aTheIndexMustBe; "The index must be rebuilt."
0x1800cb406  mov     [rsp+0A48h+hkey], rbx
0x1800cb40b  lea     rax, [rsp+0A48h+hkey]
0x1800cb410  mov     qword ptr [rsp+0A48h+samDesired], rax; HKEY *
0x1800cb415  mov     [rsp+0A48h+dwOptions], 0F003Fh; unsigned int
0x1800cb41d  lea     r8, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows Search"
0x1800cb424  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1800cb42b  call    ?WSearchRegOpenKeyEx@@YAJPEB_WPEAUHKEY__@@0KKPEAPEAU1@@Z; WSearchRegOpenKeyEx(wchar_t const *,HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x1800cb430  test    eax, eax
0x1800cb432  jle     short loc_1800CB43E
0x1800cb434  movzx   eax, ax
0x1800cb437  or      eax, 80070000h
0x1800cb43c  test    eax, eax
0x1800cb43e  js      short loc_1800CB478
0x1800cb440  mov     [rsp+0A48h+pvData], esi
0x1800cb444  mov     r9d, 4; dwType
0x1800cb44a  mov     [rsp+0A48h+samDesired], r9d; cbData
0x1800cb44f  lea     rax, [rsp+0A48h+pvData]
0x1800cb454  mov     qword ptr [rsp+0A48h+dwOptions], rax; pvData
0x1800cb459  lea     r8, aRebuildindex; "RebuildIndex"
0x1800cb460  xor     edx, edx; pszSubKey
0x1800cb462  mov     rcx, [rsp+0A48h+hkey]; hkey
0x1800cb467  call    cs:__imp_SHSetValueW
0x1800cb46d  mov     rcx, [rsp+0A48h+hkey]; hKey
0x1800cb472  call    cs:__imp_RegCloseKey
0x1800cb478  cmp     cs:?g_fStopLogged@@3HA, ebx; int g_fStopLogged
0x1800cb47e  jnz     short loc_1800CB4AF
0x1800cb480  lea     rax, aTheCatalogIsCo; "The catalog is corrupt"
0x1800cb487  test    r15b, r15b
0x1800cb48a  cmovz   rax, rdi
0x1800cb48e  mov     r9d, 0C0041801h
0x1800cb494  cmovz   r9d, r13d
0x1800cb498  mov     qword ptr [rsp+0A48h+dwOptions], rax; __int64
0x1800cb49d  mov     rcx, r14; struct CEventLog *
0x1800cb4a0  call    ShutdownSelf
0x1800cb4a5  mov     cs:?g_fStopLogged@@3HA, 1; int g_fStopLogged
0x1800cb4af  lea     rcx, [rsp+0A48h+var_9D8]; this
0x1800cb4b4  call    ??1CImpersonateSystem@@QEAA@XZ; CImpersonateSystem::~CImpersonateSystem(void)
0x1800cb4b9  xor     eax, eax
0x1800cb4bb  mov     rcx, [rsp+0A48h+var_38]
0x1800cb4c3  xor     rcx, rsp; StackCookie
0x1800cb4c6  call    __security_check_cookie
0x1800cb4cb  lea     r11, [rsp+0A48h+var_28]
0x1800cb4d3  mov     rbx, [r11+38h]
0x1800cb4d7  mov     rsi, [r11+40h]
0x1800cb4db  mov     rsp, r11
0x1800cb4de  pop     r15
0x1800cb4e0  pop     r14
0x1800cb4e2  pop     r13
0x1800cb4e4  pop     r12
0x1800cb4e6  pop     rdi
0x1800cb4e7  retn
```
