# RasmanWorker

- ea: `0x18004eb50`
- end: `0x18004f79a`
- name: `RasmanWorker`
- size: `3146`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180028cd0`

## callees

- `0x1800056c8`
- `0x180005e0c`
- `0x180005e34`
- `0x180005f1c`
- `0x1800070c4`
- `0x18000bf70`
- `0x18000bfb0`
- `0x18000d160`
- `0x18001435c`
- `0x18002040c`
- `0x180032118`
- `0x180032508`
- `0x180032a98`
- `0x180032b0c`
- `0x180037988`
- `0x180039ea0`
- `0x18003ea70`
- `0x18004033c`
- `0x180047668`
- `0x180047714`
- `0x180048464`
- `0x18004852c`
- `0x180049ebc`
- `0x18004d22c`
- `0x18004d408`
- `0x18004da64`
- `0x18004eb50`
- `0x18004f7a0`
- `0x1800e9010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004f6a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004f6a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f463`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f463`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f483`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f483`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ed5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f73e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ed5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f73e`
- `rtutils!RouterLogEventA` at `0x18004f283`
- `rtutils!RouterLogEventA` at `0x18004f283`
- `WS2_32!__imp_inet_ntoa` at `0x18004f1c5`
- `WS2_32!__imp_inet_ntoa` at `0x18004f1c5`

## pseudocode

```c
__int64 __fastcall RasmanWorker(__int64 a1, __int64 a2)
{
  struct _LIST_ENTRY *v4; // rcx
  _QWORD *PortByHandle; // rbx
  int v6; // eax
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  unsigned int v13; // eax
  unsigned int v14; // eax
  __int64 v15; // rax
  void *v16; // rax
  unsigned int v17; // esi
  int v18; // r15d
  __int64 v19; // rdx
  __int64 v20; // r9
  int v21; // eax
  __int64 v22; // rax
  __m128i v23; // xmm6
  __int64 UserData; // rax
  LPSTR *plpszSubStringArray; // rax
  struct _LIST_ENTRY *v26; // rcx
  __int64 v27; // rdx
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // r9
  __int64 v34; // rdx
  HLOCAL *Connection; // rax
  __int64 v36; // r9
  unsigned int v37; // eax
  DWORD CurrentProcessId; // eax
  int v39; // eax
  int v40; // edx
  unsigned int v42; // [rsp+A8h] [rbp+48h] BYREF
  LPSTR v43; // [rsp+B0h] [rbp+50h] BYREF
  const CHAR *v44; // [rsp+B8h] [rbp+58h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 122, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v42 = 0;
  if ( RasmanShuttingDown )
    goto LABEL_237;
  if ( !a2 )
    goto LABEL_241;
  PortByHandle = (_QWORD *)GetPortByHandle(a1);
  if ( !PortByHandle )
  {
    v6 = *(_DWORD *)(a2 + 32);
    if ( ((v6 - 7) & 0xFFFFFFFC) != 0 || v6 == 9 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 3u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 123, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids, (unsigned int)a1);
LABEL_236:
        v4 = WPP_GLOBAL_Control;
      }
LABEL_237:
      if ( !a2 )
        goto LABEL_241;
      goto LABEL_238;
    }
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control[1].Flink,
      124,
      WPP_a45645adc1993df9b9f66dc87e784804_Traceguids,
      *(unsigned int *)(a2 + 32));
    v4 = WPP_GLOBAL_Control;
  }
  v7 = *(_DWORD *)(a2 + 32);
  if ( !v7 )
  {
    if ( v4 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(v4[1].Blink) & 0x2000) == 0
      || BYTE1(v4[1].Blink) < 5u )
    {
      goto LABEL_77;
    }
    v34 = 125;
    v33 = a2;
    goto LABEL_202;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v4[1].Blink) & 0x2000) != 0
      && BYTE1(v4[1].Blink) >= 5u )
    {
      WPP_SF_(v4[1].Flink, 126, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
    v42 = -1;
    if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v4[1].Blink) & 0x2000) != 0
      && BYTE1(v4[1].Blink) >= 5u )
    {
      WPP_SF_sq(
        v4[1].Flink,
        127,
        (unsigned int)WPP_a45645adc1993df9b9f66dc87e784804_Traceguids,
        (_DWORD)PortByHandle + 8,
        a2);
    }
    (*(void (__fastcall **)(_QWORD, unsigned int *))(PortByHandle[6] + 120LL))(PortByHandle[27], &v42);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 128, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids, v42);
      v4 = WPP_GLOBAL_Control;
    }
    if ( (v42 & 1) != 0 )
    {
      v17 = 2;
      v18 = 2;
      if ( v4 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        goto LABEL_159;
      if ( (HIDWORD(v4[1].Blink) & 0x2000) != 0 && BYTE1(v4[1].Blink) >= 2u )
      {
        v19 = 129;
LABEL_153:
        WPP_SF_(v4[1].Flink, v19, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids);
        v4 = WPP_GLOBAL_Control;
        goto LABEL_154;
      }
      goto LABEL_154;
    }
    v17 = 3;
    v18 = 3;
    if ( (v42 & 2) == 0 )
    {
      if ( v4 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        goto LABEL_77;
      if ( (HIDWORD(v4[1].Blink) & 0x2000) != 0 && BYTE1(v4[1].Blink) >= 5u )
      {
        v19 = 138;
        goto LABEL_153;
      }
LABEL_154:
      if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v4[1].Blink) & 0x2000) != 0
        && BYTE1(v4[1].Blink) >= 5u )
      {
        WPP_SF_ddd(
          v4[1].Flink,
          139,
          WPP_a45645adc1993df9b9f66dc87e784804_Traceguids,
          v17,
          v18,
          *((_DWORD *)PortByHandle + 7));
        v4 = WPP_GLOBAL_Control;
      }
      if ( v17 - 1 > 1 )
        goto LABEL_77;
