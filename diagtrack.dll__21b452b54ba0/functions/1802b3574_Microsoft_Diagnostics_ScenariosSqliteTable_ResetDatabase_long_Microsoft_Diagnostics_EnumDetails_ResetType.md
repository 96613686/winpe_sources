# Microsoft::Diagnostics::ScenariosSqliteTable::ResetDatabase(long,Microsoft::Diagnostics::EnumDetails::ResetType)

- ea: `0x1802b3574`
- end: `0x1802b3d25`
- name: `?ResetDatabase@ScenariosSqliteTable@Diagnostics@Microsoft@@AEAAXJVResetType@EnumDetails@23@@Z`
- size: `1969`
- prototype: ``
- caller_count: `3`
- callee_count: `34`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1801d6278`
- `0x1802b3450`
- `0x180351665`

## callees

- `0x18001dee8`
- `0x18001df2c`
- `0x180024558`
- `0x18002cb04`
- `0x18002df00`
- `0x1800346b0`
- `0x1800346dc`
- `0x180034c78`
- `0x180034e50`
- `0x180049bec`
- `0x18005d688`
- `0x18008a4ec`
- `0x1800b6204`
- `0x1800cf7d8`
- `0x1800d9294`
- `0x1800e99a0`
- `0x1800e9cd8`
- `0x1800ff00c`
- `0x1801042b4`
- `0x180142fcc`
- `0x180166cf0`
- `0x1801bbc78`
- `0x1801cd84c`
- `0x1801daf18`
- `0x1801dfc6c`
- `0x1801e2d68`
- `0x1801e7070`
- `0x18020aac0`
- `0x1802b06e0`
- `0x1802b0d58`
- `0x1802b1f50`
- `0x1802b3574`
- `0x1802b4420`
- `0x1802b445c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1802b39df`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1802b39df`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1802b37b6`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1802b38a2`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1802b37b6`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1802b38a2`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerRegisterFile` at `0x1802b3b39`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerRegisterFile` at `0x1802b3cdd`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerRegisterFile` at `0x1802b3b39`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerRegisterFile` at `0x1802b3cdd`

## string_xrefs

