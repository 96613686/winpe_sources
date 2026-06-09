# PortClose

- ea: `0x1800210e0`
- end: `0x180021ad5`
- name: `PortClose`
- size: `2549`
- prototype: ``
- caller_count: `7`
- callee_count: `29`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180014a40`
- `0x180016500`
- `0x180018230`
- `0x180021ae0`
- `0x18002b3d0`
- `0x18003bba4`
- `0x1800510cc`

## callees

- `0x180005418`
- `0x180005bcc`
- `0x180005bfc`
- `0x180005cf8`
- `0x18000bd88`
- `0x18000c3c0`
- `0x18000c424`
- `0x1800210e0`
- `0x18003372c`
- `0x180033e78`
- `0x180034114`
- `0x180035a08`
- `0x18003b900`
- `0x180041354`
- `0x18004140c`
- `0x180047110`
- `0x180047954`
- `0x18004946c`
- `0x180049944`
- `0x1800499f0`
- `0x18004a7cc`
- `0x18004a89c`
- `0x18004aa34`
- `0x18004c9a4`
- `0x180080824`
- `0x1800a2978`
- `0x1800aa18c`
- `0x1800aa594`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180021138`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002181d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180021138`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002181d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800215da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021948`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800215da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021948`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180021935`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180021935`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021714`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021714`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021738`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021738`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021538`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800215ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002184a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021864`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002187e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021538`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800215ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002184a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021864`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002187e`

## string_xrefs

- `0x18002138a`: `PortClose: Attempt to close server port was denied`
- `0x1800212ef`: `PortClose: Access was denied`

## pseudocode

