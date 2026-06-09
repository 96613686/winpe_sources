# VidSchDdiNotifyInterruptWorker

- ea: `0x14002a680`
- end: `0x14002b0d7`
- name: `VidSchDdiNotifyInterruptWorker`
- size: `2647`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x14002a2c0`
- `0x140043c40`

## callees

- `0x1400045ec`
- `0x14002a680`
- `0x14002b0e0`
- `0x14002b150`
- `0x14002bab4`
- `0x14002bc1c`
- `0x14002bce0`
- `0x14002bee8`
- `0x14002c764`
- `0x1400444b0`
- `0x14004e324`
- `0x14004f60c`
- `0x140053d2c`
- `0x14005494c`
- `0x140054afc`
- `0x140054c08`
- `0x140054cbc`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002aa31`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002ae90`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002aa31`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002ae90`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14002af02`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14002b0a2`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14002af02`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14002b0a2`
- `watchdog!WdLogSingleEntry2` at `0x14002aa55`
- `watchdog!WdLogSingleEntry2` at `0x14002aa55`
- `watchdog!WdLogSingleEntry5` at `0x14002a9a3`
- `watchdog!WdLogSingleEntry5` at `0x14002aafe`
- `watchdog!WdLogSingleEntry5` at `0x14002ab3d`
- `watchdog!WdLogSingleEntry5` at `0x14002abe7`
- `watchdog!WdLogSingleEntry5` at `0x14002ac56`
- `watchdog!WdLogSingleEntry5` at `0x14002acc6`
- `watchdog!WdLogSingleEntry5` at `0x14002ad68`
- `watchdog!WdLogSingleEntry5` at `0x14002ae68`
- `watchdog!WdLogSingleEntry5` at `0x14002a9a3`
- `watchdog!WdLogSingleEntry5` at `0x14002aafe`
- `watchdog!WdLogSingleEntry5` at `0x14002ab3d`
- `watchdog!WdLogSingleEntry5` at `0x14002abe7`
- `watchdog!WdLogSingleEntry5` at `0x14002ac56`
- `watchdog!WdLogSingleEntry5` at `0x14002acc6`
- `watchdog!WdLogSingleEntry5` at `0x14002ad68`
- `watchdog!WdLogSingleEntry5` at `0x14002ae68`
- `watchdog!WdLogSingleEntry0` at `0x14002b019`
- `watchdog!WdLogSingleEntry0` at `0x14002b053`
- `watchdog!WdLogSingleEntry0` at `0x14002b019`
- `watchdog!WdLogSingleEntry0` at `0x14002b053`
- `watchdog!WdLogSingleEntry1` at `0x14002af1a`
- `watchdog!WdLogSingleEntry1` at `0x14002af1a`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14002a97e`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14002aad8`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14002ab14`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14002abc2`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14002ac2e`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14002aca4`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14002ad43`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14002ae42`

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
  _QWORD *v32; // rcx
  __int64 v33; // rdx
  __int64 *v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 *v38; // rbx
  __int64 v39; // rbx
  _QWORD *v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // rax
  __int64 v43; // rcx
  __int64 v44; // r8
  __int64 v45; // r9
  __int64 v46; // r8
  __int64 v47; // rdx
  __int64 v48; // rcx
  PSLIST_ENTRY v49; // rax
  int v50; // ecx
  int v51; // r8d
  int v52; // eax
  int v53; // ecx
  int v54; // r8d
  int v55; // ecx
  int v56; // r8d
  __int64 v57; // rcx
  __int64 v58; // r8
  __int64 v59; // [rsp+20h] [rbp-30h]
  __int64 v60; // [rsp+28h] [rbp-28h]
  unsigned int v61; // [rsp+90h] [rbp+40h] BYREF
  __int64 v62; // [rsp+98h] [rbp+48h] BYREF

  v4 = *(_QWORD *)(a1 + 744);
  v61 = 0;
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
          WdLogSingleEntry5(0, 281, 6);
          WdLogGlobalForLineNumber = 921;
        }
        v42 = *(unsigned int *)(v4 + 6384);
        *(_QWORD *)(v4 + 8 * v42 + 6392) = v3;
        v43 = 10 * v42;
        *(_OWORD *)(v4 + 8 * v43 + 6424) = *(_OWORD *)a2;
        *(_OWORD *)(v4 + 8 * v43 + 6440) = *(_OWORD *)(a2 + 16);
        *(_OWORD *)(v4 + 8 * v43 + 6456) = *(_OWORD *)(a2 + 32);
        *(_OWORD *)(v4 + 8 * v43 + 6472) = *(_OWORD *)(a2 + 48);
        *(_OWORD *)(v4 + 8 * v43 + 6488) = *(_OWORD *)(a2 + 64);
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
        g_DxgMmsBugcheckExportIndex = 1;
        WdLogSingleEntry5(0, 281, 16);
        WdLogGlobalForLineNumber = 921;
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
                g_DxgMmsBugcheckExportIndex = 1;
                WdLogSingleEntry5(0, 281, 16);
                WdLogGlobalForLineNumber = 921;
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
                                   &v61) )
              {
                do
                {
                  v24 = VidSchiProcessIsrCompletedPacket(v23, v61, a3, a2);
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
    v44 = *(_DWORD *)(a2 + 8) + (unsigned int)*(unsigned __int8 *)(*(unsigned int *)(a2 + 12) + v4 + 96);
    if ( !a3
      || !_bittest64(
            *(const signed __int64 **)(v4 + 736),
            *(_DWORD *)(a2 + 8) + (unsigned int)*(unsigned __int8 *)(*(unsigned int *)(a2 + 12) + v4 + 96)) )
    {
      v34 = *(__int64 **)(v4 + 776);
      if ( (unsigned int)v44 < *(_DWORD *)(v4 + 848) )
        v34 += v44;
      v35 = *v34;
      if ( *(_DWORD *)(v35 + 16) != 1 )
      {
        if ( !a3 || *(_DWORD *)(v35 + 16) != 2 )
        {
          VidSchiProcessIsrNativeFenceSignaled(a2);
          return;
        }
        v36 = *(unsigned __int16 *)(v35 + 4);
        g_DxgMmsBugcheckExportIndex = 1;
        v60 = 0;
        v59 = v36;
        WdLogSingleEntry5(0, 281, v9);
        WdLogGlobalForLineNumber = 921;
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
                               &v61) )
            VidSchiProcessIsrCompletedPacket(v17, v61, a3, a2);
          return;
        }
        v25 = *(unsigned __int16 *)(v17 + 4);
        g_DxgMmsBugcheckExportIndex = 1;
        v60 = 0;
        v59 = v25;
        WdLogSingleEntry5(0, 281, 16);
        WdLogGlobalForLineNumber = 921;
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
                            *(ADAPTER_DISPLAY **)(*(_QWORD *)(v4 + 16) + 3232LL),
                            *(_DWORD *)(a2 + 8));
                    v27 = v26;
                    if ( v26 == -1 )
                    {
                      WdLogSingleEntry0(1);
                      WdLogGlobalForLineNumber = 8197;
                      DxgkLogInternalTriageEvent(
                        v53,
                        0x40000,
                        v54,
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
                        v55,
                        0x40000,
                        v56,
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
                        if ( (byte_140086201 & 4) != 0 )
                          McTemplateK0dq_EtwWriteTransfer(
                            v57,
                            EventPeriodicFrameNotificationInterrupt,
                            v58,
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
          v37 = *(_DWORD *)(a2 + 48) + (unsigned int)*(unsigned __int8 *)(*(unsigned int *)(a2 + 52) + v4 + 96);
          if ( a3
            && _bittest64(
                 *(const signed __int64 **)(v4 + 736),
                 *(_DWORD *)(a2 + 48) + (unsigned int)*(unsigned __int8 *)(*(unsigned int *)(a2 + 52) + v4 + 96)) )
          {
            v45 = 0;
            v46 = a2;
            v47 = a1;
            v48 = 1;
            goto LABEL_110;
          }
LABEL_73:
          v38 = *(__int64 **)(v4 + 776);
          if ( (unsigned int)v37 < *(_DWORD *)(v4 + 848) )
            v38 += v37;
          v39 = *v38;
          if ( ((*(_DWORD *)(v39 + 12) >> 1) & 1) != 0 && (*(_DWORD *)(a2 + 32) & 2) == 0 )
          {
            g_DxgMmsBugcheckExportIndex = 1;
            WdLogSingleEntry5(0, 281, 13);
            WdLogGlobalForLineNumber = 921;
LABEL_78:
            v40 = *(_QWORD **)(v4 + 776);
            v41 = *(_DWORD *)(a2 + 8) + (unsigned int)*(unsigned __int8 *)(*(unsigned int *)(a2 + 12) + v4 + 96);
            if ( (unsigned int)v41 < *(_DWORD *)(v4 + 848) )
              v40 += v41;
            VidSchiProcessIsrSchedulingLogFull(*v40);
            return;
          }
          if ( *(_DWORD *)(v39 + 16) == 1 )
          {
            v45 = 0;
            v46 = a2;
            v47 = a1;
            v48 = 2;
          }
          else
          {
            if ( a3 && *(_DWORD *)(v39 + 16) == 2 )
            {
              g_DxgMmsBugcheckExportIndex = 1;
              v60 = 0;
              WdLogSingleEntry5(0, 281, 16);
              WdLogGlobalForLineNumber = 921;
            }
            if ( (*(_DWORD *)(a2 + 32) & 2) != 0 )
            {
              v49 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v39 + 11520));
              if ( v49 )
              {
                v49[2].Next = (struct _SLIST_ENTRY *)v39;
                *((_QWORD *)&v49[2].Next + 1) = *(unsigned int *)(a2 + 8);
                *((_QWORD *)&v49[3].Next + 1) = *(_QWORD *)(a2 + 16);
                LODWORD(v49[5].Next) = *(_DWORD *)(a2 + 24);
                HIDWORD(v49[5].Next) = *(_DWORD *)(a2 + 28);
                *((_DWORD *)&v49[5].Next + 2) = *(_DWORD *)(a2 + 32);
                v49[3].Next = *(struct _SLIST_ENTRY **)(a2 + 40);
                *((_DWORD *)&v49[4].Next + 2) = *(_DWORD *)(a2 + 48);
                *((_DWORD *)&v49[4].Next + 3) = *(_DWORD *)(a2 + 52);
                *((_DWORD *)&v49[5].Next + 3) = *(_DWORD *)(a2 + 56);
                LODWORD(v49[6].Next) = *(_DWORD *)(a2 + 60);
                v49[4].Next = *(struct _SLIST_ENTRY **)(a2 + 64);
                LODWORD(v49->Next) = 12;
                ExpInterlockedPushEntrySList((PSLIST_HEADER)(v4 + 2144), v49 + 1);
              }
              else
              {
                WdLogSingleEntry1(1, *(unsigned __int16 *)(v39 + 4));
                WdLogGlobalForLineNumber = 8104;
                DxgkLogInternalTriageEvent(
                  v50,
                  0x40000,
                  v51,
                  (unsigned int)L"The list of pending HW queue page faulted interrupts is full on node %d. There must be s"
                                 "evere contention on the scheduler spin lock. This interrupt will be ignored.",
                  *(unsigned __int16 *)(v39 + 4),
                  0,
                  0,
                  0);
              }
              return;
            }
            if ( !(unsigned int)VidSchiVerifyDriverReportedFenceId(
                                  (struct _VIDSCH_NODE *)v39,
                                  *(_DWORD *)(a2 + 8),
                                  0,
                                  &v61) )
              return;
            VidSchiProcessIsrCompletedPacket(v39, v61, a3, a2);
            v62 = 0;
            VidSchiProcessIsrFaultedPacket(v39, v61, a3, a2, (__int64)&v62);
            v52 = *(_DWORD *)(a2 + 32);
            v46 = a2;
            v45 = v62;
            v47 = a1;
            if ( (v52 & 4) != 0 )
            {
              v48 = 3;
            }
            else
            {
              v48 = 4;
              if ( (v52 & 8) == 0 )
                v48 = 5;
            }
          }
LABEL_110:
          LogPageFaultInformation(v48, v47, v46, v45, v59, v60);
          return;
        }
LABEL_62:
        g_DxgMmsBugcheckExportIndex = 1;
        WdLogSingleEntry5(0, 281, 13);
        WdLogGlobalForLineNumber = 921;
LABEL_63:
        if ( (*(_DWORD *)(v4 + 44) & 1) != 0 )
        {
          v32 = *(_QWORD **)(v4 + 776);
          v33 = *(_DWORD *)(a2 + 8) + (unsigned int)*(unsigned __int8 *)(*(unsigned int *)(a2 + 12) + v4 + 96);
          if ( (unsigned int)v33 < *(_DWORD *)(v4 + 848) )
            v32 += v33;
          VidSchiProcessIsrGpuEngineTimeout(*v32);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x14002a680  mov     [rsp-38h+arg_10], rbx
0x14002a685  push    rbp
0x14002a686  push    rsi
0x14002a687  push    rdi
0x14002a688  push    r12
0x14002a68a  push    r13
0x14002a68c  push    r14
0x14002a68e  push    r15
0x14002a690  mov     rbp, rsp
0x14002a693  sub     rsp, 50h
0x14002a697  mov     rsi, [rcx+2E8h]
0x14002a69e  xor     r12d, r12d
0x14002a6a1  mov     rdi, rdx
0x14002a6a4  mov     [rbp+arg_0], r12d
0x14002a6a8  mov     edx, [rdx]
0x14002a6aa  mov     r15d, r8d
0x14002a6ad  mov     r13, rcx
0x14002a6b0  lea     r10d, [r12+10h]
0x14002a6b5  cmp     edx, 12h
0x14002a6b8  ja      short loc_14002A6D5
0x14002a6ba  mov     eax, 40488h
0x14002a6bf  bt      eax, edx
0x14002a6c2  jnb     short loc_14002A6D5
0x14002a6c4  mov     eax, [rsi+2Ch]
0x14002a6c7  test    r10b, al
0x14002a6ca  jz      short loc_14002A6D5
0x14002a6cc  test    byte ptr [rsi+0D24h], 8
0x14002a6d3  jz      short loc_14002A72C
0x14002a6d5  mov     r14d, 1
0x14002a6db  cmp     edx, r14d
0x14002a6de  jnz     loc_14002A83B
0x14002a6e4  mov     eax, [rsi+2Ch]
0x14002a6e7  test    r14b, al
0x14002a6ea  jz      short loc_14002A713
0x14002a6ec  mov     eax, [rdi+10h]
0x14002a6ef  movzx   edx, byte ptr [rax+rsi+60h]
0x14002a6f4  add     edx, [rdi+0Ch]
0x14002a6f7  mov     ecx, edx
0x14002a6f9  test    r15d, r15d
0x14002a6fc  jz      loc_14002A7E0
0x14002a702  mov     rax, [rsi+2E0h]
0x14002a709  bt      [rax], rcx
0x14002a70d  jnb     loc_14002A7E0
0x14002a713  mov     rbx, [rsp+50h+arg_10]
0x14002a71b  add     rsp, 50h
0x14002a71f  pop     r15
0x14002a721  pop     r14
0x14002a723  pop     r13
0x14002a725  pop     r12
0x14002a727  pop     rdi
0x14002a728  pop     rsi
0x14002a729  pop     rbp
0x14002a72a  retn
0x14002a72c  mov     r14d, 1
0x14002a732  mov     r8d, r12d
0x14002a735  cmp     [rsi+58h], r14d
0x14002a739  ja      loc_14002AA9B
0x14002a73f  mov     rbx, 0FFFFF78000000320h
0x14002a749  mov     rdx, rdi; struct _DXGKARGCB_NOTIFY_INTERRUPT_DATA *
0x14002a74c  mov     rcx, rsi; struct _VIDSCH_GLOBAL *
0x14002a74f  mov     rbx, [rbx]
0x14002a752  mov     r9, rbx
0x14002a755  call    VidSchiProcessIsrVSync
0x14002a75a  cmp     eax, 0FFFFFFFFh
0x14002a75d  jz      loc_14002ACDC
0x14002a763  cmp     eax, [rsi+30h]
0x14002a766  jnb     loc_14002ACDC
0x14002a76c  lfence
0x14002a76f  mov     eax, eax
0x14002a771  mov     rdx, [rsi+rax*8+0DC8h]
0x14002a779  mov     eax, [rdx+0ADCCh]
0x14002a77f  mov     [rdx+rax*8+0ADD0h], rbx
0x14002a787  lea     rcx, [rax+rax*4]
0x14002a78b  movups  xmm0, xmmword ptr [rdi]
0x14002a78e  add     rcx, rcx
0x14002a791  movups  xmmword ptr [rdx+rcx*8+0ADF0h], xmm0
0x14002a799  movups  xmm1, xmmword ptr [rdi+10h]
0x14002a79d  movups  xmmword ptr [rdx+rcx*8+0AE00h], xmm1
0x14002a7a5  movups  xmm0, xmmword ptr [rdi+20h]
0x14002a7a9  movups  xmmword ptr [rdx+rcx*8+0AE10h], xmm0
0x14002a7b1  movups  xmm1, xmmword ptr [rdi+30h]
0x14002a7b5  movups  xmmword ptr [rdx+rcx*8+0AE20h], xmm1
0x14002a7bd  movups  xmm0, xmmword ptr [rdi+40h]
0x14002a7c1  movups  xmmword ptr [rdx+rcx*8+0AE30h], xmm0
0x14002a7c9  mov     eax, [rdx+0ADCCh]
0x14002a7cf  add     eax, r14d
0x14002a7d2  and     eax, 3
0x14002a7d5  mov     [rdx+0ADCCh], eax
0x14002a7db  jmp     loc_14002A713
0x14002a7e0  mov     rbx, [rsi+308h]
0x14002a7e7  cmp     edx, [rsi+350h]
0x14002a7ed  jnb     short loc_14002A7F3
0x14002a7ef  lea     rbx, [rbx+rdx*8]
0x14002a7f3  mov     rbx, [rbx]
0x14002a7f6  mov     eax, [rbx+10h]
0x14002a7f9  cmp     eax, r14d
0x14002a7fc  jz      loc_14002A713
0x14002a802  test    r15d, r15d
0x14002a805  jnz     loc_14002A972
0x14002a80b  mov     edx, [rdi+8]; unsigned int
0x14002a80e  lea     r9, [rbp+arg_0]; unsigned int *
0x14002a812  xor     r8d, r8d; int
0x14002a815  mov     rcx, rbx; struct _VIDSCH_NODE *
0x14002a818  call    ?VidSchiVerifyDriverReportedFenceId@@YAHPEAU_VIDSCH_NODE@@KHPEAK@Z; VidSchiVerifyDriverReportedFenceId(_VIDSCH_NODE *,ulong,int,ulong *)
0x14002a81d  test    eax, eax
0x14002a81f  jz      loc_14002A713
0x14002a825  mov     edx, [rbp+arg_0]
0x14002a828  mov     r9, rdi
0x14002a82b  mov     r8d, r15d
0x14002a82e  mov     rcx, rbx
0x14002a831  call    VidSchiProcessIsrCompletedPacket
0x14002a836  jmp     loc_14002A713
0x14002a83b  cmp     edx, 0Bh
0x14002a83e  jnz     short loc_14002A8B0
0x14002a840  mov     eax, [rsi+2Ch]
0x14002a843  test    r14b, al
0x14002a846  jz      loc_14002A713
0x14002a84c  mov     eax, [rdi+0Ch]
0x14002a84f  movzx   r8d, byte ptr [rax+rsi+60h]
0x14002a855  add     r8d, [rdi+8]
0x14002a859  mov     edx, r8d
0x14002a85c  test    r15d, r15d
0x14002a85f  jz      short loc_14002A872
0x14002a861  mov     rax, [rsi+2E0h]
0x14002a868  bt      [rax], rdx
0x14002a86c  jb      loc_14002A713
0x14002a872  mov     rcx, [rsi+308h]
0x14002a879  cmp     r8d, [rsi+350h]
0x14002a880  jnb     short loc_14002A886
0x14002a882  lea     rcx, [rcx+r8*8]
0x14002a886  mov     rcx, [rcx]
0x14002a889  mov     eax, [rcx+10h]
0x14002a88c  cmp     eax, r14d
0x14002a88f  jz      loc_14002A713
0x14002a895  test    r15d, r15d
0x14002a898  jz      short loc_14002A8A6
0x14002a89a  mov     eax, [rcx+10h]
0x14002a89d  cmp     eax, 2
0x14002a8a0  jz      loc_14002AD43
0x14002a8a6  call    VidSchiProcessIsrMonitoredFenceSignaled
0x14002a8ab  jmp     loc_14002A713
0x14002a8b0  cmp     edx, 13h
0x14002a8b3  jz      loc_14002AD7E
0x14002a8b9  cmp     edx, 2
0x14002a8bc  jnz     loc_14002A9B9
0x14002a8c2  mov     eax, [rsi+2Ch]
0x14002a8c5  test    r14b, al
0x14002a8c8  jz      loc_14002A713
0x14002a8ce  mov     eax, [rdi+14h]
0x14002a8d1  movzx   edx, byte ptr [rax+rsi+60h]
0x14002a8d6  add     edx, [rdi+10h]
0x14002a8d9  mov     ecx, edx
0x14002a8db  test    r15d, r15d
0x14002a8de  jnz     loc_14002ADBA
0x14002a8e4  mov     r13, [rsi+308h]
0x14002a8eb  cmp     edx, [rsi+350h]
0x14002a8f1  jnb     short loc_14002A8F8
0x14002a8f3  lea     r13, [r13+rdx*8+0]
0x14002a8f8  mov     r13, [r13+0]
0x14002a8fc  mov     eax, [r13+10h]
0x14002a900  cmp     eax, r14d
0x14002a903  jz      loc_14002A713
0x14002a909  test    r15d, r15d
0x14002a90c  jnz     loc_14002AACB
0x14002a912  mov     edx, [rdi+8]; unsigned int
0x14002a915  xor     r9d, r9d; unsigned int *
0x14002a918  mov     r8d, r14d; int
0x14002a91b  mov     rcx, r13; struct _VIDSCH_NODE *
0x14002a91e  call    ?VidSchiVerifyDriverReportedFenceId@@YAHPEAU_VIDSCH_NODE@@KHPEAK@Z; VidSchiVerifyDriverReportedFenceId(_VIDSCH_NODE *,ulong,int,ulong *)
0x14002a923  test    eax, eax
0x14002a925  jz      loc_14002A713
0x14002a92b  mov     edx, [rdi+0Ch]; unsigned int
0x14002a92e  lea     r9, [rbp+arg_0]; unsigned int *
0x14002a932  xor     r8d, r8d; int
0x14002a935  mov     rcx, r13; struct _VIDSCH_NODE *
0x14002a938  call    ?VidSchiVerifyDriverReportedFenceId@@YAHPEAU_VIDSCH_NODE@@KHPEAK@Z; VidSchiVerifyDriverReportedFenceId(_VIDSCH_NODE *,ulong,int,ulong *)
0x14002a93d  test    eax, eax
0x14002a93f  jz      loc_14002A713
0x14002a945  mov     edx, [rbp+arg_0]
0x14002a948  mov     r9, rdi
0x14002a94b  mov     r8d, r15d
0x14002a94e  mov     rcx, r13
0x14002a951  call    VidSchiProcessIsrCompletedPacket
0x14002a956  mov     edx, [rdi+8]
0x14002a959  mov     r9, rdi
0x14002a95c  mov     r8d, r15d
0x14002a95f  mov     rcx, r13
0x14002a962  mov     ebx, eax
0x14002a964  call    VidSchiProcessIsrPreemptedPacket
0x14002a969  test    ebx, ebx
0x14002a96b  jnz     short loc_14002A945
0x14002a96d  jmp     loc_14002A713
0x14002a972  mov     eax, [rbx+10h]
0x14002a975  cmp     eax, 2
0x14002a978  jnz     loc_14002A80B
0x14002a97e  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x14002a985  movzx   ecx, word ptr [rbx+4]
0x14002a989  mov     [rax], r14d
0x14002a98c  mov     [rsp+50h+var_28], r12
0x14002a991  mov     r9, rsi
0x14002a994  mov     [rsp+50h+var_30], rcx
0x14002a999  mov     r8, r10
0x14002a99c  xor     ecx, ecx
0x14002a99e  mov     edx, 119h
0x14002a9a3  call    cs:__imp_WdLogSingleEntry5
0x14002a9aa  nop     dword ptr [rax+rax+00h]
0x14002a9af  mov     cs:WdLogGlobalForLineNumber, 399h
0x14002a9b9  cmp     edx, 4
0x14002a9bc  jz      loc_14002AB14
0x14002a9c2  cmp     edx, 9
0x14002a9c5  jz      loc_14002ADD0
0x14002a9cb  cmp     edx, 0Fh
0x14002a9ce  jz      loc_14002AFCD
0x14002a9d4  cmp     edx, r10d
0x14002a9d7  jz      loc_14002AB53
0x14002a9dd  cmp     edx, 11h
0x14002a9e0  jz      loc_14002AFDE
0x14002a9e6  cmp     edx, 0Ch
0x14002a9e9  jz      loc_14002AFFA
0x14002a9ef  cmp     edx, 0Eh
0x14002a9f2  jnz     loc_14002A713
0x14002a9f8  mov     rcx, [rsi+10h]
0x14002a9fc  mov     edx, [rdi+8]; unsigned int
0x14002a9ff  mov     rcx, [rcx+0CA0h]; this
0x14002aa06  call    ?MapVidPnTargetToVidPnSource@ADAPTER_DISPLAY@@QEAAII@Z; ADAPTER_DISPLAY::MapVidPnTargetToVidPnSource(uint)
0x14002aa0b  mov     r15d, eax
0x14002aa0e  cmp     eax, 0FFFFFFFFh
0x14002aa11  jz      loc_14002B016
0x14002aa17  mov     eax, [rdi+0Ch]
0x14002aa1a  cmp     al, 8
0x14002aa1c  jnb     loc_14002B050
0x14002aa22  mov     rcx, [rsi+r15*8+0DC8h]
0x14002aa2a  add     rcx, 13480h; ListHead
0x14002aa31  call    cs:__imp_ExpInterlockedPopEntrySList
0x14002aa38  nop     dword ptr [rax+rax+00h]
0x14002aa3d  mov     rbx, rax
0x14002aa40  mov     eax, [rdi+0Ch]
0x14002aa43  test    rbx, rbx
0x14002aa46  jnz     loc_14002B08A
0x14002aa4c  mov     edx, [rdi+8]
0x14002aa4f  mov     r8d, eax
0x14002aa52  mov     ecx, r14d
0x14002aa55  call    cs:__imp_WdLogSingleEntry2
0x14002aa5c  nop     dword ptr [rax+rax+00h]
0x14002aa61  mov     [rsp+50h+var_18], r12
0x14002aa66  lea     r9, aOutOfPeriodicC; "Out of Periodic Cookies, can't process "...
0x14002aa6d  mov     cs:WdLogGlobalForLineNumber, 2023h
0x14002aa77  mov     eax, [rdi+0Ch]
0x14002aa7a  mov     ecx, [rdi+8]
0x14002aa7d  mov     [rsp+50h+var_20], r12
0x14002aa82  mov     [rsp+50h+var_28], rax
0x14002aa87  mov     [rsp+50h+var_30], rcx
0x14002aa8c  mov     edx, 40000h
0x14002aa91  call    DxgkLogInternalTriageEvent
0x14002aa96  jmp     loc_14002A713
0x14002aa9b  mov     eax, [rdi+48h]
0x14002aa9e  test    r14b, al
0x14002aaa1  jz      loc_14002A73F
0x14002aaa7  cmp     edx, 7
0x14002aaaa  jz      loc_14002AC97
0x14002aab0  cmp     edx, 0Ah
0x14002aab3  jz      loc_14002AC97
0x14002aab9  cmp     edx, 12h
0x14002aabc  jz      loc_14002AC97
0x14002aac2  mov     r8d, [rdi+18h]
0x14002aac6  jmp     loc_14002AC9B
0x14002aacb  mov     eax, [r13+10h]
0x14002aacf  cmp     eax, 2
0x14002aad2  jnz     loc_14002A912
0x14002aad8  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x14002aadf  movzx   ecx, word ptr [r13+4]
0x14002aae4  mov     [rax], r14d
0x14002aae7  mov     [rsp+50h+var_28], r12
0x14002aaec  mov     r9, rsi
0x14002aaef  mov     [rsp+50h+var_30], rcx
0x14002aaf4  mov     r8, r10
0x14002aaf7  xor     ecx, ecx
0x14002aaf9  mov     edx, 119h
0x14002aafe  call    cs:__imp_WdLogSingleEntry5
0x14002ab05  nop     dword ptr [rax+rax+00h]
0x14002ab0a  mov     cs:WdLogGlobalForLineNumber, 399h
0x14002ab14  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x14002ab1b  mov     ecx, [rdi+8]
0x14002ab1e  mov     edx, [rdi+14h]
0x14002ab21  mov     r9d, [rdi+10h]
0x14002ab25  mov     [rax], r14d
0x14002ab28  mov     [rsp+50h+var_28], rcx
0x14002ab2d  xor     ecx, ecx
0x14002ab2f  mov     [rsp+50h+var_30], rdx
0x14002ab34  mov     edx, 119h
0x14002ab39  lea     r8d, [rcx+0Dh]
0x14002ab3d  call    cs:__imp_WdLogSingleEntry5
0x14002ab44  nop     dword ptr [rax+rax+00h]
0x14002ab49  mov     cs:WdLogGlobalForLineNumber, 399h
0x14002ab53  mov     eax, [rsi+2Ch]
0x14002ab56  test    r14b, al
0x14002ab59  jz      loc_14002A713
0x14002ab5f  mov     eax, [rdi+0Ch]
0x14002ab62  mov     rcx, [rsi+308h]
0x14002ab69  movzx   edx, byte ptr [rax+rsi+60h]
  ... truncated ...
```
