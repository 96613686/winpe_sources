# RasmanWorker

- ea: `0x1800510cc`
- end: `0x180051d44`
- name: `RasmanWorker`
- size: `3192`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180029de0`

## callees

- `0x180005418`
- `0x180005bcc`
- `0x180005bfc`
- `0x180005cf8`
- `0x180006f70`
- `0x18000c37c`
- `0x18000c3c0`
- `0x18000d600`
- `0x180014b6c`
- `0x1800210e0`
- `0x18003372c`
- `0x180033b38`
- `0x180034114`
- `0x180034190`
- `0x180039530`
- `0x18003bba4`
- `0x180040998`
- `0x18004236c`
- `0x180049944`
- `0x1800499f0`
- `0x18004a7cc`
- `0x18004a89c`
- `0x18004c2d8`
- `0x18004f720`
- `0x18004f910`
- `0x18004ff9c`
- `0x1800510cc`
- `0x180051d4c`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180051c40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180051c40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800519f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800519f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051a1a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051a1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800512d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051ce1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800512d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051ce1`
- `rtutils!RouterLogEventA` at `0x18005180e`
- `rtutils!RouterLogEventA` at `0x18005180e`
- `WS2_32!__imp_inet_ntoa` at `0x18005174a`
- `WS2_32!__imp_inet_ntoa` at `0x18005174a`

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
  __int64 v16; // rax
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
  __int64 Connection; // rax
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
        SignalNotifiers(pConnectionNotifierList, 2, 0);
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
        v44 = byte_1800F2282;
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
      v16 = *(_QWORD *)(v15 + 16);
    else
      v16 = 0;
    if ( *(_DWORD *)(a2 + 32) == 1 && v16 )
    {
      Connection = FindConnection(v16);
      if ( (*((_DWORD *)PortByHandle + 67) || *((_DWORD *)PortByHandle + 329))
        && Connection
        && *(_DWORD *)(Connection + 68) == 1
        && *(_DWORD *)(Connection + 24)
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
0x1800510cc  mov     [rsp-38h+arg_0], rbx
0x1800510d1  push    rbp
0x1800510d2  push    rsi
0x1800510d3  push    rdi
0x1800510d4  push    r12
0x1800510d6  push    r13
0x1800510d8  push    r14
0x1800510da  push    r15
0x1800510dc  mov     rbp, rsp
0x1800510df  sub     rsp, 60h
0x1800510e3  movaps  [rsp+60h+var_10], xmm6
0x1800510e8  mov     r13, rdx
0x1800510eb  mov     rdi, rcx
0x1800510ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800510f5  lea     rsi, WPP_GLOBAL_Control
0x1800510fc  mov     r12d, 2000h
0x180051102  cmp     rcx, rsi
0x180051105  jz      short loc_18005112F
0x180051107  test    [rcx+1Ch], r12d
0x18005110b  jz      short loc_18005112F
0x18005110d  cmp     byte ptr [rcx+19h], 6
0x180051111  jb      short loc_18005112F
0x180051113  mov     rcx, [rcx+10h]
0x180051117  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x18005111e  mov     edx, 7Ah ; 'z'
0x180051123  call    WPP_SF_
0x180051128  mov     rcx, cs:WPP_GLOBAL_Control
0x18005112f  cmp     cs:RasmanShuttingDown, 0
0x180051136  mov     [rbp+arg_8], 0
0x18005113d  jnz     loc_180051CC6
0x180051143  test    r13, r13
0x180051146  jz      loc_180051CF4
0x18005114c  mov     rcx, rdi
0x18005114f  call    GetPortByHandle
0x180051154  mov     rbx, rax
0x180051157  test    rax, rax
0x18005115a  jnz     short loc_1800511B6
0x18005115c  mov     eax, [r13+20h]
0x180051160  lea     ecx, [rax-7]
0x180051163  test    ecx, 0FFFFFFFCh
0x180051169  jnz     short loc_180051170
0x18005116b  cmp     eax, 9
0x18005116e  jnz     short loc_1800511B6
0x180051170  mov     rcx, cs:WPP_GLOBAL_Control
0x180051177  cmp     rcx, rsi
0x18005117a  jz      loc_180051CC6
0x180051180  test    [rcx+1Ch], r12d
0x180051184  jz      loc_180051CC6
0x18005118a  mov     r14d, 3
0x180051190  cmp     [rcx+19h], r14b
0x180051194  jb      loc_180051CC6
0x18005119a  mov     rcx, [rcx+10h]
0x18005119e  lea     edx, [r14+78h]
0x1800511a2  mov     r9d, edi
0x1800511a5  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x1800511ac  call    WPP_SF_d
0x1800511b1  jmp     loc_180051CBF
0x1800511b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800511bd  lea     rdi, WPP_GLOBAL_Control
0x1800511c4  cmp     rcx, rdi
0x1800511c7  jz      short loc_1800511F5
0x1800511c9  test    [rcx+1Ch], r12d
0x1800511cd  jz      short loc_1800511F5
0x1800511cf  cmp     byte ptr [rcx+19h], 5
0x1800511d3  jb      short loc_1800511F5
0x1800511d5  mov     r9d, [r13+20h]
0x1800511d9  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x1800511e0  mov     rcx, [rcx+10h]
0x1800511e4  mov     edx, 7Ch ; '|'
0x1800511e9  call    WPP_SF_d
0x1800511ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800511f5  mov     edx, [r13+20h]
0x1800511f9  test    edx, edx
0x1800511fb  jz      loc_180051B38
0x180051201  sub     edx, 1
0x180051204  jz      loc_1800514EA
0x18005120a  sub     edx, 1
0x18005120d  jz      loc_180051435
0x180051213  sub     edx, 1
0x180051216  jz      loc_1800513F7
0x18005121c  sub     edx, 4
0x18005121f  jz      loc_180051392
0x180051225  sub     edx, 1
0x180051228  jz      loc_1800512E9
0x18005122e  cmp     edx, 2
0x180051231  jz      short loc_180051271
0x180051233  cmp     rcx, rdi
0x180051236  jz      loc_1800514C8
0x18005123c  test    [rcx+1Ch], r12d
0x180051240  jz      loc_1800514C8
0x180051246  cmp     byte ptr [rcx+19h], 5
0x18005124a  jb      loc_1800514C8
0x180051250  mov     rcx, [rcx+10h]
0x180051254  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x18005125b  mov     edx, 9Bh
0x180051260  call    WPP_SF_
0x180051265  mov     rcx, cs:WPP_GLOBAL_Control
0x18005126c  jmp     loc_1800514C8
0x180051271  cmp     rcx, rdi
0x180051274  jz      short loc_180051297
0x180051276  test    [rcx+1Ch], r12d
0x18005127a  jz      short loc_180051297
0x18005127c  cmp     byte ptr [rcx+19h], 5
0x180051280  jb      short loc_180051297
0x180051282  mov     rcx, [rcx+10h]
0x180051286  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x18005128d  mov     edx, 99h
0x180051292  call    WPP_SF_
0x180051297  mov     rcx, [r13+28h]
0x18005129b  call    DwProcessRasConfigChangeNotification
0x1800512a0  test    eax, eax
0x1800512a2  jz      short loc_1800512D4
0x1800512a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800512ab  cmp     rcx, rdi
0x1800512ae  jz      short loc_1800512D4
0x1800512b0  test    [rcx+1Ch], r12d
0x1800512b4  jz      short loc_1800512D4
0x1800512b6  cmp     byte ptr [rcx+19h], 2
0x1800512ba  jb      short loc_1800512D4
0x1800512bc  mov     rcx, [rcx+10h]
0x1800512c0  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x1800512c7  mov     edx, 9Ah
0x1800512cc  mov     r9d, eax
0x1800512cf  call    WPP_SF_d
0x1800512d4  mov     rcx, [r13+28h]; hMem
0x1800512d8  call    cs:__imp_LocalFree
0x1800512df  nop     dword ptr [rax+rax+00h]
0x1800512e4  jmp     loc_180051265
0x1800512e9  cmp     rcx, rdi
0x1800512ec  jz      short loc_180051340
0x1800512ee  test    [rcx+1Ch], r12d
0x1800512f2  jz      short loc_180051316
0x1800512f4  cmp     byte ptr [rcx+19h], 5
0x1800512f8  jb      short loc_180051316
0x1800512fa  mov     rcx, [rcx+10h]
0x1800512fe  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x180051305  mov     edx, 96h
0x18005130a  call    WPP_SF_
0x18005130f  mov     rcx, cs:WPP_GLOBAL_Control
0x180051316  cmp     rcx, rdi
0x180051319  jz      short loc_180051340
0x18005131b  test    [rcx+1Ch], r12d
0x18005131f  jz      short loc_180051340
0x180051321  cmp     byte ptr [rcx+19h], 5
0x180051325  jb      short loc_180051340
0x180051327  mov     r9, [r13+28h]
0x18005132b  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x180051332  mov     rcx, [rcx+10h]
0x180051336  mov     edx, 97h
0x18005133b  call    WPP_SF_q
0x180051340  mov     rcx, [r13+28h]; hMem
0x180051344  call    DwProcessLineRemoveNotification
0x180051349  test    eax, eax
0x18005134b  jz      loc_180051265
0x180051351  mov     rcx, cs:WPP_GLOBAL_Control
0x180051358  cmp     rcx, rdi
0x18005135b  jz      loc_1800514C8
0x180051361  test    [rcx+1Ch], r12d
0x180051365  jz      loc_1800514C8
0x18005136b  cmp     byte ptr [rcx+19h], 2
0x18005136f  jb      loc_1800514C8
0x180051375  mov     rcx, [rcx+10h]
0x180051379  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x180051380  mov     edx, 98h
0x180051385  mov     r9d, eax
0x180051388  call    WPP_SF_d
0x18005138d  jmp     loc_180051265
0x180051392  cmp     rcx, rdi
0x180051395  jz      short loc_1800513E9
0x180051397  test    [rcx+1Ch], r12d
0x18005139b  jz      short loc_1800513BF
0x18005139d  cmp     byte ptr [rcx+19h], 5
0x1800513a1  jb      short loc_1800513BF
0x1800513a3  mov     rcx, [rcx+10h]
0x1800513a7  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x1800513ae  mov     edx, 94h
0x1800513b3  call    WPP_SF_
0x1800513b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800513bf  cmp     rcx, rdi
0x1800513c2  jz      short loc_1800513E9
0x1800513c4  test    [rcx+1Ch], r12d
0x1800513c8  jz      short loc_1800513E9
0x1800513ca  cmp     byte ptr [rcx+19h], 5
0x1800513ce  jb      short loc_1800513E9
0x1800513d0  mov     r9, [r13+28h]
0x1800513d4  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x1800513db  mov     rcx, [rcx+10h]
0x1800513df  mov     edx, 95h
0x1800513e4  call    WPP_SF_q
0x1800513e9  mov     rcx, [r13+28h]; hMem
0x1800513ed  call    DwProcessNewPortNotification
0x1800513f2  jmp     loc_180051265
0x1800513f7  cmp     rcx, rdi
0x1800513fa  jz      loc_180051CCB
0x180051400  test    [rcx+1Ch], r12d
0x180051404  jz      loc_180051CCB
0x18005140a  cmp     byte ptr [rcx+19h], 5
0x18005140e  jb      loc_180051CCB
0x180051414  mov     rcx, [rcx+10h]
0x180051418  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x18005141f  mov     edx, 93h
0x180051424  call    WPP_SF_
0x180051429  mov     rcx, cs:WPP_GLOBAL_Control
0x180051430  jmp     loc_180051CCB
0x180051435  cmp     rcx, rdi
0x180051438  jz      short loc_18005149F
0x18005143a  test    [rcx+1Ch], r12d
0x18005143e  jz      short loc_180051462
0x180051440  cmp     byte ptr [rcx+19h], 5
0x180051444  jb      short loc_180051462
0x180051446  mov     rcx, [rcx+10h]
0x18005144a  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x180051451  mov     edx, 91h
0x180051456  call    WPP_SF_
0x18005145b  mov     rcx, cs:WPP_GLOBAL_Control
0x180051462  cmp     rcx, rdi
0x180051465  jz      short loc_18005149F
0x180051467  test    [rcx+1Ch], r12d
0x18005146b  jz      short loc_18005149F
0x18005146d  cmp     byte ptr [rcx+19h], 5
0x180051471  jb      short loc_18005149F
0x180051473  mov     eax, [rbx+1Ch]
0x180051476  lea     r9, [rbx+8]
0x18005147a  mov     rcx, [rcx+10h]
0x18005147e  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x180051485  mov     [rsp+60h+dwErrorCode], eax
0x180051489  mov     edx, 92h
0x18005148e  mov     [rsp+60h+plpszSubStringArray], r13
0x180051493  call    WPP_SF_sqD
0x180051498  mov     rcx, cs:WPP_GLOBAL_Control
0x18005149f  cmp     dword ptr [rbx+1Ch], 4
0x1800514a3  jz      short loc_1800514C8
0x1800514a5  mov     rcx, rbx
0x1800514a8  call    ServiceWorkRequest
0x1800514ad  mov     edi, 258h
0x1800514b2  cmp     eax, edi
0x1800514b4  jz      loc_180051CBF
0x1800514ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800514c1  lea     rdi, WPP_GLOBAL_Control
0x1800514c8  test    rbx, rbx
0x1800514cb  jz      loc_180051B5F
0x1800514d1  mov     rax, [rbx+428h]
0x1800514d8  test    rax, rax
0x1800514db  jz      loc_180051B5F
0x1800514e1  mov     rax, [rax+10h]
0x1800514e5  jmp     loc_180051B61
0x1800514ea  cmp     rcx, rdi
0x1800514ed  jz      short loc_180051517
0x1800514ef  test    [rcx+1Ch], r12d
0x1800514f3  jz      short loc_180051517
0x1800514f5  cmp     byte ptr [rcx+19h], 5
0x1800514f9  jb      short loc_180051517
0x1800514fb  mov     rcx, [rcx+10h]
0x1800514ff  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x180051506  mov     edx, 7Eh ; '~'
0x18005150b  call    WPP_SF_
0x180051510  mov     rcx, cs:WPP_GLOBAL_Control
0x180051517  mov     [rbp+arg_8], 0FFFFFFFFh
0x18005151e  cmp     rcx, rdi
0x180051521  jz      short loc_18005154D
0x180051523  test    [rcx+1Ch], r12d
0x180051527  jz      short loc_18005154D
0x180051529  cmp     byte ptr [rcx+19h], 5
0x18005152d  jb      short loc_18005154D
0x18005152f  mov     rcx, [rcx+10h]
0x180051533  lea     r9, [rbx+8]
0x180051537  mov     edx, 7Fh
0x18005153c  mov     [rsp+60h+plpszSubStringArray], r13
0x180051541  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x180051548  call    WPP_SF_sq
0x18005154d  mov     rax, [rbx+30h]
0x180051551  lea     rdx, [rbp+arg_8]
0x180051555  mov     rcx, [rbx+0D8h]
0x18005155c  mov     rax, [rax+78h]
0x180051560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051565  mov     rcx, cs:WPP_GLOBAL_Control
0x18005156c  cmp     rcx, rdi
0x18005156f  jz      short loc_18005159D
0x180051571  test    [rcx+1Ch], r12d
0x180051575  jz      short loc_18005159D
0x180051577  cmp     byte ptr [rcx+19h], 5
0x18005157b  jb      short loc_18005159D
0x18005157d  mov     r9d, [rbp+arg_8]
0x180051581  lea     r8, WPP_a45645adc1993df9b9f66dc87e784804_Traceguids
0x180051588  mov     rcx, [rcx+10h]
0x18005158c  mov     edx, 80h
0x180051591  call    WPP_SF_d
0x180051596  mov     rcx, cs:WPP_GLOBAL_Control
0x18005159d  test    byte ptr [rbp+arg_8], 1
0x1800515a1  mov     r14d, 3
0x1800515a7  jz      short loc_1800515D5
0x1800515a9  lea     esi, [r14-1]
0x1800515ad  mov     r15d, esi
0x1800515b0  cmp     rcx, rdi
0x1800515b3  jz      loc_1800518BF
0x1800515b9  test    [rcx+1Ch], r12d
0x1800515bd  jz      loc_180051877
0x1800515c3  cmp     [rcx+19h], sil
0x1800515c7  jb      loc_180051877
0x1800515cd  lea     edx, [rsi+7Fh]
  ... truncated ...
```
