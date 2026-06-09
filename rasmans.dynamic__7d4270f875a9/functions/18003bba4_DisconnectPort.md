# DisconnectPort

- ea: `0x18003bba4`
- end: `0x18003c9ae`
- name: `DisconnectPort`
- size: `3594`
- prototype: ``
- caller_count: `12`
- callee_count: `34`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021e2c`
- `0x18003c9b4`
- `0x18003d6b8`
- `0x180044830`
- `0x180044ad0`
- `0x180044ce0`
- `0x180046fc4`
- `0x18004e9ac`
- `0x18004f350`
- `0x18004f720`
- `0x180050738`
- `0x1800510cc`

## callees

- `0x180005418`
- `0x180005a20`
- `0x180005bcc`
- `0x180005bfc`
- `0x180005cf8`
- `0x18000c3c0`
- `0x18000d600`
- `0x180014b6c`
- `0x18001b340`
- `0x1800210e0`
- `0x18002adfc`
- `0x1800304b4`
- `0x180033654`
- `0x18003372c`
- `0x180033e78`
- `0x180034190`
- `0x180038b8c`
- `0x180039530`
- `0x180039f1c`
- `0x18003a718`
- `0x18003bba4`
- `0x180040c68`
- `0x180040d34`
- `0x180041284`
- `0x180046b70`
- `0x180049944`
- `0x1800499f0`
- `0x18004a7cc`
- `0x18004a89c`
- `0x18004aa34`
- `0x18004bd28`
- `0x180055174`
- `0x1800e8e96`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003bdb6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003c98d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003bdb6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003c98d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c50f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c50f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c642`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c642`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c668`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c668`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bfbd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c4e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bfbd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c4e3`
- `rtutils!RouterLogEventStringA` at `0x18003c4cb`
- `rtutils!RouterLogEventStringA` at `0x18003c4cb`
- `NduProv!__imp_NduCloseHandle` at `0x18003c7aa`
- `NduProv!__imp_NduCloseHandle` at `0x18003c7aa`

## pseudocode