LABEL_159:
      if ( (unsigned __int64)(PortByHandle[160] - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL && (PortByHandle[153] & 0x10) == 0 )
      {
        if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v4[1].Blink) & 0x2000) != 0
          && BYTE1(v4[1].Blink) >= 5u )
        {
          WPP_SF_s(v4[1].Flink, 140, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids, PortByHandle + 1);
          goto LABEL_29;
        }
        goto LABEL_77;
      }
      if ( *((_DWORD *)PortByHandle + 7) == 3 )
      {
        CompleteDisconnectRequest(PortByHandle);
        if ( PortByHandle[60] )
          RemoveTimeoutElement(PortByHandle);
        PortByHandle[60] = 0;
        goto LABEL_29;
      }
      if ( v17 != 2 && *((_DWORD *)PortByHandle + 7) == 4 )
        goto LABEL_77;
      if ( *((_DWORD *)PortByHandle + 118) )
      {
        v28 = *((_DWORD *)PortByHandle + 66);
        if ( !v28 || v28 == 600 )
        {
          *((_DWORD *)PortByHandle + 66) = 619;
          CompleteAsyncRequest(PortByHandle);
          v4 = WPP_GLOBAL_Control;
        }
      }
      if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v4[1].Blink) & 0x2000) != 0
        && BYTE1(v4[1].Blink) >= 5u )
      {
        WPP_SF_qqd(
          v4[1].Flink,
          141,
          WPP_a45645adc1993df9b9f66dc87e784804_Traceguids,
          *PortByHandle,
          PortByHandle[133],
          v17);
      }
      *((_DWORD *)PortByHandle + 331) = v18;
      DisconnectPort(PortByHandle, (void *)0xFFFFFFFFFFFFFFFFLL, v17);
      if ( *((_DWORD *)PortByHandle + 7) != 4 )
      {
        SignalPortDisconnect(PortByHandle, 0);
        EnterCriticalSection(&g_csConnectionNotifierList);
        SignalNotifiers(pConnectionNotifierList, 2);
        LeaveCriticalSection(&g_csConnectionNotifierList);
      }
      if ( *((_DWORD *)PortByHandle + 7) == 1 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
        {
          WPP_SF_s(WPP_GLOBAL_Control[1].Flink, 143, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids, PortByHandle + 1);
          goto LABEL_193;
        }
      }
      else
      {
        v31 = PortByHandle[133];
        if ( !v31 || (*(_BYTE *)(v31 + 112) & 4) == 0 )
        {
          SetPortConnState(v30, v29, PortByHandle, 4);
          SetPortAsyncReqType("onecoreuap\\net\\rras\\ras\\rasman\\rasman\\worker.c", 1409, PortByHandle, 0);
          goto LABEL_193;
        }
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
        {
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 142, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids);
LABEL_193:
          v4 = WPP_GLOBAL_Control;
        }
      }
      v32 = *((_DWORD *)PortByHandle + 66);
      if ( v32 && v32 != 600 )
        goto LABEL_77;
      if ( *((_DWORD *)PortByHandle + 7) != 1 )
      {
        *((_DWORD *)PortByHandle + 66) = 619;
        goto LABEL_29;
      }
      if ( v4 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(v4[1].Blink) & 0x2000) == 0
        || BYTE1(v4[1].Blink) < 5u )
      {
        goto LABEL_77;
      }
      v33 = *PortByHandle;
      v34 = 144;
