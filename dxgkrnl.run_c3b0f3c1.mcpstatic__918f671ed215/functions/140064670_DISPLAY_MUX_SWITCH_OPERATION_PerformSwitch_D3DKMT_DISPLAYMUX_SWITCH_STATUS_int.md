# DISPLAY_MUX_SWITCH_OPERATION::PerformSwitch(_D3DKMT_DISPLAYMUX_SWITCH_STATUS *,int *)

- ea: `0x140064670`
- end: `0x1400656f2`
- name: `?PerformSwitch@DISPLAY_MUX_SWITCH_OPERATION@@QEAAXPEAU_D3DKMT_DISPLAYMUX_SWITCH_STATUS@@PEAH@Z`
- size: `4226`
- prototype: `void __fastcall(DISPLAY_MUX_SWITCH_OPERATION *__hidden this, struct _D3DKMT_DISPLAYMUX_SWITCH_STATUS *, int *)`
- caller_count: `1`
- callee_count: `39`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140064554`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x14001bffc`
- `0x14002f75c`
- `0x14004075c`
- `0x14004094c`
- `0x140047f20`
- `0x140057440`
- `0x140064670`
- `0x140067174`
- `0x140080f14`
- `0x14008138c`
- `0x140081588`
- `0x140085b20`
- `0x140085b58`
- `0x140085bc4`
- `0x140085c0c`
- `0x1400862b0`
- `0x14008752c`
- `0x140088410`
- `0x140088594`
- `0x140088c24`
- `0x140088c74`
- `0x140088d28`
- `0x140089498`
- `0x140089654`
- `0x14008ce20`
- `0x14008ce80`
- `0x14008d44c`
- `0x14008d58c`
- `0x14008d624`
- `0x14008d6cc`
- `0x14008d7f8`
- `0x1400a0bd0`
- `0x1400a1000`
- `0x1401bff2c`
- `0x1402ba810`
- `0x1402ba900`
- `0x1402c07e4`

## import_xrefs

- `ntoskrnl!PoFxIdleComponent` at `0x140064ad7`
- `ntoskrnl!PoFxIdleComponent` at `0x140064d2c`
- `ntoskrnl!PoFxIdleComponent` at `0x140064d80`
- `ntoskrnl!PoFxIdleComponent` at `0x140064e7a`
- `ntoskrnl!PoFxIdleComponent` at `0x140064ece`
- `ntoskrnl!PoFxIdleComponent` at `0x1400650a4`
- `ntoskrnl!PoFxIdleComponent` at `0x140064ad7`
- `ntoskrnl!PoFxIdleComponent` at `0x140064d2c`
- `ntoskrnl!PoFxIdleComponent` at `0x140064d80`
- `ntoskrnl!PoFxIdleComponent` at `0x140064e7a`
- `ntoskrnl!PoFxIdleComponent` at `0x140064ece`
- `ntoskrnl!PoFxIdleComponent` at `0x1400650a4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006480e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006480e`
- `ntoskrnl!KeReleaseMutex` at `0x14006484b`
- `ntoskrnl!KeReleaseMutex` at `0x14006484b`
- `watchdog!WdLogSingleEntry2` at `0x1400652cd`
- `watchdog!WdLogSingleEntry2` at `0x140065501`
- `watchdog!WdLogSingleEntry2` at `0x140065575`
- `watchdog!WdLogSingleEntry2` at `0x1400655f2`
- `watchdog!WdLogSingleEntry2` at `0x1400652cd`
- `watchdog!WdLogSingleEntry2` at `0x140065501`
- `watchdog!WdLogSingleEntry2` at `0x140065575`
- `watchdog!WdLogSingleEntry2` at `0x1400655f2`
- `watchdog!WdLogSingleEntry0` at `0x140065657`
- `watchdog!WdLogSingleEntry0` at `0x140065657`
- `watchdog!WdLogSingleEntry5` at `0x140065193`
- `watchdog!WdLogSingleEntry5` at `0x140065203`
- `watchdog!WdLogSingleEntry5` at `0x140065238`
- `watchdog!WdLogSingleEntry5` at `0x1400652b0`
- `watchdog!WdLogSingleEntry5` at `0x1400654e4`
- `watchdog!WdLogSingleEntry5` at `0x140065558`
- `watchdog!WdLogSingleEntry5` at `0x1400655d5`
- `watchdog!WdLogSingleEntry5` at `0x14006563a`
- `watchdog!WdLogSingleEntry5` at `0x140065193`
- `watchdog!WdLogSingleEntry5` at `0x140065203`
- `watchdog!WdLogSingleEntry5` at `0x140065238`
- `watchdog!WdLogSingleEntry5` at `0x1400652b0`
- `watchdog!WdLogSingleEntry5` at `0x1400654e4`
- `watchdog!WdLogSingleEntry5` at `0x140065558`
- `watchdog!WdLogSingleEntry5` at `0x1400655d5`
- `watchdog!WdLogSingleEntry5` at `0x14006563a`
- `watchdog!WdLogSingleEntry1` at `0x1400651b0`
- `watchdog!WdLogSingleEntry1` at `0x140065258`
- `watchdog!WdLogSingleEntry1` at `0x1400651b0`
- `watchdog!WdLogSingleEntry1` at `0x140065258`

## pseudocode

