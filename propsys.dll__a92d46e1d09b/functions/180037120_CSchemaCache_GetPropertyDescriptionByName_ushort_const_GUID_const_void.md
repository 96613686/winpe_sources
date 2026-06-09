# CSchemaCache::GetPropertyDescriptionByName(ushort const *,_GUID const &,void * *)

- ea: `0x180037120`
- end: `0x180037ac6`
- name: `?GetPropertyDescriptionByName@CSchemaCache@@UEAAJPEBGAEBU_GUID@@PEAPEAX@Z`
- size: `2470`
- prototype: `__int64 __fastcall(CSchemaCache *__hidden this, const unsigned __int16 *Src, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180037110`

## callees

- `0x180003898`
- `0x180017970`
- `0x18001c4fc`
- `0x18002f9e0`
- `0x1800350ac`
- `0x180035260`
- `0x1800359b8`
- `0x180035a14`
- `0x180036094`
- `0x180037120`
- `0x180037acc`
- `0x1800386a0`
- `0x18003878c`
- `0x180039230`
- `0x1800396ac`
- `0x180039a10`
- `0x180039ad8`
- `0x180039c40`
- `0x180039cd0`
- `0x180063900`
- `0x18006ed20`
- `0x18006fb74`
- `0x18008f890`
- `0x180091d78`
- `0x1800921e8`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180037202`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180037202`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800374cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800374cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037174`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037174`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpCW` at `0x180037446`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpCW` at `0x1800375c7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpCW` at `0x180037446`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpCW` at `0x1800375c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037945`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003797c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800379b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037945`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003797c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800379b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180037263`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800377d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180037263`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800377d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800372bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800372bd`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18003764e`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18003764e`

## string_xrefs

- `0x1800377a6`: `onecoreuap\shell\propsys\schemacache.cpp`
- `0x180037a43`: `onecoreuap\shell\propsys\schemacache.cpp`
- `0x180037a8d`: `onecoreuap\shell\propsys\schemacache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
int __fastcall CSchemaCache::GetPropertyDescriptionByName(
        CSchemaCache *this,
        unsigned __int16 *Src,
        const struct _GUID *a3,
        void **a4)
{
  unsigned __int16 *v4; // rdi
  unsigned __int64 v6; // r13
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rsi
  int v10; // eax
  WCHAR *v11; // r13
  __int64 v12; // r8
  wchar_t *v13; // rbx
  int StringOrdinal; // eax
  int Instance; // r15d
  int refreshed; // ebx
  unsigned int v17; // r15d
  unsigned int v18; // r9d
  __int64 (__fastcall *v19)(unsigned __int16 *, _QWORD, _QWORD); // rax
  unsigned int v20; // eax
  unsigned __int64 v21; // r8
  unsigned int v22; // eax
  __int64 *v23; // rsi
  unsigned __int64 v24; // rsi
  __int64 v25; // rax
  const WCHAR *v26; // r8
  unsigned __int64 v27; // rax
  unsigned __int64 v28; // rbx
  __int64 v29; // rcx
  unsigned int *v30; // rax
  __int64 v31; // rcx
  const WCHAR *v32; // rdx
  int v33; // eax
  struct IMemoryMappedCache *v34; // rcx
  const unsigned __int16 *v36; // rbx
  LPCWSTR v37; // r15
  __int64 v38; // rcx
  unsigned int *v39; // rax
  __int64 v40; // rcx
  const WCHAR *v41; // rdx
  __int64 v42; // rcx
  unsigned __int64 v43; // rcx
  LPCWSTR v44; // r13
  void *v45; // rbx
  DWORD TickCount; // eax
  unsigned int i; // r15d
  char *v48; // rcx
  unsigned __int8 *v49; // r13
  unsigned int j; // r15d
  char *v51; // rcx
  unsigned __int8 *v52; // r13
  unsigned int k; // r15d
  char *v54; // rcx
  unsigned __int8 *v55; // r13
  unsigned __int8 *v56; // rcx
  unsigned __int8 *v57; // rcx
  unsigned __int8 *v58; // rcx
  int v59; // eax
  int v60; // eax
  int cchValue; // [rsp+20h] [rbp-E0h]
  int cchValuea; // [rsp+20h] [rbp-E0h]
  int cchValueb; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v64; // [rsp+30h] [rbp-D0h] BYREF
  char v65; // [rsp+38h] [rbp-C8h]
  void *Srca; // [rsp+40h] [rbp-C0h]
  LPCWSTR lpStringSource; // [rsp+48h] [rbp-B8h] BYREF
  IUnknown *punk; // [rsp+50h] [rbp-B0h]
  void **v69; // [rsp+58h] [rbp-A8h]
  const struct _GUID *v70; // [rsp+60h] [rbp-A0h]
  struct IMemoryMappedCache *v71; // [rsp+68h] [rbp-98h] BYREF
  __int128 v72; // [rsp+70h] [rbp-90h] BYREF
  void **v73; // [rsp+80h] [rbp-80h] BYREF
  char v74[272]; // [rsp+88h] [rbp-78h] BYREF
  char v75[8]; // [rsp+198h] [rbp+98h] BYREF
  char v76[24]; // [rsp+1A0h] [rbp+A0h] BYREF
  int v77; // [rsp+1B8h] [rbp+B8h]
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v69 = a4;
  v70 = a3;
  v4 = Src;
  v6 = 0;
  *a4 = 0;
  if ( *Src == 123 )
    return CSchemaCache::_CreateDummyPropertyDescription(this, Src, a3, a4);
  EnterCriticalSection(&CSchemaCache::s_critsec);
  v9 = -1;
  if ( !*((_QWORD *)this + 3) )
    goto LABEL_3;
  TickCount = GetTickCount();
  if ( TickCount - *((_DWORD *)this + 50) <= 0x1388 )
    goto LABEL_22;
  *((_DWORD *)this + 50) = TickCount;
  LODWORD(v64) = 0;
  refreshed = CCachedData<GLOBAL_MAPPING_HEADER,CGlobalMappingData>::RefreshIfNeeded(*((_QWORD *)this + 3), &v64);
  if ( refreshed < 0 )
  {
    SafeRelease<IShellFolder2>((char *)this + 24);
  }
  else if ( !(_DWORD)v64 )
  {
    goto LABEL_21;
  }
  *(_QWORD *)&v72 = CSchemaCache::s_ReleaseCB<IPropertyDescription>;
  *((_QWORD *)&v72 + 1) = 0;
  for ( i = 0; i < *((_DWORD *)this + 21); ++i )
  {
    v48 = (char *)(8LL * i);
    Srca = v48;
    v49 = *(unsigned __int8 **)&v48[*((_QWORD *)this + 11)];
    if ( v49 )
    {
      do
      {
        CHashTable<CSchemaData,_GUID>::s_DestroyCallback(
          &v49[*((unsigned int *)this + 25)],
          *((_DWORD *)this + 24),
          &v72);
        v56 = v49;
        v49 = *(unsigned __int8 **)v49;
        LocalFree(v56);
      }
      while ( v49 );
      v48 = (char *)Srca;
    }
    v6 = 0;
    *(_QWORD *)&v48[*((_QWORD *)this + 11)] = 0;
  }
  *((_DWORD *)this + 20) = 0;
  *(_QWORD *)&v72 = CSchemaCache::s_ReleaseCB<IPropertyDescription>;
  *((_QWORD *)&v72 + 1) = 0;
  for ( j = 0; j < *((_DWORD *)this + 31); ++j )
  {
    v51 = (char *)(8LL * j);
    Srca = v51;
    v52 = *(unsigned __int8 **)&v51[*((_QWORD *)this + 16)];
    if ( v52 )
    {
      do
      {
        CHashTable<CSchemaData,_GUID>::s_DestroyCallback(
          &v52[*((unsigned int *)this + 35)],
          *((_DWORD *)this + 34),
          &v72);
        v57 = v52;
        v52 = *(unsigned __int8 **)v52;
        LocalFree(v57);
      }
      while ( v52 );
      v51 = (char *)Srca;
    }
    v6 = 0;
    *(_QWORD *)&v51[*((_QWORD *)this + 16)] = 0;
  }
  *((_DWORD *)this + 30) = 0;
  *(_QWORD *)&v72 = CSchemaCache::s_ReleaseCB<IPropertyDescription>;
  *((_QWORD *)&v72 + 1) = 0;
  for ( k = 0; k < *((_DWORD *)this + 41); ++k )
  {
    v54 = (char *)(8LL * k);
    Srca = v54;
    v55 = *(unsigned __int8 **)&v54[*((_QWORD *)this + 21)];
    if ( v55 )
    {
      do
      {
        CHashTable<CSchemaData,_GUID>::s_DestroyCallback(
          &v55[*((unsigned int *)this + 45)],
          *((_DWORD *)this + 44),
          &v72);
        v58 = v55;
        v55 = *(unsigned __int8 **)v55;
        LocalFree(v58);
      }
      while ( v55 );
      v54 = (char *)Srca;
    }
    v6 = 0;
    *(_QWORD *)&v54[*((_QWORD *)this + 21)] = 0;
  }
  *((_DWORD *)this + 40) = 0;
  SafeRelease<IShellFolder2>((char *)this + 192);
  if ( (_DWORD)v64 )
    CSchemaCache::_RefreshCachedSchemas(this);
LABEL_21:
  if ( refreshed >= 0 )
    goto LABEL_22;
LABEL_3:
  lpStringSource = 0;
  v10 = wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,128>(
          v8,
          v7,
          &lpStringSource);
  if ( v10 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x224,
      (unsigned int)"onecoreuap\\shell\\propsys\\schemacache.cpp",
      (const char *)(unsigned int)v10,
      cchValue);
  v65 = 0;
  v11 = (WCHAR *)lpStringSource;
  if ( lpStringSource )
  {
    v12 = -1;
    do
      ++v12;
    while ( lpStringSource[v12] );
    v13 = (wchar_t *)&lpStringSource[v12];
    if ( v12 && *(v13 - 1) == 92 )
      LODWORD(v12) = v12 - 1;
    StringOrdinal = FindStringOrdinal(0x800000u, lpStringSource, v12, L"\\", 1, 1);
    if ( StringOrdinal != -1 )
      v13 = &v11[StringOrdinal + 1];
  }
  else
  {
    v13 = L"Unknown";
  }
  Srca = v13;
  PropsysTelemetry::SchemaCacheGlobalMappingLoad::Start<unsigned short const *,bool>((PropsysTelemetry::SchemaCacheGlobalMappingLoad *)&v73);
  v72 = CACHEID_GlobalMapping;
  Instance = CCachedData<GLOBAL_MAPPING_HEADER,CGlobalMappingData>::CreateInstance(
               *((IUnknown **)this + 2),
               (IUnknown **)this + 3);
  if ( Instance < 0 )
  {
    v71 = 0;
    v59 = CSchemaCache::_BuildGlobalMapping((IUnknown **)this, 0, &v71);
    Instance = v59;
    if ( v59 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x22C,
        (unsigned int)"onecoreuap\\shell\\propsys\\schemacache.cpp",
        (const char *)(unsigned int)v59,
        cchValuea);
      goto LABEL_13;
    }
    LODWORD(v64) = v59 == 0;
    PropsysTelemetry::SchemaCacheGlobalMappingLoad::RebuiltGlobalMapping<int &>(&v73, &v64);
    v72 = CACHEID_GlobalMapping;
    v60 = CCachedData<GLOBAL_MAPPING_HEADER,CGlobalMappingData>::CreateInstance(
            *((IUnknown **)this + 2),
            (IUnknown **)this + 3);
    Instance = v60;
    if ( v60 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x234,
        (unsigned int)"onecoreuap\\shell\\propsys\\schemacache.cpp",
        (const char *)(unsigned int)v60,
        cchValueb);
    (*(void (__fastcall **)(struct IMemoryMappedCache *))(*(_QWORD *)v71 + 16LL))(v71);
    if ( Instance < 0 )
      goto LABEL_13;
  }
  *((_DWORD *)this + 50) = GetTickCount();
