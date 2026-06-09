# JetTerm(x)

- ea: `0x100287e0`
- end: `0x100291fc`
- name: `_JetTerm@4`
- size: `2588`
- prototype: `JET_ERR __stdcall(JET_INSTANCE instance)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x1001ab50`

## callees

- `0x100287e0`
- `0x1003ee40`
- `0x1004f89d`
- `0x10050190`
- `0x1005814f`
- `0x1005e748`
- `0x10061284`
- `0x100618e6`
- `0x10077bf6`
- `0x10096b0c`
- `0x100b75cd`
- `0x10123110`
- `0x10123c5a`
- `0x10123c92`
- `0x10123ca8`
- `0x10124048`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100288ea`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10028c4e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1002915c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100291a2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100288ea`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10028c4e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1002915c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100291a2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x100289be`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x100289e8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x10028a12`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x10028a97`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x100289be`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x100289e8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x10028a12`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x10028a97`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x10028f31`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x10028f31`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x10029095`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x10029095`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10029007`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10029048`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10029007`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10029048`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10028e7f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10028e7f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10028888`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10028ffe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100291bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100291dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10028888`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10028ffe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100291bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100291dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10028810`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10028fce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10028810`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10028fce`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x10029187`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x10029187`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1002909d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1002909d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1002901c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1002905d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1002901c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1002905d`

## pseudocode

