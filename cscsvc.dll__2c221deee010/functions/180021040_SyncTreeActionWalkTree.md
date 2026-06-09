# SyncTreeActionWalkTree

- ea: `0x180021040`
- end: `0x180021dc6`
- name: `SyncTreeActionWalkTree`
- size: `3462`
- prototype: ``
- caller_count: `6`
- callee_count: `18`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180078e00`
- `0x1800798e0`
- `0x180079af0`
- `0x18007a140`
- `0x18007a540`
- `0x18007a8d0`

## callees

- `0x180004c40`
- `0x1800134c0`
- `0x180020ef0`
- `0x180021040`
- `0x180021dcc`
- `0x180032700`
- `0x180035f80`
- `0x1800360c0`
- `0x180036394`
- `0x18003c460`
- `0x18003c488`
- `0x180044554`
- `0x18007479c`
- `0x18007e734`
- `0x18007e930`
- `0x18007efc8`
- `0x18007f4b4`
- `0x180089010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180021663`
- `ntdll!RtlNtStatusToDosError` at `0x180021bd0`
- `ntdll!RtlNtStatusToDosError` at `0x180021663`
- `ntdll!RtlNtStatusToDosError` at `0x180021bd0`

## string_xrefs

- `0x1800210b2`: `SyncTreeActionWalkTree: OpArgs: 0x%p DesiredAccess: 0x%x Pre/Post/File: %d/%d/%d CC: 0x%p Flags: 0x%08x`
- `0x1800215b0`: `SyncTreeActionWalkTree: DirCreateCallback failed on the root with %x for %ws`
- `0x180021d19`: `SyncTreeActionWalkTree: SyncTreeActionCreateAndInitializeContext failed with %x ... Aborting Tree Action.`
- `0x1800218fc`: `Marking context for delete [%ws]`
- `0x180021b1d`: `SyncTreeActionWalkTree: DirCreateCallback failed with %x for %ws`

## pseudocode

```c
__int64 __fastcall SyncTreeActionWalkTree(_QWORD **a1)
{
  char *v2; // r15
  __int64 v3; // rdx
  __int64 v4; // r8
  int v5; // r12d
  __int64 v6; // rax
  __int64 v7; // r13
  unsigned int v8; // edi
  __int64 v9; // r9
  __int64 v10; // r8
  char *v11; // rdx
  _DWORD *v12; // rcx
  _QWORD *v13; // rdx
  unsigned int v14; // ebx
  CObjectMonitor *v15; // rcx
  __int64 v16; // rdx
  __int64 *v17; // rdx
  _QWORD *v18; // rdx
  unsigned int v19; // ebx
  CObjectMonitor *v20; // rcx
  __int64 v21; // rdx
  unsigned int v22; // eax
  int v23; // r12d
  CObjectMonitor *v24; // rcx
  unsigned __int64 v25; // rax
  __int64 v26; // r8
  __int64 v27; // rbx
  unsigned int v28; // eax
  unsigned int v29; // ebx
  int v30; // ecx
  unsigned int **v31; // r12
  __int64 v32; // rdx
  int v33; // ebx
  void *v34; // rcx
  char *v35; // rbx
  unsigned int Directory; // eax
  bool v37; // zf
  _DWORD *v38; // rcx
  __int64 *v39; // rdx
  unsigned int v40; // eax
  unsigned int v41; // ebx
  CObjectMonitor *v42; // rcx
  void *v43; // rcx
  int v44; // ebx
  __int64 v45; // r8
  unsigned int v46; // ebx
  unsigned int v47; // eax
  NTSTATUS v48; // edi
  int v49; // r12d
  CObjectMonitor *v50; // rcx
  unsigned __int64 v51; // rax
  __int64 v52; // r8
  __int64 v53; // rbx
  void *v54; // rbx
  __int128 v56; // [rsp+50h] [rbp-28h] BYREF
  __int64 v57; // [rsp+60h] [rbp-18h]
  int v58; // [rsp+C0h] [rbp+48h] BYREF
  int v59; // [rsp+C8h] [rbp+50h]
  LPVOID v60; // [rsp+D0h] [rbp+58h] BYREF
  LPVOID lpAddress; // [rsp+D8h] [rbp+60h] BYREF

  v60 = 0;
  v57 = 0;
  v2 = 0;
  lpAddress = 0;
  v56 = 0;
  v58 = 0;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
  {
    SyncTraceOutputInternal(
      L"SyncTreeActionWalkTree: OpArgs: 0x%p DesiredAccess: 0x%x Pre/Post/File: %d/%d/%d CC: 0x%p Flags: 0x%08x",
      *a1,
      *((unsigned int *)a1 + 2),
      *((unsigned int *)a1 + 3),
      *((_DWORD *)a1 + 4),
      *((_DWORD *)a1 + 5),
      a1[4],
      *((_DWORD *)a1 + 12));
    WPP_SF_qDdddqD(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      v3,
      v4,
      *a1,
      *((_DWORD *)a1 + 2),
      *((_DWORD *)a1 + 3),
      *((_DWORD *)a1 + 4),
      *((_DWORD *)a1 + 5),
      a1[4],
      *((_DWORD *)a1 + 12),
      v56,
      *((_QWORD *)&v56 + 1),
      v57);
  }
  v5 = *((_DWORD *)a1 + 12);
  v6 = SyncAlloc(248);
  v7 = v6;
  if ( !v6 )
  {
    v8 = -1073741670;
    goto LABEL_13;
  }
  v9 = -1;
  *(_QWORD *)v6 = **a1;
  *(_QWORD *)(v6 + 24) = (*a1)[3];
  *(_DWORD *)(v6 + 32) = *((_DWORD *)*a1 + 8);
  *(_QWORD *)(v6 + 64) = (*a1)[8];
  *(_QWORD *)(v6 + 72) = (*a1)[9];
  *(_QWORD *)(v6 + 88) = (*a1)[11];
  *(_QWORD *)(v6 + 80) = (*a1)[10];
  *(_QWORD *)(v6 + 96) = (*a1)[12];
  v10 = (*a1)[1];
  do
    ++v9;
  while ( *(_WORD *)(v10 + 2 * v9) );
  v8 = SyncTreeActionNewContext(&v60, 0, v10, (unsigned int)(2 * v9 + 2));
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(L"SyncTreeActionWalkTree: SyncTreeActionNewContext failed with %x", v8);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 29, WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids, v8);
    }
    goto LABEL_12;
  }
  *((_QWORD *)v60 + 1) = 0;
  *((_QWORD *)v60 + 2) = (*a1)[2];
  *((_DWORD *)v60 + 11) = 1;
  v12 = (char *)v60 + 48;
  *((_QWORD *)v60 + 4) = (char *)v60 + 48;
  *v12 = 0;
  v13 = *a1;
  DWORD2(v56) = 0;
  *(_QWORD *)&v56 = (char *)v60 + 8240;
  v57 = *((_QWORD *)v60 + 2);
  v14 = ((__int64 (__fastcall *)(__int128 *, _QWORD))v13[8])(&v56, v13[12]);
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    SyncTraceOutputInternal(L"SyncTreeActionWalkTree: Received %d on BEGIN for [%ws]", v14, (char *)v60 + 8240);
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      30,
      (unsigned int)WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids,
      v14,
      (__int64)v60 + 8240);
    v15 = WPP_GLOBAL_Control;
  }
  if ( v14 )
  {
    if ( v15 == (CObjectMonitor *)&WPP_GLOBAL_Control || (*((_BYTE *)v15 + 108) & 1) == 0 )
      goto LABEL_25;
    SyncTraceOutputInternal(L"SyncTreeActionWalkTree: Received abort from callback on begin ... Aborting Tree Action.");
    v16 = 31;
    goto LABEL_24;
  }
  v18 = *a1;
  DWORD2(v56) = 1;
  *(_QWORD *)&v56 = (char *)v60 + 8240;
  v19 = ((__int64 (__fastcall *)(__int128 *, _QWORD))v18[8])(&v56, v18[12]);
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    SyncTraceOutputInternal(L"SyncTreeActionWalkTree: Received %d on NEXT ITEM for [%ws]", v19, (char *)v60 + 8240);
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      32,
      (unsigned int)WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids,
      v19,
      (__int64)v60 + 8240);
    v20 = WPP_GLOBAL_Control;
  }
  if ( v19 )
  {
    if ( v20 == (CObjectMonitor *)&WPP_GLOBAL_Control || (*((_BYTE *)v20 + 108) & 1) == 0 )
      goto LABEL_25;
    SyncTraceOutputInternal(L"SyncTreeActionWalkTree: Received abort/skip from callback on next item ... Aborting Tree Action.");
    v16 = 33;
LABEL_24:
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), v16, WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids);
    goto LABEL_25;
  }
  v37 = ((_BYTE)a1[6] & 2) == 0;
  v59 = v5 & 8;
  if ( v37 )
    goto LABEL_43;
  v8 = ((__int64 (__fastcall *)(LPVOID, _QWORD, _QWORD))a1[5])(v60, *((unsigned int *)*a1 + 8), 0);
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_25;
    SyncTraceOutputInternal(L"SyncTreeActionWalkTree: DirProcessCallback failed with %x", v8);
    v21 = 34;