LABEL_13:
  wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v73, (unsigned int)Instance);
  v73 = &PropsysTelemetry::SchemaCacheGlobalMappingLoad::`vftable';
  wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v73);
  if ( v77 )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v76);
  wil::details::shared_object<wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PropsysTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(v75);
  wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PropsysTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<PropsysTelemetry,_TlgReflectorTag_Param0IsProviderType>(v74);
  if ( v11 )
    CoTaskMemFree(v11);
  if ( Instance < 0 )
    goto LABEL_49;
  v6 = 0;
  do
LABEL_22:
    ++v9;
  while ( v4[v9] );
  v71 = 0;
  if ( *((_QWORD *)this + 11) )
  {
    v17 = 2 * v9 + 2;
    v18 = *((_DWORD *)this + 21);
    v19 = (__int64 (__fastcall *)(unsigned __int16 *, _QWORD, _QWORD))*((_QWORD *)this + 9);
    if ( v19 )
    {
      v22 = v19(v4, v17, v18);
    }
    else
    {
      v20 = 314159269;
      v21 = 0;
      if ( 2 * (_DWORD)v9 != -2 )
      {
        do
          v20 ^= (v20 >> 2) + 2080 * v20 + *((unsigned __int8 *)v4 + v21++);
        while ( v21 < v17 );
      }
      v22 = (v20 & 0x7FFFFFFF) % v18;
    }
    v23 = *(__int64 **)(*((_QWORD *)this + 11) + 8LL * v22);
    if ( v23 )
    {
      while ( v17 != *((_DWORD *)v23 + 2) || memcmp_0(v4, (char *)v23 + *((unsigned int *)this + 26), v17) )
      {
        v23 = (__int64 *)*v23;
        if ( !v23 )
          goto LABEL_32;
      }
      if ( *((_DWORD *)this + 24) == 8 )
      {
        v71 = *(struct IMemoryMappedCache **)((char *)v23 + *((unsigned int *)this + 25));
        (*(void (__fastcall **)(struct IMemoryMappedCache *))(*(_QWORD *)v71 + 8LL))(v71);
LABEL_46:
        Instance = (**(__int64 (__fastcall ***)(struct IMemoryMappedCache *, const struct _GUID *, void **))v71)(
                     v71,
                     v70,
                     v69);
        goto LABEL_47;
      }
    }
  }
LABEL_32:
  v64 = 0;
  Instance = CSchemaCache::_GetSchemaForEntity<unsigned short const *,&public: long CGlobalMappingData::GetSchemaIdForPropertyByName(unsigned short const *,_GUID *)>(this);
  if ( Instance >= 0 )
  {
    Srca = 0;
LABEL_34:
    v24 = v64;
    v25 = *(_QWORD *)(v64 + 72);
    if ( !v25 )
    {
      Instance = -2147319765;
LABEL_58:
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v24 + 16LL))(v24);
      if ( Instance < 0 )
        goto LABEL_47;
      goto LABEL_46;
    }
    v26 = *(const WCHAR **)(v64 + 16);
    lpStringSource = v26;
    v27 = v25 - 1;
    v64 = v27;
    Instance = 0;
    while ( 1 )
    {
      if ( Instance < 0 )
        goto LABEL_58;
      v28 = (v27 + v6) >> 1;
      v29 = *(unsigned int *)(*(_QWORD *)(v24 + 64) + 4 * v28);
      if ( (_DWORD)v29 == -1 )
        v30 = 0;
      else
        v30 = (unsigned int *)((char *)v26 + v29);
      v31 = *v30;
      if ( (_DWORD)v31 == -1 )
        v32 = 0;
      else
        v32 = (const WCHAR *)((char *)v26 + v31);
      v33 = -StrCmpCW(v4, v32);
      if ( v33 <= 0 )
      {
        if ( v33 >= 0 )
        {
          if ( v28 )
          {
            v37 = lpStringSource;
            do
            {
              v38 = *(unsigned int *)(*(_QWORD *)(v24 + 64) + 4 * v28 - 4);
              if ( (_DWORD)v38 == -1 )
                v39 = 0;
              else
                v39 = (unsigned int *)((char *)v37 + v38);
              v40 = *v39;
              if ( (_DWORD)v40 == -1 )
                v41 = 0;
              else
                v41 = (LPCWSTR)((char *)v37 + v40);
              if ( StrCmpCW(v4, v41) )
                break;
              --v28;
            }
            while ( v28 );
          }
          v42 = *(unsigned int *)(*(_QWORD *)(v24 + 64) + 4 * v28);
          if ( (_DWORD)v42 == -1 )
            v43 = 0;
          else
            v43 = *(_QWORD *)(v24 + 16) + v42;
          v64 = v43;
          punk = *(IUnknown **)(v24 + 56);
          LODWORD(v72) = 1;
          DWORD1(v72) = *(_DWORD *)(v43 + 112);
          DWORD2(v72) = *(_DWORD *)(v43 + 104);
          v71 = 0;
          Instance = -2147024809;
          if ( punk )
          {
            lpStringSource = 0;
            Instance = CTRefBase<CPropertyDescription,IPropertyDescription,CTRefBase_DllModuleLifetimePolicy>::Create(&lpStringSource);
            if ( Instance >= 0 )
            {
              v44 = lpStringSource;
              IUnknown_Set((IUnknown **)lpStringSource + 3, punk);
              *((_QWORD *)v44 + 5) = v64;
              Instance = (*(__int64 (__fastcall **)(_QWORD, LPCWSTR))(**((_QWORD **)v44 + 3) + 32LL))(
                           *((_QWORD *)v44 + 3),
                           v44 + 16);
              if ( Instance >= 0 )
              {
                Instance = (*(__int64 (__fastcall **)(LPCWSTR, __int128 *))(*(_QWORD *)v44 + 208LL))(v44, &v72);
                if ( Instance >= 0 )
                  Instance = (**(__int64 (__fastcall ***)(LPCWSTR, GUID *, struct IMemoryMappedCache **))v44)(
                               v44,
                               &GUID_6f79d558_3e96_4549_a1d1_7d75d2288814,
                               &v71);
              }
              (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)v44 + 16LL))(v44);
            }
          }
          if ( Instance >= 0 )
          {
            if ( (int)CHashTable<IPropertyDescription,unsigned short>::ContainsKey((char *)this + 72, v4) < 0
              && (int)CHashTable<CACHED_SCHEMA_REGISTRATION const,unsigned short>::AddPtr(
                        (CSchemaCache *)((char *)this + 72),
                        v4) >= 0 )
            {
              (*(void (__fastcall **)(struct IMemoryMappedCache *))(*(_QWORD *)v71 + 8LL))(v71);
            }
            v45 = Srca;
            if ( Srca
              && (int)CHashTable<IPropertyDescription,unsigned short>::ContainsKey((char *)this + 72, Srca) < 0
              && (int)CHashTable<CACHED_SCHEMA_REGISTRATION const,unsigned short>::AddPtr(
                        (CSchemaCache *)((char *)this + 72),
                        v45) >= 0 )
            {
              (*(void (__fastcall **)(struct IMemoryMappedCache *))(*(_QWORD *)v71 + 8LL))(v71);
            }
          }
          goto LABEL_58;
        }
        v6 = v28 + 1;
      }
      else
      {
        if ( v28 )
        {
          v27 = v28 - 1;
          v64 = v28 - 1;
          goto LABEL_55;
        }
        Instance = -2147319765;
      }
      v27 = v64;
LABEL_55:
      v26 = lpStringSource;
      if ( v27 < v6 )
        Instance = -2147319765;
    }
  }
  v36 = CSchemaCache::_AliasToName(v4);
  if ( v36 )
  {
    Instance = CSchemaCache::_GetSchemaForEntity<unsigned short const *,&public: long CGlobalMappingData::GetSchemaIdForPropertyByName(unsigned short const *,_GUID *)>(this);
    if ( Instance >= 0 )
    {
      Srca = v4;
      v4 = (unsigned __int16 *)v36;
      goto LABEL_34;
    }
  }
LABEL_47:
  v34 = v71;
  v71 = 0;
  if ( v34 )
    (*(void (__fastcall **)(struct IMemoryMappedCache *))(*(_QWORD *)v34 + 16LL))(v34);
LABEL_49:
  LeaveCriticalSection(&CSchemaCache::s_critsec);
  if ( *((_BYTE *)this + 204) )
  {
    *((_BYTE *)this + 204) = 0;
    _ChangeNotifyHandlers();
  }
  return Instance;
}

```