```c
__int64 __fastcall PortClose(_QWORD *a1, unsigned int a2, char a3, char a4)
{
  DWORD CurrentProcessId; // edi
  struct _LIST_ENTRY *v9; // rcx
  struct _LIST_ENTRY *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rax
  struct _LIST_ENTRY *v14; // rcx
  __int64 v15; // rdx
  bool v16; // r13
  int v17; // eax
  void *v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rdi
  void *v24; // rcx
  void *v25; // rcx
  void *v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  unsigned int v29; // ebx
  unsigned int i; // edi
  unsigned int v31; // eax
  unsigned int v32; // eax

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 148, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
  }
  CurrentProcessId = GetCurrentProcessId();
  if ( a1 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control[1].Flink,
        151,
        WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
        *a1,
        *((unsigned __int16 *)a1 + 22));
      v11 = WPP_GLOBAL_Control;
    }
    if ( *((_DWORD *)a1 + 7) == 3 && *((_DWORD *)a1 + 118) == 9 )
    {
      if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v11[1].Blink) & 0x2000) != 0
        && BYTE1(v11[1].Blink) >= 4u )
      {
        WPP_SF_s(v11[1].Flink, 152, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, a1 + 1);
      }
      *((_DWORD *)a1 + 268) = 1;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 6u )
      {
        return 0;
      }
      v12 = 153;
LABEL_165:
      WPP_SF_d(v11[1].Flink, v12, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, 0);
      return 0;
    }
    if ( *((_DWORD *)a1 + 6) == 1 )
    {
      if ( v11 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(v11[1].Blink) & 0x2000) == 0
        || BYTE1(v11[1].Blink) < 6u )
      {
        return 0;
      }
      v12 = 154;
      goto LABEL_165;
    }
    if ( *((_DWORD *)a1 + 68) == CurrentProcessId && a2 != CurrentProcessId )
    {
      v13 = a1[133];
      if ( v13 )
      {
        if ( (unsigned int)IsRouterPhonebook((LPCWSTR)(v13 + 184)) )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 155, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
          }
          TelemetryEventWriteStateChange(a1, 5, "PortClose: Access was denied");
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 6u )
          {
            return 5;
          }
          v15 = 156;
LABEL_58:
          WPP_SF_d(v14[1].Flink, v15, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, 5);
          return 5;
        }
        v11 = WPP_GLOBAL_Control;
      }
    }
    if ( *((_WORD *)a1 + 22) == 1 && CurrentProcessId == *((_DWORD *)a1 + 115) && !a4 )
    {
      if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v11[1].Blink) & 0x2000) != 0
        && BYTE1(v11[1].Blink) >= 2u )
      {
        WPP_SF_d(v11[1].Flink, 157, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, a2);
      }
      TelemetryEventWriteStateChange(a1, 5, "PortClose: Attempt to close server port was denied");
      *((_DWORD *)a1 + 306) &= 0xFFFFFFF3;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 6u )
      {
        return 5;
      }
      v15 = 158;
      goto LABEL_58;
    }
    v16 = a2 == *((_DWORD *)a1 + 68);
    if ( *((_WORD *)a1 + 22) == 2
      && *((_DWORD *)a1 + 115) == a2
      && !*((_DWORD *)a1 + 67)
      && v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v11[1].Blink) & 0x2000) != 0
      && BYTE1(v11[1].Blink) >= 2u )
    {
      WPP_SF_s(v11[1].Flink, 159, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, a1 + 1);
      v11 = WPP_GLOBAL_Control;
    }
    if ( *((_DWORD *)a1 + 118) && *((_DWORD *)a1 + 7) != 3 )
    {
      v17 = *((_DWORD *)a1 + 66);
      if ( !v17 || v17 == 600 )
        *((_DWORD *)a1 + 66) = 619;
      CompleteAsyncRequest(a1);
      v11 = WPP_GLOBAL_Control;
    }
    if ( a1[143] )
    {
      if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v11[1].Blink) & 0x2000) != 0
        && BYTE1(v11[1].Blink) >= 4u )
      {
        WPP_SF_(v11[1].Flink, 160, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
      }
      SetDialMachineEventHandleCommon(a1, a1[143], *((unsigned int *)a1 + 290), 0, 0, 0, 0, 0, a1[144]);
      v11 = WPP_GLOBAL_Control;
    }
    if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v11[1].Blink) & 0x2000) != 0
      && BYTE1(v11[1].Blink) >= 4u )
    {
      WPP_SF_q(v11[1].Flink, 161, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, *a1);
    }
    FreeNotifierList(a1 + 53);
    v18 = (void *)a1[70];
    if ( v18 )
    {
      LocalFree(v18);
      a1[70] = 0;
      *((_DWORD *)a1 + 142) = 0;
    }
    if ( !a4 && *(_WORD *)(a1[154] + 96LL) == 9 )
    {
      v19 = DisableClientIpSecFilter(a1);
      if ( v19
        && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_sd(
          WPP_GLOBAL_Control[1].Flink,
          162,
          (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
          (_DWORD)a1 + 8,
          v19);
      }
      FreeIkeInitiateContext((HLOCAL)a1[162]);
      a1[162] = 0;
    }
    v20 = a1[163];
    if ( v20 )
    {
      CloseHandle(*(HANDLE *)(v20 + 8));
      LocalFree((HLOCAL)a1[163]);
      a1[163] = 0;
    }
    FreeUserData(a1 + 135);
    *((_DWORD *)a1 + 68) = 0;
    --*((_WORD *)a1 + 22);
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control[1].Flink,
        163,
        WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
        *a1,
        *((unsigned __int16 *)a1 + 22));
    }
    *((_DWORD *)a1 + 8) &= ~4u;
    if ( !*((_WORD *)a1 + 22) || *((_DWORD *)a1 + 6) == 2 || (a1[153] & 8) != 0 )
    {
      if ( *((_DWORD *)a1 + 7) != 4 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
        {
          WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 164, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, *a1);
        }
        SignalPortDisconnect(a1, 0);
        EnterCriticalSection(&g_csConnectionNotifierList);
        SignalNotifiers(pConnectionNotifierList, 2, 0);
        LeaveCriticalSection(&g_csConnectionNotifierList);
      }
      if ( (a3 || *((_DWORD *)a1 + 6) == 2)
        && ((*(void (__fastcall **)(_QWORD))(a1[6] + 32LL))(a1[27]), *((_DWORD *)a1 + 6) == 2) )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
        {
          WPP_SF_sq(
            WPP_GLOBAL_Control[1].Flink,
            165,
            (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
            (_DWORD)a1 + 8,
            *a1);
        }
        RemovePort(*a1);
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 166, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
        }
      }
      else
      {
        SetPortAsyncReqType("onecoreuap\\net\\rras\\ras\\rasman\\rasman\\request.c", 3190, a1, 0);
        SetPortConnState(v22, v21, a1, 4);
        *((_DWORD *)a1 + 130) = 0;
        *((_DWORD *)a1 + 6) = 1;
        *((_DWORD *)a1 + 143) = 0;
      }
    }
    else
    {
      a1[70] = a1[56];
      *((_DWORD *)a1 + 142) = *((_DWORD *)a1 + 114);
      if ( !a3 )
        (*(void (__fastcall **)(_QWORD *, _QWORD *, HANDLE, _QWORD))(a1[6] + 24LL))(
          a1 + 1,
          a1 + 27,
          hIoCompletionPort,
          *(unsigned int *)a1);
      RePostListenOnBiplexPort(a1);
    }
    if ( a2 == GetCurrentProcessId() )
      *((_DWORD *)a1 + 306) &= ~8u;
    v23 = a1[133];
    v24 = (void *)a1[150];
    a1[133] = 0;
    LocalFree(v24);
    v25 = (void *)a1[151];
    a1[150] = 0;
    LocalFree(v25);
    v26 = (void *)a1[152];
    a1[151] = 0;
    LocalFree(v26);
    a1[152] = 0;
    a1[157] = 0;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 167, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, *a1);
    }
    v28 = a1[160];
    *((_DWORD *)a1 + 306) &= 0xFFFFFFEB;
    *((_DWORD *)a1 + 10) = 0;
    a1[159] = 0;
    *((_DWORD *)a1 + 329) = 0;
    if ( (unsigned __int64)(v28 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
      {
        WPP_SF_qs(
          WPP_GLOBAL_Control[1].Flink,
          168,
          (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
          v28,
          (__int64)(a1 + 1));
      }
      SetEvent((HANDLE)a1[160]);
      CloseHandle((HANDLE)a1[160]);
    }
    LOBYTE(v27) = v16;
    a1[160] = -1;
    RemoveConnectionPort(a1, v23, v27);
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 169, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, *a1);
    }
    *((_DWORD *)a1 + 268) = 0;
    if ( *((_DWORD *)a1 + 316) )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
      {
        WPP_SF_sq(
          WPP_GLOBAL_Control[1].Flink,
          170,
          (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
          (_DWORD)a1 + 8,
          a1[30]);
      }
      a1[30] = 0;
      *((_DWORD *)a1 + 316) = 0;
    }
    if ( !(unsigned int)fAnyConnectedPorts() )
    {
      SetRasmanServiceStopControl(1);
      v29 = 0;
      for ( i = 1; i < 6; ++i )
      {
        v31 = DisableAutoWPPTracingForSubComponent(i);
        if ( v31 )
          v29 = v31;
      }
      if ( v29
        && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 171, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v29);
      }
      v32 = DisableAutoTracing();
      if ( v32 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          return 0;
        if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          goto LABEL_161;
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 172, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v32);
      }
    }
    v11 = WPP_GLOBAL_Control;
LABEL_161:
    if ( v11 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(v11[1].Blink) & 0x2000) == 0
      || BYTE1(v11[1].Blink) < 6u )
    {
      return 0;
    }
    v12 = 173;
    goto LABEL_165;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 149, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v9 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v9[1].Blink) & 0x2000) != 0
      && BYTE1(v9[1].Blink) >= 6u )
    {
      WPP_SF_d(v9[1].Flink, 150, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, 615);
    }
  }
  return 615;
}

```

