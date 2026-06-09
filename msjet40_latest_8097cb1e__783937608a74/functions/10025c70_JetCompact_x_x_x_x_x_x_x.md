# JetCompact(x,x,x,x,x,x,x)

- ea: `0x10025c70`
- end: `0x100268a5`
- name: `_JetCompact@28`
- size: `3125`
- prototype: `int __stdcall(void *, int, int, int, int, int, int)`
- caller_count: `0`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x10017150`
- `0x1001ec50`
- `0x1001ecc0`
- `0x1001f5e0`
- `0x10023270`
- `0x10023f10`
- `0x100240c0`
- `0x10024a80`
- `0x10024d40`
- `0x10025240`
- `0x10025320`
- `0x10025390`
- `0x10025400`
- `0x10025c70`
- `0x1002d380`
- `0x1002ed50`
- `0x1003e9b0`
- `0x10042b60`
- `0x10043220`
- `0x10043890`
- `0x10043960`
- `0x100439d0`
- `0x10044240`
- `0x100443d0`
- `0x10044920`
- `0x1004650c`
- `0x10050190`
- `0x10117310`
- `0x10123110`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100267a3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100267a3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x10025dd7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x10025dd7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1002677a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1002677a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10025cfc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10025d34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10025d68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100267f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10026835`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1002685e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10026883`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10025cfc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10025d34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10025d68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100267f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10026835`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1002685e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10026883`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10025ccc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10025ccc`

## string_xrefs