LABEL_63:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), v21, WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids, v8);
    goto LABEL_25;
  }
  do
  {
    SyncTreeActionCallItemHandler(v7, *((unsigned int *)a1 + 3), v60);
    if ( !*(_DWORD *)(*(_QWORD *)(v7 + 16) + 4LL) )
      break;
    v8 = SyncTreeActionSendCompletionAndCommitNode(
           (_DWORD)a1,
           *(_DWORD *)(v7 + 104),
           *((_DWORD *)a1 + 5),
           (_DWORD)v60,
           1,
           (__int64)&v58);
    if ( v8 )
      goto LABEL_25;
  }
  while ( v58 );
LABEL_43:
  while ( 1 )
  {
    v22 = ((__int64 (__fastcall *)(char *, _QWORD, _QWORD, __int64))a1[4])(
            (char *)v60 + 8,
            (*a1)[1],
            *((_DWORD *)a1 + 2) | 0x81u,
            1);
    v8 = v22;
    if ( !v22 )
      break;
    v23 = 4096;
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(
        L"SyncTreeActionWalkTree: DirCreateCallback failed on the root with %x for %ws",
        v22,
        (char *)v60 + 8240);
      WPP_SF_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        35,
        (unsigned int)WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids,
        v8,
        (__int64)v60 + 8240);
      v24 = WPP_GLOBAL_Control;
    }
    if ( v59 )
    {
      v25 = v8 + 1073741809;
      if ( (unsigned int)v25 <= 0x2B )
      {
        v26 = 0x82000000001LL;
        if ( _bittest64(&v26, v25) )
        {
          if ( v24 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v24 + 108) & 1) != 0 )
          {
            SyncTraceOutputInternal(L"Ignoring \"not found\" status");
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 36, WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids);
          }
          v8 = 0;
          v23 = 0;
        }
      }
    }
    v27 = *((_QWORD *)v60 + 2);
    *(_DWORD *)(v27 + 4) = RtlNtStatusToDosError(v8);
    v28 = SyncTreeActionSendCompletionAndCommitNode((_DWORD)a1, v23, *((_DWORD *)a1 + 5), (_DWORD)v60, 1, (__int64)&v58);
    if ( v28 )
    {
      v8 = v28;
      goto LABEL_25;
    }
    v29 = v8;
    if ( !v58 )
    {
      if ( ((_BYTE)a1[6] & 1) == 0 )
        goto LABEL_25;
      v8 = ((__int64 (__fastcall *)(LPVOID, _QWORD, __int64))a1[5])(v60, *((unsigned int *)*a1 + 8), 1);
      if ( !v8 )
      {
        v8 = v29;
        goto LABEL_25;
      }
      if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_25;
      }
      SyncTraceOutputInternal(L"SyncTreeActionWalkTree: DirProcessCallback failed with %x", v8);
      v21 = 37;
      goto LABEL_63;
    }
    SyncTreeActionCloseDirectory(v60);
  }
  v2 = (char *)v60;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