```c
JET_ERR __stdcall JetTerm(JET_INSTANCE instance)
{
  _DWORD *v1; // ecx
  int v2; // edi
  int v3; // eax
  JET_INSTANCE v4; // ebx
  int v5; // eax
  int v7; // esi
  void *v8; // eax
  JET_INSTANCE v9; // esi
  void *v10; // eax
  _DWORD *v11; // edi
  unsigned int v12; // eax
  int v13; // edx
  int v14; // eax
  unsigned int v15; // edi
  int v16; // ebx
  void (__thiscall *v17)(_DWORD); // esi
  int v18; // eax
  void **v19; // ebx
  int v20; // ebx
  int v21; // ecx
  struct Instance *v22; // edi
  _DWORD *v23; // ecx
  Table *v24; // ecx
  Table *v25; // ecx
  void (__thiscall ***v26)(_DWORD, int); // ebx
  unsigned int v27; // esi
  _DWORD *v28; // esi
  int v29; // ecx
  unsigned int v30; // ecx
  struct Instance **v31; // edx
  unsigned int v32; // eax
  unsigned int v33; // eax
  IAccMeth *v34; // ecx
  int v35; // edi
  int v36; // ecx
  int v37; // esi
  int v38; // eax
  unsigned int v39; // ecx
  unsigned int v40; // ecx
  _DWORD *v41; // edx
  unsigned int v42; // eax
  unsigned int v43; // eax
  int v44; // ecx
  unsigned int v45; // ecx
  _DWORD *v46; // edx
  unsigned int v47; // eax
  unsigned int v48; // eax
  _DWORD *v49; // esi
  int v50; // ecx
  unsigned int v51; // ecx
  _DWORD *v52; // edx
  unsigned int v53; // eax
  unsigned int v54; // eax
  volatile signed __int32 *v55; // edi
  int v56; // edi
  unsigned int v57; // esi
  int v58; // ecx
  HANDLE *v59; // eax
  unsigned int j; // ebx
  LPCRITICAL_SECTION v61; // esi
  char *v62; // edi
  void *v63; // ecx
  HANDLE OwningThread; // eax
  struct Err *v65; // ecx
  struct Err *v66; // ecx
  unsigned int k; // edi
  HANDLE *v68; // esi
  JET_INSTANCE v69; // ebx
  JET_ERR v70; // esi
  int v71; // [esp+14h] [ebp-50h] BYREF
  __int64 v72; // [esp+1Ch] [ebp-48h]
  void *v73; // [esp+24h] [ebp-40h]
  _DWORD v74[3]; // [esp+28h] [ebp-3Ch] BYREF
  void *v75; // [esp+34h] [ebp-30h]
  void *v76; // [esp+38h] [ebp-2Ch]
  void **v77; // [esp+3Ch] [ebp-28h]
  int v78; // [esp+40h] [ebp-24h]
  int i; // [esp+44h] [ebp-20h]
  int v80; // [esp+48h] [ebp-1Ch]
  int v81; // [esp+4Ch] [ebp-18h]
  JET_INSTANCE v82; // [esp+50h] [ebp-14h]
  int v83; // [esp+60h] [ebp-4h]

  EnterCriticalSection(critJet);
  v1 = rgtib;
  v2 = 0;
  v3 = dword_1012C324;
  v80 = 0;
  if ( !rgtib )
  {
    v2 = -1;
LABEL_5:
    v80 = v2;
    goto LABEL_6;
  }
  if ( dword_1012C324 != -1 )
  {
    do
    {
      v3 = rgtibNext[v3];
      ++v2;
    }
    while ( v3 != -1 );
    goto LABEL_5;
  }
LABEL_6:
  v4 = instance - 144;
  if ( (int)(instance - 144) <= -1 || v4 >= 0x40 )
  {
    LeaveCriticalSection(critJet);
    return -1029;
  }
  else
  {
    v5 = 2316 * v4;
    v81 = 2316 * v4;
    if ( !*((_DWORD *)rgtib + 579 * v4 + 263) )
    {
      ReleaseTib(instance - 144);
      LeaveCriticalSection(critJet);
      return 0;
    }
    _mm_lfence();
    v7 = *(_DWORD *)((char *)rgtib + v5 + 1216);
    if ( v7 )
    {
      RmtFreeTaskConnections(*(_DWORD *)((char *)rgtib + v5 + 1216));
      pfnSQLFreeEnv(pfnSQLFreeEnv, v7);
      v1 = rgtib;
      v5 = v81;
      *(_DWORD *)((char *)rgtib + v81 + 1216) = 0;
    }
    v8 = *(void **)((char *)v1 + v5 + 1220);
    if ( v8 )
    {
      _free(v8);
      v1 = rgtib;
      *(_DWORD *)((char *)rgtib + v81 + 1220) = 0;
    }
    v9 = instance - 144;
    v82 = instance - 144;
    if ( v2 == 1 )
    {
      v10 = (void *)dword_1013112C;
      v82 = instance - 144;
      if ( dword_1013112C )
      {
        v11 = (_DWORD *)*((_DWORD *)dword_1013112C + 7);
        v82 = instance - 144;
        if ( v11 )
        {
          v82 = instance - 144;
          do
          {
            if ( v11[6] )
            {
              pfnSQLDisconnect(pfnSQLDisconnect, v11[6]);
              pfnSQLFreeConnect(pfnSQLFreeConnect, v11[6]);
            }
            v12 = (unsigned int)(v11 + 8);
            if ( v11 + 8 < v11 + 48 )
            {
              do
              {
                *(_DWORD *)v12 = -1;
                *(_BYTE *)(v12 + 4) = 0;
                v12 += 8;
              }
              while ( v12 < (unsigned int)(v11 + 48) );
            }
            v11[1] &= ~0x40u;
            v11[6] = 0;
            v11 = (_DWORD *)v11[53];
          }
          while ( v11 );
          v10 = (void *)dword_1013112C;
          v9 = instance - 144;
        }
        FreeHseg(v10);
        v1 = rgtib;
        dword_1013112C = 0;
      }
      if ( hmodODBC )
      {
        FreeLibrary(hmodODBC);
        v1 = rgtib;
        hmodODBC = 0;
      }
      fOneTimeJetInitDone = 0;
      if ( hWingDll )
      {
        FreeLibrary(hWingDll);
        v1 = rgtib;
        hWingDll = 0;
        fLoadWingDll = 1;
      }
      if ( g_hMPRLibrary )
      {
        FreeLibrary(g_hMPRLibrary);
        v1 = rgtib;
        g_hMPRLibrary = 0;
      }
    }
    v13 = v81;
    v14 = v1[v81 / 4u + 261];
    if ( v14 != -1 )
    {
      v15 = 0;
      if ( v14 )
      {
        do
        {
          if ( v1 )
          {
            if ( v15 <= 0x27 )
            {
              _mm_lfence();
              v16 = v1[579 * v9 + 264 + v15];
              if ( v16 )
              {
                if ( *(_DWORD *)(v16 + 16) == v15 )
                {
                  v17 = *(void (__thiscall **)(_DWORD))(*(_DWORD *)v16 + 76);
                  if ( (**(_BYTE **)v16 & 0x20) != 0 )
                    ((void (__thiscall *)(void (__thiscall *)(_DWORD), _DWORD, int))v17)(v17, *(_DWORD *)(v16 + 8), 1);
                  else
                    v17(v17);
                }
                FreeLibrary(*(HMODULE *)(v16 + 4));
                v18 = dword_10130570;
                v13 = v81;
                dword_10130570 = (v16 - (int)&xmmword_10130580) / 24;
                dword_10130594[6 * dword_10130570] = v18;
                v1 = rgtib;
              }
            }
          }
          v9 = v82;
          ++v15;
        }
        while ( v15 < *(_DWORD *)((char *)v1 + v13 + 1044) );
      }
    }
    v19 = *(void ***)((char *)v1 + v13 + 2280);
    v77 = v19;
    v74[0] = 1;
    if ( v19 )
    {
      if ( v19[2] )
      {
        do
        {
          v20 = *(_DWORD *)*v19;
          v78 = v20;
          if ( v20 )
          {
            v83 = 0;
            while ( *(int *)(v20 + 8) > 0 )
            {
              v71 = 1;
              Session::AbortTransaction((Session *)v20, (struct Err *)&v71);
              if ( (v71 & 0xFFFFFFFE) != 0 )
              {
                if ( HIDWORD(v72) )
                  operator delete[]((void *)HIDWORD(v72));
                if ( v73 )
                  operator delete[](v73);
              }
            }
            v21 = *(_DWORD *)(v20 + 164) - 1;
            for ( i = v21; i >= 0; --i )
            {
              v22 = *(struct Instance **)(*(_DWORD *)(v20 + 156) + 4 * v21);
              v23 = (_DWORD *)*((_DWORD *)v22 + 16);
              *((_DWORD *)v22 + 16) = (char *)v23 - 1;
              if ( v23 == (_DWORD *)1 )
              {
                LOBYTE(v83) = 1;
                *((_DWORD *)v22 + 16) = 1;
                v24 = (Table *)*((_DWORD *)v22 + 17);
                if ( v24 )
                {
                  Table::Release(v24, v22);
                  *((_DWORD *)v22 + 17) = 0;
                }
                v25 = (Table *)*((_DWORD *)v22 + 18);
                if ( v25 )
                {
                  Table::Release(v25, v22);
                  *((_DWORD *)v22 + 18) = 0;
                }
                if ( *((_DWORD *)v22 + 2) )
                {
                  do
                  {
                    v26 = **(void (__thiscall *****)(_DWORD, int))v22;
                    if ( v26 )
                      (**v26)(v26, 1);
                  }
                  while ( *((_DWORD *)v22 + 2) );
                  v20 = v78;
                }
                v27 = 256;
                if ( dbidInit != 256 )
                {
                  while ( 1 )
                  {
                    --v27;
                    if ( (struct Instance *)*(&mpdbiddbid + v27) == v22 && (int *)mpdbidpvdbfndef[v27] == vdbfndefIsam )
                      break;
                    if ( v27 == dbidInit )
                      goto LABEL_74;
                  }
                  if ( v27 != -1 )
                  {
                    *(&mpdbiddbid + v27) = dbidFree;
                    mpdbidpvdbfndef[v27] = (int)vdbfndefInvalidDbid;
                    if ( v27 < 0x100 )
                    {
                      if ( *(&rgrepdbinfo + v27) )
                        _free(*(&rgrepdbinfo + v27));
                      *(&rgrepdbinfo + v27) = 0;
                    }
                    dbidFree = v27;
                  }
                }
LABEL_74:
                v28 = (_DWORD *)*((_DWORD *)v22 + 3);
                v29 = v28[41];
                if ( v29 )
                {
                  *(_DWORD *)(v28[39] + 4 * v29) = v22;
                  v30 = 0;
                  v31 = (struct Instance **)v28[39];
                  if ( *v31 != v22 )
                  {
                    do
                      ++v30;
                    while ( v31[v30] != v22 );
                  }
                  v32 = v28[41];
                  if ( v30 < v32 )
                  {
                    v33 = v32 - 1;
                    v28[41] = v33;
                    v31[v30] = v31[v33];
                  }
                }
                v34 = (IAccMeth *)*((_DWORD *)v22 + 15);
                if ( v34 )
                  IAccMeth::Release(v34);
                if ( *(_DWORD *)v22 )
                  operator delete[](*(void **)v22);
                operator delete(v22, 0x4Cu);
              }
              v21 = i - 1;
            }
            v35 = *(_DWORD *)(v20 + 200) - 1;
            if ( v35 >= 0 )
            {
              while ( 1 )
              {
                v36 = v35--;
                v37 = *(_DWORD *)(*(_DWORD *)(v20 + 192) + 4 * v36);
                v38 = 0;
                v39 = *(_DWORD *)(v37 + 120);
                if ( v39 )
                  break;
LABEL_89:
                if ( v38 != v39 )
                {
                  if ( v39 )
                    goto LABEL_91;
                  goto LABEL_95;
                }
LABEL_100:
                if ( v35 < 0 )
                  goto LABEL_101;
              }
              while ( *(_DWORD *)(*(_DWORD *)(v37 + 112) + 4 * v38) != v20 )
              {
                if ( ++v38 >= v39 )
                  goto LABEL_89;
              }
LABEL_91:
              *(_DWORD *)(*(_DWORD *)(v37 + 112) + 4 * v39) = v20;
              v40 = 0;
              v41 = *(_DWORD **)(v37 + 112);
              if ( *v41 != v20 )
              {
                do
                  ++v40;
                while ( v41[v40] != v20 );
              }
              v42 = *(_DWORD *)(v37 + 120);
              if ( v40 < v42 )
              {
                v43 = v42 - 1;
                *(_DWORD *)(v37 + 120) = v43;
                v41[v40] = v41[v43];
              }
LABEL_95:
              v44 = *(_DWORD *)(v20 + 200);
              if ( v44 )
              {
                *(_DWORD *)(*(_DWORD *)(v20 + 192) + 4 * v44) = v37;
                v45 = 0;
                v46 = *(_DWORD **)(v20 + 192);
                if ( *v46 != v37 )
                {
                  do
                    ++v45;
                  while ( v46[v45] != v37 );
                }
                v47 = *(_DWORD *)(v20 + 200);
                if ( v45 < v47 )
                {
                  v48 = v47 - 1;
                  *(_DWORD *)(v20 + 200) = v48;
                  v46[v45] = v46[v48];
                }
              }
              goto LABEL_100;
            }
LABEL_101:
            v49 = *(_DWORD **)v20;
            v50 = *(_DWORD *)(*(_DWORD *)v20 + 8);
            if ( v50 )
            {
              *(_DWORD *)(*v49 + 4 * v50) = v20;
              v51 = 0;
              v52 = (_DWORD *)*v49;
              if ( *(_DWORD *)*v49 != v20 )
              {
                do
                  ++v51;
                while ( v52[v51] != v20 );
              }
              v53 = v49[2];
              if ( v51 < v53 )
              {
                v54 = v53 - 1;
                v49[2] = v54;
                v52[v51] = v52[v54];
              }
            }
            if ( *(_DWORD *)(v20 + 204) )
              operator delete[](*(void **)(v20 + 204));
            if ( *(_DWORD *)(v20 + 192) )
              operator delete[](*(void **)(v20 + 192));
            if ( *(_DWORD *)(v20 + 180) )
              operator delete[](*(void **)(v20 + 180));
            if ( *(_DWORD *)(v20 + 168) )
              operator delete[](*(void **)(v20 + 168));
            if ( *(_DWORD *)(v20 + 156) )
              operator delete[](*(void **)(v20 + 156));
            operator delete((void *)v20, 0xDCu);
          }
          v19 = v77;
        }
        while ( v77[2] );
      }
      v55 = (volatile signed __int32 *)v19[6];
      if ( v55 && !_InterlockedExchangeAdd(v55 + 19, 0xFFFFFFFF) )
        (**(void (__thiscall ***)(void *, int))v55)((void *)v55, 1);
      if ( v19[27] )
        operator delete[](v19[27]);
      v83 = 2;
      DeleteCriticalSection((LPCRITICAL_SECTION)(v19 + 7));
      v83 = -1;
      if ( v19[3] )
        operator delete[](v19[3]);
      if ( *v19 )
        operator delete[](*v19);
      operator delete(v19, 0x74u);
      v1 = rgtib;
    }
    v56 = v80;
    if ( v80 == 1 && dword_10130518 )
    {
      Queue::CancelMessages(lpCriticalSection, 0, (struct Err *)v74);
      if ( (v74[0] & 0xFFFFFFFE) != 0 )
      {
        if ( v75 )
          operator delete[](v75);
        if ( v76 )
          operator delete[](v76);
      }
      v57 = 0;
      v58 = 1;
      v74[0] = 1;
      if ( dword_10130514 )
      {
        do
        {
          v59 = (HANDLE *)*((_DWORD *)dword_10130518 + v57);
          if ( v59 )
            SetThreadPriority(*v59, 2);
          ++v57;
        }
        while ( v57 < dword_10130514 );
        v58 = v74[0];
      }
      for ( j = 0; j < dword_10130514; ++j )
      {
        if ( (v58 & 0xFFFFFFFE) != 0 )
        {
          if ( v75 )
            operator delete[](v75);
          if ( v76 )
            operator delete[](v76);
        }
        v58 = 1;
        v74[0] = 1;
        if ( *((_DWORD *)dword_10130518 + j) )
        {
          v61 = lpCriticalSection;
          v62 = (char *)operator new(0x18u);
          v63 = v73;
          *(_QWORD *)(v62 + 12) = v72;
          *((_DWORD *)v62 + 5) = v63;
          *(_DWORD *)v62 = 0;
          *((_DWORD *)v62 + 1) = 0;
          *((_DWORD *)v62 + 2) = 0;
          *((_DWORD *)v62 + 3) = 0;
          EnterCriticalSection(v61);
          OwningThread = v61[1].OwningThread;
          if ( (unsigned int)OwningThread < v61[1].RecursionCount
            || (Collection::Grow((Collection *)&v61[1].LockCount, (unsigned int)OwningThread + 1, (struct Err *)v74),
                (v74[0] & 8) == 0) )
          {
            *(_DWORD *)(v61[1].LockCount + 4 * (int)v61[1].OwningThread++) = v62;
          }
          LeaveCriticalSection(v61);
          if ( !SetEvent(v61[1].DebugInfo) )
            System::ErrGetLastError(v65);
          Sleep(0xAu);
          v58 = v74[0];
        }
      }
      while ( dword_10130568 )
      {
        if ( !SetEvent(lpCriticalSection[1].DebugInfo) )
          System::ErrGetLastError(v66);
        Sleep(0xAu);
      }
      for ( k = 0; k < dword_10130514; ++k )
      {
        v68 = (HANDLE *)*((_DWORD *)dword_10130518 + k);
        if ( v68 )
        {
          v83 = 3;
          if ( *v68 )
          {
            WaitForSingleObject(*v68, 0x3E8u);
            CloseHandle(*v68);
            *v68 = 0;
          }
          v83 = -1;
          operator delete(v68, 4u);
          *((_DWORD *)dword_10130518 + k) = 0;
        }
      }
      operator delete[](dword_10130518);
      v1 = rgtib;
      v56 = v80;
      dword_10130518 = 0;
    }
    v69 = v82;
    if ( (v74[0] & 1) != 0 )
      v70 = 0;
    else
      v70 = v74[1];
    if ( (v74[0] & 0xFFFFFFFE) != 0 )
    {
      if ( v75 )
      {
        operator delete[](v75);
        v1 = rgtib;
      }
      if ( v76 )
      {
        operator delete[](v76);
        v1 = rgtib;
      }
    }
    v1[v81 / 4u + 263] = 0;
    if ( v56 == 1 )
    {
      fOneTimeJetInitDone = 0;
      if ( rgvtdefname )
        _free(rgvtdefname);
      rgvtdefname = 0;
    }
    ReleaseTib(v69);
    if ( pVCache )
    {
      VirtualFree((LPVOID)pVCache, 0, 0x8000u);
      pVCache = 0;
    }
    if ( v56 == 1 )
    {
      _free(rgtib);
      rgtib = 0;
    }
    LeaveCriticalSection(critJet);
    return v70;
  }
}

```

