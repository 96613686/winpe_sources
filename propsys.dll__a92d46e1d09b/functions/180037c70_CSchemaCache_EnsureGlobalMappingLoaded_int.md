# CSchemaCache::_EnsureGlobalMappingLoaded(int)

- ea: `0x180037c70`
- end: `0x180038196`
- name: `?_EnsureGlobalMappingLoaded@CSchemaCache@@AEAAJH@Z`
- size: `1318`
- prototype: `__int64 __fastcall(CSchemaCache *__hidden this, int)`
- caller_count: `9`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180035310`
- `0x180035b18`
- `0x1800362d0`
- `0x180037acc`
- `0x1800385f0`
- `0x180039330`
- `0x180090650`
- `0x180090870`
- `0x1800920ec`

## callees

- `0x180003898`
- `0x180017970`
- `0x18001c4fc`
- `0x18002f9e0`
- `0x1800359b8`
- `0x180037c70`
- `0x180039230`
- `0x1800396ac`
- `0x1800398d8`
- `0x180039a10`
- `0x180039ad8`
- `0x180039b78`
- `0x180039c40`
- `0x180039cd0`
- `0x180063900`
- `0x18006ed20`
- `0x18008f890`
- `0x1800921e8`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180037d2c`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180037d2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038029`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038060`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003809f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038029`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038060`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003809f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180037da8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180037ea7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180037da8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180037ea7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037dff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037dff`

## string_xrefs

- `0x180037e91`: `onecoreuap\shell\propsys\schemacache.cpp`
- `0x180038129`: `onecoreuap\shell\propsys\schemacache.cpp`
- `0x18003816e`: `onecoreuap\shell\propsys\schemacache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSchemaCache::_EnsureGlobalMappingLoaded(CSchemaCache *this, __int64 a2)
{
  int v2; // r14d
  IUnknown **v4; // rdi
  DWORD *v5; // r15
  int v6; // esi
  int v7; // eax
  WCHAR *v8; // r14
  __int64 v9; // r8
  const unsigned __int16 *v10; // r12
  int StringOrdinal; // eax
  DWORD *v12; // r13
  int refreshed; // r12d
  int v14; // r13d
  DWORD TickCount; // eax
  unsigned int v17; // r13d
  const WCHAR *v18; // rcx
  unsigned __int8 *v19; // rdi
  unsigned int v20; // edi
  const WCHAR *v21; // rcx
  unsigned __int8 *v22; // r13
  unsigned int v23; // r13d
  const WCHAR *v24; // rcx
  unsigned __int8 *v25; // rdi
  unsigned __int8 *v26; // rcx
  unsigned __int8 *v27; // rcx
  unsigned __int8 *v28; // rcx
  int v29; // eax
  int Instance; // eax
  int cchValue; // [rsp+20h] [rbp-E0h]
  int cchValuea; // [rsp+20h] [rbp-E0h]
  int cchValueb; // [rsp+20h] [rbp-E0h]
  bool v34; // [rsp+30h] [rbp-D0h]
  int v35; // [rsp+34h] [rbp-CCh] BYREF
  LPCWSTR lpStringSource; // [rsp+38h] [rbp-C8h] BYREF
  struct IMemoryMappedCache *v37[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v38; // [rsp+50h] [rbp-B0h] BYREF
  void **v39; // [rsp+60h] [rbp-A0h] BYREF
  char v40[272]; // [rsp+68h] [rbp-98h] BYREF
  char v41[8]; // [rsp+178h] [rbp+78h] BYREF
  char v42[24]; // [rsp+180h] [rbp+80h] BYREF
  int v43; // [rsp+198h] [rbp+98h]
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  v2 = a2;
  v4 = (IUnknown **)((char *)this + 24);
  if ( !*((_QWORD *)this + 3) )
  {
    v5 = (DWORD *)((char *)this + 200);
    v6 = 0;
    goto LABEL_3;
  }
  TickCount = GetTickCount();
  v6 = 0;
  if ( v2 || TickCount - *((_DWORD *)this + 50) > 0x1388 )
  {
    v5 = (DWORD *)((char *)this + 200);
    *((_DWORD *)this + 50) = TickCount;
    LODWORD(v37[0]) = 0;
    refreshed = CCachedData<GLOBAL_MAPPING_HEADER,CGlobalMappingData>::RefreshIfNeeded(*v4, v37);
    if ( refreshed < 0 )
    {
      SafeRelease<IShellFolder2>(v4);
      v14 = (int)v37[0];
    }
    else
    {
      v14 = (int)v37[0];
      if ( !LODWORD(v37[0]) )
        goto LABEL_21;
    }
    *(_QWORD *)&v38 = CSchemaCache::s_ReleaseCB<IPropertyDescription>;
    *((_QWORD *)&v38 + 1) = 0;
    if ( *((_DWORD *)this + 21) )
    {
      v17 = 0;
      do
      {
        v18 = (const WCHAR *)(8LL * v17);
        lpStringSource = v18;
        v19 = *(unsigned __int8 **)((char *)v18 + *((_QWORD *)this + 11));
        if ( v19 )
        {
          do
          {
            CHashTable<CSchemaData,_GUID>::s_DestroyCallback(
              &v19[*((unsigned int *)this + 25)],
              *((_DWORD *)this + 24),
              &v38);
            v26 = v19;
            v19 = *(unsigned __int8 **)v19;
            LocalFree(v26);
          }
          while ( v19 );
          v18 = lpStringSource;
        }
        *(_QWORD *)((char *)v18 + *((_QWORD *)this + 11)) = 0;
        ++v17;
      }
      while ( v17 < *((_DWORD *)this + 21) );
      v4 = (IUnknown **)((char *)this + 24);
      v14 = (int)v37[0];
    }
    *((_DWORD *)this + 20) = 0;
    *(_QWORD *)&v38 = CSchemaCache::s_ReleaseCB<IPropertyDescription>;
    *((_QWORD *)&v38 + 1) = 0;
    if ( *((_DWORD *)this + 31) )
    {
      v20 = 0;
      do
      {
        v21 = (const WCHAR *)(8LL * v20);
        lpStringSource = v21;
        v22 = *(unsigned __int8 **)((char *)v21 + *((_QWORD *)this + 16));
        if ( v22 )
        {
          do
          {
            CHashTable<CSchemaData,_GUID>::s_DestroyCallback(
              &v22[*((unsigned int *)this + 35)],
              *((_DWORD *)this + 34),
              &v38);
            v27 = v22;
            v22 = *(unsigned __int8 **)v22;
            LocalFree(v27);
          }
          while ( v22 );
          v21 = lpStringSource;
        }
        *(_QWORD *)((char *)v21 + *((_QWORD *)this + 16)) = 0;
        ++v20;
      }
      while ( v20 < *((_DWORD *)this + 31) );
      v4 = (IUnknown **)((char *)this + 24);
      v14 = (int)v37[0];
    }
    *((_DWORD *)this + 30) = 0;
    *(_QWORD *)&v38 = CSchemaCache::s_ReleaseCB<IPropertyDescription>;
    *((_QWORD *)&v38 + 1) = 0;
    if ( *((_DWORD *)this + 41) )
    {
      v23 = 0;
      do
      {
        v24 = (const WCHAR *)(8LL * v23);
        lpStringSource = v24;
        v25 = *(unsigned __int8 **)((char *)v24 + *((_QWORD *)this + 21));
        if ( v25 )
        {
          do
          {
            CHashTable<CSchemaData,_GUID>::s_DestroyCallback(
              &v25[*((unsigned int *)this + 45)],
              *((_DWORD *)this + 44),
              &v38);
            v28 = v25;
            v25 = *(unsigned __int8 **)v25;
            LocalFree(v28);
          }
          while ( v25 );
          v24 = lpStringSource;
        }
        *(_QWORD *)((char *)v24 + *((_QWORD *)this + 21)) = 0;
        ++v23;
      }
      while ( v23 < *((_DWORD *)this + 41) );
      v4 = (IUnknown **)((char *)this + 24);
      v14 = (int)v37[0];
    }
    *((_DWORD *)this + 40) = 0;
    SafeRelease<IShellFolder2>((char *)this + 192);
    if ( v14 )
      CSchemaCache::_RefreshCachedSchemas(this);
LABEL_21:
    if ( refreshed >= 0 )
      return (unsigned int)refreshed;
LABEL_3:
    lpStringSource = 0;
    v7 = wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,128>(
           this,
           a2,
           &lpStringSource);
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x224,
        (unsigned int)"onecoreuap\\shell\\propsys\\schemacache.cpp",
        (const char *)(unsigned int)v7,
        cchValue);
    v34 = v2 != 0;
    v8 = (WCHAR *)lpStringSource;
    if ( lpStringSource )
    {
      v9 = -1;
      do
        ++v9;
      while ( lpStringSource[v9] );
      v10 = &lpStringSource[v9];
      if ( v9 && *(v10 - 1) == 92 )
        LODWORD(v9) = v9 - 1;
      StringOrdinal = FindStringOrdinal(0x800000u, lpStringSource, v9, L"\\", 1, 1);
      if ( StringOrdinal != -1 )
        v10 = &v8[StringOrdinal + 1];
      v12 = (DWORD *)((char *)this + 200);
    }
    else
    {
      v10 = L"Unknown";
      v12 = v5;
    }
    wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v39);
    v39 = &PropsysTelemetry::SchemaCacheGlobalMappingLoad::`vftable';
    PropsysTelemetry::SchemaCacheGlobalMappingLoad::StartActivity(
      (PropsysTelemetry::SchemaCacheGlobalMappingLoad *)&v39,
      v10,
      v34);
    v38 = CACHEID_GlobalMapping;
    refreshed = CCachedData<GLOBAL_MAPPING_HEADER,CGlobalMappingData>::CreateInstance(*((IUnknown **)this + 2), v4);
    if ( refreshed < 0 )
    {
      v37[0] = 0;
      v29 = CSchemaCache::_BuildGlobalMapping((IUnknown **)this, 0, v37);
      refreshed = v29;
      if ( v29 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x22C,
          (unsigned int)"onecoreuap\\shell\\propsys\\schemacache.cpp",
          (const char *)(unsigned int)v29,
          cchValuea);
        goto LABEL_15;
      }
      LOBYTE(v6) = v29 == 0;
      v35 = v6;
      PropsysTelemetry::SchemaCacheGlobalMappingLoad::RebuiltGlobalMapping<int &>(&v39, &v35);
      v38 = CACHEID_GlobalMapping;
      Instance = CCachedData<GLOBAL_MAPPING_HEADER,CGlobalMappingData>::CreateInstance(*((IUnknown **)this + 2), v4);
      refreshed = Instance;
      if ( Instance < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x234,
          (unsigned int)"onecoreuap\\shell\\propsys\\schemacache.cpp",
          (const char *)(unsigned int)Instance,
          cchValueb);
      (*(void (__fastcall **)(struct IMemoryMappedCache *))(*(_QWORD *)v37[0] + 16LL))(v37[0]);
      if ( refreshed < 0 )
        goto LABEL_15;
    }
    else
    {
      v5 = v12;
    }
    *v5 = GetTickCount();
LABEL_15:
    wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
      &v39,
      (unsigned int)refreshed);
    v39 = &PropsysTelemetry::SchemaCacheGlobalMappingLoad::`vftable';
    wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v39);
    if ( v43 )
      wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v42);
    wil::details::shared_object<wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PropsysTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(v41);
    wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PropsysTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<PropsysTelemetry,_TlgReflectorTag_Param0IsProviderType>(v40);
    if ( v8 )
      CoTaskMemFree(v8);
    return (unsigned int)refreshed;
  }
  return 0;
}