```c
__int64 __fastcall DisconnectPort(_QWORD *a1, void *a2, int a3)
{
  struct _LIST_ENTRY *v6; // rbx
  __int64 v7; // r9
  __int128 v8; // xmm1
  _DWORD *v9; // rsi
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  int v18; // ebx
  unsigned int v19; // eax
  __int64 v20; // rcx
  struct _LIST_ENTRY *v21; // rcx
  int v22; // eax
  bool v23; // zf
  struct _LIST_ENTRY *v24; // rcx
  __int64 v25; // rdx
  struct _LIST_ENTRY *v26; // rcx
  __int64 v27; // rdx
  int v28; // eax
  _DWORD *v29; // rbx
  DWORD v31; // eax
  __int64 v32; // rdx
  DWORD dwErrorCode; // esi
  _QWORD *v34; // rcx
  struct _LIST_ENTRY *v35; // rcx
  __int64 v36; // rax
  __int64 v37; // r9
  __int64 v38; // rdx
  __int64 v39; // rcx
  int v40; // eax
  struct _LIST_ENTRY *v41; // rcx
  __int64 v42; // rbx
  __int64 v43; // rdx
  __int64 v44; // r8
  unsigned int v45; // eax
  DWORD CurrentProcessId; // eax
  _OWORD v47[8]; // [rsp+50h] [rbp-89h] BYREF
  _OWORD v48[6]; // [rsp+D0h] [rbp-9h]
  LPSTR plpszSubStringArray; // [rsp+140h] [rbp+67h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_sqD(
      WPP_GLOBAL_Control[1].Flink,
      137,
      (unsigned int)WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids,
      (_DWORD)a1 + 8,
      *a1,
      a3);
    v6 = WPP_GLOBAL_Control;
  }
  v7 = a1[133];
  if ( v7 && (*(_BYTE *)(v7 + 112) & 0x10) != 0 )
  {
    if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v6[1].Blink) & 0x2000) != 0
      && BYTE1(v6[1].Blink) >= 5u )
    {
      WPP_SF_q(v6[1].Flink, 138, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, *(_QWORD *)(v7 + 16));
    }
    CheckAndInitiateProtocolRenegotiation(a1[133], a1);
    v6 = WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)a1 + 7) == 1
    && v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v6[1].Blink) & 0x2000) != 0
    && BYTE1(v6[1].Blink) >= 5u )
  {
    WPP_SF_q(v6[1].Flink, 139, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, *a1);
    v6 = WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)a1 + 7) == 2 )
  {
    if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v6[1].Blink) & 0x2000) != 0
      && BYTE1(v6[1].Blink) >= 5u )
    {
      WPP_SF_q(v6[1].Flink, 140, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, *a1);
      v6 = WPP_GLOBAL_Control;
    }
    memset_0(v47, 0, 0x9Cu);
    if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v6[1].Blink) & 0x2000) != 0
      && BYTE1(v6[1].Blink) >= 5u )
    {
      WPP_SF_s(v6[1].Flink, 141, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, a1 + 1);
    }
    GetBundleStatisticsFromNdisWan(a1, v47);
    v8 = v47[1];
    v9 = (_DWORD *)a1[133];
    *((_OWORD *)a1 + 36) = v47[0];
    v10 = v47[2];
    *((_OWORD *)a1 + 37) = v8;
    v11 = v47[3];
    *((_OWORD *)a1 + 38) = v10;
    v12 = v47[4];
    *((_OWORD *)a1 + 39) = v11;
    v13 = v47[5];
    *((_OWORD *)a1 + 40) = v12;
    v14 = v47[6];
    *((_OWORD *)a1 + 41) = v13;
    v15 = v47[7];
    *((_OWORD *)a1 + 42) = v14;
    v16 = v48[0];
    *((_OWORD *)a1 + 43) = v15;
    v17 = *(_OWORD *)((char *)v48 + 12);
    *((_OWORD *)a1 + 44) = v16;
    *(_OWORD *)((char *)a1 + 716) = v17;
    if ( !v9 )
      goto LABEL_39;
    if ( v9[17] != 1 )
      goto LABEL_39;
    v18 = v9[35];
    if ( v18 == GetCurrentProcessId() && v9[215] != 2 )
      goto LABEL_39;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 142, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
    }
    v19 = RevertPostConnectionActions(a1[133]);
    if ( !v19 )
      goto LABEL_39;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 143, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v19);
LABEL_39:
      v6 = WPP_GLOBAL_Control;
    }
  }
  v20 = a1[133];
  if ( v20 )
  {
    LODWORD(plpszSubStringArray) = 0;
    if ( (*(_BYTE *)(v20 + 112) & 8) != 0 )
    {
      if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v6[1].Blink) & 0x2000) != 0
        && BYTE1(v6[1].Blink) >= 5u )
      {
        WPP_SF_(v6[1].Flink, 144, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
      }
    }
    else
    {
      if ( (*(_BYTE *)(v20 + 112) & 4) != 0 )
      {
        if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v6[1].Blink) & 0x2000) != 0
          && BYTE1(v6[1].Blink) >= 5u )
        {
          WPP_SF_(v6[1].Flink, 145, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
        }
        TelemetryEventWriteStateChange(a1, 617, 0);
        FreeNotifierHandle(a2);
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 6u )
        {
          return 617;
        }
        v25 = 146;
        goto LABEL_126;
      }
      QueueCloseConnections(v20, a2, &plpszSubStringArray);
      if ( (_DWORD)plpszSubStringArray )
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          return 600;
        if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
        {
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 147, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
          v26 = WPP_GLOBAL_Control;
        }
        if ( v26 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(v26[1].Blink) & 0x2000) == 0
          || BYTE1(v26[1].Blink) < 6u )
        {
          return 600;
        }
        v27 = 148;
        goto LABEL_207;
      }
    }
  }
  UnmapEndPoint(a1);
  a1[28] = a1[27];
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control[1].Flink,
      149,
      WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids,
      *((unsigned int *)a1 + 7));
    v21 = WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    if ( v21 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v21[1].Blink) & 0x2000) != 0
      && BYTE1(v21[1].Blink) >= 5u )
    {
      WPP_SF_q(v21[1].Flink, 153, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, a1[58]);
    }
    FreeNotifierHandle((HANDLE)a1[58]);
    a1[58] = -1;
  }
  else
  {
    if ( *((_DWORD *)a1 + 7) == 3 )
      goto LABEL_102;
    if ( v21 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v21[1].Blink) & 0x2000) != 0
      && BYTE1(v21[1].Blink) >= 5u )
    {
      WPP_SF_(v21[1].Flink, 150, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
      v21 = WPP_GLOBAL_Control;
    }
    if ( *((_DWORD *)a1 + 7) == 2 )
    {
      if ( !a1[66] )
        goto LABEL_102;
      v22 = *((_DWORD *)a1 + 66);
      if ( !v22 || v22 == 600 )
        *((_DWORD *)a1 + 66) = 619;
      CompleteAsyncRequest(a1);
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
      {
        WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 151, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, *a1);
      }
      FreeNotifierHandle((HANDLE)a1[58]);
      v23 = (a1[153] & 1) == 0;
      a1[58] = -1;
      if ( v23 )
        SendDisconnectNotificationToProtcolEngine(a1);
      else
        LocalFree((HLOCAL)a1[66]);
      a1[66] = 0;
    }
    else
    {
      if ( !*((_DWORD *)a1 + 118) )
        goto LABEL_102;
      v28 = *((_DWORD *)a1 + 66);
      if ( !v28 || v28 == 600 )
        *((_DWORD *)a1 + 66) = 619;
      CompleteAsyncRequest(a1);
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
      {
        WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 152, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, *a1);
      }
      FreeNotifierHandle((HANDLE)a1[58]);
      a1[58] = -1;
      RemoveTimeoutElement(a1);
      a1[60] = 0;
    }
  }
  v21 = WPP_GLOBAL_Control;
LABEL_102:
  if ( (a1[153] & 2) != 0 )
  {
    if ( v21 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(v21[1].Blink) & 0x2000) == 0
      || BYTE1(v21[1].Blink) < 5u )
    {
      v29 = a1 + 153;
    }
    else
    {
      WPP_SF_s(v21[1].Flink, 154, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, a1 + 1);
      v29 = a1 + 153;
    }
    if ( a1[60] )
    {
      RemoveTimeoutElement(a1);
      a1[60] = 0;
    }
    else
    {
      v29 = a1 + 153;
    }
    *v29 = 0;
    v21 = WPP_GLOBAL_Control;
  }
  if ( a1[58] != -1 && *((_DWORD *)a1 + 7) == 3 )
  {
    if ( v21 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(v21[1].Blink) & 0x2000) != 0 && BYTE1(v21[1].Blink) >= 5u )
      {
        WPP_SF_qs(
          v21[1].Flink,
          155,
          (unsigned int)WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids,
          (_DWORD)a2,
          (__int64)(a1 + 1));
        v21 = WPP_GLOBAL_Control;
      }
      if ( v21 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v21[1].Blink) & 0x2000) != 0
        && BYTE1(v21[1].Blink) >= 5u )
      {
        WPP_SF_q(v21[1].Flink, 156, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, a1[58]);
      }
    }
    TelemetryEventWriteStateChange(a1, 617, 0);
    FreeNotifierHandle(a2);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 6u )
    {
      return 617;
    }
    v25 = 157;
LABEL_126:
    WPP_SF_d(v24[1].Flink, v25, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, 617);
    return 617;
  }
  if ( a2 != (void *)-1LL && *((_DWORD *)a1 + 7) == 3 )
  {
    if ( v21 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v21[1].Blink) & 0x2000) != 0
      && BYTE1(v21[1].Blink) >= 5u )
    {
      WPP_SF_s(v21[1].Flink, 158, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, a1 + 1);
    }
    a1[58] = a2;
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 6u )
    {
      return 600;
    }
    v27 = 159;
LABEL_207:
    WPP_SF_d(v26[1].Flink, v27, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, 600);
    return 600;
  }
  if ( *((_DWORD *)a1 + 7) == 4 )
  {
    a1[58] = a2;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
    {
      WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 160, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, *a1);
    }
    CompleteDisconnectRequest(a1);
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 161, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, 0);
    }
    return 0;
  }
  if ( a1[60] )
  {
    RemoveTimeoutElement(a1);
    a1[60] = 0;
    v21 = WPP_GLOBAL_Control;
  }
  if ( a1[133] && a3 && *((char *)a1 + 40) >= 0 )
  {
    if ( v21 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v21[1].Blink) & 0x2000) != 0
      && BYTE1(v21[1].Blink) >= 5u )
    {
      WPP_SF_q(v21[1].Flink, 162, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, *a1);
    }
    *((_DWORD *)a1 + 268) = 1;
  }
  v31 = (*(__int64 (__fastcall **)(_QWORD))(a1[6] + 56LL))(a1[27]);
  dwErrorCode = v31;
  if ( v31 && v31 != 600 )
  {
    plpszSubStringArray = (LPSTR)(a1 + 1);
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_qD(WPP_GLOBAL_Control[1].Flink, 163, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, *a1, v31);
    }
    TelemetryEventWriteStateChange(a1, dwErrorCode, 0);
    RouterLogEventStringA(hLogEvents, 1u, 0x4E5Eu, 1u, &plpszSubStringArray, dwErrorCode, 1u);
  }
  while ( 1 )
  {
    v34 = (_QWORD *)a1[139];
    if ( !v34 )
      break;
    a1[139] = *v34;
    LocalFree(v34);
  }
  v35 = (struct _LIST_ENTRY *)a1[138];
  a1[140] = 0;
  if ( v35 != (struct _LIST_ENTRY *)-1LL )
  {
    CloseHandle(v35);
    a1[138] = -1;
  }
  if ( (*((_DWORD *)a1 + 7) & 0xFFFFFFFA) == 0 && *((_DWORD *)a1 + 7) != 4 )
    FreeDeviceList(a1);
  v36 = a1[131];
  if ( v36 )
  {
    --*(_DWORD *)(v36 + 24);
    v35 = (struct _LIST_ENTRY *)a1[131];
    if ( !v35[2].Flink && !LODWORD(v35[1].Blink) )
    {
      FreeBundle(v35);
LABEL_177:
      a1[131] = 0;
      goto LABEL_178;
    }
    if ( !a1[133] )
      goto LABEL_177;
  }
LABEL_178:
  *((_DWORD *)a1 + 67) = a3;
  a1[31] = -1;
  a1[32] = -1;
  if ( !dwErrorCode || dwErrorCode == 600 )
  {
    v37 = 3;
  }
  else
  {
    v35 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
    {
      WPP_SF_dq(WPP_GLOBAL_Control[1].Flink, 164, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, dwErrorCode, *a1);
    }
    v37 = 4;
  }
  SetPortConnState(v35, v32, a1, v37);
  FlushPcbReceivePackets(a1);
  if ( !dwErrorCode )
  {
    SetPortConnState(v39, v38, a1, 4);
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
    {
      WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 165, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, *a1);
    }
    SignalPortDisconnect(a1, 0);
    EnterCriticalSection(&g_csConnectionNotifierList);
    SignalNotifiers(pConnectionNotifierList, 2, 0);
    LeaveCriticalSection(&g_csConnectionNotifierList);
  }
  if ( !a3 )
  {
    if ( !dwErrorCode || dwErrorCode == 600 )
    {
      v40 = *((_DWORD *)a1 + 66);
      if ( !v40 || v40 == 600 )
        *((_DWORD *)a1 + 66) = dwErrorCode;
    }
    else
    {
      *((_DWORD *)a1 + 66) = 619;
    }
  }
  if ( a2 != (void *)-1LL )
  {
    a1[58] = a2;
    SetPortAsyncReqType("onecoreuap\\net\\rras\\ras\\rasman\\rasman\\util.c", 2013, a1, 9);
    if ( dwErrorCode == 600 )
    {
      if ( a1[60] )
      {
        RemoveTimeoutElement(a1);
        a1[60] = 0;
      }
      a1[60] = AddTimeoutElement(DisconnectTimeout, a1, 0, 10);
      AdjustTimer();
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 6u )
      {
        return 600;
      }
      v27 = 166;
      goto LABEL_207;
    }
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
    {
      WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 167, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, *a1);
    }
    CompleteDisconnectRequest(a1);
    goto LABEL_214;
  }
  SetPortAsyncReqType("onecoreuap\\net\\rras\\ras\\rasman\\rasman\\util.c", 2046, a1, 0);
  a1[58] = -1;
  if ( !dwErrorCode )
  {
    v42 = a1[133];
    v41 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
    {
      if ( v42 )
      {
        v43 = *(unsigned int *)(v42 + 68);
        v44 = *(unsigned int *)(v42 + 24);
      }
      else
      {
        v43 = 0;
        v44 = 0;
      }
      WPP_SF_ddqddqc(
        WPP_GLOBAL_Control[1].Flink,
        v43,
        v44,
        *((unsigned int *)a1 + 67),
        *((_DWORD *)a1 + 331),
        v42,
        v43,
        v44,
        a1[160],
        *((_DWORD *)a1 + 329) != 0);
      v41 = WPP_GLOBAL_Control;
    }
    if ( (*((_DWORD *)a1 + 67) || *((_DWORD *)a1 + 329))
      && v42
      && *(_DWORD *)(v42 + 68) == 1
      && *(_DWORD *)(v42 + 24)
      && ((a1[160] + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v45 = DwQueueRedial(v42);
      if ( v45 )
      {
        v41 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_247;
        }
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 169, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v45);
      }
    }
    else
    {
      if ( (unsigned __int64)(a1[160] - 1LL) > 0xFFFFFFFFFFFFFFFDuLL
        || v41 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(v41[1].Blink) & 0x2000) == 0
        || BYTE1(v41[1].Blink) < 5u )
      {
        goto LABEL_247;
      }
      WPP_SF_s(v41[1].Flink, 170, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, a1 + 1);
    }
    v41 = WPP_GLOBAL_Control;
LABEL_247:
    if ( !*((_DWORD *)a1 + 268) )
      goto LABEL_215;
    if ( v41 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v41[1].Blink) & 0x2000) != 0
      && BYTE1(v41[1].Blink) >= 5u )
    {
      WPP_SF_q(v41[1].Flink, 171, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, *a1);
    }
    CurrentProcessId = GetCurrentProcessId();
    PortClose(a1, CurrentProcessId, 1, 0);
  }
LABEL_214:
  v41 = WPP_GLOBAL_Control;
LABEL_215:
  if ( a1[171] != -1 )
  {
    NduCloseHandle(a1[171]);
    a1[171] = -1;
    v41 = WPP_GLOBAL_Control;
  }
  if ( v41 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v41[1].Blink) & 0x2000) != 0
    && BYTE1(v41[1].Blink) >= 6u )
  {
    WPP_SF_d(v41[1].Flink, 172, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, dwErrorCode);
  }
  return dwErrorCode;
}

```

