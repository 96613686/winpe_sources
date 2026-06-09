# DAS::ProviderManagement::ProviderManager::ProcessRegChange(void)

- ea: `0x140012c08`
- end: `0x14001372c`
- name: `?ProcessRegChange@ProviderManager@ProviderManagement@DAS@@QEAAJXZ`
- size: `2852`
- prototype: `__int64 __fastcall(DAS::ProviderManagement::ProviderManager *__hidden this)`
- caller_count: `2`
- callee_count: `24`
- tags: `file_ops, registry_config`

## callers

- `0x140009160`
- `0x140012748`

## callees

- `0x140001570`
- `0x140001594`
- `0x1400018d4`
- `0x14000190c`
- `0x1400020d0`
- `0x14000217c`
- `0x140006ce4`
- `0x1400106b4`
- `0x140011224`
- `0x1400115a8`
- `0x140011650`
- `0x14001176c`
- `0x140011a10`
- `0x140011ab0`
- `0x1400128a0`
- `0x140012c08`
- `0x140013754`
- `0x1400142dc`
- `0x140014570`
- `0x1400145b8`
- `0x1400149d8`
- `0x140014a38`
- `0x140014fd8`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140012f0d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140013255`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140012f0d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140013255`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400136e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400136e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001314b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400134a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400134cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001314b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400134a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400134cf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140013542`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140013542`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140012d6d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140012d6d`

## string_xrefs

- `0x140012db1`: `failed to read subkeys in %ws`

## pseudocode

```c
__int64 __fastcall DAS::ProviderManagement::ProviderManager::ProcessRegChange(
        DAS::ProviderManagement::ProviderManager *this)
{
  int v1; // eax
  unsigned int v2; // ebx
  unsigned int v3; // r8d
  const char *v4; // r9
  __int64 result; // rax
  int i; // r15d
  LSTATUS v7; // r14d
  DWORD j; // r12d
  LSTATUS v9; // eax
  unsigned int v10; // edi
  __int64 v11; // rdx
  RTL_SRWLOCK *v12; // rdi
  RTL_SRWLOCK *v13; // r13
  RTL_SRWLOCK *v14; // r12
  __int64 *v15; // rbx
  __int64 v16; // rax
  volatile signed __int32 *v17; // rdi
  __int64 k; // r14
  __int64 v19; // r15
  const wchar_t *v20; // rdx
  const wchar_t *p_S1; // rcx
  int v22; // eax
  __int64 **v23; // rcx
  __int64 *m; // rax
  __int64 *n; // rcx
  volatile signed __int32 *v26; // rbx
  __int64 v27; // rbx
  __int64 v28; // rdi
  __int64 v29; // r14
  __int64 v30; // r9
  size_t *v31; // rcx
  int v32; // eax
  unsigned int v33; // ebx
  RTL_SRWLOCK *v34; // rbx
  _DWORD *v35; // r12
  __int64 inserted; // r15
  const wchar_t *v37; // rdx
  wchar_t *v38; // rbx
  const wchar_t *v39; // rcx
  wchar_t *v40; // r8
  int v41; // eax
  __int64 v42; // r15
  _OWORD *v43; // rbx
  volatile signed __int32 *v44; // rbx
  PVOID Ptr; // rdi
  const wchar_t *v46; // rdx
  wchar_t *v47; // r14
  wchar_t *v48; // r15
  const wchar_t *v49; // rcx
  wchar_t *v50; // r8
  int v51; // eax
  __int64 v52; // r14
  __int64 v53; // r12
  __int64 v54; // rdi
  __int64 v55; // rax
  char **v56; // r15
  unsigned __int64 v57; // rdx
  char *v58; // rax
  unsigned __int64 v59; // rdx
  char *v60; // rcx
  int lpReserved; // [rsp+20h] [rbp-358h]
  int lpReserveda; // [rsp+20h] [rbp-358h]
  DWORD cchName[2]; // [rsp+40h] [rbp-338h] BYREF
  __int128 v64; // [rsp+48h] [rbp-330h] BYREF
  __int64 v65; // [rsp+58h] [rbp-320h]
  int v66[2]; // [rsp+60h] [rbp-318h] BYREF
  HKEY hKey[2]; // [rsp+68h] [rbp-310h] BYREF
  RTL_SRWLOCK *v68; // [rsp+78h] [rbp-300h]
  PSRWLOCK SRWLock; // [rsp+80h] [rbp-2F8h]
  __int128 v70; // [rsp+90h] [rbp-2E8h] BYREF
  RTL_SRWLOCK *v71; // [rsp+A0h] [rbp-2D8h]
  RTL_SRWLOCK *v72; // [rsp+A8h] [rbp-2D0h]
  __int64 *v73; // [rsp+B0h] [rbp-2C8h] BYREF
  __int64 v74; // [rsp+B8h] [rbp-2C0h]
  __int128 v75; // [rsp+C0h] [rbp-2B8h] BYREF
  __int64 v76; // [rsp+D0h] [rbp-2A8h]
  wchar_t *v77[2]; // [rsp+D8h] [rbp-2A0h] BYREF
  wchar_t *S2[2]; // [rsp+E8h] [rbp-290h] BYREF
  __int64 v79; // [rsp+F8h] [rbp-280h]
  unsigned __int64 v80; // [rsp+100h] [rbp-278h]
  wchar_t *S1; // [rsp+108h] [rbp-270h] BYREF
  __int64 v82; // [rsp+110h] [rbp-268h]
  size_t N[3]; // [rsp+118h] [rbp-260h] BYREF
  unsigned __int64 v84; // [rsp+130h] [rbp-248h]
  WCHAR Name[256]; // [rsp+140h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+378h] [rbp+0h]

  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    *(_QWORD *)v66 = this;
    `eh vector constructor iterator'(
      hKey,
      8u,
      2u,
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>,
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>);
    v1 = DAS::ProviderManagement::ProviderManager::OpenKeysStatic((__int64)hKey);
    v2 = v1;
    if ( v1 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x34C,
        (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
        (const char *)(unsigned int)v1,
        lpReserveda);
      `eh vector destructor iterator'(
        hKey,
        8u,
        2u,
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>);
      return v2;
    }
    v64 = 0;
    v65 = 0;
    for ( i = 0; (unsigned __int64)i < 2; ++i )
    {
      if ( hKey[i] )
      {
        v7 = 0;
        for ( j = 0; !v7; ++j )
        {
          cchName[0] = 255;
          memset_0(Name, 0, 0x1FEu);
          v9 = RegEnumKeyExW(hKey[i], j, Name, cchName, 0, 0, 0, 0);
          v7 = v9;
          if ( v9 == 259 )
            break;
          if ( v9 )
          {
            if ( v9 > 0 )
              v10 = (unsigned __int16)v9 | 0x80070000;
            else
              v10 = v9;
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0x36A,
              (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
              (const char *)v10,
              (int)"failed to read subkeys in %ws",
              (const char *)*(&DAS::ProviderManagement::c_providerRegistrationPaths + 3 * i + 1));
            std::vector<std::tuple<std::wstring,HKEY__ *,bool,enum _DAF_PROVIDER_PATH>>::~vector<std::tuple<std::wstring,HKEY__ *,bool,enum _DAF_PROVIDER_PATH>>((char ***)&v64);
            `eh vector destructor iterator'(
              hKey,
              8u,
              2u,
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>);
            return v10;
          }
          LODWORD(v77[0]) = i;
          BYTE4(v77[0]) = *((_BYTE *)&DAS::ProviderManagement::c_providerRegistrationPaths + 24 * i + 16);
          v77[1] = (wchar_t *)hKey[i];
          std::wstring::wstring(S2);
          v11 = *((_QWORD *)&v64 + 1);
          if ( *((_QWORD *)&v64 + 1) == v65 )
          {
            std::vector<std::tuple<std::wstring,HKEY__ *,bool,enum _DAF_PROVIDER_PATH>>::_Emplace_reallocate<std::tuple<std::wstring,HKEY__ *,bool,enum _DAF_PROVIDER_PATH>>(
              (void **)&v64,
              *((char **)&v64 + 1),
              (__int64)v77);
          }
          else
          {
            **((_DWORD **)&v64 + 1) = v77[0];
            *(_BYTE *)(v11 + 4) = BYTE4(v77[0]);
            *(wchar_t **)(v11 + 8) = v77[1];
            *(_WORD *)(v11 + 16) = S2[0];
            *(wchar_t **)(v11 + 18) = *(wchar_t **)((char *)S2 + 2);
            *(_DWORD *)(v11 + 26) = *(_DWORD *)((char *)&S2[1] + 2);
            *(_WORD *)(v11 + 30) = HIWORD(S2[1]);
            *(_QWORD *)(v11 + 32) = v79;
            *(_QWORD *)(v11 + 40) = v80;
            v79 = 0;
            v80 = 7;
            LOWORD(S2[0]) = 0;
            *((_QWORD *)&v64 + 1) += 48LL;
          }
          std::wstring::~wstring((char **)S2);
        }
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          WPP_c259ffd365a33e780ba81409624fcc4e_Traceguids,
          *(&DAS::ProviderManagement::c_providerRegistrationPaths + 3 * i + 1));
      }
    }
    v12 = *(RTL_SRWLOCK **)v66;
    v13 = (RTL_SRWLOCK *)(*(_QWORD *)v66 + 24LL);
    AcquireSRWLockExclusive((PSRWLOCK)(*(_QWORD *)v66 + 24LL));
    SRWLock = v13;
    v14 = v12 + 4;
    *(_QWORD *)cchName = v12 + 4;
    v15 = *(__int64 **)v12[4].Ptr;
LABEL_24:
    if ( !*((_BYTE *)v15 + 25) )
    {
      std::wstring::wstring((__int64)&S1, (__int64)(v15 + 4));
      v16 = v15[9];
      if ( v16 )
        _InterlockedIncrement((volatile signed __int32 *)(v16 + 8));
      N[2] = v15[8];
      v17 = (volatile signed __int32 *)v15[9];
      v84 = (unsigned __int64)v17;
      v19 = *((_QWORD *)&v64 + 1);
      for ( k = v64; k != v19; k += 48 )
      {
        LODWORD(v77[0]) = *(_DWORD *)k;
        BYTE4(v77[0]) = *(_BYTE *)(k + 4);
        v77[1] = *(wchar_t **)(k + 8);
        std::wstring::wstring((__int64)S2, k + 16);
        v20 = (const wchar_t *)S2;
        if ( v80 > 7 )
          v20 = S2[0];
        p_S1 = (const wchar_t *)&S1;
        if ( N[1] > 7 )
          p_S1 = S1;
        if ( N[0] == v79 )
        {
          if ( !N[0] || (v22 = wmemcmp(p_S1, v20, N[0]), v17 = (volatile signed __int32 *)v84, !v22) )
          {
            std::wstring::~wstring((char **)S2);
            if ( v17 )
            {
              if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
                if ( !_InterlockedDecrement(v17 + 3) )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
              }
            }
            std::wstring::~wstring((char **)&S1);
            v23 = (__int64 **)v15[2];
            if ( *((_BYTE *)v23 + 25) )
            {
              for ( m = (__int64 *)v15[1]; !*((_BYTE *)m + 25) && v15 == (__int64 *)m[2]; m = (__int64 *)m[1] )
                v15 = m;
              v15 = m;
            }
            else
            {
              v15 = (__int64 *)v15[2];
              for ( n = *v23; !*((_BYTE *)n + 25); n = (__int64 *)*n )
                v15 = n;
            }
            goto LABEL_24;
          }
        }
        std::wstring::~wstring((char **)S2);
      }
      std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ProviderContext>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ProviderContext>>>,0>>::erase(
        v14,
        &S1);
      v26 = (volatile signed __int32 *)v84;
      if ( v84 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v84 + 8), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
          if ( !_InterlockedDecrement(v26 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
        }
      }
      std::wstring::~wstring((char **)&S1);
    }
    SRWLock = v13;
    if ( v13 )
      ReleaseSRWLockExclusive(v13);
    v27 = v64;
    while ( 1 )
    {
      v28 = *((_QWORD *)&v64 + 1);
      if ( v27 == *((_QWORD *)&v64 + 1) )
      {
        v29 = v64;
        while ( 2 )
        {
          if ( v29 == v28 )
          {
            std::vector<std::tuple<std::wstring,HKEY__ *,bool,enum _DAF_PROVIDER_PATH>>::~vector<std::tuple<std::wstring,HKEY__ *,bool,enum _DAF_PROVIDER_PATH>>((char ***)&v64);
            `eh vector destructor iterator'(
              hKey,
              8u,
              2u,
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>);
            return 0;
          }
          LODWORD(S1) = *(_DWORD *)v29;
          BYTE4(S1) = *(_BYTE *)(v29 + 4);
          v82 = *(_QWORD *)(v29 + 8);
          std::wstring::wstring((__int64)N, v29 + 16);
          *(_QWORD *)v66 = 0;
          v31 = N;
          if ( v84 > 7 )
            v31 = (size_t *)N[0];
          LOBYTE(v30) = BYTE4(S1);
          v32 = ((__int64 (__fastcall *)(size_t *, _QWORD, __int64, __int64))ProviderContext::MakeAndInitialize)(
                  v31,
                  (unsigned int)S1,
                  v82,
                  v30);
          v33 = v32;
          if ( v32 == -2147024894 )
            goto LABEL_86;
          if ( v32 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3A8,
              (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
              (const char *)(unsigned int)v32,
              (int)v66);
            std::wstring::~wstring((char **)N);
            std::vector<std::tuple<std::wstring,HKEY__ *,bool,enum _DAF_PROVIDER_PATH>>::~vector<std::tuple<std::wstring,HKEY__ *,bool,enum _DAF_PROVIDER_PATH>>((char ***)&v64);
            `eh vector destructor iterator'(
              hKey,
              8u,
              2u,
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>);
            return v33;
          }
          AcquireSRWLockExclusive(v13);
          if ( __eh34_try(0, 1) )
          {
            __eh34_scope_strut(1);
            v72 = v13;
            v70 = 0;
            v34 = *(RTL_SRWLOCK **)v66;
            v71 = *(RTL_SRWLOCK **)v66;
            v68 = *(RTL_SRWLOCK **)v66;
            v35 = operator new(0x18u);
            v35[2] = 1;
            v35[3] = 1;
            *(_QWORD *)v35 = &std::_Ref_count<ProviderContext>::`vftable';
            *((_QWORD *)v35 + 2) = v34;
            *(_QWORD *)&v70 = v34;
            *((_QWORD *)&v70 + 1) = v35;
            std::wstring::wstring(v77);
            std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ProviderContext>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ProviderContext>>>,0>>::_Find_lower_bound<std::wstring>(
              *(_QWORD *)cchName,
              &v75,
              v77);
            inserted = v76;
            if ( *(_BYTE *)(v76 + 25) )
            {
LABEL_78:
              if ( *(_QWORD *)(*(_QWORD *)cchName + 8LL) == 0x333333333333333LL )
                std::_Throw_tree_length_error();
              v42 = **(_QWORD **)cchName;
              v73 = *(__int64 **)cchName;
              v74 = 0;
              v43 = operator new(0x50u);
              v43[2] = *(_OWORD *)v77;
              v43[3] = *(_OWORD *)S2;
              S2[0] = 0;
              S2[1] = (wchar_t *)7;
              LOWORD(v77[0]) = 0;
              *((_QWORD *)v43 + 8) = 0;
              *((_QWORD *)v43 + 9) = 0;
              *(_QWORD *)v43 = v42;
              *((_QWORD *)v43 + 1) = v42;
              *((_QWORD *)v43 + 2) = v42;
              *((_WORD *)v43 + 12) = 0;
              v74 = 0;
              std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ProviderContext>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ProviderContext>>,void *>>>((__int64)&v73);
              v70 = v75;
              inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<ProviderContext>>>>::_Insert_node(
                           *(_QWORD *)cchName,
                           &v70,
                           v43);
            }
            else
            {
              v37 = (const wchar_t *)(v76 + 32);
              v38 = *(wchar_t **)(v76 + 48);
              if ( *(_QWORD *)(v76 + 56) > 7u )
                v37 = *(const wchar_t **)v37;
              v68 = (RTL_SRWLOCK *)S2[0];
              v39 = (const wchar_t *)v77;
              if ( S2[1] > (wchar_t *)7 )
                v39 = v77[0];
              v40 = S2[0];
              if ( v38 < S2[0] )
                v40 = v38;
              v41 = wmemcmp(v39, v37, (size_t)v40);
              if ( v41 )
              {
                if ( v41 < 0 )
                  goto LABEL_78;
              }
              else if ( v68 < (RTL_SRWLOCK *)v38 )
              {
                goto LABEL_78;
              }
            }
            v70 = 0;
            *(_QWORD *)(inserted + 64) = v71;
            v44 = *(volatile signed __int32 **)(inserted + 72);
            *(_QWORD *)(inserted + 72) = v35;
            if ( v44 )
            {
              if ( _InterlockedExchangeAdd(v44 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v44)(v44);
                if ( !_InterlockedDecrement(v44 + 3) )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v44 + 8LL))(v44);
              }
            }
            std::wstring::~wstring((char **)v77);
            if ( v13 )
              ReleaseSRWLockExclusive(v13);
          }
          if ( __eh34_catch(1) )
          {
            if ( __eh34_catch_type(1, &std::bad_alloc `RTTI Type Descriptor', 0) )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x3B3,
                (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
                (const char *)0x8007000ELL,
                lpReserved);
              __eh34_try_continuation(1, &std::bad_alloc `RTTI Type Descriptor', &loc_1400134C2);
              if ( SRWLock )
                ReleaseSRWLockExclusive(SRWLock);
              std::wstring::~wstring((char **)N);
              std::vector<std::tuple<std::wstring,HKEY__ *,bool,enum _DAF_PROVIDER_PATH>>::~vector<std::tuple<std::wstring,HKEY__ *,bool,enum _DAF_PROVIDER_PATH>>((char ***)&v64);
              `eh vector destructor iterator'(
                hKey,
                8u,
                2u,
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>);
              return 2147942414LL;
            }
          }
LABEL_86:
          std::wstring::~wstring((char **)N);
          v29 += 48;
          continue;
        }
      }
      AcquireSRWLockShared(v13);
      v72 = v13;
      std::wstring::wstring(v77);
      std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ProviderContext>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ProviderContext>>>,0>>::_Find_lower_bound<std::wstring>(
        v14,
        &v75,
        v77);
      Ptr = (PVOID)v76;
      if ( !*(_BYTE *)(v76 + 25) )
      {
        v46 = (const wchar_t *)(v76 + 32);
        v47 = *(wchar_t **)(v76 + 48);
        if ( *(_QWORD *)(v76 + 56) > 7u )
          v46 = *(const wchar_t **)v46;
        v48 = S2[0];
        v49 = (const wchar_t *)v77;
        if ( S2[1] > (wchar_t *)7 )
          v49 = v77[0];
        v50 = S2[0];
        if ( v47 < S2[0] )
          v50 = *(wchar_t **)(v76 + 48);
        v51 = wmemcmp(v49, v46, (size_t)v50);
        if ( v51 )
        {
          if ( v51 >= 0 )
            goto LABEL_103;
        }
        else if ( v48 >= v47 )
        {
          goto LABEL_103;
        }
      }
      Ptr = v14->Ptr;
LABEL_103:
      std::wstring::~wstring((char **)v77);
      if ( Ptr == v14->Ptr )
      {
        v27 += 48;
      }
      else
      {
        v52 = v27;
        v53 = *((_QWORD *)&v64 + 1);
        v54 = v27 + 48;
        if ( v27 + 48 != *((_QWORD *)&v64 + 1) )
        {
          do
          {
            v55 = v54 + 16;
            v56 = (char **)(v52 + 16);
            if ( v52 + 16 != v54 + 16 )
            {
              v57 = *(_QWORD *)(v52 + 40);
              if ( v57 > 7 )
              {
                v58 = *v56;
                v59 = 2 * v57 + 2;
                if ( v59 < 0x1000 )
                {
                  v60 = *v56;
                }
                else
                {
                  v60 = (char *)*((_QWORD *)v58 - 1);
                  if ( (unsigned __int64)(v58 - v60 - 8) > 0x1F )
                    __fastfail(5u);
                  v59 += 39LL;
                }
                ((void (__fastcall *)(void *, unsigned __int64))operator delete)(v60, v59);
                v55 = v54 + 16;
              }
              *(_QWORD *)(v52 + 32) = 0;
              *(_QWORD *)(v52 + 40) = 7;
              *(_WORD *)v56 = 0;
              *(_OWORD *)v56 = *(_OWORD *)v55;
              *(_OWORD *)(v52 + 32) = *(_OWORD *)(v55 + 16);
              *(_QWORD *)(v55 + 16) = 0;
              *(_QWORD *)(v55 + 24) = 7;
              *(_WORD *)v55 = 0;
            }
            *(_QWORD *)(v52 + 8) = *(_QWORD *)(v54 + 8);
            *(_BYTE *)(v52 + 4) = *(_BYTE *)(v54 + 4);
            *(_DWORD *)v52 = *(_DWORD *)v54;
            v52 += 48;
            v54 += 48;
          }
          while ( v54 != v53 );
          v53 = *((_QWORD *)&v64 + 1);
        }
        std::wstring::~wstring((char **)(v53 - 32));
        *((_QWORD *)&v64 + 1) -= 48LL;
        v14 = *(RTL_SRWLOCK **)cchName;
      }
      if ( v13 )
        ReleaseSRWLockShared(v13);
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_ellipsis(0) )
    {
      __eh34_try_continuation(0, &loc_1400136F4);
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x3B9, v3, v4);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140012c08  mov     [rsp+arg_8], rbx
0x140012c0d  mov     [rsp+arg_10], rsi
0x140012c12  push    rdi
0x140012c13  push    r12
0x140012c15  push    r13
0x140012c17  push    r14
0x140012c19  push    r15
0x140012c1b  sub     rsp, 350h
0x140012c22  mov     rax, cs:__security_cookie
0x140012c29  xor     rax, rsp
0x140012c2c  mov     [rsp+378h+var_38], rax
0x140012c34  mov     qword ptr [rsp+378h+var_318], rcx
0x140012c39  lea     r14, ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(void)
0x140012c40  mov     [rsp+378h+lpReserved], r14; int
0x140012c45  lea     r9, ??0?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x140012c4c  mov     r13d, 2
0x140012c52  mov     r8d, r13d; unsigned __int64
0x140012c55  lea     edi, [r13+6]
0x140012c59  mov     edx, edi; unsigned __int64
0x140012c5b  lea     rcx, [rsp+378h+hKey]; void *
0x140012c60  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x140012c65  nop
0x140012c66  lea     rcx, [rsp+378h+hKey]
0x140012c6b  call    ?OpenKeysStatic@ProviderManager@ProviderManagement@DAS@@CAJPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z; DAS::ProviderManagement::ProviderManager::OpenKeysStatic(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> *,ulong)
0x140012c70  mov     ebx, eax
0x140012c72  xor     esi, esi
0x140012c74  test    eax, eax
0x140012c76  jns     short loc_140012CAE
0x140012c78  mov     rcx, [rsp+378h]; this
0x140012c80  mov     r9d, eax; char *
0x140012c83  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\association\\li"...
0x140012c8a  mov     edx, 34Ch; void *
0x140012c8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012c94  nop
0x140012c95  mov     r9, r14; void (*)(void *)
0x140012c98  mov     r8d, r13d; unsigned __int64
0x140012c9b  mov     edx, edi; unsigned __int64
0x140012c9d  lea     rcx, [rsp+378h+hKey]; void *
0x140012ca2  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x140012ca7  mov     eax, ebx
0x140012ca9  jmp     loc_1400136F8
0x140012cae  xorps   xmm0, xmm0
0x140012cb1  movdqu  [rsp+378h+var_330], xmm0
0x140012cb7  mov     [rsp+378h+var_320], rsi
0x140012cbc  mov     r15d, esi
0x140012cbf  lea     r8, ?c_providerRegistrationPaths@ProviderManagement@DAS@@3PAU_PROVIDER_REGISTRATION_PATH@12@A; DAS::ProviderManagement::_PROVIDER_REGISTRATION_PATH near * DAS::ProviderManagement::c_providerRegistrationPaths
0x140012cc6  movsxd  rbx, r15d
0x140012cc9  cmp     rbx, r13
0x140012ccc  jnb     loc_140012F01
0x140012cd2  cmp     [rsp+rbx*8+378h+hKey], rsi
0x140012cd7  jnz     short loc_140012D1C
0x140012cd9  lea     rax, WPP_GLOBAL_Control
0x140012ce0  mov     rcx, cs:WPP_GLOBAL_Control
0x140012ce7  cmp     rcx, rax
0x140012cea  jz      short loc_140012D17
0x140012cec  cmp     byte ptr [rcx+19h], 4
0x140012cf0  jb      short loc_140012D17
0x140012cf2  lea     r9, [rbx+rbx*2]
0x140012cf6  mov     edx, 1Fh
0x140012cfb  mov     r9, [r8+r9*8+8]
0x140012d00  lea     r8, WPP_c259ffd365a33e780ba81409624fcc4e_Traceguids
0x140012d07  mov     rcx, [rcx+10h]
0x140012d0b  call    WPP_SF_S
0x140012d10  lea     r8, ?c_providerRegistrationPaths@ProviderManagement@DAS@@3PAU_PROVIDER_REGISTRATION_PATH@12@A; DAS::ProviderManagement::_PROVIDER_REGISTRATION_PATH near * DAS::ProviderManagement::c_providerRegistrationPaths
0x140012d17  inc     r15d
0x140012d1a  jmp     short loc_140012CC6
0x140012d1c  mov     r14d, esi
0x140012d1f  mov     r12d, esi
0x140012d22  test    r14d, r14d
0x140012d25  jnz     short loc_140012D10
0x140012d27  mov     [rsp+378h+cchName], 0FFh
0x140012d2f  xor     edx, edx; Val
0x140012d31  mov     r8d, 1FEh; Size
0x140012d37  lea     rcx, [rsp+378h+Name]; void *
0x140012d3f  call    memset_0
0x140012d44  mov     [rsp+378h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x140012d49  mov     [rsp+378h+lpcchClass], rsi; lpcchClass
0x140012d4e  mov     [rsp+378h+lpClass], rsi; lpClass
0x140012d53  mov     [rsp+378h+lpReserved], rsi; lpReserved
0x140012d58  lea     r9, [rsp+378h+cchName]; lpcchName
0x140012d5d  lea     r8, [rsp+378h+Name]; lpName
0x140012d65  mov     edx, r12d; dwIndex
0x140012d68  mov     rcx, [rsp+rbx*8+378h+hKey]; hKey
0x140012d6d  call    cs:__imp_RegEnumKeyExW
0x140012d73  mov     r14d, eax
0x140012d76  cmp     eax, 103h
0x140012d7b  jz      short loc_140012D10
0x140012d7d  test    eax, eax
0x140012d7f  jz      short loc_140012DFD
0x140012d81  jg      short loc_140012D87
0x140012d83  mov     edi, eax
0x140012d85  jmp     short loc_140012D90
0x140012d87  movzx   edi, ax
0x140012d8a  or      edi, 80070000h
0x140012d90  test    edi, edi
0x140012d92  jns     short loc_140012DFD
0x140012d94  lea     rax, [rbx+rbx*2]
0x140012d98  mov     rcx, [rsp+378h]; this
0x140012da0  lea     rdx, ?c_providerRegistrationPaths@ProviderManagement@DAS@@3PAU_PROVIDER_REGISTRATION_PATH@12@A; DAS::ProviderManagement::_PROVIDER_REGISTRATION_PATH near * DAS::ProviderManagement::c_providerRegistrationPaths
0x140012da7  mov     rax, [rdx+rax*8+8]
0x140012dac  mov     [rsp+378h+lpClass], rax; char *
0x140012db1  lea     rax, aFailedToReadSu; "failed to read subkeys in %ws"
0x140012db8  mov     [rsp+378h+lpReserved], rax; int
0x140012dbd  mov     r9d, edi; char *
0x140012dc0  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\association\\li"...
0x140012dc7  mov     edx, 36Ah; void *
0x140012dcc  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x140012dd1  nop
0x140012dd2  lea     rcx, [rsp+378h+var_330]
0x140012dd7  call    ??1?$vector@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@_NW4_DAF_PROVIDER_PATH@@@std@@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@_NW4_DAF_PROVIDER_PATH@@@std@@@2@@std@@QEAA@XZ; std::vector<std::tuple<std::wstring,HKEY__ *,bool,_DAF_PROVIDER_PATH>>::~vector<std::tuple<std::wstring,HKEY__ *,bool,_DAF_PROVIDER_PATH>>(void)
0x140012ddc  nop
0x140012ddd  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x140012de4  mov     r8, r13; unsigned __int64
0x140012de7  mov     edx, 8; unsigned __int64
0x140012dec  lea     rcx, [rsp+378h+hKey]; void *
0x140012df1  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x140012df6  mov     eax, edi
0x140012df8  jmp     loc_1400136F8
0x140012dfd  lea     rax, [rbx+rbx*2]
0x140012e01  mov     dword ptr [rsp+378h+var_2A0], r15d
0x140012e09  lea     rcx, ?c_providerRegistrationPaths@ProviderManagement@DAS@@3PAU_PROVIDER_REGISTRATION_PATH@12@A; DAS::ProviderManagement::_PROVIDER_REGISTRATION_PATH near * DAS::ProviderManagement::c_providerRegistrationPaths
0x140012e10  mov     al, [rcx+rax*8+10h]
0x140012e14  mov     byte ptr [rsp+378h+var_2A0+4], al
0x140012e1b  mov     rax, [rsp+rbx*8+378h+hKey]
0x140012e20  mov     [rsp+378h+var_2A0+8], rax
0x140012e28  lea     rdx, [rsp+378h+Name]
0x140012e30  lea     rcx, [rsp+378h+S2]
0x140012e38  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140012e3d  nop
0x140012e3e  mov     rdx, qword ptr [rsp+378h+var_330+8]
0x140012e43  cmp     rdx, [rsp+378h+var_320]
0x140012e48  jz      loc_140012ED9
0x140012e4e  mov     eax, dword ptr [rsp+378h+var_2A0]
0x140012e55  mov     [rdx], eax
0x140012e57  mov     al, byte ptr [rsp+378h+var_2A0+4]
0x140012e5e  mov     [rdx+4], al
0x140012e61  mov     rax, [rsp+378h+var_2A0+8]
0x140012e69  mov     [rdx+8], rax
0x140012e6d  movzx   eax, word ptr [rsp+378h+S2]
0x140012e75  mov     [rdx+10h], ax
0x140012e79  movsd   xmm0, [rsp+378h+S2+2]
0x140012e82  movsd   qword ptr [rdx+12h], xmm0
0x140012e87  mov     eax, dword ptr [rsp+378h+S2+0Ah]
0x140012e8e  mov     [rdx+1Ah], eax
0x140012e91  movzx   eax, word ptr [rsp+378h+S2+0Eh]
0x140012e99  mov     [rdx+1Eh], ax
0x140012e9d  mov     rax, [rsp+378h+var_280]
0x140012ea5  mov     [rdx+20h], rax
0x140012ea9  mov     rax, [rsp+378h+var_278]
0x140012eb1  mov     [rdx+28h], rax
0x140012eb5  mov     [rsp+378h+var_280], rsi
0x140012ebd  mov     [rsp+378h+var_278], 7
0x140012ec9  mov     word ptr [rsp+378h+S2], si
0x140012ed1  add     qword ptr [rsp+378h+var_330+8], 30h ; '0'
0x140012ed7  jmp     short loc_140012EEC
0x140012ed9  lea     r8, [rsp+378h+var_2A0]
0x140012ee1  lea     rcx, [rsp+378h+var_330]
0x140012ee6  call    ??$_Emplace_reallocate@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@_NW4_DAF_PROVIDER_PATH@@@std@@@?$vector@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@_NW4_DAF_PROVIDER_PATH@@@std@@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@_NW4_DAF_PROVIDER_PATH@@@std@@@2@@std@@AEAAPEAV?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@_NW4_DAF_PROVIDER_PATH@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::tuple<std::wstring,HKEY__ *,bool,_DAF_PROVIDER_PATH>>::_Emplace_reallocate<std::tuple<std::wstring,HKEY__ *,bool,_DAF_PROVIDER_PATH>>(std::tuple<std::wstring,HKEY__ *,bool,_DAF_PROVIDER_PATH> * const,std::tuple<std::wstring,HKEY__ *,bool,_DAF_PROVIDER_PATH> &&)
0x140012eeb  nop
0x140012eec  lea     rcx, [rsp+378h+S2]
0x140012ef4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140012ef9  inc     r12d
0x140012efc  jmp     loc_140012D22
0x140012f01  mov     rdi, qword ptr [rsp+378h+var_318]
0x140012f06  lea     r13, [rdi+18h]
0x140012f0a  mov     rcx, r13; SRWLock
0x140012f0d  call    cs:__imp_AcquireSRWLockExclusive
0x140012f13  mov     [rsp+378h+SRWLock], r13
0x140012f1b  lea     r12, [rdi+20h]
0x140012f1f  mov     qword ptr [rsp+378h+cchName], r12
0x140012f24  mov     rbx, [r12]
0x140012f28  mov     rbx, [rbx]
0x140012f2b  cmp     [rbx+19h], sil
0x140012f2f  jnz     loc_14001313B
0x140012f35  lea     rdx, [rbx+20h]
0x140012f39  lea     rcx, [rsp+378h+S1]
0x140012f41  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140012f46  mov     rax, [rbx+48h]
0x140012f4a  test    rax, rax
0x140012f4d  jz      short loc_140012F53
0x140012f4f  lock inc dword ptr [rax+8]
0x140012f53  mov     rax, [rbx+40h]
0x140012f57  mov     [rsp+378h+var_250], rax
0x140012f5f  mov     rdi, [rbx+48h]
0x140012f63  mov     [rsp+378h+var_248], rdi
0x140012f6b  mov     r14, qword ptr [rsp+378h+var_330]
0x140012f70  mov     r15, qword ptr [rsp+378h+var_330+8]
0x140012f75  cmp     r14, r15
0x140012f78  jz      loc_1400130D4
0x140012f7e  mov     eax, [r14]
0x140012f81  mov     dword ptr [rsp+378h+var_2A0], eax
0x140012f88  mov     al, [r14+4]
0x140012f8c  mov     byte ptr [rsp+378h+var_2A0+4], al
0x140012f93  mov     rax, [r14+8]
0x140012f97  mov     [rsp+378h+var_2A0+8], rax
0x140012f9f  lea     rdx, [r14+10h]
0x140012fa3  lea     rcx, [rsp+378h+S2]
0x140012fab  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140012fb0  lea     rdx, [rsp+378h+S2]
0x140012fb8  cmp     [rsp+378h+var_278], 7
0x140012fc1  cmova   rdx, [rsp+378h+S2]; S2
0x140012fca  mov     r8, [rsp+378h+N]; N
0x140012fd2  lea     rcx, [rsp+378h+S1]
0x140012fda  cmp     [rsp+378h+var_258], 7
0x140012fe3  cmova   rcx, [rsp+378h+S1]; S1
0x140012fec  cmp     r8, [rsp+378h+var_280]
0x140012ff4  jnz     loc_1400130BE
0x140012ffa  test    r8, r8
0x140012ffd  jz      short loc_140013014
0x140012fff  call    wmemcmp
0x140013004  mov     rdi, [rsp+378h+var_248]
0x14001300c  test    eax, eax
0x14001300e  jnz     loc_1400130BE
0x140013014  lea     rcx, [rsp+378h+S2]
0x14001301c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140013021  nop
0x140013022  test    rdi, rdi
0x140013025  jz      short loc_140013062
0x140013027  or      r14d, 0FFFFFFFFh
0x14001302b  mov     eax, r14d
0x14001302e  lock xadd [rdi+8], eax
0x140013033  add     eax, r14d
0x140013036  jnz     short loc_140013062
0x140013038  mov     rax, [rdi]
0x14001303b  mov     rcx, rdi
0x14001303e  mov     rax, [rax]
0x140013041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013046  mov     eax, r14d
0x140013049  lock xadd [rdi+0Ch], eax
0x14001304e  add     eax, r14d
0x140013051  jnz     short loc_140013062
0x140013053  mov     rax, [rdi]
0x140013056  mov     rcx, rdi
0x140013059  mov     rax, [rax+8]
0x14001305d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013062  lea     rcx, [rsp+378h+S1]
0x14001306a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001306f  mov     rcx, [rbx+10h]
0x140013073  cmp     [rcx+19h], sil
0x140013077  jz      short loc_14001309A
0x140013079  mov     rax, [rbx+8]
0x14001307d  jmp     short loc_14001308C
0x14001307f  cmp     rbx, [rax+10h]
0x140013083  jnz     short loc_140013092
0x140013085  mov     rbx, rax
0x140013088  mov     rax, [rax+8]
0x14001308c  cmp     [rax+19h], sil
0x140013090  jz      short loc_14001307F
0x140013092  mov     rbx, rax
0x140013095  jmp     loc_140012F2B
0x14001309a  mov     rbx, rcx
0x14001309d  mov     rcx, [rcx]
0x1400130a0  cmp     [rcx+19h], sil
0x1400130a4  jnz     loc_140012F2B
0x1400130aa  mov     rbx, rcx
0x1400130ad  mov     rax, [rcx]
0x1400130b0  mov     rcx, rax
0x1400130b3  cmp     [rax+19h], sil
0x1400130b7  jz      short loc_1400130AA
0x1400130b9  jmp     loc_140012F2B
0x1400130be  lea     rcx, [rsp+378h+S2]
0x1400130c6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400130cb  add     r14, 30h ; '0'
0x1400130cf  jmp     loc_140012F75
0x1400130d4  lea     rdx, [rsp+378h+S1]
0x1400130dc  mov     rcx, r12
0x1400130df  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VProviderContext@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VProviderContext@@@2@@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ProviderContext>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ProviderContext>>>,0>>::erase(std::wstring const &)
0x1400130e4  nop
0x1400130e5  mov     rbx, [rsp+378h+var_248]
0x1400130ed  test    rbx, rbx
0x1400130f0  jz      short loc_14001312D
0x1400130f2  or      r14d, 0FFFFFFFFh
0x1400130f6  mov     eax, r14d
0x1400130f9  lock xadd [rbx+8], eax
0x1400130fe  add     eax, r14d
0x140013101  jnz     short loc_14001312D
0x140013103  mov     rax, [rbx]
0x140013106  mov     rcx, rbx
0x140013109  mov     rax, [rax]
0x14001310c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013111  mov     eax, r14d
0x140013114  lock xadd [rbx+0Ch], eax
0x140013119  add     eax, r14d
0x14001311c  jnz     short loc_14001312D
0x14001311e  mov     rax, [rbx]
0x140013121  mov     rcx, rbx
0x140013124  mov     rax, [rax+8]
0x140013128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001312d  lea     rcx, [rsp+378h+S1]
0x140013135  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001313a  nop
0x14001313b  mov     [rsp+378h+SRWLock], r13
0x140013143  test    r13, r13
0x140013146  jz      short loc_140013151
0x140013148  mov     rcx, r13; SRWLock
0x14001314b  call    cs:__imp_ReleaseSRWLockExclusive
0x140013151  mov     rbx, qword ptr [rsp+378h+var_330]
0x140013156  mov     rdi, qword ptr [rsp+378h+var_330+8]
0x14001315b  cmp     rbx, rdi
0x14001315e  jnz     loc_14001353F
  ... truncated ...
```
