# Microsoft::Diagnostics::ScenarioCounterStorage::DeleteExpiredScenarios(std::function<bool (_GUID const &)>)

- ea: `0x18010aa68`
- end: `0x18010af65`
- name: `?DeleteExpiredScenarios@ScenarioCounterStorage@Diagnostics@Microsoft@@QEAAXV?$function@$$A6A_NAEBU_GUID@@@Z@std@@@Z`
- size: `1277`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1801606ac`

## callees

- `0x18001d9a0`
- `0x18001dee8`
- `0x18001fd84`
- `0x180021538`
- `0x180024558`
- `0x18002afd8`
- `0x18002b7c0`
- `0x18002bfc0`
- `0x18002cae0`
- `0x18002df00`
- `0x18008a4ec`
- `0x18009c7e4`
- `0x18009c8c0`
- `0x1800c1920`
- `0x180101424`
- `0x18010aa68`
- `0x18010af6c`
- `0x18012c62c`
- `0x1801a9494`
- `0x1801abcac`
- `0x1801f4aa8`
- `0x18020aac0`
- `0x1802b0298`
- `0x180369010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18010af14`
- `msvcp_win!_Mtx_unlock` at `0x18010af14`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18010ae7f`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18010ae7f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18010aea9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18010aea9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18010abeb`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18010abeb`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18010aafc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18010aafc`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18010ac25`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18010ac25`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18010ab74`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18010ab74`

## string_xrefs

- `0x18010ab1c`: `onecore\base\telemetry\utc\service\scenarios\base\scenariocounterstorage.cpp`
- `0x18010ab81`: `onecore\base\telemetry\utc\service\scenarios\base\scenariocounterstorage.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
int __fastcall Microsoft::Diagnostics::ScenarioCounterStorage::DeleteExpiredScenarios(HKEY *a1, __int64 a2)
{
  int v4; // eax
  HRESULT v5; // eax
  DWORD i; // r14d
  WCHAR *v7; // r8
  int v8; // eax
  const OLECHAR *v9; // rcx
  __int64 v10; // rcx
  LPWSTR *v11; // rdx
  int Qword; // eax
  LPWSTR *v13; // rdx
  int v14; // eax
  int String; // eax
  __int64 v16; // rcx
  int v17; // eax
  LPCWSTR v18; // rbx
  LPCWSTR v19; // r14
  const WCHAR *v20; // rdx
  int v21; // eax
  int result; // eax
  __int64 v23; // rdx
  __int64 v24; // rcx
  int lpcSubKeys; // [rsp+20h] [rbp-E0h]
  int lpcSubKeysa; // [rsp+20h] [rbp-E0h]
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cchName; // [rsp+68h] [rbp-98h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-90h] BYREF
  __int64 v31; // [rsp+78h] [rbp-88h] BYREF
  __int128 v32; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+90h] [rbp-70h] BYREF
  _Mtx_t v34; // [rsp+A8h] [rbp-58h] BYREF
  char v35; // [rsp+B0h] [rbp-50h]
  __int64 v36; // [rsp+B8h] [rbp-48h]
  __int128 v37; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v38[16]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v39[16]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v40[16]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v41[16]; // [rsp+100h] [rbp+0h] BYREF
  LPWSTR lpName[2]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v43; // [rsp+120h] [rbp+20h]
  unsigned __int64 v44; // [rsp+128h] [rbp+28h]
  GUID pclsid; // [rsp+130h] [rbp+30h] BYREF
  _OWORD v46[2]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE Src[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v48[32]; // [rsp+180h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v36 = a2;
  std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(&v34, a1 + 1);
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v4 = RegQueryInfoKeyW(*a1, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v4 > 0 )
    v4 = (unsigned __int16)v4 | 0x80070000;
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D0,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariocounterstorage.cpp",
      (const char *)(unsigned int)v4,
      lpcSubKeys);
  *(_OWORD *)lpName = 0;
  v43 = 0;
  v44 = 0;
  std::wstring::_Construct<0,wchar_t>(lpName, 0, cbMaxSubKeyLen + 1);
  ppv = 0;
  v5 = CoCreateInstance(&CLSID_FlightClientAPI, 0, 1u, &GUID_79588f37_5be1_4a35_b23d_29832257cada, &ppv);
  if ( v5 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1DB,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariocounterstorage.cpp",
      (const char *)(unsigned int)v5,
      lpcSubKeysa);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>(lpSubKey);
  for ( i = 0; i < cSubKeys; ++i )
  {
    cchName = cbMaxSubKeyLen + 1;
    v7 = (WCHAR *)lpName;
    if ( v44 > 7 )
      v7 = lpName[0];
    v8 = RegEnumKeyExW(*a1, i, v7, &cchName, 0, 0, 0, 0);
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1EB,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariocounterstorage.cpp",
        (const char *)(unsigned int)v8,
        lpcSubKeysa);
    pclsid = 0;
    v9 = (const OLECHAR *)lpName;
    if ( v44 > 7 )
      v9 = lpName[0];
    if ( CLSIDFromString(v9, &pclsid) >= 0 )
    {
      v10 = *(_QWORD *)(a2 + 56);
      if ( !v10 )
      {
        std::_Xbad_function_call();
        __debugbreak();
      }
      if ( (*(unsigned __int8 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v10 + 16LL))(v10, &pclsid) )
        continue;
    }
    v11 = lpName;
    if ( v44 > 7 )
      v11 = (LPWSTR *)lpName[0];
    std::wstring::wstring(v46, v11);
    std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(lpSubKey, v46);
    std::wstring::_Tidy_deallocate(v46);
    v32 = *(_OWORD *)std::_Tree<std::_Tmap_traits<_GUID,Microsoft::Diagnostics::ScenarioCounters,LessGuid,std::allocator<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioCounters>>,0>>::_Eqrange<_GUID>(
                       a1 + 11,
                       v38,
                       &pclsid);
    std::_Tree<std::_Tmap_traits<_GUID,Microsoft::Diagnostics::ScenarioCounters,LessGuid,std::allocator<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioCounters>>,0>>::_Erase(
      a1 + 11,
      &v32);
    v31 = 0;
    std::wstring::wstring(Src);
    std::wstring::append(Src, L"\\");
    std::wstring::_Append<wchar_t>(Src);
    v32 = *(_OWORD *)&off_180372910;
    v46[0] = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v39);
    Qword = Microsoft::Diagnostics::Utils::Registry::GetQword(-2147483646, v46, &v32, &v31);
    if ( Qword < 0 )
    {
      if ( Qword != -2147024894 )
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x21A,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariocounterstorage.cpp",
          (const char *)(unsigned int)Qword,
          lpcSubKeysa);
    }
    else if ( ppv )
    {
      v13 = lpName;
      if ( v44 > 7 )
        LODWORD(v13) = lpName[0];
      lpcSubKeysa = (int)v13;
      v14 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 4, v31);
      if ( v14 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x215,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariocounterstorage.cpp",
          (const char *)(unsigned int)v14,
          lpcSubKeysa);
    }
    std::wstring::wstring(v48);
    v46[0] = *(_OWORD *)&off_180372890;
    v32 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v40);
    String = Microsoft::Diagnostics::Utils::Registry::GetString(-2147483646, &v32, v46, v48);
    if ( String < 0 )
    {
      if ( String != -2147024894 )
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x22E,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariocounterstorage.cpp",
          (const char *)(unsigned int)String,
          lpcSubKeysa);
    }
    else
    {
      Microsoft::Diagnostics::LifetimeManager::GetEscalationEngine((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      v37 = *(_OWORD *)std::wstring::operator std::wstring_view(v48, v41);
      v17 = Microsoft::Diagnostics::SnapshotManager::StopHeapSnapshotByProcessNameOnScenarioExpiry(v16, &v37);
      if ( v17 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x22A,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariocounterstorage.cpp",
          (const char *)(unsigned int)v17,
          lpcSubKeysa);
    }
    std::wstring::_Tidy_deallocate(v48);
    std::wstring::_Tidy_deallocate(Src);
  }
  v18 = lpSubKey[0];
  v19 = lpSubKey[1];
  while ( v18 != v19 )
  {
    if ( *((_QWORD *)v18 + 3) <= 7u )
      v20 = v18;
    else
      v20 = *(const WCHAR **)v18;
    v21 = RegDeleteTreeW(*a1, v20);
    if ( v21 > 0 )
      v21 = (unsigned __int16)v21 | 0x80070000;
    if ( v21 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x236,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariocounterstorage.cpp",
        (const char *)(unsigned int)v21,
        lpcSubKeysa);
    v18 += 16;
  }
  std::vector<std::wstring>::_Tidy(lpSubKey);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  result = std::wstring::_Tidy_deallocate(lpName);
  if ( v35 )
    result = _Mtx_unlock(v34);
  v24 = *(_QWORD *)(a2 + 56);
  if ( v24 )
  {
    LOBYTE(v23) = v24 != a2;
    result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 32LL))(v24, v23);
    *(_QWORD *)(a2 + 56) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18010aa68  mov     [rsp-8+arg_10], rbx
