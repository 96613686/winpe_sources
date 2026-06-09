# JetCompact(x,x,x,x,x,x,x)

- ea: `0x10025b10`
- end: `0x10026745`
- name: `_JetCompact@28`
- size: `3125`
- prototype: `int __stdcall(void *, int, int, int, int, int, int)`
- caller_count: `0`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x10017010`
- `0x1001eb00`
- `0x1001eb70`
- `0x1001f490`
- `0x10023110`
- `0x10023db0`
- `0x10023f60`
- `0x10024920`
- `0x10024be0`
- `0x100250e0`
- `0x100251c0`
- `0x10025230`
- `0x100252a0`
- `0x10025b10`
- `0x1002d1d0`
- `0x1002ebb0`
- `0x1003e820`
- `0x100429d0`
- `0x10043090`
- `0x10043700`
- `0x100437d0`
- `0x10043840`
- `0x100440c0`
- `0x10044250`
- `0x100447a0`
- `0x1004638c`
- `0x10050000`
- `0x10117160`
- `0x10122f60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10026643`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10026643`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x10025c77`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x10025c77`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1002661a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1002661a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10025b9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10025bd4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10025c08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10026694`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100266d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100266fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10026723`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10025b9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10025bd4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10025c08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10026694`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100266d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100266fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10026723`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10025b6c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10025b6c`

## string_xrefs

- `0x10025f96`: `FTPDirectory`

## pseudocode

```c
int __stdcall JetCompact(
        Session *a1,
        const unsigned __int16 *a2,
        int a3,
        const unsigned __int16 *a4,
        int a5,
        void (__stdcall *a6)(_DWORD, _DWORD, _DWORD, _DWORD),
        unsigned int a7)
{
  int v7; // eax
  Session *v8; // esi
  _DWORD *v10; // ebx
  void (__stdcall *v11)(_DWORD, _DWORD, _DWORD, _DWORD); // ecx
  int Containers; // edi
  unsigned int v13; // ecx
  _DWORD *v14; // edx
  unsigned int v15; // edi
  int v16; // edi
  bool v17; // zf
  int v18; // eax
  int v19; // eax
  int v20; // ecx
  Session *v21; // ecx
  unsigned int v22; // edx
  Session *v23; // ecx
  Session *v24; // ecx
  unsigned int v25; // edx
  Session *v26; // ecx
  unsigned int v27; // edx
  int v28; // eax
  int v29; // eax
  int v30; // edi
  int v31; // edx
  int v32; // edx
  int v33; // ecx
  int v34; // eax
  int v35; // esi
  int v36; // eax
  int v37; // eax
  int v38; // eax
  __int16 *v39; // [esp+48h] [ebp-A8h]
  int v40; // [esp+48h] [ebp-A8h]
  unsigned int v41; // [esp+4Ch] [ebp-A4h]
  const unsigned __int16 *v42; // [esp+50h] [ebp-A0h]
  int v43; // [esp+54h] [ebp-9Ch]
  int v44; // [esp+54h] [ebp-9Ch]
  int v45; // [esp+68h] [ebp-88h] BYREF
  unsigned int v46; // [esp+6Ch] [ebp-84h] BYREF
  unsigned int v47; // [esp+70h] [ebp-80h] BYREF
  int v48; // [esp+74h] [ebp-7Ch] BYREF
  int v49; // [esp+78h] [ebp-78h] BYREF
  int v50; // [esp+7Ch] [ebp-74h]
  unsigned int v51; // [esp+80h] [ebp-70h]
  int v52; // [esp+84h] [ebp-6Ch] BYREF
  void (__stdcall *v53)(_DWORD, _DWORD, _DWORD, _DWORD); // [esp+88h] [ebp-68h]
  BOOL v54; // [esp+8Ch] [ebp-64h]
  int v55; // [esp+90h] [ebp-60h]
  int v56; // [esp+94h] [ebp-5Ch]
  int v57; // [esp+98h] [ebp-58h] BYREF
  int v58; // [esp+9Ch] [ebp-54h] BYREF
  int v59; // [esp+A0h] [ebp-50h] BYREF
  __int64 v60; // [esp+A4h] [ebp-4Ch]
  _DWORD v61[6]; // [esp+ACh] [ebp-44h] BYREF
  _DWORD v62[10]; // [esp+C4h] [ebp-2Ch] BYREF

  v49 = a3;
  v50 = a5;
  v51 = (unsigned int)a4;
  v53 = a6;
  v56 = 0;
  v55 = 0;
  v54 = 0;
  EnterCriticalSection(critJet);
  v7 = isibHead;
  if ( isibHead == -1 )
  {
LABEL_5:
    LeaveCriticalSection(critJet);
    return -1104;
  }
  v8 = a1;
  while ( (Session *)rgsib[26 * v7] != a1 )
  {
    v7 = dword_1016EAE8[26 * v7];
    if ( v7 == -1 )
      goto LABEL_5;
  }
  v47 = 104 * v7;
  if ( dword_1016EAEC[26 * v7] )
  {
    LeaveCriticalSection(critJet);
    return -1108;
  }
  if ( (a7 & 3) == 3 || (a7 & 0xFFFFEC80) != 0 )
  {
    LeaveCriticalSection(critJet);
    return -1003;
  }
  if ( wcslen(a2) < 0x104 && wcslen(a4) < 0x104 )
  {
    v10 = _malloc(0x88DCu);
    if ( !v10 )
      return -1011;
    v11 = v53;
    *v10 = v53;
    v10[580] = (a7 >> 2) & 1;
    v10[581] = 0;
    v10[582] = 0;
    v10[583] = 0;
    if ( v11 )
    {
      v59 = 12;
      v60 = 0;
      v53(a1, 4, 5, &v59);
    }
    v10[1] = a1;
    v42 = (const unsigned __int16 *)v50;
    v10[588] = 0;
    v41 = v51;
    *((_WORD *)v10 + 1196) = 0;
    v39 = (__int16 *)v49;
    v10[590] = 0;
    v10[589] = 0;
    v10[591] = 0;
    v10[592] = -1;
    v10[597] = 0;
    Containers = ErrCompactInit((int)v10, (int)a2, v39, v41, v42, a7);
    if ( Containers < 0 )
    {
      v56 = v10[6];
      goto LABEL_137;
    }
    v13 = v10[4];
    v14 = rgtib;
    v15 = v47;
    if ( v13 >= 0x30000 && v10[5] >= 0x30000u && *((_DWORD *)rgtib + 579 * *(int *)((char *)dword_1016EAA4 + v47) + 571) )
      v10[588] = 1;
    if ( v13 < 0x40000 && v10[5] >= 0x40000u && v14[579 * *(int *)((char *)dword_1016EAA4 + v15) + 576] )
      v10[590] = 1;
    Containers = ErrCreateContainers(v10);
    if ( Containers >= 0 )
    {
      v16 = 2 * v10[12];
      if ( FDbidIsReplicable(v10[2]) )
      {
        v17 = v10[4] == 196608;
        v10[8] = v16 + 6;
        if ( v17 && v10[5] >= 0x40000u )
        {
          Containers = ErrDispOpenTable(a1, v10[2], &v49, L"MSysTableGuids", 0x80000000);
          if ( Containers < 0 )
            goto LABEL_122;
          Containers = ErrDispGetTableInfo(a1, v49, v62, 40, 0);
          if ( Containers < 0 )
            goto LABEL_122;
          v43 = v49;
          v10[8] += v62[8];
          ErrDispCloseTable(a1, v43);
          v10[8] += 5;
        }
      }
      else
      {
        v10[8] = v16;
      }
      v10[9] = 0;
      Containers = ErrCopyObjects(v10);
      if ( Containers >= 0 )
      {
        if ( (a7 & 0x100) != 0 || (Containers = ErrCopyRelationships(v10), Containers >= 0) )
        {
          Containers = ErrCopyACLs(v10);
          if ( Containers >= 0 )
          {
            Containers = ErrReportProgress(v10);
            if ( Containers >= 0 )
            {
              Containers = ErrConvert3xTo40(v10);
              if ( Containers >= 0 )
              {
                if ( !FDbidIsReplicable(v10[2]) )
                {
LABEL_117:
                  if ( (a7 & 0x200) == 0 )
                  {
                    LOWORD(v45) = 0;
                    if ( JetIRetrieveProperty(
                           (int)v8,
                           v10[3],
                           (int)L"Databases",
                           L"MSysDb",
                           0,
                           (int)L"Replicable",
                           (int)&v45,
                           2,
                           (int)&v57,
                           (int)&v52,
                           0,
                           0) >= 0
                      && v52 == 10
                      && (_WORD)v45 == 82 )
                    {
                      v54 = off_1012B010(v8, v10[3], 0, 0, 9) >= 0;
                    }
                  }
                  goto LABEL_122;
                }
                v18 = v10[4];
                v47 = -1;
                v49 = 0;
                v46 = -1;
                if ( v18 == 196608 )
                {
                  v49 = v10[5] >= 0x40000u;
                  goto LABEL_93;
                }
                if ( v18 != 0x40000 || v10[5] != 0x40000 )
                  goto LABEL_93;
                Containers = ErrDispOpenTable(v10[1], v10[3], &v46, L"MSysTranspAddress", 2);
                if ( Containers >= 0 )
                {
                  v19 = ErrDispRenameColumn(v10[1], v46, L"HTTPAddress", L"InternetAddress");
                  if ( v19 < 0 && (v19 == -1507 || v19 == -1508) )
                  {
                    Containers = 0;
                  }
                  else
                  {
                    Containers = ErrDispRenameColumn(v10[1], v46, L"FTPAddress", L"HttpScriptsFolder");
                    if ( Containers >= 0 )
                    {
                      Containers = ErrDispRenameColumn(v10[1], v46, L"FTPDirectory", L"InternetDropbox");
                      if ( Containers >= 0 )
                      {
                        v62[0] = 24;
                        v62[2] = 1;
                        Containers = ErrDispAddColumn(v10[1], v46, (int)L"HTTPEnable", (int)v62, 0, 0, (int)&v57);
                        if ( Containers >= 0 )
                        {
                          Containers = ErrDispGetTableColumnInfo(v10[1], v46, L"CMCEnable", v62, 24, 0);
                          if ( Containers >= 0 )
                          {
                            v45 = v62[1];
                            Containers = ErrDispMove2(a1, v46, 0x80000000, 0);
                            if ( Containers >= 0 )
                            {
                              while ( 1 )
                              {
                                if ( v46 >= 0x800 || v46 < tableidInit )
                                  goto LABEL_89;
                                v20 = (int)v8;
                                if ( rgvtdef[4 * v46] != -1 )
                                  v20 = rgvtdef[4 * v46];
                                Containers = (*(int (__thiscall **)(_DWORD, int, int, int, char *, int, int *, _DWORD, _DWORD))(dword_1016362C[4 * v46] + 140))(
                                               *(_DWORD *)(dword_1016362C[4 * v46] + 140),
                                               v20,
                                               dword_10163624[4 * v46],
                                               v45,
                                               (char *)&v48 + 3,
                                               1,
                                               &v58,
                                               0,
                                               0);
                                if ( Containers < 0 )
                                  goto LABEL_90;
                                if ( !v58 )
                                  HIBYTE(v48) = 0;
                                if ( v46 >= 0x800 || v46 < tableidInit )
                                  goto LABEL_89;
                                v21 = a1;
                                v22 = 4 * v46;
                                _mm_lfence();
                                if ( rgvtdef[v22] != -1 )
                                  v21 = (Session *)rgvtdef[4 * v46];
                                Containers = (*(int (__thiscall **)(_DWORD, Session *, int, int))(dword_1016362C[4 * v46]
                                                                                                + 124))(
                                               *(_DWORD *)(dword_1016362C[4 * v46] + 124),
                                               v21,
                                               dword_10163624[4 * v46],
                                               2);
                                if ( Containers < 0 )
                                  goto LABEL_90;
                                if ( v46 >= 0x800 || v46 < tableidInit )
                                  goto LABEL_89;
                                v23 = a1;
                                if ( rgvtdef[4 * v46] != -1 )
                                  v23 = (Session *)rgvtdef[4 * v46];
                                Containers = (*(int (__thiscall **)(_DWORD, Session *, int, int, char *, int, _DWORD, _DWORD))(dword_1016362C[4 * v46] + 156))(
                                               *(_DWORD *)(dword_1016362C[4 * v46] + 156),
                                               v23,
                                               dword_10163624[4 * v46],
                                               v57,
                                               (char *)&v48 + 3,
                                               1,
                                               0,
                                               0);
                                if ( Containers < 0 )
                                  goto LABEL_90;
                                if ( v46 >= 0x800 || v46 < tableidInit )
                                {
LABEL_89:
                                  Containers = -1310;
                                  goto LABEL_90;
                                }
                                v24 = a1;
                                v25 = 4 * v46;
                                _mm_lfence();
                                if ( rgvtdef[v25] != -1 )
                                  v24 = (Session *)rgvtdef[4 * v46];
                                Containers = (*(int (__thiscall **)(_DWORD, Session *, int, _DWORD, _DWORD, _DWORD))(dword_1016362C[4 * v46] + 164))(
                                               *(_DWORD *)(dword_1016362C[4 * v46] + 164),
                                               v24,
                                               dword_10163624[4 * v46],
                                               0,
                                               0,
                                               0);
                                if ( Containers < 0 )
                                  goto LABEL_90;
                                if ( v46 >= 0x800 || v46 < tableidInit )
                                  break;
                                v26 = a1;
                                v27 = 4 * v46;
                                _mm_lfence();
                                if ( rgvtdef[v27] != -1 )
                                  v26 = (Session *)rgvtdef[4 * v46];
                                v28 = (*(int (__thiscall **)(_DWORD, Session *, int, int, _DWORD))(dword_1016362C[4 * v46]
                                                                                                 + 104))(
                                        *(_DWORD *)(dword_1016362C[4 * v46] + 104),
                                        v26,
                                        dword_10163624[4 * v46],
                                        1,
                                        0);
                                Containers = v28;
                                if ( v28 < 0 )
                                  goto LABEL_87;
                                v8 = a1;
                              }
                              v28 = -1310;
                              Containers = -1310;
LABEL_87:
                              if ( v28 == -1603 )
                                Containers = 0;
                            }
                          }
                        }
                      }
                    }
                  }
                }
LABEL_90:
                if ( v46 != -1 )
                  ErrDispCloseTable(v10[1], v46);
                if ( Containers >= 0 )
                {
LABEL_93:
                  LODWORD(v60) = v10[9];
                  v29 = v10[8];
                  v59 = 12;
                  HIDWORD(v60) = v29;
                  if ( v49 )
                  {
                    v8 = a1;
                    Containers = off_1012B008((void *)v10[1], v10[2], v10[3], 1, *v10, (int)&v59);
                    if ( Containers < 0
                      || (LOBYTE(v45) = 0,
                          Containers = JetISetProperty(
                                         a1,
                                         v10[3],
                                         (int)L"Databases",
                                         (int)L"MSysDb",
                                         0,
                                         L"ColumnLevelTracking",
                                         &v45,
                                         1u,
                                         1,
                                         128),
                          Containers < 0) )
                    {
LABEL_115:
                      if ( v47 != -1 )
                        ErrDispCloseDatabase(v8, v47, 0);
                      goto LABEL_117;
                    }
                  }
                  v30 = v10[1];
                  v61[3] = v10[7];
                  v40 = v10[3];
                  v45 = -1;
                  v61[0] = 24;
                  v61[1] = 0;
                  v61[4] = 0;
                  v61[5] = 0;
                  v61[2] = 15;
                  if ( (int)ErrDispOpenTable(v30, v40, &v45, L"MSysConflicts", 2) >= 0 )
                  {
                    v31 = v45;
                    if ( (unsigned int)v45 >= 0x800 || v45 < (unsigned int)tableidInit )
                      goto LABEL_105;
                    v32 = 4 * v45;
                    v33 = v30;
                    _mm_lfence();
                    if ( rgvtdef[v32] != -1 )
                      v33 = rgvtdef[4 * v45];
                    v34 = (*(int (__thiscall **)(_DWORD, int, int, const wchar_t *, _DWORD *, _DWORD, _DWORD, int *))(dword_1016362C[4 * v45] + 8))(
                            *(_DWORD *)(dword_1016362C[4 * v45] + 8),
                            v33,
                            dword_10163624[4 * v45],
                            L"WinningReplicaId",
                            v61,
                            0,
                            0,
                            &v52);
                    if ( v34 >= 0 || v34 == -1508 )
                      ErrDispAddColumn(v30, v45, (int)L"LosingReplicaId", (int)v61, 0, 0, (int)&v52);
                  }
                  v31 = v45;
LABEL_105:
                  if ( v31 != -1 )
                    ErrDispCloseTable(v30, v31);
                  v8 = a1;
                  Containers = ErrOpenDatabase(a1, v51, v50, &v47, 268435458);
                  if ( Containers >= 0 )
                  {
                    *((_DWORD *)*(&rgrepdbinfo + v47) + 57) |= 0x100000u;
                    if ( v49
                      && (Containers = off_1012B008((void *)v10[1], v10[2], v47, 0, *v10, (int)&v59), Containers < 0)
                      || (Containers = off_1012B004((void *)v10[1], v47, *v10, (int)&v59), Containers < 0) )
                    {
                      v8 = a1;
                    }
                    else
                    {
                      v8 = a1;
                      if ( v10[589] )
                      {
                        LOWORD(v45) = 0;
                        *((_DWORD *)*(&rgrepdbinfo + v47) + 57) |= 0x10u;
                        Containers = JetISetProperty(
                                       a1,
                                       v47,
                                       (int)L"Databases",
                                       (int)L"MSysDb",
                                       0,
                                       L"Replicable",
                                       L"R",
                                       2u,
                                       10,
                                       128);
                        JetISetProperty(
                          a1,
                          v47,
                          (int)L"Databases",
                          (int)L"MSysDb",
                          0,
                          L"ReplicableBool",
                          &v45,
                          1u,
                          1,
                          128);
                        if ( v10[589] )
                          v10[589] = 0;
                      }
                    }
                  }
                  goto LABEL_115;
                }
              }
            }
          }
        }
      }
    }
LABEL_122:
    v44 = v10[11];
    v50 = v10[1];
    v35 = ErrDispCloseTable(v50, v44);
    v36 = ErrConvert2xTo30(v10);
    if ( v36 < 0 && v35 >= 0 )
      v35 = v36;
    v37 = ErrDispCloseDatabase(v50, v10[2], 0);
    if ( v37 < 0 && v35 >= 0 )
      v35 = v37;
    v38 = ErrDispCloseDatabase(v50, v10[3], 0);
    if ( v38 >= 0 )
    {
      if ( v35 >= 0 )
      {
LABEL_134:
        if ( v54 )
          off_1012B014(a1, v51, (int)L"~TmpRpRc.mdb", (int)&v52);
        v8 = a1;
LABEL_137:
        if ( v10[592] != -1 )
        {
          ErrDispCloseTable(v10[1], v10[592]);
          v10[592] = -1;
        }
        if ( v10[597] )
          FreeLibrary((HMODULE)v10[597]);
        if ( Containers >= 0 )
        {
          if ( v10[589] )
          {
            ClearErrorInfo(v10[1]);
            Containers = 3800;
            v55 = 1;
          }
        }
        _free(v10);
        if ( v53 )
        {
          if ( Containers >= 0 )
          {
            v59 = 12;
            v60 = 0;
            ((void (__thiscall *)(void (__stdcall *)(_DWORD, _DWORD, _DWORD, _DWORD), Session *, int, int, int *))v53)(
              v53,
              v8,
              4,
              6,
              &v59);
            LeaveCriticalSection(critJet);
            return Containers;
          }
          ((void (__thiscall *)(void (__stdcall *)(_DWORD, _DWORD, _DWORD, _DWORD), Session *, int, int, _DWORD))v53)(
            v53,
            v8,
            4,
            3,
            0);
        }
        else if ( Containers >= 0 )
        {
LABEL_153:
          LeaveCriticalSection(critJet);
          return Containers;
        }
        if ( !v55 )
        {
          if ( Containers != -1201 )
          {
            ErrUtilDeleteFile((void *)v51);
            LeaveCriticalSection(critJet);
            return Containers;
          }
          Containers = v56;
        }
        goto LABEL_153;
      }
    }
    else if ( v35 >= 0 )
    {
      v35 = v38;
    }
    if ( Containers >= 0 )
      Containers = v35;
    goto LABEL_134;
  }
  LeaveCriticalSection(critJet);
  return -1023;
}

