# DisconnectPort

- ea: `0x180039ea0`
- end: `0x18003ac73`
- name: `DisconnectPort`
- size: `3539`
- prototype: `__int64 __fastcall(_QWORD *, void *, int)`
- caller_count: `12`
- callee_count: `34`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800210fc`
- `0x18003ac7c`
- `0x18003b8fc`
- `0x1800426a0`
- `0x180042920`
- `0x180042b20`
- `0x180044d00`
- `0x18004c518`
- `0x18004ce78`
- `0x18004d22c`
- `0x18004e1ec`
- `0x18004eb50`

## callees

- `0x1800056c8`
- `0x180005c6c`
- `0x180005e0c`
- `0x180005e34`
- `0x180005f1c`
- `0x18000bfb0`
- `0x18000d160`
- `0x18001435c`
- `0x18001a8c8`
- `0x18002040c`
- `0x180029c20`
- `0x18002f0a0`
- `0x18003204c`
- `0x180032118`
- `0x180032814`
- `0x180032b0c`
- `0x18003705c`
- `0x180037988`
- `0x1800382e8`
- `0x180038aa0`
- `0x180039ea0`
- `0x18003ed34`
- `0x18003edf8`
- `0x18003f2e0`
- `0x1800448e0`
- `0x180047668`
- `0x180047714`
- `0x180048464`
- `0x18004852c`
- `0x1800486b4`
- `0x180049944`
- `0x180052a20`
- `0x1800e7206`
- `0x1800e9010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003a0b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003ac58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003a0b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003ac58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a7f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a7f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a920`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a920`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a940`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a940`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a2b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a7cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a2b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a7cd`
- `rtutils!RouterLogEventStringA` at `0x18003a7bb`
- `rtutils!RouterLogEventStringA` at `0x18003a7bb`
- `NduProv!__imp_NduCloseHandle` at `0x18003aa7c`
- `NduProv!__imp_NduCloseHandle` at `0x18003aa7c`

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
  __int64 v47; // r8
  _OWORD v48[8]; // [rsp+50h] [rbp-89h] BYREF
  _OWORD v49[6]; // [rsp+D0h] [rbp-9h]
  LPSTR plpszSubStringArray; // [rsp+140h] [rbp+67h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_sqD(
      WPP_GLOBAL_Control[1].Flink,
      137,
      (unsigned int)WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids,
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
      WPP_SF_q(v6[1].Flink, 138, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, *(_QWORD *)(v7 + 16));
    }
    CheckAndInitiateProtocolRenegotiation(a1[133], a1);
    v6 = WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)a1 + 7) == 1
    && v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v6[1].Blink) & 0x2000) != 0
    && BYTE1(v6[1].Blink) >= 5u )
  {
    WPP_SF_q(v6[1].Flink, 139, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, *a1);
    v6 = WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)a1 + 7) == 2 )
  {
    if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v6[1].Blink) & 0x2000) != 0
      && BYTE1(v6[1].Blink) >= 5u )
    {
      WPP_SF_q(v6[1].Flink, 140, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, *a1);
      v6 = WPP_GLOBAL_Control;
    }
    memset_0(v48, 0, 0x9Cu);
    if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v6[1].Blink) & 0x2000) != 0
      && BYTE1(v6[1].Blink) >= 5u )
    {
      WPP_SF_s(v6[1].Flink, 141, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, a1 + 1);
    }
    GetBundleStatisticsFromNdisWan(a1, v48);
    v8 = v48[1];
    v9 = (_DWORD *)a1[133];
    *((_OWORD *)a1 + 36) = v48[0];
    v10 = v48[2];
    *((_OWORD *)a1 + 37) = v8;
    v11 = v48[3];
    *((_OWORD *)a1 + 38) = v10;
    v12 = v48[4];
    *((_OWORD *)a1 + 39) = v11;
    v13 = v48[5];
    *((_OWORD *)a1 + 40) = v12;
    v14 = v48[6];
    *((_OWORD *)a1 + 41) = v13;
    v15 = v48[7];
    *((_OWORD *)a1 + 42) = v14;
    v16 = v49[0];
    *((_OWORD *)a1 + 43) = v15;
    v17 = *(_OWORD *)((char *)v49 + 12);
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
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 142, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
    }
    v19 = RevertPostConnectionActions(a1[133]);
    if ( !v19 )
      goto LABEL_39;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 143, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v19);
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
        WPP_SF_(v6[1].Flink, 144, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
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
          WPP_SF_(v6[1].Flink, 145, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
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
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 147, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
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
  UnmapEndPoint((__int64)a1);
  a1[28] = a1[27];
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control[1].Flink,
      149,
      WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids,
      *((unsigned int *)a1 + 7));
    v21 = WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    if ( v21 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v21[1].Blink) & 0x2000) != 0
      && BYTE1(v21[1].Blink) >= 5u )
    {
      WPP_SF_q(v21[1].Flink, 153, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, a1[58]);
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
      WPP_SF_(v21[1].Flink, 150, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
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
        WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 151, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, *a1);
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
        WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 152, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, *a1);
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
      WPP_SF_s(v21[1].Flink, 154, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, a1 + 1);
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
          (unsigned int)WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids,
          (_DWORD)a2,
          (__int64)(a1 + 1));
        v21 = WPP_GLOBAL_Control;
      }
      if ( v21 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v21[1].Blink) & 0x2000) != 0
        && BYTE1(v21[1].Blink) >= 5u )
      {
        WPP_SF_q(v21[1].Flink, 156, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, a1[58]);
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
    WPP_SF_d(v24[1].Flink, v25, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, 617);
    return 617;
  }
  if ( a2 != (void *)-1LL && *((_DWORD *)a1 + 7) == 3 )
  {
    if ( v21 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v21[1].Blink) & 0x2000) != 0
      && BYTE1(v21[1].Blink) >= 5u )
    {
      WPP_SF_s(v21[1].Flink, 158, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, a1 + 1);
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
    WPP_SF_d(v26[1].Flink, v27, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, 600);
    return 600;
  }
  if ( *((_DWORD *)a1 + 7) == 4 )
  {
    a1[58] = a2;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
    {
      WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 160, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, *a1);
    }
    CompleteDisconnectRequest(a1);
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 161, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, 0);
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
      WPP_SF_q(v21[1].Flink, 162, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, *a1);
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
      WPP_SF_qD(WPP_GLOBAL_Control[1].Flink, 163, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, *a1, v31);
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
      WPP_SF_dq(WPP_GLOBAL_Control[1].Flink, 164, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, dwErrorCode, *a1);
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
      WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 165, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, *a1);
    }
    SignalPortDisconnect(a1, 0);
    EnterCriticalSection(&g_csConnectionNotifierList);
    SignalNotifiers(pConnectionNotifierList, 2);
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
      WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 167, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, *a1);
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
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 169, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v45);
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
      WPP_SF_s(v41[1].Flink, 170, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, a1 + 1);
    }
    v41 = WPP_GLOBAL_Control;
LABEL_247:
    if ( !*((_DWORD *)a1 + 268) )
      goto LABEL_215;
    if ( v41 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v41[1].Blink) & 0x2000) != 0
      && BYTE1(v41[1].Blink) >= 5u )
    {
      WPP_SF_q(v41[1].Flink, 171, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, *a1);
    }
    CurrentProcessId = GetCurrentProcessId();
    LOBYTE(v47) = 1;
    PortClose(a1, CurrentProcessId, v47, 0);
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
    WPP_SF_d(v41[1].Flink, 172, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, dwErrorCode);
  }
  return dwErrorCode;
}

```