0x18010aa6d  mov     [rsp-8+arg_18], rsi
0x18010aa72  push    rbp
0x18010aa73  push    rdi
0x18010aa74  push    r12
0x18010aa76  push    r14
0x18010aa78  push    r15
0x18010aa7a  lea     rbp, [rsp-0B0h]
0x18010aa82  sub     rsp, 1B0h
0x18010aa89  mov     rax, cs:__security_cookie
0x18010aa90  xor     rax, rsp
0x18010aa93  mov     [rbp+0D0h+var_30], rax
0x18010aa9a  mov     rsi, rdx
0x18010aa9d  mov     r15, rcx
0x18010aaa0  mov     [rbp+0D0h+var_118], rdx
0x18010aaa4  lea     rdx, [rcx+8]
0x18010aaa8  lea     rcx, [rbp+0D0h+var_128]
0x18010aaac  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x18010aab1  nop
0x18010aab2  xor     r12d, r12d
0x18010aab5  mov     [rsp+1D0h+cSubKeys], r12d
0x18010aaba  mov     [rsp+1D0h+cbMaxSubKeyLen], r12d
0x18010aabf  mov     [rsp+1D0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18010aac4  mov     [rsp+1D0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18010aac9  mov     [rsp+1D0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18010aace  mov     [rsp+1D0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x18010aad3  mov     [rsp+1D0h+lpcValues], r12; lpcValues
0x18010aad8  mov     [rsp+1D0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18010aadd  lea     rax, [rsp+1D0h+cbMaxSubKeyLen]
0x18010aae2  mov     [rsp+1D0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18010aae7  lea     rax, [rsp+1D0h+cSubKeys]
0x18010aaec  mov     [rsp+1D0h+lpcSubKeys], rax; int
0x18010aaf1  xor     r9d, r9d; lpReserved
0x18010aaf4  xor     r8d, r8d; lpcchClass
0x18010aaf7  xor     edx, edx; lpClass
0x18010aaf9  mov     rcx, [r15]; hKey
0x18010aafc  call    cs:__imp_RegQueryInfoKeyW
0x18010ab02  test    eax, eax
0x18010ab04  jle     short loc_18010AB0E
0x18010ab06  movzx   eax, ax
0x18010ab09  or      eax, 80070000h
0x18010ab0e  mov     rcx, [rbp+0D8h]; this
0x18010ab15  test    eax, eax
0x18010ab17  jns     short loc_18010AB2E
0x18010ab19  mov     r9d, eax; char *
0x18010ab1c  lea     r8, aOnecoreBaseTel_148; "onecore\\base\\telemetry\\utc\\service"...
0x18010ab23  mov     edx, 1D0h; void *
0x18010ab28  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18010ab2e  xorps   xmm0, xmm0
0x18010ab31  movups  xmmword ptr [rbp+0D0h+lpName], xmm0
0x18010ab35  mov     [rbp+0D0h+var_B0], r12
0x18010ab39  mov     [rbp+0D0h+var_A8], r12
0x18010ab3d  mov     r8d, [rsp+1D0h+cbMaxSubKeyLen]
0x18010ab42  inc     r8d
0x18010ab45  xor     edx, edx
0x18010ab47  lea     rcx, [rbp+0D0h+lpName]
0x18010ab4b  call    ??$_Construct@$0A@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAX_W_K@Z; std::wstring::_Construct<0,wchar_t>(wchar_t,unsigned __int64)
0x18010ab50  nop
0x18010ab51  mov     [rsp+1D0h+ppv], r12
0x18010ab56  lea     rax, [rsp+1D0h+ppv]
0x18010ab5b  mov     [rsp+1D0h+lpcSubKeys], rax; int
0x18010ab60  lea     r9, _GUID_79588f37_5be1_4a35_b23d_29832257cada; riid
0x18010ab67  xor     edx, edx; pUnkOuter
0x18010ab69  lea     r8d, [rdx+1]; dwClsContext
0x18010ab6d  lea     rcx, CLSID_FlightClientAPI; rclsid
0x18010ab74  call    cs:__imp_CoCreateInstance
0x18010ab7a  mov     rcx, [rbp+0D8h]; this
0x18010ab81  lea     rdi, aOnecoreBaseTel_148; "onecore\\base\\telemetry\\utc\\service"...
0x18010ab88  test    eax, eax
0x18010ab8a  jns     short loc_18010AB9C
0x18010ab8c  mov     r9d, eax; char *
0x18010ab8f  mov     r8, rdi; unsigned int
0x18010ab92  mov     edx, 1DBh; void *
0x18010ab97  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010ab9c  lea     rcx, [rbp+0D0h+lpSubKey]; void *
0x18010aba0  call    ??$?0AEBV?$allocator@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBU_GUID@@UScenarioStateMapEntry@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>>>>>>(std::allocator<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioStateMapEntry>> const &)
0x18010aba5  nop
0x18010aba6  mov     r14d, r12d
0x18010aba9  cmp     [rsp+1D0h+cSubKeys], r12d
0x18010abae  jbe     loc_18010AE75
0x18010abb4  mov     eax, [rsp+1D0h+cbMaxSubKeyLen]
0x18010abb8  inc     eax
0x18010abba  mov     [rsp+1D0h+cchName], eax
0x18010abbe  lea     r8, [rbp+0D0h+lpName]
0x18010abc2  cmp     [rbp+0D0h+var_A8], 7
0x18010abc7  cmova   r8, [rbp+0D0h+lpName]; lpName
0x18010abcc  mov     [rsp+1D0h+lpcValues], r12; lpftLastWriteTime
0x18010abd1  mov     [rsp+1D0h+lpcbMaxClassLen], r12; lpcchClass
0x18010abd6  mov     [rsp+1D0h+lpcbMaxSubKeyLen], r12; lpClass
0x18010abdb  mov     [rsp+1D0h+lpcSubKeys], r12; int
0x18010abe0  lea     r9, [rsp+1D0h+cchName]; lpcchName
0x18010abe5  mov     edx, r14d; dwIndex
0x18010abe8  mov     rcx, [r15]; hKey
0x18010abeb  call    cs:__imp_RegEnumKeyExW
0x18010abf1  test    eax, eax
0x18010abf3  jle     short loc_18010ABFD
0x18010abf5  movzx   eax, ax
0x18010abf8  or      eax, 80070000h
0x18010abfd  mov     rcx, [rbp+0D8h]; this
0x18010ac04  test    eax, eax
0x18010ac06  js      loc_18010AE86
0x18010ac0c  xorps   xmm0, xmm0
0x18010ac0f  movups  xmmword ptr [rbp+0D0h+pclsid.Data1], xmm0
0x18010ac13  lea     rcx, [rbp+0D0h+lpName]
0x18010ac17  cmp     [rbp+0D0h+var_A8], 7
0x18010ac1c  cmova   rcx, [rbp+0D0h+lpName]; lpsz
0x18010ac21  lea     rdx, [rbp+0D0h+pclsid]; pclsid
0x18010ac25  call    cs:__imp_CLSIDFromString
0x18010ac2b  test    eax, eax
0x18010ac2d  js      short loc_18010AC54
0x18010ac2f  mov     rcx, [rsi+38h]
0x18010ac33  test    rcx, rcx
0x18010ac36  jz      loc_18010AE7F
0x18010ac3c  mov     rax, [rcx]
0x18010ac3f  lea     rdx, [rbp+0D0h+pclsid]
0x18010ac43  mov     rax, [rax+10h]
0x18010ac47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ac4c  test    al, al
0x18010ac4e  jnz     loc_18010AE67
0x18010ac54  lea     rdx, [rbp+0D0h+lpName]
0x18010ac58  cmp     [rbp+0D0h+var_A8], 7
0x18010ac5d  cmova   rdx, [rbp+0D0h+lpName]
0x18010ac62  lea     rcx, [rbp+0D0h+var_90]
0x18010ac66  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18010ac6b  nop
0x18010ac6c  lea     rdx, [rbp+0D0h+var_90]
0x18010ac70  lea     rcx, [rbp+0D0h+lpSubKey]
0x18010ac74  call    ??$_Emplace_one_at_back@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x18010ac79  nop
0x18010ac7a  lea     rcx, [rbp+0D0h+var_90]
0x18010ac7e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010ac83  lea     r8, [rbp+0D0h+pclsid]
0x18010ac87  lea     rdx, [rbp+0D0h+var_100]
0x18010ac8b  lea     rcx, [r15+58h]
0x18010ac8f  call    ??$_Eqrange@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@UScenarioCounters@Diagnostics@Microsoft@@ULessGuid@@V?$allocator@U?$pair@$$CBU_GUID@@UScenarioCounters@Diagnostics@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UScenarioCounters@Diagnostics@Microsoft@@@std@@PEAX@std@@PEAU12@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,Microsoft::Diagnostics::ScenarioCounters,LessGuid,std::allocator<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioCounters>>,0>>::_Eqrange<_GUID>(_GUID const &)
0x18010ac94  movups  xmm0, xmmword ptr [rax]
0x18010ac97  movdqu  [rbp+0D0h+var_150], xmm0
0x18010ac9c  lea     rdx, [rbp+0D0h+var_150]
0x18010aca0  lea     rcx, [r15+58h]
0x18010aca4  call    ?_Erase@?$_Tree@V?$_Tmap_traits@U_GUID@@UScenarioCounters@Diagnostics@Microsoft@@ULessGuid@@V?$allocator@U?$pair@$$CBU_GUID@@UScenarioCounters@Diagnostics@Microsoft@@@std@@@std@@$0A@@std@@@std@@AEAA_KU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UScenarioCounters@Diagnostics@Microsoft@@@std@@PEAX@std@@PEAU12@@2@@Z; std::_Tree<std::_Tmap_traits<_GUID,Microsoft::Diagnostics::ScenarioCounters,LessGuid,std::allocator<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioCounters>>,0>>::_Erase(std::pair<std::_Tree_node<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioCounters>,void *> *,std::_Tree_node<std::pair<_GUID const,Microsoft::Diagnostics::ScenarioCounters>,void *> *>)
0x18010aca9  mov     [rsp+1D0h+var_158], r12
0x18010acae  lea     rdx, off_180371580; "%DiagtrackRegistryRoot%\\Scenarios"
0x18010acb5  lea     rcx, [rbp+0D0h+Src]
0x18010acb9  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18010acbe  nop
0x18010acbf  lea     rdx, asc_18039BD30; "\\"
0x18010acc6  lea     rcx, [rbp+0D0h+Src]
0x18010acca  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x18010accf  lea     rdx, [rbp+0D0h+lpName]
0x18010acd3  cmp     [rbp+0D0h+var_A8], 7
0x18010acd8  cmova   rdx, [rbp+0D0h+lpName]
0x18010acdd  mov     r8, [rbp+0D0h+var_B0]
0x18010ace1  lea     rcx, [rbp+0D0h+Src]; Src
0x18010ace5  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18010acea  movups  xmm0, xmmword ptr cs:off_180372910; "FlightId"
0x18010acf1  movdqu  [rbp+0D0h+var_150], xmm0
0x18010acf6  lea     rdx, [rbp+0D0h+var_F0]
0x18010acfa  lea     rcx, [rbp+0D0h+Src]
0x18010acfe  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18010ad03  movups  xmm0, xmmword ptr [rax]
0x18010ad06  movdqu  [rbp+0D0h+var_90], xmm0
0x18010ad0b  lea     r9, [rsp+1D0h+var_158]
0x18010ad10  lea     r8, [rbp+0D0h+var_150]
0x18010ad14  lea     rdx, [rbp+0D0h+var_90]
0x18010ad18  mov     rcx, 0FFFFFFFF80000002h
0x18010ad1f  call    ?GetQword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEA_K@Z; Microsoft::Diagnostics::Utils::Registry::GetQword(HKEY__ *,std::wstring_view,std::wstring_view,unsigned __int64 &)
0x18010ad24  test    eax, eax
0x18010ad26  js      short loc_18010AD7D
0x18010ad28  mov     rcx, [rsp+1D0h+ppv]
0x18010ad2d  test    rcx, rcx
0x18010ad30  jz      short loc_18010AD9B
0x18010ad32  mov     rax, [rcx]
0x18010ad35  lea     rdx, [rbp+0D0h+lpName]
0x18010ad39  cmp     [rbp+0D0h+var_A8], 7
0x18010ad3e  cmova   rdx, [rbp+0D0h+lpName]
0x18010ad43  mov     [rsp+1D0h+lpcSubKeys], rdx; int
0x18010ad48  mov     r9d, 3
0x18010ad4e  mov     r8, [rsp+1D0h+var_158]
0x18010ad53  lea     edx, [r9+1]
0x18010ad57  mov     rax, [rax+18h]
0x18010ad5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ad60  mov     rcx, [rbp+0D8h]; this
0x18010ad67  test    eax, eax
0x18010ad69  jns     short loc_18010AD9B
0x18010ad6b  mov     r9d, eax; char *
0x18010ad6e  mov     r8, rdi; unsigned int
0x18010ad71  mov     edx, 215h; void *
0x18010ad76  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010ad7b  jmp     short loc_18010AD9B
0x18010ad7d  cmp     eax, 80070002h
0x18010ad82  jz      short loc_18010AD9B
0x18010ad84  mov     rcx, [rbp+0D8h]; this
0x18010ad8b  mov     r9d, eax; char *
0x18010ad8e  mov     r8, rdi; unsigned int
0x18010ad91  mov     edx, 21Ah; void *
0x18010ad96  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18010ad9b  lea     rcx, [rbp+0D0h+var_50]; void *
0x18010ada2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18010ada7  nop
0x18010ada8  movups  xmm0, xmmword ptr cs:off_180372890; "HeapSnapshotProcessName"
0x18010adaf  movdqu  [rbp+0D0h+var_90], xmm0
0x18010adb4  lea     rdx, [rbp+0D0h+var_E0]
0x18010adb8  lea     rcx, [rbp+0D0h+Src]
0x18010adbc  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18010adc1  movups  xmm0, xmmword ptr [rax]
0x18010adc4  movdqu  [rbp+0D0h+var_150], xmm0
0x18010adc9  lea     r9, [rbp+0D0h+var_50]
0x18010add0  lea     r8, [rbp+0D0h+var_90]
0x18010add4  lea     rdx, [rbp+0D0h+var_150]
0x18010add8  mov     rcx, 0FFFFFFFF80000002h
0x18010addf  call    ?GetString@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@7@@Z; Microsoft::Diagnostics::Utils::Registry::GetString(HKEY__ *,std::wstring_view,std::wstring_view,std::wstring &)
0x18010ade4  test    eax, eax
0x18010ade6  js      short loc_18010AE32
0x18010ade8  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x18010adef  call    ?GetEscalationEngine@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVEscalationEngine@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetEscalationEngine(void)
0x18010adf4  lea     rdx, [rbp+0D0h+var_D0]
0x18010adf8  lea     rcx, [rbp+0D0h+var_50]
0x18010adff  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18010ae04  movups  xmm0, xmmword ptr [rax]
0x18010ae07  movdqu  [rbp+0D0h+var_110], xmm0
0x18010ae0c  lea     rdx, [rbp+0D0h+var_110]
0x18010ae10  call    ?StopHeapSnapshotByProcessNameOnScenarioExpiry@SnapshotManager@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::SnapshotManager::StopHeapSnapshotByProcessNameOnScenarioExpiry(std::wstring_view)
0x18010ae15  mov     rcx, [rbp+0D8h]; this
0x18010ae1c  test    eax, eax
0x18010ae1e  jns     short loc_18010AE51
0x18010ae20  mov     r9d, eax; char *
0x18010ae23  mov     r8, rdi; unsigned int
0x18010ae26  mov     edx, 22Ah; void *
0x18010ae2b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010ae30  jmp     short loc_18010AE51
0x18010ae32  cmp     eax, 80070002h
0x18010ae37  jz      short loc_18010AE51
0x18010ae39  mov     rcx, [rbp+0D8h]; this
0x18010ae40  mov     r9d, eax; char *
0x18010ae43  mov     r8, rdi; unsigned int
0x18010ae46  mov     edx, 22Eh; void *
0x18010ae4b  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18010ae50  nop
0x18010ae51  lea     rcx, [rbp+0D0h+var_50]
0x18010ae58  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010ae5d  nop
0x18010ae5e  lea     rcx, [rbp+0D0h+Src]
0x18010ae62  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010ae67  inc     r14d
0x18010ae6a  cmp     r14d, [rsp+1D0h+cSubKeys]
0x18010ae6f  jb      loc_18010ABB4
0x18010ae75  mov     rbx, [rbp+0D0h+lpSubKey]
0x18010ae79  mov     r14, [rbp+0D0h+var_138]
0x18010ae7d  jmp     short loc_18010AEDA
0x18010ae7f  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18010ae85  int     3; Trap to Debugger
0x18010ae86  mov     r9d, eax; char *
0x18010ae89  mov     r8, rdi; unsigned int
0x18010ae8c  mov     edx, 1EBh; void *
0x18010ae91  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18010ae97  cmp     qword ptr [rbx+18h], 7
0x18010ae9c  jbe     short loc_18010AEA3
0x18010ae9e  mov     rdx, [rbx]
0x18010aea1  jmp     short loc_18010AEA6
0x18010aea3  mov     rdx, rbx; lpSubKey
0x18010aea6  mov     rcx, [r15]; hKey
0x18010aea9  call    cs:__imp_RegDeleteTreeW
0x18010aeaf  test    eax, eax
0x18010aeb1  jle     short loc_18010AEBB
0x18010aeb3  movzx   eax, ax
0x18010aeb6  or      eax, 80070000h
0x18010aebb  mov     rcx, [rbp+0D8h]; this
0x18010aec2  test    eax, eax
0x18010aec4  jns     short loc_18010AED6
0x18010aec6  mov     r9d, eax; char *
0x18010aec9  mov     r8, rdi; unsigned int
0x18010aecc  mov     edx, 236h; void *
0x18010aed1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010aed6  add     rbx, 20h ; ' '
0x18010aeda  cmp     rbx, r14
0x18010aedd  jnz     short loc_18010AE97
0x18010aedf  lea     rcx, [rbp+0D0h+lpSubKey]
0x18010aee3  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18010aee8  nop
0x18010aee9  mov     rcx, [rsp+1D0h+ppv]
0x18010aeee  test    rcx, rcx
0x18010aef1  jz      short loc_18010AF00
0x18010aef3  mov     rax, [rcx]
0x18010aef6  mov     rax, [rax+10h]
0x18010aefa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010aeff  nop
0x18010af00  lea     rcx, [rbp+0D0h+lpName]
0x18010af04  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010af09  nop
0x18010af0a  cmp     [rbp+0D0h+var_120], r12b
0x18010af0e  jz      short loc_18010AF1B
0x18010af10  mov     rcx, [rbp+0D0h+var_128]; _Mtx_t
0x18010af14  call    cs:__imp__Mtx_unlock
0x18010af1a  nop
0x18010af1b  mov     rcx, [rsi+38h]
0x18010af1f  test    rcx, rcx
0x18010af22  jz      short loc_18010AF3A
0x18010af24  mov     rax, [rcx]
0x18010af27  cmp     rcx, rsi
0x18010af2a  setnz   dl
  ... truncated ...
```