- `0x1802b37c0`: `onecore\base\telemetry\utc\service\scenarios\base\scenariossqlitetable.cpp`
- `0x1802b38ac`: `onecore\base\telemetry\utc\service\scenarios\base\scenariossqlitetable.cpp`
- `0x1802b3b09`: `onecore\base\telemetry\utc\service\scenarios\base\scenariossqlitetable.cpp`
- `0x1802b3b52`: `onecore\base\telemetry\utc\service\scenarios\base\scenariossqlitetable.cpp`
- `0x1802b3cb7`: `onecore\base\telemetry\utc\service\scenarios\base\scenariossqlitetable.cpp`
- `0x1802b3cf9`: `onecore\base\telemetry\utc\service\scenarios\base\scenariossqlitetable.cpp`
- `0x1802b3d12`: `onecore\base\telemetry\utc\service\scenarios\base\scenariossqlitetable.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Microsoft::Diagnostics::ScenariosSqliteTable::ResetDatabase(__int64 a1, unsigned int a2, char a3)
{
  __int64 v6; // rdx
  __int64 v7; // rax
  int v8; // r8d
  int v9; // r9d
  char *v10; // rcx
  _QWORD *v11; // rbx
  __int64 v12; // rdx
  __int64 result; // rax
  const char *v14; // r9
  __int64 v15; // rax
  __int64 v16; // rax
  const WCHAR *v17; // rdx
  const WCHAR *v18; // rcx
  const char *v19; // r9
  __int64 v20; // rax
  __int64 v21; // rax
  const WCHAR *v22; // rdx
  const WCHAR *v23; // rcx
  const char *v24; // r9
  int v25; // r8d
  int v26; // r9d
  Microsoft::Diagnostics::ScenarioObjectCache *ScenarioObjectCache; // rax
  Microsoft::Diagnostics::ScenarioObjectCache *v28; // rax
  struct Microsoft::Diagnostics::ScenarioManager *ScenarioManager; // rax
  const WCHAR *v30; // rcx
  HRESULT v31; // eax
  unsigned int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  const WCHAR *v36; // rax
  unsigned int v37; // eax
  int v38; // eax
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-208h]
  int v41; // [rsp+20h] [rbp-208h]
  int v42; // [rsp+20h] [rbp-208h]
  int v43[4]; // [rsp+30h] [rbp-1F8h] BYREF
  _BYTE v44[16]; // [rsp+40h] [rbp-1E8h] BYREF
  _BYTE v45[16]; // [rsp+50h] [rbp-1D8h] BYREF
  _BYTE v46[240]; // [rsp+60h] [rbp-1C8h] BYREF
  __int64 v47; // [rsp+150h] [rbp-D8h] BYREF
  unsigned int v48; // [rsp+158h] [rbp-D0h]
  __int128 v49; // [rsp+160h] [rbp-C8h] BYREF
  __m128i v50; // [rsp+170h] [rbp-B8h]
  LPCWSTR lpNewFileName[2]; // [rsp+180h] [rbp-A8h] BYREF
  __m128i si128; // [rsp+190h] [rbp-98h]
  LPCWSTR lpExistingFileName; // [rsp+1A0h] [rbp-88h] BYREF
  __int64 v54; // [rsp+1A8h] [rbp-80h]
  unsigned int v55; // [rsp+1B0h] [rbp-78h]
  __int128 v56; // [rsp+1B8h] [rbp-70h]
  __m128i v57; // [rsp+1C8h] [rbp-60h]
  LPCWSTR *p_lpExistingFileName; // [rsp+1D8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  try
  {
    if ( (unsigned __int8)((__int64 (*)(void))wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScenarioCacheReconstruction>::__private_IsEnabled)() )
    {
      if ( a3 == 3 )
      {
        _InterlockedAdd((volatile signed __int32 *)(a1 + 304), 1u);
        if ( *(_DWORD *)(a1 + 304) >= 0x14u )
          a3 = 1;
      }
    }
    if ( (unsigned int)dword_1804543B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 16) )
    {
      Microsoft::Diagnostics::EnumDetails::ResetType::initialize();
      LOBYTE(v6) = a3;
      v7 = Microsoft::Diagnostics::EnumDetails::ResetType::_from_value_loop(v43, v6, 0);
      if ( *(_BYTE *)v7 )
        v10 = (&`Microsoft::Diagnostics::EnumDetails::better_enums::_data_ResetType::_name_array'::`2'::value)[*(_QWORD *)(v7 + 8)];
      else
        v10 = 0;
      *(_QWORD *)v43 = v10;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v10,
        (unsigned int)byte_1803F27C1,
        v8,
        v9,
        (__int64)v43);
    }
    std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(v44, a1 + 200);
    v11 = *(_QWORD **)(a1 + 280);
    std::_Tree_val<std::_Tree_simple_types<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>,void *>>>(
      a1 + 280,
      a1 + 280,
      v11[1]);
    v11[1] = v11;
    *v11 = v11;
    v11[2] = v11;
    *(_QWORD *)(a1 + 288) = 0;
    v12 = *(_QWORD *)(a1 + 40);
    *(_QWORD *)(a1 + 40) = 0;
    if ( v12 )
      std::default_delete<Microsoft::Diagnostics::SqlConnection>::operator()();
    *(_QWORD *)v43 = a1;
    if ( a3 == 2 )
    {
      Microsoft::Diagnostics::ScenariosSqliteTable::ResetDatabase_::_3_::_lambda_1_::operator()(v43);
      return std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v44);
    }
    *(_OWORD *)lpNewFileName = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(lpNewFileName[0]) = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScenarioCacheReconstruction>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ScenarioCacheReconstruction>::GetImpl'::`2'::impl) )
    {
      if ( a3 == 3 )
      {
LABEL_32:
        Microsoft::Diagnostics::ScenariosSqliteTable::ResetDatabase_::_3_::_lambda_1_::operator()(v43);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScenarioCacheReconstruction>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ScenarioCacheReconstruction>::GetImpl'::`2'::impl) )
        {
          if ( a3 )
          {
            if ( a3 == 1 )
            {
              v32 = wil::verify_hresult<long>(a2);
              wil::details::in1diag3::Log_Hr(
                retaddr,
                (void *)0x147,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariossqlitetable.cpp",
                (const char *)v32,
                v40);
              v36 = (const WCHAR *)std::wstring::c_str(lpNewFileName, v33, v34, v35);
              v37 = WerRegisterFile(v36, WerRegFileTypeOther, 1u);
              v38 = wil::verify_hresult<long>(v37);
              if ( v38 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x14A,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariossqlitetable.cpp",
                  (const char *)(unsigned int)v38,
                  v42);
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0x14B,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariossqlitetable.cpp",
                v39);
            }
            if ( a3 == 3 && !*(_BYTE *)(a1 + 308) )
            {
              if ( (unsigned int)dword_1804543B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 16) )
              {
                v43[0] = *(_DWORD *)(a1 + 304);
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                  (unsigned int)&dword_1804543B0,
                  (unsigned int)byte_1803F2771,
                  v25,
                  v26,
                  (__int64)v43);
              }
              *(_BYTE *)(a1 + 308) = 1;
              *(_DWORD *)(a1 + 48) = 0;
              Microsoft::Diagnostics::ScenariosSqliteTable::Initialize(
                (Microsoft::Diagnostics::ScenariosSqliteTable *)a1,
                1);
              if ( _InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_180463270, 0, 0) )
              {
                ScenarioObjectCache = Microsoft::Diagnostics::LifetimeManager::GetScenarioObjectCache((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                Microsoft::Diagnostics::ScenarioObjectCache::Clear(ScenarioObjectCache);
                v28 = Microsoft::Diagnostics::LifetimeManager::GetScenarioObjectCache((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                Microsoft::Diagnostics::ScenarioObjectCache::Clean(v28);
              }
              if ( _InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_180463150, 0, 0) )
              {
                ScenarioManager = Microsoft::Diagnostics::LifetimeManager::GetScenarioManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                SetEvent(*((HANDLE *)ScenarioManager + 11));
              }
            }
          }
          else
          {
            v47 = a1;
            v48 = a2;
            std::wstring::wstring(&v49, lpNewFileName);
            lpExistingFileName = (LPCWSTR)off_18037EA68;
            v54 = v47;
            v55 = v48;
            v56 = v49;
            v57 = v50;
            v50 = _mm_load_si128((const __m128i *)&_xmm);
            LOWORD(v49) = 0;
            p_lpExistingFileName = &lpExistingFileName;
            Microsoft::Diagnostics::TpSerialWork::Submit((_Mtx_t)(a1 + 80));
            std::function<bool (_GUID const &)>::~function<bool (_GUID const &)>(&lpExistingFileName);
            std::wstring::_Tidy_deallocate(&v49);
            Microsoft::Diagnostics::ScenariosSqliteTable::Initialize(
              (Microsoft::Diagnostics::ScenariosSqliteTable *)a1,
              1);
          }
        }
        else if ( a3 )
        {
          if ( a3 == 1 )
          {
            wil::details::in1diag3::Log_Hr(
              retaddr,
              (void *)0x17B,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariossqlitetable.cpp",
              (const char *)a2,
              v40);
            v30 = (const WCHAR *)lpNewFileName;
            if ( si128.m128i_i64[1] > 7uLL )
              v30 = lpNewFileName[0];
            v31 = WerRegisterFile(v30, WerRegFileTypeOther, 1u);
            if ( v31 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x17E,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariossqlitetable.cpp",
                (const char *)(unsigned int)v31,
                v41);
          }
        }
        else
        {
          v47 = a1;
          v48 = a2;
          std::wstring::wstring(&v49, lpNewFileName);
          lpExistingFileName = (LPCWSTR)off_18037EA98;
          v54 = v47;
          v55 = v48;
          v56 = v49;
          v57 = v50;
          v50 = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(v49) = 0;
          p_lpExistingFileName = &lpExistingFileName;
          Microsoft::Diagnostics::TpSerialWork::Submit((_Mtx_t)(a1 + 80));
          std::function<bool (_GUID const &)>::~function<bool (_GUID const &)>(&lpExistingFileName);
          std::wstring::_Tidy_deallocate(&v49);
          Microsoft::Diagnostics::ScenariosSqliteTable::Initialize(
            (Microsoft::Diagnostics::ScenariosSqliteTable *)a1,
            1);
        }
        std::wstring::_Tidy_deallocate(lpNewFileName);
        return std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v44);
      }
      std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v45);
      v15 = std::operator<<<wchar_t>(v46, a1 + 8);
      std::operator<<<wchar_t,std::char_traits<wchar_t>>(v15, L"\\EventStore.db");
      std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(v45, &lpExistingFileName);
      std::operator<<<wchar_t,std::char_traits<wchar_t>>(v46, L".bk");
      v16 = std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(v45, &v47);
      std::wstring::operator=(lpNewFileName, v16);
      std::wstring::_Tidy_deallocate(&v47);
      v17 = (const WCHAR *)lpNewFileName;
      if ( si128.m128i_i64[1] > 7uLL )
        v17 = lpNewFileName[0];
      v18 = (const WCHAR *)&lpExistingFileName;
      if ( (unsigned __int64)v56 > 7 )
        v18 = lpExistingFileName;
      if ( !CopyFileW(v18, v17, 1) )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x121,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariossqlitetable.cpp",
          v19);
    }
    else
    {
      std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v45);
      v20 = std::operator<<<wchar_t>(v46, a1 + 8);
      std::operator<<<wchar_t,std::char_traits<wchar_t>>(v20, L"\\EventStore.db");
      std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(v45, &lpExistingFileName);
      std::operator<<<wchar_t,std::char_traits<wchar_t>>(v46, L".bk");
      v21 = std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(v45, &v47);
      std::wstring::operator=(lpNewFileName, v21);
      std::wstring::_Tidy_deallocate(&v47);
      v22 = (const WCHAR *)lpNewFileName;
      if ( si128.m128i_i64[1] > 7uLL )
        v22 = lpNewFileName[0];
      v23 = (const WCHAR *)&lpExistingFileName;
      if ( (unsigned __int64)v56 > 7 )
        v23 = lpExistingFileName;
      if ( !CopyFileW(v23, v22, 1) )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x12C,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariossqlitetable.cpp",
          v24);
    }
    std::wstring::_Tidy_deallocate(&lpExistingFileName);
    std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(v45);
    goto LABEL_32;
  }
  catch ( ... )
  {
    wil::details::in1diag3::FailFast_CaughtException(
      retaddr,
      (void *)0x182,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariossqlitetable.cpp",
      v14);
  }
  return result;
}

