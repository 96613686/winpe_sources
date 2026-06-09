# NetworkPropertyMaps::InternalGetNetworkName(_GUID const &,wchar_t * *)

- ea: `0x1800141b0`
- end: `0x18001489d`
- name: `?InternalGetNetworkName@NetworkPropertyMaps@@AEBAXAEBU_GUID@@PEAPEA_W@Z`
- size: `1773`
- prototype: `void(NetworkPropertyMaps *__hidden this, const struct _GUID *, wchar_t **)`
- caller_count: `3`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013cac`
- `0x180034940`
- `0x1800d67ec`

## callees

- `0x18000d7bc`
- `0x1800141b0`
- `0x1800148b0`
- `0x180014aa0`
- `0x180014d80`
- `0x180014e20`
- `0x180014e74`
- `0x180014fb0`
- `0x180015608`
- `0x180018968`
- `0x1800366b0`
- `0x18004c2f8`
- `0x18005a614`
- `0x18005b3e8`
- `0x1800a88a0`
- `0x1800a9738`
- `0x1800aba19`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014220`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001423a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014549`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014220`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001423a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014549`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800145de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014645`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001467f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014715`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014778`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800145de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014645`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001467f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014715`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014778`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001443f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001443f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014765`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014765`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001450f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001450f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014536`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014536`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800144b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800144b5`

## string_xrefs

