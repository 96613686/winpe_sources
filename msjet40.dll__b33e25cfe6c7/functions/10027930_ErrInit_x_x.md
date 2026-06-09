# ErrInit(x,x)

- ea: `0x10027930`
- end: `0x100285eb`
- name: `_ErrInit@8`
- size: `3259`
- prototype: ``
- caller_count: `2`
- callee_count: `28`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1001aa00`
- `0x10026d60`

## callees

- `0x10026a00`
- `0x10027340`
- `0x10027930`
- `0x10044f50`
- `0x10045dad`
- `0x1004f70d`
- `0x10050000`
- `0x10050f9a`
- `0x100514d4`
- `0x10052ede`
- `0x100546f8`
- `0x10055f27`
- `0x10057fbf`
- `0x1005e5b8`
- `0x10060f7d`
- `0x1007467f`
- `0x100749f5`
- `0x10074ac5`
- `0x1007a6e0`
- `0x1007aa40`
- `0x10122f60`
- `0x1012398c`
- `0x10123aaa`
- `0x10123ae2`
- `0x10123af8`
- `0x10123b03`
- `0x10123e98`
- `0x101248d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100279d9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10028311`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100279d9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10028311`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x10027a05`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x10027e9e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x10027a05`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x10027e9e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10027ca0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10027ca0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10028534`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10028534`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x10027b27`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x10027b78`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x10027eb5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x10027b27`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x10027b78`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x10027eb5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10027f31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10028063`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10027f31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10028063`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10027ec4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10027ec4`

## pseudocode

```c
int __fastcall ErrInit(DWORD a1)
{
  int v2; // esi
  int result; // eax
  int v4; // eax
  Err *v5; // ecx
  char *v6; // edi
  Database *v7; // ebx
  void *v8; // eax
  File *v9; // esi
  DWORD TickCount; // eax
  UINT v11; // edi
  int v12; // ecx
  File *v13; // ebx
  unsigned __int16 *v14; // esi
  bool v15; // zf
  int v16; // eax
  Connection *v17; // ebx
  int v18; // edi
  int v19; // ebx
  struct _RTL_CRITICAL_SECTION *v20; // eax
  char *v21; // edi
  char *v22; // esi
  __int16 v23; // ax
  size_t v24; // esi
  int v25; // edi
  unsigned int v26; // kr00_4
  Connection *v27; // ebx
  CHAR *v28; // edx
  unsigned int v29; // kr04_4
  char *v30; // ecx
  int v31; // esi
  char *v32; // eax
  int v33; // edx
  int v34; // edx
  char *v35; // eax
  unsigned int v36; // ecx
  unsigned int v37; // eax
  int v38; // ebx
  int v39; // eax
  struct Instance *v40; // esi
  _DWORD *v41; // ecx
  Table *v42; // ecx
  Table *v43; // ecx
  void (__thiscall ***v44)(_DWORD, int); // ebx
  unsigned int v45; // edi
  _DWORD *v46; // edi
  int v47; // ecx
  unsigned int v48; // ecx
  struct Instance **v49; // edx
  unsigned int v50; // eax
  unsigned int v51; // eax
  IAccMeth *v52; // ecx
  int v53; // edi
  int v54; // ecx
  int v55; // edx
  int v56; // eax
  unsigned int v57; // ecx
  unsigned int v58; // ecx
  _DWORD *v59; // esi
  unsigned int v60; // eax
  unsigned int v61; // eax
  int v62; // ecx
  unsigned int v63; // ecx
  _DWORD *v64; // esi
  unsigned int v65; // eax
  unsigned int v66; // eax
  _DWORD *v67; // esi
  int v68; // ecx
  unsigned int v69; // ecx
  _DWORD *v70; // edx
  unsigned int v71; // eax
  unsigned int v72; // eax
  int v73; // edi
  void *v74; // esi
  int v75; // [esp-8h] [ebp-3A8h]
  int v76; // [esp-4h] [ebp-3A4h]
  const char *v77; // [esp+0h] [ebp-3A0h]
  size_t v78; // [esp+4h] [ebp-39Ch]
  unsigned __int16 v79[10]; // [esp+14h] [ebp-38Ch] BYREF
  _DWORD v80[3]; // [esp+28h] [ebp-378h] BYREF
  void *v81; // [esp+34h] [ebp-36Ch]
  void *v82; // [esp+38h] [ebp-368h]
  int v83; // [esp+3Ch] [ebp-364h]
  Connection **v84; // [esp+40h] [ebp-360h]
  unsigned int v85; // [esp+44h] [ebp-35Ch]
  Database *v86; // [esp+48h] [ebp-358h]
  unsigned __int16 *v87; // [esp+4Ch] [ebp-354h] BYREF
  int v88; // [esp+50h] [ebp-350h] BYREF
  int i; // [esp+54h] [ebp-34Ch]
  void *Block[4]; // [esp+58h] [ebp-348h] BYREF
  unsigned __int16 *v91; // [esp+68h] [ebp-338h] BYREF
  Connection *v92; // [esp+6Ch] [ebp-334h]
  wchar_t Destination[260]; // [esp+70h] [ebp-330h] BYREF
  char v94[280]; // [esp+278h] [ebp-128h] BYREF
  int v95; // [esp+39Ch] [ebp-4h]

  v85 = a1;
  v2 = 2316 * a1;
  v83 = 2316 * a1;
  if ( *((_DWORD *)rgtib + 579 * a1 + 263) )
    return -1030;
  result = ErrReadRegistry(a1);
  if ( result < 0 )
    return result;
  if ( !fOneTimeJetInitDone )
  {
    dbidFree = -1;
    dbidInit = 255;
    dword_1016DE5C = -1;
    dword_1016DA5C = (int)vdbfndefInvalidDbid;
    if ( ::Block )
      _free(::Block);
    ::Block = 0;
    dbidFree = 255;
    tableidFree = -1;
    rgvtdefname = _malloc(0x2000u);
    if ( !rgvtdefname )
      return -1011;
    memset(&rgrepdbinfo, 0, 0x400u);
    tableidInit = 2047;
    ReleaseTableid(2047);
    fOneTimeJetInitDone = 1;
  }
  v92 = 0;
  v84 = (Connection **)((char *)rgtib + v2 + 2280);
  v4 = 1;
  v88 = a1 + 144;
  Block[0] = (void *)1;
  if ( Sys > 1 )
  {
    v4 = Sys;
    Block[0] = (void *)Sys;
    if ( (Sys & 0xFFFFFFFE) != 0 )
    {
      Block[1] = (void *)dword_1013046C;
      Block[2] = (void *)dword_10130470;
      Err::CopyString(Sys, (unsigned __int16 **)&Block[3], dword_10130474);
      Err::CopyString(v5, &v91, dword_10130478);
      v4 = (int)Block[0];
    }
  }
  if ( (v4 & 8) == 0 )
  {
    v6 = (char *)operator new(0x74u);
    v92 = (Connection *)v6;
    *((_DWORD *)v6 + 1) = 0;
    *((_DWORD *)v6 + 2) = 0;
    *(_DWORD *)v6 = 0;
    *((_DWORD *)v6 + 4) = 0;
    *((_DWORD *)v6 + 5) = 0;
    *((_DWORD *)v6 + 3) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v6 + 28));
    v7 = (Database *)operator new(0x40Cu);
    v86 = v7;
    Database::Database(v7, (struct Connection *)v6, (struct Err *)Block);
    *(_DWORD *)v7 = &TemporaryDatabase::`vftable';
    *((_DWORD *)v7 + 248) = 0;
    *((_DWORD *)v7 + 249) = 0;
    *((_DWORD *)v7 + 250) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 1012));
    *((_DWORD *)v7 + 247) = 0;
    if ( ((int)Block[0] & 8) == 0 )
    {
      v8 = operator new[](0x4000u);
      *((_DWORD *)v7 + 247) = v8;
      *((_DWORD *)v7 + 248) = v8;
      *((_DWORD *)v7 + 249) = 0x4000;
      Bitmap::Set((Database *)((char *)v7 + 992), 0, 0x20000u, (struct Err *)Block);
      Bitmap::Clear((Database *)((char *)v7 + 992), 0, (struct Err *)Block);
      *((_DWORD *)v7 + 251) = 0;
      *((_DWORD *)v7 + 252) = 0x4000;
    }
    *((_DWORD *)v6 + 6) = v7;
    *((_DWORD *)v6 + 27) = 0;
    *((_DWORD *)v6 + 28) = 0;
    *((_DWORD *)v6 + 13) = 5000;
    *((_DWORD *)v6 + 14) = 20;
    *((_DWORD *)v6 + 15) = 0;
    *((_DWORD *)v6 + 16) = 3;
    *((_DWORD *)v6 + 17) = 0;
    *((_DWORD *)v6 + 18) = 1;
    *((_DWORD *)v6 + 19) = 2000;
    *((_DWORD *)v6 + 20) = 50;
    *((_DWORD *)v6 + 21) = 500;
    *((_DWORD *)v6 + 22) = 9500;
    *((_DWORD *)v6 + 23) = 100;
    *((_DWORD *)v6 + 24) = 0;
    *((_DWORD *)v6 + 25) = 0;
    *((_DWORD *)v6 + 26) = 50;
    v79[0] = 0;
    *((_DWORD *)v7 + 23) = 0;
    *((_DWORD *)v7 + 18) = 1;
    *((_DWORD *)v7 + 24) = 1;
    *((_DWORD *)v7 + 22) = 1;
    *((_DWORD *)v7 + 21) = 1;
    memset((char *)v7 + 424, 101, 0x200u);
    v9 = (Database *)((char *)v7 + 4);
    i = (int)v7 + 4;
    TickCount = GetTickCount();
    *((_DWORD *)v7 + 6) |= 0x52u;
    v11 = TickCount;
    v12 = (int)Block[0];
    if ( ((int)Block[0] & 8) != 0 )
      goto LABEL_33;
    v13 = (Database *)((char *)v7 + 4);
    do
    {
      System::AllocateTempFileName((unsigned __int16 **)v12, (unsigned int)&v87, v11);
      LOBYTE(v12) = Block[0];
      if ( ((int)Block[0] & 8) != 0 )
        break;
      v14 = v87;
      File::ReallyOpen(v13, v87, (struct Err *)Block, (char *)Block[0]);
      LOBYTE(v12) = Block[0];
      if ( ((int)Block[0] & 8) == 0 || ((int)Block[0] & 1) != 0 || Block[1] != (void *)-1201 )
        break;
      if ( ((int)Block[0] & 0xFFFFFFFE) != 0 )
      {
        if ( Block[3] )
          operator delete[](Block[3]);
        if ( v91 )
          operator delete[](v91);
      }
      v12 = 1;
      Block[0] = (void *)1;
      if ( v14 )
      {
        operator delete[](v14);
        v12 = (int)Block[0];
      }
      ++v11;
    }
    while ( (v12 & 8) == 0 );
    v7 = v86;
    v9 = (File *)i;
    if ( (v12 & 8) != 0
      || (Database::AllocateHashTable(v86, (struct Err *)Block), ((int)Block[0] & 8) != 0)
      || (Database::BuildInitialDatabase(v86, v79, (struct Err *)Block), ((int)Block[0] & 8) != 0) )
    {
LABEL_33:
      v15 = *(_DWORD *)v9 == -1;
      v16 = 1;
      v80[0] = 1;
      if ( !v15 )
      {
        File::Close(v9, (struct Err *)v80);
        v16 = v80[0];
      }
      *((_DWORD *)v7 + 18) = 0;
      if ( (v16 & 0xFFFFFFFE) != 0 )
      {
        if ( v81 )
          operator delete[](v81);
        if ( v82 )
          operator delete[](v82);
      }
    }
    else
    {
      *((_DWORD *)v7 + 54) = 9801;
    }
    v17 = v92;
    if ( ((int)Block[0] & 8) == 0 )
      goto LABEL_46;
    v18 = *((_DWORD *)v92 + 6);
    if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v18 + 76), 0xFFFFFFFF) && v18 )
      (**(void (__thiscall ***)(int, int))v18)(v18, 1);
    *((_DWORD *)v17 + 6) = 0;
    v4 = (int)Block[0];
    if ( ((int)Block[0] & 8) == 0 )
    {
LABEL_46:
      Connection::ScheduleSignatureCheck(v17);
      v4 = (int)Block[0];
    }
    v19 = v85;
    if ( (v4 & 8) == 0 )
    {
      if ( v88 )
      {
        if ( v85 >= 0x40 )
          v19 = -1;
        if ( critJet )
        {
          EnterCriticalSection(critJet);
        }
        else
        {
          v20 = (struct _RTL_CRITICAL_SECTION *)_malloc(0x18u);
          critJet = v20;
          if ( !v20 )
            goto LABEL_79;
          InitializeCriticalSection(v20);
          EnterCriticalSection(critJet);
        }
        if ( v19 == -1 )
        {
          LeaveCriticalSection(critJet);
        }
        else
        {
          v21 = (char *)rgtib + 2316 * v19;
          v22 = v21 + 520;
          do
          {
            v23 = *(_WORD *)v22;
            v22 += 2;
          }
          while ( v23 );
          v24 = ((v22 - (v21 + 522)) >> 1) + 1;
          if ( v24 > 0x104 )
            v24 = 260;
          wcsncpy(Destination, (const wchar_t *)v21 + 260, v24);
          Destination[v24 - 1] = 0;
          v25 = *((_DWORD *)v21 + 260);
          LeaveCriticalSection(critJet);
          if ( Destination[0] )
          {
            v26 = wcslen(Destination);
            v27 = v92;
            if ( *((_DWORD *)v92 + 27) )
            {
              operator delete[](*((void **)v92 + 27));
              *((_DWORD *)v27 + 27) = 0;
            }
            v28 = (CHAR *)operator new[](2 * v26 + 1);
            *((_DWORD *)v27 + 27) = v28;
            if ( ((int)Block[0] & 8) == 0 )
            {
              v88 = 2 * v26;
              v29 = wcslen(Destination);
              if ( v29 == -1 )
              {
                *v28 = 0;
                *((_DWORD *)v27 + 28) = v25;
              }
              else if ( ErrGenericWideNToCbMultiByte(0, Destination, v29 + 1, v28, &v88, v75, v76) < 0 )
              {
                if ( (int)Block[0] < 8 )
                {
                  if ( ((int)Block[0] & 0xFFFFFFFE) != 0 )
                  {
                    if ( Block[3] )
                      operator delete[](Block[3]);
                    if ( v91 )
                      operator delete[](v91);
                  }
                  *(_OWORD *)Block = _xmm;
                  v91 = 0;
                }
                if ( *((_DWORD *)v27 + 27) )
                  operator delete[](*((void **)v27 + 27));
                *((_DWORD *)v27 + 27) = 0;
              }
              else
              {
                *((_DWORD *)v27 + 28) = v25;
              }
            }
            goto LABEL_80;
          }
        }
      }
LABEL_79:
      v27 = v92;
LABEL_80:
      Connection::ReadConfigTree((BYTE *)v27, 0, "SOFTWARE\\Microsoft\\Jet\\4.0\\Engines\\Jet 4.0");
      v30 = (char *)*((_DWORD *)v27 + 27);
      if ( v30 && *v30 )
      {
        v31 = 2147483646;
        v32 = v94;
        v33 = 275;
        while ( v31 && *v30 )
        {
          *v32++ = *v30++;
          --v31;
          if ( !--v33 )
          {
            --v32;
            break;
          }
        }
        *v32 = 0;
        v34 = 275;
        v35 = v94;
        while ( *v35 )
        {
          ++v35;
          if ( !--v34 )
            goto LABEL_92;
        }
        StringCopyWorkerA(v30, (size_t)"\\Engines\\Jet", (size_t *)v30, v77, v78);
LABEL_92:
        v27 = v92;
        Connection::ReadConfigTree((BYTE *)v92, *((HKEY *)v92 + 28), v94);
      }
      if ( !dword_10130480 && *((_DWORD *)v27 + 16) )
        dword_1013047C = *((_DWORD *)v27 + 16);
      v36 = *((_DWORD *)v27 + 15) / 4;
      if ( !dword_101304C8 )
      {
        dword_101304C8 = 1;
        if ( v36 )
        {
          if ( v36 < 0x40 )
            v36 = 64;
          if ( v36 > dword_101304A8 )
            v36 = dword_101304A8;
          dword_101304AC = v36;
        }
      }
      v37 = *((_DWORD *)v27 + 26);
      pReplCallbacks = (int)&replCallsDef;
      if ( v37 > 0x32 )
        v37 = 50;
      dword_101304D4 = v37;
      v4 = (int)Block[0];
      goto LABEL_107;
    }
  }
  v27 = v92;
LABEL_107:
  if ( (v4 & 8) != 0 )
  {
    if ( v27 )
    {
      if ( *((_DWORD *)v27 + 2) )
      {
        do
        {
          v38 = **(_DWORD **)v27;
          v88 = v38;
          if ( v38 )
          {
            v95 = 1;
            while ( *(int *)(v38 + 8) > 0 )
            {
              v80[0] = 1;
              Session::AbortTransaction((Session *)v38, (struct Err *)v80);
              if ( (v80[0] & 0xFFFFFFFE) != 0 )
              {
                if ( v81 )
                  operator delete[](v81);
                if ( v82 )
                  operator delete[](v82);
              }
            }
            v39 = *(_DWORD *)(v38 + 164) - 1;
            for ( i = v39; i >= 0; --i )
            {
              v40 = *(struct Instance **)(*(_DWORD *)(v38 + 156) + 4 * v39);
              v41 = (_DWORD *)*((_DWORD *)v40 + 16);
              *((_DWORD *)v40 + 16) = (char *)v41 - 1;
              if ( v41 == (_DWORD *)1 )
              {
                LOBYTE(v95) = 2;
                *((_DWORD *)v40 + 16) = 1;
                v42 = (Table *)*((_DWORD *)v40 + 17);
                if ( v42 )
                {
                  Table::Release(v42, v40);
                  *((_DWORD *)v40 + 17) = 0;
                }
                v43 = (Table *)*((_DWORD *)v40 + 18);
                if ( v43 )
                {
                  Table::Release(v43, v40);
                  *((_DWORD *)v40 + 18) = 0;
                }
                if ( *((_DWORD *)v40 + 2) )
                {
                  do
                  {
                    v44 = **(void (__thiscall *****)(_DWORD, int))v40;
                    if ( v44 )
                      (**v44)(v44, 1);
                  }
                  while ( *((_DWORD *)v40 + 2) );
                  v38 = v88;
                }
                v45 = 256;
                if ( dbidInit != 256 )
                {
                  while ( 1 )
                  {
                    --v45;
                    if ( (struct Instance *)*(&mpdbiddbid + v45) == v40 && (int *)mpdbidpvdbfndef[v45] == vdbfndefIsam )
                      break;
                    if ( v45 == dbidInit )
                      goto LABEL_140;
                  }
                  if ( v45 != -1 )
                  {
                    *(&mpdbiddbid + v45) = dbidFree;
                    mpdbidpvdbfndef[v45] = (int)vdbfndefInvalidDbid;
                    if ( v45 < 0x100 )
                    {
                      if ( *(&rgrepdbinfo + v45) )
                        _free(*(&rgrepdbinfo + v45));
                      *(&rgrepdbinfo + v45) = 0;
                    }
                    dbidFree = v45;
                  }
                }
LABEL_140:
                v46 = (_DWORD *)*((_DWORD *)v40 + 3);
                v47 = v46[41];
                if ( v47 )
                {
                  *(_DWORD *)(v46[39] + 4 * v47) = v40;
                  v48 = 0;
                  v49 = (struct Instance **)v46[39];
                  if ( *v49 != v40 )
                  {
                    do
                      ++v48;
                    while ( v49[v48] != v40 );
                  }
                  v50 = v46[41];
                  if ( v48 < v50 )
                  {
                    v51 = v50 - 1;
                    v46[41] = v51;
                    v49[v48] = v49[v51];
                  }
                }
                v52 = (IAccMeth *)*((_DWORD *)v40 + 15);
                if ( v52 )
                  IAccMeth::Release(v52);
                if ( *(_DWORD *)v40 )
                  operator delete[](*(void **)v40);
                operator delete(v40, 0x4Cu);
              }
              v39 = i - 1;
            }
            v53 = *(_DWORD *)(v38 + 200) - 1;
            if ( v53 >= 0 )
            {
              while ( 1 )
              {
                v54 = v53--;
                v55 = *(_DWORD *)(*(_DWORD *)(v38 + 192) + 4 * v54);
                v56 = 0;
                v57 = *(_DWORD *)(v55 + 120);
                if ( v57 )
                  break;
LABEL_155:
                if ( v56 != v57 )
                  goto LABEL_156;
LABEL_166:
                if ( v53 < 0 )
                  goto LABEL_167;
              }
              while ( *(_DWORD *)(*(_DWORD *)(v55 + 112) + 4 * v56) != v38 )
              {
                if ( ++v56 >= v57 )
                  goto LABEL_155;
              }
LABEL_156:
              if ( v57 )
              {
                *(_DWORD *)(*(_DWORD *)(v55 + 112) + 4 * v57) = v38;
                v58 = 0;
                v59 = *(_DWORD **)(v55 + 112);
                if ( *v59 != v38 )
                {
                  do
                    ++v58;
                  while ( v59[v58] != v38 );
                }
                v60 = *(_DWORD *)(v55 + 120);
                if ( v58 < v60 )
                {
                  v61 = v60 - 1;
                  *(_DWORD *)(v55 + 120) = v61;
                  v59[v58] = v59[v61];
                }
              }
              v62 = *(_DWORD *)(v38 + 200);
              if ( v62 )
              {
                *(_DWORD *)(*(_DWORD *)(v38 + 192) + 4 * v62) = v55;
                v63 = 0;
                v64 = *(_DWORD **)(v38 + 192);
                if ( *v64 != v55 )
                {
                  do
                    ++v63;
                  while ( v64[v63] != v55 );
                }
                v65 = *(_DWORD *)(v38 + 200);
                if ( v63 < v65 )
                {
                  v66 = v65 - 1;
                  *(_DWORD *)(v38 + 200) = v66;
                  v64[v63] = v64[v66];
                }
              }
              goto LABEL_166;
            }
LABEL_167:
            v67 = *(_DWORD **)v38;
            v68 = *(_DWORD *)(*(_DWORD *)v38 + 8);
            if ( v68 )
            {
              *(_DWORD *)(*v67 + 4 * v68) = v38;
              v69 = 0;
              v70 = (_DWORD *)*v67;
              if ( *(_DWORD *)*v67 != v38 )
              {
                do
                  ++v69;
                while ( v70[v69] != v38 );
              }
              v71 = v67[2];
              if ( v69 < v71 )
              {
                v72 = v71 - 1;
                v67[2] = v72;
                v70[v69] = v70[v72];
              }
            }
            if ( *(_DWORD *)(v38 + 204) )
              operator delete[](*(void **)(v38 + 204));
            if ( *(_DWORD *)(v38 + 192) )
              operator delete[](*(void **)(v38 + 192));
            if ( *(_DWORD *)(v38 + 180) )
              operator delete[](*(void **)(v38 + 180));
            if ( *(_DWORD *)(v38 + 168) )
              operator delete[](*(void **)(v38 + 168));
            if ( *(_DWORD *)(v38 + 156) )
              operator delete[](*(void **)(v38 + 156));
            operator delete((void *)v38, 0xDCu);
          }
          v27 = v92;
        }
        while ( *((_DWORD *)v92 + 2) );
      }
      v73 = *((_DWORD *)v27 + 6);
      if ( v73 && !_InterlockedExchangeAdd((volatile signed __int32 *)(v73 + 76), 0xFFFFFFFF) )
        (**(void (__thiscall ***)(int, int))v73)(v73, 1);
      if ( *((_DWORD *)v27 + 27) )
        operator delete[](*((void **)v27 + 27));
      v95 = 3;
      DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v27 + 28));
      if ( *((_DWORD *)v27 + 3) )
        operator delete[](*((void **)v27 + 3));
      if ( *(_DWORD *)v27 )
        operator delete[](*(void **)v27);
      operator delete(v27, 0x74u);
      v4 = (int)Block[0];
    }
  }
  else
  {
    *v84 = v27;
  }
  if ( (v4 & 1) != 0 )
    v74 = 0;
  else
    v74 = Block[1];
  if ( (v4 & 0xFFFFFFFE) != 0 )
  {
    if ( Block[3] )
      operator delete[](Block[3]);
    if ( v91 )
      operator delete[](v91);
  }
  if ( (int)v74 < 0 )
    return (int)v74;
  *(_DWORD *)((char *)rgtib + v83 + 1052) = 1;
  return 0;
}

```