LABEL_202:
      WPP_SF_q(v4[1].Flink, v34, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids, v33);
      goto LABEL_29;
    }
    if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v4[1].Blink) & 0x2000) != 0
      && BYTE1(v4[1].Blink) >= 2u )
    {
      WPP_SF_d(v4[1].Flink, 130, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids, *((unsigned int *)PortByHandle + 7));
      v4 = WPP_GLOBAL_Control;
    }
    v20 = *((unsigned int *)PortByHandle + 7);
    if ( (unsigned int)v20 > 5 || (v21 = 45, !_bittest(&v21, v20)) )
    {
      if ( (PortByHandle[153] & 1) == 0 )
        goto LABEL_154;
    }
    if ( (PortByHandle[153] & 1) != 0
      && v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v4[1].Blink) & 0x2000) != 0
      && BYTE1(v4[1].Blink) >= 5u )
    {
      WPP_SF_d(v4[1].Flink, 131, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids, v20);
      v4 = WPP_GLOBAL_Control;
    }
    if ( !*((_DWORD *)PortByHandle + 7) )
    {
      if ( v4 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(v4[1].Blink) & 0x2000) == 0
        || BYTE1(v4[1].Blink) < 5u )
      {
        goto LABEL_145;
      }
      WPP_SF_q(v4[1].Flink, 132, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids, *PortByHandle);
LABEL_144:
      v4 = WPP_GLOBAL_Control;
