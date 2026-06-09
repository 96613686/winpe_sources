# CSchemaCache::GetPropertyDescriptionByKey(_tagpropertykey const &,_GUID const &,void * *)

- ea: `0x1800362d0`
- end: `0x18003710a`
- name: `?GetPropertyDescriptionByKey@CSchemaCache@@UEAAJAEBU_tagpropertykey@@AEBU_GUID@@PEAPEAX@Z`
- size: `3642`
- prototype: `__int64 __fastcall(CSchemaCache *__hidden this, const struct _tagpropertykey *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `26`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003898`
- `0x180017970`
- `0x18001c4fc`
- `0x18002f9e0`
- `0x180034c10`
- `0x1800359b8`
- `0x180035a14`
- `0x180036094`
- `0x1800362d0`
- `0x180037c70`
- `0x18003820c`
- `0x18003850c`
- `0x180039230`
- `0x1800396ac`
- `0x180039a10`
- `0x180039ad8`
- `0x180039c40`
- `0x180039cd0`
- `0x180063900`
- `0x18006ed20`
- `0x18006fb80`
- `0x18008f890`
- `0x180091d78`
- `0x1800920ec`
- `0x1800921e8`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800363a7`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800363a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036473`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036473`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036319`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036319`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036d23`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036d23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036f49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036f7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036fbf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036f49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036f7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036fbf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180036409`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180036cec`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180036409`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180036cec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800364bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800364bb`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18003697c`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18003697c`

## string_xrefs

