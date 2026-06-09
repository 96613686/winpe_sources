# PushRouter::ProcessPersistedMessages(ushort const *,ushort const *,PushRouter *,int,int *)

- ea: `0x180015500`
- end: `0x180016109`
- name: `?ProcessPersistedMessages@PushRouter@@CAJPEBG0PEAV1@HPEAH@Z`
- size: `3081`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct PushRouter *, signed int, int *)`
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000f9f0`
- `0x180014dcc`

## callees

- `0x180001464`
- `0x1800039f0`
- `0x180003a14`
- `0x1800043a8`
- `0x180006090`
- `0x1800060b4`
- `0x18000c504`
- `0x18000c63c`
- `0x18000dc6c`
- `0x18000e860`
- `0x180012bec`
- `0x180013758`
- `0x180013b14`
- `0x180013cdc`
- `0x180013d4c`
- `0x180014a58`
- `0x180014da4`
- `0x18001517c`
- `0x180015500`
- `0x180017788`
- `0x180017838`
- `0x180018060`
- `0x180018858`
- `0x180036338`
- `0x18003b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x18001603a`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x18001603a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016087`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016087`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015a60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015a8b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015f36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015a60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015a8b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015f36`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015a0d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015a7e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015edf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015a0d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015a7e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015edf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015feb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015feb`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180015786`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180015786`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180015d41`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180015d41`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180015e53`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180016074`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180015e53`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180016074`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180015fff`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180015fff`

## pseudocode