LABEL_145:
      v17 = 1;
      v18 = 4;
      if ( v4 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        goto LABEL_159;
      if ( (HIDWORD(v4[1].Blink) & 0x2000) == 0 || BYTE1(v4[1].Blink) < 2u )
        goto LABEL_154;
      v19 = 137;
      goto LABEL_153;
    }
    if ( *((_DWORD *)PortByHandle + 7) != 2 )
      goto LABEL_145;
    if ( (PortByHandle[4] & 1) == 0 )
      goto LABEL_145;
    if ( (PortByHandle[153] & 4) != 0 )
      goto LABEL_145;
    v22 = PortByHandle[154];
    if ( !v22 || *(_WORD *)(v22 + 96) != 8 )
      goto LABEL_145;
    v43 = 0;
    v23 = 0;
    if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v4[1].Blink) & 0x2000) != 0
      && BYTE1(v4[1].Blink) >= 5u )
    {
      WPP_SF_(v4[1].Flink, 133, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids);
    }
    UserData = GetUserData(PortByHandle + 135, 13);
    if ( UserData )
      v23 = *(__m128i *)(UserData + 24);
    if ( _mm_cvtsi128_si32(v23) == 1 )
    {
      v43 = inet_ntoa(*(struct in_addr *)((char *)v23.m128i_i64 + 4));
      if ( v43 )
      {
        plpszSubStringArray = &v43;
LABEL_143:
        RouterLogEventA(hLogEvents, 2u, 0x4EF1u, 1u, plpszSubStringArray, 0);
        goto LABEL_144;
      }
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 3u )
      {
LABEL_138:
        v44 = byte_1800F02BA;
        if ( v26 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v26[1].Blink) & 0x2000) != 0
          && BYTE1(v26[1].Blink) >= 3u )
        {
          WPP_SF_(v26[1].Flink, 136, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids);
        }
        plpszSubStringArray = (LPSTR *)&v44;
        goto LABEL_143;
      }
      v27 = 134;
    }
    else
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 3u )
      {
        goto LABEL_138;
      }
      v27 = 135;
    }
    WPP_SF_(v26[1].Flink, v27, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids);
    v26 = WPP_GLOBAL_Control;
    goto LABEL_138;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(v4[1].Blink) & 0x2000) != 0 && BYTE1(v4[1].Blink) >= 5u )
      {
        WPP_SF_(v4[1].Flink, 145, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids);
        v4 = WPP_GLOBAL_Control;
      }
      if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v4[1].Blink) & 0x2000) != 0
        && BYTE1(v4[1].Blink) >= 5u )
      {
        WPP_SF_sqD(
          v4[1].Flink,
          146,
          (unsigned int)WPP_a45645adc1993df9b9f66dc87e784804_Traceguids,
          (_DWORD)PortByHandle + 8,
          a2,
          *((_DWORD *)PortByHandle + 7));
        v4 = WPP_GLOBAL_Control;
      }
    }
    if ( *((_DWORD *)PortByHandle + 7) != 4 )
    {
      if ( (unsigned int)ServiceWorkRequest(PortByHandle) == 600 )
        goto LABEL_236;
      v4 = WPP_GLOBAL_Control;
    }
    goto LABEL_77;
  }
  v10 = v9 - 1;
  if ( v10 )
  {
    v11 = v10 - 4;
    if ( !v11 )
    {
      if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(v4[1].Blink) & 0x2000) != 0 && BYTE1(v4[1].Blink) >= 5u )
        {
          WPP_SF_(v4[1].Flink, 148, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids);
          v4 = WPP_GLOBAL_Control;
        }
        if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v4[1].Blink) & 0x2000) != 0
          && BYTE1(v4[1].Blink) >= 5u )
        {
          WPP_SF_q(v4[1].Flink, 149, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids, *(_QWORD *)(a2 + 40));
        }
      }
      DwProcessNewPortNotification(*(HLOCAL *)(a2 + 40));
      goto LABEL_29;
    }
    v12 = v11 - 1;
    if ( v12 )
    {
      if ( v12 == 2 )
      {
        if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v4[1].Blink) & 0x2000) != 0
          && BYTE1(v4[1].Blink) >= 5u )
        {
          WPP_SF_(v4[1].Flink, 153, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids);
        }
        v13 = DwProcessRasConfigChangeNotification(*(_QWORD *)(a2 + 40));
        if ( v13
          && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 154, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids, v13);
        }
        LocalFree(*(HLOCAL *)(a2 + 40));
        goto LABEL_29;
      }
      if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v4[1].Blink) & 0x2000) != 0
        && BYTE1(v4[1].Blink) >= 5u )
      {
        WPP_SF_(v4[1].Flink, 155, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids);
LABEL_29:
        v4 = WPP_GLOBAL_Control;
      }
    }
    else
    {
      if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(v4[1].Blink) & 0x2000) != 0 && BYTE1(v4[1].Blink) >= 5u )
        {
          WPP_SF_(v4[1].Flink, 150, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids);
          v4 = WPP_GLOBAL_Control;
        }
        if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v4[1].Blink) & 0x2000) != 0
          && BYTE1(v4[1].Blink) >= 5u )
        {
          WPP_SF_q(v4[1].Flink, 151, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids, *(_QWORD *)(a2 + 40));
        }
      }
      v14 = DwProcessLineRemoveNotification(*(HLOCAL *)(a2 + 40));
      if ( !v14 )
        goto LABEL_29;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 152, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids, v14);
        goto LABEL_29;
      }
    }