## disassembly

```asm
0x10027930  mov     edi, edi
0x10027932  push    ebp
0x10027933  mov     ebp, esp
0x10027935  push    0FFFFFFFFh
0x10027937  push    offset _ErrInit@8_SEH
0x1002793c  mov     eax, large fs:0
0x10027942  push    eax
0x10027943  sub     esp, 384h
0x10027949  mov     eax, ___security_cookie
0x1002794e  xor     eax, ebp
0x10027950  mov     [ebp+var_10], eax
0x10027953  push    ebx
0x10027954  push    esi
0x10027955  push    edi; cchToCopy
0x10027956  push    eax; unsigned int
0x10027957  lea     eax, [ebp+var_C]
0x1002795a  mov     large fs:0, eax
0x10027960  mov     ebx, ecx
0x10027962  mov     [ebp+var_35C], ebx
0x10027968  mov     eax, _rgtib
0x1002796d  imul    esi, ebx, 90Ch
0x10027973  mov     [ebp+var_364], esi
0x10027979  cmp     dword ptr [esi+eax+41Ch], 0
0x10027981  jz      short loc_1002798D
0x10027983  mov     eax, 0FFFFFBFAh
0x10027988  jmp     loc_100285CF
0x1002798d  call    ErrReadRegistry
0x10027992  test    eax, eax
0x10027994  js      loc_100285CF
0x1002799a  cmp     _fOneTimeJetInitDone, 0
0x100279a1  jnz     loc_10027A53
0x100279a7  mov     eax, Block
0x100279ac  mov     _dbidFree, 0FFFFFFFFh
0x100279b6  mov     _dbidInit, 0FFh
0x100279c0  mov     dword_1016DE5C, 0FFFFFFFFh
0x100279ca  mov     dword_1016DA5C, offset _vdbfndefInvalidDbid
0x100279d4  test    eax, eax
0x100279d6  jz      short loc_100279E2
0x100279d8  push    eax; Block
0x100279d9  call    ds:__imp__free
0x100279df  add     esp, 4
0x100279e2  push    2000h; Size
0x100279e7  mov     Block, 0
0x100279f1  mov     _dbidFree, 0FFh
0x100279fb  mov     _tableidFree, 0FFFFFFFFh
0x10027a05  call    ds:__imp__malloc
0x10027a0b  add     esp, 4
0x10027a0e  mov     _rgvtdefname, eax
0x10027a13  test    eax, eax
0x10027a15  jnz     short loc_10027A21
0x10027a17  mov     eax, 0FFFFFC0Dh
0x10027a1c  jmp     loc_100285CF
0x10027a21  push    400h; Size
0x10027a26  push    0; Val
0x10027a28  push    offset _rgrepdbinfo; void *
0x10027a2d  call    _memset
0x10027a32  add     esp, 0Ch
0x10027a35  mov     _tableidInit, 7FFh
0x10027a3f  push    7FFh
0x10027a44  call    _ReleaseTableid@4; ReleaseTableid(x)
0x10027a49  mov     _fOneTimeJetInitDone, 1
0x10027a53  mov     eax, _rgtib
0x10027a58  mov     ecx, ?Sys@@3VSystem@@A; this
0x10027a5e  add     eax, 8E8h
0x10027a63  add     eax, esi
0x10027a65  mov     [ebp+var_334], 0
0x10027a6f  mov     [ebp+var_360], eax
0x10027a75  lea     esi, [ebx+90h]
0x10027a7b  mov     eax, 1
0x10027a80  mov     [ebp+var_350], esi
0x10027a86  mov     [ebp+Block], eax
0x10027a8c  cmp     ecx, eax
0x10027a8e  jle     short loc_10027AE0
0x10027a90  mov     eax, ecx
0x10027a92  mov     [ebp+Block], eax
0x10027a98  test    ecx, 0FFFFFFFEh
0x10027a9e  jz      short loc_10027AE0
0x10027aa0  mov     eax, dword_1013046C
0x10027aa5  push    dword_10130474; unsigned __int16 *
0x10027aab  mov     [ebp+Block+4], eax
0x10027ab1  mov     eax, dword_10130470
0x10027ab6  mov     [ebp+Block+8], eax
0x10027abc  lea     eax, [ebp+Block+0Ch]
0x10027ac2  push    eax; unsigned __int16 **
0x10027ac3  call    ?CopyString@Err@@AAEXAAPAGQAG@Z; Err::CopyString(ushort * &,ushort * const)
0x10027ac8  push    dword_10130478; unsigned __int16 *
0x10027ace  lea     eax, [ebp+var_338]
0x10027ad4  push    eax; unsigned __int16 **
0x10027ad5  call    ?CopyString@Err@@AAEXAAPAGQAG@Z; Err::CopyString(ushort * &,ushort * const)
0x10027ada  mov     eax, [ebp+Block]
0x10027ae0  test    al, 8
0x10027ae2  jnz     loc_10028189
0x10027ae8  push    74h ; 't'; Size
0x10027aea  call    ??2@YAPAXI@Z; operator new(uint)
0x10027aef  mov     edi, eax
0x10027af1  add     esp, 4
0x10027af4  mov     [ebp+var_334], edi
0x10027afa  lea     ecx, [edi+1Ch]
0x10027afd  mov     dword ptr [edi+4], 0
0x10027b04  push    ecx; lpCriticalSection
0x10027b05  mov     dword ptr [edi+8], 0
0x10027b0c  mov     dword ptr [edi], 0
0x10027b12  mov     dword ptr [edi+10h], 0
0x10027b19  mov     dword ptr [edi+14h], 0
0x10027b20  mov     dword ptr [edi+0Ch], 0
0x10027b27  call    ds:__imp__InitializeCriticalSection@4; InitializeCriticalSection(x)
0x10027b2d  push    40Ch; Size
0x10027b32  call    ??2@YAPAXI@Z; operator new(uint)
0x10027b37  add     esp, 4
0x10027b3a  mov     ebx, eax
0x10027b3c  lea     eax, [ebp+Block]
0x10027b42  mov     [ebp+var_358], ebx
0x10027b48  mov     ecx, ebx; this
0x10027b4a  push    eax; struct Err *
0x10027b4b  push    edi; struct Connection *
0x10027b4c  call    ??0Database@@QAE@PAVConnection@@AAVErr@@@Z; Database::Database(Connection *,Err &)
0x10027b51  mov     dword ptr [ebx], offset ??_7TemporaryDatabase@@6B@; const TemporaryDatabase::`vftable'
0x10027b57  lea     esi, [ebx+3E0h]
0x10027b5d  lea     eax, [ebx+3F4h]
0x10027b63  mov     dword ptr [esi], 0
0x10027b69  push    eax; lpCriticalSection
0x10027b6a  mov     dword ptr [esi+4], 0
0x10027b71  mov     dword ptr [esi+8], 0
0x10027b78  call    ds:__imp__InitializeCriticalSection@4; InitializeCriticalSection(x)
0x10027b7e  mov     dword ptr [ebx+3DCh], 0
0x10027b88  test    byte ptr [ebp+Block], 8
0x10027b8f  jnz     short loc_10027BE6
0x10027b91  push    4000h; unsigned int
0x10027b96  call    ??_U@YAPAXI@Z; operator new[](uint)
0x10027b9b  add     esp, 4
0x10027b9e  mov     [ebx+3DCh], eax
0x10027ba4  mov     [esi], eax
0x10027ba6  xor     edx, edx; unsigned int
0x10027ba8  lea     eax, [ebp+Block]
0x10027bae  mov     dword ptr [esi+4], 4000h
0x10027bb5  mov     ecx, esi; this
0x10027bb7  push    eax; struct Err *
0x10027bb8  push    20000h; unsigned int
0x10027bbd  call    ?Set@Bitmap@@QAIXKKAAVErr@@@Z; Bitmap::Set(ulong,ulong,Err &)
0x10027bc2  lea     eax, [ebp+Block]
0x10027bc8  mov     ecx, esi; this
0x10027bca  push    eax; struct Err *
0x10027bcb  push    0; unsigned int
0x10027bcd  call    ?Clear@Bitmap@@QAEXKAAVErr@@@Z; Bitmap::Clear(ulong,Err &)
0x10027bd2  mov     dword ptr [ebx+3ECh], 0
0x10027bdc  mov     dword ptr [ebx+3F0h], 4000h
0x10027be6  mov     [edi+18h], ebx
0x10027be9  xor     eax, eax
0x10027beb  mov     dword ptr [edi+6Ch], 0
0x10027bf2  mov     dword ptr [edi+70h], 0
0x10027bf9  mov     dword ptr [edi+34h], 1388h
0x10027c00  mov     dword ptr [edi+38h], 14h
0x10027c07  mov     dword ptr [edi+3Ch], 0
0x10027c0e  mov     dword ptr [edi+40h], 3
0x10027c15  mov     dword ptr [edi+44h], 0
0x10027c1c  mov     dword ptr [edi+48h], 1
0x10027c23  mov     dword ptr [edi+4Ch], 7D0h
0x10027c2a  mov     dword ptr [edi+50h], 32h ; '2'
0x10027c31  mov     dword ptr [edi+54h], 1F4h
0x10027c38  mov     dword ptr [edi+58h], 251Ch
0x10027c3f  mov     dword ptr [edi+5Ch], 64h ; 'd'
0x10027c46  mov     dword ptr [edi+60h], 0
0x10027c4d  mov     dword ptr [edi+64h], 0
0x10027c54  mov     dword ptr [edi+68h], 32h ; '2'
0x10027c5b  push    200h; Size
0x10027c60  mov     [ebp+var_38C], ax
0x10027c67  mov     [ebx+5Ch], eax
0x10027c6a  lea     eax, [ebx+1A8h]
0x10027c70  push    65h ; 'e'; Val
0x10027c72  push    eax; void *
0x10027c73  mov     dword ptr [ebx+48h], 1
0x10027c7a  mov     dword ptr [ebx+60h], 1
0x10027c81  mov     dword ptr [ebx+58h], 1
0x10027c88  mov     dword ptr [ebx+54h], 1
0x10027c8f  call    _memset
0x10027c94  add     esp, 0Ch
0x10027c97  lea     esi, [ebx+4]
0x10027c9a  mov     [ebp+var_34C], esi
0x10027ca0  call    ds:__imp__GetTickCount@0; GetTickCount()
0x10027ca6  or      dword ptr [esi+14h], 52h
0x10027caa  mov     edi, eax
0x10027cac  mov     ecx, [ebp+Block]; unsigned __int16 **
0x10027cb2  test    cl, 8
0x10027cb5  jnz     loc_10027DB5
0x10027cbb  mov     ebx, esi
0x10027cbd  nop     dword ptr [eax]
0x10027cc0  lea     eax, [ebp+Block]
0x10027cc6  push    eax
0x10027cc7  push    edi; uUnique
0x10027cc8  lea     eax, [ebp+var_354]
0x10027cce  push    eax; unsigned int
0x10027ccf  call    ?AllocateTempFileName@System@@QAEXPAPAGIAAVErr@@@Z; System::AllocateTempFileName(ushort * *,uint,Err &)
0x10027cd4  mov     ecx, [ebp+Block]
0x10027cda  test    cl, 8
0x10027cdd  jnz     loc_10027D6B
0x10027ce3  mov     esi, [ebp+var_354]
0x10027ce9  lea     eax, [ebp+Block]
0x10027cef  push    ecx; char *
0x10027cf0  push    eax; struct Err *
0x10027cf1  push    esi; unsigned __int16 *
0x10027cf2  mov     ecx, ebx; this
0x10027cf4  call    ?ReallyOpen@File@@AAEXPAGAAVErr@@PAD@Z; File::ReallyOpen(ushort *,Err &,char *)
0x10027cf9  mov     ecx, [ebp+Block]
0x10027cff  test    cl, 8
0x10027d02  jz      short loc_10027D6B
0x10027d04  test    cl, 1
0x10027d07  jnz     short loc_10027D6B
0x10027d09  cmp     [ebp+Block+4], 0FFFFFB4Fh
0x10027d13  jnz     short loc_10027D6B
0x10027d15  test    ecx, 0FFFFFFFEh
0x10027d1b  jz      short loc_10027D43
0x10027d1d  mov     eax, [ebp+Block+0Ch]
0x10027d23  test    eax, eax
0x10027d25  jz      short loc_10027D30
0x10027d27  push    eax; Block
0x10027d28  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10027d2d  add     esp, 4
0x10027d30  mov     eax, [ebp+var_338]
0x10027d36  test    eax, eax
0x10027d38  jz      short loc_10027D43
0x10027d3a  push    eax; Block
0x10027d3b  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10027d40  add     esp, 4
0x10027d43  mov     ecx, 1
0x10027d48  mov     [ebp+Block], ecx
0x10027d4e  test    esi, esi
0x10027d50  jz      short loc_10027D61
0x10027d52  push    esi; Block
0x10027d53  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10027d58  mov     ecx, [ebp+Block]
0x10027d5e  add     esp, 4
0x10027d61  inc     edi
0x10027d62  test    cl, 8
0x10027d65  jz      loc_10027CC0
0x10027d6b  mov     ebx, [ebp+var_358]
0x10027d71  mov     esi, [ebp+var_34C]
0x10027d77  test    cl, 8
0x10027d7a  jnz     short loc_10027DB5
0x10027d7c  lea     eax, [ebp+Block]
0x10027d82  mov     ecx, ebx; this
0x10027d84  push    eax; struct Err *
0x10027d85  call    ?AllocateHashTable@Database@@IAEXAAVErr@@@Z; Database::AllocateHashTable(Err &)
0x10027d8a  mov     ecx, [ebp+Block]
0x10027d90  test    cl, 8
0x10027d93  jnz     short loc_10027DB5
0x10027d95  lea     eax, [ebp+Block]
0x10027d9b  mov     ecx, ebx; this
0x10027d9d  push    eax; struct Err *
0x10027d9e  lea     eax, [ebp+var_38C]
0x10027da4  push    eax; unsigned __int16 *
0x10027da5  call    ?BuildInitialDatabase@Database@@IAEXQBGAAVErr@@@Z; Database::BuildInitialDatabase(ushort const * const,Err &)
0x10027daa  mov     ecx, [ebp+Block]
0x10027db0  test    cl, 8
0x10027db3  jz      short loc_10027E0F
0x10027db5  cmp     dword ptr [esi], 0FFFFFFFFh
0x10027db8  mov     eax, 1
0x10027dbd  mov     [ebp+var_378], eax
0x10027dc3  jz      short loc_10027DD9
0x10027dc5  lea     eax, [ebp+var_378]
0x10027dcb  mov     ecx, esi; this
0x10027dcd  push    eax; struct Err *
0x10027dce  call    ?Close@File@@QAEXAAVErr@@@Z; File::Close(Err &)
0x10027dd3  mov     eax, [ebp+var_378]
0x10027dd9  mov     dword ptr [ebx+48h], 0
0x10027de0  test    eax, 0FFFFFFFEh
0x10027de5  jz      short loc_10027E19
0x10027de7  mov     eax, [ebp+var_36C]
0x10027ded  test    eax, eax
0x10027def  jz      short loc_10027DFA
0x10027df1  push    eax; Block
0x10027df2  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10027df7  add     esp, 4
0x10027dfa  mov     eax, [ebp+var_368]
0x10027e00  test    eax, eax
0x10027e02  jz      short loc_10027E19
0x10027e04  push    eax; Block
0x10027e05  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10027e0a  add     esp, 4
0x10027e0d  jmp     short loc_10027E19
0x10027e0f  mov     dword ptr [ebx+0D8h], 2649h
0x10027e19  mov     eax, [ebp+Block]
0x10027e1f  mov     ebx, [ebp+var_334]
0x10027e25  test    al, 8
0x10027e27  jz      short loc_10027E5D
0x10027e29  mov     edi, [ebx+18h]
0x10027e2c  or      eax, 0FFFFFFFFh
0x10027e2f  lock xadd [edi+4Ch], eax
0x10027e34  jnz     short loc_10027E4C
0x10027e36  test    edi, edi
0x10027e38  jz      short loc_10027E4C
0x10027e3a  mov     eax, [edi]
0x10027e3c  push    1; void *
0x10027e3e  mov     esi, [eax]
0x10027e40  mov     ecx, esi
0x10027e42  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10027e48  mov     ecx, edi
0x10027e4a  call    esi
0x10027e4c  mov     dword ptr [ebx+18h], 0
0x10027e53  mov     eax, [ebp+Block]
0x10027e59  test    al, 8
  ... truncated ...
```