LABEL_66:
        v30 = *((_DWORD *)v2 + 11);
        v31 = (unsigned int **)(v2 + 32);
        if ( (v30 & 2) != 0 && !**v31 )
        {
          if ( ((_BYTE)a1[6] & 1) != 0
            && (v8 = ((__int64 (__fastcall *)(char *, _QWORD, __int64))a1[5])(v2, *((unsigned int *)*a1 + 8), 1)) != 0 )
          {
            if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
            {
              SyncTraceOutputInternal(L"SyncTreeActionWalkTree: DirProcessCallback failed with %x", v8);
              v21 = 38;
              goto LABEL_63;
            }
          }
          else
          {
            SyncTreeActionCloseDirectory(v2);
            while ( 1 )
            {
              if ( ((_BYTE)a1[6] & 1) != 0 )
              {
                v32 = 7;
                v33 = *(_DWORD *)(v7 + 32);
                if ( (v2[44] & 8) == 0 )
                  v32 = *((unsigned int *)a1 + 4);
                *(_DWORD *)(v7 + 32) = *((_DWORD *)a1 + 6) | v33;
                SyncTreeActionCallItemHandler(v7, v32, v2);
                *(_DWORD *)(v7 + 32) = v33;
              }
              v8 = SyncTreeActionSendCompletionAndCommitNode(
                     (_DWORD)a1,
                     *(_DWORD *)(v7 + 104),
                     *((_DWORD *)a1 + 5),
                     (_DWORD)v2,
                     0,
                     (__int64)&v58);
              if ( v8 )
                break;
              if ( !v58 )
              {
                v8 = 0;
                if ( v2 == v60 )
                  goto LABEL_25;
                v34 = v2;
                v2 = *(char **)v2;
                SyncTreeActionFreeContext(v34);
                goto LABEL_66;
              }
            }
          }
          goto LABEL_25;
        }
        if ( **v31 )
          break;
        v35 = v2 + 48;
        Directory = SyncQueryDirectory(
                      *((HANDLE *)v2 + 1),
                      0,
                      v2 + 48,
                      0x2000u,
                      FileFullDirectoryInformation,
                      0,
                      0,
                      v30 & 1,
                      1);
        *((_DWORD *)v2 + 11) &= ~1u;
        v8 = Directory;
        if ( !Directory )
          goto LABEL_84;
        if ( Directory != -2147483642 )
          goto LABEL_25;
        *((_DWORD *)v2 + 11) |= 2u;
      }
      v35 = (char *)*v31 + **v31;
