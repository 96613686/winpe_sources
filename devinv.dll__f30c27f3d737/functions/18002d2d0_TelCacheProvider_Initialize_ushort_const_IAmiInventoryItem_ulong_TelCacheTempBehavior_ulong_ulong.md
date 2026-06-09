# TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)

- ea: `0x18002d2d0`
- end: `0x18002db8b`
- name: `?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z`
- size: `2235`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a500`
- `0x18003d8c0`

## callees

- `0x1800066f0`
- `0x18000eb24`
- `0x180010a10`
- `0x180010b3c`
- `0x180012af4`
- `0x18002670c`
- `0x18002c860`
- `0x18002ca88`
- `0x18002cf28`
- `0x18002d2d0`
- `0x18002f0f4`
- `0x180030d6c`
- `0x180030fe4`
- `0x180066c10`
- `0x180116010`

## import_xrefs

- `AEPIC!__imp_InvCacheOpenVerProvider` at `0x18002d618`
- `AEPIC!__imp_InvCacheOpenVerProvider` at `0x18002d618`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002d5b2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002d5b2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002d642`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002d642`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d5e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d5e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002d53e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002d81d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002d9cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002dad0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002d53e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002d81d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002d9cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002dad0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d548`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d827`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d9d6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002dada`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d548`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d827`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d9d6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002dada`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d526`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d805`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d9b4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002dab8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d526`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d805`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d9b4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002dab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d5c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d5c5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002d62d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002d62d`

## string_xrefs