```c
__int64 __fastcall PushRouter::ProcessPersistedMessages(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct PushRouter *a3,
        signed int a4,
        int *a5)
{
  char *v9; // r14
  const unsigned __int16 *v10; // r8
  signed int List; // esi
  __int64 v12; // r15
  __int64 v13; // rax
  __int64 v14; // rcx
  WCHAR *v15; // rdx
  unsigned __int16 v16; // r9
  WCHAR *v17; // rax
  __int64 v18; // rdx
  unsigned __int16 *v19; // rax
  BOOL i; // eax
  __int64 v21; // rax
  __int64 v22; // rcx
  WCHAR *v23; // rdx
  unsigned __int16 v24; // r9
  WCHAR *v25; // rax
  __int64 v26; // rax
  int v27; // eax
  __int64 v28; // rcx
  char *v29; // rax
  int v30; // eax
  struct IPersistStore *v31; // rbx
  int v32; // ebx
  __int64 v33; // rcx
  unsigned int v34; // ebx
  signed int GenIdFromQueueId; // eax
  int v36; // edx
  int v37; // ecx
  int v38; // eax
  __int64 v39; // rcx
  int v40; // eax
  int v41; // ecx
  __int64 v42; // rax
  const struct std::nothrow_t *v43; // rax
  const struct std::nothrow_t *v44; // rbx
  const unsigned __int16 *v45; // rax
  __int64 v46; // rcx
  const struct std::nothrow_t *v47; // rdx
  unsigned __int16 v48; // r8
  const struct std::nothrow_t *v49; // rax
  int v50; // eax
  __int64 v51; // rcx
  signed int LastError; // eax
  __int64 v53; // rcx
  int v54; // eax
  __int64 v55; // rcx
  struct PushRouter *v56; // r14
  struct _RTL_CRITICAL_SECTION *v57; // r12
  struct IPersistStore *v58; // r15
  unsigned int *v59; // rcx
  unsigned int *v60; // rbx
  const unsigned __int16 *v61; // rsi
  signed int v62; // eax
  __int64 v63; // rcx
  _BYTE *v65; // [rsp+20h] [rbp-7F8h]
  int v66; // [rsp+30h] [rbp-7E8h]
  unsigned int v67; // [rsp+34h] [rbp-7E4h] BYREF
  struct IPersistStore *v68; // [rsp+38h] [rbp-7E0h] BYREF
  signed int v69; // [rsp+40h] [rbp-7D8h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-7D0h] BYREF
  HANDLE hFindFile; // [rsp+50h] [rbp-7C8h]
  const unsigned __int16 *v72; // [rsp+58h] [rbp-7C0h]
  __int128 v73; // [rsp+60h] [rbp-7B8h] BYREF
  __int64 v74; // [rsp+70h] [rbp-7A8h]
  struct PushClient *v75; // [rsp+78h] [rbp-7A0h] BYREF
  HANDLE v76; // [rsp+80h] [rbp-798h]
  const unsigned __int16 *v77; // [rsp+88h] [rbp-790h]
  struct PushRouter *v78; // [rsp+90h] [rbp-788h]
  char *v79; // [rsp+98h] [rbp-780h]
  char v80; // [rsp+A0h] [rbp-778h]
  const struct std::nothrow_t *v81; // [rsp+B0h] [rbp-768h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+C0h] [rbp-758h] BYREF
  _BYTE v83[16]; // [rsp+310h] [rbp-508h] BYREF
  WCHAR *v84; // [rsp+320h] [rbp-4F8h]
  __int64 v85; // [rsp+328h] [rbp-4F0h]
  WCHAR Src[264]; // [rsp+330h] [rbp-4E8h] BYREF
  _WORD v87[64]; // [rsp+540h] [rbp-2D8h] BYREF
  WCHAR FileName[264]; // [rsp+5C0h] [rbp-258h] BYREF

  v69 = a4;
  v78 = a3;
  v72 = a1;
  v77 = a1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  hFindFile = 0;
  v68 = 0;
  v9 = 0;
  v75 = 0;
  hMem = 0;
  memset_0(FileName, 0, 0x208u);
  memset_0(Src, 0, 0x208u);
  memset_0(v87, 0, sizeof(v87));
  v67 = 0;
  v73 = 0;
  v74 = 0;
  if ( (unsigned int)dword_180050060 > 5 )
  {
    LODWORD(v65) = 2;
    tlgWriteTransfer_EventWriteTransfer(&dword_180050060, byte_18004665D, 0);
  }
  if ( a4 )
  {
    if ( !a5 )
    {
LABEL_5:
      List = -2147024809;
      v66 = -2147024809;
      goto LABEL_6;
    }
LABEL_10:
    *a5 = 0;
    goto LABEL_11;
  }
  if ( !a3 )
    goto LABEL_5;
  if ( a5 )
    goto LABEL_10;
LABEL_11:
  v12 = 2147483646;
  v13 = 2147483646;
  v10 = a1;
  v14 = 260;
  v15 = FileName;
  do
  {
    if ( !v13 )
      break;
    v16 = *v10;
    if ( !*v10 )
      break;
    ++v10;
    *v15++ = v16;
    --v13;
    --v14;
  }
  while ( v14 );
  List = v14 == 0 ? 0x8007007A : 0;
  v66 = List;
  v17 = v15 - 1;
  if ( v14 )
    v17 = v15;
  *v17 = 0;
  if ( !v14 )
    goto LABEL_6;
  List = StringCchCatW(FileName, 0x104u, L"\\");
  v66 = List;
  if ( List < 0 )
    goto LABEL_6;
  List = StringCchCatW(FileName, 0x104u, a2);
  v66 = List;
  if ( List < 0 )
    goto LABEL_6;
  v18 = 0x7FFFFFFF;
  v19 = aQueue;
  do
  {
    if ( !*v19 )
      break;
    ++v19;
    --v18;
  }
  while ( v18 );
  List = v18 == 0 ? 0x80070057 : 0;
  v66 = List;
  if ( v18 )
  {
    hFindFile = FindFirstFileW(FileName, &FindFileData);
    v76 = hFindFile;
    for ( i = (char *)hFindFile + 1 != 0; ; i = FindNextFileW(hFindFile, &FindFileData) )
    {
      v66 = List;
      if ( !i )
        break;
      v21 = 2147483646;
      v10 = v72;
      v22 = 260;
      v23 = Src;
      do
      {
        if ( !v21 )
          break;
        v24 = *v10;
        if ( !*v10 )
          break;
        ++v10;
        *v23++ = v24;
        --v21;
        --v22;
      }
      while ( v22 );
      v25 = v23 - 1;
      if ( v22 )
        v25 = v23;
      *v25 = 0;
      List = v22 == 0 ? 0x8007007A : 0;
      v66 = List;
      v9 = 0;
      if ( !v22 )
        goto LABEL_6;
      List = StringCchCatW(Src, 0x104u, L"\\");
      v66 = List;
      if ( List < 0 )
        goto LABEL_6;
      List = StringCchCatW(Src, 0x104u, FindFileData.cFileName);
      v66 = List;
      if ( List < 0 )
        goto LABEL_6;
      if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
      {
        v26 = -1;
        do
          ++v26;
        while ( Src[v26] );
        v84 = Src;
        v85 = (unsigned int)(2 * v26 + 2);
        v65 = v83;
        McGenEventWrite_EventWriteTransfer(MDM_PUSHROUTER_Context, PushRouterPersistenceQueueFileFound, v10, 2);
      }
      v27 = PersistXmlStore::CreatePersistXmlStore(Src, &v68);
      if ( v27 >= 0 )
      {
        v29 = (char *)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
        v9 = v29;
        v81 = (const struct std::nothrow_t *)v29;
        if ( v29 )
        {
          *(_QWORD *)v29 = &PersistList::`vftable';
          *((_QWORD *)v29 + 1) = 0;
          *((_QWORD *)v29 + 2) = 0;
          *((_QWORD *)v29 + 3) = 0;
          *((_QWORD *)v29 + 4) = 0;
          *(_OWORD *)(v29 + 40) = 0;
          *(_OWORD *)(v29 + 56) = 0;
          *((_QWORD *)v29 + 9) = 0;
          v30 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v29 + 40));
          if ( v30 < 0 )
            ATL::AtlThrowImpl(v30);
        }
        else
        {
          v9 = 0;
        }
        if ( !v9 )
        {
LABEL_52:
          List = -2147024882;
          v66 = -2147024882;
          goto LABEL_6;
        }
        v79 = v9 + 40;
        EnterCriticalSection((LPCRITICAL_SECTION)v9 + 1);
        v80 = 1;
        if ( *((_DWORD *)v9 + 7) )
        {
          List = -2147023649;
          v66 = -2147023649;
        }
        else
        {
          v31 = v68;
          List = 0;
          v66 = 0;
          if ( !v68 || (List = PersistList::LoadList((PersistList *)v9, v68), v66 = List, List >= 0) )
          {
            *((_QWORD *)v9 + 4) = v31;
            *((_DWORD *)v9 + 7) = 1;
          }
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)v9 + 1);
        v80 = 0;
        if ( List < 0 )
          goto LABEL_6;
        v68 = 0;
        EnterCriticalSection((LPCRITICAL_SECTION)v9 + 1);
        v32 = *((_DWORD *)v9 + 4);
        LeaveCriticalSection((LPCRITICAL_SECTION)v9 + 1);
        if ( v32 )
        {
          if ( a5 )
            *a5 = 1;
          if ( v69 )
            goto LABEL_127;
          (**(void (__fastcall ***)(char *, __int64))v9)(v9, 1);
          v9 = 0;
          List = PushRouter::GetQueueIdFromFileName(FindFileData.cFileName, &v67);
          v66 = List;
          if ( List < 0 )
            goto LABEL_6;
          v34 = v67;
          if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
            McTemplateU0zd_EventWriteTransfer(v33, PushRouterFoundQueueForPersistedMessage, Src, v67, v65);
          GenIdFromQueueId = GetGenIdFromQueueId(v34, (unsigned __int16 **)&hMem);
          List = GenIdFromQueueId;
          v66 = GenIdFromQueueId;
          if ( GenIdFromQueueId == -2147023728 || GenIdFromQueueId == -2147024894 )
          {
            if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
              McTemplateU0zdd_EventWriteTransfer(v37, v36, (int)Src, v34, GenIdFromQueueId);
            List = 0;
            if ( __eh34_try(-1, 2) )
            {
              __eh34_scope_strut(2);
              if ( *((_QWORD *)&v73 + 1) == v74 )
              {
                std::vector<unsigned long>::_Emplace_reallocate<unsigned long const &>(
                  &v73,
                  *((_QWORD *)&v73 + 1),
                  &v67);
              }
              else
              {
                **((_DWORD **)&v73 + 1) = v34;
                *((_QWORD *)&v73 + 1) += 4LL;
              }
            }
            if ( __eh34_catch(2) )
            {
              if ( __eh34_catch_type(2, &std::bad_alloc `RTTI Type Descriptor', 0) )
              {
                v67 = -2147024882;
                List = -2147024882;
                hFindFile = v76;
                v66 = -2147024882;
                v9 = 0;
                v72 = v77;
                __eh34_try_continuation(2, &std::bad_alloc `RTTI Type Descriptor', &loc_180015C86);
                goto LABEL_6;
              }
            }
          }
          else
          {
            if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
              McTemplateU0zzdd_EventWriteTransfer(
                v37,
                (int)PushRouterClientFoundForQueueForPersistedMessage,
                (int)Src,
                (int)hMem,
                v34,
                GenIdFromQueueId);
            if ( List < 0 )
              goto LABEL_6;
            v38 = PersistXmlStore::CreatePersistXmlStore(Src, &v68);
            List = v38;
            v66 = v38;
            if ( v38 < 0 )
            {
              if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
                McTemplateU0zd_EventWriteTransfer(v39, PushRouterFailedToLoadPeristedFile, Src, (unsigned int)v38, v65);
              goto LABEL_6;
            }
            if ( !v68 )
              goto LABEL_52;
            List = PushClient::CreateClient((const unsigned __int16 *)hMem, v68, &v75);
            v66 = List;
            if ( List < 0 )
              goto LABEL_6;
            v68 = 0;
            CTList<PushClient>::AddHead((char *)v78 + 24, v75);
            v40 = PushClient::LaunchRegisteredApp(v75);
            List = v40;
            v66 = v40;
            if ( v40 < 0 )
            {
              if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
                McTemplateU0zzdd_EventWriteTransfer(
                  v41,
                  (int)PushRouterFailedToLaunchRegisteredApp,
                  (int)Src,
                  (int)hMem,
                  v34,
                  v40);
              goto LABEL_6;
            }
          }
        }
        else
        {
          if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
          {
            v42 = -1;
            do
              ++v42;
            while ( Src[v42] );
            v84 = Src;
            v85 = (unsigned int)(2 * v42 + 2);
            v65 = v83;
            McGenEventWrite_EventWriteTransfer(
              MDM_PUSHROUTER_Context,
              PushRouterNoPersistedMessageFoundInQueueFile,
              v10,
              2);
          }
          (**(void (__fastcall ***)(char *, __int64))v9)(v9, 1);
        }
        v12 = 2147483646;
      }
      else
      {
        if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
          McTemplateU0zd_EventWriteTransfer(v28, PushRouterFailedToLoadPeristedFile, Src, (unsigned int)v27, v65);
        List = PushRouter::GetQueueIdFromFileName(FindFileData.cFileName, &v67);
        v66 = List;
        v9 = 0;
        if ( List < 0 )
          goto LABEL_6;
        List = 0;
        if ( __eh34_try(-1, 0) )
        {
          __eh34_scope_strut(0);
          if ( *((_QWORD *)&v73 + 1) == v74 )
          {
            std::vector<unsigned long>::_Emplace_reallocate<unsigned long const &>(&v73, *((_QWORD *)&v73 + 1), &v67);
          }
          else
          {
            **((_DWORD **)&v73 + 1) = v67;
            *((_QWORD *)&v73 + 1) += 4LL;
          }
        }
        if ( __eh34_catch(0) )
        {
          if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
          {
            v67 = -2147024882;
            List = -2147024882;
            hFindFile = v76;
            v66 = -2147024882;
            v9 = 0;
            v72 = v77;
            __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180015958);
            goto LABEL_6;
          }
        }
      }
      if ( v68 )
        (**(void (__fastcall ***)(struct IPersistStore *, __int64))v68)(v68, 1);
      v68 = 0;
      Src[0] = 0;
    }
    if ( v69 )
    {
      v9 = 0;
      if ( List < 0 )
        goto LABEL_6;
    }
    else
    {
      v43 = (const struct std::nothrow_t *)operator new[](0x208u, (const struct std::nothrow_t *)&std::nothrow);
      v44 = v43;
      v81 = v43;
      if ( !v43 )
      {
        List = -2147024882;
        v66 = -2147024882;
LABEL_97:
        v9 = 0;
        goto LABEL_6;
      }
      *(_WORD *)v43 = 0;
      v45 = v72;
      v46 = 260;
      v47 = v44;
      do
      {
        if ( !v12 )
          break;
        v48 = *v45;
        if ( !*v45 )
          break;
        ++v45;
        *(_WORD *)v47 = v48;
        v47 = (const struct std::nothrow_t *)((char *)v47 + 2);
        --v12;
        --v46;
      }
      while ( v46 );
      List = v46 == 0 ? 0x8007007A : 0;
      v66 = List;
      v49 = (const struct std::nothrow_t *)((char *)v47 - 2);
      if ( v46 )
        v49 = v47;
      *(_WORD *)v49 = 0;
      if ( !v46
        || (List = StringCchCatW((unsigned __int16 *)v44, 0x104u, L"\\"), v66 = List, List < 0)
        || (List = StringCchCatW((unsigned __int16 *)v44, 0x104u, L"unauthmessages"), v66 = List, List < 0) )
      {
LABEL_105:
        operator delete(v44, v47);
        goto LABEL_97;
      }
      v50 = PersistXmlStore::CreatePersistXmlStore((const unsigned __int16 *)v44, &v68);
      if ( v50 < 0 )
      {
        if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
          McTemplateU0zd_EventWriteTransfer(v51, PushRouterFailedToLoadMessageFile, v44, (unsigned int)v50, v65);
        if ( !DeleteFileW((LPCWSTR)v44) && (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          McTemplateU0zd_EventWriteTransfer(v53, PushRouterFailedToDeleteMessageFile, v44, (unsigned int)LastError, v65);
        }
        v54 = PersistXmlStore::CreatePersistXmlStore((const unsigned __int16 *)v44, &v68);
        List = v54;
        v66 = v54;
        if ( v54 < 0 )
        {
          if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
            McTemplateU0zd_EventWriteTransfer(v55, PushRouterFailedToLoadMessageFile, v44, (unsigned int)v54, v65);
          goto LABEL_105;
        }
      }
      v56 = v78;
      v57 = (struct _RTL_CRITICAL_SECTION *)((char *)v78 + 136);
      v79 = (char *)v78 + 136;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v78 + 136));
      v80 = 1;
      if ( *((_DWORD *)v56 + 31) )
      {
        List = -2147023649;
        v66 = -2147023649;
      }
      else
      {
        v58 = v68;
        List = 0;
        v66 = 0;
        if ( !v68 || (List = PersistList::LoadList((struct PushRouter *)((char *)v56 + 96), v68), v66 = List, List >= 0) )
        {
          *((_QWORD *)v56 + 16) = v58;
          *((_DWORD *)v56 + 31) = 1;
        }
      }
      LeaveCriticalSection(v57);
      if ( List < 0 )
        goto LABEL_105;
      v68 = 0;
      operator delete(v44, v47);
      v9 = 0;
    }
