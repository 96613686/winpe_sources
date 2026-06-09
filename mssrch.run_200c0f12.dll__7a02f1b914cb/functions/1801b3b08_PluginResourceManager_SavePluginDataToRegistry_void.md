# PluginResourceManager::SavePluginDataToRegistry(void)

- ea: `0x1801b3b08`
- end: `0x1801b4292`
- name: `?SavePluginDataToRegistry@PluginResourceManager@@AEAAJXZ`
- size: `1930`
- prototype: `__int64 __fastcall(PluginResourceManager *__hidden this)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801b2ff0`

## callees

- `0x18001d8a0`
- `0x18002bf00`
- `0x180054730`
- `0x1800555f0`
- `0x180055ac4`
- `0x1800569e0`
- `0x180075a40`
- `0x18008db70`
- `0x18009f1f0`
- `0x1800b0760`
- `0x1800e2374`
- `0x1800e95f0`
- `0x1801244c0`
- `0x1801b2684`
- `0x1801b26c8`
- `0x1801b2834`
- `0x1801b29b4`
- `0x1801b2b4c`
- `0x1801b2bd4`
- `0x1801b2ed8`
- `0x1801b3b08`
- `0x1801b4910`
- `0x1801b4aec`
- `0x1801b4bdc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3b70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3ba9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3e23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3b70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3ba9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3e23`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801b3f8a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801b3f8a`

## string_xrefs

- `0x1801b41da`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\pluginresourcemanager.cxx`
- `0x1801b41ef`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\pluginresourcemanager.cxx`
- `0x1801b4204`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\pluginresourcemanager.cxx`
- `0x1801b4216`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\pluginresourcemanager.cxx`
- `0x1801b4227`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\pluginresourcemanager.cxx`
- `0x1801b4238`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\pluginresourcemanager.cxx`
- `0x1801b4249`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\pluginresourcemanager.cxx`
- `0x1801b425a`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\pluginresourcemanager.cxx`
- `0x1801b426b`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\pluginresourcemanager.cxx`
- `0x1801b427f`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\pluginresourcemanager.cxx`
- `0x1801b3b84`: `PluginResourceData`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall PluginResourceManager::SavePluginDataToRegistry(PluginResourceManager *this)
{
  const char *v2; // r9
  const char *v3; // r9
  char IsEnabled; // al
  __int64 v5; // rdx
  bool v6; // r15
  __int64 *v7; // rbx
  __int64 *v8; // rdi
  __int64 *v9; // rbx
  _OWORD *v10; // rcx
  _OWORD *v11; // rdx
  _OWORD *v12; // r8
  __int64 result; // rax
  const wchar_t **v14; // rdi
  const wchar_t *v15; // rdx
  const char *v16; // r9
  const wchar_t *v18; // r8
  const char *v19; // r9
  const char *v20; // r9
  const char *v21; // r9
  const char *v22; // r9
  const char *v23; // r9
  const char *v24; // r9
  const OLECHAR *v25; // rcx
  HRESULT v26; // eax
  GUID v27; // xmm6
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // rcx
  const wchar_t *v35; // [rsp+20h] [rbp-378h]
  int v36; // [rsp+20h] [rbp-378h]
  __int128 v37; // [rsp+30h] [rbp-368h] BYREF
  __int64 v38; // [rsp+40h] [rbp-358h]
  __int128 v39; // [rsp+48h] [rbp-350h] BYREF
  _OWORD *v40; // [rsp+58h] [rbp-340h]
  _DWORD v41[4]; // [rsp+60h] [rbp-338h] BYREF
  _BYTE v42[8]; // [rsp+70h] [rbp-328h] BYREF
  __int64 *v43; // [rsp+78h] [rbp-320h]
  __int64 v44; // [rsp+80h] [rbp-318h]
  _BYTE v45[16]; // [rsp+B0h] [rbp-2E8h] BYREF
  GUID v46; // [rsp+C0h] [rbp-2D8h] BYREF
  _BYTE v47[28]; // [rsp+D0h] [rbp-2C8h]
  GUID pclsid; // [rsp+F0h] [rbp-2A8h] BYREF
  _BYTE v49[192]; // [rsp+100h] [rbp-298h] BYREF
  _BYTE v50[192]; // [rsp+1C0h] [rbp-1D8h] BYREF
  _BYTE v51[192]; // [rsp+280h] [rbp-118h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+0h]

  wil::EnterCriticalSection(v41, (char *)this + 152);
  try
  {
    CRegistry::CRegistry((CRegistry *)v51, HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows Search", 0x20006u, v35);
    if ( GetLastError() )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xF0,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\pluginresourcemanager.cxx",
        v2);
    CRegistry::CRegistry((CRegistry *)v50, (struct CRegistry *)v51, L"PluginResourceData", 0x20006u);
    if ( GetLastError() )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xF3,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\pluginresourcemanager.cxx",
        v3);
    v37 = 0;
    v38 = 0;
    std::unordered_map<std::wstring,SearchIndexerPluginIsolationTelemetry::PluginData>::unordered_map<std::wstring,SearchIndexerPluginIsolationTelemetry::PluginData>(v42);
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_59360409>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_59360409>::GetImpl'::`2'::impl);
    v5 = *((_QWORD *)this + 5);
    if ( IsEnabled )
    {
      std::_Hash<std::_Umap_traits<std::wstring,SearchIndexerPluginIsolationTelemetry::PluginData,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,SearchIndexerPluginIsolationTelemetry::PluginData>>,0>>::reserve(
        v42,
        v5);
      v6 = *((_BYTE *)this + 208) == 0;
    }
    else
    {
      v6 = 1;
      std::vector<SearchIndexerPluginIsolationTelemetry::PluginData>::reserve(&v37, v5);
    }
    v7 = (__int64 *)*((_QWORD *)this + 4);
    while ( 1 )
    {
      v7 = (__int64 *)*v7;
      if ( v7 == *((__int64 **)this + 4) )
        break;
      v14 = (const wchar_t **)(v7 + 2);
      if ( (unsigned __int64)v7[5] <= 7 )
        v15 = (const wchar_t *)(v7 + 2);
      else
        v15 = *v14;
      if ( !(unsigned int)CRegistry::CreateSubKey((CRegistry *)v50, v15) && GetLastError() != 183 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x10C,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\pluginresourcemanager.cxx",
          v16);
      *((_DWORD *)v7 + 15) = 0;
      if ( (unsigned __int64)v7[5] <= 7 )
        v18 = (const wchar_t *)(v7 + 2);
      else
        v18 = *v14;
      CRegistry::CRegistry((CRegistry *)v49, (struct CRegistry *)v50, v18, 0x20006u);
      if ( !(unsigned int)CRegistry::SetValue((CRegistry *)v49, L"CpuCycles", *((_DWORD *)v7 + 13)) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x112,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\pluginresourcemanager.cxx",
          v19);
      if ( !(unsigned int)CRegistry::SetValue((CRegistry *)v49, L"CpuMax", *((_DWORD *)v7 + 12)) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x113,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\pluginresourcemanager.cxx",
          v20);
      if ( !(unsigned int)CRegistry::SetValue((CRegistry *)v49, L"Memory", *((_DWORD *)v7 + 14)) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x114,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\pluginresourcemanager.cxx",
          v21);
      if ( !(unsigned int)CRegistry::SetValue((CRegistry *)v49, L"PenaltyBox", *((_DWORD *)v7 + 15)) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x115,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\pluginresourcemanager.cxx",
          v22);
      if ( !(unsigned int)CRegistry::SetValue((CRegistry *)v49, L"Duration", *((_DWORD *)v7 + 16)) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x116,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\pluginresourcemanager.cxx",
          v23);
      if ( !(unsigned int)CRegistry::SetValue((CRegistry *)v49, L"Items", *((_DWORD *)v7 + 17)) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x117,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\pluginresourcemanager.cxx",
          v24);
      pclsid = 0;
      if ( (unsigned __int64)v7[5] <= 7 )
        v25 = (const OLECHAR *)(v7 + 2);
      else
        v25 = *v14;
      v26 = CLSIDFromString(v25, &pclsid);
      if ( v26 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x11A,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\pluginresourcemanager.cxx",
          (const char *)(unsigned int)v26,
          v36);
      *(_WORD *)&v47[25] = 0;
      v47[27] = 0;
      v27 = pclsid;
      v46 = pclsid;
      *(_DWORD *)v47 = *((_DWORD *)v7 + 12);
      *(_QWORD *)&v47[4] = v7[7];
      *(_DWORD *)&v47[16] = *((_DWORD *)v7 + 16);
      *(_DWORD *)&v47[20] = *((_DWORD *)v7 + 17);
      *(_DWORD *)&v47[12] = *((_DWORD *)v7 + 13);
      v47[24] = *(_DWORD *)&v47[8] < *((_DWORD *)this + 49);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59360409>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_59360409>::GetImpl'::`2'::impl) )
      {
        std::_Hash<std::_Umap_traits<std::wstring,SearchIndexerPluginIsolationTelemetry::PluginData,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,SearchIndexerPluginIsolationTelemetry::PluginData>>,0>>::emplace<std::wstring const &,SearchIndexerPluginIsolationTelemetry::PluginData &>(
          v42,
          v45,
          v7 + 2,
          &v46);
        if ( !v6 && *((_BYTE *)this + 208) )
        {
          v29 = std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring>(
                  v28,
                  v7 + 2);
          v30 = *(_QWORD *)(std::_Hash<std::_Umap_traits<std::wstring,SearchIndexerPluginIsolationTelemetry::PluginData,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,SearchIndexerPluginIsolationTelemetry::PluginData>>,0>>::_Find_last<std::wstring>(
                              (char *)this + 216,
                              &v39,
                              v7 + 2,
                              v29)
                          + 8);
          if ( !v30 )
            v30 = *((_QWORD *)this + 28);
          if ( v30 == *((_QWORD *)this + 28)
            || *(_DWORD *)(v30 + 64) != *(_DWORD *)v47
            || (v32 = v30 + 48, *(_QWORD *)(v32 + 20) != *(_QWORD *)&v47[4])
            || *(_DWORD *)(v32 + 32) != *(_DWORD *)&v47[16]
            || *(_DWORD *)(v32 + 36) != *(_DWORD *)&v47[20]
            || *(_DWORD *)(v32 + 28) != *(_DWORD *)&v47[12]
            || *(_BYTE *)(v32 + 40) != v47[24]
            || !(unsigned int)InlineIsEqualGUID(v32, &v46, v31) )
          {
            v6 = 1;
          }
        }
      }
      else
      {
        v33 = *((_QWORD *)&v37 + 1);
        if ( *((_QWORD *)&v37 + 1) == v38 )
        {
          std::vector<SearchIndexerPluginIsolationTelemetry::PluginData>::_Emplace_reallocate<SearchIndexerPluginIsolationTelemetry::PluginData const &>(
            &v37,
            *((_QWORD *)&v37 + 1),
            &v46);
          v34 = *((_QWORD *)&v37 + 1);
        }
        else
        {
          **((_OWORD **)&v37 + 1) = v27;
          *(_OWORD *)(v33 + 16) = *(_OWORD *)v47;
          *(_OWORD *)(v33 + 28) = *(_OWORD *)&v47[12];
          v34 = *((_QWORD *)&v37 + 1) + 44LL;
          *((_QWORD *)&v37 + 1) += 44LL;
        }
        if ( 0x2E8BA2E8BA2E8BA3LL * ((v34 - (__int64)v37) >> 2) == 100
                                                                 * (0x2E8BA2E8BA2E8BA3LL
                                                                  * ((v34 - (__int64)v37) >> 2)
                                                                  / 0x64uLL) )
        {
          SearchIndexerPluginIsolationTelemetry::PluginIsolationProperties<std::vector<SearchIndexerPluginIsolationTelemetry::PluginData> &>(&v37);
          if ( (_QWORD)v37 != *((_QWORD *)&v37 + 1) )
            *((_QWORD *)&v37 + 1) = v37;
        }
      }
      CRegistry::~CRegistry((CRegistry *)v49);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59360409>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_59360409>::GetImpl'::`2'::impl) )
    {
      if ( v6 || *((_BYTE *)this + 208) && v44 != *((_QWORD *)this + 29) )
      {
        v39 = 0;
        v40 = 0;
        std::vector<SearchIndexerPluginIsolationTelemetry::PluginData>::reserve(&v39, 100);
        v8 = v43;
        v9 = (__int64 *)*v43;
        v10 = (_OWORD *)*((_QWORD *)&v39 + 1);
        v11 = (_OWORD *)v39;
        while ( v9 != v8 )
        {
          v12 = v9 + 6;
          if ( v10 == v40 )
          {
            std::vector<SearchIndexerPluginIsolationTelemetry::PluginData>::_Emplace_reallocate<SearchIndexerPluginIsolationTelemetry::PluginData const &>(
              &v39,
              v10,
              v12);
            v10 = (_OWORD *)*((_QWORD *)&v39 + 1);
          }
          else
          {
            *v10 = *v12;
            v10[1] = *((_OWORD *)v9 + 4);
            *(_OWORD *)((char *)v10 + 28) = *(_OWORD *)((char *)v9 + 76);
            v10 = (_OWORD *)(*((_QWORD *)&v39 + 1) + 44LL);
            *((_QWORD *)&v39 + 1) += 44LL;
          }
          v11 = (_OWORD *)v39;
          if ( (_OWORD *)((char *)v10 - v39) == (_OWORD *)4400 )
          {
            SearchIndexerPluginIsolationTelemetry::PluginIsolationProperties<std::vector<SearchIndexerPluginIsolationTelemetry::PluginData> &>(&v39);
            v10 = (_OWORD *)*((_QWORD *)&v39 + 1);
            v11 = (_OWORD *)v39;
            if ( (_QWORD)v39 != *((_QWORD *)&v39 + 1) )
            {
              v10 = (_OWORD *)v39;
              *((_QWORD *)&v39 + 1) = v39;
            }
          }
          v9 = (__int64 *)*v9;
        }
        if ( v11 != v10 )
          SearchIndexerPluginIsolationTelemetry::PluginIsolationProperties<std::vector<SearchIndexerPluginIsolationTelemetry::PluginData> &>(&v39);
        *((_BYTE *)this + 208) = 1;
        std::_Hash<std::_Umap_traits<std::wstring,SearchIndexerPluginIsolationTelemetry::PluginData,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,SearchIndexerPluginIsolationTelemetry::PluginData>>,0>>::operator=(
          (char *)this + 216,
          v42);
        if ( (_QWORD)v39 )
          std::_Deallocate<16>(v39, 4 * ((__int64)((__int64)v40 - v39) >> 2));
      }
    }
    else if ( 0x2E8BA2E8BA2E8BA3LL * ((__int64)(*((_QWORD *)&v37 + 1) - v37) >> 2) )
    {
      SearchIndexerPluginIsolationTelemetry::PluginIsolationProperties<std::vector<SearchIndexerPluginIsolationTelemetry::PluginData> &>(&v37);
    }
    std::_Hash<std::_Umap_traits<std::wstring,SearchIndexerPluginIsolationTelemetry::PluginData,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,SearchIndexerPluginIsolationTelemetry::PluginData>>,0>>::~_Hash<std::_Umap_traits<std::wstring,SearchIndexerPluginIsolationTelemetry::PluginData,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,SearchIndexerPluginIsolationTelemetry::PluginData>>,0>>(v42);
    if ( (_QWORD)v37 )
    {
      std::_Deallocate<16>(v37, 4 * ((v38 - (__int64)v37) >> 2));
      v37 = 0;
      v38 = 0;
    }
    CRegistry::~CRegistry((CRegistry *)v50);
    CRegistry::~CRegistry((CRegistry *)v51);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v41);
    result = 0;
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      365,
      "onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\pluginresourcemanager.cxx");
  }
  return result;
}