```c
void __fastcall DISPLAY_MUX_SWITCH_OPERATION::PerformSwitch(
        DISPLAY_MUX_SWITCH_OPERATION *this,
        struct _D3DKMT_DISPLAYMUX_SWITCH_STATUS *a2,
        int *a3)
{
  void *v4; // r14
  char v5; // r15
  struct _LUID *v6; // r12
  bool v7; // zf
  struct _KMUTANT *v8; // r13
  struct _KMUTANT *v9; // rbx
  char v10; // al
  __int64 v11; // rbx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // r8
  int v16; // eax
  char v17; // bl
  int v18; // ecx
  int v19; // r8d
  __int64 v20; // rbx
  unsigned int v21; // edi
  __int64 v22; // rcx
  __int64 v23; // rcx
  int v24; // r8d
  unsigned int v25; // edi
  __int64 v26; // rbx
  __int64 v27; // rbx
  unsigned int v28; // edx
  char *v29; // r8
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rdx
  int v33; // eax
  char *v34; // r8
  unsigned int v35; // edi
  __int64 v36; // rbx
  __int64 v37; // rcx
  __int64 v38; // rcx
  int v39; // r8d
  __int64 v40; // rbx
  unsigned int v41; // edi
  __int64 v42; // rbx
  unsigned int v43; // edi
  __int64 v44; // rcx
  int v45; // ecx
  int v46; // r8d
  unsigned int v47; // edi
  __int64 v48; // rbx
  __int64 v49; // rcx
  bool v50; // zf
  __int64 v51; // r13
  __int64 v52; // r12
  __int64 v53; // r14
  __int64 v54; // rbx
  __int64 v55; // rax
  int v56; // edx
  int v57; // r9d
  unsigned int v58; // r8d
  int v59; // ecx
  DISPLAY_MUX_MGR *v60; // rcx
  __int64 v61; // r14
  __int64 v62; // rdi
  char v63; // al
  __int64 v64; // rdx
  __int64 v65; // rdx
  __int64 v66; // r8
  __int64 v67; // rdx
  __int64 v68; // r8
  char v69[4]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int AdapterAndAcquire; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int8 v71[2]; // [rsp+38h] [rbp-C8h] BYREF
  char v72; // [rsp+3Ch] [rbp-C4h]
  __int64 v73; // [rsp+40h] [rbp-C0h] BYREF
  char v74; // [rsp+48h] [rbp-B8h]
  struct _KMUTANT *v75; // [rsp+50h] [rbp-B0h] BYREF
  char v76; // [rsp+58h] [rbp-A8h]
  DISPLAY_MUX_SWITCH_OPERATION *v77; // [rsp+60h] [rbp-A0h] BYREF
  char v78; // [rsp+68h] [rbp-98h]
  __int64 v79; // [rsp+70h] [rbp-90h] BYREF
  int v80; // [rsp+78h] [rbp-88h]
  int v81; // [rsp+7Ch] [rbp-84h]
  __int128 v82; // [rsp+80h] [rbp-80h]
  char v83; // [rsp+90h] [rbp-70h]
  unsigned int v84; // [rsp+98h] [rbp-68h] BYREF
  __int64 v85; // [rsp+A0h] [rbp-60h] BYREF
  int v86; // [rsp+A8h] [rbp-58h]
  int v87; // [rsp+ACh] [rbp-54h]
  __int128 v88; // [rsp+B0h] [rbp-50h]
  char v89; // [rsp+C0h] [rbp-40h]
  _QWORD v90[3]; // [rsp+C8h] [rbp-38h] BYREF
  char v91; // [rsp+E0h] [rbp-20h]
  struct _DEVICE_OBJECT *v92; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v93; // [rsp+F0h] [rbp-10h]
  unsigned int v94; // [rsp+108h] [rbp+8h]
  unsigned int v95; // [rsp+118h] [rbp+18h]
  DISPLAY_MUX_SWITCH_OPERATION *v96; // [rsp+120h] [rbp+20h] BYREF
  struct _DEVICE_OBJECT **v97; // [rsp+128h] [rbp+28h]
  char v98; // [rsp+130h] [rbp+30h]
  int v99; // [rsp+138h] [rbp+38h]
  void *v100; // [rsp+140h] [rbp+40h] BYREF
  int v101; // [rsp+148h] [rbp+48h]
  __int64 v102; // [rsp+150h] [rbp+50h] BYREF
  _OWORD *v103; // [rsp+158h] [rbp+58h]
  int *v104; // [rsp+160h] [rbp+60h]
  _OWORD v105[15]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v106[224]; // [rsp+260h] [rbp+160h] BYREF
  struct _D3DKMT_DISPLAYMUX_SWITCH_STATUS *v107; // [rsp+398h] [rbp+298h] BYREF

  v107 = a2;
  v104 = a3;
  AdapterAndAcquire = 0;
  v102 = 0;
  v84 = 0;
  v4 = 0;
  v105[0] = 0;
  MINIPORT_LIST_AUTO_LOCK::MINIPORT_LIST_AUTO_LOCK((MINIPORT_LIST_AUTO_LOCK *)v69, (bool)a2);
  v5 = byte_140163579;
  v6 = (struct _LUID *)((char *)this + 68);
  v75 = 0;
  v76 = 0;
  AdapterAndAcquire = AUTO_REMOVE_LOCK::FindAdapterAndAcquire(
                        (AUTO_REMOVE_LOCK *)&v75,
                        (struct _LUID *)((char *)this + 68));
  if ( (unsigned __int8)CheckFailed(AdapterAndAcquire, 1044, (char *)this + 92, 542) )
    goto LABEL_2;
  v73 = 0;
  v74 = 0;
  AdapterAndAcquire = AUTO_REMOVE_LOCK::FindAdapterAndAcquire((AUTO_REMOVE_LOCK *)&v73, (struct _LUID *)this + 10);
  if ( (unsigned __int8)CheckFailed(AdapterAndAcquire, 1045, (char *)this + 92, 550) )
  {
    AUTO_REMOVE_LOCK::Release((AUTO_REMOVE_LOCK *)&v73);
LABEL_2:
    AUTO_REMOVE_LOCK::Release((AUTO_REMOVE_LOCK *)&v75);
    v7 = v69[0] == 0;
    goto LABEL_62;
  }
  v77 = this;
  v85 = 0;
  v87 = -1;
  v81 = -1;
  v78 = 1;
  v86 = 0;
  v88 = 0;
  v89 = 0;
  v79 = 0;
  v80 = 0;
  v82 = 0;
  v83 = 0;
  DISPLAY_MUX_MGR::SetDisableProcessingDisplayBatchesStatus(qword_1401634C8, 1);
  v90[1] = this;
  v90[0] = &AdapterAndAcquire;
  v91 = 1;
  v90[2] = &v107;
  v99 = 0;
  *(_WORD *)v71 = 0;
  memset((char *)&v105[1] + 8, 0, 0xD1u);
  v8 = v75;
  v9 = v75 + 81;
  KeWaitForSingleObject(&v75[81], Executive, 0, 0, 0);
  v7 = *(_WORD *)(&v8[85].ApcDisable + 1) == 3;
  v95 = *(_DWORD *)&v8[80].Abandoned;
  v10 = BYTE8(v105[1]);
  if ( v7 )
    v10 = 1;
  BYTE8(v105[1]) = v10;
  KeReleaseMutex(v9, 0);
  CInterfaceCallContext::CInterfaceCallContext(&v92, v73);
  if ( (unsigned __int8)CheckFailed(v94, 1028, (char *)this + 92, 614) )
    goto LABEL_14;
  v11 = v93;
  if ( !*(_BYTE *)(v93 + 6441) )
  {
    memset(v106, 0, 0xD1u);
    if ( !DISPLAY_MUX_MGR::GetInternalPanelInfo(
            qword_1401634C8,
            (struct _DXGK_DISPLAYMUX_SET_INTERNAL_PANEL_INFO *)v106) )
    {
      CheckFailed(3221225473LL, 1051, (char *)this + 92, 637);
      goto LABEL_14;
    }
    AdapterAndAcquire = DpiDxgkDdiDisplayMuxSetInternalPanelInfo(v11, *((unsigned int *)this + 22), v106);
    if ( (unsigned __int8)CheckFailed(v94, 1049, (char *)this + 92, 628) )
    {
LABEL_14:
      CInterfaceCallContext::~CInterfaceCallContext((CInterfaceCallContext *)&v92);
      DXGKCALLONEXIT__lambda_5bf16074e78eca97c9745c10e52e39f7____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(v90);
      DXGKCALLONEXIT__lambda_8e64b2d4059ca463867f9c5833a46b2d____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(&v77);
      AUTO_REMOVE_LOCK::Release((AUTO_REMOVE_LOCK *)&v73);
      AUTO_REMOVE_LOCK::Release((AUTO_REMOVE_LOCK *)&v75);
      v7 = v69[0] == 0;
      goto LABEL_62;
    }
    *(_BYTE *)(v11 + 6441) = 1;
  }
  if ( (unsigned __int8)CheckForMdmFaultOrDelayInjection(4, 1027, (char *)this + 92) )
    goto LABEL_14;
  v12 = *((_DWORD *)this + 22);
  v13 = *(_QWORD *)(v11 + 4032);
  v100 = (void *)*((_QWORD *)this + 10);
  v101 = v12;
  TARGET_POWER_REFERENCE::TakePowerReference(&v79, v13, &v100);
  v14 = *((unsigned int *)this + 22);
  v15 = v95;
  *(_QWORD *)((char *)this + 20) = *((_QWORD *)this + 10);
  *((_DWORD *)this + 7) = v14;
  v16 = DpiDxgkDdiDisplayMuxPreSwitchTo(v11, v14, v15);
  if ( v16 >= 0 )
    *((_DWORD *)this + 1) = 2;
  AdapterAndAcquire = v16;
  if ( (unsigned __int8)CheckFailed((unsigned int)v16, 1027, (char *)this + 92, 653) )
  {
    CInterfaceCallContext::~CInterfaceCallContext((CInterfaceCallContext *)&v92);
    goto LABEL_25;
  }
  v17 = *(_BYTE *)(v11 + 6440);
  v72 = v17;
  CInterfaceCallContext::~CInterfaceCallContext((CInterfaceCallContext *)&v92);
  if ( !v17 )
  {
    if ( BYTE8(v105[1])
      && ((AdapterAndAcquire = DpiBrightness3GetCaps(
                                 v8->MutantListEntry.Flink,
                                 *((_DWORD *)this + 19),
                                 (struct _DXGK_BRIGHTNESS_CAPS *)((char *)&v105[1] + 9)),
           (unsigned __int8)CheckFailed(AdapterAndAcquire, 1046, (char *)this + 92, 672))
       || (AdapterAndAcquire = DpiBrightness3GetNitRanges(
                                 v8->MutantListEntry.Flink,
                                 *((_DWORD *)this + 19),
                                 (struct _DXGK_BRIGHTNESS_GET_NIT_RANGES_OUT *)((char *)&v105[1] + 13)),
           (unsigned __int8)CheckFailed(AdapterAndAcquire, 1047, (char *)this + 92, 678)))
      || (AdapterAndAcquire = DpiGetIntegratedEdidSizeForDisplayMuxTarget(
                                v8->MutantListEntry.Flink,
                                *((unsigned int *)this + 19),
                                v71),
          (unsigned __int8)CheckFailed(AdapterAndAcquire, 1047, (char *)this + 92, 686)) )
    {
LABEL_25:
      DXGKCALLONEXIT__lambda_5bf16074e78eca97c9745c10e52e39f7____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(v90);
      if ( v83 )
      {
        v20 = v82;
        v21 = v81;
        if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
          McTemplateK0pqq_EtwWriteTransfer(v18, (unsigned int)Dxgk_ReportPowerComponentState, v19, v82, v81, 0);
        v22 = *(_QWORD *)(v20 + 3360);
        if ( v22 )
          PoFxIdleComponent(v22, v21, 0);
      }
      goto LABEL_61;
    }
    v99 = *(unsigned __int16 *)v71;
  }
  CInterfaceCallContext::CInterfaceCallContext(&v92, v8);
  if ( (unsigned __int8)CheckFailed(v94, 1029, (char *)this + 92, 696) )
    goto LABEL_34;
  v27 = v93;
  v28 = *((_DWORD *)this + 19);
  v71[0] = 0;
  AdapterAndAcquire = MonitorIsMonitorConnected(*(void **)(v93 + 4032), v28, 1u, v71);
  if ( (unsigned __int8)CheckFailed(AdapterAndAcquire, 1025, (char *)this + 92, 704) )
    goto LABEL_34;
  v29 = (char *)this + 92;
  if ( !v71[0] )
  {
    CheckFailed(3221226021LL, 1026, v29, 710);
LABEL_34:
    CInterfaceCallContext::~CInterfaceCallContext((CInterfaceCallContext *)&v92);
    DXGKCALLONEXIT__lambda_5bf16074e78eca97c9745c10e52e39f7____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(v90);
    if ( !v83 )
    {
LABEL_61:
      DXGKCALLONEXIT__lambda_8e64b2d4059ca463867f9c5833a46b2d____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(&v77);
      AUTO_REMOVE_LOCK::Release((AUTO_REMOVE_LOCK *)&v73);
      AUTO_REMOVE_LOCK::Release((AUTO_REMOVE_LOCK *)&v75);
      v7 = v69[0] == 0;
LABEL_62:
      if ( !v7 )
        ReleaseMiniportListMutex();
      return;
    }
    v25 = v81;
    v26 = v82;
LABEL_56:
    if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
      McTemplateK0pqq_EtwWriteTransfer(v23, (unsigned int)Dxgk_ReportPowerComponentState, v24, v26, v25, 0);
    v37 = *(_QWORD *)(v26 + 3360);
    if ( v37 )
      PoFxIdleComponent(v37, v25, 0);
    goto LABEL_61;
  }
  if ( (unsigned __int8)CheckForMdmFaultOrDelayInjection(5, 1030, v29) )
    goto LABEL_34;
  v30 = *((_DWORD *)this + 19);
  v31 = *(_QWORD *)(v27 + 4032);
  v100 = *(void **)((char *)this + 68);
  v101 = v30;
  TARGET_POWER_REFERENCE::TakePowerReference(&v85, v31, &v100);
  AdapterAndAcquire = DISPLAY_MUX_MGR::SetDisableQueryConnectionDdiStatus(qword_1401634C8, *v6, 1);
  if ( (unsigned __int8)CheckFailed(AdapterAndAcquire, 1030, (char *)this + 92, 727) )
  {
LABEL_48:
    CInterfaceCallContext::~CInterfaceCallContext((CInterfaceCallContext *)&v92);
    DXGKCALLONEXIT__lambda_5bf16074e78eca97c9745c10e52e39f7____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(v90);
    if ( v83 )
    {
      v35 = v81;
      v36 = v82;
      if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
        McTemplateK0pqq_EtwWriteTransfer(v23, (unsigned int)Dxgk_ReportPowerComponentState, v24, v82, v81, 0);
      v23 = *(_QWORD *)(v36 + 3360);
      if ( v23 )
        PoFxIdleComponent(v23, v35, 0);
    }
    if ( !v89 )
      goto LABEL_61;
    v25 = v87;
    v26 = v88;
    goto LABEL_56;
  }
  v96 = this;
  LOBYTE(v97) = 1;
  if ( (unsigned __int8)CheckForMdmFaultOrDelayInjection(6, 1031, (char *)this + 92) )
    goto LABEL_47;
  v32 = *((unsigned int *)this + 19);
  *((_QWORD *)this + 1) = *(_QWORD *)((char *)this + 68);
  *((_DWORD *)this + 4) = v32;
  v33 = DpiDxgkDdiDisplayMuxPreSwitchAway(v27, v32, &v84);
  if ( v33 >= 0 )
    *(_DWORD *)this = 2;
  AdapterAndAcquire = v33;
  if ( (unsigned __int8)CheckFailed((unsigned int)v33, 1031, (char *)this + 92, 744) )
  {
LABEL_47:
    DXGKCALLONEXIT__lambda_b3b73720c9a5b94f1e3275d94b86d9de____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(&v96);
    goto LABEL_48;
  }
  DISPLAY_MUX_MGR::SetAdapterAllowedToReportDisplayMuxHpd(
    qword_1401634C8,
    (DISPLAY_MUX_SWITCH_OPERATION *)((char *)this + 68));
  v34 = (char *)this + 92;
  if ( v84 > 0x100000 )
  {
    CheckFailed(3221225990LL, 1032, v34, 755);
    goto LABEL_47;
  }
  if ( (unsigned __int8)CheckForMdmFaultOrDelayInjection(7, 1034, v34) )
    goto LABEL_47;
  if ( v84 )
  {
    v102 = operator new[](v84, 0x4B677844u, 256);
    v4 = (void *)v102;
    if ( !v102 )
    {
      CheckFailed(3221225495LL, 1033, (char *)this + 92, 772);
LABEL_68:
      DXGKCALLONEXIT__lambda_b3b73720c9a5b94f1e3275d94b86d9de____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(&v96);
      CInterfaceCallContext::~CInterfaceCallContext((CInterfaceCallContext *)&v92);
      DXGKCALLONEXIT__lambda_5bf16074e78eca97c9745c10e52e39f7____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(v90);
      if ( v83 )
      {
        v40 = v82;
        v41 = v81;
        if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
          McTemplateK0pqq_EtwWriteTransfer(v38, (unsigned int)Dxgk_ReportPowerComponentState, v39, v82, v81, 0);
        v38 = *(_QWORD *)(v40 + 3360);
        if ( v38 )
          PoFxIdleComponent(v38, v41, 0);
      }
      if ( v89 )
      {
        v42 = v88;
        v43 = v87;
        if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
          McTemplateK0pqq_EtwWriteTransfer(v38, (unsigned int)Dxgk_ReportPowerComponentState, v39, v88, v87, 0);
        v44 = *(_QWORD *)(v42 + 3360);
        if ( v44 )
          PoFxIdleComponent(v44, v43, 0);
      }
      DXGKCALLONEXIT__lambda_8e64b2d4059ca463867f9c5833a46b2d____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(&v77);
      AUTO_REMOVE_LOCK::Release((AUTO_REMOVE_LOCK *)&v73);
      AUTO_REMOVE_LOCK::Release((AUTO_REMOVE_LOCK *)&v75);
      if ( v69[0] )
        ReleaseMiniportListMutex();
      if ( v4 )
        DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v4);
      return;
    }
    AdapterAndAcquire = DpiDxgkDdiDisplayMuxPreSwitchAwayGetPrivateData(
                          v27,
                          *((_DWORD *)this + 19),
                          v84,
                          v102,
                          (__int64)v105);
    if ( (unsigned __int8)CheckFailed(AdapterAndAcquire, 1034, (char *)this + 92, 782) )
      goto LABEL_68;
    v100 = v4;
    v103 = v105;
  }
  else
  {
    v103 = 0;
    v100 = 0;
  }
  if ( (unsigned __int8)CheckForMdmFaultOrDelayInjection(8, 1035, (char *)this + 92) )
    goto LABEL_68;
  AdapterAndAcquire = DISPLAY_MUX_MGR::SwitchMux(
                        qword_1401634C8,
                        *(struct _LUID *)((char *)this + 80),
                        *((_DWORD *)this + 22));
  if ( (unsigned __int8)CheckFailed(AdapterAndAcquire, 1035, (char *)this + 92, 798) )
    goto LABEL_68;
  if ( !*(_BYTE *)(v27 + 2716) )
    qword_1401631A8 = *(_QWORD *)(v73 + 24);
  if ( (unsigned __int8)CheckForMdmFaultOrDelayInjection(9, 1037, (char *)this + 92) )
    goto LABEL_68;
  AdapterAndAcquire = DISPLAY_MUX_MGR::SetDisableQueryConnectionDdiStatus(qword_1401634C8, *v6, 0);
  if ( (unsigned __int8)CheckFailed(AdapterAndAcquire, 1037, (char *)this + 92, 817) )
    goto LABEL_68;
  DXGKCALLONEXIT__lambda_b3b73720c9a5b94f1e3275d94b86d9de____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(&v96);
  if ( (unsigned __int8)CheckForMdmFaultOrDelayInjection(10, 1038, (char *)this + 92) )
  {
    CInterfaceCallContext::~CInterfaceCallContext((CInterfaceCallContext *)&v92);
    DXGKCALLONEXIT__lambda_5bf16074e78eca97c9745c10e52e39f7____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(v90);
    if ( v83 )
    {
      v47 = v81;
      v48 = v82;
      if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
        McTemplateK0pqq_EtwWriteTransfer(v45, (unsigned int)Dxgk_ReportPowerComponentState, v46, v82, v81, 0);
      v49 = *(_QWORD *)(v48 + 3360);
      if ( v49 )
        PoFxIdleComponent(v49, v47, 0);
    }
  }
  else
  {
    AdapterAndAcquire = QueryConnectionChanges(
                          v92,
                          *(struct _LUID *)((char *)this + 68),
                          (struct _GUID *)((char *)this + 92),
                          (struct _GUID *)((char *)this + 108));
    DISPLAY_MUX_MGR::SetAdapterAllowedToReportDisplayMuxHpd(qword_1401634C8, 0);
    if ( !(unsigned __int8)CheckFailed(AdapterAndAcquire, 1038, (char *)this + 92, 832) )
    {
      v51 = *((unsigned int *)qword_1401634C8 + 32);
      v52 = *((unsigned int *)qword_1401634C8 + 29);
      v53 = *((unsigned int *)qword_1401634C8 + 31);
      v54 = *((unsigned int *)qword_1401634C8 + 33);
      v95 = *((_DWORD *)qword_1401634C8 + 30);
      if ( (_DWORD)v51 )
      {
        v5 |= (unsigned __int8)((__int64 (*)(void))DpiAcpiIsLidOpen)() == 0;
        if ( v5 )
        {
          WdLogSingleEntry1(2, (unsigned int)v51);
          WdLogGlobalForLineNumber = 855;
        }
        else
        {
          WdLogSingleEntry5(0, 484, 52, 2, (unsigned int)v51, 0);
          WdLogGlobalForLineNumber = 851;
        }
      }
      if ( (_DWORD)v54 != 1 )
      {
        v5 |= (unsigned __int8)((__int64 (*)(void))DpiAcpiIsLidOpen)() == 0;
        if ( v5 )
        {
          WdLogSingleEntry1(2, v54);
          WdLogGlobalForLineNumber = 886;
        }
        else if ( (_DWORD)v54 )
        {
          WdLogSingleEntry5(0, 484, 52, 3, v54, 0);
          WdLogGlobalForLineNumber = 881;
        }
        else
        {
          WdLogSingleEntry5(0, 484, 52, 3, 0, 0);
          WdLogGlobalForLineNumber = 874;
        }
      }
      if ( *((_DWORD *)this + 17) != (_DWORD)v52
        || *((_DWORD *)this + 18) != v95
        || *((_DWORD *)this + 19) != (_DWORD)v53 )
      {
        v5 |= (unsigned __int8)((__int64 (*)(void))DpiAcpiIsLidOpen)() == 0;
        if ( v5 )
        {
          WdLogSingleEntry2(2, v52, v53);
          WdLogGlobalForLineNumber = 910;
        }
        else
        {
          WdLogSingleEntry5(0, 484, 52, 4, v52, v53);
          WdLogGlobalForLineNumber = 904;
        }
      }
      CInterfaceCallContext::~CInterfaceCallContext((CInterfaceCallContext *)&v92);
      CInterfaceCallContext::CInterfaceCallContext(&v92, v73);
      if ( !(unsigned __int8)CheckFailed(v94, 1039, (char *)this + 92, 919)
        && !(unsigned __int8)CheckForMdmFaultOrDelayInjection(11, 1040, (char *)this + 92) )
      {
        if ( v72
          || (AdapterAndAcquire = DpiSetIntegratedEdidSizeForDisplayMuxTarget(
                                    v92,
                                    *((unsigned int *)this + 22),
                                    (unsigned __int16)v99),
              !(unsigned __int8)CheckFailed(v94, 1050, (char *)this + 92, 934)) )
        {
          if ( !(unsigned __int8)CheckForMdmFaultOrDelayInjection(12, 1041, (char *)this + 92) )
          {
            v55 = (__int64)v103;
            v56 = *((_DWORD *)this + 22);
            v57 = (int)v100;
            v58 = v84;
            v59 = v93;
            *((_BYTE *)this + 32) = 1;
            AdapterAndAcquire = DpiDxgkDdiDisplayMuxPostSwitchToPhase1(v59, v56, v58, v57, v55);
            if ( !(unsigned __int8)CheckFailed(AdapterAndAcquire, 1041, (char *)this + 92, 952) )
            {
              v97 = &v92;
              v96 = this;
              v98 = 1;
              AdapterAndAcquire = DpiQueryIntegratedDescriptorWrapper(v92);
              if ( (unsigned __int8)CheckFailed(AdapterAndAcquire, 1040, (char *)this + 92, 978)
                || (unsigned __int8)CheckForMdmFaultOrDelayInjection(13, 1042, (char *)this + 92) )
              {
                DXGKCALLONEXIT__lambda_81c4496798e6cbc83c2bde0911ff3b32____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(&v96);
              }
              else
              {
                DXGKCALLONEXIT__lambda_81c4496798e6cbc83c2bde0911ff3b32____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(&v96);
                DISPLAY_MUX_MGR::SetAdapterAllowedToReportDisplayMuxHpd(
                  qword_1401634C8,
                  (DISPLAY_MUX_SWITCH_OPERATION *)((char *)this + 80));
                AdapterAndAcquire = QueryConnectionChanges(
                                      v92,
                                      *(struct _LUID *)((char *)this + 80),
                                      (struct _GUID *)((char *)this + 92),
                                      (struct _GUID *)((char *)this + 108));
                DISPLAY_MUX_MGR::SetAdapterAllowedToReportDisplayMuxHpd(qword_1401634C8, 0);
                if ( !(unsigned __int8)CheckFailed(AdapterAndAcquire, 1042, (char *)this + 92, 995) )
                {
                  v60 = qword_1401634C8;
                  v61 = *((unsigned int *)qword_1401634C8 + 32);
                  v62 = *((unsigned int *)qword_1401634C8 + 33);
                  if ( *((_DWORD *)this + 20) != *((_DWORD *)qword_1401634C8 + 29)
                    || *((_DWORD *)this + 21) != *((_DWORD *)qword_1401634C8 + 30)
                    || *((_DWORD *)this + 22) != *((_DWORD *)qword_1401634C8 + 31) )
                  {
                    v63 = ((__int64 (*)(void))DpiAcpiIsLidOpen)();
                    v64 = *((unsigned int *)this + 20);
                    v5 |= v63 == 0;
                    if ( v5 )
                    {
                      WdLogSingleEntry2(2, v64, *((unsigned int *)this + 22));
                      WdLogGlobalForLineNumber = 1023;
                    }
                    else
                    {
                      WdLogSingleEntry5(0, 484, 52, 1, v64, *((unsigned int *)this + 22));
                      WdLogGlobalForLineNumber = 1017;
                    }
                  }
                  if ( (_DWORD)v62 == (_DWORD)v54 )
                  {
                    if ( (_DWORD)v61 != (_DWORD)v51 + 1 )
                    {
                      if ( (unsigned __int8)v5 | ((unsigned __int8)DpiAcpiIsLidOpen(v60, v61, v51) == 0) )
                      {
                        WdLogSingleEntry2(2, v65, v66);
                        WdLogGlobalForLineNumber = 1048;
                      }
                      else
                      {
                        WdLogSingleEntry5(0, 484, 52, 5, v51, v65);
                        WdLogGlobalForLineNumber = 1042;
                      }
                    }
                    *v104 = 1;
                  }
                  else if ( (_DWORD)v61 == (_DWORD)v51 )
                  {
                    if ( (_DWORD)v62 != (_DWORD)v54 + 1 )
                    {
                      if ( (unsigned __int8)v5 | ((unsigned __int8)DpiAcpiIsLidOpen(v60, v62, v54) == 0) )
                      {
                        WdLogSingleEntry2(2, v67, v68);
                        WdLogGlobalForLineNumber = 1075;
                      }
                      else
                      {
                        WdLogSingleEntry5(0, 484, 52, 6, v54, v67);
                        WdLogGlobalForLineNumber = 1069;
                      }
                    }
                    *v104 = 0;
                  }
                  else if ( (unsigned __int8)v5 | ((unsigned __int8)((__int64 (*)(void))DpiAcpiIsLidOpen)() == 0) )
                  {
                    WdLogSingleEntry0(2);
                    WdLogGlobalForLineNumber = 1096;
                  }
                  else
                  {
                    WdLogSingleEntry5(0, 484, 52, 7, 0, 0);
                    WdLogGlobalForLineNumber = 1092;
                  }
                }
              }
            }
          }
        }
      }
      CInterfaceCallContext::~CInterfaceCallContext((CInterfaceCallContext *)&v92);
      DXGKCALLONEXIT__lambda_5bf16074e78eca97c9745c10e52e39f7____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(v90);
      TARGET_POWER_REFERENCE::ReleaseReference((TARGET_POWER_REFERENCE *)&v79);
      TARGET_POWER_REFERENCE::ReleaseReference((TARGET_POWER_REFERENCE *)&v85);
      DXGKCALLONEXIT__lambda_8e64b2d4059ca463867f9c5833a46b2d____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(&v77);
      AUTO_REMOVE_LOCK::Release((AUTO_REMOVE_LOCK *)&v73);
      AUTO_REMOVE_LOCK::Release((AUTO_REMOVE_LOCK *)&v75);
      v50 = v69[0] == 0;
      goto LABEL_151;
    }
    CInterfaceCallContext::~CInterfaceCallContext((CInterfaceCallContext *)&v92);
    DXGKCALLONEXIT__lambda_5bf16074e78eca97c9745c10e52e39f7____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(v90);
    TARGET_POWER_REFERENCE::ReleaseReference((TARGET_POWER_REFERENCE *)&v79);
  }
  TARGET_POWER_REFERENCE::ReleaseReference((TARGET_POWER_REFERENCE *)&v85);
  DXGKCALLONEXIT__lambda_8e64b2d4059ca463867f9c5833a46b2d____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(&v77);
  AUTO_REMOVE_LOCK::Release((AUTO_REMOVE_LOCK *)&v73);
  AUTO_REMOVE_LOCK::Release((AUTO_REMOVE_LOCK *)&v75);
  v50 = v69[0] == 0;
LABEL_151:
  if ( !v50 )
    ReleaseMiniportListMutex();
  wistd::unique_ptr<_KEY_VALUE_PARTIAL_INFORMATION,DxgMonitor::byte_array_deleter<_KEY_VALUE_PARTIAL_INFORMATION>>::reset(
    &v102,
    0);
}

```