- `0x18001439e`: `onecore\net\netprofiles\service\src\host\lib\networkpropertymaps.cpp`
- `0x1800147b7`: `onecore\net\netprofiles\service\src\host\lib\networkpropertymaps.cpp`
- `0x1800147cf`: `onecore\net\netprofiles\service\src\host\lib\networkpropertymaps.cpp`
- `0x180014846`: `onecore\net\netprofiles\service\src\host\lib\networkpropertymaps.cpp`
- `0x18001488b`: `onecore\net\netprofiles\service\src\host\lib\networkpropertymaps.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall NetworkPropertyMaps::InternalGetNetworkName(
        NetworkPropertyMaps *this,
        const struct _GUID *a2,
        wchar_t **a3)
{
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  bool IsProfileTlsAuthenticated; // r13
  NetworkPropertyMaps *v7; // rcx
  __int64 v8; // rdi
  __int64 v9; // r12
  __int64 v10; // rsi
  __int64 v11; // r14
  char v12; // cl
  __int64 *v13; // rax
  __int64 v14; // rax
  __int64 *v15; // rdi
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  HKEY v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rdx
  BYTE *v23; // r8
  __int16 v24; // r9
  __int64 v25; // r9
  BYTE *v26; // rcx
  __int64 i; // rax
  __int64 v28; // rax
  LPCWSTR *v29; // r9
  LSTATUS v30; // eax
  unsigned int v31; // ecx
  int v32; // eax
  __int64 v33; // rcx
  unsigned int v34; // r9d
  __int64 v35; // rdi
  __int64 v36; // r12
  __int64 v37; // rsi
  __int64 v38; // r14
  __int64 *v39; // rax
  HKEY v40; // r9
  __int64 j; // rax
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t **v46; // [rsp+38h] [rbp-C8h]
  int v47; // [rsp+4Ch] [rbp-B4h]
  char *v48; // [rsp+58h] [rbp-A8h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbData; // [rsp+68h] [rbp-98h] BYREF
  OLECHAR sz[8]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v52; // [rsp+80h] [rbp-80h]
  __int128 v53; // [rsp+90h] [rbp-70h]
  BYTE v54[30]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t Data[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR SubKey[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+528h] [rbp+428h]

  v46 = a3;
  *a3 = 0;
  memset_0(Data, 0, 0x202u);
  cbData = GetPolicyData(a2, 1u, Data);
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 784);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 784));
  v48 = (char *)this + 784;
  IsProfileTlsAuthenticated = NetworkPropertyMaps::IsProfileTlsAuthenticated(a2);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 784));
  pv = (char *)this + 824;
  v8 = *((_QWORD *)this + 103);
  v9 = *(_QWORD *)(v8 + 8);
  v47 = 0;
  v10 = v8;
  v11 = v9;
  if ( !*(_BYTE *)(v9 + 25) )
  {
    do
    {
      if ( memcmp_0((const void *)(v11 + 32), a2, 0x10u) < 0 )
      {
        v12 = 1;
      }
      else
      {
        v12 = 0;
        v10 = v11;
      }
      v13 = (__int64 *)(v11 + 16);
      if ( !v12 )
        v13 = (__int64 *)v11;
      v11 = *v13;
    }
    while ( !*(_BYTE *)(*v13 + 25) );
  }
  v47 = 0;
  while ( !*(_BYTE *)(v9 + 25) )
  {
    if ( memcmp_0(a2, (const void *)(v9 + 32), 0x10u) < 0 )
    {
      v8 = v9;
      v9 = *(_QWORD *)v9;
    }
    else
    {
      v9 = *(_QWORD *)(v9 + 16);
    }
  }
  while ( 1 )
  {
    if ( v10 == v8 )
    {
      if ( v5 )
        LeaveCriticalSection(v5);
      LOBYTE(v7) = 0;
      goto LABEL_15;
    }
    if ( *(_BYTE *)(v10 + 157) )
      break;
    v7 = *(NetworkPropertyMaps **)(v10 + 16);
    if ( *((_BYTE *)v7 + 25) )
    {
      for ( i = *(_QWORD *)(v10 + 8); !*(_BYTE *)(i + 25); i = *(_QWORD *)(i + 8) )
      {
        if ( v10 != *(_QWORD *)(i + 16) )
          break;
        v10 = i;
      }
      v10 = i;
    }
    else
    {
      v10 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<ConnectedProcess>>>>::_Min();
    }
  }
  if ( v5 )
    LeaveCriticalSection(v5);
  LOBYTE(v7) = 1;
LABEL_15:
  v14 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&g_unidentifiedGuid.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&g_unidentifiedGuid.Data1 )
    v14 = *(_QWORD *)a2->Data4 - *(_QWORD *)g_unidentifiedGuid.Data4;
  if ( v14 )
  {
    v28 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&g_identifyingGuid.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&g_identifyingGuid.Data1 )
      v28 = *(_QWORD *)a2->Data4 - *(_QWORD *)g_identifyingGuid.Data4;
    if ( v28 )
    {
      if ( !IsProfileTlsAuthenticated && !(_BYTE)v7 )
      {
        *(_OWORD *)sz = 0;
        v52 = 0;
        v53 = 0;
        memset(v54, 0, sizeof(v54));
        StringFromGUID2(a2, sz, 39);
        if ( cbData == 1 )
        {
          hKey = 0;
          v29 = &qword_1801C7140;
          if ( (unsigned __int64)qword_1801C7158 > 7 )
            v29 = (LPCWSTR *)qword_1801C7140;
          StringCchPrintfW(SubKey, 0x78u, L"%s\\%s", v29, sz);
          v30 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
          v31 = v30;
          if ( v30 > 0 )
            v31 = (unsigned __int16)v30 | 0x80070000;
          if ( v31 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x546,
              (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\networkpropertymaps.cpp",
              v31 != 0 ? (const char *)0x8000FFFFLL : 0,
              phkResulta);
          cbData = 514;
          v32 = RegQueryValueExW(hKey, L"ProfileName", 0, 0, (LPBYTE)Data, &cbData);
          if ( v32 > 0 )
            v32 = (unsigned __int16)v32 | 0x80070000;
          if ( v32 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x549,
              (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\networkpropertymaps.cpp",
              (const char *)(unsigned int)v32,
              phkResultb);
          if ( hKey )
            RegCloseKey(hKey);
        }
        else if ( (cbData & 0x80000000) != 0 )
        {
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x54D,
            (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\networkpropertymaps.cpp",
            (const char *)cbData,
            phkResult);
        }
        v15 = (__int64 *)pv;
        goto LABEL_55;
      }
LABEL_20:
      hKey = 0;
      v15 = (__int64 *)pv;
      std::_Tree<std::_Tmap_traits<_GUID,ACTIVE_NETWORK,std::less<_GUID>,std::allocator<std::pair<_GUID const,ACTIVE_NETWORK>>,1>>::lower_bound(
        pv,
        &hKey,
        a2);
      if ( hKey == *(HKEY *)pv )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v17, v16, v18, v19);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x537,
          (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\networkpropertymaps.cpp",
          (const char *)0x8000FFFFLL,
          phkResult);
      }
      v20 = hKey + 12;
      if ( *((_QWORD *)hKey + 9) > 7u )
        v20 = *(HKEY *)v20;
      v21 = 2147483646;
      v22 = 257;
      v23 = (BYTE *)Data;
      do
      {
        if ( !v21 )
          break;
        v24 = *(_WORD *)v20;
        if ( !*(_WORD *)v20 )
          break;
        v20 = (HKEY)((char *)v20 + 2);
        *(_WORD *)v23 = v24;
        v23 += 2;
        --v21;
        --v22;
      }
      while ( v22 );
      v25 = 2147942522LL;
      if ( v22 )
        v25 = 0;
      v26 = v23 - 2;
      if ( v22 )
        v26 = v23;
      *(_WORD *)v26 = 0;
      if ( !v22 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x53A,
          (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\networkpropertymaps.cpp",
          (const char *)v25,
          phkResult);
LABEL_55:
      hKey = 0;
      EnterCriticalSection(v5);
      v35 = *v15;
      v36 = *(_QWORD *)(v35 + 8);
      v47 = 0;
      v37 = v35;
      v38 = v36;
      if ( !*(_BYTE *)(v36 + 25) )
      {
        do
        {
          if ( memcmp_0((const void *)(v38 + 32), a2, 0x10u) < 0 )
          {
            LOBYTE(v33) = 1;
          }
          else
          {
            LOBYTE(v33) = 0;
            v37 = v38;
          }
          v39 = (__int64 *)(v38 + 16);
          if ( !(_BYTE)v33 )
            v39 = (__int64 *)v38;
          v38 = *v39;
        }
        while ( !*(_BYTE *)(*v39 + 25) );
      }
      while ( !*(_BYTE *)(v36 + 25) )
      {
        if ( memcmp_0(a2, (const void *)(v36 + 32), 0x10u) < 0 )
        {
          v35 = v36;
          v36 = *(_QWORD *)v36;
        }
        else
        {
          v36 = *(_QWORD *)(v36 + 16);
        }
      }
      while ( 1 )
      {
        if ( v37 == v35 )
        {
          if ( v5 )
            goto LABEL_67;
          goto LABEL_68;
        }
        if ( *(_BYTE *)(v37 + 157) )
        {
          if ( v5 )
            goto LABEL_87;
          goto LABEL_88;
        }
        if ( *(_DWORD *)(v37 + 144) )
        {
          if ( v5 )
LABEL_67:
            LeaveCriticalSection(v5);
LABEL_68:
          wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
            &pv,
            Data);
          wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
            &hKey,
            pv);
          goto LABEL_69;
        }
        if ( (*(_DWORD *)(v37 + 204) & 0x10000) != 0 )
          break;
        v33 = *(_QWORD *)(v37 + 16);
        if ( *(_BYTE *)(v33 + 25) )
        {
          for ( j = *(_QWORD *)(v37 + 8); !*(_BYTE *)(j + 25); j = *(_QWORD *)(j + 8) )
          {
            if ( v37 != *(_QWORD *)(j + 16) )
              break;
            v37 = j;
          }
          v37 = j;
        }
        else
        {
          v37 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<ConnectedProcess>>>>::_Min();
        }
      }
      if ( v5 )
LABEL_87:
        LeaveCriticalSection(v5);
LABEL_88:
      AppendSuffix((const wchar_t *)v33, Data, &g_unauthenticatedString, v34, SubKey);
      wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
        &pv,
        SubKey);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
        &hKey,
        &pv);
      if ( pv )
        CoTaskMemFree(pv);
LABEL_69:
      v40 = hKey;
      *v46 = (wchar_t *)hKey;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_87eca99fb86d3f2974af9b60843a1c5f_Traceguids, v40);
      if ( v5 )
        goto LABEL_73;
      return;
    }
  }
  if ( IsProfileTlsAuthenticated || (_BYTE)v7 )
    goto LABEL_20;
  NetworkPropertyMaps::GetDefaultName(v7, a2, v46);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_87eca99fb86d3f2974af9b60843a1c5f_Traceguids, *v46);
  if ( v5 )
LABEL_73:
    LeaveCriticalSection(v5);
}

```

