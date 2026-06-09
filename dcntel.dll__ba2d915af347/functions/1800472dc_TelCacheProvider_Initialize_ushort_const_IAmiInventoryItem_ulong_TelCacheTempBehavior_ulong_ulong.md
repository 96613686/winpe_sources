# TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)

- ea: `0x1800472dc`
- end: `0x180047b7e`
- name: `?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z`
- size: `2210`
- prototype: `__int64 __fastcall(_QWORD *, const unsigned __int16 *, __int64, __int64, unsigned int, int)`
- caller_count: `3`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a2cd0`
- `0x1800b5df0`
- `0x1800d4c30`

## callees

- `0x1800097d0`
- `0x180013774`
- `0x18001697c`
- `0x18004036c`
- `0x1800413d4`
- `0x180046870`
- `0x180046a98`
- `0x180046f38`
- `0x1800472dc`
- `0x1800496e0`
- `0x18004b2ec`
- `0x18004b3e8`
- `0x18004c2b0`
- `0x18016796c`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800473fd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800473fd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180047485`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180047485`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004742f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004742f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180047664`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004782e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180047a73`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180047acf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180047664`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004782e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180047a73`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180047acf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180047642`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004780c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180047a51`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180047aad`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180047642`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004780c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180047a51`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180047aad`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18004765a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180047824`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180047a69`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180047ac5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18004765a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180047824`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180047a69`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180047ac5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047410`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047410`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004746f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004746f`
- `AEPIC!__imp_InvCacheOpenVerProvider` at `0x180047459`
- `AEPIC!__imp_InvCacheOpenVerProvider` at `0x180047459`

## string_xrefs