## disassembly

```asm
0x180039ea0  push    rbp
0x180039ea2  push    rbx
0x180039ea3  push    rsi
0x180039ea4  push    rdi
0x180039ea5  push    r12
0x180039ea7  push    r13
0x180039ea9  push    r14
0x180039eab  push    r15
0x180039ead  lea     rbp, [rsp-1Fh]
0x180039eb2  sub     rsp, 0F8h
0x180039eb9  mov     r15d, r8d
0x180039ebc  mov     r14, rdx
0x180039ebf  mov     rdi, rcx
0x180039ec2  mov     rbx, cs:WPP_GLOBAL_Control
0x180039ec9  lea     rsi, WPP_GLOBAL_Control
0x180039ed0  mov     r13d, 2000h
0x180039ed6  cmp     rbx, rsi
0x180039ed9  jz      short loc_180039F14
0x180039edb  test    [rbx+1Ch], r13d
0x180039edf  jz      short loc_180039F14
0x180039ee1  cmp     byte ptr [rbx+19h], 6
0x180039ee5  jb      short loc_180039F14
0x180039ee7  mov     rax, [rcx]
0x180039eea  lea     r9, [rcx+8]
0x180039eee  mov     rcx, [rbx+10h]
0x180039ef2  mov     edx, 89h
0x180039ef7  mov     [rsp+130h+dwErrorCode], r8d
0x180039efc  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x180039f03  mov     [rsp+130h+plpszSubStringArray], rax
0x180039f08  call    WPP_SF_sqD
0x180039f0d  mov     rbx, cs:WPP_GLOBAL_Control
0x180039f14  mov     r9, [rdi+428h]
0x180039f1b  xor     r12d, r12d
0x180039f1e  test    r9, r9
0x180039f21  jz      short loc_180039F6A
0x180039f23  test    byte ptr [r9+70h], 10h
0x180039f28  jz      short loc_180039F6A
0x180039f2a  cmp     rbx, rsi
0x180039f2d  jz      short loc_180039F54
0x180039f2f  test    [rbx+1Ch], r13d
0x180039f33  jz      short loc_180039F54
0x180039f35  cmp     byte ptr [rbx+19h], 5
0x180039f39  jb      short loc_180039F54
0x180039f3b  mov     r9, [r9+10h]
0x180039f3f  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x180039f46  mov     rcx, [rbx+10h]
0x180039f4a  mov     edx, 8Ah
0x180039f4f  call    WPP_SF_q
0x180039f54  mov     rcx, [rdi+428h]
0x180039f5b  mov     rdx, rdi
0x180039f5e  call    CheckAndInitiateProtocolRenegotiation
0x180039f63  mov     rbx, cs:WPP_GLOBAL_Control
0x180039f6a  cmp     dword ptr [rdi+1Ch], 1
0x180039f6e  jnz     short loc_180039FA0
0x180039f70  cmp     rbx, rsi
0x180039f73  jz      short loc_180039FA0
0x180039f75  test    [rbx+1Ch], r13d
0x180039f79  jz      short loc_180039FA0
0x180039f7b  cmp     byte ptr [rbx+19h], 5
0x180039f7f  jb      short loc_180039FA0
0x180039f81  mov     r9, [rdi]
0x180039f84  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x180039f8b  mov     rcx, [rbx+10h]
0x180039f8f  mov     edx, 8Bh
0x180039f94  call    WPP_SF_q
0x180039f99  mov     rbx, cs:WPP_GLOBAL_Control
0x180039fa0  cmp     dword ptr [rdi+1Ch], 2
0x180039fa4  jnz     loc_18003A149
0x180039faa  cmp     rbx, rsi
0x180039fad  jz      short loc_180039FDA
0x180039faf  test    [rbx+1Ch], r13d
0x180039fb3  jz      short loc_180039FDA
0x180039fb5  cmp     byte ptr [rbx+19h], 5
0x180039fb9  jb      short loc_180039FDA
0x180039fbb  mov     r9, [rdi]
0x180039fbe  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x180039fc5  mov     rcx, [rbx+10h]
0x180039fc9  mov     edx, 8Ch
0x180039fce  call    WPP_SF_q
0x180039fd3  mov     rbx, cs:WPP_GLOBAL_Control
0x180039fda  xor     edx, edx; Val
0x180039fdc  lea     rcx, [rsp+130h+var_E0]; void *
0x180039fe1  mov     r8d, 9Ch; Size
0x180039fe7  call    memset_0
0x180039fec  cmp     rbx, rsi
0x180039fef  jz      short loc_18003A016
0x180039ff1  test    [rbx+1Ch], r13d
0x180039ff5  jz      short loc_18003A016
0x180039ff7  cmp     byte ptr [rbx+19h], 5
0x180039ffb  jb      short loc_18003A016
0x180039ffd  mov     rcx, [rbx+10h]
0x18003a001  lea     r9, [rdi+8]
0x18003a005  mov     edx, 8Dh
0x18003a00a  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003a011  call    WPP_SF_s
0x18003a016  lea     rdx, [rsp+130h+var_E0]
0x18003a01b  mov     rcx, rdi
0x18003a01e  call    GetBundleStatisticsFromNdisWan
0x18003a023  movaps  xmm0, [rsp+130h+var_E0]
0x18003a028  movaps  xmm1, [rbp+57h+var_D0]
0x18003a02c  mov     rsi, [rdi+428h]
0x18003a033  movups  xmmword ptr [rdi+240h], xmm0
0x18003a03a  movaps  xmm0, [rbp+57h+var_C0]
0x18003a03e  movups  xmmword ptr [rdi+250h], xmm1
0x18003a045  movaps  xmm1, [rbp+57h+var_B0]
0x18003a049  movups  xmmword ptr [rdi+260h], xmm0
0x18003a050  movaps  xmm0, [rbp+57h+var_A0]
0x18003a054  movups  xmmword ptr [rdi+270h], xmm1
0x18003a05b  movaps  xmm1, [rbp+57h+var_90]
0x18003a05f  movups  xmmword ptr [rdi+280h], xmm0
0x18003a066  movaps  xmm0, [rbp+57h+var_80]
0x18003a06a  movups  xmmword ptr [rdi+290h], xmm1
0x18003a071  movaps  xmm1, [rbp+57h+var_70]
0x18003a075  movups  xmmword ptr [rdi+2A0h], xmm0
0x18003a07c  movaps  xmm0, [rbp+57h+var_60]
0x18003a080  movups  xmmword ptr [rdi+2B0h], xmm1
0x18003a087  movups  xmm1, [rbp+57h+var_60+0Ch]
0x18003a08b  movups  xmmword ptr [rdi+2C0h], xmm0
0x18003a092  movups  xmmword ptr [rdi+2CCh], xmm1
0x18003a099  test    rsi, rsi
0x18003a09c  jz      loc_18003A13B
0x18003a0a2  cmp     dword ptr [rsi+44h], 1
0x18003a0a6  jnz     loc_18003A13B
0x18003a0ac  mov     ebx, [rsi+8Ch]
0x18003a0b2  call    cs:__imp_GetCurrentProcessId
0x18003a0b8  cmp     ebx, eax
0x18003a0ba  jnz     short loc_18003A0C5
0x18003a0bc  cmp     dword ptr [rsi+35Ch], 2
0x18003a0c3  jnz     short loc_18003A13B
0x18003a0c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a0cc  lea     rsi, WPP_GLOBAL_Control
0x18003a0d3  cmp     rcx, rsi
0x18003a0d6  jz      short loc_18003A0F9
0x18003a0d8  test    [rcx+1Ch], r13d
0x18003a0dc  jz      short loc_18003A0F9
0x18003a0de  cmp     byte ptr [rcx+19h], 5
0x18003a0e2  jb      short loc_18003A0F9
0x18003a0e4  mov     rcx, [rcx+10h]
0x18003a0e8  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003a0ef  mov     edx, 8Eh
0x18003a0f4  call    WPP_SF_
0x18003a0f9  mov     rcx, [rdi+428h]
0x18003a100  call    RevertPostConnectionActions
0x18003a105  test    eax, eax
0x18003a107  jz      short loc_18003A142
0x18003a109  mov     rbx, cs:WPP_GLOBAL_Control
0x18003a110  cmp     rbx, rsi
0x18003a113  jz      short loc_18003A149
0x18003a115  test    [rbx+1Ch], r13d
0x18003a119  jz      short loc_18003A149
0x18003a11b  cmp     byte ptr [rbx+19h], 2
0x18003a11f  jb      short loc_18003A149
0x18003a121  mov     rcx, [rbx+10h]
0x18003a125  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003a12c  mov     edx, 8Fh
0x18003a131  mov     r9d, eax
0x18003a134  call    WPP_SF_d
0x18003a139  jmp     short loc_18003A142
0x18003a13b  lea     rsi, WPP_GLOBAL_Control
0x18003a142  mov     rbx, cs:WPP_GLOBAL_Control
0x18003a149  mov     rcx, [rdi+428h]
0x18003a150  test    rcx, rcx
0x18003a153  jz      short loc_18003A189
0x18003a155  mov     dword ptr [rbp+57h+arg_0], r12d
0x18003a159  test    byte ptr [rcx+70h], 8
0x18003a15d  jz      loc_18003A2BE
0x18003a163  cmp     rbx, rsi
0x18003a166  jz      short loc_18003A189
0x18003a168  test    [rbx+1Ch], r13d
0x18003a16c  jz      short loc_18003A189
0x18003a16e  cmp     byte ptr [rbx+19h], 5
0x18003a172  jb      short loc_18003A189
0x18003a174  mov     rcx, [rbx+10h]
0x18003a178  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003a17f  mov     edx, 90h
0x18003a184  call    WPP_SF_
0x18003a189  mov     rcx, rdi
0x18003a18c  call    UnmapEndPoint
0x18003a191  mov     rax, [rdi+0D8h]
0x18003a198  mov     [rdi+0E0h], rax
0x18003a19f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a1a6  lea     rbx, WPP_GLOBAL_Control
0x18003a1ad  cmp     rcx, rbx
0x18003a1b0  jz      short loc_18003A1DE
0x18003a1b2  test    [rcx+1Ch], r13d
0x18003a1b6  jz      short loc_18003A1DE
0x18003a1b8  cmp     byte ptr [rcx+19h], 5
0x18003a1bc  jb      short loc_18003A1DE
0x18003a1be  mov     r9d, [rdi+1Ch]
0x18003a1c2  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003a1c9  mov     rcx, [rcx+10h]
0x18003a1cd  mov     edx, 95h
0x18003a1d2  call    WPP_SF_d
0x18003a1d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a1de  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003a1e2  test    r15d, r15d
0x18003a1e5  jnz     loc_18003A445
0x18003a1eb  cmp     dword ptr [rdi+1Ch], 3
0x18003a1ef  jz      loc_18003A48C
0x18003a1f5  cmp     rcx, rbx
0x18003a1f8  jz      short loc_18003A222
0x18003a1fa  test    [rcx+1Ch], r13d
0x18003a1fe  jz      short loc_18003A222
0x18003a200  cmp     byte ptr [rcx+19h], 5
0x18003a204  jb      short loc_18003A222
0x18003a206  mov     rcx, [rcx+10h]
0x18003a20a  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003a211  mov     edx, 96h
0x18003a216  call    WPP_SF_
0x18003a21b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a222  cmp     dword ptr [rdi+1Ch], 2
0x18003a226  jnz     loc_18003A3C1
0x18003a22c  cmp     [rdi+210h], r12
0x18003a233  jz      loc_18003A48C
0x18003a239  mov     eax, [rdi+108h]
0x18003a23f  test    eax, eax
0x18003a241  jz      short loc_18003A24A
0x18003a243  cmp     eax, 258h
0x18003a248  jnz     short loc_18003A254
0x18003a24a  mov     dword ptr [rdi+108h], 26Bh
0x18003a254  mov     rcx, rdi
0x18003a257  call    CompleteAsyncRequest
0x18003a25c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a263  cmp     rcx, rbx
0x18003a266  jz      short loc_18003A28C
0x18003a268  test    [rcx+1Ch], r13d
0x18003a26c  jz      short loc_18003A28C
0x18003a26e  cmp     byte ptr [rcx+19h], 5
0x18003a272  jb      short loc_18003A28C
0x18003a274  mov     r9, [rdi]
0x18003a277  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003a27e  mov     rcx, [rcx+10h]
0x18003a282  mov     edx, 97h
0x18003a287  call    WPP_SF_q
0x18003a28c  mov     rcx, [rdi+1D0h]; hObject
0x18003a293  call    FreeNotifierHandle
0x18003a298  test    byte ptr [rdi+4C8h], 1
0x18003a29f  mov     [rdi+1D0h], rsi
0x18003a2a6  jz      loc_18003A3AD
0x18003a2ac  mov     rcx, [rdi+210h]; hMem
0x18003a2b3  call    cs:__imp_LocalFree
0x18003a2b9  jmp     loc_18003A3B5
0x18003a2be  test    byte ptr [rcx+70h], 4
0x18003a2c2  jz      short loc_18003A332
0x18003a2c4  cmp     rbx, rsi
0x18003a2c7  jz      short loc_18003A2EA
0x18003a2c9  test    [rbx+1Ch], r13d
0x18003a2cd  jz      short loc_18003A2EA
0x18003a2cf  cmp     byte ptr [rbx+19h], 5
0x18003a2d3  jb      short loc_18003A2EA
0x18003a2d5  mov     rcx, [rbx+10h]
0x18003a2d9  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003a2e0  mov     edx, 91h
0x18003a2e5  call    WPP_SF_
0x18003a2ea  mov     ebx, 269h
0x18003a2ef  xor     r8d, r8d
0x18003a2f2  mov     edx, ebx
0x18003a2f4  mov     rcx, rdi
0x18003a2f7  call    TelemetryEventWriteStateChange
0x18003a2fc  mov     rcx, r14; hObject
0x18003a2ff  call    FreeNotifierHandle
0x18003a304  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a30b  cmp     rcx, rsi
0x18003a30e  jz      loc_18003A5CB
0x18003a314  test    [rcx+1Ch], r13d
0x18003a318  jz      loc_18003A5CB
0x18003a31e  cmp     byte ptr [rcx+19h], 6
0x18003a322  jb      loc_18003A5CB
0x18003a328  mov     edx, 92h
0x18003a32d  jmp     loc_18003A5B8
0x18003a332  lea     r8, [rbp+57h+arg_0]
0x18003a336  mov     rdx, r14
0x18003a339  call    QueueCloseConnections
0x18003a33e  cmp     dword ptr [rbp+57h+arg_0], r12d
0x18003a342  jz      loc_18003A189
0x18003a348  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a34f  cmp     rcx, rsi
0x18003a352  jz      loc_18003AA1D
0x18003a358  test    [rcx+1Ch], r13d
0x18003a35c  jz      short loc_18003A380
0x18003a35e  cmp     byte ptr [rcx+19h], 5
0x18003a362  jb      short loc_18003A380
0x18003a364  mov     rcx, [rcx+10h]
0x18003a368  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003a36f  mov     edx, 93h
0x18003a374  call    WPP_SF_
0x18003a379  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a380  cmp     rcx, rsi
0x18003a383  jz      loc_18003AA1D
0x18003a389  test    [rcx+1Ch], r13d
0x18003a38d  jz      loc_18003AA1D
0x18003a393  cmp     byte ptr [rcx+19h], 6
0x18003a397  jb      loc_18003AA1D
0x18003a39d  mov     edx, 94h
0x18003a3a2  mov     r9d, 258h
0x18003a3a8  jmp     loc_18003AA0D
0x18003a3ad  mov     rcx, rdi
0x18003a3b0  call    SendDisconnectNotificationToProtcolEngine
0x18003a3b5  mov     [rdi+210h], r12
0x18003a3bc  jmp     loc_18003A485
  ... truncated ...
```