## disassembly

```asm
0x1800141b0  mov     [rsp-8+arg_18], rbx
0x1800141b5  push    rbp
0x1800141b6  push    rsi
0x1800141b7  push    rdi
0x1800141b8  push    r12
0x1800141ba  push    r13
0x1800141bc  push    r14
0x1800141be  push    r15
0x1800141c0  lea     rbp, [rsp-3F0h]
0x1800141c8  sub     rsp, 4F0h
0x1800141cf  mov     rax, cs:__security_cookie
0x1800141d6  xor     rax, rsp
0x1800141d9  mov     [rbp+420h+var_40], rax
0x1800141e0  mov     [rsp+520h+var_4E8], r8
0x1800141e5  mov     r15, rdx
0x1800141e8  mov     rdi, rcx
0x1800141eb  xor     ecx, ecx
0x1800141ed  mov     [r8], rcx
0x1800141f0  xor     edx, edx; Val
0x1800141f2  mov     r8d, 202h; Size
0x1800141f8  lea     rcx, [rbp+420h+Data]; void *
0x1800141fc  call    memset_0
0x180014201  lea     r8, [rbp+420h+Data]
0x180014205  mov     edx, 1; unsigned int
0x18001420a  mov     rcx, r15; Buf1
0x18001420d  call    ?GetPolicyData@@YAJPEBU_GUID@@KZZ; GetPolicyData(_GUID const *,ulong,...)
0x180014212  mov     [rsp+520h+cbData], eax
0x180014216  lea     rbx, [rdi+310h]
0x18001421d  mov     rcx, rbx; lpCriticalSection
0x180014220  call    cs:__imp_EnterCriticalSection
0x180014226  mov     [rsp+520h+var_4C8], rbx
0x18001422b  mov     rcx, r15; Buf1
0x18001422e  call    ?IsProfileTlsAuthenticated@NetworkPropertyMaps@@SA_NAEBU_GUID@@@Z; NetworkPropertyMaps::IsProfileTlsAuthenticated(_GUID const &)
0x180014233  movzx   r13d, al
0x180014237  mov     rcx, rbx; lpCriticalSection
0x18001423a  call    cs:__imp_EnterCriticalSection
0x180014240  lea     rax, [rdi+338h]
0x180014247  mov     [rsp+520h+pv], rax
0x18001424c  mov     rdi, [rax]
0x18001424f  mov     r12, [rdi+8]
0x180014253  xor     eax, eax
0x180014255  mov     [rsp+520h+var_4D4], eax
0x180014259  mov     rsi, rdi
0x18001425c  mov     r14, r12
0x18001425f  cmp     [r12+19h], al
0x180014264  jnz     short loc_180014299
0x180014266  lea     rcx, [r14+20h]; Buf1
0x18001426a  mov     r8d, 10h; Size
0x180014270  mov     rdx, r15; Buf2
0x180014273  call    memcmp_0
0x180014278  test    eax, eax
0x18001427a  js      loc_1800143B0
0x180014280  xor     cl, cl
0x180014282  mov     rsi, r14
0x180014285  lea     rax, [r14+10h]
0x180014289  test    cl, cl
0x18001428b  cmovz   rax, r14
0x18001428f  mov     r14, [rax]
0x180014292  cmp     byte ptr [r14+19h], 0
0x180014297  jz      short loc_180014266
0x180014299  xor     eax, eax
0x18001429b  mov     [rsp+520h+var_4D4], eax
0x18001429f  cmp     [r12+19h], al
0x1800142a4  jnz     short loc_1800142CE
0x1800142a6  lea     rdx, [r12+20h]; Buf2
0x1800142ab  mov     r8d, 10h; Size
0x1800142b1  mov     rcx, r15; Buf1
0x1800142b4  call    memcmp_0
0x1800142b9  test    eax, eax
0x1800142bb  js      loc_1800146AE
0x1800142c1  mov     r12, [r12+10h]
0x1800142c6  cmp     byte ptr [r12+19h], 0
0x1800142cc  jz      short loc_1800142A6
0x1800142ce  cmp     rsi, rdi
0x1800142d1  jnz     loc_1800143B7
0x1800142d7  test    rbx, rbx
0x1800142da  jnz     loc_18001467C
0x1800142e0  xor     cl, cl; this
0x1800142e2  mov     rax, [r15]
0x1800142e5  sub     rax, qword ptr cs:?g_unidentifiedGuid@@3U_GUID@@A.Data1; _GUID g_unidentifiedGuid ...
0x1800142ec  jnz     short loc_1800142F9
0x1800142ee  mov     rax, [r15+8]
0x1800142f2  sub     rax, qword ptr cs:?g_unidentifiedGuid@@3U_GUID@@A.Data4; _GUID g_unidentifiedGuid ...
0x1800142f9  test    rax, rax
0x1800142fc  jnz     loc_1800143E8
0x180014302  test    r13b, r13b
0x180014305  jnz     short loc_18001430F
0x180014307  test    cl, cl
0x180014309  jz      loc_180014803
0x18001430f  xor     esi, esi
0x180014311  mov     [rsp+520h+hKey], rsi
0x180014316  mov     r8, r15
0x180014319  lea     rdx, [rsp+520h+hKey]
0x18001431e  mov     rdi, [rsp+520h+pv]
0x180014323  mov     rcx, rdi
0x180014326  call    ?lower_bound@?$_Tree@V?$_Tmap_traits@U_GUID@@UACTIVE_NETWORK@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@UACTIVE_NETWORK@@@std@@@4@$00@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UACTIVE_NETWORK@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,ACTIVE_NETWORK,std::less<_GUID>,std::allocator<std::pair<_GUID const,ACTIVE_NETWORK>>,1>>::lower_bound(_GUID const &)
0x18001432b  mov     rax, [rsp+520h+hKey]
0x180014330  cmp     rax, [rdi]
0x180014333  jz      loc_180014879
0x180014339  add     rax, 30h ; '0'
0x18001433d  cmp     qword ptr [rax+18h], 7
0x180014342  jbe     short loc_180014347
0x180014344  mov     rax, [rax]
0x180014347  mov     ecx, 7FFFFFFEh
0x18001434c  mov     edx, 101h
0x180014351  lea     r8, [rbp+420h+Data]
0x180014355  test    rcx, rcx
0x180014358  jz      short loc_180014379
0x18001435a  movzx   r9d, word ptr [rax]
0x18001435e  test    r9w, r9w
0x180014362  jz      short loc_180014379
0x180014364  add     rax, 2
0x180014368  mov     [r8], r9w
0x18001436c  add     r8, 2
0x180014370  dec     rcx
0x180014373  sub     rdx, 1
0x180014377  jnz     short loc_180014355
0x180014379  mov     r9d, 8007007Ah
0x18001437f  test    rdx, rdx
0x180014382  cmovnz  r9d, esi; char *
0x180014386  lea     rcx, [r8-2]
0x18001438a  cmovnz  rcx, r8
0x18001438e  mov     [rcx], si
0x180014391  mov     rcx, [rbp+428h]; this
0x180014398  jnz     loc_180014541
0x18001439e  lea     r8, aOnecoreNetNetp_33; "onecore\\net\\netprofiles\\service\\src"...
0x1800143a5  mov     edx, 53Ah; void *
0x1800143aa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800143b0  mov     cl, 1
0x1800143b2  jmp     loc_180014285
0x1800143b7  cmp     byte ptr [rsi+9Dh], 0
0x1800143be  jnz     loc_180014770
0x1800143c4  mov     rcx, [rsi+10h]
0x1800143c8  cmp     byte ptr [rcx+19h], 0
0x1800143cc  jz      loc_1800146E1
0x1800143d2  mov     rax, [rsi+8]
0x1800143d6  cmp     byte ptr [rax+19h], 0
0x1800143da  jz      loc_1800146F0
0x1800143e0  mov     rsi, rax
0x1800143e3  jmp     loc_1800142CE
0x1800143e8  mov     rax, [r15]
0x1800143eb  sub     rax, qword ptr cs:?g_identifyingGuid@@3U_GUID@@A.Data1; _GUID g_identifyingGuid ...
0x1800143f2  jnz     short loc_1800143FF
0x1800143f4  mov     rax, [r15+8]
0x1800143f8  sub     rax, qword ptr cs:?g_identifyingGuid@@3U_GUID@@A.Data4; _GUID g_identifyingGuid ...
0x1800143ff  test    rax, rax
0x180014402  jz      loc_180014302
0x180014408  test    r13b, r13b
0x18001440b  jnz     loc_18001430F
0x180014411  test    cl, cl
0x180014413  jnz     loc_18001430F
0x180014419  xorps   xmm0, xmm0
0x18001441c  movups  xmmword ptr [rsp+520h+sz], xmm0
0x180014421  movups  [rbp+420h+var_4A0], xmm0
0x180014425  movups  [rbp+420h+var_490], xmm0
0x180014429  movups  xmmword ptr [rbp+420h+var_480], xmm0
0x18001442d  movups  xmmword ptr [rbp+420h+var_480+0Eh], xmm0
0x180014431  mov     r8d, 27h ; '''; cchMax
0x180014437  lea     rdx, [rsp+520h+sz]; lpsz
0x18001443c  mov     rcx, r15; rguid
0x18001443f  call    cs:__imp_StringFromGUID2
0x180014445  mov     r9d, [rsp+520h+cbData]; char *
0x18001444a  cmp     r9d, 1
0x18001444e  jnz     loc_18001483A
0x180014454  xor     esi, esi
0x180014456  mov     [rsp+520h+hKey], rsi
0x18001445b  lea     r9, qword_1801C7140
0x180014462  cmp     cs:qword_1801C7158, 7
0x18001446a  cmova   r9, cs:qword_1801C7140
0x180014472  lea     rax, [rsp+520h+sz]
0x180014477  mov     [rsp+520h+phkResult], rax
0x18001447c  lea     r8, aSS; "%s\\%s"
0x180014483  mov     edx, 78h ; 'x'; unsigned __int64
0x180014488  lea     rcx, [rbp+420h+SubKey]; wchar_t *
0x18001448f  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180014494  lea     rax, [rsp+520h+hKey]
0x180014499  mov     [rsp+520h+phkResult], rax; int
0x18001449e  mov     r9d, 20019h; samDesired
0x1800144a4  xor     r8d, r8d; ulOptions
0x1800144a7  lea     rdx, [rbp+420h+SubKey]; lpSubKey
0x1800144ae  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800144b5  call    cs:__imp_RegOpenKeyExW
0x1800144bb  mov     ecx, eax
0x1800144bd  test    eax, eax
0x1800144bf  jg      loc_1800146C6
0x1800144c5  mov     eax, ecx
0x1800144c7  neg     eax
0x1800144c9  sbb     r9d, r9d
0x1800144cc  and     r9d, 8000FFFFh; char *
0x1800144d3  mov     rax, [rbp+428h]
0x1800144da  test    ecx, ecx
0x1800144dc  jnz     loc_1800147B7
0x1800144e2  mov     [rsp+520h+cbData], 202h
0x1800144ea  lea     rax, [rsp+520h+cbData]
0x1800144ef  mov     [rsp+520h+lpcbData], rax; lpcbData
0x1800144f4  lea     rax, [rbp+420h+Data]
0x1800144f8  mov     [rsp+520h+phkResult], rax; int
0x1800144fd  xor     r9d, r9d; lpType
0x180014500  xor     r8d, r8d; lpReserved
0x180014503  lea     rdx, Value; "ProfileName"
0x18001450a  mov     rcx, [rsp+520h+hKey]; hKey
0x18001450f  call    cs:__imp_RegQueryValueExW
0x180014515  test    eax, eax
0x180014517  jg      loc_1800146D4
0x18001451d  mov     rcx, [rbp+428h]; this
0x180014524  test    eax, eax
0x180014526  js      loc_1800147CC
0x18001452c  mov     rcx, [rsp+520h+hKey]; hKey
0x180014531  test    rcx, rcx
0x180014534  jz      short loc_18001453C
0x180014536  call    cs:__imp_RegCloseKey
0x18001453c  mov     rdi, [rsp+520h+pv]
0x180014541  mov     [rsp+520h+hKey], rsi
0x180014546  mov     rcx, rbx; lpCriticalSection
0x180014549  call    cs:__imp_EnterCriticalSection
0x18001454f  mov     rdi, [rdi]
0x180014552  mov     r12, [rdi+8]
0x180014556  xor     eax, eax
0x180014558  mov     [rsp+520h+var_4D4], eax
0x18001455c  mov     rsi, rdi
0x18001455f  mov     r14, r12
0x180014562  cmp     [r12+19h], al
0x180014567  jnz     short loc_18001459C
0x180014569  lea     rcx, [r14+20h]; Buf1
0x18001456d  mov     r8d, 10h; Size
0x180014573  mov     rdx, r15; Buf2
0x180014576  call    memcmp_0
0x18001457b  test    eax, eax
0x18001457d  js      loc_180014675
0x180014583  xor     cl, cl
0x180014585  mov     rsi, r14
0x180014588  lea     rax, [r14+10h]
0x18001458c  test    cl, cl
0x18001458e  cmovz   rax, r14
0x180014592  mov     r14, [rax]
0x180014595  cmp     byte ptr [r14+19h], 0
0x18001459a  jz      short loc_180014569
0x18001459c  xor     eax, eax
0x18001459e  cmp     [r12+19h], al
0x1800145a3  jnz     short loc_1800145CD
0x1800145a5  lea     rdx, [r12+20h]; Buf2
0x1800145aa  mov     r8d, 10h; Size
0x1800145b0  mov     rcx, r15; Buf1
0x1800145b3  call    memcmp_0
0x1800145b8  test    eax, eax
0x1800145ba  js      loc_1800146BA
0x1800145c0  mov     r12, [r12+10h]
0x1800145c5  cmp     byte ptr [r12+19h], 0
0x1800145cb  jz      short loc_1800145A5
0x1800145cd  cmp     rsi, rdi
0x1800145d0  jnz     loc_18001468A
0x1800145d6  test    rbx, rbx
0x1800145d9  jz      short loc_1800145E4
0x1800145db  mov     rcx, rbx; lpCriticalSection
0x1800145de  call    cs:__imp_LeaveCriticalSection
0x1800145e4  lea     rdx, [rbp+420h+Data]
0x1800145e8  lea     rcx, [rsp+520h+pv]
0x1800145ed  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x1800145f2  mov     rdx, [rsp+520h+pv]
0x1800145f7  lea     rcx, [rsp+520h+hKey]
0x1800145fc  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x180014601  mov     r9, [rsp+520h+hKey]
0x180014606  mov     rdi, [rsp+520h+var_4E8]
0x18001460b  mov     [rdi], r9
0x18001460e  lea     rax, WPP_GLOBAL_Control
0x180014615  mov     rcx, cs:WPP_GLOBAL_Control
0x18001461c  cmp     rcx, rax
0x18001461f  jz      short loc_18001463D
0x180014621  test    byte ptr [rcx+1Ch], 8
0x180014625  jz      short loc_18001463D
0x180014627  mov     edx, 15h
0x18001462c  lea     r8, WPP_87eca99fb86d3f2974af9b60843a1c5f_Traceguids
0x180014633  mov     rcx, [rcx+10h]
0x180014637  call    WPP_SF_S
0x18001463c  nop
0x18001463d  test    rbx, rbx
0x180014640  jz      short loc_18001464B
0x180014642  mov     rcx, rbx; lpCriticalSection
0x180014645  call    cs:__imp_LeaveCriticalSection
0x18001464b  mov     rcx, [rbp+420h+var_40]
0x180014652  xor     rcx, rsp; StackCookie
0x180014655  call    __security_check_cookie
0x18001465a  mov     rbx, [rsp+520h+arg_18]
0x180014662  add     rsp, 4F0h
0x180014669  pop     r15
0x18001466b  pop     r14
0x18001466d  pop     r13
0x18001466f  pop     r12
0x180014671  pop     rdi
0x180014672  pop     rsi
0x180014673  pop     rbp
0x180014674  retn
0x180014675  mov     cl, 1
0x180014677  jmp     loc_180014588
0x18001467c  mov     rcx, rbx; lpCriticalSection
0x18001467f  call    cs:__imp_LeaveCriticalSection
0x180014685  jmp     loc_1800142E0
0x18001468a  cmp     byte ptr [rsi+9Dh], 0
0x180014691  jnz     short loc_18001470D
0x180014693  cmp     dword ptr [rsi+90h], 0
  ... truncated ...
```
