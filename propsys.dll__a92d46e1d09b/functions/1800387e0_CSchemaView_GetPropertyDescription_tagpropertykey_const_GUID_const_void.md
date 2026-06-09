# CSchemaView::GetPropertyDescription(_tagpropertykey const &,_GUID const &,void * *)

- ea: `0x1800387e0`
- end: `0x180038edd`
- name: `?GetPropertyDescription@CSchemaView@@UEAAJAEBU_tagpropertykey@@AEBU_GUID@@PEAPEAX@Z`
- size: `1789`
- prototype: `int(CSchemaView *__hidden this, const struct _tagpropertykey *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003898`
- `0x180017970`
- `0x18001c4fc`
- `0x18002f9e0`
- `0x1800359b8`
- `0x180035a14`
- `0x1800360fc`
- `0x1800385f0`
- `0x1800387e0`
- `0x180038ee4`
- `0x180039000`
- `0x180039230`
- `0x1800396ac`
- `0x180039a10`
- `0x180039ad8`
- `0x180039c40`
- `0x180039cd0`
- `0x18003b19c`
- `0x18006ed20`
- `0x18008f890`
- `0x180091d78`
- `0x1800921e8`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800388b0`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800388b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003896f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003896f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003882b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003882b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038cdd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038dc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038deb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038cdd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038dc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038deb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003890d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180038c54`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003890d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180038c54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800389b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800389b6`

## string_xrefs

- `0x180038854`: `onecoreuap\shell\propsys\schemacache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSchemaView::GetPropertyDescription(
        CSchemaView *this,
        struct _tagpropertykey *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // rcx
  IUnknown **v8; // rsi
  int v9; // eax
  WCHAR *v10; // r14
  __int64 v11; // r8
  const wchar_t *v12; // rbx
  int StringOrdinal; // eax
  int Instance; // esi
  __int64 (__fastcall *v16)(struct _tagpropertykey *, __int64, _QWORD); // rax
  unsigned int v17; // eax
  unsigned __int64 i; // r8
  unsigned int v19; // eax
  __int64 *v20; // rcx
  __int64 v21; // rax
  unsigned __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  LPCWSTR v25; // rbx
  struct IMemoryMappedCache *v26; // r12
  __int64 v27; // rcx
  char *v28; // rdx
  DWORD TickCount; // eax
  int refreshed; // r12d
  int v31; // r15d
  unsigned int v32; // ebx
  unsigned __int8 *v33; // rsi
  unsigned __int8 *v34; // rcx
  unsigned int v35; // ebx
  unsigned __int8 *v36; // rsi
  unsigned int v37; // ebx
  unsigned __int8 *v38; // rsi
  unsigned __int8 *v39; // rcx
  unsigned __int8 *v40; // rcx
  int v41; // eax
  int v42; // eax
  int cchValue; // [rsp+20h] [rbp-E0h]
  int cchValuea; // [rsp+20h] [rbp-E0h]
  int cchValueb; // [rsp+20h] [rbp-E0h]
  BOOL bIgnoreCase; // [rsp+28h] [rbp-D8h]
  LPCWSTR lpStringSource; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v50; // [rsp+60h] [rbp-A0h]
  __int128 v51; // [rsp+70h] [rbp-90h] BYREF
  struct IMemoryMappedCache *v52[2]; // [rsp+80h] [rbp-80h] BYREF
  void **v53; // [rsp+90h] [rbp-70h] BYREF
  char v54[272]; // [rsp+98h] [rbp-68h] BYREF
  char v55[8]; // [rsp+1A8h] [rbp+A8h] BYREF
  char v56[48]; // [rsp+1B0h] [rbp+B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  v5 = *((_QWORD *)this + 4);
  *a4 = 0;
  EnterCriticalSection(&CSchemaCache::s_critsec);
  v8 = (IUnknown **)(v5 + 24);
  if ( !*(_QWORD *)(v5 + 24) )
    goto LABEL_2;
  TickCount = GetTickCount();
  if ( TickCount - *(_DWORD *)(v5 + 200) <= 0x1388 )
    goto LABEL_53;
  *(_DWORD *)(v5 + 200) = TickCount;
  LODWORD(v51) = 0;
  refreshed = CCachedData<GLOBAL_MAPPING_HEADER,CGlobalMappingData>::RefreshIfNeeded(*v8, &v51);
  v31 = v51;
  if ( refreshed < 0 )
  {
    SafeRelease<IShellFolder2>(v5 + 24);
  }
  else if ( !(_DWORD)v51 )
  {
    goto LABEL_52;
  }
  lpStringSource = (LPCWSTR)CSchemaCache::s_ReleaseCB<IPropertyDescription>;
  v50 = 0;
  v32 = 0;
  if ( *(_DWORD *)(v5 + 84) )
  {
    do
    {
      v33 = *(unsigned __int8 **)(*(_QWORD *)(v5 + 88) + 8LL * v32);
      while ( v33 )
      {
        CHashTable<CSchemaData,_GUID>::s_DestroyCallback(
          &v33[*(unsigned int *)(v5 + 100)],
          *(_DWORD *)(v5 + 96),
          &lpStringSource);
        v34 = v33;
        v33 = *(unsigned __int8 **)v33;
        LocalFree(v34);
      }
      *(_QWORD *)(*(_QWORD *)(v5 + 88) + 8LL * v32++) = 0;
    }
    while ( v32 < *(_DWORD *)(v5 + 84) );
    v31 = v51;
  }
  *(_DWORD *)(v5 + 80) = 0;
  lpStringSource = (LPCWSTR)CSchemaCache::s_ReleaseCB<IPropertyDescription>;
  v50 = 0;
  v35 = 0;
  if ( *(_DWORD *)(v5 + 124) )
  {
    do
    {
      v36 = *(unsigned __int8 **)(*(_QWORD *)(v5 + 128) + 8LL * v35);
      while ( v36 )
      {
        CHashTable<CSchemaData,_GUID>::s_DestroyCallback(
          &v36[*(unsigned int *)(v5 + 140)],
          *(_DWORD *)(v5 + 136),
          &lpStringSource);
        v39 = v36;
        v36 = *(unsigned __int8 **)v36;
        LocalFree(v39);
      }
      *(_QWORD *)(*(_QWORD *)(v5 + 128) + 8LL * v35++) = 0;
    }
    while ( v35 < *(_DWORD *)(v5 + 124) );
    v31 = v51;
  }
  *(_DWORD *)(v5 + 120) = 0;
  lpStringSource = (LPCWSTR)CSchemaCache::s_ReleaseCB<IPropertyDescription>;
  v50 = 0;
  v37 = 0;
  if ( *(_DWORD *)(v5 + 164) )
  {
    do
    {
      v38 = *(unsigned __int8 **)(*(_QWORD *)(v5 + 168) + 8LL * v37);
      while ( v38 )
      {
        CHashTable<CSchemaData,_GUID>::s_DestroyCallback(
          &v38[*(unsigned int *)(v5 + 180)],
          *(_DWORD *)(v5 + 176),
          &lpStringSource);
        v40 = v38;
        v38 = *(unsigned __int8 **)v38;
        LocalFree(v40);
      }
      *(_QWORD *)(*(_QWORD *)(v5 + 168) + 8LL * v37++) = 0;
    }
    while ( v37 < *(_DWORD *)(v5 + 164) );
    v31 = v51;
  }
  *(_DWORD *)(v5 + 160) = 0;
  SafeRelease<IShellFolder2>(v5 + 192);
  if ( v31 )
    CSchemaCache::_RefreshCachedSchemas((CSchemaCache *)v5);
  v8 = (IUnknown **)(v5 + 24);
LABEL_52:
  if ( refreshed >= 0 )
    goto LABEL_53;
LABEL_2:
  lpStringSource = 0;
  v9 = wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,128>(
         v7,
         v6,
         &lpStringSource);
  if ( v9 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x224,
      (unsigned int)"onecoreuap\\shell\\propsys\\schemacache.cpp",
      (const char *)(unsigned int)v9,
      cchValue);
  v10 = (WCHAR *)lpStringSource;
  if ( lpStringSource )
  {
    v11 = -1;
    do
      ++v11;
    while ( lpStringSource[v11] );
    v12 = &lpStringSource[v11];
    if ( v11 && *(v12 - 1) == 92 )
      LODWORD(v11) = v11 - 1;
    StringOrdinal = FindStringOrdinal(0x800000u, lpStringSource, v11, L"\\", 1, 1);
    if ( StringOrdinal != -1 )
      v12 = &v10[StringOrdinal + 1];
  }
  else
  {
    v12 = L"Unknown";
  }
  v52[0] = (struct IMemoryMappedCache *)v12;
  PropsysTelemetry::SchemaCacheGlobalMappingLoad::Start<unsigned short const *,bool>((PropsysTelemetry::SchemaCacheGlobalMappingLoad *)&v53);
  *(_OWORD *)v52 = CACHEID_GlobalMapping;
  Instance = CCachedData<GLOBAL_MAPPING_HEADER,CGlobalMappingData>::CreateInstance(*(IUnknown **)(v5 + 16), v8);
  if ( Instance >= 0 )
    goto LABEL_11;
  v52[0] = 0;
  v41 = CSchemaCache::_BuildGlobalMapping((IUnknown **)v5, 0, v52);
  Instance = v41;
  if ( v41 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x22C,
      (unsigned int)"onecoreuap\\shell\\propsys\\schemacache.cpp",
      (const char *)(unsigned int)v41,
      cchValuea);
  }
  else
  {
    LODWORD(v51) = v41 == 0;
    PropsysTelemetry::SchemaCacheGlobalMappingLoad::RebuiltGlobalMapping<int &>(&v53, &v51);
    v51 = CACHEID_GlobalMapping;
    v42 = CCachedData<GLOBAL_MAPPING_HEADER,CGlobalMappingData>::CreateInstance(
            *(IUnknown **)(v5 + 16),
            (IUnknown **)(v5 + 24));
    Instance = v42;
    if ( v42 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x234,
        (unsigned int)"onecoreuap\\shell\\propsys\\schemacache.cpp",
        (const char *)(unsigned int)v42,
        cchValueb);
    (*(void (__fastcall **)(struct IMemoryMappedCache *))(*(_QWORD *)v52[0] + 16LL))(v52[0]);
    if ( Instance >= 0 )
LABEL_11:
      *(_DWORD *)(v5 + 200) = GetTickCount();
  }
  wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v53, (unsigned int)Instance);
  v53 = &PropsysTelemetry::SchemaCacheGlobalMappingLoad::`vftable';
  wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v53);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v56);
  wil::details::shared_object<wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PropsysTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(v55);
  wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PropsysTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<PropsysTelemetry,_TlgReflectorTag_Param0IsProviderType>(v54);
  if ( v10 )
    CoTaskMemFree(v10);
  if ( Instance >= 0 )
  {
LABEL_53:
    *(_QWORD *)&v51 = 0;
    if ( !*(_QWORD *)(v5 + 128) )
      goto LABEL_38;
    v16 = *(__int64 (__fastcall **)(struct _tagpropertykey *, __int64, _QWORD))(v5 + 112);
    if ( v16 )
    {
      v19 = v16(a2, 20, *(unsigned int *)(v5 + 124));
    }
    else
    {
      v17 = 314159269;
      for ( i = 0; i < 0x14; ++i )
        v17 ^= (v17 >> 2) + 2080 * v17 + *((unsigned __int8 *)&a2->fmtid.Data1 + i);
      v19 = (v17 & 0x7FFFFFFF) % *(_DWORD *)(v5 + 124);
    }
    v20 = *(__int64 **)(*(_QWORD *)(v5 + 128) + 8LL * v19);
    if ( !v20 )
      goto LABEL_38;
    do
    {
      if ( *((_DWORD *)v20 + 2) == 20 )
      {
        v21 = *(unsigned int *)(v5 + 144);
        v22 = *(_QWORD *)&a2->fmtid.Data1 - *(__int64 *)((char *)v20 + v21);
        if ( *(_QWORD *)&a2->fmtid.Data1 == *(__int64 *)((char *)v20 + v21) )
        {
          v22 = *(_QWORD *)a2->fmtid.Data4 - *(__int64 *)((char *)v20 + v21 + 8);
          if ( !v22 )
            v22 = a2->pid - (unsigned __int64)*(unsigned int *)((char *)v20 + v21 + 16);
        }
        if ( !v22 )
          break;
      }
      v20 = (__int64 *)*v20;
    }
    while ( v20 );
    if ( v20 && *(_DWORD *)(v5 + 136) == 8 )
    {
      *(_QWORD *)&v51 = *(__int64 *)((char *)v20 + *(unsigned int *)(v5 + 140));
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v51 + 8LL))(v51);
    }
    else
    {
LABEL_38:
      lpStringSource = 0;
      Instance = CSchemaCache::_GetSchemaForEntity<_tagpropertykey const &,&public: long CGlobalMappingData::GetSchemaIdForPropertyByKey(_tagpropertykey const &,_GUID *)>(
                   (CSchemaCache *)v5,
                   a2,
                   (struct CSchemaData **)&lpStringSource);
      if ( Instance < 0 )
        goto LABEL_36;
      v25 = lpStringSource;
      v26 = (struct IMemoryMappedCache *)*((_QWORD *)lpStringSource + 2);
      v52[0] = v26;
      v52[1] = (struct IMemoryMappedCache *)a2;
      lpStringSource = 0;
      Instance = CTSimpleFixedArray<OFFSET<CPropertyDescriptionInfo> const,CSimpleArrayStandardCompareHelper<OFFSET<CPropertyDescriptionInfo> const>>::BinarySearchEx<CKeySingleCompareHelper>(
                   v25 + 40,
                   v52,
                   v24,
                   &lpStringSource);
      if ( Instance >= 0 )
      {
        v27 = *((_QWORD *)v25 + 10);
        v28 = *(_DWORD *)(v27 + 4LL * (_QWORD)lpStringSource) == -1
            ? 0LL
            : (char *)v26 + *(unsigned int *)(v27 + 4LL * (_QWORD)lpStringSource);
        LODWORD(lpStringSource) = 1;
        HIDWORD(lpStringSource) = *((_DWORD *)v28 + 28);
        LODWORD(v50) = *((_DWORD *)v28 + 26);
        Instance = CSchemaObjectWithInfo<IPropertyDescription,CPropertyDescription,CPropertyDescriptionInfo,PROPDESCINIT>::CreateInstanceFromInfo(
                     *((IUnknown **)v25 + 7),
                     (__int64)&lpStringSource);
        if ( Instance >= 0 )
        {
          lpStringSource = (LPCWSTR)v51;
          if ( (int)CByteHashTable::_AddUpdateItem(
                      (CByteHashTable *)(v5 + 112),
                      1,
                      (const unsigned __int8 *)a2,
                      0x14u,
                      (const unsigned __int8 *)&lpStringSource,
                      bIgnoreCase,
                      0,
                      0) >= 0 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v51 + 8LL))(v51);
        }
      }
      (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)v25 + 16LL))(v25);
      if ( Instance < 0 )
        goto LABEL_36;
    }
    Instance = (**(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))v51)(v51, a3, a4);
LABEL_36:
    v23 = v51;
    *(_QWORD *)&v51 = 0;
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  LeaveCriticalSection(&CSchemaCache::s_critsec);
  if ( *(_BYTE *)(v5 + 204) )
  {
    *(_BYTE *)(v5 + 204) = 0;
    _ChangeNotifyHandlers();
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800387e0  push    rbp
0x1800387e2  push    rbx
0x1800387e3  push    rsi
0x1800387e4  push    rdi
0x1800387e5  push    r12
0x1800387e7  push    r13
0x1800387e9  push    r14
0x1800387eb  push    r15
0x1800387ed  lea     rbp, [rsp-0F8h]
0x1800387f5  sub     rsp, 1F8h
0x1800387fc  mov     rax, cs:__security_cookie
0x180038803  xor     rax, rsp
0x180038806  mov     [rbp+130h+var_50], rax
0x18003880d  mov     [rsp+230h+var_1E8], r9
0x180038812  mov     [rsp+230h+var_1E0], r8
0x180038817  mov     r13, rdx
0x18003881a  mov     rdi, [rcx+20h]
0x18003881e  xor     r15d, r15d
0x180038821  mov     [r9], r15
0x180038824  lea     rcx, ?s_critsec@CSchemaCache@@0VCCritSec@@A; lpCriticalSection
0x18003882b  call    cs:__imp_EnterCriticalSection
0x180038831  lea     rsi, [rdi+18h]
0x180038835  cmp     [rsi], r15
0x180038838  jnz     loc_180038C54
0x18003883e  mov     [rsp+230h+lpStringSource], r15
0x180038843  lea     r8, [rsp+230h+lpStringSource]
0x180038848  call    ??$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJPEAXPEAUHINSTANCE__@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18003884d  mov     rcx, [rbp+138h]; this
0x180038854  lea     r12, aOnecoreuapShel_10; "onecoreuap\\shell\\propsys\\schemacache"...
0x18003885b  test    eax, eax
0x18003885d  js      loc_1800389D1
0x180038863  mov     [rsp+230h+var_1F0], r15b
0x180038868  mov     r14, [rsp+230h+lpStringSource]
0x18003886d  test    r14, r14
0x180038870  jz      loc_1800389A7
0x180038876  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003887a  inc     r8; cchSource
0x18003887d  cmp     [r14+r8*2], r15w
0x180038882  jnz     short loc_18003887A
0x180038884  lea     rbx, [r14+r8*2]
0x180038888  test    r8, r8
0x18003888b  jnz     loc_1800389BE
0x180038891  mov     [rsp+230h+bIgnoreCase], 1; bIgnoreCase
0x180038899  mov     [rsp+230h+cchValue], 1; cchValue
0x1800388a1  lea     r9, asc_1800D17E4; "\\"
0x1800388a8  mov     rdx, r14; lpStringSource
0x1800388ab  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x1800388b0  call    cs:__imp_FindStringOrdinal
0x1800388b6  cmp     eax, 0FFFFFFFFh
0x1800388b9  jz      short loc_1800388C5
0x1800388bb  movsxd  rbx, eax
0x1800388be  inc     rbx
0x1800388c1  lea     rbx, [r14+rbx*2]
0x1800388c5  mov     [rbp+130h+var_1B0], rbx
0x1800388c9  lea     r8, [rsp+230h+var_1F0]
0x1800388ce  lea     rdx, [rbp+130h+var_1B0]
0x1800388d2  lea     rcx, [rbp+130h+var_1A0]; this
0x1800388d6  call    ??$Start@PEBG_N@SchemaCacheGlobalMappingLoad@PropsysTelemetry@@SA?AV01@$$QEAPEBG$$QEA_N@Z; PropsysTelemetry::SchemaCacheGlobalMappingLoad::Start<ushort const *,bool>(ushort const * &&,bool &&)
0x1800388db  nop
0x1800388dc  movups  xmm0, cs:CACHEID_GlobalMapping
0x1800388e3  movdqu  xmmword ptr [rbp+130h+var_1B0], xmm0
0x1800388e8  mov     qword ptr [rsp+230h+cchValue], rsi; int
0x1800388ed  mov     r9d, 1
0x1800388f3  xor     r8d, r8d
0x1800388f6  lea     rdx, [rbp+130h+var_1B0]
0x1800388fa  mov     rcx, [rdi+10h]; punk
0x1800388fe  call    ?CreateInstance@?$CCachedData@UGLOBAL_MAPPING_HEADER@@VCGlobalMappingData@@@@SAJPEAUIMemoryMappedCacheMgr@@U_GUID@@PEAUIMemoryMappedCache@@HPEAPEAVCGlobalMappingData@@@Z; CCachedData<GLOBAL_MAPPING_HEADER,CGlobalMappingData>::CreateInstance(IMemoryMappedCacheMgr *,_GUID,IMemoryMappedCache *,int,CGlobalMappingData * *)
0x180038903  mov     esi, eax
0x180038905  test    eax, eax
0x180038907  js      loc_180038DF3
0x18003890d  call    cs:__imp_GetTickCount
0x180038913  mov     [rdi+0C8h], eax
0x180038919  mov     edx, esi
0x18003891b  lea     rcx, [rbp+130h+var_1A0]
0x18003891f  call    ?Stop@?$ActivityBase@VPropsysTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180038924  nop
0x180038925  lea     rax, ??_7SchemaCacheGlobalMappingLoad@PropsysTelemetry@@6B@; const PropsysTelemetry::SchemaCacheGlobalMappingLoad::`vftable'
0x18003892c  mov     [rbp+130h+var_1A0], rax
0x180038930  lea     rcx, [rbp+130h+var_1A0]
0x180038934  call    ?Destroy@?$ActivityBase@VPropsysTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180038939  lea     rcx, [rbp+130h+var_80]; this
0x180038940  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180038945  lea     rcx, [rbp+130h+var_88]
0x18003894c  call    ?reset@?$shared_object@V?$ActivityData@VPropsysTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPropsysTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PropsysTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180038951  lea     rcx, [rbp+130h+var_198]
0x180038955  call    ??1?$ActivityData@VPropsysTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPropsysTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PropsysTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<PropsysTelemetry,_TlgReflectorTag_Param0IsProviderType>(void)
0x18003895a  nop
0x18003895b  test    r14, r14
0x18003895e  jnz     short loc_1800389B3
0x180038960  test    esi, esi
0x180038962  jns     loc_180038C3B
0x180038968  lea     rcx, ?s_critsec@CSchemaCache@@0VCCritSec@@A; lpCriticalSection
0x18003896f  call    cs:__imp_LeaveCriticalSection
0x180038975  cmp     [rdi+0CCh], r15b
0x18003897c  jnz     loc_180038ECC
0x180038982  mov     eax, esi
0x180038984  mov     rcx, [rbp+130h+var_50]
0x18003898b  xor     rcx, rsp; StackCookie
0x18003898e  call    __security_check_cookie
0x180038993  add     rsp, 1F8h
0x18003899a  pop     r15
0x18003899c  pop     r14
0x18003899e  pop     r13
0x1800389a0  pop     r12
0x1800389a2  pop     rdi
0x1800389a3  pop     rsi
0x1800389a4  pop     rbx
0x1800389a5  pop     rbp
0x1800389a6  retn
0x1800389a7  lea     rbx, aUnknown; "Unknown"
0x1800389ae  jmp     loc_1800388C5
0x1800389b3  mov     rcx, r14; pv
0x1800389b6  call    cs:__imp_CoTaskMemFree
0x1800389bc  jmp     short loc_180038960
0x1800389be  cmp     word ptr [rbx-2], 5Ch ; '\'
0x1800389c3  jnz     loc_180038891
0x1800389c9  dec     r8
0x1800389cc  jmp     loc_180038891
0x1800389d1  mov     r9d, eax; char *
0x1800389d4  mov     r8, r12; unsigned int
0x1800389d7  mov     edx, 224h; void *
0x1800389dc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800389e1  jmp     loc_180038863
0x1800389e6  mov     rax, [rdi+70h]
0x1800389ea  test    rax, rax
0x1800389ed  jnz     loc_180038BE6
0x1800389f3  mov     eax, 12B9B0A5h
0x1800389f8  mov     r8, r15
0x1800389fb  movzx   edx, byte ptr [r8+r13]
0x180038a00  imul    ecx, eax, 820h
0x180038a06  add     edx, ecx
0x180038a08  mov     ecx, eax
0x180038a0a  shr     ecx, 2
0x180038a0d  add     edx, ecx
0x180038a0f  xor     eax, edx
0x180038a11  inc     r8
0x180038a14  cmp     r8, 14h
0x180038a18  jb      short loc_1800389FB
0x180038a1a  btr     eax, 1Fh
0x180038a1e  xor     edx, edx
0x180038a20  div     dword ptr [rdi+7Ch]
0x180038a23  mov     eax, edx
0x180038a25  mov     ecx, eax
0x180038a27  mov     rax, [rdi+80h]
0x180038a2e  mov     rcx, [rax+rcx*8]
0x180038a32  test    rcx, rcx
0x180038a35  jz      loc_180038ADD
0x180038a3b  cmp     dword ptr [rcx+8], 14h
0x180038a3f  jnz     short loc_180038A6C
0x180038a41  mov     eax, [rdi+90h]
0x180038a47  mov     rdx, [r13+0]
0x180038a4b  sub     rdx, [rax+rcx]
0x180038a4f  jnz     short loc_180038A67
0x180038a51  mov     rdx, [r13+8]
0x180038a55  sub     rdx, [rax+rcx+8]
0x180038a5a  jnz     short loc_180038A67
0x180038a5c  mov     edx, [r13+10h]
0x180038a60  mov     eax, [rax+rcx+10h]
0x180038a64  sub     rdx, rax
0x180038a67  test    rdx, rdx
0x180038a6a  jz      short loc_180038A74
0x180038a6c  mov     rcx, [rcx]
0x180038a6f  test    rcx, rcx
0x180038a72  jnz     short loc_180038A3B
0x180038a74  test    rcx, rcx
0x180038a77  jz      short loc_180038ADD
0x180038a79  cmp     dword ptr [rdi+88h], 8
0x180038a80  jnz     short loc_180038ADD
0x180038a82  mov     eax, [rdi+8Ch]
0x180038a88  mov     rcx, [rax+rcx]
0x180038a8c  mov     qword ptr [rsp+230h+var_1C0], rcx
0x180038a91  mov     rax, [rcx]
0x180038a94  mov     rax, [rax+8]
0x180038a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a9d  mov     rcx, qword ptr [rsp+230h+var_1C0]
0x180038aa2  mov     rax, [rcx]
0x180038aa5  mov     r8, [rsp+230h+var_1E8]
0x180038aaa  mov     rdx, [rsp+230h+var_1E0]
0x180038aaf  mov     rax, [rax]
0x180038ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038ab7  mov     esi, eax
0x180038ab9  mov     rcx, qword ptr [rsp+230h+var_1C0]
0x180038abe  mov     qword ptr [rsp+230h+var_1C0], r15
0x180038ac3  test    rcx, rcx
0x180038ac6  jz      loc_180038968
0x180038acc  mov     rax, [rcx]
0x180038acf  mov     rax, [rax+10h]
0x180038ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038ad8  jmp     loc_180038968
0x180038add  mov     [rsp+230h+lpStringSource], r15
0x180038ae2  lea     r8, [rsp+230h+lpStringSource]; struct CSchemaData **
0x180038ae7  mov     rdx, r13; struct _tagpropertykey *
0x180038aea  mov     rcx, rdi; this
0x180038aed  call    ??$_GetSchemaForEntity@AEBU_tagpropertykey@@$1?GetSchemaIdForPropertyByKey@CGlobalMappingData@@QEAAJAEBU1@PEAU_GUID@@@Z@CSchemaCache@@AEAAJAEBU_tagpropertykey@@PEAPEAVCSchemaData@@@Z; CSchemaCache::_GetSchemaForEntity<_tagpropertykey const &,&CGlobalMappingData::GetSchemaIdForPropertyByKey(_tagpropertykey const &,_GUID *)>(_tagpropertykey const &,CSchemaData * *)
0x180038af2  mov     esi, eax
0x180038af4  test    eax, eax
0x180038af6  js      short loc_180038AB9
0x180038af8  mov     rbx, [rsp+230h+lpStringSource]
0x180038afd  mov     r12, [rbx+10h]
0x180038b01  mov     [rbp+130h+var_1B0], r12
0x180038b05  mov     [rbp+130h+var_1B0+8], r13
0x180038b09  mov     [rsp+230h+lpStringSource], r15
0x180038b0e  lea     r9, [rsp+230h+lpStringSource]
0x180038b13  lea     rdx, [rbp+130h+var_1B0]
0x180038b17  lea     rcx, [rbx+50h]
0x180038b1b  call    ??$BinarySearchEx@VCKeySingleCompareHelper@@@?$CTSimpleFixedArray@$$CBU?$OFFSET@UCPropertyDescriptionInfo@@@@V?$CSimpleArrayStandardCompareHelper@$$CBU?$OFFSET@UCPropertyDescriptionInfo@@@@@@@@QEBAJAEBVCKeySingleCompareHelper@@AEBU?$OFFSET@UCPropertyDescriptionInfo@@@@PEA_K@Z; CTSimpleFixedArray<OFFSET<CPropertyDescriptionInfo> const,CSimpleArrayStandardCompareHelper<OFFSET<CPropertyDescriptionInfo> const>>::BinarySearchEx<CKeySingleCompareHelper>(CKeySingleCompareHelper const &,OFFSET<CPropertyDescriptionInfo> const &,unsigned __int64 *)
0x180038b20  mov     esi, eax
0x180038b22  test    eax, eax
0x180038b24  js      loc_180038EC4
0x180038b2a  mov     rcx, [rbx+50h]
0x180038b2e  mov     rax, [rsp+230h+lpStringSource]
0x180038b33  cmp     dword ptr [rcx+rax*4], 0FFFFFFFFh
0x180038b37  jz      loc_180038BFC
0x180038b3d  mov     edx, [rcx+rax*4]
0x180038b40  add     rdx, r12
0x180038b43  xor     r15d, r15d
0x180038b46  mov     dword ptr [rsp+230h+lpStringSource], 1
0x180038b4e  mov     eax, [rdx+70h]
0x180038b51  mov     dword ptr [rsp+230h+lpStringSource+4], eax
0x180038b55  mov     eax, [rdx+68h]
0x180038b58  mov     dword ptr [rsp+230h+var_1D0], eax
0x180038b5c  lea     rax, [rsp+230h+lpStringSource]
0x180038b61  mov     qword ptr [rsp+230h+cchValue], rax; __int64
0x180038b66  lea     r9, [rsp+230h+var_1C0]
0x180038b6b  lea     r8, _GUID_6f79d558_3e96_4549_a1d1_7d75d2288814
0x180038b72  mov     rcx, [rbx+38h]; punk
0x180038b76  call    ?CreateInstanceFromInfo@?$CSchemaObjectWithInfo@UIPropertyDescription@@VCPropertyDescription@@UCPropertyDescriptionInfo@@UPROPDESCINIT@@@@SAJPEAUIMemoryMappedCache@@PEBUCPropertyDescriptionInfo@@AEBU_GUID@@PEAPEAXPEBUPROPDESCINIT@@@Z; CSchemaObjectWithInfo<IPropertyDescription,CPropertyDescription,CPropertyDescriptionInfo,PROPDESCINIT>::CreateInstanceFromInfo(IMemoryMappedCache *,CPropertyDescriptionInfo const *,_GUID const &,void * *,PROPDESCINIT const *)
0x180038b7b  mov     esi, eax
0x180038b7d  test    eax, eax
0x180038b7f  js      short loc_180038BCA
0x180038b81  mov     rax, qword ptr [rsp+230h+var_1C0]
0x180038b86  mov     [rsp+230h+lpStringSource], rax
0x180038b8b  mov     [rsp+230h+var_1F8], r15d; unsigned int
0x180038b90  mov     [rsp+230h+var_200], r15; unsigned __int8 *
0x180038b95  lea     rax, [rsp+230h+lpStringSource]
0x180038b9a  mov     qword ptr [rsp+230h+cchValue], rax; Src
0x180038b9f  mov     r9d, 14h; unsigned int
0x180038ba5  mov     r8, r13; unsigned __int8 *
0x180038ba8  lea     edx, [r9-13h]; int
0x180038bac  lea     rcx, [rdi+70h]; this
0x180038bb0  call    ?_AddUpdateItem@CByteHashTable@@AEAAJHPEBEI0IPEAEI@Z; CByteHashTable::_AddUpdateItem(int,uchar const *,uint,uchar const *,uint,uchar *,uint)
0x180038bb5  test    eax, eax
0x180038bb7  js      short loc_180038BCA
0x180038bb9  mov     rcx, qword ptr [rsp+230h+var_1C0]
0x180038bbe  mov     rax, [rcx]
0x180038bc1  mov     rax, [rax+8]
0x180038bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038bca  mov     rax, [rbx]
0x180038bcd  mov     rcx, rbx
0x180038bd0  mov     rax, [rax+10h]
0x180038bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038bd9  test    esi, esi
0x180038bdb  jns     loc_180038A9D
0x180038be1  jmp     loc_180038AB9
0x180038be6  mov     r8d, [rdi+7Ch]
0x180038bea  mov     edx, 14h
0x180038bef  mov     rcx, r13
0x180038bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038bf7  jmp     loc_180038A25
0x180038bfc  xor     r15d, r15d
0x180038bff  mov     edx, r15d
0x180038c02  jmp     loc_180038B46
0x180038c07  mov     r15d, dword ptr [rsp+230h+var_1C0]
0x180038c0c  xor     r14d, r14d
0x180038c0f  mov     [rdi+0A0h], r14d
0x180038c16  lea     rcx, [rdi+0C0h]
0x180038c1d  call    ??$SafeRelease@UIShellFolder2@@@@YAXPEAPEAUIShellFolder2@@@Z; SafeRelease<IShellFolder2>(IShellFolder2 * *)
0x180038c22  test    r15d, r15d
0x180038c25  jnz     loc_180038EA2
0x180038c2b  lea     rsi, [rdi+18h]
0x180038c2f  xor     r15d, r15d
0x180038c32  test    r12d, r12d
0x180038c35  js      loc_18003883E
0x180038c3b  xor     eax, eax
0x180038c3d  mov     qword ptr [rsp+230h+var_1C0], rax
0x180038c42  cmp     [rdi+80h], r15
0x180038c49  jz      loc_180038ADD
0x180038c4f  jmp     loc_1800389E6
0x180038c54  call    cs:__imp_GetTickCount
0x180038c5a  mov     ecx, eax
0x180038c5c  sub     ecx, [rdi+0C8h]
0x180038c62  cmp     ecx, 1388h
0x180038c68  jbe     short loc_180038C3B
0x180038c6a  mov     [rdi+0C8h], eax
0x180038c70  mov     dword ptr [rsp+230h+var_1C0], r15d
0x180038c75  lea     rdx, [rsp+230h+var_1C0]
0x180038c7a  mov     rcx, [rsi]
0x180038c7d  call    ?RefreshIfNeeded@?$CCachedData@UGLOBAL_MAPPING_HEADER@@VCGlobalMappingData@@@@QEAAJPEAH@Z; CCachedData<GLOBAL_MAPPING_HEADER,CGlobalMappingData>::RefreshIfNeeded(int *)
0x180038c82  mov     r12d, eax
0x180038c85  mov     r15d, dword ptr [rsp+230h+var_1C0]
0x180038c8a  xor     r14d, r14d
0x180038c8d  test    eax, eax
0x180038c8f  js      loc_180038E95
0x180038c95  test    r15d, r15d
0x180038c98  jz      short loc_180038C2F
0x180038c9a  lea     rax, ??$s_ReleaseCB@UIPropertyDescription@@@CSchemaCache@@SAXPEAUIPropertyDescription@@@Z; CSchemaCache::s_ReleaseCB<IPropertyDescription>(IPropertyDescription *)
0x180038ca1  mov     [rsp+230h+lpStringSource], rax
0x180038ca6  mov     [rsp+230h+var_1D0], r14
0x180038cab  mov     ebx, r14d
0x180038cae  cmp     [rdi+54h], r14d
  ... truncated ...
```