## disassembly

```asm
0x100287e0  mov     edi, edi
0x100287e2  push    ebp
0x100287e3  mov     ebp, esp
0x100287e5  push    0FFFFFFFFh
0x100287e7  push    offset _JetTerm@4_SEH
0x100287ec  mov     eax, large fs:0
0x100287f2  push    eax
0x100287f3  sub     esp, 48h
0x100287f6  push    ebx
0x100287f7  push    esi
0x100287f8  push    edi; unsigned int
0x100287f9  mov     eax, ___security_cookie
0x100287fe  xor     eax, ebp
0x10028800  push    eax; unsigned int
0x10028801  lea     eax, [ebp+var_C]
0x10028804  mov     large fs:0, eax
0x1002880a  push    _critJet; lpCriticalSection
0x10028810  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10028816  mov     ecx, _rgtib
0x1002881c  xor     edi, edi
0x1002881e  mov     eax, dword_1012C324
0x10028823  mov     [ebp+var_1C], edi
0x10028826  test    ecx, ecx
0x10028828  jnz     short loc_1002882F
0x1002882a  or      edi, 0FFFFFFFFh
0x1002882d  jmp     short loc_10028841
0x1002882f  cmp     eax, 0FFFFFFFFh
0x10028832  jz      short loc_10028844
0x10028834  mov     eax, _rgtibNext[eax*4]
0x1002883b  inc     edi
0x1002883c  cmp     eax, 0FFFFFFFFh
0x1002883f  jnz     short loc_10028834
0x10028841  mov     [ebp+var_1C], edi
0x10028844  mov     ebx, [ebp+instance]
0x10028847  add     ebx, 0FFFFFF70h
0x1002884d  cmp     ebx, 0FFFFFFFFh
0x10028850  jle     loc_100291D7
0x10028856  cmp     ebx, 40h ; '@'
0x10028859  jge     loc_100291D7
0x1002885f  cmp     ebx, 3Fh ; '?'
0x10028862  ja      loc_100291D7
0x10028868  imul    eax, ebx, 90Ch
0x1002886e  mov     [ebp+var_18], eax
0x10028871  cmp     dword ptr [eax+ecx+41Ch], 0
0x10028879  jnz     short loc_100288A4
0x1002887b  mov     ecx, ebx
0x1002887d  call    _ReleaseTib@4; ReleaseTib(x)
0x10028882  push    _critJet; lpCriticalSection
0x10028888  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1002888e  xor     eax, eax
0x10028890  mov     ecx, [ebp+var_C]
0x10028893  mov     large fs:0, ecx
0x1002889a  pop     ecx
0x1002889b  pop     edi
0x1002889c  pop     esi
0x1002889d  pop     ebx
0x1002889e  mov     esp, ebp
0x100288a0  pop     ebp
0x100288a1  retn    4
0x100288a4  lfence
0x100288a7  mov     esi, [eax+ecx+4C0h]
0x100288ae  test    esi, esi
0x100288b0  jz      short loc_100288DE
0x100288b2  mov     ecx, esi
0x100288b4  call    _RmtFreeTaskConnections@4; RmtFreeTaskConnections(x)
0x100288b9  push    esi; void *
0x100288ba  mov     esi, _pfnSQLFreeEnv
0x100288c0  mov     ecx, esi
0x100288c2  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100288c8  call    esi ; _pfnSQLFreeEnv
0x100288ca  mov     ecx, _rgtib
0x100288d0  mov     eax, [ebp+var_18]
0x100288d3  mov     dword ptr [eax+ecx+4C0h], 0
0x100288de  mov     eax, [eax+ecx+4C4h]
0x100288e5  test    eax, eax
0x100288e7  jz      short loc_10028907
0x100288e9  push    eax; Block
0x100288ea  call    ds:__imp__free
0x100288f0  mov     ecx, _rgtib
0x100288f6  add     esp, 4
0x100288f9  mov     eax, [ebp+var_18]
0x100288fc  mov     dword ptr [eax+ecx+4C4h], 0
0x10028907  mov     esi, ebx
0x10028909  mov     [ebp+var_14], esi
0x1002890c  cmp     edi, 1
0x1002890f  jnz     loc_10028A28
0x10028915  mov     eax, dword_1013112C
0x1002891a  mov     [ebp+var_14], esi
0x1002891d  test    eax, eax
0x1002891f  jz      loc_100289B4
0x10028925  mov     edi, [eax+1Ch]
0x10028928  mov     [ebp+var_14], esi
0x1002892b  test    edi, edi
0x1002892d  jz      short loc_1002899D
0x1002892f  mov     [ebp+var_14], ebx
0x10028932  mov     eax, [edi+18h]
0x10028935  test    eax, eax
0x10028937  jz      short loc_1002895D
0x10028939  mov     esi, _pfnSQLDisconnect
0x1002893f  mov     ecx, esi
0x10028941  push    eax; void *
0x10028942  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10028948  call    esi ; _pfnSQLDisconnect
0x1002894a  push    dword ptr [edi+18h]; void *
0x1002894d  mov     esi, _pfnSQLFreeConnect
0x10028953  mov     ecx, esi
0x10028955  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1002895b  call    esi ; _pfnSQLFreeConnect
0x1002895d  lea     eax, [edi+20h]
0x10028960  lea     ecx, [eax+0A0h]
0x10028966  cmp     eax, ecx
0x10028968  jnb     short loc_10028981
0x1002896a  nop     word ptr [eax+eax+00h]
0x10028970  mov     dword ptr [eax], 0FFFFFFFFh
0x10028976  mov     byte ptr [eax+4], 0
0x1002897a  add     eax, 8
0x1002897d  cmp     eax, ecx
0x1002897f  jb      short loc_10028970
0x10028981  and     dword ptr [edi+4], 0FFFFFFBFh
0x10028985  mov     dword ptr [edi+18h], 0
0x1002898c  mov     edi, [edi+0D4h]
0x10028992  test    edi, edi
0x10028994  jnz     short loc_10028932
0x10028996  mov     eax, dword_1013112C
0x1002899b  mov     esi, ebx
0x1002899d  mov     ecx, eax; Block
0x1002899f  call    _FreeHseg@4; FreeHseg(x)
0x100289a4  mov     ecx, _rgtib
0x100289aa  mov     dword_1013112C, 0
0x100289b4  mov     eax, _hmodODBC
0x100289b9  test    eax, eax
0x100289bb  jz      short loc_100289D4
0x100289bd  push    eax; hLibModule
0x100289be  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x100289c4  mov     ecx, _rgtib
0x100289ca  mov     _hmodODBC, 0
0x100289d4  mov     eax, _hWingDll
0x100289d9  mov     _fOneTimeJetInitDone, 0
0x100289e3  test    eax, eax
0x100289e5  jz      short loc_10028A08
0x100289e7  push    eax; hLibModule
0x100289e8  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x100289ee  mov     ecx, _rgtib
0x100289f4  mov     _hWingDll, 0
0x100289fe  mov     _fLoadWingDll, 1
0x10028a08  mov     eax, _g_hMPRLibrary
0x10028a0d  test    eax, eax
0x10028a0f  jz      short loc_10028A28
0x10028a11  push    eax; hLibModule
0x10028a12  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x10028a18  mov     ecx, _rgtib
0x10028a1e  mov     _g_hMPRLibrary, 0
0x10028a28  mov     edx, [ebp+var_18]
0x10028a2b  mov     eax, [edx+ecx+414h]
0x10028a32  cmp     eax, 0FFFFFFFFh
0x10028a35  jz      loc_10028AE3
0x10028a3b  xor     edi, edi
0x10028a3d  test    eax, eax
0x10028a3f  jz      loc_10028AE3
0x10028a45  test    ecx, ecx
0x10028a47  jz      loc_10028AD2
0x10028a4d  cmp     edi, 27h ; '''
0x10028a50  ja      loc_10028AD2
0x10028a56  imul    eax, esi, 243h
0x10028a5c  lfence
0x10028a5f  add     eax, edi
0x10028a61  mov     ebx, [ecx+eax*4+420h]
0x10028a68  test    ebx, ebx
0x10028a6a  jz      short loc_10028AD2
0x10028a6c  cmp     [ebx+10h], edi
0x10028a6f  jnz     short loc_10028A94
0x10028a71  mov     esi, [ebx]
0x10028a73  test    byte ptr [esi], 20h
0x10028a76  mov     esi, [esi+4Ch]
0x10028a79  mov     ecx, esi
0x10028a7b  jz      short loc_10028A8C
0x10028a7d  push    1; unsigned int
0x10028a7f  push    dword ptr [ebx+8]; void *
0x10028a82  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10028a88  call    esi
0x10028a8a  jmp     short loc_10028A94
0x10028a8c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10028a92  call    esi
0x10028a94  push    dword ptr [ebx+4]; hLibModule
0x10028a97  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x10028a9d  sub     ebx, offset xmmword_10130580
0x10028aa3  mov     eax, 2AAAAAABh
0x10028aa8  imul    ebx
0x10028aaa  mov     eax, dword_10130570
0x10028aaf  sar     edx, 2
0x10028ab2  mov     esi, edx
0x10028ab4  shr     esi, 1Fh
0x10028ab7  add     esi, edx
0x10028ab9  mov     edx, [ebp+var_18]
0x10028abc  mov     dword_10130570, esi
0x10028ac2  lea     ecx, [esi+esi*2]
0x10028ac5  mov     dword_10130594[ecx*8], eax
0x10028acc  mov     ecx, _rgtib
0x10028ad2  mov     esi, [ebp+var_14]
0x10028ad5  inc     edi
0x10028ad6  cmp     edi, [edx+ecx+414h]
0x10028add  jb      loc_10028A45
0x10028ae3  mov     ebx, [edx+ecx+8E8h]
0x10028aea  mov     [ebp+var_28], ebx
0x10028aed  mov     [ebp+var_3C], 1
0x10028af4  test    ebx, ebx
0x10028af6  jz      loc_10028EBC
0x10028afc  cmp     dword ptr [ebx+8], 0
0x10028b00  jbe     loc_10028E41
0x10028b06  mov     eax, [ebx]
0x10028b08  mov     ebx, [eax]
0x10028b0a  mov     [ebp+var_24], ebx
0x10028b0d  test    ebx, ebx
0x10028b0f  jz      loc_10028E34
0x10028b15  mov     [ebp+var_4], 0
0x10028b1c  cmp     dword ptr [ebx+8], 0
0x10028b20  jle     short loc_10028B63
0x10028b22  lea     eax, [ebp+var_50]
0x10028b25  mov     [ebp+var_50], 1
0x10028b2c  push    eax; struct Err *
0x10028b2d  mov     ecx, ebx; this
0x10028b2f  call    ?AbortTransaction@Session@@QAEXAAVErr@@@Z; Session::AbortTransaction(Err &)
0x10028b34  test    [ebp+var_50], 0FFFFFFFEh
0x10028b3b  jz      short loc_10028B5D
0x10028b3d  mov     eax, [ebp+Block]
0x10028b40  test    eax, eax
0x10028b42  jz      short loc_10028B4D
0x10028b44  push    eax; Block
0x10028b45  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10028b4a  add     esp, 4
0x10028b4d  mov     eax, [ebp+var_40]
0x10028b50  test    eax, eax
0x10028b52  jz      short loc_10028B5D
0x10028b54  push    eax; Block
0x10028b55  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10028b5a  add     esp, 4
0x10028b5d  cmp     dword ptr [ebx+8], 0
0x10028b61  jg      short loc_10028B22
0x10028b63  mov     ecx, [ebx+0A4h]
0x10028b69  sub     ecx, 1
0x10028b6c  mov     [ebp+var_20], ecx
0x10028b6f  js      loc_10028CE2
0x10028b75  nop     word ptr [eax+eax+00000000h]
0x10028b80  mov     eax, [ebx+9Ch]
0x10028b86  mov     edi, [eax+ecx*4]
0x10028b89  mov     ecx, [edi+40h]
0x10028b8c  lea     eax, [ecx-1]
0x10028b8f  mov     [edi+40h], eax
0x10028b92  test    eax, eax
0x10028b94  jnz     loc_10028CD3
0x10028b9a  mov     byte ptr [ebp+var_4], 1
0x10028b9e  mov     [edi+40h], ecx
0x10028ba1  mov     ecx, [edi+44h]; this
0x10028ba4  test    ecx, ecx
0x10028ba6  jz      short loc_10028BB5
0x10028ba8  push    edi; struct Instance *
0x10028ba9  call    ?Release@Table@@QAEJPAVInstance@@@Z; Table::Release(Instance *)
0x10028bae  mov     dword ptr [edi+44h], 0
0x10028bb5  mov     ecx, [edi+48h]; this
0x10028bb8  test    ecx, ecx
0x10028bba  jz      short loc_10028BC9
0x10028bbc  push    edi; struct Instance *
0x10028bbd  call    ?Release@Table@@QAEJPAVInstance@@@Z; Table::Release(Instance *)
0x10028bc2  mov     dword ptr [edi+48h], 0
0x10028bc9  cmp     dword ptr [edi+8], 0
0x10028bcd  jbe     short loc_10028BF3
0x10028bcf  nop
0x10028bd0  mov     eax, [edi]
0x10028bd2  mov     ebx, [eax]
0x10028bd4  test    ebx, ebx
0x10028bd6  jz      short loc_10028BEA
0x10028bd8  mov     eax, [ebx]
0x10028bda  push    1; void *
0x10028bdc  mov     esi, [eax]
0x10028bde  mov     ecx, esi
0x10028be0  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10028be6  mov     ecx, ebx
0x10028be8  call    esi
0x10028bea  cmp     dword ptr [edi+8], 0
0x10028bee  ja      short loc_10028BD0
0x10028bf0  mov     ebx, [ebp+var_24]
0x10028bf3  mov     eax, _dbidInit
0x10028bf8  mov     esi, 100h
0x10028bfd  cmp     eax, esi
0x10028bff  jz      short loc_10028C68
0x10028c01  dec     esi
0x10028c02  cmp     _mpdbiddbid[esi*4], edi
0x10028c09  jnz     short loc_10028C18
0x10028c0b  cmp     _mpdbidpvdbfndef[esi*4], offset _vdbfndefIsam
0x10028c16  jz      short loc_10028C1E
0x10028c18  cmp     esi, eax
0x10028c1a  jnz     short loc_10028C01
0x10028c1c  jmp     short loc_10028C68
0x10028c1e  cmp     esi, 0FFFFFFFFh
0x10028c21  jz      short loc_10028C68
0x10028c23  mov     eax, _dbidFree
0x10028c28  mov     _mpdbiddbid[esi*4], eax
0x10028c2f  mov     _mpdbidpvdbfndef[esi*4], offset _vdbfndefInvalidDbid
0x10028c3a  cmp     esi, 100h
0x10028c40  jnb     short loc_10028C62
  ... truncated ...
```