```

## disassembly

```asm
0x1801b3b08  mov     rax, rsp
0x1801b3b0b  push    rbx
0x1801b3b0c  push    rsi
0x1801b3b0d  push    rdi
0x1801b3b0e  push    r13
0x1801b3b10  push    r14
0x1801b3b12  push    r15
0x1801b3b14  sub     rsp, 368h
0x1801b3b1b  movaps  xmmword ptr [rax-48h], xmm6
0x1801b3b1f  mov     rax, cs:__security_cookie
0x1801b3b26  xor     rax, rsp
0x1801b3b29  mov     [rsp+398h+var_58], rax
0x1801b3b31  mov     rsi, rcx
0x1801b3b34  lea     rdx, [rcx+98h]
0x1801b3b3b  lea     rcx, [rsp+398h+var_338]
0x1801b3b40  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1801b3b45  nop
0x1801b3b46  mov     r9d, 20006h; unsigned int
0x1801b3b4c  lea     r8, aSoftwareMicros_13; "Software\\Microsoft\\Windows Search"
0x1801b3b53  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1801b3b5a  lea     rcx, [rsp+398h+var_118]; this
0x1801b3b62  call    ??0CRegistry@@QEAA@PEAUHKEY__@@PEB_WK1@Z; CRegistry::CRegistry(HKEY__ *,wchar_t const *,ulong,wchar_t const *)
0x1801b3b67  nop
0x1801b3b68  mov     rbx, [rsp+398h]
0x1801b3b70  call    cs:__imp_GetLastError
0x1801b3b76  test    eax, eax
0x1801b3b78  jnz     loc_1801B41DA
0x1801b3b7e  mov     r9d, 20006h; unsigned int
0x1801b3b84  lea     r8, aPluginresource; "PluginResourceData"
0x1801b3b8b  lea     rdx, [rsp+398h+var_118]; struct CRegistry *
0x1801b3b93  lea     rcx, [rsp+398h+var_1D8]; this
0x1801b3b9b  call    ??0CRegistry@@QEAA@PEAV0@PEB_WK@Z; CRegistry::CRegistry(CRegistry *,wchar_t const *,ulong)
0x1801b3ba0  nop
0x1801b3ba1  mov     rbx, [rsp+398h]
0x1801b3ba9  call    cs:__imp_GetLastError
0x1801b3baf  test    eax, eax
0x1801b3bb1  jnz     loc_1801B41EF
0x1801b3bb7  xorps   xmm0, xmm0
0x1801b3bba  movdqu  [rsp+398h+var_368], xmm0
0x1801b3bc0  mov     [rsp+398h+var_358], 0
0x1801b3bc9  lea     rcx, [rsp+398h+var_328]
0x1801b3bce  call    ??0?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UPluginData@SearchIndexerPluginIsolationTelemetry@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UPluginData@SearchIndexerPluginIsolationTelemetry@@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,SearchIndexerPluginIsolationTelemetry::PluginData>::unordered_map<std::wstring,SearchIndexerPluginIsolationTelemetry::PluginData>(void)
0x1801b3bd3  nop
0x1801b3bd4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59360409@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59360409@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59360409> `wil::Feature<__WilFeatureTraits_Feature_59360409>::GetImpl(void)'::`2'::impl
0x1801b3bdb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59360409@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59360409>::__private_IsEnabled(void)
0x1801b3be0  mov     rdx, [rsi+28h]
0x1801b3be4  test    al, al
0x1801b3be6  jz      short loc_1801B3BFF
0x1801b3be8  lea     rcx, [rsp+398h+var_328]
0x1801b3bed  call    ?reserve@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UPluginData@SearchIndexerPluginIsolationTelemetry@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UPluginData@SearchIndexerPluginIsolationTelemetry@@@std@@@2@$0A@@std@@@std@@QEAAX_K@Z; std::_Hash<std::_Umap_traits<std::wstring,SearchIndexerPluginIsolationTelemetry::PluginData,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,SearchIndexerPluginIsolationTelemetry::PluginData>>,0>>::reserve(unsigned __int64)
0x1801b3bf2  cmp     byte ptr [rsi+0D0h], 0
0x1801b3bf9  setz    r15b
0x1801b3bfd  jmp     short loc_1801B3C0C
0x1801b3bff  mov     r15b, 1
0x1801b3c02  lea     rcx, [rsp+398h+var_368]
0x1801b3c07  call    ?reserve@?$vector@UPluginData@SearchIndexerPluginIsolationTelemetry@@V?$allocator@UPluginData@SearchIndexerPluginIsolationTelemetry@@@std@@@std@@QEAAX_K@Z; std::vector<SearchIndexerPluginIsolationTelemetry::PluginData>::reserve(unsigned __int64)
0x1801b3c0c  mov     rbx, [rsi+20h]
0x1801b3c10  mov     r13, 2E8BA2E8BA2E8BA3h
0x1801b3c1a  mov     rbx, [rbx]
0x1801b3c1d  cmp     rbx, [rsi+20h]
0x1801b3c21  jnz     loc_1801B3DFF
0x1801b3c27  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59360409@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59360409@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59360409> `wil::Feature<__WilFeatureTraits_Feature_59360409>::GetImpl(void)'::`2'::impl
0x1801b3c2e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59360409@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59360409>::__private_IsEnabled(void)
0x1801b3c33  test    al, al
0x1801b3c35  jz      loc_1801B3D70
0x1801b3c3b  test    r15b, r15b
0x1801b3c3e  jnz     short loc_1801B3C62
0x1801b3c40  cmp     [rsi+0D0h], r15b
0x1801b3c47  jz      loc_1801B3D92
0x1801b3c4d  mov     rax, [rsi+0E8h]
0x1801b3c54  cmp     [rsp+398h+var_318], rax
0x1801b3c5c  jz      loc_1801B3D92
0x1801b3c62  xorps   xmm0, xmm0
0x1801b3c65  movdqu  [rsp+398h+var_350], xmm0
0x1801b3c6b  mov     [rsp+398h+var_340], 0
0x1801b3c74  mov     edx, 64h ; 'd'
0x1801b3c79  lea     rcx, [rsp+398h+var_350]
0x1801b3c7e  call    ?reserve@?$vector@UPluginData@SearchIndexerPluginIsolationTelemetry@@V?$allocator@UPluginData@SearchIndexerPluginIsolationTelemetry@@@std@@@std@@QEAAX_K@Z; std::vector<SearchIndexerPluginIsolationTelemetry::PluginData>::reserve(unsigned __int64)
0x1801b3c83  mov     rdi, [rsp+398h+var_320]
0x1801b3c88  mov     rbx, [rdi]
0x1801b3c8b  mov     rcx, qword ptr [rsp+398h+var_350+8]
0x1801b3c90  mov     rdx, qword ptr [rsp+398h+var_350]
0x1801b3c95  cmp     rbx, rdi
0x1801b3c98  jnz     short loc_1801B3CEE
0x1801b3c9a  cmp     rdx, rcx
0x1801b3c9d  jz      short loc_1801B3CA9
0x1801b3c9f  lea     rcx, [rsp+398h+var_350]
0x1801b3ca4  call    ??$PluginIsolationProperties@AEAV?$vector@UPluginData@SearchIndexerPluginIsolationTelemetry@@V?$allocator@UPluginData@SearchIndexerPluginIsolationTelemetry@@@std@@@std@@@SearchIndexerPluginIsolationTelemetry@@SAXAEAV?$vector@UPluginData@SearchIndexerPluginIsolationTelemetry@@V?$allocator@UPluginData@SearchIndexerPluginIsolationTelemetry@@@std@@@std@@@Z; SearchIndexerPluginIsolationTelemetry::PluginIsolationProperties<std::vector<SearchIndexerPluginIsolationTelemetry::PluginData> &>(std::vector<SearchIndexerPluginIsolationTelemetry::PluginData> &)
0x1801b3ca9  mov     byte ptr [rsi+0D0h], 1
0x1801b3cb0  lea     rcx, [rsi+0D8h]
0x1801b3cb7  lea     rdx, [rsp+398h+var_328]
0x1801b3cbc  call    ??4?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UPluginData@SearchIndexerPluginIsolationTelemetry@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UPluginData@SearchIndexerPluginIsolationTelemetry@@@std@@@2@$0A@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::_Hash<std::_Umap_traits<std::wstring,SearchIndexerPluginIsolationTelemetry::PluginData,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,SearchIndexerPluginIsolationTelemetry::PluginData>>,0>>::operator=(std::_Hash<std::_Umap_traits<std::wstring,SearchIndexerPluginIsolationTelemetry::PluginData,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,SearchIndexerPluginIsolationTelemetry::PluginData>>,0>> &&)
0x1801b3cc1  nop
0x1801b3cc2  mov     rcx, qword ptr [rsp+398h+var_350]
0x1801b3cc7  test    rcx, rcx
0x1801b3cca  jz      loc_1801B3D92
0x1801b3cd0  mov     rax, [rsp+398h+var_340]
0x1801b3cd5  sub     rax, rcx
0x1801b3cd8  sar     rax, 2
0x1801b3cdc  imul    rax, r13
0x1801b3ce0  imul    rdx, rax, 2Ch ; ','
0x1801b3ce4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801b3ce9  jmp     loc_1801B3D92
0x1801b3cee  lea     r8, [rbx+30h]
0x1801b3cf2  cmp     rcx, [rsp+398h+var_340]
0x1801b3cf7  jz      short loc_1801B3D22
0x1801b3cf9  movups  xmm0, xmmword ptr [r8]
0x1801b3cfd  movups  xmmword ptr [rcx], xmm0
0x1801b3d00  movups  xmm1, xmmword ptr [r8+10h]
0x1801b3d05  movups  xmmword ptr [rcx+10h], xmm1
0x1801b3d09  movups  xmm0, xmmword ptr [r8+1Ch]
0x1801b3d0e  movups  xmmword ptr [rcx+1Ch], xmm0
0x1801b3d12  mov     rcx, qword ptr [rsp+398h+var_350+8]
0x1801b3d17  add     rcx, 2Ch ; ','
0x1801b3d1b  mov     qword ptr [rsp+398h+var_350+8], rcx
0x1801b3d20  jmp     short loc_1801B3D34
0x1801b3d22  mov     rdx, rcx
0x1801b3d25  lea     rcx, [rsp+398h+var_350]
0x1801b3d2a  call    ??$_Emplace_reallocate@AEBUPluginData@SearchIndexerPluginIsolationTelemetry@@@?$vector@UPluginData@SearchIndexerPluginIsolationTelemetry@@V?$allocator@UPluginData@SearchIndexerPluginIsolationTelemetry@@@std@@@std@@AEAAPEAUPluginData@SearchIndexerPluginIsolationTelemetry@@QEAU23@AEBU23@@Z; std::vector<SearchIndexerPluginIsolationTelemetry::PluginData>::_Emplace_reallocate<SearchIndexerPluginIsolationTelemetry::PluginData const &>(SearchIndexerPluginIsolationTelemetry::PluginData * const,SearchIndexerPluginIsolationTelemetry::PluginData const &)
0x1801b3d2f  mov     rcx, qword ptr [rsp+398h+var_350+8]
0x1801b3d34  mov     rax, rcx
0x1801b3d37  mov     rdx, qword ptr [rsp+398h+var_350]
0x1801b3d3c  sub     rax, rdx
0x1801b3d3f  cmp     rax, 1130h
0x1801b3d45  jnz     short loc_1801B3D68
0x1801b3d47  lea     rcx, [rsp+398h+var_350]
0x1801b3d4c  call    ??$PluginIsolationProperties@AEAV?$vector@UPluginData@SearchIndexerPluginIsolationTelemetry@@V?$allocator@UPluginData@SearchIndexerPluginIsolationTelemetry@@@std@@@std@@@SearchIndexerPluginIsolationTelemetry@@SAXAEAV?$vector@UPluginData@SearchIndexerPluginIsolationTelemetry@@V?$allocator@UPluginData@SearchIndexerPluginIsolationTelemetry@@@std@@@std@@@Z; SearchIndexerPluginIsolationTelemetry::PluginIsolationProperties<std::vector<SearchIndexerPluginIsolationTelemetry::PluginData> &>(std::vector<SearchIndexerPluginIsolationTelemetry::PluginData> &)
0x1801b3d51  mov     rdx, qword ptr [rsp+398h+var_350]
0x1801b3d56  mov     rcx, qword ptr [rsp+398h+var_350+8]
0x1801b3d5b  cmp     rdx, rcx
0x1801b3d5e  jz      short loc_1801B3D68
0x1801b3d60  mov     rcx, rdx
0x1801b3d63  mov     qword ptr [rsp+398h+var_350+8], rdx
0x1801b3d68  mov     rbx, [rbx]
0x1801b3d6b  jmp     loc_1801B3C95
0x1801b3d70  mov     rax, qword ptr [rsp+398h+var_368+8]
0x1801b3d75  sub     rax, qword ptr [rsp+398h+var_368]
0x1801b3d7a  sar     rax, 2
0x1801b3d7e  imul    rax, r13
0x1801b3d82  test    rax, rax
0x1801b3d85  jz      short loc_1801B3D92
0x1801b3d87  lea     rcx, [rsp+398h+var_368]
0x1801b3d8c  call    ??$PluginIsolationProperties@AEAV?$vector@UPluginData@SearchIndexerPluginIsolationTelemetry@@V?$allocator@UPluginData@SearchIndexerPluginIsolationTelemetry@@@std@@@std@@@SearchIndexerPluginIsolationTelemetry@@SAXAEAV?$vector@UPluginData@SearchIndexerPluginIsolationTelemetry@@V?$allocator@UPluginData@SearchIndexerPluginIsolationTelemetry@@@std@@@std@@@Z; SearchIndexerPluginIsolationTelemetry::PluginIsolationProperties<std::vector<SearchIndexerPluginIsolationTelemetry::PluginData> &>(std::vector<SearchIndexerPluginIsolationTelemetry::PluginData> &)
0x1801b3d91  nop
0x1801b3d92  lea     rcx, [rsp+398h+var_328]
0x1801b3d97  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UPluginData@SearchIndexerPluginIsolationTelemetry@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UPluginData@SearchIndexerPluginIsolationTelemetry@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,SearchIndexerPluginIsolationTelemetry::PluginData,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,SearchIndexerPluginIsolationTelemetry::PluginData>>,0>>::~_Hash<std::_Umap_traits<std::wstring,SearchIndexerPluginIsolationTelemetry::PluginData,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,SearchIndexerPluginIsolationTelemetry::PluginData>>,0>>(void)
0x1801b3d9c  nop
0x1801b3d9d  mov     rcx, qword ptr [rsp+398h+var_368]
0x1801b3da2  test    rcx, rcx
0x1801b3da5  jz      short loc_1801B3DD2
0x1801b3da7  mov     rax, [rsp+398h+var_358]
0x1801b3dac  sub     rax, rcx
0x1801b3daf  sar     rax, 2
0x1801b3db3  imul    rax, r13
0x1801b3db7  imul    rdx, rax, 2Ch ; ','
0x1801b3dbb  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801b3dc0  xorps   xmm0, xmm0
0x1801b3dc3  movdqu  [rsp+398h+var_368], xmm0
0x1801b3dc9  mov     [rsp+398h+var_358], 0
0x1801b3dd2  lea     rcx, [rsp+398h+var_1D8]; this
0x1801b3dda  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x1801b3ddf  nop
0x1801b3de0  lea     rcx, [rsp+398h+var_118]; this
0x1801b3de8  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x1801b3ded  nop
0x1801b3dee  lea     rcx, [rsp+398h+var_338]
0x1801b3df3  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1801b3df8  xor     eax, eax
0x1801b3dfa  jmp     loc_1801B41B1
0x1801b3dff  lea     rdi, [rbx+10h]
0x1801b3e03  cmp     qword ptr [rbx+28h], 7
0x1801b3e08  jbe     short loc_1801B3E0F
0x1801b3e0a  mov     rdx, [rdi]
0x1801b3e0d  jmp     short loc_1801B3E12
0x1801b3e0f  mov     rdx, rdi; wchar_t *
0x1801b3e12  lea     rcx, [rsp+398h+var_1D8]; this
0x1801b3e1a  call    ?CreateSubKey@CRegistry@@UEAAHPEB_W@Z; CRegistry::CreateSubKey(wchar_t const *)
0x1801b3e1f  test    eax, eax
0x1801b3e21  jnz     short loc_1801B3E34
0x1801b3e23  call    cs:__imp_GetLastError
0x1801b3e29  cmp     eax, 0B7h
0x1801b3e2e  jz      short loc_1801B3E34
0x1801b3e30  mov     al, 1
0x1801b3e32  jmp     short loc_1801B3E36
0x1801b3e34  xor     al, al
0x1801b3e36  mov     rcx, [rsp+398h]; this
0x1801b3e3e  test    al, al
0x1801b3e40  jnz     loc_1801B4204
0x1801b3e46  mov     dword ptr [rbx+3Ch], 0
0x1801b3e4d  cmp     qword ptr [rbx+28h], 7
0x1801b3e52  jbe     short loc_1801B3E59
0x1801b3e54  mov     r8, [rdi]
0x1801b3e57  jmp     short loc_1801B3E5C
0x1801b3e59  mov     r8, rdi; wchar_t *
0x1801b3e5c  mov     r9d, 20006h; unsigned int
0x1801b3e62  lea     rdx, [rsp+398h+var_1D8]; struct CRegistry *
0x1801b3e6a  lea     rcx, [rsp+398h+var_298]; this
0x1801b3e72  call    ??0CRegistry@@QEAA@PEAV0@PEB_WK@Z; CRegistry::CRegistry(CRegistry *,wchar_t const *,ulong)
0x1801b3e77  nop
0x1801b3e78  mov     r8d, [rbx+34h]; unsigned int
0x1801b3e7c  lea     rdx, aCpucycles; "CpuCycles"
0x1801b3e83  lea     rcx, [rsp+398h+var_298]; this
0x1801b3e8b  call    ?SetValue@CRegistry@@QEAAHPEB_WK@Z; CRegistry::SetValue(wchar_t const *,ulong)
0x1801b3e90  mov     rcx, [rsp+398h]; this
0x1801b3e98  test    eax, eax
0x1801b3e9a  jz      loc_1801B4216
0x1801b3ea0  mov     r8d, [rbx+30h]; unsigned int
0x1801b3ea4  lea     rdx, aCpumax; "CpuMax"
0x1801b3eab  lea     rcx, [rsp+398h+var_298]; this
0x1801b3eb3  call    ?SetValue@CRegistry@@QEAAHPEB_WK@Z; CRegistry::SetValue(wchar_t const *,ulong)
0x1801b3eb8  mov     rcx, [rsp+398h]; this
0x1801b3ec0  test    eax, eax
0x1801b3ec2  jz      loc_1801B4227
0x1801b3ec8  mov     r8d, [rbx+38h]; unsigned int
0x1801b3ecc  lea     rdx, aMemory; "Memory"
0x1801b3ed3  lea     rcx, [rsp+398h+var_298]; this
0x1801b3edb  call    ?SetValue@CRegistry@@QEAAHPEB_WK@Z; CRegistry::SetValue(wchar_t const *,ulong)
0x1801b3ee0  mov     rcx, [rsp+398h]; this
0x1801b3ee8  test    eax, eax
0x1801b3eea  jz      loc_1801B4238
0x1801b3ef0  mov     r8d, [rbx+3Ch]; unsigned int
0x1801b3ef4  lea     rdx, aPenaltybox; "PenaltyBox"
0x1801b3efb  lea     rcx, [rsp+398h+var_298]; this
0x1801b3f03  call    ?SetValue@CRegistry@@QEAAHPEB_WK@Z; CRegistry::SetValue(wchar_t const *,ulong)
0x1801b3f08  mov     rcx, [rsp+398h]; this
0x1801b3f10  test    eax, eax
0x1801b3f12  jz      loc_1801B4249
0x1801b3f18  mov     r8d, [rbx+40h]; unsigned int
0x1801b3f1c  lea     rdx, aDuration; "Duration"
0x1801b3f23  lea     rcx, [rsp+398h+var_298]; this
0x1801b3f2b  call    ?SetValue@CRegistry@@QEAAHPEB_WK@Z; CRegistry::SetValue(wchar_t const *,ulong)
0x1801b3f30  mov     rcx, [rsp+398h]; this
0x1801b3f38  test    eax, eax
0x1801b3f3a  jz      loc_1801B425A
0x1801b3f40  mov     r8d, [rbx+44h]; unsigned int
0x1801b3f44  lea     rdx, aItems; "Items"
0x1801b3f4b  lea     rcx, [rsp+398h+var_298]; this
0x1801b3f53  call    ?SetValue@CRegistry@@QEAAHPEB_WK@Z; CRegistry::SetValue(wchar_t const *,ulong)
0x1801b3f58  mov     rcx, [rsp+398h]; this
0x1801b3f60  test    eax, eax
0x1801b3f62  jz      loc_1801B426B
0x1801b3f68  xorps   xmm0, xmm0
0x1801b3f6b  movups  xmmword ptr [rsp+398h+pclsid.Data1], xmm0
0x1801b3f73  cmp     qword ptr [rbx+28h], 7
0x1801b3f78  jbe     short loc_1801B3F7F
0x1801b3f7a  mov     rcx, [rdi]
0x1801b3f7d  jmp     short loc_1801B3F82
0x1801b3f7f  mov     rcx, rdi; lpsz
0x1801b3f82  lea     rdx, [rsp+398h+pclsid]; pclsid
0x1801b3f8a  call    cs:__imp_CLSIDFromString
0x1801b3f90  mov     rcx, [rsp+398h]; this
0x1801b3f98  test    eax, eax
0x1801b3f9a  js      loc_1801B427C
0x1801b3fa0  xor     eax, eax
0x1801b3fa2  mov     [rsp+398h+var_2AF], ax
0x1801b3faa  mov     [rsp+398h+var_2AD], al
0x1801b3fb1  movups  xmm6, xmmword ptr [rsp+398h+pclsid.Data1]
0x1801b3fb9  movups  [rsp+398h+var_2D8], xmm6
0x1801b3fc1  mov     eax, [rbx+30h]
0x1801b3fc4  mov     dword ptr [rsp+398h+var_2C8], eax
0x1801b3fcb  mov     eax, [rbx+38h]
0x1801b3fce  mov     dword ptr [rsp+398h+var_2C8+4], eax
0x1801b3fd5  mov     ecx, [rbx+3Ch]
0x1801b3fd8  mov     dword ptr [rsp+398h+var_2C8+8], ecx
0x1801b3fdf  mov     eax, [rbx+40h]
0x1801b3fe2  mov     [rsp+398h+var_2B8], eax
0x1801b3fe9  mov     eax, [rbx+44h]
0x1801b3fec  mov     [rsp+398h+var_2B4], eax
0x1801b3ff3  mov     eax, [rbx+34h]
0x1801b3ff6  mov     dword ptr [rsp+398h+var_2C8+0Ch], eax
0x1801b3ffd  cmp     ecx, [rsi+0C4h]
0x1801b4003  setb    [rsp+398h+var_2B0]
0x1801b400b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59360409@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59360409@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59360409> `wil::Feature<__WilFeatureTraits_Feature_59360409>::GetImpl(void)'::`2'::impl
0x1801b4012  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59360409@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59360409>::__private_IsEnabled(void)
0x1801b4017  test    al, al
0x1801b4019  jz      loc_1801B40FF
0x1801b401f  lea     r9, [rsp+398h+var_2D8]
0x1801b4027  mov     r8, rdi
0x1801b402a  lea     rdx, [rsp+398h+var_2E8]
0x1801b4032  lea     rcx, [rsp+398h+var_328]
0x1801b4037  call    ??$emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAUPluginData@SearchIndexerPluginIsolationTelemetry@@@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UPluginData@SearchIndexerPluginIsolationTelemetry@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UPluginData@SearchIndexerPluginIsolationTelemetry@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UPluginData@SearchIndexerPluginIsolationTelemetry@@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAUPluginData@SearchIndexerPluginIsolationTelemetry@@@Z; std::_Hash<std::_Umap_traits<std::wstring,SearchIndexerPluginIsolationTelemetry::PluginData,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,SearchIndexerPluginIsolationTelemetry::PluginData>>,0>>::emplace<std::wstring const &,SearchIndexerPluginIsolationTelemetry::PluginData &>(std::wstring const &,SearchIndexerPluginIsolationTelemetry::PluginData &)
0x1801b403c  test    r15b, r15b
0x1801b403f  jnz     loc_1801B419B
0x1801b4045  cmp     [rsi+0D0h], r15b
0x1801b404c  jz      loc_1801B419B
0x1801b4052  lea     r14, [rsi+0D8h]
0x1801b4059  mov     rdx, rdi
0x1801b405c  call    ??$?RV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEBA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring>(std::wstring const &)
0x1801b4061  mov     r9, rax
0x1801b4064  mov     r8, rdi
0x1801b4067  lea     rdx, [rsp+398h+var_350]
0x1801b406c  mov     rcx, r14
0x1801b406f  call    ??$_Find_last@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UPluginData@SearchIndexerPluginIsolationTelemetry@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UPluginData@SearchIndexerPluginIsolationTelemetry@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UPluginData@SearchIndexerPluginIsolationTelemetry@@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,SearchIndexerPluginIsolationTelemetry::PluginData,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,SearchIndexerPluginIsolationTelemetry::PluginData>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x1801b4074  mov     rcx, [rax+8]
0x1801b4078  test    rcx, rcx
0x1801b407b  jnz     short loc_1801B4081
0x1801b407d  mov     rcx, [r14+8]
0x1801b4081  cmp     rcx, [rsi+0E0h]
0x1801b4088  jz      short loc_1801B40F7
0x1801b408a  mov     eax, dword ptr [rsp+398h+var_2C8]
  ... truncated ...
```