## disassembly

```asm
0x18003bba4  push    rbp
0x18003bba6  push    rbx
0x18003bba7  push    rsi
0x18003bba8  push    rdi
0x18003bba9  push    r12
0x18003bbab  push    r13
0x18003bbad  push    r14
0x18003bbaf  push    r15
0x18003bbb1  lea     rbp, [rsp-1Fh]
0x18003bbb6  sub     rsp, 0F8h
0x18003bbbd  mov     r15d, r8d
0x18003bbc0  mov     r14, rdx
0x18003bbc3  mov     rdi, rcx
0x18003bbc6  mov     rbx, cs:WPP_GLOBAL_Control
0x18003bbcd  lea     rsi, WPP_GLOBAL_Control
0x18003bbd4  mov     r13d, 2000h
0x18003bbda  cmp     rbx, rsi
0x18003bbdd  jz      short loc_18003BC18
0x18003bbdf  test    [rbx+1Ch], r13d
0x18003bbe3  jz      short loc_18003BC18
0x18003bbe5  cmp     byte ptr [rbx+19h], 6
0x18003bbe9  jb      short loc_18003BC18
0x18003bbeb  mov     rax, [rcx]
0x18003bbee  lea     r9, [rcx+8]
0x18003bbf2  mov     rcx, [rbx+10h]
0x18003bbf6  mov     edx, 89h
0x18003bbfb  mov     [rsp+130h+dwErrorCode], r8d
0x18003bc00  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003bc07  mov     [rsp+130h+plpszSubStringArray], rax
0x18003bc0c  call    WPP_SF_sqD
0x18003bc11  mov     rbx, cs:WPP_GLOBAL_Control
0x18003bc18  mov     r9, [rdi+428h]
0x18003bc1f  xor     r12d, r12d
0x18003bc22  test    r9, r9
0x18003bc25  jz      short loc_18003BC6E
0x18003bc27  test    byte ptr [r9+70h], 10h
0x18003bc2c  jz      short loc_18003BC6E
0x18003bc2e  cmp     rbx, rsi
0x18003bc31  jz      short loc_18003BC58
0x18003bc33  test    [rbx+1Ch], r13d
0x18003bc37  jz      short loc_18003BC58
0x18003bc39  cmp     byte ptr [rbx+19h], 5
0x18003bc3d  jb      short loc_18003BC58
0x18003bc3f  mov     r9, [r9+10h]
0x18003bc43  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003bc4a  mov     rcx, [rbx+10h]
0x18003bc4e  mov     edx, 8Ah
0x18003bc53  call    WPP_SF_q
0x18003bc58  mov     rcx, [rdi+428h]
0x18003bc5f  mov     rdx, rdi
0x18003bc62  call    CheckAndInitiateProtocolRenegotiation
0x18003bc67  mov     rbx, cs:WPP_GLOBAL_Control
0x18003bc6e  cmp     dword ptr [rdi+1Ch], 1
0x18003bc72  jnz     short loc_18003BCA4
0x18003bc74  cmp     rbx, rsi
0x18003bc77  jz      short loc_18003BCA4
0x18003bc79  test    [rbx+1Ch], r13d
0x18003bc7d  jz      short loc_18003BCA4
0x18003bc7f  cmp     byte ptr [rbx+19h], 5
0x18003bc83  jb      short loc_18003BCA4
0x18003bc85  mov     r9, [rdi]
0x18003bc88  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003bc8f  mov     rcx, [rbx+10h]
0x18003bc93  mov     edx, 8Bh
0x18003bc98  call    WPP_SF_q
0x18003bc9d  mov     rbx, cs:WPP_GLOBAL_Control
0x18003bca4  cmp     dword ptr [rdi+1Ch], 2
0x18003bca8  jnz     loc_18003BE53
0x18003bcae  cmp     rbx, rsi
0x18003bcb1  jz      short loc_18003BCDE
0x18003bcb3  test    [rbx+1Ch], r13d
0x18003bcb7  jz      short loc_18003BCDE
0x18003bcb9  cmp     byte ptr [rbx+19h], 5
0x18003bcbd  jb      short loc_18003BCDE
0x18003bcbf  mov     r9, [rdi]
0x18003bcc2  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003bcc9  mov     rcx, [rbx+10h]
0x18003bccd  mov     edx, 8Ch
0x18003bcd2  call    WPP_SF_q
0x18003bcd7  mov     rbx, cs:WPP_GLOBAL_Control
0x18003bcde  xor     edx, edx; Val
0x18003bce0  lea     rcx, [rsp+130h+var_E0]; void *
0x18003bce5  mov     r8d, 9Ch; Size
0x18003bceb  call    memset_0
0x18003bcf0  cmp     rbx, rsi
0x18003bcf3  jz      short loc_18003BD1A
0x18003bcf5  test    [rbx+1Ch], r13d
0x18003bcf9  jz      short loc_18003BD1A
0x18003bcfb  cmp     byte ptr [rbx+19h], 5
0x18003bcff  jb      short loc_18003BD1A
0x18003bd01  mov     rcx, [rbx+10h]
0x18003bd05  lea     r9, [rdi+8]
0x18003bd09  mov     edx, 8Dh
0x18003bd0e  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003bd15  call    WPP_SF_s
0x18003bd1a  lea     rdx, [rsp+130h+var_E0]
0x18003bd1f  mov     rcx, rdi
0x18003bd22  call    GetBundleStatisticsFromNdisWan
0x18003bd27  movaps  xmm0, [rsp+130h+var_E0]
0x18003bd2c  movaps  xmm1, [rbp+57h+var_D0]
0x18003bd30  mov     rsi, [rdi+428h]
0x18003bd37  movups  xmmword ptr [rdi+240h], xmm0
0x18003bd3e  movaps  xmm0, [rbp+57h+var_C0]
0x18003bd42  movups  xmmword ptr [rdi+250h], xmm1
0x18003bd49  movaps  xmm1, [rbp+57h+var_B0]
0x18003bd4d  movups  xmmword ptr [rdi+260h], xmm0
0x18003bd54  movaps  xmm0, [rbp+57h+var_A0]
0x18003bd58  movups  xmmword ptr [rdi+270h], xmm1
0x18003bd5f  movaps  xmm1, [rbp+57h+var_90]
0x18003bd63  movups  xmmword ptr [rdi+280h], xmm0
0x18003bd6a  movaps  xmm0, [rbp+57h+var_80]
0x18003bd6e  movups  xmmword ptr [rdi+290h], xmm1
0x18003bd75  movaps  xmm1, [rbp+57h+var_70]
0x18003bd79  movups  xmmword ptr [rdi+2A0h], xmm0
0x18003bd80  movaps  xmm0, [rbp+57h+var_60]
0x18003bd84  movups  xmmword ptr [rdi+2B0h], xmm1
0x18003bd8b  movups  xmm1, [rbp+57h+var_60+0Ch]
0x18003bd8f  movups  xmmword ptr [rdi+2C0h], xmm0
0x18003bd96  movups  xmmword ptr [rdi+2CCh], xmm1
0x18003bd9d  test    rsi, rsi
0x18003bda0  jz      loc_18003BE45
0x18003bda6  cmp     dword ptr [rsi+44h], 1
0x18003bdaa  jnz     loc_18003BE45
0x18003bdb0  mov     ebx, [rsi+8Ch]
0x18003bdb6  call    cs:__imp_GetCurrentProcessId
0x18003bdbd  nop     dword ptr [rax+rax+00h]
0x18003bdc2  cmp     ebx, eax
0x18003bdc4  jnz     short loc_18003BDCF
0x18003bdc6  cmp     dword ptr [rsi+35Ch], 2
0x18003bdcd  jnz     short loc_18003BE45
0x18003bdcf  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bdd6  lea     rsi, WPP_GLOBAL_Control
0x18003bddd  cmp     rcx, rsi
0x18003bde0  jz      short loc_18003BE03
0x18003bde2  test    [rcx+1Ch], r13d
0x18003bde6  jz      short loc_18003BE03
0x18003bde8  cmp     byte ptr [rcx+19h], 5
0x18003bdec  jb      short loc_18003BE03
0x18003bdee  mov     rcx, [rcx+10h]
0x18003bdf2  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003bdf9  mov     edx, 8Eh
0x18003bdfe  call    WPP_SF_
0x18003be03  mov     rcx, [rdi+428h]
0x18003be0a  call    RevertPostConnectionActions
0x18003be0f  test    eax, eax
0x18003be11  jz      short loc_18003BE4C
0x18003be13  mov     rbx, cs:WPP_GLOBAL_Control
0x18003be1a  cmp     rbx, rsi
0x18003be1d  jz      short loc_18003BE53
0x18003be1f  test    [rbx+1Ch], r13d
0x18003be23  jz      short loc_18003BE53
0x18003be25  cmp     byte ptr [rbx+19h], 2
0x18003be29  jb      short loc_18003BE53
0x18003be2b  mov     rcx, [rbx+10h]
0x18003be2f  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003be36  mov     edx, 8Fh
0x18003be3b  mov     r9d, eax
0x18003be3e  call    WPP_SF_d
0x18003be43  jmp     short loc_18003BE4C
0x18003be45  lea     rsi, WPP_GLOBAL_Control
0x18003be4c  mov     rbx, cs:WPP_GLOBAL_Control
0x18003be53  mov     rcx, [rdi+428h]
0x18003be5a  test    rcx, rcx
0x18003be5d  jz      short loc_18003BE93
0x18003be5f  mov     dword ptr [rbp+57h+arg_0], r12d
0x18003be63  test    byte ptr [rcx+70h], 8
0x18003be67  jz      loc_18003BFCE
0x18003be6d  cmp     rbx, rsi
0x18003be70  jz      short loc_18003BE93
0x18003be72  test    [rbx+1Ch], r13d
0x18003be76  jz      short loc_18003BE93
0x18003be78  cmp     byte ptr [rbx+19h], 5
0x18003be7c  jb      short loc_18003BE93
0x18003be7e  mov     rcx, [rbx+10h]
0x18003be82  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003be89  mov     edx, 90h
0x18003be8e  call    WPP_SF_
0x18003be93  mov     rcx, rdi
0x18003be96  call    UnmapEndPoint
0x18003be9b  mov     rax, [rdi+0D8h]
0x18003bea2  mov     [rdi+0E0h], rax
0x18003bea9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003beb0  lea     rbx, WPP_GLOBAL_Control
0x18003beb7  cmp     rcx, rbx
0x18003beba  jz      short loc_18003BEE8
0x18003bebc  test    [rcx+1Ch], r13d
0x18003bec0  jz      short loc_18003BEE8
0x18003bec2  cmp     byte ptr [rcx+19h], 5
0x18003bec6  jb      short loc_18003BEE8
0x18003bec8  mov     r9d, [rdi+1Ch]
0x18003becc  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003bed3  mov     rcx, [rcx+10h]
0x18003bed7  mov     edx, 95h
0x18003bedc  call    WPP_SF_d
0x18003bee1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bee8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003beec  test    r15d, r15d
0x18003beef  jnz     loc_18003C155
0x18003bef5  cmp     dword ptr [rdi+1Ch], 3
0x18003bef9  jz      loc_18003C19C
0x18003beff  cmp     rcx, rbx
0x18003bf02  jz      short loc_18003BF2C
0x18003bf04  test    [rcx+1Ch], r13d
0x18003bf08  jz      short loc_18003BF2C
0x18003bf0a  cmp     byte ptr [rcx+19h], 5
0x18003bf0e  jb      short loc_18003BF2C
0x18003bf10  mov     rcx, [rcx+10h]
0x18003bf14  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003bf1b  mov     edx, 96h
0x18003bf20  call    WPP_SF_
0x18003bf25  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bf2c  cmp     dword ptr [rdi+1Ch], 2
0x18003bf30  jnz     loc_18003C0D1
0x18003bf36  cmp     [rdi+210h], r12
0x18003bf3d  jz      loc_18003C19C
0x18003bf43  mov     eax, [rdi+108h]
0x18003bf49  test    eax, eax
0x18003bf4b  jz      short loc_18003BF54
0x18003bf4d  cmp     eax, 258h
0x18003bf52  jnz     short loc_18003BF5E
0x18003bf54  mov     dword ptr [rdi+108h], 26Bh
0x18003bf5e  mov     rcx, rdi
0x18003bf61  call    CompleteAsyncRequest
0x18003bf66  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bf6d  cmp     rcx, rbx
0x18003bf70  jz      short loc_18003BF96
0x18003bf72  test    [rcx+1Ch], r13d
0x18003bf76  jz      short loc_18003BF96
0x18003bf78  cmp     byte ptr [rcx+19h], 5
0x18003bf7c  jb      short loc_18003BF96
0x18003bf7e  mov     r9, [rdi]
0x18003bf81  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003bf88  mov     rcx, [rcx+10h]
0x18003bf8c  mov     edx, 97h
0x18003bf91  call    WPP_SF_q
0x18003bf96  mov     rcx, [rdi+1D0h]; hObject
0x18003bf9d  call    FreeNotifierHandle
0x18003bfa2  test    byte ptr [rdi+4C8h], 1
0x18003bfa9  mov     [rdi+1D0h], rsi
0x18003bfb0  jz      loc_18003C0BD
0x18003bfb6  mov     rcx, [rdi+210h]; hMem
0x18003bfbd  call    cs:__imp_LocalFree
0x18003bfc4  nop     dword ptr [rax+rax+00h]
0x18003bfc9  jmp     loc_18003C0C5
0x18003bfce  test    byte ptr [rcx+70h], 4
0x18003bfd2  jz      short loc_18003C042
0x18003bfd4  cmp     rbx, rsi
0x18003bfd7  jz      short loc_18003BFFA
0x18003bfd9  test    [rbx+1Ch], r13d
0x18003bfdd  jz      short loc_18003BFFA
0x18003bfdf  cmp     byte ptr [rbx+19h], 5
0x18003bfe3  jb      short loc_18003BFFA
0x18003bfe5  mov     rcx, [rbx+10h]
0x18003bfe9  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003bff0  mov     edx, 91h
0x18003bff5  call    WPP_SF_
0x18003bffa  mov     ebx, 269h
0x18003bfff  xor     r8d, r8d
0x18003c002  mov     edx, ebx
0x18003c004  mov     rcx, rdi
0x18003c007  call    TelemetryEventWriteStateChange
0x18003c00c  mov     rcx, r14; hObject
0x18003c00f  call    FreeNotifierHandle
0x18003c014  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c01b  cmp     rcx, rsi
0x18003c01e  jz      loc_18003C2DB
0x18003c024  test    [rcx+1Ch], r13d
0x18003c028  jz      loc_18003C2DB
0x18003c02e  cmp     byte ptr [rcx+19h], 6
0x18003c032  jb      loc_18003C2DB
0x18003c038  mov     edx, 92h
0x18003c03d  jmp     loc_18003C2C8
0x18003c042  lea     r8, [rbp+57h+arg_0]
0x18003c046  mov     rdx, r14
0x18003c049  call    QueueCloseConnections
0x18003c04e  cmp     dword ptr [rbp+57h+arg_0], r12d
0x18003c052  jz      loc_18003BE93
0x18003c058  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c05f  cmp     rcx, rsi
0x18003c062  jz      loc_18003C74B
0x18003c068  test    [rcx+1Ch], r13d
0x18003c06c  jz      short loc_18003C090
0x18003c06e  cmp     byte ptr [rcx+19h], 5
0x18003c072  jb      short loc_18003C090
0x18003c074  mov     rcx, [rcx+10h]
0x18003c078  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003c07f  mov     edx, 93h
0x18003c084  call    WPP_SF_
0x18003c089  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c090  cmp     rcx, rsi
0x18003c093  jz      loc_18003C74B
0x18003c099  test    [rcx+1Ch], r13d
0x18003c09d  jz      loc_18003C74B
0x18003c0a3  cmp     byte ptr [rcx+19h], 6
0x18003c0a7  jb      loc_18003C74B
0x18003c0ad  mov     edx, 94h
0x18003c0b2  mov     r9d, 258h
0x18003c0b8  jmp     loc_18003C73B
0x18003c0bd  mov     rcx, rdi
0x18003c0c0  call    SendDisconnectNotificationToProtcolEngine
  ... truncated ...
```