## disassembly

```asm
0x140064670  mov     [rsp-8+arg_18], rbx
0x140064675  mov     [rsp-8+arg_8], rdx
0x14006467a  push    rbp
0x14006467b  push    rsi
0x14006467c  push    rdi
0x14006467d  push    r12
0x14006467f  push    r13
0x140064681  push    r14
0x140064683  push    r15
0x140064685  lea     rbp, [rsp-250h]
0x14006468d  sub     rsp, 350h
0x140064694  mov     rax, cs:__security_cookie
0x14006469b  xor     rax, rsp
0x14006469e  mov     [rbp+280h+var_40], rax
0x1400646a5  xor     ebx, ebx
0x1400646a7  mov     [rbp+280h+var_220], r8
0x1400646ab  mov     rsi, rcx
0x1400646ae  mov     [rsp+380h+var_34C], ebx
0x1400646b2  xorps   xmm0, xmm0
0x1400646b5  mov     [rbp+280h+var_230], rbx
0x1400646b9  lea     rcx, [rsp+380h+var_350]; this
0x1400646be  mov     [rbp+280h+var_2E8], ebx
0x1400646c1  mov     r14d, ebx
0x1400646c4  movups  [rbp+280h+var_218], xmm0
0x1400646c8  call    ??0MINIPORT_LIST_AUTO_LOCK@@QEAA@_N@Z; MINIPORT_LIST_AUTO_LOCK::MINIPORT_LIST_AUTO_LOCK(bool)
0x1400646cd  mov     r15b, cs:byte_140163579
0x1400646d4  lea     r12, [rsi+44h]
0x1400646d8  mov     rdx, r12; struct _LUID *
0x1400646db  mov     [rsp+380h+var_330], rbx
0x1400646e0  lea     rcx, [rsp+380h+var_330]; this
0x1400646e5  mov     [rsp+380h+var_328], bl
0x1400646e9  call    ?FindAdapterAndAcquire@AUTO_REMOVE_LOCK@@QEAAJPEAU_LUID@@@Z; AUTO_REMOVE_LOCK::FindAdapterAndAcquire(_LUID *)
0x1400646ee  lea     rdi, [rsi+5Ch]
0x1400646f2  mov     [rsp+380h+var_34C], eax
0x1400646f6  mov     r8, rdi
0x1400646f9  mov     r9d, 21Eh
0x1400646ff  mov     edx, 414h
0x140064704  mov     ecx, eax
0x140064706  call    ?CheckFailed@@YA_NJW4_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE@@AEAU_DISPLAYMUX_SWITCH_CONTEXT@@IPEAD@Z; CheckFailed(long,_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE,_DISPLAYMUX_SWITCH_CONTEXT &,uint,char *)
0x14006470b  test    al, al
0x14006470d  jz      short loc_140064722
0x14006470f  lea     rcx, [rsp+380h+var_330]; this
0x140064714  call    ?Release@AUTO_REMOVE_LOCK@@QEAAXXZ; AUTO_REMOVE_LOCK::Release(void)
0x140064719  cmp     [rsp+380h+var_350], bl
0x14006471d  jmp     loc_140064DAF
0x140064722  lea     rdx, [rsi+50h]; struct _LUID *
0x140064726  mov     [rsp+380h+var_340], rbx
0x14006472b  lea     rcx, [rsp+380h+var_340]; this
0x140064730  mov     [rsp+380h+var_338], bl
0x140064734  call    ?FindAdapterAndAcquire@AUTO_REMOVE_LOCK@@QEAAJPEAU_LUID@@@Z; AUTO_REMOVE_LOCK::FindAdapterAndAcquire(_LUID *)
0x140064739  mov     r9d, 226h
0x14006473f  mov     [rsp+380h+var_34C], eax
0x140064743  mov     r8, rdi
0x140064746  mov     edx, 415h
0x14006474b  mov     ecx, eax
0x14006474d  call    ?CheckFailed@@YA_NJW4_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE@@AEAU_DISPLAYMUX_SWITCH_CONTEXT@@IPEAD@Z; CheckFailed(long,_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE,_DISPLAYMUX_SWITCH_CONTEXT &,uint,char *)
0x140064752  test    al, al
0x140064754  jz      short loc_14006476C
0x140064756  lea     rcx, [rsp+380h+var_340]; this
0x14006475b  call    ?Release@AUTO_REMOVE_LOCK@@QEAAXXZ; AUTO_REMOVE_LOCK::Release(void)
0x140064760  jmp     short loc_14006470F
0x140064762  call    ?ReleaseMiniportListMutex@@YAXXZ; ReleaseMiniportListMutex(void)
0x140064767  jmp     loc_1400656C7
0x14006476c  xor     eax, eax
0x14006476e  mov     [rsp+380h+var_320], rsi
0x140064773  or      ecx, 0FFFFFFFFh
0x140064776  mov     [rbp+280h+var_2E0], rax
0x14006477a  xorps   xmm0, xmm0
0x14006477d  mov     [rbp+280h+var_2D4], ecx
0x140064780  mov     r13d, 1
0x140064786  mov     [rsp+380h+var_304], ecx
0x14006478a  mov     rcx, cs:qword_1401634C8; this
0x140064791  mov     dl, r13b; bool
0x140064794  mov     [rsp+380h+var_318], r13b
0x140064799  mov     [rbp+280h+var_2D8], eax
0x14006479c  movdqu  [rbp+280h+var_2D0], xmm0
0x1400647a1  mov     [rbp+280h+var_2C0], bl
0x1400647a4  mov     [rsp+380h+var_310], rax
0x1400647a9  mov     [rsp+380h+var_308], eax
0x1400647ad  movdqu  [rbp+280h+var_300], xmm0
0x1400647b2  mov     [rbp+280h+var_2F0], bl
0x1400647b5  call    ?SetDisableProcessingDisplayBatchesStatus@DISPLAY_MUX_MGR@@QEAAX_N@Z; DISPLAY_MUX_MGR::SetDisableProcessingDisplayBatchesStatus(bool)
0x1400647ba  lea     rax, [rsp+380h+var_34C]
0x1400647bf  mov     [rbp+280h+var_2B0], rsi
0x1400647c3  mov     [rbp+280h+var_2B8], rax
0x1400647c7  lea     rcx, [rbp+280h+var_200]; void *
0x1400647ce  lea     rax, [rbp+280h+arg_8]
0x1400647d5  mov     [rbp+280h+var_2A0], r13b
0x1400647d9  xor     edx, edx; Val
0x1400647db  mov     [rbp+280h+var_2A8], rax
0x1400647df  mov     r8d, 0D1h; Size
0x1400647e5  mov     [rbp+280h+var_248], ebx
0x1400647e8  mov     word ptr [rsp+380h+var_348], bx
0x1400647ed  call    memset
0x1400647f2  mov     r13, [rsp+380h+var_330]
0x1400647f7  xor     r9d, r9d; Alertable
0x1400647fa  xor     r8d, r8d; WaitMode
0x1400647fd  mov     [rsp+380h+Timeout], r14; Timeout
0x140064802  xor     edx, edx; WaitReason
0x140064804  lea     rbx, [r13+11B8h]
0x14006480b  mov     rcx, rbx; Object
0x14006480e  call    cs:__imp_KeWaitForSingleObject
0x140064815  nop     dword ptr [rax+rax+00h]
0x14006481a  mov     eax, [r13+11B0h]
0x140064821  mov     ecx, 3
0x140064826  cmp     [r13+12CAh], cx
0x14006482e  mov     ecx, 1
0x140064833  mov     [rbp+280h+var_268], eax
0x140064836  movzx   eax, [rbp+280h+var_200]
0x14006483d  cmovz   eax, ecx
0x140064840  xor     edx, edx; Wait
0x140064842  mov     rcx, rbx; Mutex
0x140064845  mov     [rbp+280h+var_200], al
0x14006484b  call    cs:__imp_KeReleaseMutex
0x140064852  nop     dword ptr [rax+rax+00h]
0x140064857  mov     rdx, [rsp+380h+var_340]
0x14006485c  lea     rcx, [rbp+280h+var_298]
0x140064860  call    ??0CInterfaceCallContext@@QEAA@PEAU_FDO_CONTEXT@@W4LocksToAcquire@@@Z; CInterfaceCallContext::CInterfaceCallContext(_FDO_CONTEXT *,LocksToAcquire)
0x140064865  mov     ecx, [rbp+280h+var_278]
0x140064868  mov     r9d, 266h
0x14006486e  mov     r8, rdi
0x140064871  mov     edx, 404h
0x140064876  call    ?CheckFailed@@YA_NJW4_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE@@AEAU_DISPLAYMUX_SWITCH_CONTEXT@@IPEAD@Z; CheckFailed(long,_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE,_DISPLAYMUX_SWITCH_CONTEXT &,uint,char *)
0x14006487b  test    al, al
0x14006487d  jnz     loc_14006490C
0x140064883  mov     rbx, [rbp+280h+var_290]
0x140064887  cmp     [rbx+1929h], r14b
0x14006488e  jnz     short loc_1400648F6
0x140064890  xor     edx, edx; Val
0x140064892  lea     rcx, [rbp+280h+var_120]; void *
0x140064899  mov     r8d, 0D1h; Size
0x14006489f  call    memset
0x1400648a4  mov     rcx, cs:qword_1401634C8; this
0x1400648ab  lea     rdx, [rbp+280h+var_120]; struct _DXGK_DISPLAYMUX_SET_INTERNAL_PANEL_INFO *
0x1400648b2  call    ?GetInternalPanelInfo@DISPLAY_MUX_MGR@@QEBA_NPEAU_DXGK_DISPLAYMUX_SET_INTERNAL_PANEL_INFO@@@Z; DISPLAY_MUX_MGR::GetInternalPanelInfo(_DXGK_DISPLAYMUX_SET_INTERNAL_PANEL_INFO *)
0x1400648b7  test    al, al
0x1400648b9  jz      loc_140064946
0x1400648bf  mov     edx, [rsi+58h]
0x1400648c2  lea     r8, [rbp+280h+var_120]
0x1400648c9  mov     rcx, rbx
0x1400648cc  call    DpiDxgkDdiDisplayMuxSetInternalPanelInfo
0x1400648d1  mov     ecx, [rbp+280h+var_278]
0x1400648d4  mov     r9d, 274h
0x1400648da  mov     r8, rdi
0x1400648dd  mov     [rsp+380h+var_34C], eax
0x1400648e1  mov     edx, 419h
0x1400648e6  call    ?CheckFailed@@YA_NJW4_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE@@AEAU_DISPLAYMUX_SWITCH_CONTEXT@@IPEAD@Z; CheckFailed(long,_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE,_DISPLAYMUX_SWITCH_CONTEXT &,uint,char *)
0x1400648eb  test    al, al
0x1400648ed  jnz     short loc_14006490C
0x1400648ef  mov     byte ptr [rbx+1929h], 1
0x1400648f6  mov     r8, rdi
0x1400648f9  mov     edx, 403h
0x1400648fe  mov     ecx, 4
0x140064903  call    ?CheckForMdmFaultOrDelayInjection@@YA_NW4_D3DKMT_DISPLAYMUX_SWITCH_INJECTION_STAGE@@W4_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE@@AEAU_DISPLAYMUX_SWITCH_CONTEXT@@@Z; CheckForMdmFaultOrDelayInjection(_D3DKMT_DISPLAYMUX_SWITCH_INJECTION_STAGE,_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE,_DISPLAYMUX_SWITCH_CONTEXT &)
0x140064908  test    al, al
0x14006490a  jz      short loc_140064960
0x14006490c  lea     rcx, [rbp+280h+var_298]; this
0x140064910  call    ??1CInterfaceCallContext@@QEAA@XZ; CInterfaceCallContext::~CInterfaceCallContext(void)
0x140064915  lea     rcx, [rbp+280h+var_2B8]
0x140064919  call    _DXGKCALLONEXIT__lambda_5bf16074e78eca97c9745c10e52e39f7_______2___DXGKCALLONEXIT___DXGKCALLONEXIT
0x14006491e  lea     rcx, [rsp+380h+var_320]
0x140064923  call    _DXGKCALLONEXIT__lambda_8e64b2d4059ca463867f9c5833a46b2d_______2___DXGKCALLONEXIT___DXGKCALLONEXIT
0x140064928  lea     rcx, [rsp+380h+var_340]; this
0x14006492d  call    ?Release@AUTO_REMOVE_LOCK@@QEAAXXZ; AUTO_REMOVE_LOCK::Release(void)
0x140064932  lea     rcx, [rsp+380h+var_330]; this
0x140064937  call    ?Release@AUTO_REMOVE_LOCK@@QEAAXXZ; AUTO_REMOVE_LOCK::Release(void)
0x14006493c  cmp     [rsp+380h+var_350], r14b
0x140064941  jmp     loc_140064DAF
0x140064946  mov     r9d, 27Dh
0x14006494c  mov     r8, rdi
0x14006494f  mov     edx, 41Bh
0x140064954  mov     ecx, 0C0000001h
0x140064959  call    ?CheckFailed@@YA_NJW4_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE@@AEAU_DISPLAYMUX_SWITCH_CONTEXT@@IPEAD@Z; CheckFailed(long,_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE,_DISPLAYMUX_SWITCH_CONTEXT &,uint,char *)
0x14006495e  jmp     short loc_14006490C
0x140064960  movsd   xmm0, qword ptr [rsi+50h]
0x140064965  lea     r8, [rbp+280h+var_240]
0x140064969  mov     eax, [rsi+58h]
0x14006496c  lea     rcx, [rsp+380h+var_310]
0x140064971  mov     rdx, [rbx+0FC0h]
0x140064978  movsd   [rbp+280h+var_240], xmm0
0x14006497d  mov     [rbp+280h+var_238], eax
0x140064980  call    ?TakePowerReference@TARGET_POWER_REFERENCE@@QEAAXQEAXU_DISPLAYCONFIG_DISPLAYMUX_TARGET@@@Z; TARGET_POWER_REFERENCE::TakePowerReference(void * const,_DISPLAYCONFIG_DISPLAYMUX_TARGET)
0x140064985  mov     rax, [rsi+50h]
0x140064989  mov     rcx, rbx
0x14006498c  mov     edx, [rsi+58h]
0x14006498f  mov     r8d, [rbp+280h+var_268]
0x140064993  mov     [rsi+14h], rax
0x140064997  mov     [rsi+1Ch], edx
0x14006499a  call    DpiDxgkDdiDisplayMuxPreSwitchTo
0x14006499f  test    eax, eax
0x1400649a1  js      short loc_1400649AA
0x1400649a3  mov     dword ptr [rsi+4], 2
0x1400649aa  mov     r9d, 28Dh
0x1400649b0  mov     [rsp+380h+var_34C], eax
0x1400649b4  mov     r8, rdi
0x1400649b7  mov     edx, 403h
0x1400649bc  mov     ecx, eax
0x1400649be  call    ?CheckFailed@@YA_NJW4_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE@@AEAU_DISPLAYMUX_SWITCH_CONTEXT@@IPEAD@Z; CheckFailed(long,_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE,_DISPLAYMUX_SWITCH_CONTEXT &,uint,char *)
0x1400649c3  lea     rcx, [rbp+280h+var_298]; this
0x1400649c7  test    al, al
0x1400649c9  jz      short loc_1400649D5
0x1400649cb  call    ??1CInterfaceCallContext@@QEAA@XZ; CInterfaceCallContext::~CInterfaceCallContext(void)
0x1400649d0  jmp     loc_140064A84
0x1400649d5  mov     bl, [rbx+1928h]
0x1400649db  mov     [rsp+380h+var_344], bl
0x1400649df  call    ??1CInterfaceCallContext@@QEAA@XZ; CInterfaceCallContext::~CInterfaceCallContext(void)
0x1400649e4  test    bl, bl
0x1400649e6  jnz     loc_140064B13
0x1400649ec  mov     ebx, 417h
0x1400649f1  cmp     [rbp+280h+var_200], r14b
0x1400649f8  jz      short loc_140064A55
0x1400649fa  mov     edx, [rsi+4Ch]; unsigned int
0x1400649fd  lea     r8, [rbp+280h+var_1FF]; struct _DXGK_BRIGHTNESS_CAPS *
0x140064a04  mov     rcx, [r13+18h]; void *
0x140064a08  call    ?DpiBrightness3GetCaps@@YAJPEAXKPEAU_DXGK_BRIGHTNESS_CAPS@@@Z; DpiBrightness3GetCaps(void *,ulong,_DXGK_BRIGHTNESS_CAPS *)
0x140064a0d  mov     r9d, 2A0h
0x140064a13  mov     [rsp+380h+var_34C], eax
0x140064a17  mov     r8, rdi
0x140064a1a  lea     edx, [rbx-1]
0x140064a1d  mov     ecx, eax
0x140064a1f  call    ?CheckFailed@@YA_NJW4_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE@@AEAU_DISPLAYMUX_SWITCH_CONTEXT@@IPEAD@Z; CheckFailed(long,_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE,_DISPLAYMUX_SWITCH_CONTEXT &,uint,char *)
0x140064a24  test    al, al
0x140064a26  jnz     short loc_140064A84
0x140064a28  mov     edx, [rsi+4Ch]; unsigned int
0x140064a2b  lea     r8, [rbp+280h+var_1FB]; struct _DXGK_BRIGHTNESS_GET_NIT_RANGES_OUT *
0x140064a32  mov     rcx, [r13+18h]; void *
0x140064a36  call    ?DpiBrightness3GetNitRanges@@YAJPEAXKPEAU_DXGK_BRIGHTNESS_GET_NIT_RANGES_OUT@@@Z; DpiBrightness3GetNitRanges(void *,ulong,_DXGK_BRIGHTNESS_GET_NIT_RANGES_OUT *)
0x140064a3b  mov     r9d, 2A6h
0x140064a41  mov     [rsp+380h+var_34C], eax
0x140064a45  mov     r8, rdi
0x140064a48  mov     edx, ebx
0x140064a4a  mov     ecx, eax
0x140064a4c  call    ?CheckFailed@@YA_NJW4_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE@@AEAU_DISPLAYMUX_SWITCH_CONTEXT@@IPEAD@Z; CheckFailed(long,_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE,_DISPLAYMUX_SWITCH_CONTEXT &,uint,char *)
0x140064a51  test    al, al
0x140064a53  jnz     short loc_140064A84
0x140064a55  mov     edx, [rsi+4Ch]
0x140064a58  lea     r8, [rsp+380h+var_348]
0x140064a5d  mov     rcx, [r13+18h]
0x140064a61  call    DpiGetIntegratedEdidSizeForDisplayMuxTarget
0x140064a66  mov     r9d, 2AEh
0x140064a6c  mov     [rsp+380h+var_34C], eax
0x140064a70  mov     r8, rdi
0x140064a73  mov     edx, ebx
0x140064a75  mov     ecx, eax
0x140064a77  call    ?CheckFailed@@YA_NJW4_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE@@AEAU_DISPLAYMUX_SWITCH_CONTEXT@@IPEAD@Z; CheckFailed(long,_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE,_DISPLAYMUX_SWITCH_CONTEXT &,uint,char *)
0x140064a7c  test    al, al
0x140064a7e  jz      loc_140064B0B
0x140064a84  lea     rcx, [rbp+280h+var_2B8]
0x140064a88  call    _DXGKCALLONEXIT__lambda_5bf16074e78eca97c9745c10e52e39f7_______2___DXGKCALLONEXIT___DXGKCALLONEXIT
0x140064a8d  xor     esi, esi
0x140064a8f  cmp     [rbp+280h+var_2F0], sil
0x140064a93  jz      short loc_140064AE3
0x140064a95  cmp     cs:bTracingEnabled, sil
0x140064a9c  mov     rbx, qword ptr [rbp+280h+var_300]
0x140064aa0  mov     edi, [rsp+380h+var_304]
0x140064aa4  jz      short loc_140064AC6
0x140064aa6  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 2
0x140064aad  jz      short loc_140064AC6
0x140064aaf  mov     dword ptr [rsp+380h+var_358], esi
0x140064ab3  lea     rdx, Dxgk_ReportPowerComponentState
0x140064aba  mov     r9, rbx
0x140064abd  mov     dword ptr [rsp+380h+Timeout], edi
0x140064ac1  call    McTemplateK0pqq_EtwWriteTransfer
0x140064ac6  mov     rcx, [rbx+0D20h]
0x140064acd  test    rcx, rcx
0x140064ad0  jz      short loc_140064AE3
0x140064ad2  xor     r8d, r8d
0x140064ad5  mov     edx, edi
0x140064ad7  call    cs:__imp_PoFxIdleComponent
0x140064ade  nop     dword ptr [rax+rax+00h]
0x140064ae3  lea     rcx, [rsp+380h+var_320]
0x140064ae8  call    _DXGKCALLONEXIT__lambda_8e64b2d4059ca463867f9c5833a46b2d_______2___DXGKCALLONEXIT___DXGKCALLONEXIT
0x140064aed  lea     rcx, [rsp+380h+var_340]; this
0x140064af2  call    ?Release@AUTO_REMOVE_LOCK@@QEAAXXZ; AUTO_REMOVE_LOCK::Release(void)
0x140064af7  lea     rcx, [rsp+380h+var_330]; this
0x140064afc  call    ?Release@AUTO_REMOVE_LOCK@@QEAAXXZ; AUTO_REMOVE_LOCK::Release(void)
0x140064b01  cmp     [rsp+380h+var_350], sil
0x140064b06  jmp     loc_140064DAF
0x140064b0b  movzx   eax, word ptr [rsp+380h+var_348]
0x140064b10  mov     [rbp+280h+var_248], eax
0x140064b13  mov     rdx, r13
0x140064b16  lea     rcx, [rbp+280h+var_298]
0x140064b1a  call    ??0CInterfaceCallContext@@QEAA@PEAU_FDO_CONTEXT@@W4LocksToAcquire@@@Z; CInterfaceCallContext::CInterfaceCallContext(_FDO_CONTEXT *,LocksToAcquire)
0x140064b1f  mov     ecx, [rbp+280h+var_278]
0x140064b22  mov     r9d, 2B8h
0x140064b28  mov     r8, rdi
0x140064b2b  mov     edx, 405h
0x140064b30  call    ?CheckFailed@@YA_NJW4_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE@@AEAU_DISPLAYMUX_SWITCH_CONTEXT@@IPEAD@Z; CheckFailed(long,_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE,_DISPLAYMUX_SWITCH_CONTEXT &,uint,char *)
0x140064b35  xor     r13d, r13d
0x140064b38  test    al, al
0x140064b3a  jz      short loc_140064B65
0x140064b3c  lea     rcx, [rbp+280h+var_298]; this
0x140064b40  call    ??1CInterfaceCallContext@@QEAA@XZ; CInterfaceCallContext::~CInterfaceCallContext(void)
0x140064b45  lea     rcx, [rbp+280h+var_2B8]
0x140064b49  call    _DXGKCALLONEXIT__lambda_5bf16074e78eca97c9745c10e52e39f7_______2___DXGKCALLONEXIT___DXGKCALLONEXIT
0x140064b4e  cmp     [rbp+280h+var_2F0], r13b
0x140064b52  jz      loc_140064D8C
0x140064b58  mov     edi, [rsp+380h+var_304]
0x140064b5c  mov     rbx, qword ptr [rbp+280h+var_300]
0x140064b60  jmp     loc_140064D45
  ... truncated ...
```