## disassembly

```asm
0x180037120  push    rbp
0x180037122  push    rbx
0x180037123  push    rsi
0x180037124  push    rdi
0x180037125  push    r12
0x180037127  push    r13
0x180037129  push    r14
0x18003712b  push    r15
0x18003712d  lea     rbp, [rsp-0E8h]
0x180037135  sub     rsp, 1E8h
0x18003713c  mov     rax, cs:__security_cookie
0x180037143  xor     rax, rsp
0x180037146  mov     [rbp+120h+var_50], rax
0x18003714d  mov     [rsp+220h+var_1C8], r9
0x180037152  mov     [rsp+220h+var_1C0], r8
0x180037157  mov     rdi, rdx
0x18003715a  mov     r14, rcx
0x18003715d  xor     r13d, r13d
0x180037160  mov     [r9], r13
0x180037163  cmp     word ptr [rdx], 7Bh ; '{'
0x180037167  jz      loc_180037A73
0x18003716d  lea     rcx, ?s_critsec@CSchemaCache@@0VCCritSec@@A; lpCriticalSection
0x180037174  call    cs:__imp_EnterCriticalSection
0x18003717a  lea     r12, [r14+18h]
0x18003717e  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180037185  cmp     [r12], r13
0x180037189  jnz     loc_1800377D5
0x18003718f  mov     [rsp+220h+lpStringSource], r13
0x180037194  lea     r8, [rsp+220h+lpStringSource]
0x180037199  call    ??$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJPEAXPEAUHINSTANCE__@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18003719e  mov     rcx, [rbp+128h]; this
0x1800371a5  test    eax, eax
0x1800371a7  js      loc_1800377A3
0x1800371ad  mov     [rsp+220h+var_1E8], 0
0x1800371b2  mov     r13, [rsp+220h+lpStringSource]
0x1800371b7  test    r13, r13
0x1800371ba  jz      loc_180037763
0x1800371c0  mov     r8, rsi
0x1800371c3  inc     r8; cchSource
0x1800371c6  cmp     word ptr [r13+r8*2+0], 0
0x1800371cd  jnz     short loc_1800371C3
0x1800371cf  lea     rbx, ds:0[r8*2]
0x1800371d7  add     rbx, r13
0x1800371da  test    r8, r8
0x1800371dd  jnz     loc_18003776F
0x1800371e3  mov     [rsp+220h+bIgnoreCase], 1; bIgnoreCase
0x1800371eb  mov     [rsp+220h+cchValue], 1; cchValue
0x1800371f3  lea     r9, asc_1800D17E4; "\\"
0x1800371fa  mov     rdx, r13; lpStringSource
0x1800371fd  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x180037202  call    cs:__imp_FindStringOrdinal
0x180037208  cmp     eax, 0FFFFFFFFh
0x18003720b  jz      short loc_180037217
0x18003720d  cdqe
0x18003720f  lea     rbx, [r13+2]
0x180037213  lea     rbx, [rbx+rax*2]
0x180037217  mov     [rsp+220h+Src], rbx
0x18003721c  lea     r8, [rsp+220h+var_1E8]
0x180037221  lea     rdx, [rsp+220h+Src]
0x180037226  lea     rcx, [rbp+120h+var_1A0]; this
0x18003722a  call    ??$Start@PEBG_N@SchemaCacheGlobalMappingLoad@PropsysTelemetry@@SA?AV01@$$QEAPEBG$$QEA_N@Z; PropsysTelemetry::SchemaCacheGlobalMappingLoad::Start<ushort const *,bool>(ushort const * &&,bool &&)
0x18003722f  nop
0x180037230  movups  xmm0, cs:CACHEID_GlobalMapping
0x180037237  movaps  [rsp+220h+var_1B0], xmm0
0x18003723c  mov     qword ptr [rsp+220h+cchValue], r12; int
0x180037241  mov     r9d, 1
0x180037247  xor     r8d, r8d
0x18003724a  lea     rdx, [rsp+220h+var_1B0]
0x18003724f  mov     rcx, [r14+10h]; punk
0x180037253  call    ?CreateInstance@?$CCachedData@UGLOBAL_MAPPING_HEADER@@VCGlobalMappingData@@@@SAJPEAUIMemoryMappedCacheMgr@@U_GUID@@PEAUIMemoryMappedCache@@HPEAPEAVCGlobalMappingData@@@Z; CCachedData<GLOBAL_MAPPING_HEADER,CGlobalMappingData>::CreateInstance(IMemoryMappedCacheMgr *,_GUID,IMemoryMappedCache *,int,CGlobalMappingData * *)
0x180037258  mov     r15d, eax
0x18003725b  test    eax, eax
0x18003725d  js      loc_1800379C8
0x180037263  call    cs:__imp_GetTickCount
0x180037269  mov     [r14+0C8h], eax
0x180037270  mov     edx, r15d
0x180037273  lea     rcx, [rbp+120h+var_1A0]
0x180037277  call    ?Stop@?$ActivityBase@VPropsysTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18003727c  nop
0x18003727d  lea     rax, ??_7SchemaCacheGlobalMappingLoad@PropsysTelemetry@@6B@; const PropsysTelemetry::SchemaCacheGlobalMappingLoad::`vftable'
0x180037284  mov     [rbp+120h+var_1A0], rax
0x180037288  lea     rcx, [rbp+120h+var_1A0]
0x18003728c  call    ?Destroy@?$ActivityBase@VPropsysTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180037291  nop
0x180037292  cmp     [rbp+120h+var_68], 0
0x180037299  jnz     loc_180037AA3
0x18003729f  lea     rcx, [rbp+120h+var_88]
0x1800372a6  call    ?reset@?$shared_object@V?$ActivityData@VPropsysTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPropsysTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PropsysTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x1800372ab  lea     rcx, [rbp+120h+var_198]
0x1800372af  call    ??1?$ActivityData@VPropsysTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPropsysTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PropsysTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<PropsysTelemetry,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800372b4  nop
0x1800372b5  test    r13, r13
0x1800372b8  jz      short loc_1800372C3
0x1800372ba  mov     rcx, r13; pv
0x1800372bd  call    cs:__imp_CoTaskMemFree
0x1800372c3  test    r15d, r15d
0x1800372c6  js      loc_1800374C6
0x1800372cc  xor     r13d, r13d
0x1800372cf  jmp     short loc_180037310
0x1800372d1  mov     [r14+0C8h], eax
0x1800372d8  mov     dword ptr [rsp+220h+var_1F0], r13d
0x1800372dd  lea     rdx, [rsp+220h+var_1F0]
0x1800372e2  mov     rcx, [r12]
0x1800372e6  call    ?RefreshIfNeeded@?$CCachedData@UGLOBAL_MAPPING_HEADER@@VCGlobalMappingData@@@@QEAAJPEAH@Z; CCachedData<GLOBAL_MAPPING_HEADER,CGlobalMappingData>::RefreshIfNeeded(int *)
0x1800372eb  mov     ebx, eax
0x1800372ed  test    eax, eax
0x1800372ef  js      loc_180037A7D
0x1800372f5  cmp     dword ptr [rsp+220h+var_1F0], r13d
0x1800372fa  jnz     loc_1800377F5
0x180037300  test    ebx, ebx
0x180037302  js      loc_18003718F
0x180037308  nop     dword ptr [rax+rax+00000000h]
0x180037310  lea     rsi, [rsi+1]
0x180037314  cmp     word ptr [rdi+rsi*2], 0
0x180037319  jnz     short loc_180037310
0x18003731b  xor     eax, eax
0x18003731d  mov     [rsp+220h+var_1B8], rax
0x180037322  cmp     [r14+58h], rax
0x180037326  jz      loc_1800373C0
0x18003732c  lea     r15d, ds:2[rsi*2]
0x180037334  mov     r9d, [r14+54h]
0x180037338  mov     rax, [r14+48h]
0x18003733c  mov     ebx, r15d
0x18003733f  test    rax, rax
0x180037342  jnz     loc_180037782
0x180037348  mov     eax, 12B9B0A5h
0x18003734d  mov     r8, r13
0x180037350  test    r15d, r15d
0x180037353  jz      short loc_18003737E
0x180037355  nop     word ptr [rax+rax+00000000h]
0x180037360  movzx   edx, byte ptr [r8+rdi]
0x180037365  imul    ecx, eax, 820h
0x18003736b  add     edx, ecx
0x18003736d  mov     ecx, eax
0x18003736f  shr     ecx, 2
0x180037372  add     edx, ecx
0x180037374  xor     eax, edx
0x180037376  inc     r8
0x180037379  cmp     r8, rbx
0x18003737c  jb      short loc_180037360
0x18003737e  btr     eax, 1Fh
0x180037382  xor     edx, edx
0x180037384  div     r9d
0x180037387  mov     eax, edx
0x180037389  mov     ecx, eax
0x18003738b  mov     rax, [r14+58h]
0x18003738f  mov     rsi, [rax+rcx*8]
0x180037393  test    rsi, rsi
0x180037396  jz      short loc_1800373C0
0x180037398  cmp     r15d, [rsi+8]
0x18003739c  jnz     short loc_1800373B8
0x18003739e  mov     edx, [r14+68h]
0x1800373a2  add     rdx, rsi; Buf2
0x1800373a5  mov     r8, rbx; Size
0x1800373a8  mov     rcx, rdi; Buf1
0x1800373ab  call    memcmp_0
0x1800373b0  test    eax, eax
0x1800373b2  jz      loc_18003746A
0x1800373b8  mov     rsi, [rsi]
0x1800373bb  test    rsi, rsi
0x1800373be  jnz     short loc_180037398
0x1800373c0  mov     [rsp+220h+var_1F0], r13
0x1800373c5  lea     r8, [rsp+220h+var_1F0]
0x1800373ca  mov     rdx, rdi
0x1800373cd  mov     rcx, r14
0x1800373d0  call    ??$_GetSchemaForEntity@PEBG$1?GetSchemaIdForPropertyByName@CGlobalMappingData@@QEAAJPEBGPEAU_GUID@@@Z@CSchemaCache@@AEAAJPEBGPEAPEAVCSchemaData@@@Z; CSchemaCache::_GetSchemaForEntity<ushort const *,&CGlobalMappingData::GetSchemaIdForPropertyByName(ushort const *,_GUID *)>(ushort const *,CSchemaData * *)
0x1800373d5  mov     r15d, eax
0x1800373d8  test    eax, eax
0x1800373da  js      loc_18003755A
0x1800373e0  mov     [rsp+220h+Src], r13
0x1800373e5  mov     rsi, [rsp+220h+var_1F0]
0x1800373ea  mov     rax, [rsi+48h]
0x1800373ee  test    rax, rax
0x1800373f1  jz      loc_180037758
0x1800373f7  mov     r8, [rsi+10h]
0x1800373fb  mov     [rsp+220h+lpStringSource], r8
0x180037400  dec     rax
0x180037403  mov     [rsp+220h+var_1F0], rax
0x180037408  xor     r15d, r15d
0x18003740b  nop     dword ptr [rax+rax+00h]
0x180037410  test    r15d, r15d
0x180037413  js      loc_18003753A
0x180037419  lea     rbx, [rax+r13]
0x18003741d  shr     rbx, 1
0x180037420  mov     rax, [rsi+40h]
0x180037424  mov     ecx, [rax+rbx*4]
0x180037427  cmp     ecx, 0FFFFFFFFh
0x18003742a  jz      loc_180037795
0x180037430  lea     rax, [r8+rcx]
0x180037434  mov     ecx, [rax]
0x180037436  cmp     ecx, 0FFFFFFFFh
0x180037439  jz      loc_18003779C
0x18003743f  lea     rdx, [r8+rcx]; pszStr2
0x180037443  mov     rcx, rdi; pszStr1
0x180037446  call    cs:__imp_StrCmpCW
0x18003744c  neg     eax
0x18003744e  test    eax, eax
0x180037450  jle     loc_180037507
0x180037456  test    rbx, rbx
0x180037459  jnz     loc_18003752F
0x18003745f  mov     r15d, 8002802Bh
0x180037465  jmp     loc_180037511
0x18003746a  cmp     dword ptr [r14+60h], 8
0x18003746f  jnz     loc_1800373C0
0x180037475  mov     eax, [r14+64h]
0x180037479  mov     rcx, [rax+rsi]
0x18003747d  mov     [rsp+220h+var_1B8], rcx
0x180037482  mov     rax, [rcx]
0x180037485  mov     rax, [rax+8]
0x180037489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003748e  mov     rcx, [rsp+220h+var_1B8]
0x180037493  mov     rax, [rcx]
0x180037496  mov     r8, [rsp+220h+var_1C8]
0x18003749b  mov     rdx, [rsp+220h+var_1C0]
0x1800374a0  mov     rax, [rax]
0x1800374a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800374a8  mov     r15d, eax
0x1800374ab  mov     rcx, [rsp+220h+var_1B8]
0x1800374b0  mov     [rsp+220h+var_1B8], r13
0x1800374b5  test    rcx, rcx
0x1800374b8  jz      short loc_1800374C6
0x1800374ba  mov     rax, [rcx]
0x1800374bd  mov     rax, [rax+10h]
0x1800374c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800374c6  lea     rcx, ?s_critsec@CSchemaCache@@0VCCritSec@@A; lpCriticalSection
0x1800374cd  call    cs:__imp_LeaveCriticalSection
0x1800374d3  cmp     byte ptr [r14+0CCh], 0
0x1800374db  jnz     loc_180037AB4
0x1800374e1  mov     eax, r15d
0x1800374e4  mov     rcx, [rbp+120h+var_50]
0x1800374eb  xor     rcx, rsp; StackCookie
0x1800374ee  call    __security_check_cookie
0x1800374f3  add     rsp, 1E8h
0x1800374fa  pop     r15
0x1800374fc  pop     r14
0x1800374fe  pop     r13
0x180037500  pop     r12
0x180037502  pop     rdi
0x180037503  pop     rsi
0x180037504  pop     rbx
0x180037505  pop     rbp
0x180037506  retn
0x180037507  jns     loc_180037596
0x18003750d  lea     r13, [rbx+1]
0x180037511  mov     rax, [rsp+220h+var_1F0]
0x180037516  cmp     rax, r13
0x180037519  mov     r8, [rsp+220h+lpStringSource]
0x18003751e  jnb     loc_180037410
0x180037524  mov     r15d, 8002802Bh
0x18003752a  jmp     loc_180037410
0x18003752f  lea     rax, [rbx-1]
0x180037533  mov     [rsp+220h+var_1F0], rax
0x180037538  jmp     short loc_180037516
0x18003753a  xor     r13d, r13d
0x18003753d  mov     rax, [rsi]
0x180037540  mov     rcx, rsi
0x180037543  mov     rax, [rax+10h]
0x180037547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003754c  test    r15d, r15d
0x18003754f  jns     loc_18003748E
0x180037555  jmp     loc_1800374AB
0x18003755a  mov     rcx, rdi; pszStr1
0x18003755d  call    ?_AliasToName@CSchemaCache@@CAPEBGPEBG@Z; CSchemaCache::_AliasToName(ushort const *)
0x180037562  mov     rbx, rax
0x180037565  test    rax, rax
0x180037568  jz      loc_1800374AB
0x18003756e  lea     r8, [rsp+220h+var_1F0]
0x180037573  mov     rdx, rax
0x180037576  mov     rcx, r14
0x180037579  call    ??$_GetSchemaForEntity@PEBG$1?GetSchemaIdForPropertyByName@CGlobalMappingData@@QEAAJPEBGPEAU_GUID@@@Z@CSchemaCache@@AEAAJPEBGPEAPEAVCSchemaData@@@Z; CSchemaCache::_GetSchemaForEntity<ushort const *,&CGlobalMappingData::GetSchemaIdForPropertyByName(ushort const *,_GUID *)>(ushort const *,CSchemaData * *)
0x18003757e  mov     r15d, eax
0x180037581  test    eax, eax
0x180037583  js      loc_1800374AB
0x180037589  mov     [rsp+220h+Src], rdi
0x18003758e  mov     rdi, rbx
0x180037591  jmp     loc_1800373E5
0x180037596  test    rbx, rbx
0x180037599  jz      short loc_1800375D7
0x18003759b  mov     r15, [rsp+220h+lpStringSource]
0x1800375a0  mov     rax, [rsi+40h]
0x1800375a4  mov     ecx, [rax+rbx*4-4]
0x1800375a8  cmp     ecx, 0FFFFFFFFh
0x1800375ab  jz      loc_1800377BC
0x1800375b1  lea     rax, [r15+rcx]
0x1800375b5  mov     ecx, [rax]
0x1800375b7  cmp     ecx, 0FFFFFFFFh
0x1800375ba  jz      loc_1800377C3
0x1800375c0  lea     rdx, [r15+rcx]; pszStr2
0x1800375c4  mov     rcx, rdi; pszStr1
0x1800375c7  call    cs:__imp_StrCmpCW
0x1800375cd  test    eax, eax
0x1800375cf  jnz     short loc_1800375D7
0x1800375d1  sub     rbx, 1
0x1800375d5  jnz     short loc_1800375A0
0x1800375d7  mov     rax, [rsi+40h]
0x1800375db  mov     ecx, [rax+rbx*4]
0x1800375de  cmp     ecx, 0FFFFFFFFh
0x1800375e1  jz      loc_1800377CA
0x1800375e7  add     rcx, [rsi+10h]
0x1800375eb  xor     r13d, r13d
  ... truncated ...
```