LABEL_127:
    if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
    {
      v69 = List;
      v84 = (WCHAR *)&v69;
      v85 = 4;
      McGenEventWrite_EventWriteTransfer(MDM_PUSHROUTER_Context, PushRouterProcessPersistedMessagesSucceeded, v10, 2);
    }
  }
  else
  {
LABEL_6:
    if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
    {
      v69 = List;
      v84 = (WCHAR *)&v69;
      v85 = 4;
      McGenEventWrite_EventWriteTransfer(MDM_PUSHROUTER_Context, PushRouterProcessPersistedMessagesFailed, v10, 2);
    }
  }
  if ( v68 )
    (**(void (__fastcall ***)(struct IPersistStore *, __int64))v68)(v68, 1);
  if ( v9 )
    (**(void (__fastcall ***)(char *, __int64))v9)(v9, 1);
  LocalFree(hMem);
  if ( hFindFile != (HANDLE)-1LL )
    FindClose(hFindFile);
  v59 = (unsigned int *)*((_QWORD *)&v73 + 1);
  v60 = (unsigned int *)v73;
  if ( *((_QWORD *)&v73 + 1) != (_QWORD)v73 )
  {
    v61 = v72;
    while ( v60 != v59 )
    {
      _o__itow_s(*v60, v87, 64);
      StringCchPrintfW(Src, 0x104u, L"%s\\%s%s", v61);
      if ( !DeleteFileW(Src) && (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
      {
        v62 = GetLastError();
        if ( v62 > 0 )
          v62 = (unsigned __int16)v62 | 0x80070000;
        McTemplateU0zd_EventWriteTransfer(v63, PushRouterFailedToDeleteMessageFile, Src, (unsigned int)v62, v87);
      }
      Src[0] = 0;
      v87[0] = 0;
      ++v60;
      v59 = (unsigned int *)*((_QWORD *)&v73 + 1);
    }
    List = v66;
  }
  std::vector<unsigned long>::~vector<unsigned long>(&v73);
  return (unsigned int)List;
}

```

## disassembly

```asm
0x180015500  push    rbx
0x180015502  push    rsi
0x180015503  push    rdi
0x180015504  push    r12
0x180015506  push    r13
0x180015508  push    r14
0x18001550a  push    r15
0x18001550c  sub     rsp, 7E0h
0x180015513  mov     rax, cs:__security_cookie
0x18001551a  xor     rax, rsp
0x18001551d  mov     [rsp+818h+var_48], rax
0x180015525  mov     esi, r9d
0x180015528  mov     [rsp+818h+var_7D8], r9d
0x18001552d  mov     r15, r8
0x180015530  mov     [rsp+818h+var_788], r8
0x180015538  mov     rbx, rdx
0x18001553b  mov     r13, rcx
0x18001553e  mov     [rsp+818h+var_7C0], rcx
0x180015543  mov     [rsp+818h+var_790], rcx
0x18001554b  mov     r12, [rsp+818h+arg_20]
0x180015553  xor     edx, edx; Val
0x180015555  mov     r8d, 250h; Size
0x18001555b  lea     rcx, [rsp+818h+FindFileData]; void *
0x180015563  call    memset_0
0x180015568  xor     edi, edi
0x18001556a  mov     [rsp+818h+hFindFile], rdi
0x18001556f  mov     [rsp+818h+var_7E0], rdi
0x180015574  mov     r14d, edi
0x180015577  mov     [rsp+818h+var_7A0], rdi
0x18001557c  mov     [rsp+818h+hMem], rdi
0x180015581  xor     edx, edx; Val
0x180015583  mov     r8d, 208h; Size
0x180015589  lea     rcx, [rsp+818h+FileName]; void *
0x180015591  call    memset_0
0x180015596  xor     edx, edx; Val
0x180015598  mov     r8d, 208h; Size
0x18001559e  lea     rcx, [rsp+818h+Src]; void *
0x1800155a6  call    memset_0
0x1800155ab  xor     edx, edx; Val
0x1800155ad  mov     r8d, 80h; Size
0x1800155b3  lea     rcx, [rsp+818h+var_2D8]; void *
0x1800155bb  call    memset_0
0x1800155c0  mov     [rsp+818h+var_7E4], edi
0x1800155c4  xorps   xmm0, xmm0
0x1800155c7  movdqu  [rsp+818h+var_7B8], xmm0
0x1800155cd  mov     [rsp+818h+var_7A8], rdi
0x1800155d2  mov     eax, cs:dword_180050060
0x1800155d8  cmp     eax, 5
0x1800155db  jbe     short loc_18001560B
0x1800155dd  lea     rax, [rsp+818h+var_508]
0x1800155e5  mov     [rsp+818h+var_7F0], rax
0x1800155ea  mov     dword ptr [rsp+818h+var_7F8], 2
0x1800155f2  xor     r9d, r9d
0x1800155f5  xor     r8d, r8d
0x1800155f8  lea     rdx, byte_18004665D
0x1800155ff  lea     rcx, dword_180050060
0x180015606  call    _tlgWriteTransfer_EventWriteTransfer
0x18001560b  test    esi, esi
0x18001560d  jz      short loc_18001567F
0x18001560f  test    r12, r12
0x180015612  jnz     short loc_180015689
0x180015614  mov     esi, 80070057h
0x180015619  mov     [rsp+818h+var_7E8], esi
0x18001561d  mov     r13d, 104h
0x180015623  lea     r15, aQueue; ".queue"
0x18001562a  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 1
0x180015631  jz      loc_180015FB4
0x180015637  mov     [rsp+818h+var_7D8], esi
0x18001563b  lea     rax, [rsp+818h+var_7D8]
0x180015640  mov     [rsp+818h+var_4F8], rax
0x180015648  mov     [rsp+818h+var_4F0], 4
0x180015654  lea     rax, [rsp+818h+var_508]
0x18001565c  mov     [rsp+818h+var_7F8], rax
0x180015661  mov     r9d, 2
0x180015667  lea     rdx, PushRouterProcessPersistedMessagesFailed
0x18001566e  lea     rcx, MDM_PUSHROUTER_Context
0x180015675  call    McGenEventWrite_EventWriteTransfer
0x18001567a  jmp     loc_180015FB4
0x18001567f  test    r15, r15
0x180015682  jz      short loc_180015614
0x180015684  test    r12, r12
0x180015687  jz      short loc_18001568D
0x180015689  mov     [r12], edi
0x18001568d  mov     r15d, 7FFFFFFEh
0x180015693  mov     eax, r15d
0x180015696  mov     r8, r13
0x180015699  mov     r13d, 104h
0x18001569f  mov     ecx, r13d
0x1800156a2  lea     rdx, [rsp+818h+FileName]
0x1800156aa  test    rax, rax
0x1800156ad  jz      short loc_1800156CE
0x1800156af  movzx   r9d, word ptr [r8]
0x1800156b3  test    r9w, r9w
0x1800156b7  jz      short loc_1800156CE
0x1800156b9  add     r8, 2
0x1800156bd  mov     [rdx], r9w
0x1800156c1  add     rdx, 2
0x1800156c5  dec     rax
0x1800156c8  sub     rcx, 1
0x1800156cc  jnz     short loc_1800156AA
0x1800156ce  mov     rax, rcx
0x1800156d1  neg     rax
0x1800156d4  sbb     esi, esi
0x1800156d6  not     esi
0x1800156d8  and     esi, 8007007Ah
0x1800156de  mov     [rsp+818h+var_7E8], esi
0x1800156e2  lea     rax, [rdx-2]
0x1800156e6  test    rcx, rcx
0x1800156e9  cmovnz  rax, rdx
0x1800156ed  mov     [rax], di
0x1800156f0  jz      loc_180015623
0x1800156f6  lea     r8, StringValue; "\\"
0x1800156fd  mov     rdx, r13; unsigned __int64
0x180015700  lea     rcx, [rsp+818h+FileName]; unsigned __int16 *
0x180015708  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001570d  mov     esi, eax
0x18001570f  mov     [rsp+818h+var_7E8], eax
0x180015713  test    eax, eax
0x180015715  js      loc_180015623
0x18001571b  mov     r8, rbx; unsigned __int16 *
0x18001571e  mov     rdx, r13; unsigned __int64
0x180015721  lea     rcx, [rsp+818h+FileName]; unsigned __int16 *
0x180015729  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001572e  mov     esi, eax
0x180015730  mov     [rsp+818h+var_7E8], eax
0x180015734  test    eax, eax
0x180015736  js      loc_180015623
0x18001573c  mov     edx, 7FFFFFFFh
0x180015741  lea     rax, aQueue; ".queue"
0x180015748  cmp     [rax], di
0x18001574b  jz      short loc_180015757
0x18001574d  add     rax, 2
0x180015751  sub     rdx, 1
0x180015755  jnz     short loc_180015748
0x180015757  mov     rax, rdx
0x18001575a  neg     rax
0x18001575d  sbb     ecx, ecx
0x18001575f  not     ecx
0x180015761  and     ecx, 80070057h
0x180015767  mov     esi, ecx
0x180015769  mov     [rsp+818h+var_7E8], ecx
0x18001576d  test    rdx, rdx
0x180015770  jz      loc_180015623
0x180015776  lea     rdx, [rsp+818h+FindFileData]; lpFindFileData
0x18001577e  lea     rcx, [rsp+818h+FileName]; lpFileName
0x180015786  call    cs:__imp_FindFirstFileW
0x18001578c  mov     rcx, rax
0x18001578f  mov     [rsp+818h+hFindFile], rax
0x180015794  mov     [rsp+818h+var_798], rax
0x18001579c  mov     eax, edi
0x18001579e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800157a2  setnz   al
0x1800157a5  mov     [rsp+818h+var_7E8], esi
0x1800157a9  test    eax, eax
0x1800157ab  jz      loc_180015D4C
0x1800157b1  mov     rax, r15
0x1800157b4  mov     r8, [rsp+818h+var_7C0]
0x1800157b9  mov     rcx, r13
0x1800157bc  lea     rdx, [rsp+818h+Src]
0x1800157c4  test    rax, rax
0x1800157c7  jz      short loc_1800157E8
0x1800157c9  movzx   r9d, word ptr [r8]
0x1800157cd  test    r9w, r9w
0x1800157d1  jz      short loc_1800157E8
0x1800157d3  add     r8, 2
0x1800157d7  mov     [rdx], r9w
0x1800157db  add     rdx, 2
0x1800157df  dec     rax
0x1800157e2  sub     rcx, 1
0x1800157e6  jnz     short loc_1800157C4
0x1800157e8  lea     rax, [rdx-2]
0x1800157ec  test    rcx, rcx
0x1800157ef  cmovnz  rax, rdx
0x1800157f3  mov     [rax], di
0x1800157f6  mov     rax, rcx
0x1800157f9  neg     rax
0x1800157fc  sbb     esi, esi
0x1800157fe  not     esi
0x180015800  and     esi, 8007007Ah
0x180015806  mov     [rsp+818h+var_7E8], esi
0x18001580a  mov     r14, rdi
0x18001580d  test    rcx, rcx
0x180015810  jz      loc_180015623
0x180015816  lea     r8, StringValue; "\\"
0x18001581d  mov     rdx, r13; unsigned __int64
0x180015820  lea     rcx, [rsp+818h+Src]; unsigned __int16 *
0x180015828  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001582d  mov     esi, eax
0x18001582f  mov     [rsp+818h+var_7E8], eax
0x180015833  test    eax, eax
0x180015835  js      loc_180015623
0x18001583b  lea     r8, [rsp+818h+FindFileData.cFileName]; unsigned __int16 *
0x180015843  mov     rdx, r13; unsigned __int64
0x180015846  lea     rcx, [rsp+818h+Src]; unsigned __int16 *
0x18001584e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180015853  mov     esi, eax
0x180015855  mov     [rsp+818h+var_7E8], eax
0x180015859  test    eax, eax
0x18001585b  js      loc_180015623
0x180015861  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 2
0x180015868  jz      short loc_1800158CA
0x18001586a  lea     rcx, [rsp+818h+Src]
0x180015872  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015876  inc     rax
0x180015879  cmp     [rcx+rax*2], di
0x18001587d  jnz     short loc_180015876
0x18001587f  lea     eax, ds:2[rax*2]
0x180015886  lea     rcx, [rsp+818h+Src]
0x18001588e  mov     [rsp+818h+var_4F8], rcx
0x180015896  mov     dword ptr [rsp+818h+var_4F0], eax
0x18001589d  mov     dword ptr [rsp+818h+var_4F0+4], edi
0x1800158a4  lea     rax, [rsp+818h+var_508]
0x1800158ac  mov     [rsp+818h+var_7F8], rax
0x1800158b1  mov     r9d, 2
0x1800158b7  lea     rdx, PushRouterPersistenceQueueFileFound
0x1800158be  lea     rcx, MDM_PUSHROUTER_Context
0x1800158c5  call    McGenEventWrite_EventWriteTransfer
0x1800158ca  lea     rdx, [rsp+818h+var_7E0]; struct IPersistStore **
0x1800158cf  lea     rcx, [rsp+818h+Src]; Src
0x1800158d7  call    ?CreatePersistXmlStore@PersistXmlStore@@SAJPEBGPEAPEAVIPersistStore@@@Z; PersistXmlStore::CreatePersistXmlStore(ushort const *,IPersistStore * *)
0x1800158dc  test    eax, eax
0x1800158de  jns     loc_18001598A
0x1800158e4  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 1
0x1800158eb  jz      short loc_180015904
0x1800158ed  mov     r9d, eax
0x1800158f0  lea     r8, [rsp+818h+Src]
0x1800158f8  lea     rdx, PushRouterFailedToLoadPeristedFile
0x1800158ff  call    McTemplateU0zd_EventWriteTransfer
0x180015904  lea     rdx, [rsp+818h+var_7E4]; unsigned int *
0x180015909  lea     rcx, [rsp+818h+FindFileData.cFileName]; unsigned __int16 *
0x180015911  call    ?GetQueueIdFromFileName@PushRouter@@CAJPEBGPEAK@Z; PushRouter::GetQueueIdFromFileName(ushort const *,ulong *)
0x180015916  mov     esi, eax
0x180015918  mov     [rsp+818h+var_7E8], eax
0x18001591c  mov     r14, rdi
0x18001591f  test    eax, eax
0x180015921  js      loc_180015623
0x180015927  mov     esi, edi
0x180015929  mov     rdx, qword ptr [rsp+818h+var_7B8+8]
0x18001592e  cmp     rdx, [rsp+818h+var_7A8]
0x180015933  jz      short loc_180015943
0x180015935  mov     eax, [rsp+818h+var_7E4]
0x180015939  mov     [rdx], eax
0x18001593b  add     qword ptr [rsp+818h+var_7B8+8], 4
0x180015941  jmp     short loc_180015953
0x180015943  lea     r8, [rsp+818h+var_7E4]
0x180015948  lea     rcx, [rsp+818h+var_7B8]
0x18001594d  call    ??$_Emplace_reallocate@AEBK@?$vector@KV?$allocator@K@std@@@std@@AEAAPEAKQEAKAEBK@Z; std::vector<ulong>::_Emplace_reallocate<ulong const &>(ulong * const,ulong const &)
0x180015952  nop
0x180015953  jmp     loc_180015D0D
0x180015958  mov     rax, [rsp+818h+var_798]
0x180015960  mov     esi, [rsp+818h+var_7E4]
0x180015964  xor     edi, edi
0x180015966  mov     [rsp+818h+hFindFile], rax
0x18001596b  mov     [rsp+818h+var_7E8], esi
0x18001596f  mov     r13d, 104h
0x180015975  mov     r14d, edi
0x180015978  mov     rax, [rsp+818h+var_790]
0x180015980  mov     [rsp+818h+var_7C0], rax
0x180015985  jmp     loc_180015623
0x18001598a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015991  mov     ecx, 50h ; 'P'; unsigned __int64
0x180015996  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001599b  mov     r14, rax
0x18001599e  mov     [rsp+818h+var_768], rax
0x1800159a6  test    rax, rax
0x1800159a9  jz      short loc_1800159E8
0x1800159ab  lea     rax, ??_7PersistList@@6B@; const PersistList::`vftable'
0x1800159b2  mov     [r14], rax
0x1800159b5  mov     [r14+8], rdi
0x1800159b9  mov     [r14+10h], rdi
0x1800159bd  mov     [r14+18h], rdi
0x1800159c1  mov     [r14+20h], rdi
0x1800159c5  lea     rcx, [r14+28h]; this
0x1800159c9  xorps   xmm0, xmm0
0x1800159cc  xor     eax, eax
0x1800159ce  movups  xmmword ptr [rcx], xmm0
0x1800159d1  movups  xmmword ptr [rcx+10h], xmm0
0x1800159d5  mov     [rcx+20h], rax
0x1800159d9  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800159de  test    eax, eax
0x1800159e0  js      loc_180016101
0x1800159e6  jmp     short loc_1800159EB
0x1800159e8  mov     r14, rdi
0x1800159eb  test    r14, r14
0x1800159ee  jnz     short loc_1800159FE
0x1800159f0  mov     esi, 8007000Eh
0x1800159f5  mov     [rsp+818h+var_7E8], esi
0x1800159f9  jmp     loc_180015623
0x1800159fe  lea     r15, [r14+28h]
0x180015a02  mov     [rsp+818h+var_780], r15
0x180015a0a  mov     rcx, r15; lpCriticalSection
0x180015a0d  call    cs:__imp_EnterCriticalSection
0x180015a13  mov     [rsp+818h+var_778], 1
0x180015a1b  cmp     [r14+1Ch], edi
0x180015a1f  jz      short loc_180015A2C
0x180015a21  mov     esi, 800704DFh
0x180015a26  mov     [rsp+818h+var_7E8], esi
0x180015a2a  jmp     short loc_180015A5D
0x180015a2c  mov     rbx, [rsp+818h+var_7E0]
0x180015a31  mov     esi, edi
  ... truncated ...
```