## disassembly

```asm
0x1800210e0  push    rbx
0x1800210e2  push    rbp
0x1800210e3  push    rsi
0x1800210e4  push    rdi
0x1800210e5  push    r12
0x1800210e7  push    r13
0x1800210e9  push    r14
0x1800210eb  push    r15
0x1800210ed  sub     rsp, 58h
0x1800210f1  mov     r14b, r9b
0x1800210f4  mov     r12b, r8b
0x1800210f7  mov     r15d, edx
0x1800210fa  mov     rbx, rcx
0x1800210fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180021104  lea     r13, WPP_GLOBAL_Control
0x18002110b  lea     rbp, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180021112  mov     esi, 2000h
0x180021117  cmp     rcx, r13
0x18002111a  jz      short loc_180021138
0x18002111c  test    [rcx+1Ch], esi
0x18002111f  jz      short loc_180021138
0x180021121  cmp     byte ptr [rcx+19h], 6
0x180021125  jb      short loc_180021138
0x180021127  mov     rcx, [rcx+10h]
0x18002112b  mov     edx, 94h
0x180021130  mov     r8, rbp
0x180021133  call    WPP_SF_
0x180021138  call    cs:__imp_GetCurrentProcessId
0x18002113f  nop     dword ptr [rax+rax+00h]
0x180021144  mov     edi, eax
0x180021146  test    rbx, rbx
0x180021149  jnz     short loc_1800211B4
0x18002114b  mov     rcx, cs:WPP_GLOBAL_Control
0x180021152  mov     ebx, 267h
0x180021157  cmp     rcx, r13
0x18002115a  jz      short loc_1800211AD
0x18002115c  test    [rcx+1Ch], esi
0x18002115f  jz      short loc_180021189
0x180021161  mov     esi, 2
0x180021166  cmp     [rcx+19h], sil
0x18002116a  jb      short loc_180021184
0x18002116c  mov     rcx, [rcx+10h]
0x180021170  mov     edx, 95h
0x180021175  mov     r8, rbp
0x180021178  call    WPP_SF_
0x18002117d  mov     rcx, cs:WPP_GLOBAL_Control
0x180021184  mov     esi, 2000h
0x180021189  cmp     rcx, r13
0x18002118c  jz      short loc_1800211AD
0x18002118e  test    [rcx+1Ch], esi
0x180021191  jz      short loc_1800211AD
0x180021193  cmp     byte ptr [rcx+19h], 6
0x180021197  jb      short loc_1800211AD
0x180021199  mov     rcx, [rcx+10h]
0x18002119d  mov     edx, 96h
0x1800211a2  mov     r9d, ebx
0x1800211a5  mov     r8, rbp
0x1800211a8  call    WPP_SF_d
0x1800211ad  mov     eax, ebx
0x1800211af  jmp     loc_180021AC3
0x1800211b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800211bb  cmp     rcx, r13
0x1800211be  jz      short loc_1800211EE
0x1800211c0  test    [rcx+1Ch], esi
0x1800211c3  jz      short loc_1800211EE
0x1800211c5  cmp     byte ptr [rcx+19h], 4
0x1800211c9  jb      short loc_1800211EE
0x1800211cb  movzx   eax, word ptr [rbx+2Ch]
0x1800211cf  mov     edx, 97h
0x1800211d4  mov     r9, [rbx]
0x1800211d7  mov     r8, rbp
0x1800211da  mov     rcx, [rcx+10h]
0x1800211de  mov     dword ptr [rsp+98h+var_78], eax
0x1800211e2  call    WPP_SF_qD
0x1800211e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800211ee  cmp     dword ptr [rbx+1Ch], 3
0x1800211f2  jnz     short loc_180021259
0x1800211f4  cmp     dword ptr [rbx+1D8h], 9
0x1800211fb  jnz     short loc_180021259
0x1800211fd  cmp     rcx, r13
0x180021200  jz      short loc_180021222
0x180021202  test    [rcx+1Ch], esi
0x180021205  jz      short loc_180021222
0x180021207  cmp     byte ptr [rcx+19h], 4
0x18002120b  jb      short loc_180021222
0x18002120d  mov     rcx, [rcx+10h]
0x180021211  lea     r9, [rbx+8]
0x180021215  mov     edx, 98h
0x18002121a  mov     r8, rbp
0x18002121d  call    WPP_SF_s
0x180021222  mov     dword ptr [rbx+430h], 1
0x18002122c  mov     rcx, cs:WPP_GLOBAL_Control
0x180021233  cmp     rcx, r13
0x180021236  jz      loc_180021AC1
0x18002123c  test    [rcx+1Ch], esi
0x18002123f  jz      loc_180021AC1
0x180021245  cmp     byte ptr [rcx+19h], 6
0x180021249  jb      loc_180021AC1
0x18002124f  mov     edx, 99h
0x180021254  jmp     loc_180021AAE
0x180021259  mov     ebp, 1
0x18002125e  cmp     [rbx+18h], ebp
0x180021261  jnz     short loc_180021289
0x180021263  cmp     rcx, r13
0x180021266  jz      loc_180021AC1
0x18002126c  test    [rcx+1Ch], esi
0x18002126f  jz      loc_180021AC1
0x180021275  cmp     byte ptr [rcx+19h], 6
0x180021279  jb      loc_180021AC1
0x18002127f  mov     edx, 9Ah
0x180021284  jmp     loc_180021AAE
0x180021289  cmp     [rbx+110h], edi
0x18002128f  jnz     loc_180021334
0x180021295  cmp     r15d, edi
0x180021298  jz      loc_180021334
0x18002129e  mov     rax, [rbx+428h]
0x1800212a5  test    rax, rax
0x1800212a8  jz      loc_180021334
0x1800212ae  lea     rcx, [rax+0B8h]; lpString
0x1800212b5  call    IsRouterPhonebook
0x1800212ba  test    eax, eax
0x1800212bc  jz      short loc_18002132D
0x1800212be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800212c5  cmp     rcx, r13
0x1800212c8  jz      short loc_1800212EA
0x1800212ca  test    [rcx+1Ch], esi
0x1800212cd  jz      short loc_1800212EA
0x1800212cf  cmp     byte ptr [rcx+19h], 4
0x1800212d3  jb      short loc_1800212EA
0x1800212d5  mov     rcx, [rcx+10h]
0x1800212d9  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x1800212e0  mov     edx, 9Bh
0x1800212e5  call    WPP_SF_
0x1800212ea  mov     edi, 5
0x1800212ef  lea     r8, aPortcloseAcces; "PortClose: Access was denied"
0x1800212f6  mov     edx, edi
0x1800212f8  mov     rcx, rbx
0x1800212fb  call    TelemetryEventWriteStateChange
0x180021300  mov     rcx, cs:WPP_GLOBAL_Control
0x180021307  cmp     rcx, r13
0x18002130a  jz      loc_1800213D1
0x180021310  test    [rcx+1Ch], esi
0x180021313  jz      loc_1800213D1
0x180021319  cmp     byte ptr [rcx+19h], 6
0x18002131d  jb      loc_1800213D1
0x180021323  mov     edx, 9Ch
0x180021328  jmp     loc_1800213BE
0x18002132d  mov     rcx, cs:WPP_GLOBAL_Control
0x180021334  cmp     [rbx+2Ch], bp
0x180021338  jnz     loc_1800213D8
0x18002133e  cmp     edi, [rbx+1CCh]
0x180021344  jnz     loc_1800213D8
0x18002134a  xor     edi, edi
0x18002134c  test    r14b, r14b
0x18002134f  jnz     loc_1800213DA
0x180021355  cmp     rcx, r13
0x180021358  jz      short loc_180021385
0x18002135a  test    [rcx+1Ch], esi
0x18002135d  jz      short loc_180021385
0x18002135f  lea     esi, [rdi+2]
0x180021362  cmp     [rcx+19h], sil
0x180021366  jb      short loc_180021380
0x180021368  mov     rcx, [rcx+10h]
0x18002136c  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180021373  mov     edx, 9Dh
0x180021378  mov     r9d, r15d
0x18002137b  call    WPP_SF_d
0x180021380  mov     esi, 2000h
0x180021385  mov     edi, 5
0x18002138a  lea     r8, aPortcloseAttem; "PortClose: Attempt to close server port"...
0x180021391  mov     edx, edi
0x180021393  mov     rcx, rbx
0x180021396  call    TelemetryEventWriteStateChange
0x18002139b  and     dword ptr [rbx+4C8h], 0FFFFFFF3h
0x1800213a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800213a9  cmp     rcx, r13
0x1800213ac  jz      short loc_1800213D1
0x1800213ae  test    [rcx+1Ch], esi
0x1800213b1  jz      short loc_1800213D1
0x1800213b3  cmp     byte ptr [rcx+19h], 6
0x1800213b7  jb      short loc_1800213D1
0x1800213b9  mov     edx, 9Eh
0x1800213be  mov     rcx, [rcx+10h]
0x1800213c2  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x1800213c9  mov     r9d, edi
0x1800213cc  call    WPP_SF_d
0x1800213d1  mov     eax, edi
0x1800213d3  jmp     loc_180021AC3
0x1800213d8  xor     edi, edi
0x1800213da  cmp     r15d, [rbx+110h]
0x1800213e1  mov     esi, 2
0x1800213e6  setz    r13b
0x1800213ea  cmp     [rbx+2Ch], si
0x1800213ee  jnz     short loc_18002143C
0x1800213f0  cmp     [rbx+1CCh], r15d
0x1800213f7  jnz     short loc_18002143C
0x1800213f9  cmp     [rbx+10Ch], edi
0x1800213ff  jnz     short loc_18002143C
0x180021401  lea     rdx, WPP_GLOBAL_Control
0x180021408  cmp     rcx, rdx
0x18002140b  jz      short loc_18002143C
0x18002140d  test    dword ptr [rcx+1Ch], 2000h
0x180021414  jz      short loc_18002143C
0x180021416  cmp     [rcx+19h], sil
0x18002141a  jb      short loc_18002143C
0x18002141c  mov     rcx, [rcx+10h]
0x180021420  lea     r9, [rbx+8]
0x180021424  mov     edx, 9Fh
0x180021429  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180021430  call    WPP_SF_s
0x180021435  mov     rcx, cs:WPP_GLOBAL_Control
0x18002143c  cmp     [rbx+1D8h], edi
0x180021442  jz      short loc_180021474
0x180021444  cmp     dword ptr [rbx+1Ch], 3
0x180021448  jz      short loc_180021474
0x18002144a  mov     eax, [rbx+108h]
0x180021450  test    eax, eax
0x180021452  jz      short loc_18002145B
0x180021454  cmp     eax, 258h
0x180021459  jnz     short loc_180021465
0x18002145b  mov     dword ptr [rbx+108h], 26Bh
0x180021465  mov     rcx, rbx
0x180021468  call    CompleteAsyncRequest
0x18002146d  mov     rcx, cs:WPP_GLOBAL_Control
0x180021474  cmp     [rbx+478h], rdi
0x18002147b  jz      short loc_1800214ED
0x18002147d  lea     rax, WPP_GLOBAL_Control
0x180021484  cmp     rcx, rax
0x180021487  jz      short loc_1800214AD
0x180021489  test    dword ptr [rcx+1Ch], 2000h
0x180021490  jz      short loc_1800214AD
0x180021492  cmp     byte ptr [rcx+19h], 4
0x180021496  jb      short loc_1800214AD
0x180021498  mov     rcx, [rcx+10h]
0x18002149c  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x1800214a3  mov     edx, 0A0h
0x1800214a8  call    WPP_SF_
0x1800214ad  mov     rax, [rbx+480h]
0x1800214b4  xor     r9d, r9d
0x1800214b7  mov     r8d, [rbx+488h]
0x1800214be  mov     rcx, rbx
0x1800214c1  mov     rdx, [rbx+478h]
0x1800214c8  mov     [rsp+98h+var_58], rax
0x1800214cd  mov     [rsp+98h+var_60], rdi
0x1800214d2  mov     [rsp+98h+var_68], rdi
0x1800214d7  mov     [rsp+98h+var_70], rdi
0x1800214dc  mov     [rsp+98h+var_78], rdi
0x1800214e1  call    SetDialMachineEventHandleCommon
0x1800214e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800214ed  lea     rax, WPP_GLOBAL_Control
0x1800214f4  cmp     rcx, rax
0x1800214f7  jz      short loc_180021520
0x1800214f9  test    dword ptr [rcx+1Ch], 2000h
0x180021500  jz      short loc_180021520
0x180021502  cmp     byte ptr [rcx+19h], 4
0x180021506  jb      short loc_180021520
0x180021508  mov     r9, [rbx]
0x18002150b  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180021512  mov     rcx, [rcx+10h]
0x180021516  mov     edx, 0A1h
0x18002151b  call    WPP_SF_q
0x180021520  lea     rcx, [rbx+1A8h]
0x180021527  call    FreeNotifierList
0x18002152c  mov     rcx, [rbx+230h]; hMem
0x180021533  test    rcx, rcx
0x180021536  jz      short loc_180021551
0x180021538  call    cs:__imp_LocalFree
0x18002153f  nop     dword ptr [rax+rax+00h]
0x180021544  mov     [rbx+230h], rdi
0x18002154b  mov     [rbx+238h], edi
0x180021551  test    r14b, r14b
0x180021554  jnz     short loc_1800215C7
0x180021556  mov     rax, [rbx+4D0h]
0x18002155d  cmp     word ptr [rax+60h], 9
0x180021562  jnz     short loc_1800215C7
0x180021564  mov     rcx, rbx
0x180021567  call    DisableClientIpSecFilter
0x18002156c  xor     r14d, r14d
0x18002156f  test    eax, eax
0x180021571  jz      short loc_1800215B2
0x180021573  mov     rcx, cs:WPP_GLOBAL_Control
0x18002157a  lea     rdx, WPP_GLOBAL_Control
0x180021581  cmp     rcx, rdx
0x180021584  jz      short loc_1800215B2
0x180021586  test    dword ptr [rcx+1Ch], 2000h
0x18002158d  jz      short loc_1800215B2
0x18002158f  cmp     [rcx+19h], sil
0x180021593  jb      short loc_1800215B2
0x180021595  mov     rcx, [rcx+10h]
0x180021599  lea     r9, [rbx+8]
0x18002159d  mov     edx, 0A2h
0x1800215a2  mov     dword ptr [rsp+98h+var_78], eax
0x1800215a6  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x1800215ad  call    WPP_SF_sd
0x1800215b2  mov     rcx, [rbx+510h]; hMem
0x1800215b9  call    FreeIkeInitiateContext
0x1800215be  mov     [rbx+510h], r14
0x1800215c5  jmp     short loc_1800215CA
0x1800215c7  xor     r14d, r14d
0x1800215ca  mov     rcx, [rbx+518h]
  ... truncated ...
```