```

## disassembly

```asm
0x180037c70  push    rbp
0x180037c72  push    rbx
0x180037c73  push    rsi
0x180037c74  push    rdi
0x180037c75  push    r12
0x180037c77  push    r13
0x180037c79  push    r14
0x180037c7b  push    r15
0x180037c7d  lea     rbp, [rsp-0C8h]
0x180037c85  sub     rsp, 1C8h
0x180037c8c  mov     rax, cs:__security_cookie
0x180037c93  xor     rax, rsp
0x180037c96  mov     [rbp+100h+var_50], rax
0x180037c9d  mov     r14d, edx
0x180037ca0  mov     rbx, rcx
0x180037ca3  lea     rdi, [rcx+18h]
0x180037ca7  cmp     qword ptr [rdi], 0
0x180037cab  jnz     loc_180037EA7
0x180037cb1  lea     r15, [rcx+0C8h]
0x180037cb8  xor     esi, esi
0x180037cba  mov     [rsp+200h+lpStringSource], rsi
0x180037cbf  lea     r8, [rsp+200h+lpStringSource]
0x180037cc4  call    ??$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJPEAXPEAUHINSTANCE__@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180037cc9  mov     rcx, [rbp+108h]; this
0x180037cd0  test    eax, eax
0x180037cd2  js      loc_180037E8E
0x180037cd8  test    r14d, r14d
0x180037cdb  setnz   [rsp+200h+var_1D0]
0x180037ce0  mov     r14, [rsp+200h+lpStringSource]
0x180037ce5  test    r14, r14
0x180037ce8  jz      loc_180037E6A
0x180037cee  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180037cf5  inc     r8; cchSource
0x180037cf8  cmp     word ptr [r14+r8*2], 0
0x180037cfe  jnz     short loc_180037CF5
0x180037d00  lea     r12, [r14+r8*2]
0x180037d04  test    r8, r8
0x180037d07  jnz     loc_180037E79
0x180037d0d  mov     [rsp+200h+bIgnoreCase], 1; bIgnoreCase
0x180037d15  mov     [rsp+200h+cchValue], 1; cchValue
0x180037d1d  lea     r9, asc_1800D17E4; "\\"
0x180037d24  mov     rdx, r14; lpStringSource
0x180037d27  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x180037d2c  call    cs:__imp_FindStringOrdinal
0x180037d32  cmp     eax, 0FFFFFFFFh
0x180037d35  jz      short loc_180037D41
0x180037d37  movsxd  r12, eax
0x180037d3a  inc     r12
0x180037d3d  lea     r12, [r14+r12*2]
0x180037d41  lea     r13, [rbx+0C8h]
0x180037d48  lea     rcx, [rsp+200h+var_1A0]
0x180037d4d  call    ??0?$ActivityBase@VPropsysTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180037d52  lea     rax, ??_7SchemaCacheGlobalMappingLoad@PropsysTelemetry@@6B@; const PropsysTelemetry::SchemaCacheGlobalMappingLoad::`vftable'
0x180037d59  mov     [rsp+200h+var_1A0], rax
0x180037d5e  movzx   r8d, [rsp+200h+var_1D0]; bool
0x180037d64  mov     rdx, r12; unsigned __int16 *
0x180037d67  lea     rcx, [rsp+200h+var_1A0]; this
0x180037d6c  call    ?StartActivity@SchemaCacheGlobalMappingLoad@PropsysTelemetry@@QEAAXPEBG_N@Z; PropsysTelemetry::SchemaCacheGlobalMappingLoad::StartActivity(ushort const *,bool)
0x180037d71  nop
0x180037d72  movups  xmm0, cs:CACHEID_GlobalMapping
0x180037d79  movaps  [rsp+200h+var_1B0], xmm0
0x180037d7e  mov     qword ptr [rsp+200h+cchValue], rdi; int
0x180037d83  mov     r9d, 1
0x180037d89  xor     r8d, r8d
0x180037d8c  lea     rdx, [rsp+200h+var_1B0]
0x180037d91  mov     rcx, [rbx+10h]; punk
0x180037d95  call    ?CreateInstance@?$CCachedData@UGLOBAL_MAPPING_HEADER@@VCGlobalMappingData@@@@SAJPEAUIMemoryMappedCacheMgr@@U_GUID@@PEAUIMemoryMappedCache@@HPEAPEAVCGlobalMappingData@@@Z; CCachedData<GLOBAL_MAPPING_HEADER,CGlobalMappingData>::CreateInstance(IMemoryMappedCacheMgr *,_GUID,IMemoryMappedCache *,int,CGlobalMappingData * *)
0x180037d9a  mov     r12d, eax
0x180037d9d  test    eax, eax
0x180037d9f  js      loc_1800380B4
0x180037da5  mov     r15, r13
0x180037da8  call    cs:__imp_GetTickCount
0x180037dae  mov     [r15], eax
0x180037db1  mov     edx, r12d
0x180037db4  lea     rcx, [rsp+200h+var_1A0]
0x180037db9  call    ?Stop@?$ActivityBase@VPropsysTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180037dbe  nop
0x180037dbf  lea     rax, ??_7SchemaCacheGlobalMappingLoad@PropsysTelemetry@@6B@; const PropsysTelemetry::SchemaCacheGlobalMappingLoad::`vftable'
0x180037dc6  mov     [rsp+200h+var_1A0], rax
0x180037dcb  lea     rcx, [rsp+200h+var_1A0]
0x180037dd0  call    ?Destroy@?$ActivityBase@VPropsysTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180037dd5  nop
0x180037dd6  cmp     [rbp+100h+var_68], 0
0x180037ddd  jnz     loc_180038184
0x180037de3  lea     rcx, [rbp+100h+var_88]
0x180037de7  call    ?reset@?$shared_object@V?$ActivityData@VPropsysTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPropsysTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PropsysTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180037dec  lea     rcx, [rsp+200h+var_198]
0x180037df1  call    ??1?$ActivityData@VPropsysTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPropsysTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PropsysTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<PropsysTelemetry,_TlgReflectorTag_Param0IsProviderType>(void)
0x180037df6  nop
0x180037df7  test    r14, r14
0x180037dfa  jz      short loc_180037E44
0x180037dfc  mov     rcx, r14; pv
0x180037dff  call    cs:__imp_CoTaskMemFree
0x180037e05  jmp     short loc_180037E44
0x180037e07  lea     r15, [rbx+0C8h]
0x180037e0e  mov     [r15], eax
0x180037e11  mov     dword ptr [rsp+200h+var_1C0], esi
0x180037e15  lea     rdx, [rsp+200h+var_1C0]
0x180037e1a  mov     rcx, [rdi]
0x180037e1d  call    ?RefreshIfNeeded@?$CCachedData@UGLOBAL_MAPPING_HEADER@@VCGlobalMappingData@@@@QEAAJPEAH@Z; CCachedData<GLOBAL_MAPPING_HEADER,CGlobalMappingData>::RefreshIfNeeded(int *)
0x180037e22  mov     r12d, eax
0x180037e25  test    eax, eax
0x180037e27  js      loc_180038159
0x180037e2d  mov     r13d, dword ptr [rsp+200h+var_1C0]
0x180037e32  test    r13d, r13d
0x180037e35  jnz     loc_180037ED3
0x180037e3b  test    r12d, r12d
0x180037e3e  js      loc_180037CBA
0x180037e44  mov     eax, r12d
0x180037e47  mov     rcx, [rbp+100h+var_50]
0x180037e4e  xor     rcx, rsp; StackCookie
0x180037e51  call    __security_check_cookie
0x180037e56  add     rsp, 1C8h
0x180037e5d  pop     r15
0x180037e5f  pop     r14
0x180037e61  pop     r13
0x180037e63  pop     r12
0x180037e65  pop     rdi
0x180037e66  pop     rsi
0x180037e67  pop     rbx
0x180037e68  pop     rbp
0x180037e69  retn
0x180037e6a  lea     r12, aUnknown; "Unknown"
0x180037e71  mov     r13, r15
0x180037e74  jmp     loc_180037D48
0x180037e79  cmp     word ptr [r12-2], 5Ch ; '\'
0x180037e80  jnz     loc_180037D0D
0x180037e86  dec     r8
0x180037e89  jmp     loc_180037D0D
0x180037e8e  mov     r9d, eax; char *
0x180037e91  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\propsys\\schemacache"...
0x180037e98  mov     edx, 224h; void *
0x180037e9d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180037ea2  jmp     loc_180037CD8
0x180037ea7  call    cs:__imp_GetTickCount
0x180037ead  xor     esi, esi
0x180037eaf  test    r14d, r14d
0x180037eb2  jnz     loc_180037E07
0x180037eb8  mov     ecx, eax
0x180037eba  sub     ecx, [rbx+0C8h]
0x180037ec0  cmp     ecx, 1388h
0x180037ec6  ja      loc_180037E07
0x180037ecc  mov     eax, esi
0x180037ece  jmp     loc_180037E47
0x180037ed3  lea     rdx, ??$s_ReleaseCB@UIPropertyDescription@@@CSchemaCache@@SAXPEAUIPropertyDescription@@@Z; CSchemaCache::s_ReleaseCB<IPropertyDescription>(IPropertyDescription *)
0x180037eda  mov     qword ptr [rsp+200h+var_1B0], rdx
0x180037edf  mov     qword ptr [rsp+200h+var_1B0+8], rsi
0x180037ee4  cmp     dword ptr [rbx+54h], 0
0x180037ee8  jbe     short loc_180037F2F
0x180037eea  mov     r13d, esi
0x180037eed  mov     eax, r13d
0x180037ef0  lea     rcx, ds:0[rax*8]
0x180037ef8  mov     [rsp+200h+lpStringSource], rcx
0x180037efd  mov     rax, [rbx+58h]
0x180037f01  mov     rdi, [rcx+rax]
0x180037f05  test    rdi, rdi
0x180037f08  jnz     loc_180038010
0x180037f0e  mov     rax, [rbx+58h]
0x180037f12  mov     [rcx+rax], rsi
0x180037f16  inc     r13d
0x180037f19  cmp     r13d, [rbx+54h]
0x180037f1d  jb      short loc_180037EED
0x180037f1f  lea     rdi, [rbx+18h]
0x180037f23  mov     r13d, dword ptr [rsp+200h+var_1C0]
0x180037f28  lea     rdx, ??$s_ReleaseCB@UIPropertyDescription@@@CSchemaCache@@SAXPEAUIPropertyDescription@@@Z; CSchemaCache::s_ReleaseCB<IPropertyDescription>(IPropertyDescription *)
0x180037f2f  mov     [rbx+50h], esi
0x180037f32  mov     qword ptr [rsp+200h+var_1B0], rdx
0x180037f37  mov     qword ptr [rsp+200h+var_1B0+8], rsi
0x180037f3c  cmp     dword ptr [rbx+7Ch], 0
0x180037f40  jbe     short loc_180037F82
0x180037f42  mov     edi, esi
0x180037f44  mov     eax, edi
0x180037f46  lea     rcx, ds:0[rax*8]
0x180037f4e  mov     [rsp+200h+lpStringSource], rcx
0x180037f53  mov     rax, [rbx+80h]
0x180037f5a  mov     r13, [rcx+rax]
0x180037f5e  test    r13, r13
0x180037f61  jnz     loc_180038040
0x180037f67  mov     rax, [rbx+80h]
0x180037f6e  mov     [rcx+rax], rsi
0x180037f72  inc     edi
0x180037f74  cmp     edi, [rbx+7Ch]
0x180037f77  jb      short loc_180037F44
0x180037f79  lea     rdi, [rbx+18h]
0x180037f7d  mov     r13d, dword ptr [rsp+200h+var_1C0]
0x180037f82  mov     [rbx+78h], esi
0x180037f85  lea     rax, ??$s_ReleaseCB@UIPropertyDescription@@@CSchemaCache@@SAXPEAUIPropertyDescription@@@Z; CSchemaCache::s_ReleaseCB<IPropertyDescription>(IPropertyDescription *)
0x180037f8c  mov     qword ptr [rsp+200h+var_1B0], rax
0x180037f91  mov     qword ptr [rsp+200h+var_1B0+8], rsi
0x180037f96  cmp     dword ptr [rbx+0A4h], 0
0x180037f9d  jbe     short loc_180037FE6
0x180037f9f  mov     r13d, esi
0x180037fa2  mov     eax, r13d
0x180037fa5  lea     rcx, ds:0[rax*8]
0x180037fad  mov     [rsp+200h+lpStringSource], rcx
0x180037fb2  mov     rax, [rbx+0A8h]
0x180037fb9  mov     rdi, [rcx+rax]
0x180037fbd  test    rdi, rdi
0x180037fc0  jnz     loc_180038080
0x180037fc6  mov     rax, [rbx+0A8h]
0x180037fcd  mov     [rcx+rax], rsi
0x180037fd1  inc     r13d
0x180037fd4  cmp     r13d, [rbx+0A4h]
0x180037fdb  jb      short loc_180037FA2
0x180037fdd  lea     rdi, [rbx+18h]
0x180037fe1  mov     r13d, dword ptr [rsp+200h+var_1C0]
0x180037fe6  mov     [rbx+0A0h], esi
0x180037fec  lea     rcx, [rbx+0C0h]
0x180037ff3  call    ??$SafeRelease@UIShellFolder2@@@@YAXPEAPEAUIShellFolder2@@@Z; SafeRelease<IShellFolder2>(IShellFolder2 * *)
0x180037ff8  test    r13d, r13d
0x180037ffb  jz      loc_180037E3B
0x180038001  mov     rcx, rbx; this
0x180038004  call    ?_RefreshCachedSchemas@CSchemaCache@@AEAAXXZ; CSchemaCache::_RefreshCachedSchemas(void)
0x180038009  jmp     loc_180037E3B
0x180038010  mov     ecx, [rbx+64h]
0x180038013  add     rcx, rdi; unsigned __int8 *
0x180038016  lea     r8, [rsp+200h+var_1B0]; void *
0x18003801b  mov     edx, [rbx+60h]; unsigned int
0x18003801e  call    ?s_DestroyCallback@?$CHashTable@VCSchemaData@@U_GUID@@@@CAXPEAEIPEAX@Z; CHashTable<CSchemaData,_GUID>::s_DestroyCallback(uchar *,uint,void *)
0x180038023  mov     rcx, rdi; hMem
0x180038026  mov     rdi, [rdi]
0x180038029  call    cs:__imp_LocalFree
0x18003802f  test    rdi, rdi
0x180038032  jnz     short loc_180038010
0x180038034  mov     rcx, [rsp+200h+lpStringSource]
0x180038039  jmp     loc_180037F0E
0x180038040  mov     ecx, [rbx+8Ch]
0x180038046  add     rcx, r13; unsigned __int8 *
0x180038049  lea     r8, [rsp+200h+var_1B0]; void *
0x18003804e  mov     edx, [rbx+88h]; unsigned int
0x180038054  call    ?s_DestroyCallback@?$CHashTable@VCSchemaData@@U_GUID@@@@CAXPEAEIPEAX@Z; CHashTable<CSchemaData,_GUID>::s_DestroyCallback(uchar *,uint,void *)
0x180038059  mov     rcx, r13; hMem
0x18003805c  mov     r13, [r13+0]
0x180038060  call    cs:__imp_LocalFree
0x180038066  test    r13, r13
0x180038069  jnz     short loc_180038040
0x18003806b  mov     rcx, [rsp+200h+lpStringSource]
0x180038070  jmp     loc_180037F67
0x180038080  mov     ecx, [rbx+0B4h]
0x180038086  add     rcx, rdi; unsigned __int8 *
0x180038089  lea     r8, [rsp+200h+var_1B0]; void *
0x18003808e  mov     edx, [rbx+0B0h]; unsigned int
0x180038094  call    ?s_DestroyCallback@?$CHashTable@VCSchemaData@@U_GUID@@@@CAXPEAEIPEAX@Z; CHashTable<CSchemaData,_GUID>::s_DestroyCallback(uchar *,uint,void *)
0x180038099  mov     rcx, rdi; hMem
0x18003809c  mov     rdi, [rdi]
0x18003809f  call    cs:__imp_LocalFree
0x1800380a5  test    rdi, rdi
0x1800380a8  jnz     short loc_180038080
0x1800380aa  mov     rcx, [rsp+200h+lpStringSource]
0x1800380af  jmp     loc_180037FC6
0x1800380b4  mov     [rsp+200h+var_1C0], rsi
0x1800380b9  lea     r8, [rsp+200h+var_1C0]; struct IMemoryMappedCache **
0x1800380be  xor     edx, edx; int *
0x1800380c0  mov     rcx, rbx; this
0x1800380c3  call    ?_BuildGlobalMapping@CSchemaCache@@AEAAJPEAHPEAPEAUIMemoryMappedCache@@@Z; CSchemaCache::_BuildGlobalMapping(int *,IMemoryMappedCache * *)
0x1800380c8  mov     r12d, eax
0x1800380cb  mov     rcx, [rbp+108h]; this
0x1800380d2  test    eax, eax
0x1800380d4  js      loc_18003816B
0x1800380da  setz    sil
0x1800380de  mov     [rsp+200h+var_1CC], esi
0x1800380e2  lea     rdx, [rsp+200h+var_1CC]
0x1800380e7  lea     rcx, [rsp+200h+var_1A0]
0x1800380ec  call    ??$RebuiltGlobalMapping@AEAH@SchemaCacheGlobalMappingLoad@PropsysTelemetry@@QEAAXAEAH@Z; PropsysTelemetry::SchemaCacheGlobalMappingLoad::RebuiltGlobalMapping<int &>(int &)
0x1800380f1  movups  xmm0, cs:CACHEID_GlobalMapping
0x1800380f8  movaps  [rsp+200h+var_1B0], xmm0
0x1800380fd  mov     qword ptr [rsp+200h+cchValue], rdi; int
0x180038102  mov     r9d, esi
0x180038105  mov     r8, [rsp+200h+var_1C0]
0x18003810a  lea     rdx, [rsp+200h+var_1B0]
0x18003810f  mov     rcx, [rbx+10h]; punk
0x180038113  call    ?CreateInstance@?$CCachedData@UGLOBAL_MAPPING_HEADER@@VCGlobalMappingData@@@@SAJPEAUIMemoryMappedCacheMgr@@U_GUID@@PEAUIMemoryMappedCache@@HPEAPEAVCGlobalMappingData@@@Z; CCachedData<GLOBAL_MAPPING_HEADER,CGlobalMappingData>::CreateInstance(IMemoryMappedCacheMgr *,_GUID,IMemoryMappedCache *,int,CGlobalMappingData * *)
0x180038118  mov     r12d, eax
0x18003811b  mov     rcx, [rbp+108h]; this
0x180038122  test    eax, eax
0x180038124  jns     short loc_18003813A
0x180038126  mov     r9d, eax; char *
0x180038129  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\propsys\\schemacache"...
0x180038130  mov     edx, 234h; void *
0x180038135  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003813a  mov     rcx, [rsp+200h+var_1C0]
0x18003813f  mov     rax, [rcx]
0x180038142  mov     rax, [rax+10h]
0x180038146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003814b  test    r12d, r12d
0x18003814e  js      loc_180037DB1
0x180038154  jmp     loc_180037DA8
0x180038159  mov     rcx, rdi
0x18003815c  call    ??$SafeRelease@UIShellFolder2@@@@YAXPEAPEAUIShellFolder2@@@Z; SafeRelease<IShellFolder2>(IShellFolder2 * *)
0x180038161  mov     r13d, dword ptr [rsp+200h+var_1C0]
0x180038166  jmp     loc_180037ED3
0x18003816b  mov     r9d, eax; char *
0x18003816e  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\propsys\\schemacache"...
0x180038175  mov     edx, 22Ch; void *
0x18003817a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003817f  jmp     loc_180037DB1
0x180038184  lea     rcx, [rbp+100h+var_80]; this
0x18003818b  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180038190  jmp     loc_180037DE3
```