LABEL_77:
    if ( PortByHandle && (v15 = PortByHandle[133]) != 0 )
      v16 = *(void **)(v15 + 16);
    else
      v16 = 0;
    if ( *(_DWORD *)(a2 + 32) == 1 && v16 )
    {
      Connection = FindConnection(v16);
      if ( (*((_DWORD *)PortByHandle + 67) || *((_DWORD *)PortByHandle + 329))
        && Connection
        && *((_DWORD *)Connection + 17) == 1
        && *((_DWORD *)Connection + 6)
        && ((PortByHandle[160] + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        v37 = DwQueueRedial(Connection);
        if ( v37
          && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 156, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids, v37);
        }
        *((_DWORD *)PortByHandle + 329) = 0;
      }
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
      {
        LOBYTE(v36) = *((_DWORD *)PortByHandle + 268) != 0;
        WPP_SF_c(WPP_GLOBAL_Control[1].Flink, 157, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids, v36);
        v4 = WPP_GLOBAL_Control;
      }
      if ( *((_DWORD *)PortByHandle + 268) )
      {
        CurrentProcessId = GetCurrentProcessId();
        v39 = PortClose(PortByHandle, CurrentProcessId, 1, 0);
        if ( !v39 )
          goto LABEL_236;
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_qD(
            WPP_GLOBAL_Control[1].Flink,
            158,
            WPP_a45645adc1993df9b9f66dc87e784804_Traceguids,
            *PortByHandle,
            v39);
          goto LABEL_236;
        }
      }
      else if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
             && (HIDWORD(v4[1].Blink) & 0x2000) != 0
             && BYTE1(v4[1].Blink) >= 5u )
      {
        WPP_SF_q(v4[1].Flink, 159, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids, *PortByHandle);
        goto LABEL_236;
      }
    }
    goto LABEL_237;
  }
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v4[1].Blink) & 0x2000) != 0
    && BYTE1(v4[1].Blink) >= 5u )
  {
    WPP_SF_(v4[1].Flink, 147, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
LABEL_238:
  v40 = *(_DWORD *)(a2 + 32);
  if ( ((v40 - 7) & 0xFFFFFFFC) == 0 && v40 != 9 )
  {
    LocalFree((HLOCAL)a2);
    v4 = WPP_GLOBAL_Control;
  }
LABEL_241:
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v4[1].Blink) & 0x2000) != 0
    && BYTE1(v4[1].Blink) >= 6u )
  {
    WPP_SF_d(v4[1].Flink, 160, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18004eb50  mov     [rsp-38h+arg_0], rbx
0x18004eb55  push    rbp
0x18004eb56  push    rsi
0x18004eb57  push    rdi
0x18004eb58  push    r12
0x18004eb5a  push    r13
0x18004eb5c  push    r14
0x18004eb5e  push    r15
0x18004eb60  mov     rbp, rsp
0x18004eb63  sub     rsp, 60h
0x18004eb67  movaps  [rsp+60h+var_10], xmm6
0x18004eb6c  mov     r13, rdx
0x18004eb6f  mov     rdi, rcx
0x18004eb72  mov     rcx, cs:WPP_GLOBAL_Control
0x18004eb79  lea     rsi, WPP_GLOBAL_Control
0x18004eb80  mov     r12d, 2000h
0x18004eb86  cmp     rcx, rsi
0x18004eb89  jz      short loc_18004EBB3
0x18004eb8b  test    [rcx+1Ch], r12d
0x18004eb8f  jz      short loc_18004EBB3
0x18004eb91  cmp     byte ptr [rcx+19h], 6
0x18004eb95  jb      short loc_18004EBB3
0x18004eb97  mov     rcx, [rcx+10h]
0x18004eb9b  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x18004eba2  mov     edx, 7Ah ; 'z'
0x18004eba7  call    WPP_SF_
0x18004ebac  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ebb3  cmp     cs:RasmanShuttingDown, 0
0x18004ebba  mov     [rbp+arg_8], 0
0x18004ebc1  jnz     loc_18004F723
0x18004ebc7  test    r13, r13
0x18004ebca  jz      loc_18004F74B
0x18004ebd0  mov     rcx, rdi
0x18004ebd3  call    GetPortByHandle
0x18004ebd8  mov     rbx, rax
0x18004ebdb  test    rax, rax
0x18004ebde  jnz     short loc_18004EC3A
0x18004ebe0  mov     eax, [r13+20h]
0x18004ebe4  lea     ecx, [rax-7]
0x18004ebe7  test    ecx, 0FFFFFFFCh
0x18004ebed  jnz     short loc_18004EBF4
0x18004ebef  cmp     eax, 9
0x18004ebf2  jnz     short loc_18004EC3A
0x18004ebf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ebfb  cmp     rcx, rsi
0x18004ebfe  jz      loc_18004F723
0x18004ec04  test    [rcx+1Ch], r12d
0x18004ec08  jz      loc_18004F723
0x18004ec0e  mov     r14d, 3
0x18004ec14  cmp     [rcx+19h], r14b
0x18004ec18  jb      loc_18004F723
0x18004ec1e  mov     rcx, [rcx+10h]
0x18004ec22  lea     edx, [r14+78h]
0x18004ec26  mov     r9d, edi
0x18004ec29  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x18004ec30  call    WPP_SF_d
0x18004ec35  jmp     loc_18004F71C
0x18004ec3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ec41  lea     rdi, WPP_GLOBAL_Control
0x18004ec48  cmp     rcx, rdi
0x18004ec4b  jz      short loc_18004EC79
0x18004ec4d  test    [rcx+1Ch], r12d
0x18004ec51  jz      short loc_18004EC79
0x18004ec53  cmp     byte ptr [rcx+19h], 5
0x18004ec57  jb      short loc_18004EC79
0x18004ec59  mov     r9d, [r13+20h]
0x18004ec5d  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x18004ec64  mov     rcx, [rcx+10h]
0x18004ec68  mov     edx, 7Ch ; '|'
0x18004ec6d  call    WPP_SF_d
0x18004ec72  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ec79  mov     edx, [r13+20h]
0x18004ec7d  test    edx, edx
0x18004ec7f  jz      loc_18004F59B
0x18004ec85  sub     edx, 1
0x18004ec88  jz      loc_18004EF65
0x18004ec8e  sub     edx, 1
0x18004ec91  jz      loc_18004EEB0
0x18004ec97  sub     edx, 1
0x18004ec9a  jz      loc_18004EE72
0x18004eca0  sub     edx, 4
0x18004eca3  jz      loc_18004EE0D
0x18004eca9  sub     edx, 1
0x18004ecac  jz      loc_18004ED64
0x18004ecb2  cmp     edx, 2
0x18004ecb5  jz      short loc_18004ECF5
0x18004ecb7  cmp     rcx, rdi
0x18004ecba  jz      loc_18004EF43
0x18004ecc0  test    [rcx+1Ch], r12d
0x18004ecc4  jz      loc_18004EF43
0x18004ecca  cmp     byte ptr [rcx+19h], 5
0x18004ecce  jb      loc_18004EF43
0x18004ecd4  mov     rcx, [rcx+10h]
0x18004ecd8  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x18004ecdf  mov     edx, 9Bh
0x18004ece4  call    WPP_SF_
0x18004ece9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ecf0  jmp     loc_18004EF43
0x18004ecf5  cmp     rcx, rdi
0x18004ecf8  jz      short loc_18004ED1B
0x18004ecfa  test    [rcx+1Ch], r12d
0x18004ecfe  jz      short loc_18004ED1B
0x18004ed00  cmp     byte ptr [rcx+19h], 5
0x18004ed04  jb      short loc_18004ED1B
0x18004ed06  mov     rcx, [rcx+10h]
0x18004ed0a  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x18004ed11  mov     edx, 99h
0x18004ed16  call    WPP_SF_
0x18004ed1b  mov     rcx, [r13+28h]
0x18004ed1f  call    DwProcessRasConfigChangeNotification
0x18004ed24  test    eax, eax
0x18004ed26  jz      short loc_18004ED58
0x18004ed28  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ed2f  cmp     rcx, rdi
0x18004ed32  jz      short loc_18004ED58
0x18004ed34  test    [rcx+1Ch], r12d
0x18004ed38  jz      short loc_18004ED58
0x18004ed3a  cmp     byte ptr [rcx+19h], 2
0x18004ed3e  jb      short loc_18004ED58
0x18004ed40  mov     rcx, [rcx+10h]
0x18004ed44  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x18004ed4b  mov     edx, 9Ah
0x18004ed50  mov     r9d, eax
0x18004ed53  call    WPP_SF_d
0x18004ed58  mov     rcx, [r13+28h]; hMem
0x18004ed5c  call    cs:__imp_LocalFree
0x18004ed62  jmp     short loc_18004ECE9
0x18004ed64  cmp     rcx, rdi
0x18004ed67  jz      short loc_18004EDBB
0x18004ed69  test    [rcx+1Ch], r12d
0x18004ed6d  jz      short loc_18004ED91
0x18004ed6f  cmp     byte ptr [rcx+19h], 5
0x18004ed73  jb      short loc_18004ED91
0x18004ed75  mov     rcx, [rcx+10h]
0x18004ed79  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x18004ed80  mov     edx, 96h
0x18004ed85  call    WPP_SF_
0x18004ed8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ed91  cmp     rcx, rdi
0x18004ed94  jz      short loc_18004EDBB
0x18004ed96  test    [rcx+1Ch], r12d
0x18004ed9a  jz      short loc_18004EDBB
0x18004ed9c  cmp     byte ptr [rcx+19h], 5
0x18004eda0  jb      short loc_18004EDBB
0x18004eda2  mov     r9, [r13+28h]
0x18004eda6  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x18004edad  mov     rcx, [rcx+10h]
0x18004edb1  mov     edx, 97h
0x18004edb6  call    WPP_SF_q
0x18004edbb  mov     rcx, [r13+28h]; hMem
0x18004edbf  call    DwProcessLineRemoveNotification
0x18004edc4  test    eax, eax
0x18004edc6  jz      loc_18004ECE9
0x18004edcc  mov     rcx, cs:WPP_GLOBAL_Control
0x18004edd3  cmp     rcx, rdi
0x18004edd6  jz      loc_18004EF43
0x18004eddc  test    [rcx+1Ch], r12d
0x18004ede0  jz      loc_18004EF43
0x18004ede6  cmp     byte ptr [rcx+19h], 2
0x18004edea  jb      loc_18004EF43
0x18004edf0  mov     rcx, [rcx+10h]
0x18004edf4  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x18004edfb  mov     edx, 98h
0x18004ee00  mov     r9d, eax
0x18004ee03  call    WPP_SF_d
0x18004ee08  jmp     loc_18004ECE9
0x18004ee0d  cmp     rcx, rdi
0x18004ee10  jz      short loc_18004EE64
0x18004ee12  test    [rcx+1Ch], r12d
0x18004ee16  jz      short loc_18004EE3A
0x18004ee18  cmp     byte ptr [rcx+19h], 5
0x18004ee1c  jb      short loc_18004EE3A
0x18004ee1e  mov     rcx, [rcx+10h]
0x18004ee22  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x18004ee29  mov     edx, 94h
0x18004ee2e  call    WPP_SF_
0x18004ee33  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ee3a  cmp     rcx, rdi
0x18004ee3d  jz      short loc_18004EE64
0x18004ee3f  test    [rcx+1Ch], r12d
0x18004ee43  jz      short loc_18004EE64
0x18004ee45  cmp     byte ptr [rcx+19h], 5
0x18004ee49  jb      short loc_18004EE64
0x18004ee4b  mov     r9, [r13+28h]
0x18004ee4f  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x18004ee56  mov     rcx, [rcx+10h]
0x18004ee5a  mov     edx, 95h
0x18004ee5f  call    WPP_SF_q
0x18004ee64  mov     rcx, [r13+28h]; hMem
0x18004ee68  call    DwProcessNewPortNotification
0x18004ee6d  jmp     loc_18004ECE9
0x18004ee72  cmp     rcx, rdi
0x18004ee75  jz      loc_18004F728
0x18004ee7b  test    [rcx+1Ch], r12d
0x18004ee7f  jz      loc_18004F728
0x18004ee85  cmp     byte ptr [rcx+19h], 5
0x18004ee89  jb      loc_18004F728
0x18004ee8f  mov     rcx, [rcx+10h]
0x18004ee93  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x18004ee9a  mov     edx, 93h
0x18004ee9f  call    WPP_SF_
0x18004eea4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004eeab  jmp     loc_18004F728
0x18004eeb0  cmp     rcx, rdi
0x18004eeb3  jz      short loc_18004EF1A
0x18004eeb5  test    [rcx+1Ch], r12d
0x18004eeb9  jz      short loc_18004EEDD
0x18004eebb  cmp     byte ptr [rcx+19h], 5
0x18004eebf  jb      short loc_18004EEDD
0x18004eec1  mov     rcx, [rcx+10h]
0x18004eec5  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x18004eecc  mov     edx, 91h
0x18004eed1  call    WPP_SF_
0x18004eed6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004eedd  cmp     rcx, rdi
0x18004eee0  jz      short loc_18004EF1A
0x18004eee2  test    [rcx+1Ch], r12d
0x18004eee6  jz      short loc_18004EF1A
0x18004eee8  cmp     byte ptr [rcx+19h], 5
0x18004eeec  jb      short loc_18004EF1A
0x18004eeee  mov     eax, [rbx+1Ch]
0x18004eef1  lea     r9, [rbx+8]
0x18004eef5  mov     rcx, [rcx+10h]
0x18004eef9  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x18004ef00  mov     [rsp+60h+dwErrorCode], eax
0x18004ef04  mov     edx, 92h
0x18004ef09  mov     [rsp+60h+plpszSubStringArray], r13
0x18004ef0e  call    WPP_SF_sqD
0x18004ef13  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ef1a  cmp     dword ptr [rbx+1Ch], 4
0x18004ef1e  jz      short loc_18004EF43
0x18004ef20  mov     rcx, rbx
0x18004ef23  call    ServiceWorkRequest
0x18004ef28  mov     edi, 258h
0x18004ef2d  cmp     eax, edi
0x18004ef2f  jz      loc_18004F71C
0x18004ef35  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ef3c  lea     rdi, WPP_GLOBAL_Control
0x18004ef43  test    rbx, rbx
0x18004ef46  jz      loc_18004F5C2
0x18004ef4c  mov     rax, [rbx+428h]
0x18004ef53  test    rax, rax
0x18004ef56  jz      loc_18004F5C2
0x18004ef5c  mov     rax, [rax+10h]
0x18004ef60  jmp     loc_18004F5C4
0x18004ef65  cmp     rcx, rdi
0x18004ef68  jz      short loc_18004EF92
0x18004ef6a  test    [rcx+1Ch], r12d
0x18004ef6e  jz      short loc_18004EF92
0x18004ef70  cmp     byte ptr [rcx+19h], 5
0x18004ef74  jb      short loc_18004EF92
0x18004ef76  mov     rcx, [rcx+10h]
0x18004ef7a  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x18004ef81  mov     edx, 7Eh ; '~'
0x18004ef86  call    WPP_SF_
0x18004ef8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ef92  mov     [rbp+arg_8], 0FFFFFFFFh
0x18004ef99  cmp     rcx, rdi
0x18004ef9c  jz      short loc_18004EFC8
0x18004ef9e  test    [rcx+1Ch], r12d
0x18004efa2  jz      short loc_18004EFC8
0x18004efa4  cmp     byte ptr [rcx+19h], 5
0x18004efa8  jb      short loc_18004EFC8
0x18004efaa  mov     rcx, [rcx+10h]
0x18004efae  lea     r9, [rbx+8]
0x18004efb2  mov     edx, 7Fh
0x18004efb7  mov     [rsp+60h+plpszSubStringArray], r13
0x18004efbc  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x18004efc3  call    WPP_SF_sq
0x18004efc8  mov     rax, [rbx+30h]
0x18004efcc  lea     rdx, [rbp+arg_8]
0x18004efd0  mov     rcx, [rbx+0D8h]
0x18004efd7  mov     rax, [rax+78h]
0x18004efdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004efe0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004efe7  cmp     rcx, rdi
0x18004efea  jz      short loc_18004F018
0x18004efec  test    [rcx+1Ch], r12d
0x18004eff0  jz      short loc_18004F018
0x18004eff2  cmp     byte ptr [rcx+19h], 5
0x18004eff6  jb      short loc_18004F018
0x18004eff8  mov     r9d, [rbp+arg_8]
0x18004effc  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x18004f003  mov     rcx, [rcx+10h]
0x18004f007  mov     edx, 80h
0x18004f00c  call    WPP_SF_d
0x18004f011  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f018  test    byte ptr [rbp+arg_8], 1
0x18004f01c  mov     r14d, 3
0x18004f022  jz      short loc_18004F050
0x18004f024  lea     esi, [r14-1]
0x18004f028  mov     r15d, esi
0x18004f02b  cmp     rcx, rdi
0x18004f02e  jz      loc_18004F32E
0x18004f034  test    [rcx+1Ch], r12d
0x18004f038  jz      loc_18004F2E6
0x18004f03e  cmp     [rcx+19h], sil
0x18004f042  jb      loc_18004F2E6
0x18004f048  lea     edx, [rsi+7Fh]
0x18004f04b  jmp     loc_18004F2CF
  ... truncated ...
```