- `0x18002d354`: `Already initialized [%#x]`
- `0x18002d3ee`: `ItemTemplate is null or has no schema for SQLite cache provider [%#x]`
- `0x18002d5ab`: `aepic.dll`
- `0x18002d687`: `AepicInvCache::Initialize failed [%#x]`
- `0x18002d725`: `TelCacheProvider::GetVersion failed [%#x]`
- `0x18002d703`: `InventoryCache::GetMetadata [%#x]`
- `0x18002d710`: `TelCacheProvider::GetVersion`
- `0x18002d6e2`: `TelCacheProvider::SetVersion [%#x]`
- `0x18002d405`: `Using SQLite cache provider: %ls.`
- `0x18002d8ab`: `Using SQLite cache provider: %ls.`
- `0x18002d4c6`: `SqliteInvCache::Initialize failed [%#x]`
- `0x18002d962`: `SqliteInvCache::Initialize failed [%#x]`
- `0x18002da66`: `RtlArrayCache::Initialize failed [%#x]`
- `0x18002da8b`: `Using in-memory cache provider: %ls.`
- `0x18002d330`: `TelCacheProvider::Initialize`
- `0x18002d3d8`: `TelCacheProvider::Initialize`
- `0x18002d4d3`: `TelCacheProvider::Initialize`
- `0x18002d692`: `TelCacheProvider::Initialize`
- `0x18002d732`: `TelCacheProvider::Initialize`
- `0x18002d76e`: `TelCacheProvider::Initialize`
- `0x18002d8b8`: `TelCacheProvider::Initialize`
- `0x18002d96f`: `TelCacheProvider::Initialize`
- `0x18002da57`: `TelCacheProvider::Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TelCacheProvider::Initialize(
        _QWORD *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        DWORD dwMilliseconds)
{
  char v9; // si
  Windows::Compat::Inventory::RtlArrayCache *v10; // r13
  Windows::Compat::Inventory::SqliteInvCache **v11; // r14
  int v12; // eax
  signed int v13; // ebx
  const char *v14; // r9
  __int64 v15; // r8
  Windows::Compat::Inventory::InventorySynchronization *v16; // rdi
  char v17; // bl
  _QWORD *v18; // rax
  Windows::Compat::Inventory::SqliteInvCache *v19; // rax
  Windows::Compat::Inventory::SqliteInvCache *v20; // rsi
  int v21; // eax
  char v22; // cl
  __int64 v23; // rax
  char v24; // si
  struct Windows::Compat::Inventory::InventoryCache *v25; // rsi
  HMODULE Library; // rax
  signed int LastError; // eax
  char *i; // rax
  __int64 v29; // rcx
  __int64 v30; // r8
  int v31; // eax
  TelCacheProvider *v32; // rcx
  int v33; // eax
  int v34; // eax
  char v35; // cl
  __int64 v36; // rax
  _QWORD *v37; // rax
  char v38; // dl
  char v39; // bl
  Windows::Compat::Inventory::SqliteInvCache *v40; // rax
  Windows::Compat::Inventory::SqliteInvCache *v41; // rbx
  int v42; // eax
  char v43; // cl
  __int64 v44; // rax
  char v45; // cl
  __int64 v46; // rax
  int v47; // eax
  int v49; // [rsp+20h] [rbp-48h]
  unsigned int v50; // [rsp+20h] [rbp-48h]
  unsigned int v51[2]; // [rsp+20h] [rbp-48h]
  unsigned int v52; // [rsp+20h] [rbp-48h]
  struct Windows::Compat::Inventory::InventoryCache *v53; // [rsp+30h] [rbp-38h]
  HMODULE hLibModule; // [rsp+40h] [rbp-28h]
  _BYTE v55[32]; // [rsp+48h] [rbp-20h] BYREF
  char v56; // [rsp+B0h] [rbp+48h]
  struct Windows::Compat::Inventory::InventoryCache *v58; // [rsp+C0h] [rbp+58h] BYREF
  int v59; // [rsp+C8h] [rbp+60h] BYREF

  v9 = 0;
  v56 = 0;
  v59 = 0;
  v10 = 0;
  v53 = 0;
  *a1 = a3;
  *((_WORD *)a1 + 4) = 0;
  *((_WORD *)a1 + 48) = 0;
  v11 = (Windows::Compat::Inventory::SqliteInvCache **)(a1 + 11);
  if ( !a2 )
  {
    v12 = -2147024809;
    v13 = -2147024809;
    v14 = "ProviderName argument is null [%#x]";
    v15 = 575;
LABEL_3:
    v49 = v12;
LABEL_4:
    AslLogCallPrintf(1, "TelCacheProvider::Initialize", v15, v14, v49);
    goto LABEL_132;
  }
  if ( *v11 )
  {
    v13 = -2147418113;
    v49 = -2147418113;
    v14 = "Already initialized [%#x]";
    v15 = 582;
    goto LABEL_4;
  }
  v16 = (Windows::Compat::Inventory::InventorySynchronization *)(a1 + 13);
  v12 = Windows::Compat::Inventory::InventorySynchronization::Initialize(
          (Windows::Compat::Inventory::InventorySynchronization *)(a1 + 13),
          a2);
  v13 = v12;
  if ( v12 < 0 )
  {
    v14 = "InventorySynchronization:Initialize [%#x]";
    v15 = 589;
    goto LABEL_3;
  }
  v17 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v25 = (struct Windows::Compat::Inventory::InventoryCache *)operator new(
                                                                 0x20u,
                                                                 (const struct std::nothrow_t *)std::nothrow);
    v58 = v25;
    if ( !v25 )
      goto LABEL_131;
    *(_QWORD *)v25 = &Windows::Compat::Inventory::AepicInvCache::`vftable';
    *((_QWORD *)v25 + 1) = 0;
    *((_QWORD *)v25 + 2) = 0;
    *((_BYTE *)v25 + 24) = 0;
    Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(v16);
    Library = LoadLibraryExW(L"aepic.dll", 0, 0x800u);
    hLibModule = Library;
    if ( Library )
    {
      if ( GetProcAddress(Library, (LPCSTR)0x64) )
      {
        LODWORD(v58) = a6 + 1;
        if ( a6 == -1 )
        {
          v13 = -2147467259;
        }
        else
        {
          for ( i = (char *)v25 + 8; ; i = (char *)v25 + 8 )
          {
            v13 = InvCacheOpenVerProvider(i, 0, a2, 2);
            if ( v13 >= 0 )
              break;
            LODWORD(v58) = (_DWORD)v58 - 1;
            if ( !(_DWORD)v58 )
              break;
            Sleep(dwMilliseconds);
          }
        }
      }
      else
      {
        v13 = -2147467262;
      }
      FreeLibrary(hLibModule);
    }
    else
    {
      LastError = GetLastError();
      v13 = LastError;
      if ( LastError > 0 )
        v13 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( v13 < 0 )
    {
      v24 = 1;
      if ( v13 == -2147467262 || v13 == -2147024891 || v13 == -2147024864 || v13 == -2147023582 )
      {
        v29 = 3;
        v30 = 665;
      }
      else
      {
        v29 = 1;
        v30 = 669;
      }
      AslLogCallPrintf(v29, "TelCacheProvider::Initialize", v30, "AepicInvCache::Initialize failed [%#x]", v13);
LABEL_87:
      if ( a5 == 3 )
        goto LABEL_106;
LABEL_88:
      if ( !*v11 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
        {
          if ( *a1 )
          {
            v37 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*a1 + 64LL))(*a1, v55);
            v38 = v56 | 2;
            if ( *v37 != v37[1] )
            {
              v39 = 1;
              goto LABEL_95;
            }
          }
          else
          {
            v38 = v56;
          }
          v39 = 0;
LABEL_95:
          if ( (v38 & 2) != 0 )
            std::vector<_GUID>::~vector<_GUID>(v55);
          if ( !v39 )
            goto LABEL_105;
          AslLogCallPrintf(3, "TelCacheProvider::Initialize", 745, "Using SQLite cache provider: %ls.", a2);
          v40 = (Windows::Compat::Inventory::SqliteInvCache *)operator new(
                                                                0xF0u,
                                                                (const struct std::nothrow_t *)std::nothrow);
          if ( v40 )
            v41 = (Windows::Compat::Inventory::SqliteInvCache *)Windows::Compat::Inventory::SqliteInvCache::SqliteInvCache(v40);
          else
            v41 = 0;
          if ( !v41 )
            goto LABEL_102;
          Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(v16);
          v24 = 1;
          v42 = Windows::Compat::Inventory::SqliteInvCache::Initialize(v41, a2, (struct IAmiInventoryItem *)*a1, 1, v52);
          if ( v42 >= 0 )
          {
            *v11 = v41;
            goto LABEL_105;
          }
          AslLogCallPrintf(1, "TelCacheProvider::Initialize", 763, "SqliteInvCache::Initialize failed [%#x]", v42);
          (**(void (__fastcall ***)(Windows::Compat::Inventory::SqliteInvCache *, __int64))v41)(v41, 1);
          if ( *((_BYTE *)v16 + 36) )
          {
            v45 = 0;
            v46 = *((_QWORD *)v16 + 3);
            if ( *(_DWORD *)(v46 + 4) == 1 )
            {
              *((_BYTE *)v16 + 36) = 0;
              v45 = 1;
            }
            --*(_DWORD *)(v46 + 4);
            if ( !v45 )
              goto LABEL_120;
          }
          else
          {
            if ( WaitForSingleObject(*(HANDLE *)v16, 0xFFFFFFFF) )
            {
LABEL_120:
              v24 = 0;
              goto LABEL_105;
            }
            --**((_DWORD **)v16 + 3);
            --*((_DWORD *)v16 + 8);
            ReleaseMutex(*(HANDLE *)v16);
          }
          SetEvent(*((HANDLE *)v16 + 2));
          goto LABEL_120;
        }
        v10 = (Windows::Compat::Inventory::RtlArrayCache *)operator new(
                                                             0x38u,
                                                             (const struct std::nothrow_t *)std::nothrow);
        if ( !v10 )
        {
          v10 = 0;
LABEL_102:
          v13 = -2147024882;
          goto LABEL_106;
        }
        *(_QWORD *)v10 = &Windows::Compat::Inventory::RtlArrayCache::`vftable';
        *((_QWORD *)v10 + 1) = 0;
        *((_QWORD *)v10 + 2) = 0;
        *((_QWORD *)v10 + 3) = 0;
        *((_QWORD *)v10 + 4) = 0;
        *((_QWORD *)v10 + 5) = 0;
        *((_QWORD *)v10 + 6) = 0;
        v47 = Windows::Compat::Inventory::RtlArrayCache::Initialize(v10, a2);
        v13 = v47;
        if ( v47 < 0 )
        {
          AslLogCallPrintf(1, "TelCacheProvider::Initialize", 783, "RtlArrayCache::Initialize failed [%#x]", v47);
LABEL_106:
          if ( !v24 )
            goto LABEL_129;
LABEL_107:
          if ( *((_BYTE *)v16 + 36) )
          {
            v43 = 0;
            v44 = *((_QWORD *)v16 + 3);
            if ( *(_DWORD *)(v44 + 4) == 1 )
            {
              *((_BYTE *)v16 + 36) = 0;
              v43 = 1;
            }
            --*(_DWORD *)(v44 + 4);
            if ( !v43 )
            {
LABEL_129:
              if ( v13 >= 0 )
                goto LABEL_139;
              goto LABEL_132;
            }
          }
          else
          {
            if ( WaitForSingleObject(*(HANDLE *)v16, 0xFFFFFFFF) )
              goto LABEL_129;
            --**((_DWORD **)v16 + 3);
            --*((_DWORD *)v16 + 8);
            ReleaseMutex(*(HANDLE *)v16);
          }
          SetEvent(*((HANDLE *)v16 + 2));
          goto LABEL_129;
        }
        AslLogCallPrintf(3, "TelCacheProvider::Initialize", 787, "Using in-memory cache provider: %ls.", a2);
        *v11 = v10;
      }
LABEL_105:
      v13 = 0;
      v10 = 0;
      goto LABEL_106;
    }
    v31 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCache *, const wchar_t *, int *))(*(_QWORD *)v25 + 72LL))(
            v25,
            L"ProviderVersion",
            &v59);
    v13 = v31;
    if ( v31 == -2147024894 )
    {
      v59 = 0;
      v33 = TelCacheProvider::SetVersion(v32, v25, 2u);
      v13 = v33;
      if ( v33 < 0 )
      {
        AslLogCallPrintf(1, "TelCacheProvider::Initialize", 694, "TelCacheProvider::SetVersion [%#x]", v33);
LABEL_66:
        v53 = v25;
        goto LABEL_107;
      }
      v34 = 2;
      v59 = 2;
    }
    else
    {
      if ( v31 < 0 )
      {
        AslLogCallPrintf(1, "TelCacheProvider::GetVersion", 1801, "InventoryCache::GetMetadata [%#x]", v31);
        v51[0] = v13;
        AslLogCallPrintf(
          1,
          "TelCacheProvider::Initialize",
          684,
          "TelCacheProvider::GetVersion failed [%#x]",
          *(_QWORD *)v51);
        goto LABEL_66;
      }
      v34 = v59;
    }
    v53 = v25;
    if ( v34 == 2 )
    {
      *v11 = v25;
      v53 = 0;
      LODWORD(v58) = 0;
      if ( *a1
        && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 56LL))(*a1)
        && (*(int (__fastcall **)(Windows::Compat::Inventory::SqliteInvCache *, struct Windows::Compat::Inventory::InventoryCache **))(*(_QWORD *)*v11 + 32LL))(
             *v11,
             &v58) >= 0
        && (_DWORD)v58
        && (unsigned int)TelCacheProvider::ShouldForceFullSync((TelCacheProvider *)a1, a2) )
      {
        *((_BYTE *)a1 + 97) = 1;
      }
      v13 = 0;
    }
    else
    {
      AslLogCallPrintf(
        3,
        "TelCacheProvider::Initialize",
        702,
        "%ls ProviderVersion did not match RequestedVersion.",
        a2);
      v13 = -2147467262;
    }
    if ( *((_BYTE *)v16 + 36) )
    {
      v35 = 0;
      v36 = *((_QWORD *)v16 + 3);
      if ( *(_DWORD *)(v36 + 4) == 1 )
      {
        *((_BYTE *)v16 + 36) = 0;
        v35 = 1;
      }
      --*(_DWORD *)(v36 + 4);
      if ( !v35 )
        goto LABEL_85;
    }
    else
    {
      if ( WaitForSingleObject(*(HANDLE *)v16, 0xFFFFFFFF) )
      {
LABEL_85:
        v24 = 0;
LABEL_86:
        if ( v13 >= 0 )
          goto LABEL_88;
        goto LABEL_87;
      }
      --**((_DWORD **)v16 + 3);
      --*((_DWORD *)v16 + 8);
      ReleaseMutex(*(HANDLE *)v16);
    }
    SetEvent(*((HANDLE *)v16 + 2));
    goto LABEL_85;
  }
  if ( !*a1
    || (v18 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*a1 + 64LL))(*a1, v55),
        v9 = 1,
        v56 = 1,
        *v18 == v18[1]) )
  {
    v17 = 1;
  }
  if ( (v9 & 1) != 0 )
  {
    v56 = v9 & 0xFE;
    std::vector<_GUID>::~vector<_GUID>(v55);
  }
  if ( !v17 )
  {
    AslLogCallPrintf(3, "TelCacheProvider::Initialize", 605, "Using SQLite cache provider: %ls.", a2);
    v19 = (Windows::Compat::Inventory::SqliteInvCache *)operator new(0xF0u, (const struct std::nothrow_t *)std::nothrow);
    v58 = v19;
    if ( v19 )
      v20 = (Windows::Compat::Inventory::SqliteInvCache *)Windows::Compat::Inventory::SqliteInvCache::SqliteInvCache(v19);
    else
      v20 = 0;
    if ( v20 )
    {
      Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(v16);
      v21 = Windows::Compat::Inventory::SqliteInvCache::Initialize(v20, a2, (struct IAmiInventoryItem *)*a1, 0, v50);
      v13 = v21;
      if ( v21 < 0 )
      {
        AslLogCallPrintf(1, "TelCacheProvider::Initialize", 638, "SqliteInvCache::Initialize failed [%#x]", v21);
        (**(void (__fastcall ***)(Windows::Compat::Inventory::SqliteInvCache *, __int64))v20)(v20, 1);
      }
      else
      {
        *v11 = v20;
        LODWORD(v58) = 0;
        if ( *a1
          && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 56LL))(*a1)
          && (*(int (__fastcall **)(Windows::Compat::Inventory::SqliteInvCache *, struct Windows::Compat::Inventory::InventoryCache **))(*(_QWORD *)*v11 + 32LL))(
               *v11,
               &v58) >= 0
          && (_DWORD)v58
          && (unsigned int)TelCacheProvider::ShouldForceFullSync((TelCacheProvider *)a1, a2) )
        {
          *((_BYTE *)a1 + 97) = 1;
        }
      }
      if ( *((_BYTE *)v16 + 36) )
      {
        v22 = 0;
        v23 = *((_QWORD *)v16 + 3);
        if ( *(_DWORD *)(v23 + 4) == 1 )
        {
          *((_BYTE *)v16 + 36) = 0;
          v22 = 1;
        }
        --*(_DWORD *)(v23 + 4);
        if ( !v22 )
          goto LABEL_38;
      }
      else
      {
        if ( WaitForSingleObject(*(HANDLE *)v16, 0xFFFFFFFF) )
        {
LABEL_38:
          v24 = 0;
          v53 = 0;
          goto LABEL_86;
        }
        --**((_DWORD **)v16 + 3);
        --*((_DWORD *)v16 + 8);
        ReleaseMutex(*(HANDLE *)v16);
      }
      SetEvent(*((HANDLE *)v16 + 2));
      goto LABEL_38;
    }
LABEL_131:
    v13 = -2147024882;
    goto LABEL_132;
  }
  v13 = -2147024809;
  AslLogCallPrintf(
    1,
    "TelCacheProvider::Initialize",
    600,
    "ItemTemplate is null or has no schema for SQLite cache provider [%#x]",
    -2147024809);
LABEL_132:
  if ( *((_BYTE *)a1 + 97) )
  {
    TelCacheProvider::SendNewSyncAdds((TelCacheProvider *)a1);
    *((_BYTE *)a1 + 97) = 0;
  }
  if ( *a1 )
  {
    (**(void (__fastcall ***)(_QWORD, __int64))*a1)(*a1, 1);
    *a1 = 0;
  }
  if ( *v11 )
  {
    (**(void (__fastcall ***)(Windows::Compat::Inventory::SqliteInvCache *, __int64))*v11)(*v11, 1);
    *v11 = 0;
  }
  Windows::Compat::Inventory::InventorySynchronization::Uninitialize((Windows::Compat::Inventory::InventorySynchronization *)(a1 + 13));
LABEL_139:
  if ( v53 )
    (**(void (__fastcall ***)(struct Windows::Compat::Inventory::InventoryCache *, __int64))v53)(v53, 1);
  if ( v10 )
    (**(void (__fastcall ***)(Windows::Compat::Inventory::RtlArrayCache *, __int64))v10)(v10, 1);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18002d2d0  mov     [rsp-40h+arg_18], r9d
0x18002d2d5  mov     [rsp-40h+Src], rdx
0x18002d2da  push    rbp
0x18002d2db  push    rbx
0x18002d2dc  push    rsi
0x18002d2dd  push    rdi
0x18002d2de  push    r12
0x18002d2e0  push    r13
0x18002d2e2  push    r14
0x18002d2e4  push    r15
0x18002d2e6  mov     rbp, rsp
0x18002d2e9  sub     rsp, 68h
0x18002d2ed  mov     r12, rdx
0x18002d2f0  mov     r15, rcx
0x18002d2f3  xor     esi, esi
0x18002d2f5  mov     dword ptr [rbp+arg_0], esi
0x18002d2f8  mov     [rbp+arg_18], esi
0x18002d2fb  xor     r13d, r13d
0x18002d2fe  xor     eax, eax
0x18002d300  mov     [rbp+var_38], rax
0x18002d304  mov     [rcx], r8
0x18002d307  mov     [rcx+8], ax
0x18002d30b  mov     [rcx+60h], ax
0x18002d30f  lea     r14, [rcx+58h]
0x18002d313  test    rdx, rdx
0x18002d316  jnz     short loc_18002D346
0x18002d318  mov     eax, 80070057h
0x18002d31d  mov     ebx, eax
0x18002d31f  lea     r9, aProvidernameAr; "ProviderName argument is null [%#x]"
0x18002d326  mov     r8d, 23Fh
0x18002d32c  mov     [rsp+68h+var_48], eax
0x18002d330  lea     rdx, aTelcacheprovid_24; "TelCacheProvider::Initialize"
0x18002d337  mov     ecx, 1
0x18002d33c  call    AslLogCallPrintf
0x18002d341  jmp     loc_18002DAEB
0x18002d346  cmp     [r14], rax
0x18002d349  jz      short loc_18002D363
0x18002d34b  mov     ebx, 8000FFFFh
0x18002d350  mov     [rsp+68h+var_48], ebx
0x18002d354  lea     r9, aAlreadyInitial; "Already initialized [%#x]"
0x18002d35b  mov     r8d, 246h
0x18002d361  jmp     short loc_18002D330
0x18002d363  lea     rdi, [rcx+68h]
0x18002d367  mov     rcx, rdi; this
0x18002d36a  call    ?Initialize@InventorySynchronization@Inventory@Compat@Windows@@QEAAJPEBG@Z; Windows::Compat::Inventory::InventorySynchronization::Initialize(ushort const *)
0x18002d36f  mov     ebx, eax
0x18002d371  test    eax, eax
0x18002d373  jns     short loc_18002D384
0x18002d375  lea     r9, aInventorysynch_2; "InventorySynchronization:Initialize [%#"...
0x18002d37c  mov     r8d, 24Dh
0x18002d382  jmp     short loc_18002D32C
0x18002d384  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x18002d38b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x18002d390  xor     ebx, ebx
0x18002d392  test    al, al
0x18002d394  jz      loc_18002D55C
0x18002d39a  mov     rcx, [r15]
0x18002d39d  test    rcx, rcx
0x18002d3a0  jz      short loc_18002D3C1
0x18002d3a2  mov     rax, [rcx]
0x18002d3a5  lea     rdx, [rbp+var_20]
0x18002d3a9  mov     rax, [rax+40h]
0x18002d3ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3b2  lea     esi, [rbx+1]
0x18002d3b5  mov     dword ptr [rbp+arg_0], esi
0x18002d3b8  mov     rcx, [rax+8]
0x18002d3bc  cmp     [rax], rcx
0x18002d3bf  jnz     short loc_18002D3C3
0x18002d3c1  mov     bl, 1
0x18002d3c3  test    sil, 1
0x18002d3c7  jz      short loc_18002D3D8
0x18002d3c9  and     esi, 0FFFFFFFEh
0x18002d3cc  mov     dword ptr [rbp+arg_0], esi
0x18002d3cf  lea     rcx, [rbp+var_20]
0x18002d3d3  call    ??1?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::~vector<_GUID>(void)
0x18002d3d8  lea     rdx, aTelcacheprovid_24; "TelCacheProvider::Initialize"
0x18002d3df  test    bl, bl
0x18002d3e1  jz      short loc_18002D400
0x18002d3e3  mov     eax, 80070057h
0x18002d3e8  mov     ebx, eax
0x18002d3ea  mov     [rsp+68h+var_48], eax
0x18002d3ee  lea     r9, aItemtemplateIs; "ItemTemplate is null or has no schema f"...
0x18002d3f5  mov     r8d, 258h
0x18002d3fb  jmp     loc_18002D337
0x18002d400  mov     qword ptr [rsp+68h+var_48], r12; unsigned int
0x18002d405  lea     r9, aUsingSqliteCac; "Using SQLite cache provider: %ls."
0x18002d40c  mov     r8d, 25Dh
0x18002d412  mov     ecx, 3
0x18002d417  call    AslLogCallPrintf
0x18002d41c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002d423  mov     ecx, 0F0h; unsigned __int64
0x18002d428  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002d42d  mov     [rbp+arg_10], rax
0x18002d431  test    rax, rax
0x18002d434  jz      short loc_18002D443
0x18002d436  mov     rcx, rax; this
0x18002d439  call    ??0SqliteInvCache@Inventory@Compat@Windows@@QEAA@XZ; Windows::Compat::Inventory::SqliteInvCache::SqliteInvCache(void)
0x18002d43e  mov     rsi, rax
0x18002d441  jmp     short loc_18002D445
0x18002d443  xor     esi, esi
0x18002d445  test    rsi, rsi
0x18002d448  jz      loc_18002DAE6
0x18002d44e  mov     rcx, rdi; this
0x18002d451  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x18002d456  xor     r9d, r9d; int
0x18002d459  mov     r8, [r15]; struct IAmiInventoryItem *
0x18002d45c  mov     rdx, r12; Src
0x18002d45f  mov     rcx, rsi; this
0x18002d462  call    ?Initialize@SqliteInvCache@Inventory@Compat@Windows@@QEAAJPEBGPEAVIAmiInventoryItem@@HK@Z; Windows::Compat::Inventory::SqliteInvCache::Initialize(ushort const *,IAmiInventoryItem *,int,ulong)
0x18002d467  mov     ebx, eax
0x18002d469  test    eax, eax
0x18002d46b  js      short loc_18002D4C2
0x18002d46d  mov     [r14], rsi
0x18002d470  mov     dword ptr [rbp+arg_10], 0
0x18002d477  mov     rcx, [r15]
0x18002d47a  test    rcx, rcx
0x18002d47d  jz      short loc_18002D4F7
0x18002d47f  mov     rax, [rcx]
0x18002d482  mov     rax, [rax+38h]
0x18002d486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d48b  test    al, al
0x18002d48d  jz      short loc_18002D4F7
0x18002d48f  mov     rcx, [r14]
0x18002d492  mov     rax, [rcx]
0x18002d495  lea     rdx, [rbp+arg_10]
0x18002d499  mov     rax, [rax+20h]
0x18002d49d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4a2  test    eax, eax
0x18002d4a4  js      short loc_18002D4F7
0x18002d4a6  cmp     dword ptr [rbp+arg_10], 0
0x18002d4aa  jbe     short loc_18002D4F7
0x18002d4ac  mov     rdx, r12; unsigned __int16 *
0x18002d4af  mov     rcx, r15; this
0x18002d4b2  call    ?ShouldForceFullSync@TelCacheProvider@@AEAAHPEBG@Z; TelCacheProvider::ShouldForceFullSync(ushort const *)
0x18002d4b7  test    eax, eax
0x18002d4b9  jz      short loc_18002D4F7
0x18002d4bb  mov     byte ptr [r15+61h], 1
0x18002d4c0  jmp     short loc_18002D4F7
0x18002d4c2  mov     [rsp+68h+var_48], eax
0x18002d4c6  lea     r9, aSqliteinvcache; "SqliteInvCache::Initialize failed [%#x]"
0x18002d4cd  mov     r8d, 27Eh
0x18002d4d3  lea     rdx, aTelcacheprovid_24; "TelCacheProvider::Initialize"
0x18002d4da  mov     ecx, 1
0x18002d4df  call    AslLogCallPrintf
0x18002d4e4  mov     rax, [rsi]
0x18002d4e7  mov     edx, 1
0x18002d4ec  mov     rcx, rsi
0x18002d4ef  mov     rax, [rax]
0x18002d4f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4f7  cmp     byte ptr [rdi+24h], 0
0x18002d4fb  jz      short loc_18002D51C
0x18002d4fd  xor     cl, cl
0x18002d4ff  mov     rax, [rdi+18h]
0x18002d503  cmp     dword ptr [rax+4], 1
0x18002d507  jnz     short loc_18002D50E
0x18002d509  mov     [rdi+24h], cl
0x18002d50c  mov     cl, 1
0x18002d50e  or      r12d, 0FFFFFFFFh
0x18002d512  add     [rax+4], r12d
0x18002d516  test    cl, cl
0x18002d518  jz      short loc_18002D54E
0x18002d51a  jmp     short loc_18002D544
0x18002d51c  or      r12d, 0FFFFFFFFh
0x18002d520  mov     edx, r12d; dwMilliseconds
0x18002d523  mov     rcx, [rdi]; hHandle
0x18002d526  call    cs:__imp_WaitForSingleObject
0x18002d52c  test    eax, eax
0x18002d52e  jnz     short loc_18002D54E
0x18002d530  mov     rax, [rdi+18h]
0x18002d534  add     [rax], r12d
0x18002d537  add     [rdi+20h], r12d
0x18002d53b  mov     rcx, [rdi]; hMutex
0x18002d53e  call    cs:__imp_ReleaseMutex
0x18002d544  mov     rcx, [rdi+10h]; hEvent
0x18002d548  call    cs:__imp_SetEvent
0x18002d54e  xor     sil, sil
0x18002d551  xor     eax, eax
0x18002d553  mov     [rbp+var_38], rax
0x18002d557  jmp     loc_18002D830
0x18002d55c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002d563  mov     ecx, 20h ; ' '; unsigned __int64
0x18002d568  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002d56d  mov     rsi, rax
0x18002d570  mov     [rbp+arg_10], rax
0x18002d574  test    rax, rax
0x18002d577  jz      loc_18002DAE6
0x18002d57d  lea     rax, ??_7AepicInvCache@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::AepicInvCache::`vftable'
0x18002d584  mov     [rsi], rax
0x18002d587  mov     [rsi+8], rbx
0x18002d58b  mov     [rsi+10h], rbx
0x18002d58f  mov     [rsi+18h], bl
0x18002d592  test    rsi, rsi
0x18002d595  jz      loc_18002DAE6
0x18002d59b  mov     rcx, rdi; this
0x18002d59e  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x18002d5a3  xor     edx, edx; hFile
0x18002d5a5  mov     r8d, 800h; dwFlags
0x18002d5ab  lea     rcx, aAepicDll_0; "aepic.dll"
0x18002d5b2  call    cs:__imp_LoadLibraryExW
0x18002d5b8  mov     [rbp+hLibModule], rax
0x18002d5bc  or      r12d, 0FFFFFFFFh
0x18002d5c0  test    rax, rax
0x18002d5c3  jnz     short loc_18002D5DC
0x18002d5c5  call    cs:__imp_GetLastError
0x18002d5cb  mov     ebx, eax
0x18002d5cd  test    eax, eax
0x18002d5cf  jle     short loc_18002D648
0x18002d5d1  movzx   ebx, ax
0x18002d5d4  or      ebx, 80070000h
0x18002d5da  jmp     short loc_18002D648
0x18002d5dc  mov     edx, 64h ; 'd'; lpProcName
0x18002d5e1  mov     rcx, rax; hModule
0x18002d5e4  call    cs:__imp_GetProcAddress
0x18002d5ea  test    rax, rax
0x18002d5ed  jnz     short loc_18002D5F6
0x18002d5ef  mov     ebx, 80004002h
0x18002d5f4  jmp     short loc_18002D63E
0x18002d5f6  mov     eax, [rbp+arg_28]
0x18002d5f9  add     eax, 1
0x18002d5fc  mov     dword ptr [rbp+arg_10], eax
0x18002d5ff  jz      short loc_18002D639
0x18002d601  lea     rax, [rsi+8]
0x18002d605  mov     [rbp+var_30], rax
0x18002d609  mov     r9d, 2
0x18002d60f  mov     r8, [rbp+Src]
0x18002d613  xor     edx, edx
0x18002d615  mov     rcx, rax
0x18002d618  call    cs:__imp_InvCacheOpenVerProvider
0x18002d61e  mov     ebx, eax
0x18002d620  test    eax, eax
0x18002d622  jns     short loc_18002D63E
0x18002d624  add     dword ptr [rbp+arg_10], r12d
0x18002d628  jz      short loc_18002D63E
0x18002d62a  mov     ecx, [rbp+dwMilliseconds]; dwMilliseconds
0x18002d62d  call    cs:__imp_Sleep
0x18002d633  mov     rax, [rbp+var_30]
0x18002d637  jmp     short loc_18002D609
0x18002d639  mov     ebx, 80004005h
0x18002d63e  mov     rcx, [rbp+hLibModule]; hLibModule
0x18002d642  call    cs:__imp_FreeLibrary
0x18002d648  test    ebx, ebx
0x18002d64a  jns     short loc_18002D6A3
0x18002d64c  mov     sil, 1
0x18002d64f  cmp     ebx, 80004002h
0x18002d655  jz      short loc_18002D67C
0x18002d657  cmp     ebx, 80070005h
0x18002d65d  jz      short loc_18002D67C
0x18002d65f  cmp     ebx, 80070020h
0x18002d665  jz      short loc_18002D67C
0x18002d667  cmp     ebx, 80070522h
0x18002d66d  jz      short loc_18002D67C
0x18002d66f  mov     ecx, 1
0x18002d674  mov     r8d, 29Dh
0x18002d67a  jmp     short loc_18002D687
0x18002d67c  mov     ecx, 3
0x18002d681  mov     r8d, 299h
0x18002d687  lea     r9, aAepicinvcacheI; "AepicInvCache::Initialize failed [%#x]"
0x18002d68e  mov     [rsp+68h+var_48], ebx
0x18002d692  lea     rdx, aTelcacheprovid_24; "TelCacheProvider::Initialize"
0x18002d699  call    AslLogCallPrintf
0x18002d69e  jmp     loc_18002D834
0x18002d6a3  mov     rax, [rsi]
0x18002d6a6  lea     r8, [rbp+arg_18]
0x18002d6aa  lea     rdx, aProviderversio; "ProviderVersion"
0x18002d6b1  mov     rcx, rsi
0x18002d6b4  mov     rax, [rax+48h]
0x18002d6b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d6bd  mov     ebx, eax
0x18002d6bf  cmp     eax, 80070002h
0x18002d6c4  jnz     short loc_18002D6FB
0x18002d6c6  mov     [rbp+arg_18], r13d
0x18002d6ca  mov     r8d, 2; unsigned int
0x18002d6d0  mov     rdx, rsi; struct Windows::Compat::Inventory::InventoryCache *
0x18002d6d3  call    ?SetVersion@TelCacheProvider@@AEAAJPEAVInventoryCache@Inventory@Compat@Windows@@K@Z; TelCacheProvider::SetVersion(Windows::Compat::Inventory::InventoryCache *,ulong)
0x18002d6d8  mov     ebx, eax
0x18002d6da  test    eax, eax
0x18002d6dc  jns     short loc_18002D6F1
0x18002d6de  mov     [rsp+68h+var_48], eax
0x18002d6e2  lea     r9, aTelcacheprovid_22; "TelCacheProvider::SetVersion [%#x]"
0x18002d6e9  mov     r8d, 2B6h
0x18002d6ef  jmp     short loc_18002D732
0x18002d6f1  mov     eax, 2
0x18002d6f6  mov     [rbp+arg_18], eax
0x18002d6f9  jmp     short loc_18002D74F
0x18002d6fb  test    ebx, ebx
0x18002d6fd  jns     short loc_18002D74C
0x18002d6ff  mov     [rsp+68h+var_48], ebx
0x18002d703  lea     r9, aInventorycache_0; "InventoryCache::GetMetadata [%#x]"
0x18002d70a  mov     r8d, 709h
0x18002d710  lea     rdx, aTelcacheprovid_32; "TelCacheProvider::GetVersion"
0x18002d717  mov     ecx, 1
0x18002d71c  call    AslLogCallPrintf
0x18002d721  mov     [rsp+68h+var_48], ebx
0x18002d725  lea     r9, aTelcacheprovid_12; "TelCacheProvider::GetVersion failed [%#"...
0x18002d72c  mov     r8d, 2ACh
0x18002d732  lea     rdx, aTelcacheprovid_24; "TelCacheProvider::Initialize"
0x18002d739  mov     ecx, 1
0x18002d73e  call    AslLogCallPrintf
0x18002d743  mov     [rbp+var_38], rsi
0x18002d747  jmp     loc_18002D932
  ... truncated ...
```