```

## disassembly

```asm
0x1802b3574  push    rbx
0x1802b3576  push    rsi
0x1802b3577  push    rdi
0x1802b3578  push    r12
0x1802b357a  push    r14
0x1802b357c  push    r15
0x1802b357e  sub     rsp, 1F8h
0x1802b3585  mov     rax, cs:__security_cookie
0x1802b358c  xor     rax, rsp
0x1802b358f  mov     [rsp+228h+var_48], rax
0x1802b3597  movzx   r14d, r8b
0x1802b359b  mov     r12d, edx
0x1802b359e  mov     rsi, rcx
0x1802b35a1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ScenarioCacheReconstruction@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ScenarioCacheReconstruction@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScenarioCacheReconstruction> `wil::Feature<__WilFeatureTraits_Feature_ScenarioCacheReconstruction>::GetImpl(void)'::`2'::impl
0x1802b35a8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ScenarioCacheReconstruction@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScenarioCacheReconstruction>::__private_IsEnabled(void)
0x1802b35ad  mov     r15d, 1
0x1802b35b3  test    al, al
0x1802b35b5  jz      short loc_1802B35D3
0x1802b35b7  cmp     r14b, 3
0x1802b35bb  jnz     short loc_1802B35D3
0x1802b35bd  lock add [rsi+130h], r15d
0x1802b35c5  mov     eax, [rsi+130h]
0x1802b35cb  nop
0x1802b35cc  cmp     eax, 14h
0x1802b35cf  cmovnb  r14d, r15d
0x1802b35d3  mov     eax, cs:dword_1804543B0
0x1802b35d9  cmp     eax, 5
0x1802b35dc  jbe     short loc_1802B363B
0x1802b35de  mov     edx, 10h
0x1802b35e3  lea     rcx, dword_1804543B0
0x1802b35ea  call    _tlgKeywordOn
0x1802b35ef  test    al, al
0x1802b35f1  jz      short loc_1802B363B
0x1802b35f3  call    ?initialize@ResetType@EnumDetails@Diagnostics@Microsoft@@CAHXZ; Microsoft::Diagnostics::EnumDetails::ResetType::initialize(void)
0x1802b35f8  xor     r8d, r8d
0x1802b35fb  mov     dl, r14b
0x1802b35fe  lea     rcx, [rsp+228h+var_1F8]
0x1802b3603  call    ?_from_value_loop@ResetType@EnumDetails@Diagnostics@Microsoft@@CA?AU?$optional@_K@better_enums@@E_K@Z; Microsoft::Diagnostics::EnumDetails::ResetType::_from_value_loop(uchar,unsigned __int64)
0x1802b3608  cmp     byte ptr [rax], 0
0x1802b360b  jz      short loc_1802B361E
0x1802b360d  mov     rax, [rax+8]
0x1802b3611  lea     rcx, ?value@?1??_name_array@_data_ResetType@better_enums@EnumDetails@Diagnostics@Microsoft@@YAPEAPEBDXZ@4PAPEBDA; char const * near * `Microsoft::Diagnostics::EnumDetails::better_enums::_data_ResetType::_name_array(void)'::`2'::value
0x1802b3618  mov     rcx, [rcx+rax*8]
0x1802b361c  jmp     short loc_1802B3620
0x1802b361e  xor     ecx, ecx
0x1802b3620  mov     qword ptr [rsp+228h+var_1F8], rcx
0x1802b3625  lea     rax, [rsp+228h+var_1F8]
0x1802b362a  mov     qword ptr [rsp+228h+var_208], rax; int
0x1802b362f  lea     rdx, byte_1803F27C1
0x1802b3636  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1802b363b  lea     rdx, [rsi+0C8h]
0x1802b3642  lea     rcx, [rsp+228h+var_1E8]
0x1802b3647  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x1802b364c  nop
0x1802b364d  lea     rdi, [rsi+118h]
0x1802b3654  mov     rbx, [rdi]
0x1802b3657  mov     r8, [rbx+8]
0x1802b365b  mov     rdx, rdi
0x1802b365e  mov     rcx, rdi
0x1802b3661  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>,void *>>>(std::allocator<std::_Tree_node<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>,void *>> &,std::_Tree_node<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>,void *> *)
0x1802b3666  mov     [rbx+8], rbx
0x1802b366a  mov     [rbx], rbx
0x1802b366d  mov     [rbx+10h], rbx
0x1802b3671  mov     qword ptr [rdi+8], 0
0x1802b3679  mov     rdx, [rsi+28h]
0x1802b367d  mov     qword ptr [rsi+28h], 0
0x1802b3685  test    rdx, rdx
0x1802b3688  jz      short loc_1802B368F
0x1802b368a  call    ??R?$default_delete@VSqlConnection@Diagnostics@Microsoft@@@std@@QEBAXPEAVSqlConnection@Diagnostics@Microsoft@@@Z; std::default_delete<Microsoft::Diagnostics::SqlConnection>::operator()(Microsoft::Diagnostics::SqlConnection *)
0x1802b368f  mov     qword ptr [rsp+228h+var_1F8], rsi
0x1802b3694  mov     edi, 2
0x1802b3699  cmp     r14b, dil
0x1802b369c  jnz     short loc_1802B36B8
0x1802b369e  lea     rcx, [rsp+228h+var_1F8]
0x1802b36a3  call    _Microsoft__Diagnostics__ScenariosSqliteTable__ResetDatabase____3____lambda_1___operator__
0x1802b36a8  nop
0x1802b36a9  lea     rcx, [rsp+228h+var_1E8]
0x1802b36ae  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x1802b36b3  jmp     loc_1802B3C83
0x1802b36b8  xorps   xmm0, xmm0
0x1802b36bb  movups  xmmword ptr [rsp+228h+lpNewFileName], xmm0
0x1802b36c3  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1802b36cb  movdqu  [rsp+228h+var_98], xmm1
0x1802b36d4  xor     eax, eax
0x1802b36d6  mov     word ptr [rsp+228h+lpNewFileName], ax
0x1802b36de  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ScenarioCacheReconstruction@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ScenarioCacheReconstruction@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScenarioCacheReconstruction> `wil::Feature<__WilFeatureTraits_Feature_ScenarioCacheReconstruction>::GetImpl(void)'::`2'::impl
0x1802b36e5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ScenarioCacheReconstruction@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScenarioCacheReconstruction>::__private_IsEnabled(void)
0x1802b36ea  test    al, al
0x1802b36ec  jz      loc_1802B37E8
0x1802b36f2  cmp     r14b, 3
0x1802b36f6  jz      loc_1802B38D9
0x1802b36fc  lea     rcx, [rsp+228h+var_1D8]
0x1802b3701  call    ??0?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)
0x1802b3706  nop
0x1802b3707  lea     rdx, [rsi+8]
0x1802b370b  lea     rcx, [rsp+228h+var_1C8]
0x1802b3710  call    ??$?6_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z; std::operator<<<wchar_t>(std::wostream &,std::wstring const &)
0x1802b3715  lea     rdx, aEventstoreDb; "\\EventStore.db"
0x1802b371c  mov     rcx, rax
0x1802b371f  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1802b3724  lea     rdx, [rsp+228h+lpExistingFileName]
0x1802b372c  lea     rcx, [rsp+228h+var_1D8]
0x1802b3731  call    ?str@?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(void)
0x1802b3736  nop
0x1802b3737  lea     rdx, aBk; ".bk"
0x1802b373e  lea     rcx, [rsp+228h+var_1C8]
0x1802b3743  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1802b3748  lea     rdx, [rsp+228h+var_D8]
0x1802b3750  lea     rcx, [rsp+228h+var_1D8]
0x1802b3755  call    ?str@?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(void)
0x1802b375a  mov     rdx, rax
0x1802b375d  lea     rcx, [rsp+228h+lpNewFileName]
0x1802b3765  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1802b376a  lea     rcx, [rsp+228h+var_D8]
0x1802b3772  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802b3777  lea     rdx, [rsp+228h+lpNewFileName]
0x1802b377f  cmp     qword ptr [rsp+228h+var_98+8], 7
0x1802b3788  cmova   rdx, [rsp+228h+lpNewFileName]; lpNewFileName
0x1802b3791  lea     rcx, [rsp+228h+lpExistingFileName]
0x1802b3799  cmp     qword ptr [rsp+228h+var_70], 7
0x1802b37a2  cmova   rcx, [rsp+228h+lpExistingFileName]; lpExistingFileName
0x1802b37ab  mov     rbx, [rsp+228h]
0x1802b37b3  mov     r8d, r15d; bFailIfExists
0x1802b37b6  call    cs:__imp_CopyFileW
0x1802b37bc  test    eax, eax
0x1802b37be  jnz     short loc_1802B37D5
0x1802b37c0  lea     r8, aOnecoreBaseTel_78; "onecore\\base\\telemetry\\utc\\service"...
0x1802b37c7  mov     edx, 121h; void *
0x1802b37cc  mov     rcx, rbx; this
0x1802b37cf  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1802b37d4  nop
0x1802b37d5  lea     rcx, [rsp+228h+lpExistingFileName]
0x1802b37dd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802b37e2  nop
0x1802b37e3  jmp     loc_1802B38CF
0x1802b37e8  lea     rcx, [rsp+228h+var_1D8]
0x1802b37ed  call    ??0?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)
0x1802b37f2  nop
0x1802b37f3  lea     rdx, [rsi+8]
0x1802b37f7  lea     rcx, [rsp+228h+var_1C8]
0x1802b37fc  call    ??$?6_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z; std::operator<<<wchar_t>(std::wostream &,std::wstring const &)
0x1802b3801  lea     rdx, aEventstoreDb; "\\EventStore.db"
0x1802b3808  mov     rcx, rax
0x1802b380b  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1802b3810  lea     rdx, [rsp+228h+lpExistingFileName]
0x1802b3818  lea     rcx, [rsp+228h+var_1D8]
0x1802b381d  call    ?str@?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(void)
0x1802b3822  nop
0x1802b3823  lea     rdx, aBk; ".bk"
0x1802b382a  lea     rcx, [rsp+228h+var_1C8]
0x1802b382f  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1802b3834  lea     rdx, [rsp+228h+var_D8]
0x1802b383c  lea     rcx, [rsp+228h+var_1D8]
0x1802b3841  call    ?str@?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(void)
0x1802b3846  mov     rdx, rax
0x1802b3849  lea     rcx, [rsp+228h+lpNewFileName]
0x1802b3851  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1802b3856  lea     rcx, [rsp+228h+var_D8]
0x1802b385e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802b3863  lea     rdx, [rsp+228h+lpNewFileName]
0x1802b386b  cmp     qword ptr [rsp+228h+var_98+8], 7
0x1802b3874  cmova   rdx, [rsp+228h+lpNewFileName]; lpNewFileName
0x1802b387d  lea     rcx, [rsp+228h+lpExistingFileName]
0x1802b3885  cmp     qword ptr [rsp+228h+var_70], 7
0x1802b388e  cmova   rcx, [rsp+228h+lpExistingFileName]; lpExistingFileName
0x1802b3897  mov     rbx, [rsp+228h]
0x1802b389f  mov     r8d, r15d; bFailIfExists
0x1802b38a2  call    cs:__imp_CopyFileW
0x1802b38a8  test    eax, eax
0x1802b38aa  jnz     short loc_1802B38C1
0x1802b38ac  lea     r8, aOnecoreBaseTel_78; "onecore\\base\\telemetry\\utc\\service"...
0x1802b38b3  mov     edx, 12Ch; void *
0x1802b38b8  mov     rcx, rbx; this
0x1802b38bb  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1802b38c0  nop
0x1802b38c1  lea     rcx, [rsp+228h+lpExistingFileName]
0x1802b38c9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802b38ce  nop
0x1802b38cf  lea     rcx, [rsp+228h+var_1D8]
0x1802b38d4  call    ??_D?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAXXZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(void)
0x1802b38d9  lea     rcx, [rsp+228h+var_1F8]
0x1802b38de  call    _Microsoft__Diagnostics__ScenariosSqliteTable__ResetDatabase____3____lambda_1___operator__
0x1802b38e3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ScenarioCacheReconstruction@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ScenarioCacheReconstruction@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScenarioCacheReconstruction> `wil::Feature<__WilFeatureTraits_Feature_ScenarioCacheReconstruction>::GetImpl(void)'::`2'::impl
0x1802b38ea  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ScenarioCacheReconstruction@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScenarioCacheReconstruction>::__private_IsEnabled(void)
0x1802b38ef  test    al, al
0x1802b38f1  jz      loc_1802B3AF0
0x1802b38f7  test    r14b, r14b
0x1802b38fa  jz      loc_1802B39EA
0x1802b3900  cmp     r14b, r15b
0x1802b3903  jz      loc_1802B3CA4
0x1802b3909  cmp     r14b, 3
0x1802b390d  jnz     loc_1802B3C6A
0x1802b3913  mov     al, [rsi+134h]
0x1802b3919  nop
0x1802b391a  test    al, al
0x1802b391c  jnz     loc_1802B3C6A
0x1802b3922  mov     eax, cs:dword_1804543B0
0x1802b3928  cmp     eax, 5
0x1802b392b  jbe     short loc_1802B396A
0x1802b392d  mov     edx, 10h
0x1802b3932  lea     rcx, dword_1804543B0
0x1802b3939  call    _tlgKeywordOn
0x1802b393e  test    al, al
0x1802b3940  jz      short loc_1802B396A
0x1802b3942  mov     eax, [rsi+130h]
0x1802b3948  nop
0x1802b3949  mov     [rsp+228h+var_1F8], eax
0x1802b394d  lea     rax, [rsp+228h+var_1F8]
0x1802b3952  mov     qword ptr [rsp+228h+var_208], rax
0x1802b3957  lea     rdx, byte_1803F2771
0x1802b395e  lea     rcx, dword_1804543B0
0x1802b3965  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1802b396a  mov     eax, r15d
0x1802b396d  xchg    al, [rsi+134h]
0x1802b3973  mov     dword ptr [rsi+30h], 0
0x1802b397a  mov     dl, r15b; bool
0x1802b397d  mov     rcx, rsi; this
0x1802b3980  call    ?Initialize@ScenariosSqliteTable@Diagnostics@Microsoft@@AEAAX_N@Z; Microsoft::Diagnostics::ScenariosSqliteTable::Initialize(bool)
0x1802b3985  xor     ecx, ecx
0x1802b3987  xor     eax, eax
0x1802b3989  lock cmpxchg qword ptr cs:xmmword_180463270, rcx
0x1802b3992  jz      short loc_1802B39BC
0x1802b3994  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x1802b399b  call    ?GetScenarioObjectCache@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVScenarioObjectCache@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetScenarioObjectCache(void)
0x1802b39a0  mov     rcx, rax; this
0x1802b39a3  call    ?Clear@ScenarioObjectCache@Diagnostics@Microsoft@@QEAAXXZ; Microsoft::Diagnostics::ScenarioObjectCache::Clear(void)
0x1802b39a8  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x1802b39af  call    ?GetScenarioObjectCache@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVScenarioObjectCache@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetScenarioObjectCache(void)
0x1802b39b4  mov     rcx, rax; this
0x1802b39b7  call    ?Clean@ScenarioObjectCache@Diagnostics@Microsoft@@QEAAXXZ; Microsoft::Diagnostics::ScenarioObjectCache::Clean(void)
0x1802b39bc  xor     edx, edx
0x1802b39be  xor     eax, eax
0x1802b39c0  lock cmpxchg qword ptr cs:xmmword_180463150, rdx
0x1802b39c9  jz      loc_1802B3C6A
0x1802b39cf  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x1802b39d6  call    ?GetScenarioManager@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVScenarioManager@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetScenarioManager(void)
0x1802b39db  mov     rcx, [rax+58h]; hEvent
0x1802b39df  call    cs:__imp_SetEvent
0x1802b39e5  jmp     loc_1802B3C6A
0x1802b39ea  mov     [rsp+228h+var_D8], rsi
0x1802b39f2  mov     [rsp+228h+var_D0], r12d
0x1802b39fa  lea     rdx, [rsp+228h+lpNewFileName]
0x1802b3a02  lea     rcx, [rsp+228h+var_C8]
0x1802b3a0a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1802b3a0f  nop
0x1802b3a10  lea     rax, off_18037EA68
0x1802b3a17  mov     [rsp+228h+lpExistingFileName], rax
0x1802b3a1f  mov     rax, [rsp+228h+var_D8]
0x1802b3a27  mov     [rsp+228h+var_80], rax
0x1802b3a2f  mov     eax, [rsp+228h+var_D0]
0x1802b3a36  mov     [rsp+228h+var_78], eax
0x1802b3a3d  xorps   xmm0, xmm0
0x1802b3a40  movups  [rsp+228h+var_70], xmm0
0x1802b3a48  mov     rax, qword ptr [rsp+228h+var_C8]
0x1802b3a50  mov     qword ptr [rsp+228h+var_70], rax
0x1802b3a58  mov     rax, qword ptr [rsp+228h+var_C8+8]
0x1802b3a60  mov     qword ptr [rsp+228h+var_70+8], rax
0x1802b3a68  mov     rax, qword ptr [rsp+228h+var_B8]
0x1802b3a70  mov     qword ptr [rsp+228h+var_60], rax
0x1802b3a78  mov     rax, qword ptr [rsp+228h+var_B8+8]
0x1802b3a80  mov     qword ptr [rsp+228h+var_60+8], rax
0x1802b3a88  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1802b3a90  movdqu  [rsp+228h+var_B8], xmm0
0x1802b3a99  xor     eax, eax
0x1802b3a9b  mov     word ptr [rsp+228h+var_C8], ax
0x1802b3aa3  lea     rax, [rsp+228h+lpExistingFileName]
0x1802b3aab  mov     [rsp+228h+var_50], rax
0x1802b3ab3  lea     rcx, [rsi+50h]; _Mtx_t
0x1802b3ab7  lea     rdx, [rsp+228h+lpExistingFileName]
0x1802b3abf  call    ?Submit@TpSerialWork@Diagnostics@Microsoft@@QEAAXAEBV?$function@$$A6AXXZ@std@@@Z; Microsoft::Diagnostics::TpSerialWork::Submit(std::function<void (void)> const &)
0x1802b3ac4  nop
0x1802b3ac5  lea     rcx, [rsp+228h+lpExistingFileName]
0x1802b3acd  call    ??1?$function@$$A6A_NAEBU_GUID@@@Z@std@@QEAA@XZ; std::function<bool (_GUID const &)>::~function<bool (_GUID const &)>(void)
0x1802b3ad2  nop
0x1802b3ad3  lea     rcx, [rsp+228h+var_C8]
0x1802b3adb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802b3ae0  mov     dl, r15b; bool
0x1802b3ae3  mov     rcx, rsi; this
0x1802b3ae6  call    ?Initialize@ScenariosSqliteTable@Diagnostics@Microsoft@@AEAAX_N@Z; Microsoft::Diagnostics::ScenariosSqliteTable::Initialize(bool)
0x1802b3aeb  jmp     loc_1802B3C6A
0x1802b3af0  test    r14b, r14b
0x1802b3af3  jz      short loc_1802B3B68
0x1802b3af5  cmp     r14b, r15b
0x1802b3af8  jnz     loc_1802B3C6A
0x1802b3afe  mov     rcx, [rsp+228h]; this
0x1802b3b06  mov     r9d, r12d; char *
0x1802b3b09  lea     r8, aOnecoreBaseTel_78; "onecore\\base\\telemetry\\utc\\service"...
0x1802b3b10  mov     edx, 17Bh; void *
0x1802b3b15  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1802b3b1a  lea     rcx, [rsp+228h+lpNewFileName]
0x1802b3b22  cmp     qword ptr [rsp+228h+var_98+8], 7
0x1802b3b2b  cmova   rcx, [rsp+228h+lpNewFileName]; pwzFile
0x1802b3b34  mov     r8d, r15d; dwFlags
0x1802b3b37  mov     edx, edi; regFileType
0x1802b3b39  call    cs:__imp_WerRegisterFile
0x1802b3b3f  mov     rcx, [rsp+228h]; this
0x1802b3b47  test    eax, eax
0x1802b3b49  jns     loc_1802B3C6A
0x1802b3b4f  mov     r9d, eax; char *
0x1802b3b52  lea     r8, aOnecoreBaseTel_78; "onecore\\base\\telemetry\\utc\\service"...
  ... truncated ...
```