- `0x100260f6`: `FTPDirectory`

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
  int v22; // edx
  Session *v23; // ecx
  Session *v24; // ecx
  int v25; // edx
  Session *v26; // ecx
  int v27; // edx
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
  int v39; // [esp+48h] [ebp-A8h]
  int v40; // [esp+48h] [ebp-A8h]
  unsigned int v41; // [esp+4Ch] [ebp-A4h]
  int v42; // [esp+50h] [ebp-A0h]
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
    v7 = dword_1016EB88[26 * v7];
    if ( v7 == -1 )
      goto LABEL_5;
  }
  v47 = 104 * v7;
  if ( dword_1016EB8C[26 * v7] )
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
    v42 = v50;
    v10[588] = 0;
    v41 = v51;
    *((_WORD *)v10 + 1196) = 0;
    v39 = v49;
    v10[590] = 0;
    v10[589] = 0;
    v10[591] = 0;
    v10[592] = -1;
    v10[597] = 0;
    Containers = ErrCompactInit(v39, v41, v42, a7);
    if ( Containers < 0 )
    {
      v56 = v10[6];
      goto LABEL_137;
    }
    v13 = v10[4];
    v14 = rgtib;
    v15 = v47;
    if ( v13 >= 0x30000 && v10[5] >= 0x30000u && *((_DWORD *)rgtib + 579 * *(int *)((char *)dword_1016EB44 + v47) + 571) )
      v10[588] = 1;
    if ( v13 < 0x40000 && v10[5] >= 0x40000u && v14[579 * *(int *)((char *)dword_1016EB44 + v15) + 576] )
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
                        Containers = ErrDispAddColumn(v10[1], v46, L"HTTPEnable", v62, 0, 0, &v57);
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
                                Containers = (*(int (__thiscall **)(_DWORD, int, int, int, char *, int, int *, _DWORD, _DWORD))(dword_101636CC[4 * v46] + 140))(
                                               *(_DWORD *)(dword_101636CC[4 * v46] + 140),
                                               v20,
                                               dword_101636C4[4 * v46],
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
                                Containers = (*(int (__thiscall **)(_DWORD, Session *, int, int))(dword_101636CC[4 * v46]
                                                                                                + 124))(
                                               *(_DWORD *)(dword_101636CC[4 * v46] + 124),
                                               v21,
                                               dword_101636C4[4 * v46],
                                               2);
                                if ( Containers < 0 )
                                  goto LABEL_90;
                                if ( v46 >= 0x800 || v46 < tableidInit )
                                  goto LABEL_89;
                                v23 = a1;
                                if ( rgvtdef[4 * v46] != -1 )
                                  v23 = (Session *)rgvtdef[4 * v46];
                                Containers = (*(int (__thiscall **)(_DWORD, Session *, int, int, char *, int, _DWORD, _DWORD))(dword_101636CC[4 * v46] + 156))(
                                               *(_DWORD *)(dword_101636CC[4 * v46] + 156),
                                               v23,
                                               dword_101636C4[4 * v46],
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
                                Containers = (*(int (__thiscall **)(_DWORD, Session *, int, _DWORD, _DWORD, _DWORD))(dword_101636CC[4 * v46] + 164))(
                                               *(_DWORD *)(dword_101636CC[4 * v46] + 164),
                                               v24,
                                               dword_101636C4[4 * v46],
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
                                v28 = (*(int (__thiscall **)(_DWORD, Session *, int, int, _DWORD))(dword_101636CC[4 * v46]
                                                                                                 + 104))(
                                        *(_DWORD *)(dword_101636CC[4 * v46] + 104),
                                        v26,
                                        dword_101636C4[4 * v46],
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
                    v34 = (*(int (__thiscall **)(_DWORD, int, int, const wchar_t *, _DWORD *, _DWORD, _DWORD, int *))(dword_101636CC[4 * v45] + 8))(
                            *(_DWORD *)(dword_101636CC[4 * v45] + 8),
                            v33,
                            dword_101636C4[4 * v45],
                            L"WinningReplicaId",
                            v61,
                            0,
                            0,
                            &v52);
                    if ( v34 >= 0 || v34 == -1508 )
                      ErrDispAddColumn(v30, v45, L"LosingReplicaId", v61, 0, 0, &v52);
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
0x10025c70  mov     edi, edi
0x10025c72  push    ebp
0x10025c73  mov     ebp, esp
0x10025c75  and     esp, 0FFFFFFF8h
0x10025c78  sub     esp, 8Ch
0x10025c7e  mov     eax, ___security_cookie
0x10025c83  xor     eax, esp
0x10025c85  mov     [esp+8Ch+var_4], eax
0x10025c8c  mov     eax, [ebp+arg_8]
0x10025c8f  push    ebx
0x10025c90  mov     ebx, [ebp+arg_C]
0x10025c93  push    esi
0x10025c94  push    edi
0x10025c95  push    _critJet; lpCriticalSection
0x10025c9b  mov     edi, [ebp+arg_4]
0x10025c9e  mov     dword ptr [esp+9Ch+var_78], eax
0x10025ca2  mov     eax, [ebp+arg_10]
0x10025ca5  mov     dword ptr [esp+9Ch+var_78+4], eax
0x10025ca9  mov     eax, [ebp+arg_14]
0x10025cac  mov     [esp+9Ch+var_70], ebx
0x10025cb0  mov     [esp+9Ch+var_68], eax
0x10025cb4  mov     [esp+9Ch+var_5C], 0
0x10025cbc  mov     [esp+9Ch+var_60], 0
0x10025cc4  mov     [esp+9Ch+var_64], 0
0x10025ccc  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10025cd2  mov     eax, _isibHead
0x10025cd7  cmp     eax, 0FFFFFFFFh
0x10025cda  jz      short loc_10025CF6
0x10025cdc  mov     esi, [ebp+arg_0]
0x10025cdf  nop
0x10025ce0  imul    ecx, eax, 68h ; 'h'
0x10025ce3  cmp     _rgsib[ecx], esi
0x10025ce9  jz      short loc_10025D1E
0x10025ceb  mov     eax, dword_1016EB88[ecx]
0x10025cf1  cmp     eax, 0FFFFFFFFh
0x10025cf4  jnz     short loc_10025CE0
0x10025cf6  push    _critJet; lpCriticalSection
0x10025cfc  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10025d02  mov     eax, 0FFFFFBB0h
0x10025d07  pop     edi
0x10025d08  pop     esi
0x10025d09  pop     ebx
0x10025d0a  mov     ecx, [esp+8Ch+var_4]
0x10025d11  xor     ecx, esp; StackCookie
0x10025d13  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10025d18  mov     esp, ebp
0x10025d1a  pop     ebp
0x10025d1b  retn    1Ch
0x10025d1e  imul    eax, 68h ; 'h'
0x10025d21  mov     [esp+98h+var_80], eax
0x10025d25  cmp     dword_1016EB8C[eax], 0
0x10025d2c  jbe     short loc_10025D56
0x10025d2e  push    _critJet; lpCriticalSection
0x10025d34  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10025d3a  mov     eax, 0FFFFFBACh
0x10025d3f  pop     edi
0x10025d40  pop     esi
0x10025d41  pop     ebx
0x10025d42  mov     ecx, [esp+8Ch+var_4]
0x10025d49  xor     ecx, esp; StackCookie
0x10025d4b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10025d50  mov     esp, ebp
0x10025d52  pop     ebp
0x10025d53  retn    1Ch
0x10025d56  mov     ecx, [ebp+arg_18]
0x10025d59  mov     eax, ecx
0x10025d5b  and     eax, 3
0x10025d5e  cmp     al, 3
0x10025d60  jnz     short loc_10025D8A
0x10025d62  push    _critJet; lpCriticalSection
0x10025d68  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10025d6e  mov     eax, 0FFFFFC15h
0x10025d73  pop     edi
0x10025d74  pop     esi
0x10025d75  pop     ebx
0x10025d76  mov     ecx, [esp+8Ch+var_4]
0x10025d7d  xor     ecx, esp; StackCookie
0x10025d7f  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10025d84  mov     esp, ebp
0x10025d86  pop     ebp
0x10025d87  retn    1Ch
0x10025d8a  test    ecx, 0FFFFEC80h
0x10025d90  jnz     short loc_10025D62
0x10025d92  mov     ecx, edi
0x10025d94  lea     edx, [ecx+2]
0x10025d97  mov     ax, [ecx]
0x10025d9a  add     ecx, 2
0x10025d9d  test    ax, ax
0x10025da0  jnz     short loc_10025D97
0x10025da2  sub     ecx, edx
0x10025da4  sar     ecx, 1
0x10025da6  cmp     ecx, 104h
0x10025dac  jnb     loc_1002687D
0x10025db2  mov     ecx, ebx
0x10025db4  lea     edx, [ecx+2]
0x10025db7  mov     ax, [ecx]
0x10025dba  add     ecx, 2
0x10025dbd  test    ax, ax
0x10025dc0  jnz     short loc_10025DB7
0x10025dc2  sub     ecx, edx
0x10025dc4  sar     ecx, 1
0x10025dc6  cmp     ecx, 104h
0x10025dcc  jnb     loc_1002687D
0x10025dd2  push    88DCh; Size
0x10025dd7  call    ds:__imp__malloc
0x10025ddd  mov     ebx, eax
0x10025ddf  add     esp, 4
0x10025de2  test    ebx, ebx
0x10025de4  jnz     short loc_10025E02
0x10025de6  mov     eax, 0FFFFFC0Dh
0x10025deb  pop     edi
0x10025dec  pop     esi
0x10025ded  pop     ebx
0x10025dee  mov     ecx, [esp+8Ch+var_4]
0x10025df5  xor     ecx, esp; StackCookie
0x10025df7  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10025dfc  mov     esp, ebp
0x10025dfe  pop     ebp
0x10025dff  retn    1Ch
0x10025e02  mov     eax, [ebp+arg_18]
0x10025e05  mov     ecx, [esp+98h+var_68]
0x10025e09  shr     eax, 2
0x10025e0c  and     eax, 1
0x10025e0f  mov     [ebx], ecx
0x10025e11  mov     [ebx+910h], eax
0x10025e17  mov     dword ptr [ebx+914h], 0
0x10025e21  mov     dword ptr [ebx+918h], 0
0x10025e2b  mov     dword ptr [ebx+91Ch], 0
0x10025e35  test    ecx, ecx
0x10025e37  jz      short loc_10025E60
0x10025e39  lea     eax, [esp+98h+var_50]
0x10025e3d  mov     [esp+98h+var_50], 0Ch
0x10025e45  push    eax
0x10025e46  push    5
0x10025e48  push    4; unsigned int
0x10025e4a  xorps   xmm0, xmm0
0x10025e4d  push    esi; void *
0x10025e4e  movlpd  [esp+0A8h+var_4C], xmm0
0x10025e54  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10025e5a  mov     eax, [esp+0A8h+var_68]
0x10025e5e  call    eax
0x10025e60  push    [ebp+arg_18]
0x10025e63  xor     eax, eax
0x10025e65  mov     [ebx+4], esi
0x10025e68  push    dword ptr [esp+9Ch+var_78+4]
0x10025e6c  mov     dword ptr [ebx+930h], 0
0x10025e76  mov     edx, edi
0x10025e78  push    [esp+0A0h+var_70]
0x10025e7c  mov     [ebx+958h], ax
0x10025e83  mov     ecx, ebx
0x10025e85  push    dword ptr [esp+0A4h+var_78]
0x10025e89  mov     [ebx+938h], eax
0x10025e8f  mov     [ebx+934h], eax
0x10025e95  mov     [ebx+93Ch], eax
0x10025e9b  mov     dword ptr [ebx+940h], 0FFFFFFFFh
0x10025ea5  mov     [ebx+954h], eax
0x10025eab  call    _ErrCompactInit@24; ErrCompactInit(x,x,x,x,x,x)
0x10025eb0  mov     edi, eax
0x10025eb2  test    edi, edi
0x10025eb4  jns     short loc_10025EC2
0x10025eb6  mov     eax, [ebx+18h]
0x10025eb9  mov     [esp+98h+var_5C], eax
0x10025ebd  jmp     loc_10026751
0x10025ec2  mov     ecx, [ebx+10h]
0x10025ec5  mov     edx, _rgtib
0x10025ecb  mov     edi, [esp+98h+var_80]
0x10025ecf  cmp     ecx, 30000h
0x10025ed5  jb      short loc_10025EFE
0x10025ed7  cmp     dword ptr [ebx+14h], 30000h
0x10025ede  jb      short loc_10025EFE
0x10025ee0  imul    eax, dword_1016EB44[edi], 90Ch
0x10025eea  cmp     dword ptr [eax+edx+8ECh], 0
0x10025ef2  jz      short loc_10025EFE
0x10025ef4  mov     dword ptr [ebx+930h], 1
0x10025efe  cmp     ecx, 40000h
0x10025f04  jnb     short loc_10025F2D
0x10025f06  cmp     dword ptr [ebx+14h], 40000h
0x10025f0d  jb      short loc_10025F2D
0x10025f0f  imul    eax, dword_1016EB44[edi], 90Ch
0x10025f19  cmp     dword ptr [eax+edx+900h], 0
0x10025f21  jz      short loc_10025F2D
0x10025f23  mov     dword ptr [ebx+938h], 1
0x10025f2d  mov     ecx, ebx
0x10025f2f  call    _ErrCreateContainers@4; ErrCreateContainers(x)
0x10025f34  mov     edi, eax
0x10025f36  test    edi, edi
0x10025f38  js      loc_100266CA
0x10025f3e  mov     edi, [ebx+30h]
0x10025f41  push    dword ptr [ebx+8]
0x10025f44  add     edi, edi
0x10025f46  call    _FDbidIsReplicable@4; FDbidIsReplicable(x)
0x10025f4b  test    eax, eax
0x10025f4d  jz      short loc_10025FC0
0x10025f4f  cmp     dword ptr [ebx+10h], 30000h
0x10025f56  lea     eax, [edi+6]
0x10025f59  mov     [ebx+20h], eax
0x10025f5c  jnz     short loc_10025FC3
0x10025f5e  cmp     dword ptr [ebx+14h], 40000h
0x10025f65  jb      short loc_10025FC3
0x10025f67  push    80000000h
0x10025f6c  push    offset _WZMSysTableGuids; "MSysTableGuids"
0x10025f71  lea     eax, [esp+0A0h+var_78]
0x10025f75  push    eax
0x10025f76  push    dword ptr [ebx+8]
0x10025f79  push    esi
0x10025f7a  call    _ErrDispOpenTable@20; ErrDispOpenTable(x,x,x,x,x)
0x10025f7f  mov     edi, eax
0x10025f81  test    edi, edi
0x10025f83  js      loc_100266CA
0x10025f89  push    0
0x10025f8b  push    28h ; '('
0x10025f8d  lea     eax, [esp+0A0h+var_2C]
0x10025f91  push    eax
0x10025f92  push    dword ptr [esp+0A4h+var_78]
0x10025f96  push    esi
0x10025f97  call    _ErrDispGetTableInfo@20; ErrDispGetTableInfo(x,x,x,x,x)
0x10025f9c  mov     edi, eax
0x10025f9e  test    edi, edi
0x10025fa0  js      loc_100266CA
0x10025fa6  push    dword ptr [esp+98h+var_78]
0x10025faa  mov     eax, [esp+9Ch+var_C]
0x10025fb1  add     [ebx+20h], eax
0x10025fb4  push    esi
0x10025fb5  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x10025fba  add     dword ptr [ebx+20h], 5
0x10025fbe  jmp     short loc_10025FC3
0x10025fc0  mov     [ebx+20h], edi
0x10025fc3  mov     ecx, ebx
0x10025fc5  mov     dword ptr [ebx+24h], 0
0x10025fcc  call    _ErrCopyObjects@4; ErrCopyObjects(x)
0x10025fd1  mov     edi, eax
0x10025fd3  test    edi, edi
0x10025fd5  js      loc_100266CA
0x10025fdb  test    [ebp+arg_18], 100h
0x10025fe2  jnz     short loc_10025FF5
0x10025fe4  mov     ecx, ebx
0x10025fe6  call    _ErrCopyRelationships@4; ErrCopyRelationships(x)
0x10025feb  mov     edi, eax
0x10025fed  test    edi, edi
0x10025fef  js      loc_100266CA
0x10025ff5  mov     ecx, ebx
0x10025ff7  call    _ErrCopyACLs@4; ErrCopyACLs(x)
0x10025ffc  mov     edi, eax
0x10025ffe  test    edi, edi
0x10026000  js      loc_100266CA
0x10026006  mov     ecx, ebx
0x10026008  call    _ErrReportProgress@4; ErrReportProgress(x)
0x1002600d  mov     edi, eax
0x1002600f  test    edi, edi
0x10026011  js      loc_100266CA
0x10026017  mov     ecx, ebx
0x10026019  call    _ErrConvert3xTo40@4; ErrConvert3xTo40(x)
0x1002601e  mov     edi, eax
0x10026020  test    edi, edi
0x10026022  js      loc_100266CA
0x10026028  push    dword ptr [ebx+8]
0x1002602b  call    _FDbidIsReplicable@4; FDbidIsReplicable(x)
0x10026030  test    eax, eax
0x10026032  jz      loc_10026650
0x10026038  mov     eax, [ebx+10h]
0x1002603b  mov     [esp+98h+var_80], 0FFFFFFFFh
0x10026043  mov     dword ptr [esp+98h+var_78], 0
0x1002604b  mov     [esp+98h+var_84], 0FFFFFFFFh
0x10026053  cmp     eax, 30000h
0x10026058  jnz     short loc_1002606D
0x1002605a  cmp     dword ptr [ebx+14h], 40000h
0x10026061  sbb     eax, eax
0x10026063  inc     eax
0x10026064  mov     dword ptr [esp+98h+var_78], eax
0x10026068  jmp     loc_100263B0
0x1002606d  cmp     eax, 40000h
0x10026072  jnz     loc_100263B0
0x10026078  cmp     [ebx+14h], eax
0x1002607b  jnz     loc_100263B0
0x10026081  push    2
0x10026083  push    offset _WZMSysTranspAddress; "MSysTranspAddress"
0x10026088  lea     eax, [esp+0A0h+var_84]
0x1002608c  push    eax
0x1002608d  push    dword ptr [ebx+0Ch]
0x10026090  push    dword ptr [ebx+4]
0x10026093  call    _ErrDispOpenTable@20; ErrDispOpenTable(x,x,x,x,x)
0x10026098  mov     edi, eax
0x1002609a  test    edi, edi
0x1002609c  js      loc_10026396
0x100260a2  push    offset _WZInternetAddress; "InternetAddress"
0x100260a7  push    offset _WZHTTPAddress; "HTTPAddress"
0x100260ac  push    [esp+0A0h+var_84]
0x100260b0  push    dword ptr [ebx+4]
0x100260b3  call    _ErrDispRenameColumn@16; ErrDispRenameColumn(x,x,x,x)
0x100260b8  test    eax, eax
0x100260ba  jns     short loc_100260D1
0x100260bc  cmp     eax, 0FFFFFA1Dh
0x100260c1  jz      short loc_100260CA
0x100260c3  cmp     eax, 0FFFFFA1Ch
0x100260c8  jnz     short loc_100260D1
0x100260ca  xor     edi, edi
0x100260cc  jmp     loc_10026396
0x100260d1  push    offset _WZHttpScriptsFolder; "HttpScriptsFolder"
0x100260d6  push    offset _WZFTPAddress; "FTPAddress"
0x100260db  push    [esp+0A0h+var_84]
  ... truncated ...
```