```

## disassembly

```asm
0x10025b10  mov     edi, edi
0x10025b12  push    ebp
0x10025b13  mov     ebp, esp
0x10025b15  and     esp, 0FFFFFFF8h
0x10025b18  sub     esp, 8Ch
0x10025b1e  mov     eax, ___security_cookie
0x10025b23  xor     eax, esp
0x10025b25  mov     [esp+8Ch+var_4], eax
0x10025b2c  mov     eax, [ebp+arg_8]
0x10025b2f  push    ebx
0x10025b30  mov     ebx, [ebp+arg_C]
0x10025b33  push    esi
0x10025b34  push    edi
0x10025b35  push    _critJet; lpCriticalSection
0x10025b3b  mov     edi, [ebp+arg_4]
0x10025b3e  mov     dword ptr [esp+9Ch+var_78], eax
0x10025b42  mov     eax, [ebp+arg_10]
0x10025b45  mov     dword ptr [esp+9Ch+var_78+4], eax
0x10025b49  mov     eax, [ebp+arg_14]
0x10025b4c  mov     [esp+9Ch+var_70], ebx
0x10025b50  mov     [esp+9Ch+var_68], eax
0x10025b54  mov     [esp+9Ch+var_5C], 0
0x10025b5c  mov     [esp+9Ch+var_60], 0
0x10025b64  mov     [esp+9Ch+var_64], 0
0x10025b6c  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10025b72  mov     eax, _isibHead
0x10025b77  cmp     eax, 0FFFFFFFFh
0x10025b7a  jz      short loc_10025B96
0x10025b7c  mov     esi, [ebp+arg_0]
0x10025b7f  nop
0x10025b80  imul    ecx, eax, 68h ; 'h'
0x10025b83  cmp     _rgsib[ecx], esi
0x10025b89  jz      short loc_10025BBE
0x10025b8b  mov     eax, dword_1016EAE8[ecx]
0x10025b91  cmp     eax, 0FFFFFFFFh
0x10025b94  jnz     short loc_10025B80
0x10025b96  push    _critJet; lpCriticalSection
0x10025b9c  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10025ba2  mov     eax, 0FFFFFBB0h
0x10025ba7  pop     edi
0x10025ba8  pop     esi
0x10025ba9  pop     ebx
0x10025baa  mov     ecx, [esp+8Ch+var_4]
0x10025bb1  xor     ecx, esp; StackCookie
0x10025bb3  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10025bb8  mov     esp, ebp
0x10025bba  pop     ebp
0x10025bbb  retn    1Ch
0x10025bbe  imul    eax, 68h ; 'h'
0x10025bc1  mov     [esp+98h+var_80], eax
0x10025bc5  cmp     dword_1016EAEC[eax], 0
0x10025bcc  jbe     short loc_10025BF6
0x10025bce  push    _critJet; lpCriticalSection
0x10025bd4  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10025bda  mov     eax, 0FFFFFBACh
0x10025bdf  pop     edi
0x10025be0  pop     esi
0x10025be1  pop     ebx
0x10025be2  mov     ecx, [esp+8Ch+var_4]
0x10025be9  xor     ecx, esp; StackCookie
0x10025beb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10025bf0  mov     esp, ebp
0x10025bf2  pop     ebp
0x10025bf3  retn    1Ch
0x10025bf6  mov     ecx, [ebp+arg_18]
0x10025bf9  mov     eax, ecx
0x10025bfb  and     eax, 3
0x10025bfe  cmp     al, 3
0x10025c00  jnz     short loc_10025C2A
0x10025c02  push    _critJet; lpCriticalSection
0x10025c08  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10025c0e  mov     eax, 0FFFFFC15h
0x10025c13  pop     edi
0x10025c14  pop     esi
0x10025c15  pop     ebx
0x10025c16  mov     ecx, [esp+8Ch+var_4]
0x10025c1d  xor     ecx, esp; StackCookie
0x10025c1f  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10025c24  mov     esp, ebp
0x10025c26  pop     ebp
0x10025c27  retn    1Ch
0x10025c2a  test    ecx, 0FFFFEC80h
0x10025c30  jnz     short loc_10025C02
0x10025c32  mov     ecx, edi
0x10025c34  lea     edx, [ecx+2]
0x10025c37  mov     ax, [ecx]
0x10025c3a  add     ecx, 2
0x10025c3d  test    ax, ax
0x10025c40  jnz     short loc_10025C37
0x10025c42  sub     ecx, edx
0x10025c44  sar     ecx, 1
0x10025c46  cmp     ecx, 104h
0x10025c4c  jnb     loc_1002671D
0x10025c52  mov     ecx, ebx
0x10025c54  lea     edx, [ecx+2]
0x10025c57  mov     ax, [ecx]
0x10025c5a  add     ecx, 2
0x10025c5d  test    ax, ax
0x10025c60  jnz     short loc_10025C57
0x10025c62  sub     ecx, edx
0x10025c64  sar     ecx, 1
0x10025c66  cmp     ecx, 104h
0x10025c6c  jnb     loc_1002671D
0x10025c72  push    88DCh; Size
0x10025c77  call    ds:__imp__malloc
0x10025c7d  mov     ebx, eax
0x10025c7f  add     esp, 4
0x10025c82  test    ebx, ebx
0x10025c84  jnz     short loc_10025CA2
0x10025c86  mov     eax, 0FFFFFC0Dh
0x10025c8b  pop     edi
0x10025c8c  pop     esi
0x10025c8d  pop     ebx
0x10025c8e  mov     ecx, [esp+8Ch+var_4]
0x10025c95  xor     ecx, esp; StackCookie
0x10025c97  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10025c9c  mov     esp, ebp
0x10025c9e  pop     ebp
0x10025c9f  retn    1Ch
0x10025ca2  mov     eax, [ebp+arg_18]
0x10025ca5  mov     ecx, [esp+98h+var_68]
0x10025ca9  shr     eax, 2
0x10025cac  and     eax, 1
0x10025caf  mov     [ebx], ecx
0x10025cb1  mov     [ebx+910h], eax
0x10025cb7  mov     dword ptr [ebx+914h], 0
0x10025cc1  mov     dword ptr [ebx+918h], 0
0x10025ccb  mov     dword ptr [ebx+91Ch], 0
0x10025cd5  test    ecx, ecx
0x10025cd7  jz      short loc_10025D00
0x10025cd9  lea     eax, [esp+98h+var_50]
0x10025cdd  mov     [esp+98h+var_50], 0Ch
0x10025ce5  push    eax
0x10025ce6  push    5
0x10025ce8  push    4; unsigned int
0x10025cea  xorps   xmm0, xmm0
0x10025ced  push    esi; void *
0x10025cee  movlpd  [esp+0A8h+var_4C], xmm0
0x10025cf4  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10025cfa  mov     eax, [esp+0A8h+var_68]
0x10025cfe  call    eax
0x10025d00  push    [ebp+arg_18]
0x10025d03  xor     eax, eax
0x10025d05  mov     [ebx+4], esi
0x10025d08  push    dword ptr [esp+9Ch+var_78+4]
0x10025d0c  mov     dword ptr [ebx+930h], 0
0x10025d16  mov     edx, edi
0x10025d18  push    [esp+0A0h+var_70]
0x10025d1c  mov     [ebx+958h], ax
0x10025d23  mov     ecx, ebx
0x10025d25  push    dword ptr [esp+0A4h+var_78]
0x10025d29  mov     [ebx+938h], eax
0x10025d2f  mov     [ebx+934h], eax
0x10025d35  mov     [ebx+93Ch], eax
0x10025d3b  mov     dword ptr [ebx+940h], 0FFFFFFFFh
0x10025d45  mov     [ebx+954h], eax
0x10025d4b  call    _ErrCompactInit@24; ErrCompactInit(x,x,x,x,x,x)
0x10025d50  mov     edi, eax
0x10025d52  test    edi, edi
0x10025d54  jns     short loc_10025D62
0x10025d56  mov     eax, [ebx+18h]
0x10025d59  mov     [esp+98h+var_5C], eax
0x10025d5d  jmp     loc_100265F1
0x10025d62  mov     ecx, [ebx+10h]
0x10025d65  mov     edx, _rgtib
0x10025d6b  mov     edi, [esp+98h+var_80]
0x10025d6f  cmp     ecx, 30000h
0x10025d75  jb      short loc_10025D9E
0x10025d77  cmp     dword ptr [ebx+14h], 30000h
0x10025d7e  jb      short loc_10025D9E
0x10025d80  imul    eax, dword_1016EAA4[edi], 90Ch
0x10025d8a  cmp     dword ptr [eax+edx+8ECh], 0
0x10025d92  jz      short loc_10025D9E
0x10025d94  mov     dword ptr [ebx+930h], 1
0x10025d9e  cmp     ecx, 40000h
0x10025da4  jnb     short loc_10025DCD
0x10025da6  cmp     dword ptr [ebx+14h], 40000h
0x10025dad  jb      short loc_10025DCD
0x10025daf  imul    eax, dword_1016EAA4[edi], 90Ch
0x10025db9  cmp     dword ptr [eax+edx+900h], 0
0x10025dc1  jz      short loc_10025DCD
0x10025dc3  mov     dword ptr [ebx+938h], 1
0x10025dcd  mov     ecx, ebx
0x10025dcf  call    _ErrCreateContainers@4; ErrCreateContainers(x)
0x10025dd4  mov     edi, eax
0x10025dd6  test    edi, edi
0x10025dd8  js      loc_1002656A
0x10025dde  mov     edi, [ebx+30h]
0x10025de1  push    dword ptr [ebx+8]
0x10025de4  add     edi, edi
0x10025de6  call    _FDbidIsReplicable@4; FDbidIsReplicable(x)
0x10025deb  test    eax, eax
0x10025ded  jz      short loc_10025E60
0x10025def  cmp     dword ptr [ebx+10h], 30000h
0x10025df6  lea     eax, [edi+6]
0x10025df9  mov     [ebx+20h], eax
0x10025dfc  jnz     short loc_10025E63
0x10025dfe  cmp     dword ptr [ebx+14h], 40000h
0x10025e05  jb      short loc_10025E63
0x10025e07  push    80000000h
0x10025e0c  push    offset _WZMSysTableGuids; "MSysTableGuids"
0x10025e11  lea     eax, [esp+0A0h+var_78]
0x10025e15  push    eax
0x10025e16  push    dword ptr [ebx+8]
0x10025e19  push    esi
0x10025e1a  call    _ErrDispOpenTable@20; ErrDispOpenTable(x,x,x,x,x)
0x10025e1f  mov     edi, eax
0x10025e21  test    edi, edi
0x10025e23  js      loc_1002656A
0x10025e29  push    0
0x10025e2b  push    28h ; '('
0x10025e2d  lea     eax, [esp+0A0h+var_2C]
0x10025e31  push    eax
0x10025e32  push    dword ptr [esp+0A4h+var_78]
0x10025e36  push    esi
0x10025e37  call    _ErrDispGetTableInfo@20; ErrDispGetTableInfo(x,x,x,x,x)
0x10025e3c  mov     edi, eax
0x10025e3e  test    edi, edi
0x10025e40  js      loc_1002656A
0x10025e46  push    dword ptr [esp+98h+var_78]
0x10025e4a  mov     eax, [esp+9Ch+var_C]
0x10025e51  add     [ebx+20h], eax
0x10025e54  push    esi
0x10025e55  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x10025e5a  add     dword ptr [ebx+20h], 5
0x10025e5e  jmp     short loc_10025E63
0x10025e60  mov     [ebx+20h], edi
0x10025e63  mov     ecx, ebx
0x10025e65  mov     dword ptr [ebx+24h], 0
0x10025e6c  call    _ErrCopyObjects@4; ErrCopyObjects(x)
0x10025e71  mov     edi, eax
0x10025e73  test    edi, edi
0x10025e75  js      loc_1002656A
0x10025e7b  test    [ebp+arg_18], 100h
0x10025e82  jnz     short loc_10025E95
0x10025e84  mov     ecx, ebx
0x10025e86  call    _ErrCopyRelationships@4; ErrCopyRelationships(x)
0x10025e8b  mov     edi, eax
0x10025e8d  test    edi, edi
0x10025e8f  js      loc_1002656A
0x10025e95  mov     ecx, ebx
0x10025e97  call    _ErrCopyACLs@4; ErrCopyACLs(x)
0x10025e9c  mov     edi, eax
0x10025e9e  test    edi, edi
0x10025ea0  js      loc_1002656A
0x10025ea6  mov     ecx, ebx
0x10025ea8  call    _ErrReportProgress@4; ErrReportProgress(x)
0x10025ead  mov     edi, eax
0x10025eaf  test    edi, edi
0x10025eb1  js      loc_1002656A
0x10025eb7  mov     ecx, ebx
0x10025eb9  call    _ErrConvert3xTo40@4; ErrConvert3xTo40(x)
0x10025ebe  mov     edi, eax
0x10025ec0  test    edi, edi
0x10025ec2  js      loc_1002656A
0x10025ec8  push    dword ptr [ebx+8]
0x10025ecb  call    _FDbidIsReplicable@4; FDbidIsReplicable(x)
0x10025ed0  test    eax, eax
0x10025ed2  jz      loc_100264F0
0x10025ed8  mov     eax, [ebx+10h]
0x10025edb  mov     [esp+98h+var_80], 0FFFFFFFFh
0x10025ee3  mov     dword ptr [esp+98h+var_78], 0
0x10025eeb  mov     [esp+98h+var_84], 0FFFFFFFFh
0x10025ef3  cmp     eax, 30000h
0x10025ef8  jnz     short loc_10025F0D
0x10025efa  cmp     dword ptr [ebx+14h], 40000h
0x10025f01  sbb     eax, eax
0x10025f03  inc     eax
0x10025f04  mov     dword ptr [esp+98h+var_78], eax
0x10025f08  jmp     loc_10026250
0x10025f0d  cmp     eax, 40000h
0x10025f12  jnz     loc_10026250
0x10025f18  cmp     [ebx+14h], eax
0x10025f1b  jnz     loc_10026250
0x10025f21  push    2
0x10025f23  push    offset _WZMSysTranspAddress; "MSysTranspAddress"
0x10025f28  lea     eax, [esp+0A0h+var_84]
0x10025f2c  push    eax
0x10025f2d  push    dword ptr [ebx+0Ch]
0x10025f30  push    dword ptr [ebx+4]
0x10025f33  call    _ErrDispOpenTable@20; ErrDispOpenTable(x,x,x,x,x)
0x10025f38  mov     edi, eax
0x10025f3a  test    edi, edi
0x10025f3c  js      loc_10026236
0x10025f42  push    offset _WZInternetAddress; "InternetAddress"
0x10025f47  push    offset _WZHTTPAddress; "HTTPAddress"
0x10025f4c  push    [esp+0A0h+var_84]
0x10025f50  push    dword ptr [ebx+4]
0x10025f53  call    _ErrDispRenameColumn@16; ErrDispRenameColumn(x,x,x,x)
0x10025f58  test    eax, eax
0x10025f5a  jns     short loc_10025F71
0x10025f5c  cmp     eax, 0FFFFFA1Dh
0x10025f61  jz      short loc_10025F6A
0x10025f63  cmp     eax, 0FFFFFA1Ch
0x10025f68  jnz     short loc_10025F71
0x10025f6a  xor     edi, edi
0x10025f6c  jmp     loc_10026236
0x10025f71  push    offset _WZHttpScriptsFolder; "HttpScriptsFolder"
0x10025f76  push    offset _WZFTPAddress; "FTPAddress"
0x10025f7b  push    [esp+0A0h+var_84]
  ... truncated ...
```