- `0x1800364d9`: `onecoreuap\shell\propsys\schemacache.cpp`
- `0x180037050`: `onecoreuap\shell\propsys\schemacache.cpp`
- `0x180037094`: `onecoreuap\shell\propsys\schemacache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSchemaCache::GetPropertyDescriptionByKey(
        CSchemaCache *this,
        const struct _tagpropertykey *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v7; // rdx
  __int64 v8; // rcx
  CGlobalMappingData **v9; // r13
  int v10; // eax
  WCHAR *v11; // rsi
  __int64 v12; // r8
  const wchar_t *v13; // rbx
  int StringOrdinal; // eax
  int SchemaIdForPropertyByKey; // r15d
  int refreshed; // ebx
  int v18; // esi
  unsigned int v19; // r9d
  __int64 (__fastcall *v20)(const struct _tagpropertykey *, __int64, _QWORD); // rax
  unsigned int v21; // edx
  unsigned int v22; // ecx
  unsigned int v23; // edx
  unsigned int v24; // ecx
  unsigned int v25; // edx
  unsigned int v26; // ecx
  unsigned int v27; // edx
  unsigned int v28; // ecx
  unsigned int v29; // edx
  unsigned int v30; // ecx
  unsigned int v31; // edx
  unsigned int v32; // ecx
  unsigned int v33; // edx
  unsigned int v34; // ecx
  unsigned int v35; // edx
  unsigned int v36; // ecx
  unsigned int v37; // edx
  unsigned int v38; // r8d
  unsigned int v39; // eax
  __int64 *v40; // rdx
  __int64 v41; // rcx
  unsigned __int64 v42; // rax
  IUnknown v43; // rdx
  unsigned __int64 v44; // r8
  struct IMemoryMappedCache *v45; // r13
  __int64 v46; // r10
  __int64 v47; // rbx
  unsigned __int64 v48; // r10
  unsigned __int64 v49; // rcx
  __int64 v50; // r11
  __int64 v51; // rax
  __int64 v52; // rax
  IUnknown *v53; // rcx
  unsigned __int64 v54; // r9
  DWORD pid; // r9d
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // rdx
  __int64 v59; // rcx
  struct IMemoryMappedCache *v60; // r15
  struct IMemoryMappedCache *v61; // rbx
  unsigned int v62; // r9d
  unsigned int (__fastcall *v63)(const struct _tagpropertykey *, __int64, _QWORD); // rax
  unsigned int v64; // edx
  unsigned int v65; // ecx
  unsigned int v66; // edx
  unsigned int v67; // ecx
  unsigned int v68; // edx
  unsigned int v69; // ecx
  unsigned int v70; // edx
  unsigned int v71; // ecx
  unsigned int v72; // edx
  unsigned int v73; // ecx
  unsigned int v74; // edx
  unsigned int v75; // ecx
  unsigned int v76; // edx
  unsigned int v77; // ecx
  unsigned int v78; // edx
  unsigned int v79; // ecx
  unsigned int v80; // edx
  unsigned int v81; // r8d
  __int64 v82; // rbx
  __int64 v83; // rax
  unsigned __int64 v84; // rcx
  DWORD TickCount; // eax
  const WCHAR *v86; // rax
  __int64 v87; // rdx
  LPCWSTR v88; // rcx
  unsigned int v89; // esi
  const WCHAR *v90; // rcx
  unsigned __int8 *v91; // r15
  unsigned int v92; // r13d
  const WCHAR *v93; // rcx
  unsigned __int8 *v94; // r15
  unsigned int v95; // r13d
  const WCHAR *v96; // rcx
  unsigned __int8 *v97; // r15
  unsigned __int8 *v98; // rcx
  unsigned __int8 *v99; // rcx
  unsigned __int8 *v100; // rcx
  int v101; // eax
  int Instance; // eax
  int cchValue; // [rsp+20h] [rbp-E0h]
  int cchValuea; // [rsp+20h] [rbp-E0h]
  int cchValueb; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpStringSource; // [rsp+38h] [rbp-C8h] BYREF
  IUnknown *punk; // [rsp+40h] [rbp-C0h] BYREF
  const struct _GUID *v108; // [rsp+48h] [rbp-B8h]
  IUnknown *v109; // [rsp+50h] [rbp-B0h] BYREF
  struct IMemoryMappedCache *v110; // [rsp+58h] [rbp-A8h] BYREF
  struct _GUID v111; // [rsp+60h] [rbp-A0h] BYREF
  void **v112; // [rsp+70h] [rbp-90h] BYREF
  char v113[272]; // [rsp+78h] [rbp-88h] BYREF
  char v114[8]; // [rsp+188h] [rbp+88h] BYREF
  char v115[24]; // [rsp+190h] [rbp+90h] BYREF
  int v116; // [rsp+1A8h] [rbp+A8h]
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v108 = a3;
  *a4 = 0;
  EnterCriticalSection(&CSchemaCache::s_critsec);
  v9 = (CGlobalMappingData **)((char *)this + 24);
  if ( *((_QWORD *)this + 3) )
  {
    TickCount = GetTickCount();
    if ( TickCount - *((_DWORD *)this + 50) <= 0x1388 )
      goto LABEL_26;
    *((_DWORD *)this + 50) = TickCount;
    LODWORD(v110) = 0;
    refreshed = CCachedData<GLOBAL_MAPPING_HEADER,CGlobalMappingData>::RefreshIfNeeded(*v9, &v110);
    if ( refreshed < 0 )
    {
      SafeRelease<IShellFolder2>((char *)this + 24);
      v18 = (int)v110;
    }
    else
    {
      v18 = (int)v110;
      if ( !(_DWORD)v110 )
        goto LABEL_25;
    }
    *(_QWORD *)&v111.Data1 = CSchemaCache::s_ReleaseCB<IPropertyDescription>;
    *(_QWORD *)v111.Data4 = 0;
    LODWORD(v109) = 0;
    if ( *((_DWORD *)this + 21) )
    {
      v89 = (unsigned int)v109;
      do
      {
        v90 = (const WCHAR *)(8LL * v89);
        lpStringSource = v90;
        v91 = *(unsigned __int8 **)((char *)v90 + *((_QWORD *)this + 11));
        if ( v91 )
        {
          do
          {
            CHashTable<CSchemaData,_GUID>::s_DestroyCallback(
              &v91[*((unsigned int *)this + 25)],
              *((_DWORD *)this + 24),
              &v111);
            v98 = v91;
            v91 = *(unsigned __int8 **)v91;
            LocalFree(v98);
          }
          while ( v91 );
          v90 = lpStringSource;
        }
        *(_QWORD *)((char *)v90 + *((_QWORD *)this + 11)) = 0;
        ++v89;
      }
      while ( v89 < *((_DWORD *)this + 21) );
      v18 = (int)v110;
    }
    *((_DWORD *)this + 20) = 0;
    *(_QWORD *)&v111.Data1 = CSchemaCache::s_ReleaseCB<IPropertyDescription>;
    *(_QWORD *)v111.Data4 = 0;
    LODWORD(v109) = 0;
    if ( *((_DWORD *)this + 31) )
    {
      v92 = (unsigned int)v109;
      do
      {
        v93 = (const WCHAR *)(8LL * v92);
        lpStringSource = v93;
        v94 = *(unsigned __int8 **)((char *)v93 + *((_QWORD *)this + 16));
        if ( v94 )
        {
          do
          {
            CHashTable<CSchemaData,_GUID>::s_DestroyCallback(
              &v94[*((unsigned int *)this + 35)],
              *((_DWORD *)this + 34),
              &v111);
            v99 = v94;
            v94 = *(unsigned __int8 **)v94;
            LocalFree(v99);
          }
          while ( v94 );
          v93 = lpStringSource;
        }
        *(_QWORD *)((char *)v93 + *((_QWORD *)this + 16)) = 0;
        ++v92;
      }
      while ( v92 < *((_DWORD *)this + 31) );
      v9 = (CGlobalMappingData **)((char *)this + 24);
    }
    *((_DWORD *)this + 30) = 0;
    *(_QWORD *)&v111.Data1 = CSchemaCache::s_ReleaseCB<IPropertyDescription>;
    *(_QWORD *)v111.Data4 = 0;
    LODWORD(v109) = 0;
    if ( *((_DWORD *)this + 41) )
    {
      v95 = (unsigned int)v109;
      do
      {
        v96 = (const WCHAR *)(8LL * v95);
        lpStringSource = v96;
        v97 = *(unsigned __int8 **)((char *)v96 + *((_QWORD *)this + 21));
        if ( v97 )
        {
          do
          {
            CHashTable<CSchemaData,_GUID>::s_DestroyCallback(
              &v97[*((unsigned int *)this + 45)],
              *((_DWORD *)this + 44),
              &v111);
            v100 = v97;
            v97 = *(unsigned __int8 **)v97;
            LocalFree(v100);
          }
          while ( v97 );
          v96 = lpStringSource;
        }
        *(_QWORD *)((char *)v96 + *((_QWORD *)this + 21)) = 0;
        ++v95;
      }
      while ( v95 < *((_DWORD *)this + 41) );
      v9 = (CGlobalMappingData **)((char *)this + 24);
    }
    *((_DWORD *)this + 40) = 0;
    SafeRelease<IShellFolder2>((char *)this + 192);
    if ( v18 )
      CSchemaCache::_RefreshCachedSchemas(this);
LABEL_25:
    if ( refreshed < 0 )
      goto LABEL_2;
LABEL_26:
    v109 = 0;
    if ( *((_QWORD *)this + 16) )
    {
      v19 = *((_DWORD *)this + 31);
      v20 = (__int64 (__fastcall *)(const struct _tagpropertykey *, __int64, _QWORD))*((_QWORD *)this + 14);
      if ( v20 )
      {
        v39 = v20(a2, 20, v19);
      }
      else
      {
        _mm_lfence();
        v21 = (LOBYTE(a2->fmtid.Data1) + 694790345)
            ^ 0x12B9B0A5
            ^ ((((LOBYTE(a2->fmtid.Data1) + 694790345) ^ 0x12B9B0A5u) >> 2)
             + 2080 * ((LOBYTE(a2->fmtid.Data1) + 694790345) ^ 0x12B9B0A5)
             + BYTE1(a2->fmtid.Data1));
        v22 = v21 ^ ((v21 >> 2) + 2080 * v21 + BYTE2(a2->fmtid.Data1));
        v23 = v22 ^ ((v22 >> 2) + 2080 * v22 + HIBYTE(a2->fmtid.Data1));
        v24 = v23 ^ ((v23 >> 2) + 2080 * v23 + LOBYTE(a2->fmtid.Data2));
        v25 = v24 ^ ((v24 >> 2) + 2080 * v24 + HIBYTE(a2->fmtid.Data2));
        v26 = v25 ^ ((v25 >> 2) + 2080 * v25 + LOBYTE(a2->fmtid.Data3));
        v27 = v26 ^ ((v26 >> 2) + 2080 * v26 + HIBYTE(a2->fmtid.Data3));
        v28 = v27 ^ ((v27 >> 2) + 2080 * v27 + a2->fmtid.Data4[0]);
        v29 = v28 ^ ((v28 >> 2) + 2080 * v28 + a2->fmtid.Data4[1]);
        v30 = v29 ^ ((v29 >> 2) + 2080 * v29 + a2->fmtid.Data4[2]);
        v31 = v30 ^ ((v30 >> 2) + 2080 * v30 + a2->fmtid.Data4[3]);
        v32 = v31 ^ ((v31 >> 2) + 2080 * v31 + a2->fmtid.Data4[4]);
        v33 = v32 ^ ((v32 >> 2) + 2080 * v32 + a2->fmtid.Data4[5]);
        v34 = v33 ^ ((v33 >> 2) + 2080 * v33 + a2->fmtid.Data4[6]);
        v35 = v34 ^ ((v34 >> 2) + 2080 * v34 + a2->fmtid.Data4[7]);
        v36 = v35 ^ ((v35 >> 2) + 2080 * v35 + LOBYTE(a2->pid));
        v37 = v36 ^ ((v36 >> 2) + 2080 * v36 + BYTE1(a2->pid));
        v38 = v37 ^ ((v37 >> 2) + 2080 * v37 + BYTE2(a2->pid));
        v39 = ((v38 ^ ((v38 >> 2) + 2080 * v38 + HIBYTE(a2->pid))) & 0x7FFFFFFF) % v19;
      }
      v40 = *(__int64 **)(*((_QWORD *)this + 16) + 8LL * v39);
      if ( v40 )
      {
        while ( 1 )
        {
          if ( *((_DWORD *)v40 + 2) == 20 )
          {
            v41 = *((unsigned int *)this + 36);
            v42 = *(_QWORD *)&a2->fmtid.Data1 - *(__int64 *)((char *)v40 + v41);
            if ( *(_QWORD *)&a2->fmtid.Data1 == *(__int64 *)((char *)v40 + v41) )
            {
              v42 = *(_QWORD *)a2->fmtid.Data4 - *(__int64 *)((char *)v40 + v41 + 8);
              if ( !v42 )
                v42 = a2->pid - (unsigned __int64)*(unsigned int *)((char *)v40 + v41 + 16);
            }
            if ( !v42 )
              break;
          }
          v40 = (__int64 *)*v40;
          if ( !v40 )
            goto LABEL_36;
        }
        if ( *((_DWORD *)this + 34) == 8 )
        {
          v109 = *(IUnknown **)((char *)v40 + *((unsigned int *)this + 35));
          ((void (__fastcall *)(IUnknown *))v109->lpVtbl->AddRef)(v109);
          goto LABEL_51;
        }
      }
    }
LABEL_36:
    v110 = 0;
    SchemaIdForPropertyByKey = CSchemaCache::_EnsureGlobalMappingLoaded(this, 0);
    if ( SchemaIdForPropertyByKey >= 0 )
    {
      v111 = 0;
      SchemaIdForPropertyByKey = CGlobalMappingData::GetSchemaIdForPropertyByKey(*v9, a2, &v111);
      if ( SchemaIdForPropertyByKey >= 0 )
      {
        SchemaIdForPropertyByKey = CSchemaCache::_EnsureSchemaLoadedWithCacheItem(this, &v111, 0, 1, &v110);
        if ( SchemaIdForPropertyByKey < 0 )
        {
          SchemaIdForPropertyByKey = CSchemaCache::_ForceRebuildGlobalMapping(this, (int)v43.lpVtbl, 0);
          if ( SchemaIdForPropertyByKey >= 0 )
            SchemaIdForPropertyByKey = CSchemaCache::_EnsureSchemaLoadedWithCacheItem(this, &v111, 0, 1, &v110);
        }
        if ( SchemaIdForPropertyByKey < 0 )
          goto LABEL_52;
        v45 = v110;
        v46 = *((_QWORD *)v110 + 11);
        if ( v46 )
        {
          v47 = *((_QWORD *)v110 + 2);
          v44 = 0;
          v48 = v46 - 1;
          SchemaIdForPropertyByKey = 0;
          while ( 1 )
          {
            if ( SchemaIdForPropertyByKey < 0 )
              goto LABEL_88;
            v49 = (v48 + v44) >> 1;
            v50 = *((_QWORD *)v110 + 10);
            v51 = *(unsigned int *)(v50 + 4 * v49);
            v52 = (_DWORD)v51 == -1 ? 0LL : v47 + v51;
            v43.lpVtbl = *(struct IUnknownVtbl **)&a2->fmtid.Data1;
            if ( *(_QWORD *)(v52 + 36) >= *(_QWORD *)&a2->fmtid.Data1 )
            {
              if ( *(_QWORD *)(v52 + 36) > *(_QWORD *)&a2->fmtid.Data1 )
                goto LABEL_47;
              v54 = *(_QWORD *)(v52 + 44);
              if ( v54 >= *(_QWORD *)a2->fmtid.Data4 )
              {
                if ( v54 > *(_QWORD *)a2->fmtid.Data4 )
                  goto LABEL_47;
                pid = a2->pid;
                if ( *(_DWORD *)(v52 + 52) >= pid )
                  break;
              }
            }
            v44 = v49 + 1;
LABEL_58:
            if ( v48 < v44 )
              SchemaIdForPropertyByKey = -2147319765;
          }
          if ( *(_DWORD *)(v52 + 52) <= pid )
          {
            for ( ; v49; --v49 )
            {
              v56 = *(unsigned int *)(v50 + 4 * v49 - 4);
              if ( (_DWORD)v56 == -1 )
                v57 = 0;
              else
                v57 = v47 + v56;
              if ( *(_QWORD *)(v57 + 36) < (unsigned __int64)v43.lpVtbl )
                break;
              if ( *(_QWORD *)(v57 + 36) > (unsigned __int64)v43.lpVtbl )
                break;
              v44 = *(_QWORD *)(v57 + 44);
              if ( v44 < *(_QWORD *)a2->fmtid.Data4 )
                break;
              if ( v44 > *(_QWORD *)a2->fmtid.Data4 )
                break;
              if ( *(_DWORD *)(v57 + 52) < pid )
                break;
              if ( *(_DWORD *)(v57 + 52) > pid )
                break;
            }
            v58 = *(unsigned int *)(v50 + 4 * v49);
            if ( (_DWORD)v58 == -1 )
              v59 = 0;
            else
              v59 = v47 + v58;
            lpStringSource = (LPCWSTR)v59;
            v43.lpVtbl = (struct IUnknownVtbl *)*((_QWORD *)v110 + 7);
            punk = (IUnknown *)v43.lpVtbl;
            v111.Data1 = 1;
            *(_DWORD *)&v111.Data2 = *(_DWORD *)(v59 + 112);
            *(_DWORD *)v111.Data4 = *(_DWORD *)(v59 + 104);
            v109 = 0;
            SchemaIdForPropertyByKey = -2147024809;
            if ( v43.lpVtbl )
            {
              v110 = 0;
              SchemaIdForPropertyByKey = CTRefBase<CPropertyDescription,IPropertyDescription,CTRefBase_DllModuleLifetimePolicy>::Create(&v110);
              if ( SchemaIdForPropertyByKey >= 0 )
              {
                v60 = v110;
                IUnknown_Set((IUnknown **)v110 + 3, punk);
                *((_QWORD *)v60 + 5) = lpStringSource;
                v61 = v60;
                SchemaIdForPropertyByKey = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v60 + 3) + 32LL))(
                                             *((_QWORD *)v60 + 3),
                                             (__int64)v60 + 32);
                if ( SchemaIdForPropertyByKey >= 0 )
                {
                  SchemaIdForPropertyByKey = (*(__int64 (__fastcall **)(struct IMemoryMappedCache *, struct _GUID *))(*(_QWORD *)v61 + 208LL))(
                                               v61,
                                               &v111);
                  if ( SchemaIdForPropertyByKey >= 0 )
                    SchemaIdForPropertyByKey = (**(__int64 (__fastcall ***)(struct IMemoryMappedCache *, GUID *, IUnknown **))v61)(
                                                 v61,
                                                 &GUID_6f79d558_3e96_4549_a1d1_7d75d2288814,
                                                 &v109);
                }
                (*(void (__fastcall **)(struct IMemoryMappedCache *))(*(_QWORD *)v61 + 16LL))(v61);
              }
            }
            if ( SchemaIdForPropertyByKey >= 0 )
            {
              punk = v109;
              if ( *((_QWORD *)this + 16) )
              {
                v62 = *((_DWORD *)this + 31);
                v63 = (unsigned int (__fastcall *)(const struct _tagpropertykey *, __int64, _QWORD))*((_QWORD *)this + 14);
                if ( v63 )
                {
                  v44 = v63(a2, 20, v62);
                }
                else
                {
                  _mm_lfence();
                  v64 = (LOBYTE(a2->fmtid.Data1) + 694790345)
                      ^ 0x12B9B0A5
                      ^ ((((LOBYTE(a2->fmtid.Data1) + 694790345) ^ 0x12B9B0A5u) >> 2)
                       + 2080 * ((LOBYTE(a2->fmtid.Data1) + 694790345) ^ 0x12B9B0A5)
                       + BYTE1(a2->fmtid.Data1));
                  v65 = v64 ^ ((v64 >> 2) + 2080 * v64 + BYTE2(a2->fmtid.Data1));
                  v66 = v65 ^ ((v65 >> 2) + 2080 * v65 + HIBYTE(a2->fmtid.Data1));
                  v67 = v66 ^ ((v66 >> 2) + 2080 * v66 + LOBYTE(a2->fmtid.Data2));
                  v68 = v67 ^ ((v67 >> 2) + 2080 * v67 + HIBYTE(a2->fmtid.Data2));
                  v69 = v68 ^ ((v68 >> 2) + 2080 * v68 + LOBYTE(a2->fmtid.Data3));
                  v70 = v69 ^ ((v69 >> 2) + 2080 * v69 + HIBYTE(a2->fmtid.Data3));
                  v71 = v70 ^ (a2->fmtid.Data4[0] + (v70 >> 2) + 2080 * v70);
                  v72 = v71 ^ ((v71 >> 2) + 2080 * v71 + a2->fmtid.Data4[1]);
                  v73 = v72 ^ ((v72 >> 2) + 2080 * v72 + a2->fmtid.Data4[2]);
                  v74 = v73 ^ ((v73 >> 2) + 2080 * v73 + a2->fmtid.Data4[3]);
                  v75 = v74 ^ ((v74 >> 2) + 2080 * v74 + a2->fmtid.Data4[4]);
                  v76 = v75 ^ ((v75 >> 2) + 2080 * v75 + a2->fmtid.Data4[5]);
                  v77 = v76 ^ ((v76 >> 2) + 2080 * v76 + a2->fmtid.Data4[6]);
                  v78 = v77 ^ ((v77 >> 2) + 2080 * v77 + a2->fmtid.Data4[7]);
                  v79 = v78 ^ (LOBYTE(a2->pid) + (v78 >> 2) + 2080 * v78);
                  v80 = v79 ^ ((v79 >> 2) + 2080 * v79 + BYTE1(a2->pid));
                  v81 = v80 ^ ((v80 >> 2) + 2080 * v80 + BYTE2(a2->pid));
                  v44 = ((v81 ^ ((v81 >> 2) + 2080 * v81 + HIBYTE(a2->pid))) & 0x7FFFFFFF) % v62;
                }
                v82 = 8LL * (unsigned int)v44;
                v43.lpVtbl = *(struct IUnknownVtbl **)(v82 + *((_QWORD *)this + 16));
                if ( !v43.lpVtbl )
                  goto LABEL_144;
                do
                {
                  if ( LODWORD(v43.lpVtbl->AddRef) == 20 )
                  {
                    v83 = *((unsigned int *)this + 36);
                    v84 = *(_QWORD *)&a2->fmtid.Data1 - *(unsigned __int64 *)((char *)&v43.lpVtbl->QueryInterface + v83);
                    if ( *(HRESULT (__stdcall **)(IUnknown *, const IID *const, void **))&a2->fmtid.Data1 == *(HRESULT (__stdcall **)(IUnknown *, const IID *const, void **))((char *)&v43.lpVtbl->QueryInterface + v83) )
                    {
                      v84 = *(_QWORD *)a2->fmtid.Data4 - *(unsigned __int64 *)((char *)&v43.lpVtbl->AddRef + v83);
                      if ( !v84 )
                        v84 = a2->pid - (unsigned __int64)*(unsigned int *)((char *)&v43.lpVtbl->Release + v83);
                    }
                    if ( !v84 )
                      break;
                  }
                  v43.lpVtbl = (struct IUnknownVtbl *)v43.lpVtbl->QueryInterface;
                }
                while ( v43.lpVtbl );
                if ( !v43.lpVtbl )
                {
LABEL_144:
                  if ( *((_DWORD *)this + 34) == 8 && (unsigned int)v44 < *((_DWORD *)this + 31) )
                  {
                    v86 = (const WCHAR *)LocalAlloc(0x40u, (unsigned int)(*((_DWORD *)this + 36) + 20));
                    lpStringSource = v86;
                    if ( v86 )
                    {
                      *((_DWORD *)v86 + 2) = 20;
                      v87 = *((unsigned int *)this + 36);
                      *(GUID *)((char *)v86 + v87) = a2->fmtid;
                      *(_DWORD *)((char *)v86 + v87 + 16) = a2->pid;
                      memcpy_0((char *)v86 + *((unsigned int *)this + 35), &punk, *((unsigned int *)this + 34));
                      v88 = lpStringSource;
                      *(_QWORD *)lpStringSource = *(_QWORD *)(v82 + *((_QWORD *)this + 16));
                      *(_QWORD *)(v82 + *((_QWORD *)this + 16)) = v88;
                      if ( ++*((_DWORD *)this + 30) > *((_DWORD *)this + 31) )
                        CByteHashTable::_GrowTable((CSchemaCache *)((char *)this + 112));
                      ((void (__fastcall *)(IUnknown *))v109->lpVtbl->AddRef)(v109);
                    }
                  }
                }
              }
            }
            goto LABEL_88;
          }
LABEL_47:
          if ( v49 )
            v48 = v49 - 1;
          else
            SchemaIdForPropertyByKey = -2147319765;
          goto LABEL_58;
        }
        SchemaIdForPropertyByKey = -2147319765;
LABEL_88:
        (*(void (__fastcall **)(struct IMemoryMappedCache *, IUnknown, unsigned __int64))(*(_QWORD *)v45 + 16LL))(
          v45,
          v43,
          v44);
      }
    }
    if ( SchemaIdForPropertyByKey < 0 )
    {
LABEL_52:
      v53 = v109;
      v109 = 0;
      if ( v53 )
        ((void (__fastcall *)(IUnknown *))v53->lpVtbl->Release)(v53);
      goto LABEL_17;
    }
LABEL_51:
    SchemaIdForPropertyByKey = ((__int64 (__fastcall *)(IUnknown *, const struct _GUID *, void **))v109->lpVtbl->QueryInterface)(
                                 v109,
                                 v108,
                                 a4);
    goto LABEL_52;
  }
LABEL_2:
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
  v11 = (WCHAR *)lpStringSource;
  if ( lpStringSource )
  {
    v12 = -1;
    do
      ++v12;
    while ( lpStringSource[v12] );
    v13 = &lpStringSource[v12];
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
  v109 = (IUnknown *)v13;
  PropsysTelemetry::SchemaCacheGlobalMappingLoad::Start<unsigned short const *,bool>((PropsysTelemetry::SchemaCacheGlobalMappingLoad *)&v112);
  v111 = (struct _GUID)CACHEID_GlobalMapping;
  SchemaIdForPropertyByKey = CCachedData<GLOBAL_MAPPING_HEADER,CGlobalMappingData>::CreateInstance(
                               *((IUnknown **)this + 2),
                               (IUnknown **)v9);
  if ( SchemaIdForPropertyByKey >= 0 )
    goto LABEL_11;
  v110 = 0;
  v101 = CSchemaCache::_BuildGlobalMapping((IUnknown **)this, 0, &v110);
  SchemaIdForPropertyByKey = v101;
  if ( v101 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x22C,
      (unsigned int)"onecoreuap\\shell\\propsys\\schemacache.cpp",
      (const char *)(unsigned int)v101,
      cchValuea);
  }
  else
  {
    LODWORD(v109) = v101 == 0;
    PropsysTelemetry::SchemaCacheGlobalMappingLoad::RebuiltGlobalMapping<int &>(&v112, &v109);
    v111 = (struct _GUID)CACHEID_GlobalMapping;
    Instance = CCachedData<GLOBAL_MAPPING_HEADER,CGlobalMappingData>::CreateInstance(
                 *((IUnknown **)this + 2),
                 (IUnknown **)v9);
    SchemaIdForPropertyByKey = Instance;
    if ( Instance < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x234,
        (unsigned int)"onecoreuap\\shell\\propsys\\schemacache.cpp",
        (const char *)(unsigned int)Instance,
        cchValueb);
    (*(void (__fastcall **)(struct IMemoryMappedCache *))(*(_QWORD *)v110 + 16LL))(v110);
    if ( SchemaIdForPropertyByKey >= 0 )
LABEL_11:
      *((_DWORD *)this + 50) = GetTickCount();
  }
  wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    &v112,
    (unsigned int)SchemaIdForPropertyByKey);
  v112 = &PropsysTelemetry::SchemaCacheGlobalMappingLoad::`vftable';
  wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v112);
  if ( v116 )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v115);
  wil::details::shared_object<wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PropsysTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(v114);
  wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PropsysTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<PropsysTelemetry,_TlgReflectorTag_Param0IsProviderType>(v113);
  if ( v11 )
    CoTaskMemFree(v11);
  if ( SchemaIdForPropertyByKey >= 0 )
    goto LABEL_26;
