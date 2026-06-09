# VidSchDdiNotifyInterruptWorker

- ea: `0x140027fc0`
- end: `0x140028a17`
- name: `VidSchDdiNotifyInterruptWorker`
- size: `2647`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x140027c00`
- `0x140043db0`

## callees

- `0x140004268`
- `0x140027fc0`
- `0x140028a20`
- `0x140028a90`
- `0x1400293f4`
- `0x14002955c`
- `0x140029620`
- `0x140029828`
- `0x14002a0a4`
- `0x1400446b4`
- `0x14004ea34`
- `0x14004fd1c`
- `0x14005443c`
- `0x140055224`
- `0x1400553d4`
- `0x1400554e0`
- `0x140055594`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140028371`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400287d0`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140028371`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400287d0`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140028842`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400289e2`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140028842`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400289e2`
- `watchdog!WdLogSingleEntry2` at `0x140028395`
- `watchdog!WdLogSingleEntry2` at `0x140028395`
- `watchdog!WdLogSingleEntry5` at `0x1400282e3`
- `watchdog!WdLogSingleEntry5` at `0x14002843e`
- `watchdog!WdLogSingleEntry5` at `0x14002847d`
- `watchdog!WdLogSingleEntry5` at `0x140028527`
- `watchdog!WdLogSingleEntry5` at `0x140028596`
- `watchdog!WdLogSingleEntry5` at `0x140028606`
- `watchdog!WdLogSingleEntry5` at `0x1400286a8`
- `watchdog!WdLogSingleEntry5` at `0x1400287a8`
- `watchdog!WdLogSingleEntry5` at `0x1400282e3`
- `watchdog!WdLogSingleEntry5` at `0x14002843e`
- `watchdog!WdLogSingleEntry5` at `0x14002847d`
- `watchdog!WdLogSingleEntry5` at `0x140028527`
- `watchdog!WdLogSingleEntry5` at `0x140028596`
- `watchdog!WdLogSingleEntry5` at `0x140028606`
- `watchdog!WdLogSingleEntry5` at `0x1400286a8`
- `watchdog!WdLogSingleEntry5` at `0x1400287a8`
- `watchdog!WdLogSingleEntry0` at `0x140028959`
- `watchdog!WdLogSingleEntry0` at `0x140028993`
- `watchdog!WdLogSingleEntry0` at `0x140028959`
- `watchdog!WdLogSingleEntry0` at `0x140028993`
- `watchdog!WdLogSingleEntry1` at `0x14002885a`
- `watchdog!WdLogSingleEntry1` at `0x14002885a`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400282be`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x140028418`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x140028454`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x140028502`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14002856e`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400285e4`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x140028683`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x140028782`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
void __fastcall VidSchDdiNotifyInterruptWorker(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // rbx
  __int64 v4; // rsi
  unsigned int v6; // edx
  __int64 v9; // r10
  int v10; // eax
  __int64 v11; // rdx
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 *v16; // rbx
  __int64 v17; // rbx
  unsigned __int64 v18; // r8
  __int64 *v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 *v22; // r13
  __int64 v23; // r13
  int v24; // ebx
  __int64 v25; // rcx
  unsigned int v26; // eax
  unsigned int v27; // r15d
  PSLIST_ENTRY v28; // rbx
  unsigned int v29; // eax
  int v30; // r8d
  int v31; // r8d
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // r9
  _QWORD *v36; // rcx
  __int64 v37; // rdx
  __int64 *v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // rdx
  __int64 *v42; // rbx
  __int64 v43; // rbx
  unsigned int v44; // r8d
  __int64 v45; // rcx
  __int64 v46; // rdx
  _QWORD *v47; // rcx
  __int64 v48; // rdx
  __int64 v49; // rax
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // r8
  __int64 v53; // r9
  __int64 v54; // r8
  __int64 v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // rcx
  PSLIST_ENTRY v58; // rax
  int v59; // ecx
  int v60; // r8d
  int v61; // eax
  int v62; // ecx
  int v63; // r8d
  int v64; // ecx
  int v65; // r8d
  __int64 v66; // rcx
  __int64 v67; // r8
  unsigned int v68; // [rsp+90h] [rbp+40h] BYREF
  __int64 v69; // [rsp+98h] [rbp+48h] BYREF

  v4 = *(_QWORD *)(a1 + 744);
  v68 = 0;
  v6 = *(_DWORD *)a2;
  v9 = 16;
  if ( v6 <= 0x12 )
  {
    v10 = 263304;
    if ( _bittest(&v10, v6) )
    {
      if ( (*(_DWORD *)(v4 + 44) & 0x10) != 0 && (*(_BYTE *)(v4 + 3364) & 8) == 0 )
      {
        if ( *(_DWORD *)(v4 + 88) <= 1u
          || (*(_DWORD *)(a2 + 72) & 1) == 0
          || (v6 == 7 || v6 == 10 || v6 == 18 ? (v31 = *(_DWORD *)(a2 + 12)) : (v31 = *(_DWORD *)(a2 + 24)), v31) )
        {
          v3 = MEMORY[0xFFFFF78000000320];
          v12 = VidSchiProcessIsrVSync((struct _VIDSCH_GLOBAL *)v4, (struct _DXGKARGCB_NOTIFY_INTERRUPT_DATA *)a2);
          if ( v12 != -1 && v12 < *(_DWORD *)(v4 + 48) )
          {
            _mm_lfence();
            v13 = *(_QWORD *)(v4 + 8LL * v12 + 3528);
            v14 = *(unsigned int *)(v13 + 44492);
            *(_QWORD *)(v13 + 8 * v14 + 44496) = v3;
            v15 = 10 * v14;
            *(_OWORD *)(v13 + 8 * v15 + 44528) = *(_OWORD *)a2;
            *(_OWORD *)(v13 + 8 * v15 + 44544) = *(_OWORD *)(a2 + 16);
            *(_OWORD *)(v13 + 8 * v15 + 44560) = *(_OWORD *)(a2 + 32);
            *(_OWORD *)(v13 + 8 * v15 + 44576) = *(_OWORD *)(a2 + 48);
            *(_OWORD *)(v13 + 8 * v15 + 44592) = *(_OWORD *)(a2 + 64);
            *(_DWORD *)(v13 + 44492) = ((unsigned __int8)*(_DWORD *)(v13 + 44492) + 1) & 3;
            return;
          }
        }
        else
        {
          g_DxgMmsBugcheckExportIndex = 1;
          WdLogSingleEntry5(0, 281, 6, v4, 0, 0);
          WdLogGlobalForLineNumber = 926;
        }
        v49 = *(unsigned int *)(v4 + 6384);
        *(_QWORD *)(v4 + 8 * v49 + 6392) = v3;
        v50 = 10 * v49;
        *(_OWORD *)(v4 + 8 * v50 + 6424) = *(_OWORD *)a2;
        *(_OWORD *)(v4 + 8 * v50 + 6440) = *(_OWORD *)(a2 + 16);
        *(_OWORD *)(v4 + 8 * v50 + 6456) = *(_OWORD *)(a2 + 32);
        *(_OWORD *)(v4 + 8 * v50 + 6472) = *(_OWORD *)(a2 + 48);
        *(_OWORD *)(v4 + 8 * v50 + 6488) = *(_OWORD *)(a2 + 64);
        *(_DWORD *)(v4 + 6384) = ((unsigned __int8)*(_DWORD *)(v4 + 6384) + 1) & 3;
        return;
      }
    }
  }
  if ( v6 != 1 )
  {
    switch ( v6 )
    {
      case 0xBu:
        if ( (*(_DWORD *)(v4 + 44) & 1) == 0 )
          return;
        v18 = *(_DWORD *)(a2 + 8) + (unsigned int)*(unsigned __int8 *)(*(unsigned int *)(a2 + 12) + v4 + 96);
        if ( a3 )
        {
          if ( _bittest64(*(const signed __int64 **)(v4 + 736), v18) )
            return;
        }
        v19 = *(__int64 **)(v4 + 776);
        if ( (unsigned int)v18 < *(_DWORD *)(v4 + 848) )
          v19 += v18;
        v20 = *v19;
        if ( *(_DWORD *)(v20 + 16) == 1 )
          return;
        if ( !a3 || *(_DWORD *)(v20 + 16) != 2 )
        {
          VidSchiProcessIsrMonitoredFenceSignaled(v20, v18);
          return;
        }
        v51 = *(unsigned __int16 *)(v20 + 4);
        g_DxgMmsBugcheckExportIndex = 1;
        WdLogSingleEntry5(0, 281, 16, v4, v51, 0);
        WdLogGlobalForLineNumber = 926;
        break;
      case 0x13u:
        break;
      case 2u:
        if ( (*(_DWORD *)(v4 + 44) & 1) != 0 )
        {
          v21 = *(_DWORD *)(a2 + 16) + (unsigned int)*(unsigned __int8 *)(*(unsigned int *)(a2 + 20) + v4 + 96);
          if ( !a3
            || !_bittest64(
                  *(const signed __int64 **)(v4 + 736),
                  *(_DWORD *)(a2 + 16) + (unsigned int)*(unsigned __int8 *)(*(unsigned int *)(a2 + 20) + v4 + 96)) )
          {
            v22 = *(__int64 **)(v4 + 776);
            if ( (unsigned int)v21 < *(_DWORD *)(v4 + 848) )
              v22 += v21;
            v23 = *v22;
            if ( *(_DWORD *)(v23 + 16) != 1 )
            {
              if ( a3 && *(_DWORD *)(v23 + 16) == 2 )
              {
                v32 = *(unsigned __int16 *)(v23 + 4);
                g_DxgMmsBugcheckExportIndex = 1;
                WdLogSingleEntry5(0, 281, 16, v4, v32, 0);
                WdLogGlobalForLineNumber = 926;
                goto LABEL_62;
              }
              if ( (unsigned int)VidSchiVerifyDriverReportedFenceId(
                                   (struct _VIDSCH_NODE *)v23,
                                   *(_DWORD *)(a2 + 8),
                                   1,
                                   0)
                && (unsigned int)VidSchiVerifyDriverReportedFenceId(
                                   (struct _VIDSCH_NODE *)v23,
                                   *(_DWORD *)(a2 + 12),
                                   0,
                                   &v68) )
              {
                do
                {
                  v24 = VidSchiProcessIsrCompletedPacket(v23, v68, a3, a2);
                  VidSchiProcessIsrPreemptedPacket(v23, *(unsigned int *)(a2 + 8), a3, a2);
                }
                while ( v24 );
              }
            }
          }
        }
        return;
      default:
        goto LABEL_44;
    }
    v52 = *(_DWORD *)(a2 + 8) + (unsigned int)*(unsigned __int8 *)(*(unsigned int *)(a2 + 12) + v4 + 96);
    if ( !a3
      || !_bittest64(
            *(const signed __int64 **)(v4 + 736),
            *(_DWORD *)(a2 + 8) + (unsigned int)*(unsigned __int8 *)(*(unsigned int *)(a2 + 12) + v4 + 96)) )
    {
      v38 = *(__int64 **)(v4 + 776);
      if ( (unsigned int)v52 < *(_DWORD *)(v4 + 848) )
        v38 += v52;
      v39 = *v38;
      if ( *(_DWORD *)(v39 + 16) != 1 )
      {
        if ( !a3 || *(_DWORD *)(v39 + 16) != 2 )
        {
          VidSchiProcessIsrNativeFenceSignaled(a2, (union _SLIST_HEADER *)v39);
          return;
        }
        v40 = *(unsigned __int16 *)(v39 + 4);
        g_DxgMmsBugcheckExportIndex = 1;
        WdLogSingleEntry5(0, 281, v9, v4, v40, 0);
        WdLogGlobalForLineNumber = 926;
        goto LABEL_73;
      }
    }
    return;
  }
  if ( (*(_DWORD *)(v4 + 44) & 1) != 0 )
  {
    v11 = *(_DWORD *)(a2 + 12) + (unsigned int)*(unsigned __int8 *)(*(unsigned int *)(a2 + 16) + v4 + 96);
    if ( !a3
      || !_bittest64(
            *(const signed __int64 **)(v4 + 736),
            *(_DWORD *)(a2 + 12) + (unsigned int)*(unsigned __int8 *)(*(unsigned int *)(a2 + 16) + v4 + 96)) )
    {
      v16 = *(__int64 **)(v4 + 776);
      if ( (unsigned int)v11 < *(_DWORD *)(v4 + 848) )
        v16 += v11;
      v17 = *v16;
      if ( *(_DWORD *)(v17 + 16) != 1 )
      {
        if ( !a3 || *(_DWORD *)(v17 + 16) != 2 )
        {
          if ( (unsigned int)VidSchiVerifyDriverReportedFenceId(
                               (struct _VIDSCH_NODE *)v17,
                               *(_DWORD *)(a2 + 8),
                               0,
                               &v68) )
            VidSchiProcessIsrCompletedPacket(v17, v68, a3, a2);
          return;
        }
        v25 = *(unsigned __int16 *)(v17 + 4);
        g_DxgMmsBugcheckExportIndex = 1;
        WdLogSingleEntry5(0, 281, 16, v4, v25, 0);
        WdLogGlobalForLineNumber = 926;
LABEL_44:
        if ( v6 != 4 )
        {
          if ( v6 != 9 )
          {
            if ( v6 != 15 )
            {
              if ( v6 != (_DWORD)v9 )
              {
                switch ( v6 )
                {
                  case 0x11u:
                    if ( (*(_DWORD *)(v4 + 44) & 1) != 0 )
                      VidSchiProcessIsrSuspendContextCompleted(v4, a2);
                    break;
                  case 0xCu:
                    if ( (*(_DWORD *)(v4 + 44) & 1) != 0 )
                      VidSchiProcessIsrHwQueuePageFaulted(v4, a2);
                    break;
                  case 0xEu:
                    v26 = ADAPTER_DISPLAY::MapVidPnTargetToVidPnSource(
                            *(ADAPTER_DISPLAY **)(*(_QWORD *)(v4 + 16) + 3248LL),
                            *(_DWORD *)(a2 + 8));
                    v27 = v26;
                    if ( v26 == -1 )
                    {
                      WdLogSingleEntry0(1);
                      WdLogGlobalForLineNumber = 8197;
                      DxgkLogInternalTriageEvent(
                        v62,
                        0x40000,
                        v63,
                        (unsigned int)L"Dropping invalid VidPnTargetId for interrupt type DXGK_INTERRUPT_PERIODIC_MONITORE"
                                       "D_FENCE_SIGNALED",
                        8197,
                        0,
                        0,
                        0);
                    }
                    else if ( (unsigned __int8)*(_DWORD *)(a2 + 12) >= 8u )
                    {
                      WdLogSingleEntry0(1);
                      WdLogGlobalForLineNumber = 8204;
                      DxgkLogInternalTriageEvent(
                        v64,
                        0x40000,
                        v65,
                        (unsigned int)L"Dropping invalid NotificationID for interrupt type DXGK_INTERRUPT_PERIODIC_MONITOR"
                                       "ED_FENCE_SIGNALED",
                        8204,
                        0,
                        0,
                        0);
                    }
                    else
                    {
                      v28 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(*(_QWORD *)(v4 + 8LL * v26 + 3528) + 78976LL));
                      v29 = *(_DWORD *)(a2 + 12);
                      if ( v28 )
                      {
                        HIDWORD(v28[2].Next) = v29;
                        LODWORD(v28[2].Next) = v27;
                        LODWORD(v28->Next) = 14;
                        ExpInterlockedPushEntrySList((PSLIST_HEADER)(v4 + 2144), v28 + 1);
                        if ( (byte_140087201 & 4) != 0 )
                          McTemplateK0dq_EtwWriteTransfer(
                            v66,
                            EventPeriodicFrameNotificationInterrupt,
                            v67,
                            LODWORD(v28[2].Next),
                            HIDWORD(v28[2].Next));
                      }
                      else
                      {
                        WdLogSingleEntry2(1, *(unsigned int *)(a2 + 8), v29);
                        WdLogGlobalForLineNumber = 8227;
                        DxgkLogInternalTriageEvent(
                          *(_DWORD *)(a2 + 8),
                          0x40000,
                          v30,
                          (unsigned int)L"Out of Periodic Cookies, can't process DXGK_INTERRUPT_PERIODIC_MONITORED_FENCE_S"
                                         "IGNALED with VidPnTargetId:%d NotificationID:%d",
                          *(unsigned int *)(a2 + 8),
                          *(unsigned int *)(a2 + 12),
                          0,
                          0);
                      }
                    }
                    break;
                }
                return;
              }
              goto LABEL_63;
            }
            if ( (*(_DWORD *)(v4 + 44) & 1) == 0 )
              return;
            goto LABEL_78;
          }
          if ( (*(_DWORD *)(v4 + 44) & 4) == 0 )
            return;
          VidSchiValidatePageFaultFlags(*(enum _DXGK_PAGE_FAULT_FLAGS *)(a2 + 32));
          v41 = *(_DWORD *)(a2 + 48) + (unsigned int)*(unsigned __int8 *)(*(unsigned int *)(a2 + 52) + v4 + 96);
          if ( a3
            && _bittest64(
                 *(const signed __int64 **)(v4 + 736),
                 *(_DWORD *)(a2 + 48) + (unsigned int)*(unsigned __int8 *)(*(unsigned int *)(a2 + 52) + v4 + 96)) )
          {
            v53 = 0;
            v54 = a2;
            v55 = a1;
            v56 = 1;
            goto LABEL_110;
          }
LABEL_73:
          v42 = *(__int64 **)(v4 + 776);
          if ( (unsigned int)v41 < *(_DWORD *)(v4 + 848) )
            v42 += v41;
          v43 = *v42;
          v44 = (*(_DWORD *)(v43 + 12) >> 1) & 1;
          if ( v44 && (*(_DWORD *)(a2 + 32) & 2) == 0 )
          {
            v45 = *(unsigned int *)(a2 + 44);
            v46 = *(unsigned int *)(a2 + 40);
            g_DxgMmsBugcheckExportIndex = 1;
            WdLogSingleEntry5(0, 281, 13, v44, v46, v45);
            WdLogGlobalForLineNumber = 926;
LABEL_78:
            v47 = *(_QWORD **)(v4 + 776);
            v48 = *(_DWORD *)(a2 + 8) + (unsigned int)*(unsigned __int8 *)(*(unsigned int *)(a2 + 12) + v4 + 96);
            if ( (unsigned int)v48 < *(_DWORD *)(v4 + 848) )
              v47 += v48;
            VidSchiProcessIsrSchedulingLogFull(*v47);
            return;
          }
          if ( *(_DWORD *)(v43 + 16) == 1 )
          {
            v53 = 0;
            v54 = a2;
            v55 = a1;
            v56 = 2;
          }
          else
          {
            if ( a3 && *(_DWORD *)(v43 + 16) == 2 )
            {
              v57 = *(unsigned __int16 *)(v43 + 4);
              g_DxgMmsBugcheckExportIndex = 1;
              WdLogSingleEntry5(0, 281, 16, v4, v57, 0);
              WdLogGlobalForLineNumber = 926;
            }
            if ( (*(_DWORD *)(a2 + 32) & 2) != 0 )
            {
              v58 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v43 + 11520));
              if ( v58 )
              {
                v58[2].Next = (struct _SLIST_ENTRY *)v43;
                *((_QWORD *)&v58[2].Next + 1) = *(unsigned int *)(a2 + 8);
                *((_QWORD *)&v58[3].Next + 1) = *(_QWORD *)(a2 + 16);
                LODWORD(v58[5].Next) = *(_DWORD *)(a2 + 24);
                HIDWORD(v58[5].Next) = *(_DWORD *)(a2 + 28);
                *((_DWORD *)&v58[5].Next + 2) = *(_DWORD *)(a2 + 32);
                v58[3].Next = *(struct _SLIST_ENTRY **)(a2 + 40);
                *((_DWORD *)&v58[4].Next + 2) = *(_DWORD *)(a2 + 48);
                *((_DWORD *)&v58[4].Next + 3) = *(_DWORD *)(a2 + 52);
                *((_DWORD *)&v58[5].Next + 3) = *(_DWORD *)(a2 + 56);
                LODWORD(v58[6].Next) = *(_DWORD *)(a2 + 60);
                v58[4].Next = *(struct _SLIST_ENTRY **)(a2 + 64);
                LODWORD(v58->Next) = 12;
                ExpInterlockedPushEntrySList((PSLIST_HEADER)(v4 + 2144), v58 + 1);
              }
              else
              {
                WdLogSingleEntry1(1, *(unsigned __int16 *)(v43 + 4));
                WdLogGlobalForLineNumber = 8104;
                DxgkLogInternalTriageEvent(
                  v59,
                  0x40000,
                  v60,
                  (unsigned int)L"The list of pending HW queue page faulted interrupts is full on node %d. There must be s"
                                 "evere contention on the scheduler spin lock. This interrupt will be ignored.",
                  *(unsigned __int16 *)(v43 + 4),
                  0,
                  0,
                  0);
              }
              return;
            }
            if ( !(unsigned int)VidSchiVerifyDriverReportedFenceId(
                                  (struct _VIDSCH_NODE *)v43,
                                  *(_DWORD *)(a2 + 8),
                                  0,
                                  &v68) )
              return;
            VidSchiProcessIsrCompletedPacket(v43, v68, a3, a2);
            v69 = 0;
            VidSchiProcessIsrFaultedPacket(v43, v68, a3, a2, (__int64)&v69);
            v61 = *(_DWORD *)(a2 + 32);
            v54 = a2;
            v53 = v69;
            v55 = a1;
            if ( (v61 & 4) != 0 )
            {
              v56 = 3;
            }
            else
            {
              v56 = 4;
              if ( (v61 & 8) == 0 )
                v56 = 5;
            }
          }
LABEL_110:
          LogPageFaultInformation(v56, v55, v54, v53);
          return;
        }
LABEL_62:
        v33 = *(unsigned int *)(a2 + 8);
        v34 = *(unsigned int *)(a2 + 20);
        v35 = *(unsigned int *)(a2 + 16);
        g_DxgMmsBugcheckExportIndex = 1;
        WdLogSingleEntry5(0, 281, 13, v35, v34, v33);
        WdLogGlobalForLineNumber = 926;
LABEL_63:
        if ( (*(_DWORD *)(v4 + 44) & 1) != 0 )
        {
          v36 = *(_QWORD **)(v4 + 776);
          v37 = *(_DWORD *)(a2 + 8) + (unsigned int)*(unsigned __int8 *)(*(unsigned int *)(a2 + 12) + v4 + 96);
          if ( (unsigned int)v37 < *(_DWORD *)(v4 + 848) )
            v36 += v37;
          VidSchiProcessIsrGpuEngineTimeout(*v36);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x140027fc0  mov     [rsp-38h+arg_10], rbx
0x140027fc5  push    rbp
0x140027fc6  push    rsi
0x140027fc7  push    rdi
0x140027fc8  push    r12
0x140027fca  push    r13
0x140027fcc  push    r14
0x140027fce  push    r15
0x140027fd0  mov     rbp, rsp
0x140027fd3  sub     rsp, 50h
0x140027fd7  mov     rsi, [rcx+2E8h]
0x140027fde  xor     r12d, r12d
0x140027fe1  mov     rdi, rdx
0x140027fe4  mov     [rbp+arg_0], r12d
0x140027fe8  mov     edx, [rdx]
0x140027fea  mov     r15d, r8d
0x140027fed  mov     r13, rcx
0x140027ff0  lea     r10d, [r12+10h]
0x140027ff5  cmp     edx, 12h
0x140027ff8  ja      short loc_140028015
0x140027ffa  mov     eax, 40488h
0x140027fff  bt      eax, edx
0x140028002  jnb     short loc_140028015
0x140028004  mov     eax, [rsi+2Ch]
0x140028007  test    r10b, al
0x14002800a  jz      short loc_140028015
0x14002800c  test    byte ptr [rsi+0D24h], 8
0x140028013  jz      short loc_14002806C
0x140028015  mov     r14d, 1
0x14002801b  cmp     edx, r14d
0x14002801e  jnz     loc_14002817B
0x140028024  mov     eax, [rsi+2Ch]
0x140028027  test    r14b, al
0x14002802a  jz      short loc_140028053
0x14002802c  mov     eax, [rdi+10h]
0x14002802f  movzx   edx, byte ptr [rax+rsi+60h]
0x140028034  add     edx, [rdi+0Ch]
0x140028037  mov     ecx, edx
0x140028039  test    r15d, r15d
0x14002803c  jz      loc_140028120
0x140028042  mov     rax, [rsi+2E0h]
0x140028049  bt      [rax], rcx
0x14002804d  jnb     loc_140028120
0x140028053  mov     rbx, [rsp+50h+arg_10]
0x14002805b  add     rsp, 50h
0x14002805f  pop     r15
0x140028061  pop     r14
0x140028063  pop     r13
0x140028065  pop     r12
0x140028067  pop     rdi
0x140028068  pop     rsi
0x140028069  pop     rbp
0x14002806a  retn
0x14002806c  mov     r14d, 1
0x140028072  mov     r8d, r12d
0x140028075  cmp     [rsi+58h], r14d
0x140028079  ja      loc_1400283DB
0x14002807f  mov     rbx, 0FFFFF78000000320h
0x140028089  mov     rdx, rdi; struct _DXGKARGCB_NOTIFY_INTERRUPT_DATA *
0x14002808c  mov     rcx, rsi; struct _VIDSCH_GLOBAL *
0x14002808f  mov     rbx, [rbx]
0x140028092  mov     r9, rbx
0x140028095  call    VidSchiProcessIsrVSync
0x14002809a  cmp     eax, 0FFFFFFFFh
0x14002809d  jz      loc_14002861C
0x1400280a3  cmp     eax, [rsi+30h]
0x1400280a6  jnb     loc_14002861C
0x1400280ac  lfence
0x1400280af  mov     eax, eax
0x1400280b1  mov     rdx, [rsi+rax*8+0DC8h]
0x1400280b9  mov     eax, [rdx+0ADCCh]
0x1400280bf  mov     [rdx+rax*8+0ADD0h], rbx
0x1400280c7  lea     rcx, [rax+rax*4]
0x1400280cb  movups  xmm0, xmmword ptr [rdi]
0x1400280ce  add     rcx, rcx
0x1400280d1  movups  xmmword ptr [rdx+rcx*8+0ADF0h], xmm0
0x1400280d9  movups  xmm1, xmmword ptr [rdi+10h]
0x1400280dd  movups  xmmword ptr [rdx+rcx*8+0AE00h], xmm1
0x1400280e5  movups  xmm0, xmmword ptr [rdi+20h]
0x1400280e9  movups  xmmword ptr [rdx+rcx*8+0AE10h], xmm0
0x1400280f1  movups  xmm1, xmmword ptr [rdi+30h]
0x1400280f5  movups  xmmword ptr [rdx+rcx*8+0AE20h], xmm1
0x1400280fd  movups  xmm0, xmmword ptr [rdi+40h]
0x140028101  movups  xmmword ptr [rdx+rcx*8+0AE30h], xmm0
0x140028109  mov     eax, [rdx+0ADCCh]
0x14002810f  add     eax, r14d
0x140028112  and     eax, 3
0x140028115  mov     [rdx+0ADCCh], eax
0x14002811b  jmp     loc_140028053
0x140028120  mov     rbx, [rsi+308h]
0x140028127  cmp     edx, [rsi+350h]
0x14002812d  jnb     short loc_140028133
0x14002812f  lea     rbx, [rbx+rdx*8]
0x140028133  mov     rbx, [rbx]
0x140028136  mov     eax, [rbx+10h]
0x140028139  cmp     eax, r14d
0x14002813c  jz      loc_140028053
0x140028142  test    r15d, r15d
0x140028145  jnz     loc_1400282B2
0x14002814b  mov     edx, [rdi+8]; unsigned int
0x14002814e  lea     r9, [rbp+arg_0]; unsigned int *
0x140028152  xor     r8d, r8d; int
0x140028155  mov     rcx, rbx; struct _VIDSCH_NODE *
0x140028158  call    ?VidSchiVerifyDriverReportedFenceId@@YAHPEAU_VIDSCH_NODE@@KHPEAK@Z; VidSchiVerifyDriverReportedFenceId(_VIDSCH_NODE *,ulong,int,ulong *)
0x14002815d  test    eax, eax
0x14002815f  jz      loc_140028053
0x140028165  mov     edx, [rbp+arg_0]
0x140028168  mov     r9, rdi
0x14002816b  mov     r8d, r15d
0x14002816e  mov     rcx, rbx
0x140028171  call    VidSchiProcessIsrCompletedPacket
0x140028176  jmp     loc_140028053
0x14002817b  cmp     edx, 0Bh
0x14002817e  jnz     short loc_1400281F0
0x140028180  mov     eax, [rsi+2Ch]
0x140028183  test    r14b, al
0x140028186  jz      loc_140028053
0x14002818c  mov     eax, [rdi+0Ch]
0x14002818f  movzx   r8d, byte ptr [rax+rsi+60h]
0x140028195  add     r8d, [rdi+8]
0x140028199  mov     edx, r8d
0x14002819c  test    r15d, r15d
0x14002819f  jz      short loc_1400281B2
0x1400281a1  mov     rax, [rsi+2E0h]
0x1400281a8  bt      [rax], rdx
0x1400281ac  jb      loc_140028053
0x1400281b2  mov     rcx, [rsi+308h]
0x1400281b9  cmp     r8d, [rsi+350h]
0x1400281c0  jnb     short loc_1400281C6
0x1400281c2  lea     rcx, [rcx+r8*8]
0x1400281c6  mov     rcx, [rcx]
0x1400281c9  mov     eax, [rcx+10h]
0x1400281cc  cmp     eax, r14d
0x1400281cf  jz      loc_140028053
0x1400281d5  test    r15d, r15d
0x1400281d8  jz      short loc_1400281E6
0x1400281da  mov     eax, [rcx+10h]
0x1400281dd  cmp     eax, 2
0x1400281e0  jz      loc_140028683
0x1400281e6  call    VidSchiProcessIsrMonitoredFenceSignaled
0x1400281eb  jmp     loc_140028053
0x1400281f0  cmp     edx, 13h
0x1400281f3  jz      loc_1400286BE
0x1400281f9  cmp     edx, 2
0x1400281fc  jnz     loc_1400282F9
0x140028202  mov     eax, [rsi+2Ch]
0x140028205  test    r14b, al
0x140028208  jz      loc_140028053
0x14002820e  mov     eax, [rdi+14h]
0x140028211  movzx   edx, byte ptr [rax+rsi+60h]
0x140028216  add     edx, [rdi+10h]
0x140028219  mov     ecx, edx
0x14002821b  test    r15d, r15d
0x14002821e  jnz     loc_1400286FA
0x140028224  mov     r13, [rsi+308h]
0x14002822b  cmp     edx, [rsi+350h]
0x140028231  jnb     short loc_140028238
0x140028233  lea     r13, [r13+rdx*8+0]
0x140028238  mov     r13, [r13+0]
0x14002823c  mov     eax, [r13+10h]
0x140028240  cmp     eax, r14d
0x140028243  jz      loc_140028053
0x140028249  test    r15d, r15d
0x14002824c  jnz     loc_14002840B
0x140028252  mov     edx, [rdi+8]; unsigned int
0x140028255  xor     r9d, r9d; unsigned int *
0x140028258  mov     r8d, r14d; int
0x14002825b  mov     rcx, r13; struct _VIDSCH_NODE *
0x14002825e  call    ?VidSchiVerifyDriverReportedFenceId@@YAHPEAU_VIDSCH_NODE@@KHPEAK@Z; VidSchiVerifyDriverReportedFenceId(_VIDSCH_NODE *,ulong,int,ulong *)
0x140028263  test    eax, eax
0x140028265  jz      loc_140028053
0x14002826b  mov     edx, [rdi+0Ch]; unsigned int
0x14002826e  lea     r9, [rbp+arg_0]; unsigned int *
0x140028272  xor     r8d, r8d; int
0x140028275  mov     rcx, r13; struct _VIDSCH_NODE *
0x140028278  call    ?VidSchiVerifyDriverReportedFenceId@@YAHPEAU_VIDSCH_NODE@@KHPEAK@Z; VidSchiVerifyDriverReportedFenceId(_VIDSCH_NODE *,ulong,int,ulong *)
0x14002827d  test    eax, eax
0x14002827f  jz      loc_140028053
0x140028285  mov     edx, [rbp+arg_0]
0x140028288  mov     r9, rdi
0x14002828b  mov     r8d, r15d
0x14002828e  mov     rcx, r13
0x140028291  call    VidSchiProcessIsrCompletedPacket
0x140028296  mov     edx, [rdi+8]
0x140028299  mov     r9, rdi
0x14002829c  mov     r8d, r15d
0x14002829f  mov     rcx, r13
0x1400282a2  mov     ebx, eax
0x1400282a4  call    VidSchiProcessIsrPreemptedPacket
0x1400282a9  test    ebx, ebx
0x1400282ab  jnz     short loc_140028285
0x1400282ad  jmp     loc_140028053
0x1400282b2  mov     eax, [rbx+10h]
0x1400282b5  cmp     eax, 2
0x1400282b8  jnz     loc_14002814B
0x1400282be  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400282c5  movzx   ecx, word ptr [rbx+4]
0x1400282c9  mov     [rax], r14d
0x1400282cc  mov     [rsp+50h+var_28], r12
0x1400282d1  mov     r9, rsi
0x1400282d4  mov     [rsp+50h+var_30], rcx
0x1400282d9  mov     r8, r10
0x1400282dc  xor     ecx, ecx
0x1400282de  mov     edx, 119h
0x1400282e3  call    cs:__imp_WdLogSingleEntry5
0x1400282ea  nop     dword ptr [rax+rax+00h]
0x1400282ef  mov     cs:WdLogGlobalForLineNumber, 39Eh
0x1400282f9  cmp     edx, 4
0x1400282fc  jz      loc_140028454
0x140028302  cmp     edx, 9
0x140028305  jz      loc_140028710
0x14002830b  cmp     edx, 0Fh
0x14002830e  jz      loc_14002890D
0x140028314  cmp     edx, r10d
0x140028317  jz      loc_140028493
0x14002831d  cmp     edx, 11h
0x140028320  jz      loc_14002891E
0x140028326  cmp     edx, 0Ch
0x140028329  jz      loc_14002893A
0x14002832f  cmp     edx, 0Eh
0x140028332  jnz     loc_140028053
0x140028338  mov     rcx, [rsi+10h]
0x14002833c  mov     edx, [rdi+8]; unsigned int
0x14002833f  mov     rcx, [rcx+0CB0h]; this
0x140028346  call    ?MapVidPnTargetToVidPnSource@ADAPTER_DISPLAY@@QEAAII@Z; ADAPTER_DISPLAY::MapVidPnTargetToVidPnSource(uint)
0x14002834b  mov     r15d, eax
0x14002834e  cmp     eax, 0FFFFFFFFh
0x140028351  jz      loc_140028956
0x140028357  mov     eax, [rdi+0Ch]
0x14002835a  cmp     al, 8
0x14002835c  jnb     loc_140028990
0x140028362  mov     rcx, [rsi+r15*8+0DC8h]
0x14002836a  add     rcx, 13480h; ListHead
0x140028371  call    cs:__imp_ExpInterlockedPopEntrySList
0x140028378  nop     dword ptr [rax+rax+00h]
0x14002837d  mov     rbx, rax
0x140028380  mov     eax, [rdi+0Ch]
0x140028383  test    rbx, rbx
0x140028386  jnz     loc_1400289CA
0x14002838c  mov     edx, [rdi+8]
0x14002838f  mov     r8d, eax
0x140028392  mov     ecx, r14d
0x140028395  call    cs:__imp_WdLogSingleEntry2
0x14002839c  nop     dword ptr [rax+rax+00h]
0x1400283a1  mov     [rsp+50h+var_18], r12
0x1400283a6  lea     r9, aOutOfPeriodicC; "Out of Periodic Cookies, can't process "...
0x1400283ad  mov     cs:WdLogGlobalForLineNumber, 2023h
0x1400283b7  mov     eax, [rdi+0Ch]
0x1400283ba  mov     ecx, [rdi+8]
0x1400283bd  mov     [rsp+50h+var_20], r12
0x1400283c2  mov     [rsp+50h+var_28], rax
0x1400283c7  mov     [rsp+50h+var_30], rcx
0x1400283cc  mov     edx, 40000h
0x1400283d1  call    DxgkLogInternalTriageEvent
0x1400283d6  jmp     loc_140028053
0x1400283db  mov     eax, [rdi+48h]
0x1400283de  test    r14b, al
0x1400283e1  jz      loc_14002807F
0x1400283e7  cmp     edx, 7
0x1400283ea  jz      loc_1400285D7
0x1400283f0  cmp     edx, 0Ah
0x1400283f3  jz      loc_1400285D7
0x1400283f9  cmp     edx, 12h
0x1400283fc  jz      loc_1400285D7
0x140028402  mov     r8d, [rdi+18h]
0x140028406  jmp     loc_1400285DB
0x14002840b  mov     eax, [r13+10h]
0x14002840f  cmp     eax, 2
0x140028412  jnz     loc_140028252
0x140028418  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x14002841f  movzx   ecx, word ptr [r13+4]
0x140028424  mov     [rax], r14d
0x140028427  mov     [rsp+50h+var_28], r12
0x14002842c  mov     r9, rsi
0x14002842f  mov     [rsp+50h+var_30], rcx
0x140028434  mov     r8, r10
0x140028437  xor     ecx, ecx
0x140028439  mov     edx, 119h
0x14002843e  call    cs:__imp_WdLogSingleEntry5
0x140028445  nop     dword ptr [rax+rax+00h]
0x14002844a  mov     cs:WdLogGlobalForLineNumber, 39Eh
0x140028454  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x14002845b  mov     ecx, [rdi+8]
0x14002845e  mov     edx, [rdi+14h]
0x140028461  mov     r9d, [rdi+10h]
0x140028465  mov     [rax], r14d
0x140028468  mov     [rsp+50h+var_28], rcx
0x14002846d  xor     ecx, ecx
0x14002846f  mov     [rsp+50h+var_30], rdx
0x140028474  mov     edx, 119h
0x140028479  lea     r8d, [rcx+0Dh]
0x14002847d  call    cs:__imp_WdLogSingleEntry5
0x140028484  nop     dword ptr [rax+rax+00h]
0x140028489  mov     cs:WdLogGlobalForLineNumber, 39Eh
0x140028493  mov     eax, [rsi+2Ch]
0x140028496  test    r14b, al
0x140028499  jz      loc_140028053
0x14002849f  mov     eax, [rdi+0Ch]
0x1400284a2  mov     rcx, [rsi+308h]
0x1400284a9  movzx   edx, byte ptr [rax+rsi+60h]
  ... truncated ...
```
