# ErrInit(x,x)

- ea: `0x10027a90`
- end: `0x100287c9`
- name: `_ErrInit@8`
- size: `3385`
- prototype: ``
- caller_count: `2`
- callee_count: `28`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1001ab50`
- `0x10026ec0`

## callees

- `0x10026b60`
- `0x100274a0`
- `0x10027a90`
- `0x100450d0`
- `0x10045f2d`
- `0x1004f89d`
- `0x10050190`
- `0x1005112a`
- `0x10051664`
- `0x1005306e`
- `0x10054888`
- `0x100560b7`
- `0x1005814f`
- `0x1005e748`
- `0x10061111`
- `0x1007480f`
- `0x10074b85`
- `0x10074c55`
- `0x1007a870`
- `0x1007abd0`
- `0x10123110`
- `0x10123b3c`
- `0x10123c5a`
- `0x10123c92`
- `0x10123ca8`
- `0x10123cb3`
- `0x10124048`
- `0x10124a88`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10027b4c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100284cd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10027b4c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100284cd`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x10027b78`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x10028016`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x10027b78`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x10028016`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10027e19`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10027e19`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10028710`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10028710`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x10027c9a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x10027ceb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1002802d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x10027c9a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x10027ceb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1002802d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100280a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100281f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100280a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100281f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1002803c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1002803c`

## pseudocode

```c
int __usercall ErrInit@<eax>(DWORD a1@<ecx>, int a2@<ebp>, size_t a3@<edi>)
{
  int v4; // edi
  int result; // eax
  int v6; // eax
  Err *v7; // ecx
  char *v8; // edi
  Database *v9; // esi
  void *v10; // eax
  BYTE *v11; // eax
  DWORD TickCount; // eax
  UINT v13; // edi
  int v14; // ecx
  unsigned __int16 *v15; // esi
  bool v16; // zf
  int v17; // eax
  BYTE *v18; // ecx
  int v19; // edi
  int v20; // esi
  struct _RTL_CRITICAL_SECTION *v21; // eax
  char *v22; // edi
  char *v23; // esi
  __int16 v24; // ax
  size_t v25; // esi
  int v26; // edi
  unsigned int v27; // kr00_4
  CHAR *v28; // edx
  unsigned int v29; // kr04_4
  BYTE *v30; // esi
  char *v31; // ecx
  char *v32; // eax
  int v33; // esi
  int v34; // edx
  char *v35; // eax
  unsigned int v36; // ecx
  unsigned int v37; // eax
  unsigned int v38; // edi
  int v39; // eax
  struct Instance *v40; // esi
  _DWORD *v41; // ecx
  Table *v42; // ecx
  Table *v43; // ecx
  void (__thiscall ***v44)(int, int); // eax
  unsigned int v45; // edi
  _DWORD *v46; // edi
  int v47; // ecx
  unsigned int v48; // ecx
  struct Instance **v49; // edx
  unsigned int v50; // eax
  unsigned int v51; // eax
  IAccMeth *v52; // ecx
  int v53; // eax
  int v54; // edx
  int v55; // eax
  unsigned int v56; // ecx
  unsigned int v57; // ecx
  _DWORD *v58; // esi
  unsigned int v59; // eax
  unsigned int v60; // eax
  int v61; // ecx
  unsigned int v62; // ecx
  _DWORD *v63; // esi
  unsigned int v64; // eax
  unsigned int v65; // eax
  _DWORD *v66; // esi
  int v67; // ecx
  unsigned int v68; // ecx
  _DWORD *v69; // edx
  unsigned int v70; // eax
  unsigned int v71; // eax
  int v72; // edi
  int v73; // esi
  int v74; // [esp-3B4h] [ebp-3C0h]
  int v75; // [esp-3B0h] [ebp-3BCh]
  const char *v76; // [esp-3ACh] [ebp-3B8h]
  unsigned __int16 v78; // [esp-398h] [ebp-3A4h] BYREF
  _DWORD v79[3]; // [esp-384h] [ebp-390h] BYREF
  void *v80; // [esp-378h] [ebp-384h]
  void *v81; // [esp-374h] [ebp-380h]
  int v82; // [esp-370h] [ebp-37Ch]
  BYTE **v83; // [esp-36Ch] [ebp-378h]
  Database *v84; // [esp-368h] [ebp-374h]
  File *v85; // [esp-364h] [ebp-370h]
  unsigned int v86; // [esp-360h] [ebp-36Ch]
  __int128 v87; // [esp-35Ch] [ebp-368h] BYREF
  unsigned __int16 *v88; // [esp-34Ch] [ebp-358h] BYREF
  void (__thiscall ***v89)(int, int); // [esp-348h] [ebp-354h] BYREF
  int i; // [esp-340h] [ebp-34Ch] BYREF
  BYTE *v91; // [esp-33Ch] [ebp-348h]
  wchar_t v92[260]; // [esp-338h] [ebp-344h] BYREF
  char v93[288]; // [esp-130h] [ebp-13Ch] BYREF
  int *v94; // [esp-10h] [ebp-1Ch]
  struct _EXCEPTION_REGISTRATION_RECORD *ExceptionList; // [esp-Ch] [ebp-18h]
  void *v96; // [esp-8h] [ebp-14h]
  int v97; // [esp-4h] [ebp-10h]
  int v98; // [esp+0h] [ebp-Ch]
  void *v99; // [esp+4h] [ebp-8h]
  int v100; // [esp+8h] [ebp-4h] BYREF
  void *retaddr; // [esp+Ch] [ebp+0h]

  v98 = a2;
  v99 = retaddr;
  v97 = -1;
  v96 = &loc_10124B40;
  ExceptionList = NtCurrentTeb()->NtTib.ExceptionList;
  v94 = &v100;
  v86 = a1;
  v4 = 2316 * a1;
  v82 = 2316 * a1;
  if ( *((_DWORD *)rgtib + 579 * a1 + 263) )
    return -1030;
  result = ErrReadRegistry(a1);
  if ( result < 0 )
    return result;
  if ( !fOneTimeJetInitDone )
  {
    dbidFree = -1;
    dbidInit = 255;
    dword_1016DEFC = -1;
    dword_1016DAFC = (int)vdbfndefInvalidDbid;
    if ( Block )
      _free(Block);
    Block = 0;
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
  v91 = 0;
  v83 = (BYTE **)((char *)rgtib + v4 + 2280);
  v6 = 1;
  v89 = (void (__thiscall ***)(int, int))(a1 + 144);
  LODWORD(v87) = 1;
  if ( Sys > 1 )
  {
    v6 = Sys;
    LODWORD(v87) = Sys;
    if ( (Sys & 0xFFFFFFFE) != 0 )
    {
      *(_QWORD *)((char *)&v87 + 4) = qword_10130504;
      Err::CopyString(Sys, (unsigned __int16 **)&v87 + 3, dword_1013050C);
      Err::CopyString(v7, &v88, dword_10130510);
      v6 = v87;
    }
  }
  if ( (v6 & 8) == 0 )
  {
    v8 = (char *)operator new(0x74u);
    v91 = (BYTE *)v8;
    *((_DWORD *)v8 + 1) = 0;
    *((_DWORD *)v8 + 2) = 0;
    *(_DWORD *)v8 = 0;
    *((_DWORD *)v8 + 4) = 0;
    *((_DWORD *)v8 + 5) = 0;
    *((_DWORD *)v8 + 3) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v8 + 28));
    v9 = (Database *)operator new(0x40Cu);
    v84 = v9;
    Database::Database(v9, (struct Connection *)v8, (struct Err *)&v87);
    *(_DWORD *)v9 = &TemporaryDatabase::`vftable';
    *((_DWORD *)v9 + 248) = 0;
    *((_DWORD *)v9 + 249) = 0;
    *((_DWORD *)v9 + 250) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)((char *)v9 + 1012));
    *((_DWORD *)v9 + 247) = 0;
    if ( (v87 & 8) == 0 )
    {
      v10 = operator new[](0x4000u);
      *((_DWORD *)v9 + 247) = v10;
      *((_DWORD *)v9 + 248) = v10;
      *((_DWORD *)v9 + 249) = 0x4000;
      Bitmap::Set((Database *)((char *)v9 + 992), 0, 0x20000u, (struct Err *)&v87);
      Bitmap::Clear((Database *)((char *)v9 + 992), 0, (struct Err *)&v87);
      *((_DWORD *)v9 + 251) = 0;
      *((_DWORD *)v9 + 252) = 0x4000;
    }
    v11 = v91;
    *((_DWORD *)v91 + 6) = v9;
    *((_DWORD *)v11 + 27) = 0;
    *((_DWORD *)v11 + 28) = 0;
    *((_DWORD *)v11 + 13) = 5000;
    *((_DWORD *)v11 + 14) = 20;
    *((_DWORD *)v11 + 15) = 0;
    *((_DWORD *)v11 + 16) = 3;
    *((_DWORD *)v11 + 17) = 0;
    *((_DWORD *)v11 + 18) = 1;
    *((_DWORD *)v11 + 19) = 2000;
    *((_DWORD *)v11 + 20) = 50;
    *((_DWORD *)v11 + 21) = 500;
    *((_DWORD *)v11 + 22) = 9500;
    *((_DWORD *)v11 + 23) = 100;
    *((_DWORD *)v11 + 24) = 0;
    *((_DWORD *)v11 + 25) = 0;
    *((_DWORD *)v11 + 26) = 50;
    v78 = 0;
    *((_DWORD *)v9 + 23) = 0;
    *((_DWORD *)v9 + 18) = 1;
    *((_DWORD *)v9 + 24) = 1;
    *((_DWORD *)v9 + 22) = 1;
    *((_DWORD *)v9 + 21) = 1;
    memset((char *)v9 + 424, 101, 0x200u);
    v85 = (Database *)((char *)v9 + 4);
    TickCount = GetTickCount();
    *((_DWORD *)v9 + 6) |= 0x52u;
    v13 = TickCount;
    v14 = v87;
    if ( (v87 & 8) != 0 )
      goto LABEL_32;
    do
    {
      System::AllocateTempFileName((unsigned __int16 **)v14, (unsigned int)&i, v13);
      LOBYTE(v14) = v87;
      if ( (v87 & 8) != 0 )
        break;
      v15 = (unsigned __int16 *)i;
      File::ReallyOpen(v85, (unsigned __int16 *)i, (struct Err *)&v87, (char *)v87);
      LOBYTE(v14) = v87;
      if ( (v87 & 8) == 0 || (v87 & 1) != 0 || DWORD1(v87) != -1201 )
        break;
      if ( (v87 & 0xFFFFFFFE) != 0 )
      {
        if ( HIDWORD(v87) )
          operator delete[]((void *)HIDWORD(v87));
        if ( v88 )
          operator delete[](v88);
      }
      v14 = 1;
      LODWORD(v87) = 1;
      if ( v15 )
      {
        operator delete[](v15);
        v14 = v87;
      }
      ++v13;
    }
    while ( (v14 & 8) == 0 );
    v9 = v84;
    if ( (v14 & 8) != 0
      || (Database::AllocateHashTable(v84, (struct Err *)&v87), (v87 & 8) != 0)
      || (Database::BuildInitialDatabase(v84, &v78, (struct Err *)&v87), (v87 & 8) != 0) )
    {
LABEL_32:
      v16 = *((_DWORD *)v9 + 1) == -1;
      v17 = 1;
      v79[0] = 1;
      if ( !v16 )
      {
        File::Close((Database *)((char *)v9 + 4), (struct Err *)v79);
        v17 = v79[0];
      }
      *((_DWORD *)v9 + 18) = 0;
      if ( (v17 & 0xFFFFFFFE) != 0 )
      {
        if ( v80 )
          operator delete[](v80);
        if ( v81 )
          operator delete[](v81);
      }
    }
    else
    {
      *((_DWORD *)v9 + 54) = 9801;
    }
    v18 = v91;
    if ( (v87 & 8) == 0 )
      goto LABEL_45;
    v19 = *((_DWORD *)v91 + 6);
    if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v19 + 76), 0xFFFFFFFF) && v19 )
    {
      (**(void (__thiscall ***)(int, int))v19)(v19, 1);
      v18 = v91;
    }
    *((_DWORD *)v18 + 6) = 0;
    v6 = v87;
    if ( (v87 & 8) == 0 )
    {
LABEL_45:
      Connection::ScheduleSignatureCheck((Connection *)v18);
      v6 = v87;
    }
    v20 = v86;
    if ( (v6 & 8) == 0 )
    {
      if ( v89 )
      {
        if ( v86 >= 0x40 )
          v20 = -1;
        if ( critJet )
        {
          EnterCriticalSection(critJet);
        }
        else
        {
          v21 = (struct _RTL_CRITICAL_SECTION *)_malloc(0x18u);
          critJet = v21;
          if ( !v21 )
            goto LABEL_78;
          InitializeCriticalSection(v21);
          EnterCriticalSection(critJet);
        }
        if ( v20 == -1 )
        {
          LeaveCriticalSection(critJet);
        }
        else
        {
          v22 = (char *)rgtib + 2316 * v20;
          v23 = v22 + 520;
          do
          {
            v24 = *(_WORD *)v23;
            v23 += 2;
          }
          while ( v24 );
          v25 = ((v23 - (v22 + 522)) >> 1) + 1;
          if ( v25 > 0x104 )
            v25 = 260;
          wcsncpy(v92, (const wchar_t *)v22 + 260, v25);
          v92[v25 - 1] = 0;
          v26 = *((_DWORD *)v22 + 260);
          LeaveCriticalSection(critJet);
          if ( v92[0] )
          {
            v27 = wcslen(v92);
            if ( *((_DWORD *)v91 + 27) )
            {
              operator delete[](*((void **)v91 + 27));
              *((_DWORD *)v91 + 27) = 0;
            }
            v28 = (CHAR *)operator new[](2 * v27 + 1);
            *((_DWORD *)v91 + 27) = v28;
            if ( (v87 & 8) == 0 )
            {
              v89 = (void (__thiscall ***)(int, int))(2 * v27);
              v29 = wcslen(v92);
              if ( v29 == -1 )
              {
                v30 = v91;
                *v28 = 0;
                *((_DWORD *)v30 + 28) = v26;
              }
              else if ( ErrGenericWideNToCbMultiByte(0, v92, v29 + 1, v28, (int *)&v89, v74, v75) < 0 )
              {
                if ( (int)v87 < 8 )
                {
                  if ( (v87 & 0xFFFFFFFE) != 0 )
                  {
                    if ( HIDWORD(v87) )
                      operator delete[]((void *)HIDWORD(v87));
                    if ( v88 )
                      operator delete[](v88);
                  }
                  v87 = _xmm;
                  v88 = 0;
                }
                v30 = v91;
                if ( *((_DWORD *)v91 + 27) )
                  operator delete[](*((void **)v91 + 27));
                *((_DWORD *)v30 + 27) = 0;
              }
              else
              {
                v30 = v91;
                *((_DWORD *)v91 + 28) = v26;
              }
              goto LABEL_79;
            }
          }
        }
      }
LABEL_78:
      v30 = v91;
LABEL_79:
      Connection::ReadConfigTree(v30, 0, "SOFTWARE\\Microsoft\\Jet\\4.0\\Engines\\Jet 4.0");
      v31 = (char *)*((_DWORD *)v30 + 27);
      if ( v31 && *v31 )
      {
        v32 = v93;
        v33 = 2147483646;
        i = 275;
        while ( v33 && *v31 )
        {
          --v33;
          *v32++ = *v31++;
          if ( !--i )
          {
            --v32;
            break;
          }
        }
        *v32 = 0;
        v34 = 275;
        v35 = v93;
        while ( *v35 )
        {
          ++v35;
          if ( !--v34 )
            goto LABEL_91;
        }
        StringCopyWorkerA(v31, (size_t)"\\Engines\\Jet", (size_t *)v31, v76, a3);
LABEL_91:
        v30 = v91;
        Connection::ReadConfigTree(v91, *((HKEY *)v91 + 28), v93);
      }
      if ( !dword_10130518 && *((_DWORD *)v30 + 16) )
        dword_10130514 = *((_DWORD *)v30 + 16);
      v36 = *((_DWORD *)v30 + 15) / 4;
      if ( !dword_10130560 )
      {
        dword_10130560 = 1;
        if ( v36 )
        {
          if ( v36 < 0x40 )
            v36 = 64;
          if ( v36 > dword_10130540 )
            v36 = dword_10130540;
          dword_10130544 = v36;
        }
      }
      v37 = *((_DWORD *)v30 + 26);
      pReplCallbacks = (int)&replCallsDef;
      if ( v37 > 0x32 )
        v37 = 50;
      dword_1013056C = v37;
      v6 = v87;
      goto LABEL_106;
    }
  }
  v30 = v91;
LABEL_106:
  if ( (v6 & 8) != 0 )
  {
    if ( v30 )
    {
      while ( *((_DWORD *)v30 + 2) )
      {
        v38 = **(_DWORD **)v30;
        v86 = v38;
        if ( v38 )
        {
          v97 = 1;
          while ( *(int *)(v38 + 8) > 0 )
          {
            v79[0] = 1;
            Session::AbortTransaction((Session *)v38, (struct Err *)v79);
            if ( (v79[0] & 0xFFFFFFFE) != 0 )
            {
              if ( v80 )
                operator delete[](v80);
              if ( v81 )
                operator delete[](v81);
            }
          }
          v39 = *(_DWORD *)(v38 + 164) - 1;
          for ( i = v39; v39 >= 0; i = v39 )
          {
            v40 = *(struct Instance **)(*(_DWORD *)(v38 + 156) + 4 * v39);
            v41 = (_DWORD *)*((_DWORD *)v40 + 16);
            *((_DWORD *)v40 + 16) = (char *)v41 - 1;
            if ( v41 == (_DWORD *)1 )
            {
              LOBYTE(v97) = 2;
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
              while ( *((_DWORD *)v40 + 2) )
              {
                v44 = **(void (__thiscall *****)(int, int))v40;
                v89 = v44;
                if ( v44 )
                  (**v44)((int)v89, 1);
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
                    goto LABEL_138;
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
LABEL_138:
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
              v38 = v86;
            }
            v39 = i - 1;
          }
          v53 = *(_DWORD *)(v38 + 200) - 1;
          if ( v53 >= 0 )
          {
            while ( 1 )
            {
              v89 = (void (__thiscall ***)(int, int))(v53 - 1);
              v54 = *(_DWORD *)(*(_DWORD *)(v38 + 192) + 4 * v53);
              v55 = 0;
              v56 = *(_DWORD *)(v54 + 120);
              if ( v56 )
                break;
LABEL_153:
              if ( v55 != v56 )
                goto LABEL_154;
LABEL_164:
              v53 = (int)v89;
              if ( (int)v89 < 0 )
                goto LABEL_165;
            }
            while ( *(_DWORD *)(*(_DWORD *)(v54 + 112) + 4 * v55) != v38 )
            {
              if ( ++v55 >= v56 )
                goto LABEL_153;
            }
LABEL_154:
            if ( v56 )
            {
              *(_DWORD *)(*(_DWORD *)(v54 + 112) + 4 * v56) = v38;
              v57 = 0;
              v58 = *(_DWORD **)(v54 + 112);
              if ( *v58 != v38 )
              {
                do
                  ++v57;
                while ( v58[v57] != v38 );
              }
              v59 = *(_DWORD *)(v54 + 120);
              if ( v57 < v59 )
              {
                v60 = v59 - 1;
                *(_DWORD *)(v54 + 120) = v60;
                v58[v57] = v58[v60];
              }
            }
            v61 = *(_DWORD *)(v38 + 200);
            if ( v61 )
            {
              *(_DWORD *)(*(_DWORD *)(v38 + 192) + 4 * v61) = v54;
              v62 = 0;
              v63 = *(_DWORD **)(v38 + 192);
              if ( *v63 != v54 )
              {
                do
                  ++v62;
                while ( v63[v62] != v54 );
              }
              v64 = *(_DWORD *)(v38 + 200);
              if ( v62 < v64 )
              {
                v65 = v64 - 1;
                *(_DWORD *)(v38 + 200) = v65;
                v63[v62] = v63[v65];
              }
            }
            goto LABEL_164;
          }
LABEL_165:
          v66 = *(_DWORD **)v38;
          v67 = *(_DWORD *)(*(_DWORD *)v38 + 8);
          if ( v67 )
          {
            *(_DWORD *)(*v66 + 4 * v67) = v38;
            v68 = 0;
            v69 = (_DWORD *)*v66;
            if ( *(_DWORD *)*v66 != v38 )
            {
              do
                ++v68;
              while ( v69[v68] != v38 );
            }
            v70 = v66[2];
            if ( v68 < v70 )
            {
              v71 = v70 - 1;
              v66[2] = v71;
              v69[v68] = v69[v71];
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
          v30 = v91;
        }
      }
      v72 = *((_DWORD *)v30 + 6);
      if ( v72 && !_InterlockedExchangeAdd((volatile signed __int32 *)(v72 + 76), 0xFFFFFFFF) )
      {
        (**(void (__thiscall ***)(int, int))v72)(v72, 1);
        v30 = v91;
      }
      if ( *((_DWORD *)v30 + 27) )
        operator delete[](*((void **)v30 + 27));
      v97 = 3;
      DeleteCriticalSection((LPCRITICAL_SECTION)(v30 + 28));
      if ( *((_DWORD *)v30 + 3) )
        operator delete[](*((void **)v30 + 3));
      if ( *(_DWORD *)v30 )
        operator delete[](*(void **)v30);
      operator delete(v30, 0x74u);
      v6 = v87;
    }
  }
  else
  {
    *v83 = v30;
  }
  if ( (v6 & 1) != 0 )
    v73 = 0;
  else
    v73 = DWORD1(v87);
  if ( (v6 & 0xFFFFFFFE) != 0 )
  {
    if ( HIDWORD(v87) )
      operator delete[]((void *)HIDWORD(v87));
    if ( v88 )
      operator delete[](v88);
  }
  if ( v73 < 0 )
    return v73;
  *(_DWORD *)((char *)rgtib + v82 + 1052) = 1;
  return 0;
}

```

## disassembly

```asm
0x10027a90  mov     edi, edi
0x10027a92  push    ebx
0x10027a93  mov     ebx, esp
0x10027a95  sub     esp, 8
0x10027a98  and     esp, 0FFFFFFF8h
0x10027a9b  add     esp, 4
0x10027a9e  push    ebp
0x10027a9f  mov     ebp, [ebx+4]
0x10027aa2  mov     [esp+0Ch+var_8], ebp
0x10027aa6  mov     ebp, esp
0x10027aa8  push    0FFFFFFFFh
0x10027aaa  push    offset loc_10124B40
0x10027aaf  mov     eax, large fs:0
0x10027ab5  push    eax
0x10027ab6  push    ebx
0x10027ab7  sub     esp, 390h
0x10027abd  mov     eax, ___security_cookie
0x10027ac2  xor     eax, ebp
0x10027ac4  mov     [ebp-14h], eax
0x10027ac7  push    esi
0x10027ac8  push    edi; cchToCopy
0x10027ac9  push    eax; unsigned int
0x10027aca  lea     eax, [ebp-0Ch]
0x10027acd  mov     large fs:0, eax
0x10027ad3  mov     esi, ecx
0x10027ad5  mov     [ebp-360h], esi
0x10027adb  mov     eax, _rgtib
0x10027ae0  imul    edi, esi, 90Ch
0x10027ae6  mov     [ebp-370h], edi
0x10027aec  cmp     dword ptr [edi+eax+41Ch], 0
0x10027af4  jz      short loc_10027B00
0x10027af6  mov     eax, 0FFFFFBFAh
0x10027afb  jmp     loc_100287AB
0x10027b00  call    ErrReadRegistry
0x10027b05  test    eax, eax
0x10027b07  js      loc_100287AB
0x10027b0d  cmp     _fOneTimeJetInitDone, 0
0x10027b14  jnz     loc_10027BC6
0x10027b1a  mov     eax, Block
0x10027b1f  mov     _dbidFree, 0FFFFFFFFh
0x10027b29  mov     _dbidInit, 0FFh
0x10027b33  mov     dword_1016DEFC, 0FFFFFFFFh
0x10027b3d  mov     dword_1016DAFC, offset _vdbfndefInvalidDbid
0x10027b47  test    eax, eax
0x10027b49  jz      short loc_10027B55
0x10027b4b  push    eax; Block
0x10027b4c  call    ds:__imp__free
0x10027b52  add     esp, 4
0x10027b55  push    2000h; Size
0x10027b5a  mov     Block, 0
0x10027b64  mov     _dbidFree, 0FFh
0x10027b6e  mov     _tableidFree, 0FFFFFFFFh
0x10027b78  call    ds:__imp__malloc
0x10027b7e  add     esp, 4
0x10027b81  mov     _rgvtdefname, eax
0x10027b86  test    eax, eax
0x10027b88  jnz     short loc_10027B94
0x10027b8a  mov     eax, 0FFFFFC0Dh
0x10027b8f  jmp     loc_100287AB
0x10027b94  push    400h; Size
0x10027b99  push    0; Val
0x10027b9b  push    offset _rgrepdbinfo; void *
0x10027ba0  call    _memset
0x10027ba5  add     esp, 0Ch
0x10027ba8  mov     _tableidInit, 7FFh
0x10027bb2  push    7FFh
0x10027bb7  call    _ReleaseTableid@4; ReleaseTableid(x)
0x10027bbc  mov     _fOneTimeJetInitDone, 1
0x10027bc6  mov     eax, _rgtib
0x10027bcb  mov     ecx, ?Sys@@3VSystem@@A; this
0x10027bd1  add     eax, 8E8h
0x10027bd6  add     eax, edi
0x10027bd8  mov     dword ptr [ebp-33Ch], 0
0x10027be2  mov     [ebp-36Ch], eax
0x10027be8  lea     edi, [esi+90h]
0x10027bee  mov     eax, 1
0x10027bf3  mov     [ebp-348h], edi
0x10027bf9  mov     [ebp-35Ch], eax
0x10027bff  cmp     ecx, eax
0x10027c01  jle     short loc_10027C53
0x10027c03  mov     eax, ecx
0x10027c05  mov     [ebp-35Ch], eax
0x10027c0b  test    ecx, 0FFFFFFFEh
0x10027c11  jz      short loc_10027C53
0x10027c13  mov     eax, dword ptr qword_10130504
0x10027c18  push    dword_1013050C; unsigned __int16 *
0x10027c1e  mov     [ebp-358h], eax
0x10027c24  mov     eax, dword ptr qword_10130504+4
0x10027c29  mov     [ebp-354h], eax
0x10027c2f  lea     eax, [ebp-350h]
0x10027c35  push    eax; unsigned __int16 **
0x10027c36  call    ?CopyString@Err@@AAEXAAPAGQAG@Z; Err::CopyString(ushort * &,ushort * const)
0x10027c3b  push    dword_10130510; unsigned __int16 *
0x10027c41  lea     eax, [ebp-34Ch]
0x10027c47  push    eax; unsigned __int16 **
0x10027c48  call    ?CopyString@Err@@AAEXAAPAGQAG@Z; Err::CopyString(ushort * &,ushort * const)
0x10027c4d  mov     eax, [ebp-35Ch]
0x10027c53  test    al, 8
0x10027c55  jnz     loc_10028339
0x10027c5b  push    74h ; 't'; Size
0x10027c5d  call    ??2@YAPAXI@Z; operator new(uint)
0x10027c62  mov     edi, eax
0x10027c64  add     esp, 4
0x10027c67  mov     [ebp-33Ch], edi
0x10027c6d  lea     ecx, [edi+1Ch]
0x10027c70  mov     dword ptr [edi+4], 0
0x10027c77  push    ecx; lpCriticalSection
0x10027c78  mov     dword ptr [edi+8], 0
0x10027c7f  mov     dword ptr [edi], 0
0x10027c85  mov     dword ptr [edi+10h], 0
0x10027c8c  mov     dword ptr [edi+14h], 0
0x10027c93  mov     dword ptr [edi+0Ch], 0
0x10027c9a  call    ds:__imp__InitializeCriticalSection@4; InitializeCriticalSection(x)
0x10027ca0  push    40Ch; Size
0x10027ca5  call    ??2@YAPAXI@Z; operator new(uint)
0x10027caa  add     esp, 4
0x10027cad  mov     esi, eax
0x10027caf  lea     eax, [ebp-35Ch]
0x10027cb5  mov     [ebp-368h], esi
0x10027cbb  mov     ecx, esi; this
0x10027cbd  push    eax; struct Err *
0x10027cbe  push    edi; struct Connection *
0x10027cbf  call    ??0Database@@QAE@PAVConnection@@AAVErr@@@Z; Database::Database(Connection *,Err &)
0x10027cc4  mov     dword ptr [esi], offset ??_7TemporaryDatabase@@6B@; const TemporaryDatabase::`vftable'
0x10027cca  lea     edi, [esi+3E0h]
0x10027cd0  lea     eax, [esi+3F4h]
0x10027cd6  mov     dword ptr [edi], 0
0x10027cdc  push    eax; lpCriticalSection
0x10027cdd  mov     dword ptr [edi+4], 0
0x10027ce4  mov     dword ptr [edi+8], 0
0x10027ceb  call    ds:__imp__InitializeCriticalSection@4; InitializeCriticalSection(x)
0x10027cf1  mov     dword ptr [esi+3DCh], 0
0x10027cfb  test    byte ptr [ebp-35Ch], 8
0x10027d02  jnz     short loc_10027D59
0x10027d04  push    4000h; unsigned int
0x10027d09  call    ??_U@YAPAXI@Z; operator new[](uint)
0x10027d0e  add     esp, 4
0x10027d11  mov     [esi+3DCh], eax
0x10027d17  mov     [edi], eax
0x10027d19  xor     edx, edx; unsigned int
0x10027d1b  lea     eax, [ebp-35Ch]
0x10027d21  mov     dword ptr [edi+4], 4000h
0x10027d28  mov     ecx, edi; this
0x10027d2a  push    eax; struct Err *
0x10027d2b  push    20000h; unsigned int
0x10027d30  call    ?Set@Bitmap@@QAIXKKAAVErr@@@Z; Bitmap::Set(ulong,ulong,Err &)
0x10027d35  lea     eax, [ebp-35Ch]
0x10027d3b  mov     ecx, edi; this
0x10027d3d  push    eax; struct Err *
0x10027d3e  push    0; unsigned int
0x10027d40  call    ?Clear@Bitmap@@QAEXKAAVErr@@@Z; Bitmap::Clear(ulong,Err &)
0x10027d45  mov     dword ptr [esi+3ECh], 0
0x10027d4f  mov     dword ptr [esi+3F0h], 4000h
0x10027d59  mov     eax, [ebp-33Ch]
0x10027d5f  push    200h; Size
0x10027d64  push    65h ; 'e'; Val
0x10027d66  mov     [eax+18h], esi
0x10027d69  mov     dword ptr [eax+6Ch], 0
0x10027d70  mov     dword ptr [eax+70h], 0
0x10027d77  mov     dword ptr [eax+34h], 1388h
0x10027d7e  mov     dword ptr [eax+38h], 14h
0x10027d85  mov     dword ptr [eax+3Ch], 0
0x10027d8c  mov     dword ptr [eax+40h], 3
0x10027d93  mov     dword ptr [eax+44h], 0
0x10027d9a  mov     dword ptr [eax+48h], 1
0x10027da1  mov     dword ptr [eax+4Ch], 7D0h
0x10027da8  mov     dword ptr [eax+50h], 32h ; '2'
0x10027daf  mov     dword ptr [eax+54h], 1F4h
0x10027db6  mov     dword ptr [eax+58h], 251Ch
0x10027dbd  mov     dword ptr [eax+5Ch], 64h ; 'd'
0x10027dc4  mov     dword ptr [eax+60h], 0
0x10027dcb  mov     dword ptr [eax+64h], 0
0x10027dd2  mov     dword ptr [eax+68h], 32h ; '2'
0x10027dd9  xor     eax, eax
0x10027ddb  mov     [ebp-398h], ax
0x10027de2  mov     [esi+5Ch], eax
0x10027de5  lea     eax, [esi+1A8h]
0x10027deb  push    eax; void *
0x10027dec  mov     dword ptr [esi+48h], 1
0x10027df3  mov     dword ptr [esi+60h], 1
0x10027dfa  mov     dword ptr [esi+58h], 1
0x10027e01  mov     dword ptr [esi+54h], 1
0x10027e08  call    _memset
0x10027e0d  add     esp, 0Ch
0x10027e10  lea     eax, [esi+4]
0x10027e13  mov     [ebp-364h], eax
0x10027e19  call    ds:__imp__GetTickCount@0; GetTickCount()
0x10027e1f  or      dword ptr [esi+18h], 52h
0x10027e23  mov     edi, eax
0x10027e25  mov     ecx, [ebp-35Ch]; unsigned __int16 **
0x10027e2b  test    cl, 8
0x10027e2e  jnz     loc_10027F27
0x10027e34  lea     eax, [ebp-35Ch]
0x10027e3a  push    eax
0x10027e3b  push    edi; uUnique
0x10027e3c  lea     eax, [ebp-340h]
0x10027e42  push    eax; unsigned int
0x10027e43  call    ?AllocateTempFileName@System@@QAEXPAPAGIAAVErr@@@Z; System::AllocateTempFileName(ushort * *,uint,Err &)
0x10027e48  mov     ecx, [ebp-35Ch]
0x10027e4e  test    cl, 8
0x10027e51  jnz     loc_10027EE3
0x10027e57  mov     esi, [ebp-340h]
0x10027e5d  lea     eax, [ebp-35Ch]
0x10027e63  push    ecx; char *
0x10027e64  mov     ecx, [ebp-364h]; this
0x10027e6a  push    eax; struct Err *
0x10027e6b  push    esi; unsigned __int16 *
0x10027e6c  call    ?ReallyOpen@File@@AAEXPAGAAVErr@@PAD@Z; File::ReallyOpen(ushort *,Err &,char *)
0x10027e71  mov     ecx, [ebp-35Ch]
0x10027e77  test    cl, 8
0x10027e7a  jz      short loc_10027EE3
0x10027e7c  test    cl, 1
0x10027e7f  jnz     short loc_10027EE3
0x10027e81  cmp     dword ptr [ebp-358h], 0FFFFFB4Fh
0x10027e8b  jnz     short loc_10027EE3
0x10027e8d  test    ecx, 0FFFFFFFEh
0x10027e93  jz      short loc_10027EBB
0x10027e95  mov     eax, [ebp-350h]
0x10027e9b  test    eax, eax
0x10027e9d  jz      short loc_10027EA8
0x10027e9f  push    eax; Block
0x10027ea0  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10027ea5  add     esp, 4
0x10027ea8  mov     eax, [ebp-34Ch]
0x10027eae  test    eax, eax
0x10027eb0  jz      short loc_10027EBB
0x10027eb2  push    eax; Block
0x10027eb3  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10027eb8  add     esp, 4
0x10027ebb  mov     ecx, 1
0x10027ec0  mov     [ebp-35Ch], ecx
0x10027ec6  test    esi, esi
0x10027ec8  jz      short loc_10027ED9
0x10027eca  push    esi; Block
0x10027ecb  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10027ed0  mov     ecx, [ebp-35Ch]
0x10027ed6  add     esp, 4
0x10027ed9  inc     edi
0x10027eda  test    cl, 8
0x10027edd  jz      loc_10027E34
0x10027ee3  mov     esi, [ebp-368h]
0x10027ee9  test    cl, 8
0x10027eec  jnz     short loc_10027F27
0x10027eee  lea     eax, [ebp-35Ch]
0x10027ef4  mov     ecx, esi; this
0x10027ef6  push    eax; struct Err *
0x10027ef7  call    ?AllocateHashTable@Database@@IAEXAAVErr@@@Z; Database::AllocateHashTable(Err &)
0x10027efc  mov     ecx, [ebp-35Ch]
0x10027f02  test    cl, 8
0x10027f05  jnz     short loc_10027F27
0x10027f07  lea     eax, [ebp-35Ch]
0x10027f0d  mov     ecx, esi; this
0x10027f0f  push    eax; struct Err *
0x10027f10  lea     eax, [ebp-398h]
0x10027f16  push    eax; unsigned __int16 *
0x10027f17  call    ?BuildInitialDatabase@Database@@IAEXQBGAAVErr@@@Z; Database::BuildInitialDatabase(ushort const * const,Err &)
0x10027f1c  mov     ecx, [ebp-35Ch]
0x10027f22  test    cl, 8
0x10027f25  jz      short loc_10027F83
0x10027f27  cmp     dword ptr [esi+4], 0FFFFFFFFh
0x10027f2b  lea     ecx, [esi+4]; this
0x10027f2e  mov     eax, 1
0x10027f33  mov     [ebp-384h], eax
0x10027f39  jz      short loc_10027F4D
0x10027f3b  lea     eax, [ebp-384h]
0x10027f41  push    eax; struct Err *
0x10027f42  call    ?Close@File@@QAEXAAVErr@@@Z; File::Close(Err &)
0x10027f47  mov     eax, [ebp-384h]
0x10027f4d  mov     dword ptr [esi+48h], 0
0x10027f54  test    eax, 0FFFFFFFEh
0x10027f59  jz      short loc_10027F8D
0x10027f5b  mov     eax, [ebp-378h]
0x10027f61  test    eax, eax
0x10027f63  jz      short loc_10027F6E
0x10027f65  push    eax; Block
0x10027f66  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10027f6b  add     esp, 4
0x10027f6e  mov     eax, [ebp-374h]
0x10027f74  test    eax, eax
0x10027f76  jz      short loc_10027F8D
0x10027f78  push    eax; Block
0x10027f79  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10027f7e  add     esp, 4
0x10027f81  jmp     short loc_10027F8D
0x10027f83  mov     dword ptr [esi+0D8h], 2649h
0x10027f8d  mov     eax, [ebp-35Ch]
0x10027f93  mov     ecx, [ebp-33Ch]
0x10027f99  test    al, 8
0x10027f9b  jz      short loc_10027FD7
0x10027f9d  mov     edi, [ecx+18h]
0x10027fa0  or      eax, 0FFFFFFFFh
0x10027fa3  lock xadd [edi+4Ch], eax
0x10027fa8  jnz     short loc_10027FC6
0x10027faa  test    edi, edi
0x10027fac  jz      short loc_10027FC6
0x10027fae  mov     eax, [edi]
0x10027fb0  push    1; void *
0x10027fb2  mov     esi, [eax]
0x10027fb4  mov     ecx, esi
0x10027fb6  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
  ... truncated ...
```