LABEL_17:
  LeaveCriticalSection(&CSchemaCache::s_critsec);
  if ( *((_BYTE *)this + 204) )
  {
    *((_BYTE *)this + 204) = 0;
    _ChangeNotifyHandlers();
  }
  return (unsigned int)SchemaIdForPropertyByKey;
}

```

## disassembly

```asm
0x1800362d0  push    rbp
0x1800362d2  push    rbx
0x1800362d3  push    rsi
0x1800362d4  push    rdi
0x1800362d5  push    r12
0x1800362d7  push    r13
0x1800362d9  push    r14
0x1800362db  push    r15
0x1800362dd  lea     rbp, [rsp-0D8h]
0x1800362e5  sub     rsp, 1D8h
0x1800362ec  mov     rax, cs:__security_cookie
0x1800362f3  xor     rax, rsp
0x1800362f6  mov     [rbp+110h+var_50], rax
0x1800362fd  mov     r12, r9
0x180036300  mov     [rsp+210h+var_1C8], r8
0x180036305  mov     r14, rdx
0x180036308  mov     rdi, rcx
0x18003630b  mov     qword ptr [r9], 0
0x180036312  lea     rcx, ?s_critsec@CSchemaCache@@0VCCritSec@@A; lpCriticalSection
0x180036319  call    cs:__imp_EnterCriticalSection
0x18003631f  lea     r13, [rdi+18h]
0x180036323  cmp     qword ptr [r13+0], 0
0x180036328  jnz     loc_180036CEC
0x18003632e  mov     [rsp+210h+lpStringSource], 0
0x180036337  lea     r8, [rsp+210h+lpStringSource]
0x18003633c  call    ??$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJPEAXPEAUHINSTANCE__@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180036341  mov     rcx, [rbp+118h]; this
0x180036348  test    eax, eax
0x18003634a  js      loc_1800364D6
0x180036350  mov     [rsp+210h+var_1E0], 0
0x180036355  mov     rsi, [rsp+210h+lpStringSource]
0x18003635a  test    rsi, rsi
0x18003635d  jz      loc_1800364AC
0x180036363  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18003636a  nop     word ptr [rax+rax+00h]
0x180036370  inc     r8; cchSource
0x180036373  cmp     word ptr [rsi+r8*2], 0
0x180036379  jnz     short loc_180036370
0x18003637b  lea     rbx, [rsi+r8*2]
0x18003637f  test    r8, r8
0x180036382  jnz     loc_1800364C3
0x180036388  mov     [rsp+210h+bIgnoreCase], 1; bIgnoreCase
0x180036390  mov     [rsp+210h+cchValue], 1; cchValue
0x180036398  lea     r9, asc_1800D17E4; "\\"
0x18003639f  mov     rdx, rsi; lpStringSource
0x1800363a2  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x1800363a7  call    cs:__imp_FindStringOrdinal
0x1800363ad  cmp     eax, 0FFFFFFFFh
0x1800363b0  jz      short loc_1800363BC
0x1800363b2  movsxd  rbx, eax
0x1800363b5  inc     rbx
0x1800363b8  lea     rbx, [rsi+rbx*2]
0x1800363bc  mov     [rsp+210h+var_1C0], rbx
0x1800363c1  lea     r8, [rsp+210h+var_1E0]
0x1800363c6  lea     rdx, [rsp+210h+var_1C0]
0x1800363cb  lea     rcx, [rsp+210h+var_1A0]; this
0x1800363d0  call    ??$Start@PEBG_N@SchemaCacheGlobalMappingLoad@PropsysTelemetry@@SA?AV01@$$QEAPEBG$$QEA_N@Z; PropsysTelemetry::SchemaCacheGlobalMappingLoad::Start<ushort const *,bool>(ushort const * &&,bool &&)
0x1800363d5  nop
0x1800363d6  movups  xmm0, cs:CACHEID_GlobalMapping
0x1800363dd  movaps  xmmword ptr [rsp+210h+var_1B0.Data1], xmm0
0x1800363e2  mov     qword ptr [rsp+210h+cchValue], r13; int
0x1800363e7  mov     r9d, 1
0x1800363ed  xor     r8d, r8d
0x1800363f0  lea     rdx, [rsp+210h+var_1B0]
0x1800363f5  mov     rcx, [rdi+10h]; punk
0x1800363f9  call    ?CreateInstance@?$CCachedData@UGLOBAL_MAPPING_HEADER@@VCGlobalMappingData@@@@SAJPEAUIMemoryMappedCacheMgr@@U_GUID@@PEAUIMemoryMappedCache@@HPEAPEAVCGlobalMappingData@@@Z; CCachedData<GLOBAL_MAPPING_HEADER,CGlobalMappingData>::CreateInstance(IMemoryMappedCacheMgr *,_GUID,IMemoryMappedCache *,int,CGlobalMappingData * *)
0x1800363fe  mov     r15d, eax
0x180036401  test    eax, eax
0x180036403  js      loc_180036FD4
0x180036409  call    cs:__imp_GetTickCount
0x18003640f  mov     [rdi+0C8h], eax
0x180036415  mov     edx, r15d
0x180036418  lea     rcx, [rsp+210h+var_1A0]
0x18003641d  call    ?Stop@?$ActivityBase@VPropsysTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180036422  nop
0x180036423  lea     rax, ??_7SchemaCacheGlobalMappingLoad@PropsysTelemetry@@6B@; const PropsysTelemetry::SchemaCacheGlobalMappingLoad::`vftable'
0x18003642a  mov     [rsp+210h+var_1A0], rax
0x18003642f  lea     rcx, [rsp+210h+var_1A0]
0x180036434  call    ?Destroy@?$ActivityBase@VPropsysTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180036439  nop
0x18003643a  cmp     [rbp+110h+var_68], 0
0x180036441  jnz     loc_1800370AA
0x180036447  lea     rcx, [rbp+110h+var_88]
0x18003644e  call    ?reset@?$shared_object@V?$ActivityData@VPropsysTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPropsysTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PropsysTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180036453  lea     rcx, [rsp+210h+var_198]
0x180036458  call    ??1?$ActivityData@VPropsysTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPropsysTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PropsysTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<PropsysTelemetry,_TlgReflectorTag_Param0IsProviderType>(void)
0x18003645d  nop
0x18003645e  test    rsi, rsi
0x180036461  jnz     short loc_1800364B8
0x180036463  test    r15d, r15d
0x180036466  jns     loc_180036529
0x18003646c  lea     rcx, ?s_critsec@CSchemaCache@@0VCCritSec@@A; lpCriticalSection
0x180036473  call    cs:__imp_LeaveCriticalSection
0x180036479  cmp     byte ptr [rdi+0CCh], 0
0x180036480  jnz     loc_1800370F9
0x180036486  mov     eax, r15d
0x180036489  mov     rcx, [rbp+110h+var_50]
0x180036490  xor     rcx, rsp; StackCookie
0x180036493  call    __security_check_cookie
0x180036498  add     rsp, 1D8h
0x18003649f  pop     r15
0x1800364a1  pop     r14
0x1800364a3  pop     r13
0x1800364a5  pop     r12
0x1800364a7  pop     rdi
0x1800364a8  pop     rsi
0x1800364a9  pop     rbx
0x1800364aa  pop     rbp
0x1800364ab  retn
0x1800364ac  lea     rbx, aUnknown; "Unknown"
0x1800364b3  jmp     loc_1800363BC
0x1800364b8  mov     rcx, rsi; pv
0x1800364bb  call    cs:__imp_CoTaskMemFree
0x1800364c1  jmp     short loc_180036463
0x1800364c3  cmp     word ptr [rbx-2], 5Ch ; '\'
0x1800364c8  jnz     loc_180036388
0x1800364ce  dec     r8
0x1800364d1  jmp     loc_180036388
0x1800364d6  mov     r9d, eax; char *
0x1800364d9  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\propsys\\schemacache"...
0x1800364e0  mov     edx, 224h; void *
0x1800364e5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800364ea  jmp     loc_180036350
0x1800364ef  mov     [rdi+0C8h], eax
0x1800364f5  mov     dword ptr [rsp+210h+var_1B8], 0
0x1800364fd  lea     rdx, [rsp+210h+var_1B8]
0x180036502  mov     rcx, [r13+0]
0x180036506  call    ?RefreshIfNeeded@?$CCachedData@UGLOBAL_MAPPING_HEADER@@VCGlobalMappingData@@@@QEAAJPEAH@Z; CCachedData<GLOBAL_MAPPING_HEADER,CGlobalMappingData>::RefreshIfNeeded(int *)
0x18003650b  mov     ebx, eax
0x18003650d  test    eax, eax
0x18003650f  js      loc_180037080
0x180036515  mov     esi, dword ptr [rsp+210h+var_1B8]
0x180036519  test    esi, esi
0x18003651b  jnz     loc_180036DB8
0x180036521  test    ebx, ebx
0x180036523  js      loc_18003632E
0x180036529  xor     eax, eax
0x18003652b  mov     [rsp+210h+var_1C0], rax
0x180036530  cmp     [rdi+80h], rax
0x180036537  jz      loc_180036762
0x18003653d  mov     r9d, [rdi+7Ch]
0x180036541  mov     rax, [rdi+70h]
0x180036545  test    rax, rax
0x180036548  jnz     loc_180036CAA
0x18003654e  lfence
0x180036551  movzx   ecx, byte ptr [r14]
0x180036555  add     ecx, 2969A8C9h
0x18003655b  xor     ecx, 12B9B0A5h
0x180036561  movzx   edx, byte ptr [r14+1]
0x180036566  imul    eax, ecx, 820h
0x18003656c  add     edx, eax
0x18003656e  mov     eax, ecx
0x180036570  shr     eax, 2
0x180036573  add     edx, eax
0x180036575  xor     edx, ecx
0x180036577  movzx   ecx, byte ptr [r14+2]
0x18003657c  imul    eax, edx, 820h
0x180036582  add     ecx, eax
0x180036584  mov     eax, edx
0x180036586  shr     eax, 2
0x180036589  add     ecx, eax
0x18003658b  xor     ecx, edx
0x18003658d  movzx   edx, byte ptr [r14+3]
0x180036592  imul    eax, ecx, 820h
0x180036598  add     edx, eax
0x18003659a  mov     eax, ecx
0x18003659c  shr     eax, 2
0x18003659f  add     edx, eax
0x1800365a1  xor     edx, ecx
0x1800365a3  movzx   ecx, byte ptr [r14+4]
0x1800365a8  imul    eax, edx, 820h
0x1800365ae  add     ecx, eax
0x1800365b0  mov     eax, edx
0x1800365b2  shr     eax, 2
0x1800365b5  add     ecx, eax
0x1800365b7  xor     ecx, edx
0x1800365b9  movzx   edx, byte ptr [r14+5]
0x1800365be  imul    eax, ecx, 820h
0x1800365c4  add     edx, eax
0x1800365c6  mov     eax, ecx
0x1800365c8  shr     eax, 2
0x1800365cb  add     edx, eax
0x1800365cd  xor     edx, ecx
0x1800365cf  movzx   ecx, byte ptr [r14+6]
0x1800365d4  imul    eax, edx, 820h
0x1800365da  add     ecx, eax
0x1800365dc  mov     eax, edx
0x1800365de  shr     eax, 2
0x1800365e1  add     ecx, eax
0x1800365e3  xor     ecx, edx
0x1800365e5  movzx   edx, byte ptr [r14+7]
0x1800365ea  imul    eax, ecx, 820h
0x1800365f0  add     edx, eax
0x1800365f2  mov     eax, ecx
0x1800365f4  shr     eax, 2
0x1800365f7  add     edx, eax
0x1800365f9  xor     edx, ecx
0x1800365fb  movzx   ecx, byte ptr [r14+8]
0x180036600  imul    eax, edx, 820h
0x180036606  add     ecx, eax
0x180036608  mov     eax, edx
0x18003660a  shr     eax, 2
0x18003660d  add     ecx, eax
0x18003660f  xor     ecx, edx
0x180036611  movzx   edx, byte ptr [r14+9]
0x180036616  imul    eax, ecx, 820h
0x18003661c  add     edx, eax
0x18003661e  mov     eax, ecx
0x180036620  shr     eax, 2
0x180036623  add     edx, eax
0x180036625  xor     edx, ecx
0x180036627  movzx   ecx, byte ptr [r14+0Ah]
0x18003662c  imul    eax, edx, 820h
0x180036632  add     ecx, eax
0x180036634  mov     eax, edx
0x180036636  shr     eax, 2
0x180036639  add     ecx, eax
0x18003663b  xor     ecx, edx
0x18003663d  movzx   edx, byte ptr [r14+0Bh]
0x180036642  imul    eax, ecx, 820h
0x180036648  add     edx, eax
0x18003664a  mov     eax, ecx
0x18003664c  shr     eax, 2
0x18003664f  add     edx, eax
0x180036651  xor     edx, ecx
0x180036653  movzx   ecx, byte ptr [r14+0Ch]
0x180036658  imul    eax, edx, 820h
0x18003665e  add     ecx, eax
0x180036660  mov     eax, edx
0x180036662  shr     eax, 2
0x180036665  add     ecx, eax
0x180036667  xor     ecx, edx
0x180036669  movzx   edx, byte ptr [r14+0Dh]
0x18003666e  imul    eax, ecx, 820h
0x180036674  add     edx, eax
0x180036676  mov     eax, ecx
0x180036678  shr     eax, 2
0x18003667b  add     edx, eax
0x18003667d  xor     edx, ecx
0x18003667f  movzx   ecx, byte ptr [r14+0Eh]
0x180036684  imul    eax, edx, 820h
0x18003668a  add     ecx, eax
0x18003668c  mov     eax, edx
0x18003668e  shr     eax, 2
0x180036691  add     ecx, eax
0x180036693  xor     ecx, edx
0x180036695  movzx   edx, byte ptr [r14+0Fh]
0x18003669a  imul    eax, ecx, 820h
0x1800366a0  add     edx, eax
0x1800366a2  mov     eax, ecx
0x1800366a4  shr     eax, 2
0x1800366a7  add     edx, eax
0x1800366a9  xor     edx, ecx
0x1800366ab  movzx   ecx, byte ptr [r14+10h]
0x1800366b0  imul    eax, edx, 820h
0x1800366b6  add     ecx, eax
0x1800366b8  mov     eax, edx
0x1800366ba  shr     eax, 2
0x1800366bd  add     ecx, eax
0x1800366bf  xor     ecx, edx
0x1800366c1  movzx   edx, byte ptr [r14+11h]
0x1800366c6  imul    eax, ecx, 820h
0x1800366cc  add     edx, eax
0x1800366ce  mov     eax, ecx
0x1800366d0  shr     eax, 2
0x1800366d3  add     edx, eax
0x1800366d5  xor     edx, ecx
0x1800366d7  movzx   r8d, byte ptr [r14+12h]
0x1800366dc  imul    eax, edx, 820h
0x1800366e2  add     r8d, eax
0x1800366e5  mov     eax, edx
0x1800366e7  shr     eax, 2
0x1800366ea  add     r8d, eax
0x1800366ed  xor     r8d, edx
0x1800366f0  movzx   eax, byte ptr [r14+13h]
0x1800366f5  imul    ecx, r8d, 820h
0x1800366fc  add     eax, ecx
0x1800366fe  mov     ecx, r8d
0x180036701  shr     ecx, 2
0x180036704  add     eax, ecx
0x180036706  xor     eax, r8d
0x180036709  btr     eax, 1Fh
0x18003670d  xor     edx, edx
0x18003670f  div     r9d
0x180036712  mov     eax, edx
0x180036714  mov     ecx, eax
0x180036716  mov     rax, [rdi+80h]
0x18003671d  mov     rdx, [rax+rcx*8]
0x180036721  test    rdx, rdx
0x180036724  jz      short loc_180036762
0x180036726  cmp     dword ptr [rdx+8], 14h
0x18003672a  jnz     short loc_18003675A
0x18003672c  mov     ecx, [rdi+90h]
0x180036732  mov     rax, [r14]
0x180036735  sub     rax, [rcx+rdx]
0x180036739  jnz     short loc_180036751
0x18003673b  mov     rax, [r14+8]
0x18003673f  sub     rax, [rcx+rdx+8]
0x180036744  jnz     short loc_180036751
0x180036746  mov     eax, [r14+10h]
  ... truncated ...
```