- `0x180047363`: `Already initialized [%#x]`
- `0x1800476cd`: `ItemTemplate is null or has no schema for SQLite cache provider [%#x]`
- `0x1800473f6`: `aepic.dll`
- `0x180047543`: `InventoryCache::GetMetadata [%#x]`
- `0x180047550`: `TelCacheProvider::GetVersion`
- `0x1800474ce`: `AepicInvCache::Initialize failed [%#x]`
- `0x180047565`: `TelCacheProvider::GetVersion failed [%#x]`
- `0x1800476e4`: `Using SQLite cache provider: %ls.`
- `0x180047979`: `Using SQLite cache provider: %ls.`
- `0x180047525`: `TelCacheProvider::SetVersion [%#x]`
- `0x1800477ac`: `SqliteInvCache::Initialize failed [%#x]`
- `0x1800479ff`: `SqliteInvCache::Initialize failed [%#x]`
- `0x180047902`: `Using in-memory cache provider: %ls.`
- `0x18004733f`: `TelCacheProvider::Initialize`
- `0x1800474d5`: `TelCacheProvider::Initialize`
- `0x180047572`: `TelCacheProvider::Initialize`
- `0x1800475b0`: `TelCacheProvider::Initialize`
- `0x1800476b7`: `TelCacheProvider::Initialize`
- `0x1800477b9`: `TelCacheProvider::Initialize`
- `0x1800478ce`: `TelCacheProvider::Initialize`
- `0x180047986`: `TelCacheProvider::Initialize`
- `0x180047a0c`: `TelCacheProvider::Initialize`
- `0x1800478dd`: `RtlArrayCache::Initialize failed [%#x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TelCacheProvider::Initialize(
        _QWORD *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        int a6)
{
  int v8; // r15d
  Windows::Compat::Inventory::RtlArrayCache *v9; // r13
  Windows::Compat::Inventory::SqliteInvCache **v10; // r14
  int v11; // eax
  int v12; // ebx
  const char *v13; // r9
  __int64 v14; // r8
  Windows::Compat::Inventory::InventorySynchronization *v15; // rdi
  char v16; // bl
  struct Windows::Compat::Inventory::InventoryCache *v17; // rsi
  HMODULE Library; // rax
  signed int LastError; // eax
  signed int v20; // ebx
  int v21; // edi
  char v22; // si
  __int64 v23; // rcx
  __int64 v24; // r8
  int v25; // eax
  TelCacheProvider *v26; // rcx
  int v27; // eax
  int v28; // eax
  char v29; // cl
  __int64 v30; // rax
  _QWORD *v31; // rax
  Windows::Compat::Inventory::SqliteInvCache *v32; // rax
  Windows::Compat::Inventory::SqliteInvCache *v33; // rbx
  int v34; // eax
  char v35; // cl
  __int64 v36; // rax
  int v37; // eax
  _QWORD *v38; // rax
  char v39; // dl
  char v40; // bl
  Windows::Compat::Inventory::SqliteInvCache *v41; // rax
  Windows::Compat::Inventory::SqliteInvCache *v42; // rbx
  int v43; // eax
  char v44; // cl
  __int64 v45; // rax
  char v46; // cl
  __int64 v47; // rax
  int v49; // [rsp+20h] [rbp-38h]
  unsigned int v50[2]; // [rsp+20h] [rbp-38h]
  unsigned int v51; // [rsp+20h] [rbp-38h]
  unsigned int v52; // [rsp+20h] [rbp-38h]
  HMODULE hLibModule; // [rsp+30h] [rbp-28h]
  _BYTE v54[32]; // [rsp+38h] [rbp-20h] BYREF
  struct Windows::Compat::Inventory::InventoryCache *v55; // [rsp+A0h] [rbp+48h]
  int v57; // [rsp+B8h] [rbp+60h] BYREF

  v8 = 0;
  a5 = 0;
  v57 = 0;
  v9 = 0;
  v55 = 0;
  *a1 = a3;
  *((_WORD *)a1 + 4) = 0;
  *((_WORD *)a1 + 48) = 0;
  v10 = (Windows::Compat::Inventory::SqliteInvCache **)(a1 + 11);
  if ( !a2 )
  {
    v11 = -2147024809;
    v12 = -2147024809;
    v13 = "ProviderName argument is null [%#x]";
    v14 = 575;
LABEL_3:
    v49 = v11;
LABEL_4:
    AslLogCallPrintf(1, "TelCacheProvider::Initialize", v14, v13, v49);
    goto LABEL_127;
  }
  if ( *v10 )
  {
    v12 = -2147418113;
    v49 = -2147418113;
    v13 = "Already initialized [%#x]";
    v14 = 582;
    goto LABEL_4;
  }
  v15 = (Windows::Compat::Inventory::InventorySynchronization *)(a1 + 13);
  v11 = Windows::Compat::Inventory::InventorySynchronization::Initialize(
          (Windows::Compat::Inventory::InventorySynchronization *)(a1 + 13),
          a2);
  v12 = v11;
  if ( v11 < 0 )
  {
    v13 = "InventorySynchronization:Initialize [%#x]";
    v14 = 589;
    goto LABEL_3;
  }
  v16 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v17 = (struct Windows::Compat::Inventory::InventoryCache *)operator new(
                                                                 0x20u,
                                                                 (const struct std::nothrow_t *)&std::nothrow);
    if ( v17 )
    {
      *(_QWORD *)v17 = &Windows::Compat::Inventory::AepicInvCache::`vftable';
      *((_QWORD *)v17 + 1) = 0;
      *((_QWORD *)v17 + 2) = 0;
      *((_BYTE *)v17 + 24) = 0;
      Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(v15);
      Library = LoadLibraryExW(L"aepic.dll", 0, 0x800u);
      hLibModule = Library;
      if ( Library )
      {
        if ( GetProcAddress(Library, (LPCSTR)0x64) )
        {
          v21 = 4;
          while ( 1 )
          {
            v20 = InvCacheOpenVerProvider((char *)v17 + 8, 0, a2, 2);
            if ( v20 >= 0 )
              break;
            if ( !--v21 )
              break;
            Sleep(0x64u);
          }
          v15 = (Windows::Compat::Inventory::InventorySynchronization *)(a1 + 13);
          v10 = (Windows::Compat::Inventory::SqliteInvCache **)(a1 + 11);
        }
        else
        {
          v20 = -2147467262;
        }
        FreeLibrary(hLibModule);
      }
      else
      {
        LastError = GetLastError();
        v20 = LastError;
        if ( LastError > 0 )
          v20 = (unsigned __int16)LastError | 0x80070000;
      }
      if ( v20 < 0 )
      {
        v22 = 1;
        if ( v20 == -2147467262 || v20 == -2147024891 || v20 == -2147024864 || v20 == -2147023582 )
        {
          v23 = 3;
          v24 = 665;
        }
        else
        {
          v23 = 1;
          v24 = 669;
        }
        AslLogCallPrintf(v23, "TelCacheProvider::Initialize", v24, "AepicInvCache::Initialize failed [%#x]", v20);
LABEL_85:
        if ( *v10 )
        {
LABEL_116:
          v12 = 0;
          v9 = 0;
LABEL_117:
          if ( !v22 )
            goto LABEL_126;
LABEL_118:
          if ( *((_BYTE *)v15 + 36) )
          {
            v46 = 0;
            v47 = *((_QWORD *)v15 + 3);
            if ( *(_DWORD *)(v47 + 4) == 1 )
            {
              *((_BYTE *)v15 + 36) = 0;
              v46 = 1;
            }
            --*(_DWORD *)(v47 + 4);
            if ( !v46 )
            {
LABEL_126:
              if ( v12 >= 0 )
                goto LABEL_134;
              goto LABEL_127;
            }
          }
          else
          {
            if ( WaitForSingleObject(*(HANDLE *)v15, 0xFFFFFFFF) )
              goto LABEL_126;
            --**((_DWORD **)v15 + 3);
            --*((_DWORD *)v15 + 8);
            ReleaseMutex(*(HANDLE *)v15);
          }
          SetEvent(*((HANDLE *)v15 + 2));
          goto LABEL_126;
        }
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
        {
          v9 = (Windows::Compat::Inventory::RtlArrayCache *)operator new(
                                                              0x38u,
                                                              (const struct std::nothrow_t *)&std::nothrow);
          if ( v9 )
          {
            *(_QWORD *)v9 = &Windows::Compat::Inventory::RtlArrayCache::`vftable';
            *((_QWORD *)v9 + 1) = 0;
            *((_QWORD *)v9 + 2) = 0;
            *((_QWORD *)v9 + 3) = 0;
            *((_QWORD *)v9 + 4) = 0;
            *((_QWORD *)v9 + 5) = 0;
            *((_QWORD *)v9 + 6) = 0;
            v37 = Windows::Compat::Inventory::RtlArrayCache::Initialize(v9, a2);
            v12 = v37;
            if ( v37 < 0 )
            {
              AslLogCallPrintf(1, "TelCacheProvider::Initialize", 783, "RtlArrayCache::Initialize failed [%#x]", v37);
              goto LABEL_117;
            }
            AslLogCallPrintf(3, "TelCacheProvider::Initialize", 787, "Using in-memory cache provider: %ls.", a2);
            *v10 = v9;
            goto LABEL_116;
          }
          v9 = 0;
LABEL_104:
          v12 = -2147024882;
          goto LABEL_117;
        }
        if ( *a1 )
        {
          v38 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*a1 + 64LL))(*a1, v54);
          v39 = a5 | 2;
          if ( *v38 != v38[1] )
          {
            v40 = 1;
            goto LABEL_97;
          }
        }
        else
        {
          v39 = a5;
        }
        v40 = 0;
LABEL_97:
        if ( (v39 & 2) != 0 )
          std::vector<IAmiInventoryItem::_CacheItemProperty>::~vector<IAmiInventoryItem::_CacheItemProperty>(v54);
        if ( !v40 )
          goto LABEL_116;
        AslLogCallPrintf(3, "TelCacheProvider::Initialize", 745, "Using SQLite cache provider: %ls.", a2);
        v41 = (Windows::Compat::Inventory::SqliteInvCache *)operator new(
                                                              0xF0u,
                                                              (const struct std::nothrow_t *)&std::nothrow);
        if ( v41 )
          v42 = (Windows::Compat::Inventory::SqliteInvCache *)Windows::Compat::Inventory::SqliteInvCache::SqliteInvCache(v41);
        else
          v42 = 0;
        if ( !v42 )
          goto LABEL_104;
        Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(v15);
        v22 = 1;
        v43 = Windows::Compat::Inventory::SqliteInvCache::Initialize(v42, a2, (struct IAmiInventoryItem *)*a1, 1, v52);
        if ( v43 >= 0 )
        {
          *v10 = v42;
          goto LABEL_116;
        }
        AslLogCallPrintf(1, "TelCacheProvider::Initialize", 763, "SqliteInvCache::Initialize failed [%#x]", v43);
        (**(void (__fastcall ***)(Windows::Compat::Inventory::SqliteInvCache *, __int64))v42)(v42, 1);
        if ( *((_BYTE *)v15 + 36) )
        {
          v44 = 0;
          v45 = *((_QWORD *)v15 + 3);
          if ( *(_DWORD *)(v45 + 4) == 1 )
          {
            *((_BYTE *)v15 + 36) = 0;
            v44 = 1;
          }
          --*(_DWORD *)(v45 + 4);
          if ( !v44 )
            goto LABEL_115;
        }
        else
        {
          if ( WaitForSingleObject(*(HANDLE *)v15, 0xFFFFFFFF) )
          {
LABEL_115:
            v22 = 0;
            goto LABEL_116;
          }
          --**((_DWORD **)v15 + 3);
          --*((_DWORD *)v15 + 8);
          ReleaseMutex(*(HANDLE *)v15);
        }
        SetEvent(*((HANDLE *)v15 + 2));
        goto LABEL_115;
      }
      v25 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCache *, const wchar_t *, int *))(*(_QWORD *)v17 + 72LL))(
              v17,
              L"ProviderVersion",
              &v57);
      v12 = v25;
      if ( v25 == -2147024894 )
      {
        v57 = 0;
        v27 = TelCacheProvider::SetVersion(v26, v17, 0);
        v12 = v27;
        if ( v27 < 0 )
        {
          AslLogCallPrintf(1, "TelCacheProvider::Initialize", 694, "TelCacheProvider::SetVersion [%#x]", v27);
LABEL_37:
          v55 = v17;
          goto LABEL_118;
        }
        v28 = 0;
        v57 = 0;
      }
      else
      {
        if ( v25 < 0 )
        {
          AslLogCallPrintf(1, "TelCacheProvider::GetVersion", 1801, "InventoryCache::GetMetadata [%#x]", v25);
          v50[0] = v12;
          AslLogCallPrintf(
            1,
            "TelCacheProvider::Initialize",
            684,
            "TelCacheProvider::GetVersion failed [%#x]",
            *(_QWORD *)v50);
          goto LABEL_37;
        }
        v28 = v57;
      }
      v55 = v17;
      if ( v28 )
      {
        AslLogCallPrintf(
          3,
          "TelCacheProvider::Initialize",
          702,
          "%ls ProviderVersion did not match RequestedVersion.",
          a2);
      }
      else
      {
        *v10 = v17;
        v55 = 0;
        a6 = 0;
        if ( *a1
          && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 56LL))(*a1)
          && (*(int (__fastcall **)(Windows::Compat::Inventory::SqliteInvCache *, int *))(*(_QWORD *)*v10 + 32LL))(
               *v10,
               &a6) >= 0
          && a6
          && (unsigned int)TelCacheProvider::ShouldForceFullSync((TelCacheProvider *)a1, a2) )
        {
          *((_BYTE *)a1 + 97) = 1;
        }
      }
      if ( *((_BYTE *)v15 + 36) )
      {
        v29 = 0;
        v30 = *((_QWORD *)v15 + 3);
        if ( *(_DWORD *)(v30 + 4) == 1 )
        {
          *((_BYTE *)v15 + 36) = 0;
          v29 = 1;
        }
        --*(_DWORD *)(v30 + 4);
        if ( !v29 )
          goto LABEL_55;
      }
      else
      {
        if ( WaitForSingleObject(*(HANDLE *)v15, 0xFFFFFFFF) )
        {
LABEL_55:
          v22 = 0;
          goto LABEL_85;
        }
        --**((_DWORD **)v15 + 3);
        --*((_DWORD *)v15 + 8);
        ReleaseMutex(*(HANDLE *)v15);
      }
      SetEvent(*((HANDLE *)v15 + 2));
      goto LABEL_55;
    }
    goto LABEL_67;
  }
  if ( !*a1
    || (v31 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*a1 + 64LL))(*a1, v54),
        v8 = 1,
        a5 = 1,
        *v31 == v31[1]) )
  {
    v16 = 1;
  }
  if ( (v8 & 1) != 0 )
  {
    a5 = v8 & 0xFFFFFFFE;
    std::vector<IAmiInventoryItem::_CacheItemProperty>::~vector<IAmiInventoryItem::_CacheItemProperty>(v54);
  }
  if ( !v16 )
  {
    AslLogCallPrintf(3, "TelCacheProvider::Initialize", 605, "Using SQLite cache provider: %ls.", a2);
    v32 = (Windows::Compat::Inventory::SqliteInvCache *)operator new(
                                                          0xF0u,
                                                          (const struct std::nothrow_t *)&std::nothrow);
    if ( v32 )
      v33 = (Windows::Compat::Inventory::SqliteInvCache *)Windows::Compat::Inventory::SqliteInvCache::SqliteInvCache(v32);
    else
      v33 = 0;
    if ( !v33 )
    {
LABEL_67:
      v12 = -2147024882;
      goto LABEL_127;
    }
    Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(v15);
    v34 = Windows::Compat::Inventory::SqliteInvCache::Initialize(v33, a2, (struct IAmiInventoryItem *)*a1, 0, v51);
    if ( v34 < 0 )
    {
      AslLogCallPrintf(1, "TelCacheProvider::Initialize", 638, "SqliteInvCache::Initialize failed [%#x]", v34);
      (**(void (__fastcall ***)(Windows::Compat::Inventory::SqliteInvCache *, __int64))v33)(v33, 1);
    }
    else
    {
      *v10 = v33;
      a6 = 0;
      if ( *a1
        && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 56LL))(*a1)
        && (*(int (__fastcall **)(Windows::Compat::Inventory::SqliteInvCache *, int *))(*(_QWORD *)*v10 + 32LL))(
             *v10,
             &a6) >= 0
        && a6
        && (unsigned int)TelCacheProvider::ShouldForceFullSync((TelCacheProvider *)a1, a2) )
      {
        *((_BYTE *)a1 + 97) = 1;
      }
    }
    if ( *((_BYTE *)v15 + 36) )
    {
      v35 = 0;
      v36 = *((_QWORD *)v15 + 3);
      if ( *(_DWORD *)(v36 + 4) == 1 )
      {
        *((_BYTE *)v15 + 36) = 0;
        v35 = 1;
      }
      --*(_DWORD *)(v36 + 4);
      if ( !v35 )
        goto LABEL_84;
    }
    else
    {
      if ( WaitForSingleObject(*(HANDLE *)v15, 0xFFFFFFFF) )
      {
LABEL_84:
        v22 = 0;
        v55 = 0;
        goto LABEL_85;
      }
      --**((_DWORD **)v15 + 3);
      --*((_DWORD *)v15 + 8);
      ReleaseMutex(*(HANDLE *)v15);
    }
    SetEvent(*((HANDLE *)v15 + 2));
    goto LABEL_84;
  }
  v12 = -2147024809;
  AslLogCallPrintf(
    1,
    "TelCacheProvider::Initialize",
    600,
    "ItemTemplate is null or has no schema for SQLite cache provider [%#x]",
    -2147024809);
LABEL_127:
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
  if ( *v10 )
  {
    (**(void (__fastcall ***)(Windows::Compat::Inventory::SqliteInvCache *, __int64))*v10)(*v10, 1);
    *v10 = 0;
  }
  Windows::Compat::Inventory::InventorySynchronization::Uninitialize((Windows::Compat::Inventory::InventorySynchronization *)(a1 + 13));
LABEL_134:
  if ( v55 )
    (**(void (__fastcall ***)(struct Windows::Compat::Inventory::InventoryCache *, __int64))v55)(v55, 1);
  if ( v9 )
    (**(void (__fastcall ***)(Windows::Compat::Inventory::RtlArrayCache *, __int64))v9)(v9, 1);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800472dc  mov     [rsp-40h+arg_18], r9d
0x1800472e1  mov     [rsp-40h+Src], rdx
0x1800472e6  push    rbp
0x1800472e7  push    rbx
0x1800472e8  push    rsi
0x1800472e9  push    rdi
0x1800472ea  push    r12
0x1800472ec  push    r13
0x1800472ee  push    r14
0x1800472f0  push    r15
0x1800472f2  mov     rbp, rsp
0x1800472f5  sub     rsp, 58h
0x1800472f9  mov     rsi, rdx
0x1800472fc  mov     r12, rcx
0x1800472ff  xor     r15d, r15d
0x180047302  mov     [rbp+arg_20], r15d
0x180047306  mov     [rbp+arg_18], r15d
0x18004730a  xor     r13d, r13d
0x18004730d  xor     eax, eax
0x18004730f  mov     [rbp+arg_0], rax
0x180047313  mov     [rcx], r8
0x180047316  mov     [rcx+8], ax
0x18004731a  mov     [rcx+60h], ax
0x18004731e  lea     r14, [rcx+58h]
0x180047322  test    rdx, rdx
0x180047325  jnz     short loc_180047355
0x180047327  mov     eax, 80070057h
0x18004732c  mov     ebx, eax
0x18004732e  lea     r9, aProvidernameAr; "ProviderName argument is null [%#x]"
0x180047335  mov     r8d, 23Fh
0x18004733b  mov     [rsp+58h+var_38], eax
0x18004733f  lea     rdx, aTelcacheprovid_13; "TelCacheProvider::Initialize"
0x180047346  mov     ecx, 1
0x18004734b  call    AslLogCallPrintf
0x180047350  jmp     loc_180047AD9
0x180047355  cmp     [r14], rax
0x180047358  jz      short loc_180047372
0x18004735a  mov     ebx, 8000FFFFh
0x18004735f  mov     [rsp+58h+var_38], ebx
0x180047363  lea     r9, aAlreadyInitial; "Already initialized [%#x]"
0x18004736a  mov     r8d, 246h
0x180047370  jmp     short loc_18004733F
0x180047372  lea     rdi, [rcx+68h]
0x180047376  mov     rcx, rdi; this
0x180047379  call    ?Initialize@InventorySynchronization@Inventory@Compat@Windows@@QEAAJPEBG@Z; Windows::Compat::Inventory::InventorySynchronization::Initialize(ushort const *)
0x18004737e  mov     ebx, eax
0x180047380  test    eax, eax
0x180047382  jns     short loc_180047393
0x180047384  lea     r9, aInventorysynch_2; "InventorySynchronization:Initialize [%#"...
0x18004738b  mov     r8d, 24Dh
0x180047391  jmp     short loc_18004733B
0x180047393  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x18004739a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x18004739f  xor     ebx, ebx
0x1800473a1  test    al, al
0x1800473a3  jnz     loc_180047672
0x1800473a9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800473b0  lea     ecx, [rbx+20h]; unsigned __int64
0x1800473b3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800473b8  mov     rsi, rax
0x1800473bb  mov     [rbp+hLibModule], rax
0x1800473bf  test    rax, rax
0x1800473c2  jz      loc_180047729
0x1800473c8  lea     rax, ??_7AepicInvCache@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::AepicInvCache::`vftable'
0x1800473cf  mov     [rsi], rax
0x1800473d2  mov     [rsi+8], rbx
0x1800473d6  mov     [rsi+10h], rbx
0x1800473da  mov     [rsi+18h], bl
0x1800473dd  test    rsi, rsi
0x1800473e0  jz      loc_180047729
0x1800473e6  mov     rcx, rdi; this
0x1800473e9  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x1800473ee  xor     edx, edx; hFile
0x1800473f0  mov     r8d, 800h; dwFlags
0x1800473f6  lea     rcx, aAepicDll_0; "aepic.dll"
0x1800473fd  call    cs:__imp_LoadLibraryExW
0x180047403  mov     [rbp+hLibModule], rax
0x180047407  or      r15d, 0FFFFFFFFh
0x18004740b  test    rax, rax
0x18004740e  jnz     short loc_180047427
0x180047410  call    cs:__imp_GetLastError
0x180047416  mov     ebx, eax
0x180047418  test    eax, eax
0x18004741a  jle     short loc_18004748B
0x18004741c  movzx   ebx, ax
0x18004741f  or      ebx, 80070000h
0x180047425  jmp     short loc_18004748B
0x180047427  mov     edx, 64h ; 'd'; lpProcName
0x18004742c  mov     rcx, rax; hModule
0x18004742f  call    cs:__imp_GetProcAddress
0x180047435  test    rax, rax
0x180047438  jnz     short loc_180047441
0x18004743a  mov     ebx, 80004002h
0x18004743f  jmp     short loc_180047481
0x180047441  mov     edi, 4
0x180047446  mov     r14, [rbp+Src]
0x18004744a  mov     r9d, 2
0x180047450  mov     r8, r14
0x180047453  xor     edx, edx
0x180047455  lea     rcx, [rsi+8]
0x180047459  call    cs:__imp_InvCacheOpenVerProvider
0x18004745f  mov     ebx, eax
0x180047461  test    eax, eax
0x180047463  jns     short loc_180047477
0x180047465  add     edi, r15d
0x180047468  jz      short loc_180047477
0x18004746a  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18004746f  call    cs:__imp_Sleep
0x180047475  jmp     short loc_18004744A
0x180047477  lea     rdi, [r12+68h]
0x18004747c  lea     r14, [r12+58h]
0x180047481  mov     rcx, [rbp+hLibModule]; hLibModule
0x180047485  call    cs:__imp_FreeLibrary
0x18004748b  test    ebx, ebx
0x18004748d  jns     short loc_1800474E6
0x18004748f  mov     sil, 1
0x180047492  cmp     ebx, 80004002h
0x180047498  jz      short loc_1800474BF
0x18004749a  cmp     ebx, 80070005h
0x1800474a0  jz      short loc_1800474BF
0x1800474a2  cmp     ebx, 80070020h
0x1800474a8  jz      short loc_1800474BF
0x1800474aa  cmp     ebx, 80070522h
0x1800474b0  jz      short loc_1800474BF
0x1800474b2  mov     ecx, 1
0x1800474b7  mov     r8d, 29Dh
0x1800474bd  jmp     short loc_1800474CA
0x1800474bf  mov     ecx, 3
0x1800474c4  mov     r8d, 299h
0x1800474ca  mov     [rsp+58h+var_38], ebx
0x1800474ce  lea     r9, aAepicinvcacheI; "AepicInvCache::Initialize failed [%#x]"
0x1800474d5  lea     rdx, aTelcacheprovid_13; "TelCacheProvider::Initialize"
0x1800474dc  call    AslLogCallPrintf
0x1800474e1  jmp     loc_18004783D
0x1800474e6  mov     rax, [rsi]
0x1800474e9  lea     r8, [rbp+arg_18]
0x1800474ed  lea     rdx, aProviderversio; "ProviderVersion"
0x1800474f4  mov     rcx, rsi
0x1800474f7  mov     rax, [rax+48h]
0x1800474fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047500  mov     ebx, eax
0x180047502  cmp     eax, 80070002h
0x180047507  jnz     short loc_18004753B
0x180047509  mov     [rbp+arg_18], 0
0x180047510  xor     r8d, r8d; unsigned int
0x180047513  mov     rdx, rsi; struct Windows::Compat::Inventory::InventoryCache *
0x180047516  call    ?SetVersion@TelCacheProvider@@AEAAJPEAVInventoryCache@Inventory@Compat@Windows@@K@Z; TelCacheProvider::SetVersion(Windows::Compat::Inventory::InventoryCache *,ulong)
0x18004751b  mov     ebx, eax
0x18004751d  test    eax, eax
0x18004751f  jns     short loc_180047534
0x180047521  mov     [rsp+58h+var_38], eax
0x180047525  lea     r9, aTelcacheprovid_11; "TelCacheProvider::SetVersion [%#x]"
0x18004752c  mov     r8d, 2B6h
0x180047532  jmp     short loc_180047572
0x180047534  xor     eax, eax
0x180047536  mov     [rbp+arg_18], eax
0x180047539  jmp     short loc_18004758F
0x18004753b  test    ebx, ebx
0x18004753d  jns     short loc_18004758C
0x18004753f  mov     [rsp+58h+var_38], ebx
0x180047543  lea     r9, aInventorycache_0; "InventoryCache::GetMetadata [%#x]"
0x18004754a  mov     r8d, 709h
0x180047550  lea     rdx, aTelcacheprovid_18; "TelCacheProvider::GetVersion"
0x180047557  mov     ecx, 1
0x18004755c  call    AslLogCallPrintf
0x180047561  mov     [rsp+58h+var_38], ebx
0x180047565  lea     r9, aTelcacheprovid_7; "TelCacheProvider::GetVersion failed [%#"...
0x18004756c  mov     r8d, 2ACh
0x180047572  lea     rdx, aTelcacheprovid_13; "TelCacheProvider::Initialize"
0x180047579  mov     ecx, 1
0x18004757e  call    AslLogCallPrintf
0x180047583  mov     [rbp+arg_0], rsi
0x180047587  jmp     loc_180047A86
0x18004758c  mov     eax, [rbp+arg_18]
0x18004758f  mov     rbx, rsi
0x180047592  mov     [rbp+arg_0], rbx
0x180047596  test    eax, eax
0x180047598  jz      short loc_1800475C3
0x18004759a  mov     rax, [rbp+Src]
0x18004759e  mov     qword ptr [rsp+58h+var_38], rax
0x1800475a3  lea     r9, aLsProvidervers; "%ls ProviderVersion did not match Reque"...
0x1800475aa  mov     r8d, 2BEh
0x1800475b0  lea     rdx, aTelcacheprovid_13; "TelCacheProvider::Initialize"
0x1800475b7  mov     ecx, 3
0x1800475bc  call    AslLogCallPrintf
0x1800475c1  jmp     short loc_18004761B
0x1800475c3  mov     [r14], rbx
0x1800475c6  xor     eax, eax
0x1800475c8  mov     [rbp+arg_0], rax
0x1800475cc  mov     [rbp+arg_28], eax
0x1800475cf  mov     rcx, [r12]
0x1800475d3  test    rcx, rcx
0x1800475d6  jz      short loc_18004761B
0x1800475d8  mov     rax, [rcx]
0x1800475db  mov     rax, [rax+38h]
0x1800475df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800475e4  test    al, al
0x1800475e6  jz      short loc_18004761B
0x1800475e8  mov     rcx, [r14]
0x1800475eb  mov     rax, [rcx]
0x1800475ee  lea     rdx, [rbp+arg_28]
0x1800475f2  mov     rax, [rax+20h]
0x1800475f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800475fb  test    eax, eax
0x1800475fd  js      short loc_18004761B
0x1800475ff  cmp     [rbp+arg_28], 0
0x180047603  jbe     short loc_18004761B
0x180047605  mov     rdx, [rbp+Src]; unsigned __int16 *
0x180047609  mov     rcx, r12; this
0x18004760c  call    ?ShouldForceFullSync@TelCacheProvider@@AEAAHPEBG@Z; TelCacheProvider::ShouldForceFullSync(ushort const *)
0x180047611  test    eax, eax
0x180047613  jz      short loc_18004761B
0x180047615  mov     byte ptr [r12+61h], 1
0x18004761b  cmp     byte ptr [rdi+24h], 0
0x18004761f  jz      short loc_18004763C
0x180047621  xor     cl, cl
0x180047623  mov     rax, [rdi+18h]
0x180047627  cmp     dword ptr [rax+4], 1
0x18004762b  jnz     short loc_180047632
0x18004762d  mov     [rdi+24h], cl
0x180047630  mov     cl, 1
0x180047632  add     [rax+4], r15d
0x180047636  test    cl, cl
0x180047638  jz      short loc_18004766A
0x18004763a  jmp     short loc_180047660
0x18004763c  mov     edx, r15d; dwMilliseconds
0x18004763f  mov     rcx, [rdi]; hHandle
0x180047642  call    cs:__imp_WaitForSingleObject
0x180047648  test    eax, eax
0x18004764a  jnz     short loc_18004766A
0x18004764c  mov     rax, [rdi+18h]
0x180047650  add     [rax], r15d
0x180047653  add     [rdi+20h], r15d
0x180047657  mov     rcx, [rdi]; hMutex
0x18004765a  call    cs:__imp_ReleaseMutex
0x180047660  mov     rcx, [rdi+10h]; hEvent
0x180047664  call    cs:__imp_SetEvent
0x18004766a  xor     sil, sil
0x18004766d  jmp     loc_18004783D
0x180047672  mov     rcx, [r12]
0x180047676  test    rcx, rcx
0x180047679  jz      short loc_18004769E
0x18004767b  mov     rax, [rcx]
0x18004767e  lea     rdx, [rbp+var_20]
0x180047682  mov     rax, [rax+40h]
0x180047686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004768b  mov     r15d, 1
0x180047691  mov     [rbp+arg_20], r15d
0x180047695  mov     rcx, [rax+8]
0x180047699  cmp     [rax], rcx
0x18004769c  jnz     short loc_1800476A0
0x18004769e  mov     bl, 1
0x1800476a0  test    r15b, 1
0x1800476a4  jz      short loc_1800476B7
0x1800476a6  and     r15d, 0FFFFFFFEh
0x1800476aa  mov     [rbp+arg_20], r15d
0x1800476ae  lea     rcx, [rbp+var_20]
0x1800476b2  call    ??1?$vector@U_CacheItemProperty@IAmiInventoryItem@@V?$allocator@U_CacheItemProperty@IAmiInventoryItem@@@std@@@std@@QEAA@XZ; std::vector<IAmiInventoryItem::_CacheItemProperty>::~vector<IAmiInventoryItem::_CacheItemProperty>(void)
0x1800476b7  lea     rdx, aTelcacheprovid_13; "TelCacheProvider::Initialize"
0x1800476be  test    bl, bl
0x1800476c0  jz      short loc_1800476DF
0x1800476c2  mov     eax, 80070057h
0x1800476c7  mov     ebx, eax
0x1800476c9  mov     [rsp+58h+var_38], eax
0x1800476cd  lea     r9, aItemtemplateIs; "ItemTemplate is null or has no schema f"...
0x1800476d4  mov     r8d, 258h
0x1800476da  jmp     loc_180047346
0x1800476df  mov     qword ptr [rsp+58h+var_38], rsi; unsigned int
0x1800476e4  lea     r9, aUsingSqliteCac; "Using SQLite cache provider: %ls."
0x1800476eb  mov     r8d, 25Dh
0x1800476f1  mov     ecx, 3
0x1800476f6  call    AslLogCallPrintf
0x1800476fb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180047702  mov     ecx, 0F0h; unsigned __int64
0x180047707  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004770c  mov     [rbp+arg_10], rax
0x180047710  test    rax, rax
0x180047713  jz      short loc_180047722
0x180047715  mov     rcx, rax; this
0x180047718  call    ??0SqliteInvCache@Inventory@Compat@Windows@@QEAA@XZ; Windows::Compat::Inventory::SqliteInvCache::SqliteInvCache(void)
0x18004771d  mov     rbx, rax
0x180047720  jmp     short loc_180047724
0x180047722  xor     ebx, ebx
0x180047724  test    rbx, rbx
0x180047727  jnz     short loc_180047733
0x180047729  mov     ebx, 8007000Eh
0x18004772e  jmp     loc_180047AD9
0x180047733  mov     rcx, rdi; this
0x180047736  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x18004773b  xor     r9d, r9d; int
0x18004773e  mov     r8, [r12]; struct IAmiInventoryItem *
0x180047742  mov     rdx, rsi; Src
0x180047745  mov     rcx, rbx; this
0x180047748  call    ?Initialize@SqliteInvCache@Inventory@Compat@Windows@@QEAAJPEBGPEAVIAmiInventoryItem@@HK@Z; Windows::Compat::Inventory::SqliteInvCache::Initialize(ushort const *,IAmiInventoryItem *,int,ulong)
0x18004774d  test    eax, eax
0x18004774f  js      short loc_1800477A8
0x180047751  mov     [r14], rbx
0x180047754  mov     [rbp+arg_28], 0
0x18004775b  mov     rcx, [r12]
0x18004775f  test    rcx, rcx
  ... truncated ...
```