LABEL_84:
      *v31 = (unsigned int *)v35;
      if ( *((_DWORD *)v35 + 15) != 2 )
        break;
      v37 = *((_WORD *)v35 + 34) == 46;
LABEL_89:
      if ( !v37 )
        goto LABEL_90;
    }
    if ( *((_DWORD *)v35 + 15) == 4 && *((_WORD *)v35 + 34) == 46 )
    {
      v37 = *((_WORD *)v35 + 35) == 46;
      goto LABEL_89;
    }
LABEL_90:
    v8 = SyncTreeActionCreateAndInitializeContext(**a1, v2, &lpAddress, *((_DWORD *)*a1 + 8));
    if ( v8 )
      break;
    v38 = lpAddress;
    if ( !lpAddress )
      break;
    if ( ((_BYTE)a1[6] & 4) != 0 && **((char **)lpAddress + 2) < 0 )
    {
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        SyncTraceOutputInternal(L"Marking context for delete [%ws]", (char *)lpAddress + 8240);
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          v8 + 40,
          WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids,
          (char *)lpAddress + 8240);
        v38 = lpAddress;
      }
      v38[11] |= 8u;
      v38 = lpAddress;
    }
    v39 = *a1;
    *(_QWORD *)&v56 = v38 + 2060;
    DWORD2(v56) = 1;
    v57 = *((_QWORD *)v38 + 2);
    v40 = ((__int64 (__fastcall *)(__int128 *, __int64))v39[8])(&v56, v39[12]);
    v41 = v40;
    v42 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
    {
      SyncTraceOutputInternal(
        L"SyncTreeActionWalkTree: Received %d on NEXT_ITEM for [%ws]",
        v40,
        (char *)lpAddress + 8240);
      WPP_SF_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        41,
        (unsigned int)WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids,
        v41,
        (__int64)lpAddress + 8240);
      v42 = WPP_GLOBAL_Control;
    }
    if ( v41 )
    {
      if ( v41 != 1 )
      {
        if ( v42 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v42 + 108) & 1) != 0 )
        {
          SyncTraceOutputInternal(L"SyncTreeActionWalkTree: Received abort from callback ... Aborting Tree Action.");
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 42, WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids);
        }
        SyncTreeActionFreeContext(lpAddress);
        lpAddress = 0;
        goto LABEL_25;
      }
      v43 = lpAddress;
LABEL_104:
      SyncTreeActionFreeContext(v43);
LABEL_105:
      lpAddress = 0;
    }
    else
    {
      v44 = (*v31)[14] & 0x10;
      if ( v44 )
      {
        if ( ((_BYTE)a1[6] & 2) == 0 )
          goto LABEL_123;
        v45 = 0;
      }
      else
      {
        v45 = 2;
      }
      v8 = ((__int64 (__fastcall *)(LPVOID, _QWORD, __int64))a1[5])(lpAddress, *((unsigned int *)*a1 + 8), v45);
      if ( v8 || (v43 = lpAddress) == 0 )
      {
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          SyncTraceOutputInternal(L"SyncTreeActionWalkTree: DirProcessCallback failed with %x", v8);
          v21 = 43;
          goto LABEL_63;
        }
        goto LABEL_25;
      }
      if ( (*((_BYTE *)lpAddress + 44) & 8) != 0 )
      {
        v46 = v44 != 0 ? 16 : 7;
      }
      else if ( v44 )
      {
        v46 = *((_DWORD *)a1 + 3);
      }
      else
      {
        v46 = *((_DWORD *)a1 + 5);
      }
      if ( v46 != 16 )
      {
        while ( 1 )
        {
          SyncTreeActionCallItemHandler(v7, v46, v43);
          if ( ((*v31)[14] & 0x10) != 0 && !*(_DWORD *)(*(_QWORD *)(v7 + 16) + 4LL) )
            break;
          v8 = SyncTreeActionSendCompletionAndCommitNode(
                 (_DWORD)a1,
                 *(_DWORD *)(v7 + 104),
                 v46,
                 (_DWORD)lpAddress,
                 0,
                 (__int64)&v58);
          if ( v8 )
            goto LABEL_25;
          if ( !v58 )
            break;
          v43 = lpAddress;
        }
LABEL_123:
        v43 = lpAddress;
      }
      if ( ((*v31)[14] & 0x10) == 0 )
        goto LABEL_104;
      while ( 1 )
      {
        v47 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64))a1[4])(
                (__int64)v43 + 8,
                (__int64)v43 + 8240,
                *((_DWORD *)a1 + 2) | 0x81u,
                1);
        v48 = v47;
        if ( !v47 )
          break;
        v49 = 4096;
        v50 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          SyncTraceOutputInternal(
            L"SyncTreeActionWalkTree: DirCreateCallback failed with %x for %ws",
            v47,
            (char *)lpAddress + 8240);
          WPP_SF_dS(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            44,
            (unsigned int)WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids,
            v48,
            (__int64)lpAddress + 8240);
          v50 = WPP_GLOBAL_Control;
        }
        if ( v59 )
        {
          v51 = (unsigned int)(v48 + 1073741809);
          if ( (unsigned int)v51 <= 0x2B )
          {
            v52 = 0x82000000001LL;
            if ( _bittest64(&v52, v51) )
            {
              if ( v50 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v50 + 108) & 1) != 0 )
              {
                SyncTraceOutputInternal(L"Ignoring \"not found\" status");
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 45, WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids);
              }
              v48 = 0;
              v49 = 0;
            }
          }
        }
        v53 = *((_QWORD *)lpAddress + 2);
        *(_DWORD *)(v53 + 4) = RtlNtStatusToDosError(v48);
        v8 = SyncTreeActionSendCompletionAndCommitNode(
               (_DWORD)a1,
               v49,
               *((_DWORD *)a1 + 5),
               (_DWORD)lpAddress,
               0,
               (__int64)&v58);
        if ( v8 )
          goto LABEL_25;
        if ( !v58 )
        {
          SyncTreeActionFreeContext(lpAddress);
          goto LABEL_105;
        }
        SyncTreeActionCloseDirectory(lpAddress);
        v43 = lpAddress;
      }
      v2 = (char *)lpAddress;
      lpAddress = 0;
      *((_QWORD *)v2 + 4) = v2 + 48;
      *((_DWORD *)v2 + 12) = 0;
    }
  }
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    SyncTraceOutputInternal(
      L"SyncTreeActionWalkTree: SyncTreeActionCreateAndInitializeContext failed with %x ... Aborting Tree Action.",
      v8);
    v21 = 39;
    goto LABEL_63;
  }
LABEL_25:
  v17 = *a1;
  DWORD2(v56) = 3;
  *(_QWORD *)&v56 = (char *)v60 + 8240;
  v57 = *((_QWORD *)v60 + 2);
  ((void (__fastcall *)(__int128 *, __int64))v17[8])(&v56, v17[12]);
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    SyncTraceOutputInternal(L"SyncTreeActionWalkTree: Sent DONE for [%ws]", (char *)v60 + 8240);
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      46,
      WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids,
      (char *)v60 + 8240);
  }
LABEL_12:
  SyncFree(v7);
LABEL_13:
  if ( lpAddress )
  {
    SyncTreeActionCloseDirectory(lpAddress);
    SyncTreeActionFreeContext(lpAddress);
    lpAddress = 0;
  }
  v11 = (char *)v60;
  if ( v2 )
  {
    while ( v11 != v2 )
    {
      v54 = v2;
      v2 = *(char **)v2;
      SyncTreeActionCloseDirectory(v54);
      SyncTreeActionFreeContext(v54);
      v11 = (char *)v60;
    }
  }
  if ( v11 )
  {
    SyncTreePruneTempNodes(**a1, v11 + 16);
    SyncTreeActionCloseDirectory(v60);
    SyncTreeActionFreeContext(v60);
  }
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncTreeActionWalkTree: %x", v8);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 47, WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x180021040  push    rbp
0x180021042  push    rbx
0x180021043  push    rsi
0x180021044  push    rdi
0x180021045  push    r12
0x180021047  push    r13
0x180021049  push    r14
0x18002104b  push    r15
0x18002104d  mov     rbp, rsp
0x180021050  sub     rsp, 78h
0x180021054  xor     ebx, ebx
0x180021056  xorps   xmm0, xmm0
0x180021059  xor     eax, eax
0x18002105b  mov     [rbp+arg_10], rbx
0x18002105f  mov     [rbp+var_18], rax
0x180021063  mov     rsi, rcx
0x180021066  mov     r15d, ebx
0x180021069  mov     [rbp+lpAddress], rbx
0x18002106d  movups  [rbp+var_28], xmm0
0x180021071  mov     [rbp+arg_0], ebx
0x180021074  mov     rax, cs:WPP_GLOBAL_Control
0x18002107b  lea     r14, WPP_GLOBAL_Control
0x180021082  cmp     rax, r14
0x180021085  jz      short loc_180021101
0x180021087  test    byte ptr [rax+6Ch], 4
0x18002108b  jz      short loc_180021101
0x18002108d  mov     eax, [rcx+30h]
0x180021090  mov     r9d, [rcx+0Ch]
0x180021094  mov     r8d, [rcx+8]
0x180021098  mov     rdx, [rcx]
0x18002109b  mov     dword ptr [rsp+78h+var_40], eax
0x18002109f  mov     rax, [rcx+20h]
0x1800210a3  mov     [rsp+78h+var_48], rax
0x1800210a8  mov     eax, [rcx+14h]
0x1800210ab  mov     dword ptr [rsp+78h+var_50], eax
0x1800210af  mov     eax, [rcx+10h]
0x1800210b2  lea     rcx, aSynctreeaction_18; "SyncTreeActionWalkTree: OpArgs: 0x%p De"...
0x1800210b9  mov     [rsp+78h+var_58], eax
0x1800210bd  call    SyncTraceOutputInternal
0x1800210c2  mov     eax, [rsi+30h]
0x1800210c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800210cc  mov     r9, [rsi]
0x1800210cf  mov     [rsp+78h+var_30], eax
0x1800210d3  mov     rax, [rsi+20h]
0x1800210d7  mov     rcx, [rcx+60h]
0x1800210db  mov     qword ptr [rsp+78h+var_38], rax
0x1800210e0  mov     eax, [rsi+14h]
0x1800210e3  mov     dword ptr [rsp+78h+var_40], eax
0x1800210e7  mov     eax, [rsi+10h]
0x1800210ea  mov     dword ptr [rsp+78h+var_48], eax
0x1800210ee  mov     eax, [rsi+0Ch]
0x1800210f1  mov     dword ptr [rsp+78h+var_50], eax
0x1800210f5  mov     eax, [rsi+8]
0x1800210f8  mov     [rsp+78h+var_58], eax
0x1800210fc  call    WPP_SF_qDdddqD
0x180021101  mov     r12d, [rsi+30h]
0x180021105  mov     ecx, 0F8h
0x18002110a  call    SyncAlloc
0x18002110f  mov     r13, rax
0x180021112  test    rax, rax
0x180021115  jnz     short loc_180021121
0x180021117  mov     edi, 0C000009Ah
0x18002111c  jmp     loc_1800211FC
0x180021121  mov     rax, [rsi]
0x180021124  or      r9, 0FFFFFFFFFFFFFFFFh
0x180021128  mov     rcx, [rax]
0x18002112b  mov     [r13+0], rcx
0x18002112f  mov     rax, [rsi]
0x180021132  mov     rcx, [rax+18h]
0x180021136  mov     [r13+18h], rcx
0x18002113a  mov     rax, [rsi]
0x18002113d  mov     ecx, [rax+20h]
0x180021140  mov     [r13+20h], ecx
0x180021144  mov     rax, [rsi]
0x180021147  mov     rcx, [rax+40h]
0x18002114b  mov     [r13+40h], rcx
0x18002114f  mov     rax, [rsi]
0x180021152  mov     rcx, [rax+48h]
0x180021156  mov     [r13+48h], rcx
0x18002115a  mov     rax, [rsi]
0x18002115d  mov     rcx, [rax+58h]
0x180021161  mov     [r13+58h], rcx
0x180021165  mov     rax, [rsi]
0x180021168  mov     rcx, [rax+50h]
0x18002116c  mov     [r13+50h], rcx
0x180021170  mov     rax, [rsi]
0x180021173  mov     rcx, [rax+60h]
0x180021177  mov     [r13+60h], rcx
0x18002117b  mov     rax, [rsi]
0x18002117e  mov     r8, [rax+8]
0x180021182  inc     r9
0x180021185  cmp     [r8+r9*2], bx
0x18002118a  jnz     short loc_180021182
0x18002118c  lea     r9d, ds:2[r9*2]
0x180021194  xor     edx, edx
0x180021196  lea     rcx, [rbp+arg_10]
0x18002119a  call    SyncTreeActionNewContext
0x18002119f  mov     edi, eax
0x1800211a1  test    eax, eax
0x1800211a3  jz      loc_180021229
0x1800211a9  mov     rax, cs:WPP_GLOBAL_Control
0x1800211b0  cmp     rax, r14
0x1800211b3  jz      short loc_1800211F4
0x1800211b5  mov     r14d, 1
0x1800211bb  test    [rax+6Ch], r14b
0x1800211bf  jz      short loc_1800211ED
0x1800211c1  mov     edx, edi
0x1800211c3  lea     rcx, aSynctreeaction_29; "SyncTreeActionWalkTree: SyncTreeActionN"...
0x1800211ca  call    SyncTraceOutputInternal
0x1800211cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800211d6  lea     edx, [r14+1Ch]
0x1800211da  mov     r9d, edi
0x1800211dd  lea     r8, WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids
0x1800211e4  mov     rcx, [rcx+60h]
0x1800211e8  call    WPP_SF_d
0x1800211ed  lea     r14, WPP_GLOBAL_Control
0x1800211f4  mov     rcx, r13
0x1800211f7  call    SyncFree
0x1800211fc  mov     rcx, [rbp+lpAddress]
0x180021200  test    rcx, rcx
0x180021203  jz      short loc_180021217
0x180021205  call    SyncTreeActionCloseDirectory
0x18002120a  mov     rcx, [rbp+lpAddress]; lpAddress
0x18002120e  call    SyncTreeActionFreeContext
0x180021213  mov     [rbp+lpAddress], rbx
0x180021217  mov     rdx, [rbp+arg_10]
0x18002121b  test    r15, r15
0x18002121e  jnz     loc_180021D49
0x180021224  jmp     loc_180021D4E
0x180021229  mov     rax, [rbp+arg_10]
0x18002122d  mov     r14d, 1
0x180021233  mov     [rax+8], rbx
0x180021237  mov     rax, [rsi]
0x18002123a  mov     rcx, [rax+10h]
0x18002123e  mov     rax, [rbp+arg_10]
0x180021242  mov     [rax+10h], rcx
0x180021246  mov     rax, [rbp+arg_10]
0x18002124a  mov     [rax+2Ch], r14d
0x18002124e  mov     rax, [rbp+arg_10]
0x180021252  lea     rcx, [rax+30h]
0x180021256  mov     [rax+20h], rcx
0x18002125a  mov     [rcx], ebx
0x18002125c  mov     rcx, [rbp+arg_10]
0x180021260  mov     rdx, [rsi]
0x180021263  mov     dword ptr [rbp+var_28+8], ebx
0x180021266  lea     rax, [rcx+2030h]
0x18002126d  mov     qword ptr [rbp+var_28], rax
0x180021271  mov     rax, [rcx+10h]
0x180021275  lea     rcx, [rbp+var_28]
0x180021279  mov     [rbp+var_18], rax
0x18002127d  mov     rax, [rdx+40h]
0x180021281  mov     rdx, [rdx+60h]
0x180021285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002128a  mov     ebx, eax
0x18002128c  mov     rcx, cs:WPP_GLOBAL_Control
0x180021293  lea     rax, WPP_GLOBAL_Control
0x18002129a  cmp     rcx, rax
0x18002129d  jz      short loc_1800212F9
0x18002129f  test    byte ptr [rcx+6Ch], 2
0x1800212a3  jz      short loc_1800212F9
0x1800212a5  mov     r8, [rbp+arg_10]
0x1800212a9  lea     rcx, aSynctreeaction_10; "SyncTreeActionWalkTree: Received %d on "...
0x1800212b0  add     r8, 2030h
0x1800212b7  mov     edx, ebx
0x1800212b9  call    SyncTraceOutputInternal
0x1800212be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800212c5  lea     edx, [r14+1Dh]
0x1800212c9  mov     rax, [rbp+arg_10]
0x1800212cd  lea     r8, WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids
0x1800212d4  add     rax, 2030h
0x1800212da  mov     r9d, ebx
0x1800212dd  mov     qword ptr [rsp+78h+var_58], rax
0x1800212e2  mov     rcx, [rcx+60h]
0x1800212e6  call    WPP_SF_dS
0x1800212eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800212f2  lea     rax, WPP_GLOBAL_Control
0x1800212f9  test    ebx, ebx
0x1800212fb  jz      loc_1800213CC
0x180021301  cmp     rcx, rax
0x180021304  jz      short loc_180021334
0x180021306  test    [rcx+6Ch], r14b
0x18002130a  jz      short loc_180021334
0x18002130c  lea     rcx, aSynctreeaction_8; "SyncTreeActionWalkTree: Received abort "...
0x180021313  call    SyncTraceOutputInternal
0x180021318  mov     edx, 1Fh
0x18002131d  mov     rcx, cs:WPP_GLOBAL_Control
0x180021324  lea     r8, WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids
0x18002132b  mov     rcx, [rcx+60h]
0x18002132f  call    WPP_SF_
0x180021334  xor     ebx, ebx
0x180021336  mov     rcx, [rbp+arg_10]
0x18002133a  mov     rdx, [rsi]
0x18002133d  mov     dword ptr [rbp+var_28+8], 3
0x180021344  lea     rax, [rcx+2030h]
0x18002134b  mov     qword ptr [rbp+var_28], rax
0x18002134f  mov     rax, [rcx+10h]
0x180021353  lea     rcx, [rbp+var_28]
0x180021357  mov     [rbp+var_18], rax
0x18002135b  mov     rax, [rdx+40h]
0x18002135f  mov     rdx, [rdx+60h]
0x180021363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021368  mov     rax, cs:WPP_GLOBAL_Control
0x18002136f  lea     r14, WPP_GLOBAL_Control
0x180021376  cmp     rax, r14
0x180021379  jz      loc_1800211F4
0x18002137f  test    byte ptr [rax+6Ch], 2
0x180021383  jz      loc_1800211F4
0x180021389  mov     rdx, [rbp+arg_10]
0x18002138d  lea     rcx, aSynctreeaction_42; "SyncTreeActionWalkTree: Sent DONE for ["...
0x180021394  add     rdx, 2030h
0x18002139b  call    SyncTraceOutputInternal
0x1800213a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800213a7  lea     r8, WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids
0x1800213ae  mov     r9, [rbp+arg_10]
0x1800213b2  mov     edx, 2Eh ; '.'
0x1800213b7  add     r9, 2030h
0x1800213be  mov     rcx, [rcx+60h]
0x1800213c2  call    WPP_SF_S
0x1800213c7  jmp     loc_1800211F4
0x1800213cc  mov     rdx, [rsi]
0x1800213cf  lea     rcx, [rbp+var_28]
0x1800213d3  mov     rax, [rbp+arg_10]
0x1800213d7  add     rax, 2030h
0x1800213dd  mov     dword ptr [rbp+var_28+8], r14d
0x1800213e1  mov     qword ptr [rbp+var_28], rax
0x1800213e5  mov     rax, [rdx+40h]
0x1800213e9  mov     rdx, [rdx+60h]
0x1800213ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213f2  mov     ebx, eax
0x1800213f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800213fb  lea     rax, WPP_GLOBAL_Control
0x180021402  cmp     rcx, rax
0x180021405  jz      short loc_180021462
0x180021407  test    byte ptr [rcx+6Ch], 2
0x18002140b  jz      short loc_180021462
0x18002140d  mov     r8, [rbp+arg_10]
0x180021411  lea     rcx, aSynctreeaction_12; "SyncTreeActionWalkTree: Received %d on "...
0x180021418  add     r8, 2030h
0x18002141f  mov     edx, ebx
0x180021421  call    SyncTraceOutputInternal
0x180021426  mov     rcx, cs:WPP_GLOBAL_Control
0x18002142d  lea     r8, WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids
0x180021434  mov     rax, [rbp+arg_10]
0x180021438  mov     edx, 20h ; ' '
0x18002143d  add     rax, 2030h
0x180021443  mov     r9d, ebx
0x180021446  mov     qword ptr [rsp+78h+var_58], rax
0x18002144b  mov     rcx, [rcx+60h]
0x18002144f  call    WPP_SF_dS
0x180021454  mov     rcx, cs:WPP_GLOBAL_Control
0x18002145b  lea     rax, WPP_GLOBAL_Control
0x180021462  test    ebx, ebx
0x180021464  jz      short loc_18002148F
0x180021466  cmp     rcx, rax
0x180021469  jz      loc_180021334
0x18002146f  test    [rcx+6Ch], r14b
0x180021473  jz      loc_180021334
0x180021479  lea     rcx, aSynctreeaction_39; "SyncTreeActionWalkTree: Received abort/"...
0x180021480  call    SyncTraceOutputInternal
0x180021485  mov     edx, 21h ; '!'
0x18002148a  jmp     loc_18002131D
0x18002148f  and     r12d, 8
0x180021493  test    byte ptr [rsi+30h], 2
0x180021497  mov     [rbp+arg_8], r12d
0x18002149b  jz      loc_18002155B
0x1800214a1  mov     rdx, [rsi]
0x1800214a4  xor     r8d, r8d
0x1800214a7  mov     rcx, [rbp+arg_10]
0x1800214ab  mov     rax, [rsi+28h]
0x1800214af  mov     edx, [rdx+20h]
0x1800214b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214b7  xor     ebx, ebx
0x1800214b9  mov     edi, eax
0x1800214bb  test    eax, eax
0x1800214bd  jz      short loc_180021510
0x1800214bf  mov     rax, cs:WPP_GLOBAL_Control
0x1800214c6  lea     rdx, WPP_GLOBAL_Control
0x1800214cd  cmp     rax, rdx
0x1800214d0  jz      loc_180021336
0x1800214d6  test    [rax+6Ch], r14b
0x1800214da  jz      loc_180021336
0x1800214e0  mov     edx, edi
0x1800214e2  lea     rcx, aSynctreeaction_4; "SyncTreeActionWalkTree: DirProcessCallb"...
0x1800214e9  call    SyncTraceOutputInternal
0x1800214ee  lea     edx, [rbx+22h]
0x1800214f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800214f8  lea     r8, WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids
0x1800214ff  mov     r9d, edi
0x180021502  mov     rcx, [rcx+60h]
0x180021506  call    WPP_SF_d
0x18002150b  jmp     loc_180021336
0x180021510  mov     r8, [rbp+arg_10]
0x180021514  mov     rcx, r13
0x180021517  mov     edx, [rsi+0Ch]
0x18002151a  call    SyncTreeActionCallItemHandler
0x18002151f  mov     rax, [r13+10h]
0x180021523  cmp     [rax+4], ebx
0x180021526  jz      short loc_18002155D
0x180021528  mov     r9, [rbp+arg_10]
0x18002152c  lea     rax, [rbp+arg_0]
  ... truncated ...
```
