# DISPLAY_MUX_SWITCH_OPERATION::PerformSwitch(_D3DKMT_DISPLAYMUX_SWITCH_STATUS *,int *)

- ea: `0x140064250`
- end: `0x1400652d2`
- name: `?PerformSwitch@DISPLAY_MUX_SWITCH_OPERATION@@QEAAXPEAU_D3DKMT_DISPLAYMUX_SWITCH_STATUS@@PEAH@Z`
- size: `4226`
- prototype: `void __fastcall(DISPLAY_MUX_SWITCH_OPERATION *__hidden this, struct _D3DKMT_DISPLAYMUX_SWITCH_STATUS *, int *)`
- caller_count: `1`
- callee_count: `39`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140064134`

## callees

- `0x140009030`
- `0x14000d7d0`
- `0x14001becc`
- `0x14002f58c`
- `0x1400404fc`
- `0x1400406ec`
- `0x140047d20`
- `0x1400571d0`
- `0x140064250`
- `0x140066d54`
- `0x140080614`
- `0x140080a8c`
- `0x140080c88`
- `0x140085150`
- `0x140085188`
- `0x1400851f4`
- `0x14008523c`
- `0x1400858e0`
- `0x140086b5c`
- `0x140087a50`
- `0x140087bd4`
- `0x140088264`
- `0x1400882b4`
- `0x140088368`
- `0x140088ad8`
- `0x140088c94`
- `0x14008c408`
- `0x14008c468`
- `0x14008ca2c`
- `0x14008cb6c`
- `0x14008cc04`
- `0x14008ccac`
- `0x14008cdd8`
- `0x1400a0100`
- `0x1400a0540`
- `0x1401bd32c`
- `0x1402b3e60`
- `0x1402b3f50`
- `0x1402b9d94`

## import_xrefs

- `ntoskrnl!PoFxIdleComponent` at `0x1400646b7`
- `ntoskrnl!PoFxIdleComponent` at `0x14006490c`
- `ntoskrnl!PoFxIdleComponent` at `0x140064960`
- `ntoskrnl!PoFxIdleComponent` at `0x140064a5a`
- `ntoskrnl!PoFxIdleComponent` at `0x140064aae`
- `ntoskrnl!PoFxIdleComponent` at `0x140064c84`
- `ntoskrnl!PoFxIdleComponent` at `0x1400646b7`
- `ntoskrnl!PoFxIdleComponent` at `0x14006490c`
- `ntoskrnl!PoFxIdleComponent` at `0x140064960`
- `ntoskrnl!PoFxIdleComponent` at `0x140064a5a`
- `ntoskrnl!PoFxIdleComponent` at `0x140064aae`
- `ntoskrnl!PoFxIdleComponent` at `0x140064c84`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400643ee`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400643ee`
- `ntoskrnl!KeReleaseMutex` at `0x14006442b`
- `ntoskrnl!KeReleaseMutex` at `0x14006442b`
- `watchdog!WdLogSingleEntry2` at `0x140064ead`
- `watchdog!WdLogSingleEntry2` at `0x1400650e1`
- `watchdog!WdLogSingleEntry2` at `0x140065155`
- `watchdog!WdLogSingleEntry2` at `0x1400651d2`
- `watchdog!WdLogSingleEntry2` at `0x140064ead`
- `watchdog!WdLogSingleEntry2` at `0x1400650e1`
- `watchdog!WdLogSingleEntry2` at `0x140065155`
- `watchdog!WdLogSingleEntry2` at `0x1400651d2`
- `watchdog!WdLogSingleEntry0` at `0x140065237`
- `watchdog!WdLogSingleEntry0` at `0x140065237`
- `watchdog!WdLogSingleEntry5` at `0x140064d73`
- `watchdog!WdLogSingleEntry5` at `0x140064de3`
- `watchdog!WdLogSingleEntry5` at `0x140064e18`
- `watchdog!WdLogSingleEntry5` at `0x140064e90`
- `watchdog!WdLogSingleEntry5` at `0x1400650c4`
- `watchdog!WdLogSingleEntry5` at `0x140065138`
- `watchdog!WdLogSingleEntry5` at `0x1400651b5`
- `watchdog!WdLogSingleEntry5` at `0x14006521a`
- `watchdog!WdLogSingleEntry5` at `0x140064d73`
- `watchdog!WdLogSingleEntry5` at `0x140064de3`
- `watchdog!WdLogSingleEntry5` at `0x140064e18`
- `watchdog!WdLogSingleEntry5` at `0x140064e90`
- `watchdog!WdLogSingleEntry5` at `0x1400650c4`
- `watchdog!WdLogSingleEntry5` at `0x140065138`
- `watchdog!WdLogSingleEntry5` at `0x1400651b5`
- `watchdog!WdLogSingleEntry5` at `0x14006521a`
- `watchdog!WdLogSingleEntry1` at `0x140064d90`
- `watchdog!WdLogSingleEntry1` at `0x140064e38`
- `watchdog!WdLogSingleEntry1` at `0x140064d90`
- `watchdog!WdLogSingleEntry1` at `0x140064e38`

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
  __int64 v66; // rdx
  char v67[4]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int AdapterAndAcquire; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int8 v69[2]; // [rsp+38h] [rbp-C8h] BYREF
  char v70; // [rsp+3Ch] [rbp-C4h]
  __int64 v71; // [rsp+40h] [rbp-C0h] BYREF
  char v72; // [rsp+48h] [rbp-B8h]
  struct _KMUTANT *v73; // [rsp+50h] [rbp-B0h] BYREF
  char v74; // [rsp+58h] [rbp-A8h]
  DISPLAY_MUX_SWITCH_OPERATION *v75; // [rsp+60h] [rbp-A0h] BYREF
  char v76; // [rsp+68h] [rbp-98h]
  __int64 v77; // [rsp+70h] [rbp-90h] BYREF
  int v78; // [rsp+78h] [rbp-88h]
  int v79; // [rsp+7Ch] [rbp-84h]
  __int128 v80; // [rsp+80h] [rbp-80h]
  char v81; // [rsp+90h] [rbp-70h]
  unsigned int v82; // [rsp+98h] [rbp-68h] BYREF
  __int64 v83; // [rsp+A0h] [rbp-60h] BYREF
  int v84; // [rsp+A8h] [rbp-58h]
  int v85; // [rsp+ACh] [rbp-54h]
  __int128 v86; // [rsp+B0h] [rbp-50h]
  char v87; // [rsp+C0h] [rbp-40h]
  _QWORD v88[3]; // [rsp+C8h] [rbp-38h] BYREF
  char v89; // [rsp+E0h] [rbp-20h]
  struct _DEVICE_OBJECT *v90; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v91; // [rsp+F0h] [rbp-10h]
  unsigned int v92; // [rsp+108h] [rbp+8h]
  unsigned int v93; // [rsp+118h] [rbp+18h]
  DISPLAY_MUX_SWITCH_OPERATION *v94; // [rsp+120h] [rbp+20h] BYREF
  struct _DEVICE_OBJECT **v95; // [rsp+128h] [rbp+28h]
  char v96; // [rsp+130h] [rbp+30h]
  int v97; // [rsp+138h] [rbp+38h]
  void *v98; // [rsp+140h] [rbp+40h] BYREF
  int v99; // [rsp+148h] [rbp+48h]
  __int64 v100; // [rsp+150h] [rbp+50h] BYREF
  _OWORD *v101; // [rsp+158h] [rbp+58h]
  int *v102; // [rsp+160h] [rbp+60h]
  _OWORD v103[15]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v104[224]; // [rsp+260h] [rbp+160h] BYREF
  struct _D3DKMT_DISPLAYMUX_SWITCH_STATUS *v105; // [rsp+398h] [rbp+298h] BYREF

  v105 = a2;
  v102 = a3;
  AdapterAndAcquire = 0;
  v100 = 0;
  v82 = 0;
  v4 = 0;
  v103[0] = 0;
  MINIPORT_LIST_AUTO_LOCK::MINIPORT_LIST_AUTO_LOCK((MINIPORT_LIST_AUTO_LOCK *)v67, (bool)a2);
  v5 = byte_14015F4F1;
  v6 = (struct _LUID *)((char *)this + 68);
  v73 = 0;
  v74 = 0;
  AdapterAndAcquire = AUTO_REMOVE_LOCK::FindAdapterAndAcquire(
                        (AUTO_REMOVE_LOCK *)&v73,
                        (struct _LUID *)((char *)this + 68));
  if ( (unsigned __int8)CheckFailed(AdapterAndAcquire, 1044, (char *)this + 92, 542) )
    goto LABEL_2;
  v71 = 0;
  v72 = 0;
  AdapterAndAcquire = AUTO_REMOVE_LOCK::FindAdapterAndAcquire((AUTO_REMOVE_LOCK *)&v71, (struct _LUID *)this + 10);
  if ( (unsigned __int8)CheckFailed(AdapterAndAcquire, 1045, (char *)this + 92, 550) )
  {
    AUTO_REMOVE_LOCK::Release((AUTO_REMOVE_LOCK *)&v71);
LABEL_2:
    AUTO_REMOVE_LOCK::Release((AUTO_REMOVE_LOCK *)&v73);
    v7 = v67[0] == 0;
    goto LABEL_62;
  }
  v75 = this;
  v83 = 0;
  v85 = -1;
  v79 = -1;
  v76 = 1;
  v84 = 0;
  v86 = 0;
  v87 = 0;
  v77 = 0;
  v78 = 0;
  v80 = 0;
  v81 = 0;
  DISPLAY_MUX_MGR::SetDisableProcessingDisplayBatchesStatus(qword_14015F448, 1);
  v88[1] = this;
  v88[0] = &AdapterAndAcquire;
  v89 = 1;
  v88[2] = &v105;
  v97 = 0;
  *(_WORD *)v69 = 0;
  memset((char *)&v103[1] + 8, 0, 0xD1u);
  v8 = v73;
  v9 = v73 + 81;
  KeWaitForSingleObject(&v73[81], Executive, 0, 0, 0);
  v7 = *(_WORD *)(&v8[85].ApcDisable + 1) == 3;
  v93 = *(_DWORD *)&v8[80].Abandoned;
  v10 = BYTE8(v103[1]);
  if ( v7 )
    v10 = 1;
  BYTE8(v103[1]) = v10;
  KeReleaseMutex(v9, 0);
  CInterfaceCallContext::CInterfaceCallContext(&v90, v71);
  if ( (unsigned __int8)CheckFailed(v92, 1028, (char *)this + 92, 614) )
    goto LABEL_14;
  v11 = v91;
  if ( !*(_BYTE *)(v91 + 6441) )
  {
    memset(v104, 0, 0xD1u);
    if ( !DISPLAY_MUX_MGR::GetInternalPanelInfo(
            qword_14015F448,
            (struct _DXGK_DISPLAYMUX_SET_INTERNAL_PANEL_INFO *)v104) )
    {
      CheckFailed(3221225473LL, 1051, (char *)this + 92, 637);
      goto LABEL_14;
    }
    AdapterAndAcquire = DpiDxgkDdiDisplayMuxSetInternalPanelInfo(v11, *((unsigned int *)this + 22), v104);
    if ( (unsigned __int8)CheckFailed(v92, 1049, (char *)this + 92, 628) )
    {
LABEL_14:
      CInterfaceCallContext::~CInterfaceCallContext((CInterfaceCallContext *)&v90);
      DXGKCALLONEXIT__lambda_5bf16074e78eca97c9745c10e52e39f7____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(v88);
      DXGKCALLONEXIT__lambda_8e64b2d4059ca463867f9c5833a46b2d____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(&v75);
      AUTO_REMOVE_LOCK::Release((AUTO_REMOVE_LOCK *)&v71);
      AUTO_REMOVE_LOCK::Release((AUTO_REMOVE_LOCK *)&v73);
      v7 = v67[0] == 0;
      goto LABEL_62;
    }
    *(_BYTE *)(v11 + 6441) = 1;
  }
  if ( (unsigned __int8)CheckForMdmFaultOrDelayInjection(4, 1027, (char *)this + 92) )
    goto LABEL_14;
  v12 = *((_DWORD *)this + 22);
  v13 = *(_QWORD *)(v11 + 4032);
  v98 = (void *)*((_QWORD *)this + 10);
  v99 = v12;
  TARGET_POWER_REFERENCE::TakePowerReference(&v77, v13, &v98);
  v14 = *((unsigned int *)this + 22);
  v15 = v93;
  *(_QWORD *)((char *)this + 20) = *((_QWORD *)this + 10);
  *((_DWORD *)this + 7) = v14;
  v16 = DpiDxgkDdiDisplayMuxPreSwitchTo(v11, v14, v15);
  if ( v16 >= 0 )
    *((_DWORD *)this + 1) = 2;
  AdapterAndAcquire = v16;
  if ( (unsigned __int8)CheckFailed((unsigned int)v16, 1027, (char *)this + 92, 653) )
  {
    CInterfaceCallContext::~CInterfaceCallContext((CInterfaceCallContext *)&v90);
    goto LABEL_25;
  }
  v17 = *(_BYTE *)(v11 + 6440);
  v70 = v17;
  CInterfaceCallContext::~CInterfaceCallContext((CInterfaceCallContext *)&v90);
  if ( !v17 )
  {
    if ( BYTE8(v103[1])
      && ((AdapterAndAcquire = DpiBrightness3GetCaps(
                                 v8->MutantListEntry.Flink,
                                 *((_DWORD *)this + 19),
                                 (struct _DXGK_BRIGHTNESS_CAPS *)((char *)&v103[1] + 9)),
           (unsigned __int8)CheckFailed(AdapterAndAcquire, 1046, (char *)this + 92, 672))
       || (AdapterAndAcquire = DpiBrightness3GetNitRanges(
                                 v8->MutantListEntry.Flink,
                                 *((_DWORD *)this + 19),
                                 (struct _DXGK_BRIGHTNESS_GET_NIT_RANGES_OUT *)((char *)&v103[1] + 13)),
           (unsigned __int8)CheckFailed(AdapterAndAcquire, 1047, (char *)this + 92, 678)))
      || (AdapterAndAcquire = DpiGetIntegratedEdidSizeForDisplayMuxTarget(
                                v8->MutantListEntry.Flink,
                                *((unsigned int *)this + 19),
                                v69),
          (unsigned __int8)CheckFailed(AdapterAndAcquire, 1047, (char *)this + 92, 686)) )
    {
LABEL_25:
      DXGKCALLONEXIT__lambda_5bf16074e78eca97c9745c10e52e39f7____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(v88);
      if ( v81 )
      {
        v20 = v80;
        v21 = v79;
        if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
          McTemplateK0pqq_EtwWriteTransfer(v18, (unsigned int)Dxgk_ReportPowerComponentState, v19, v80, v79, 0);
        v22 = *(_QWORD *)(v20 + 3344);
        if ( v22 )
          PoFxIdleComponent(v22, v21, 0);
      }
      goto LABEL_61;
    }
    v97 = *(unsigned __int16 *)v69;
  }
  CInterfaceCallContext::CInterfaceCallContext(&v90, v8);
  if ( (unsigned __int8)CheckFailed(v92, 1029, (char *)this + 92, 696) )
    goto LABEL_34;
  v27 = v91;
  v28 = *((_DWORD *)this + 19);
  v69[0] = 0;
  AdapterAndAcquire = MonitorIsMonitorConnected(*(void **)(v91 + 4032), v28, 1u, v69);
  if ( (unsigned __int8)CheckFailed(AdapterAndAcquire, 1025, (char *)this + 92, 704) )
    goto LABEL_34;
  v29 = (char *)this + 92;
  if ( !v69[0] )
  {
    CheckFailed(3221226021LL, 1026, v29, 710);
LABEL_34:
    CInterfaceCallContext::~CInterfaceCallContext((CInterfaceCallContext *)&v90);
    DXGKCALLONEXIT__lambda_5bf16074e78eca97c9745c10e52e39f7____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(v88);
    if ( !v81 )
    {
LABEL_61:
      DXGKCALLONEXIT__lambda_8e64b2d4059ca463867f9c5833a46b2d____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(&v75);
      AUTO_REMOVE_LOCK::Release((AUTO_REMOVE_LOCK *)&v71);
      AUTO_REMOVE_LOCK::Release((AUTO_REMOVE_LOCK *)&v73);
      v7 = v67[0] == 0;
LABEL_62:
      if ( !v7 )
        ReleaseMiniportListMutex();
      return;
    }
    v25 = v79;
    v26 = v80;
LABEL_56:
    if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
      McTemplateK0pqq_EtwWriteTransfer(v23, (unsigned int)Dxgk_ReportPowerComponentState, v24, v26, v25, 0);
    v37 = *(_QWORD *)(v26 + 3344);
    if ( v37 )
      PoFxIdleComponent(v37, v25, 0);
    goto LABEL_61;
  }
  if ( (unsigned __int8)CheckForMdmFaultOrDelayInjection(5, 1030, v29) )
    goto LABEL_34;
  v30 = *((_DWORD *)this + 19);
  v31 = *(_QWORD *)(v27 + 4032);
  v98 = *(void **)((char *)this + 68);
  v99 = v30;
  TARGET_POWER_REFERENCE::TakePowerReference(&v83, v31, &v98);
  AdapterAndAcquire = DISPLAY_MUX_MGR::SetDisableQueryConnectionDdiStatus(qword_14015F448, *v6, 1);
  if ( (unsigned __int8)CheckFailed(AdapterAndAcquire, 1030, (char *)this + 92, 727) )
  {
LABEL_48:
    CInterfaceCallContext::~CInterfaceCallContext((CInterfaceCallContext *)&v90);
    DXGKCALLONEXIT__lambda_5bf16074e78eca97c9745c10e52e39f7____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(v88);
    if ( v81 )
    {
      v35 = v79;
      v36 = v80;
      if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
        McTemplateK0pqq_EtwWriteTransfer(v23, (unsigned int)Dxgk_ReportPowerComponentState, v24, v80, v79, 0);
      v23 = *(_QWORD *)(v36 + 3344);
      if ( v23 )
        PoFxIdleComponent(v23, v35, 0);
    }
    if ( !v87 )
      goto LABEL_61;
    v25 = v85;
    v26 = v86;
    goto LABEL_56;
  }
  v94 = this;
  LOBYTE(v95) = 1;
  if ( (unsigned __int8)CheckForMdmFaultOrDelayInjection(6, 1031, (char *)this + 92) )
    goto LABEL_47;
  v32 = *((unsigned int *)this + 19);
  *((_QWORD *)this + 1) = *(_QWORD *)((char *)this + 68);
  *((_DWORD *)this + 4) = v32;
  v33 = DpiDxgkDdiDisplayMuxPreSwitchAway(v27, v32, &v82);
  if ( v33 >= 0 )
    *(_DWORD *)this = 2;
  AdapterAndAcquire = v33;
  if ( (unsigned __int8)CheckFailed((unsigned int)v33, 1031, (char *)this + 92, 744) )
  {
LABEL_47:
    DXGKCALLONEXIT__lambda_b3b73720c9a5b94f1e3275d94b86d9de____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(&v94);
    goto LABEL_48;
  }
  DISPLAY_MUX_MGR::SetAdapterAllowedToReportDisplayMuxHpd(
    qword_14015F448,
    (DISPLAY_MUX_SWITCH_OPERATION *)((char *)this + 68));
  v34 = (char *)this + 92;
  if ( v82 > 0x100000 )
  {
    CheckFailed(3221225990LL, 1032, v34, 755);
    goto LABEL_47;
  }
  if ( (unsigned __int8)CheckForMdmFaultOrDelayInjection(7, 1034, v34) )
    goto LABEL_47;
  if ( v82 )
  {
    v100 = operator new[](v82, 1265072196, 256);
    v4 = (void *)v100;
    if ( !v100 )
    {
      CheckFailed(3221225495LL, 1033, (char *)this + 92, 772);
LABEL_68:
      DXGKCALLONEXIT__lambda_b3b73720c9a5b94f1e3275d94b86d9de____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(&v94);
      CInterfaceCallContext::~CInterfaceCallContext((CInterfaceCallContext *)&v90);
      DXGKCALLONEXIT__lambda_5bf16074e78eca97c9745c10e52e39f7____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(v88);
      if ( v81 )
      {
        v40 = v80;
        v41 = v79;
        if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
          McTemplateK0pqq_EtwWriteTransfer(v38, (unsigned int)Dxgk_ReportPowerComponentState, v39, v80, v79, 0);
        v38 = *(_QWORD *)(v40 + 3344);
        if ( v38 )
          PoFxIdleComponent(v38, v41, 0);
      }
      if ( v87 )
      {
        v42 = v86;
        v43 = v85;
        if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
          McTemplateK0pqq_EtwWriteTransfer(v38, (unsigned int)Dxgk_ReportPowerComponentState, v39, v86, v85, 0);
        v44 = *(_QWORD *)(v42 + 3344);
        if ( v44 )
          PoFxIdleComponent(v44, v43, 0);
      }
      DXGKCALLONEXIT__lambda_8e64b2d4059ca463867f9c5833a46b2d____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(&v75);
      AUTO_REMOVE_LOCK::Release((AUTO_REMOVE_LOCK *)&v71);
      AUTO_REMOVE_LOCK::Release((AUTO_REMOVE_LOCK *)&v73);
      if ( v67[0] )
        ReleaseMiniportListMutex();
      if ( v4 )
        DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v4);
      return;
    }
    AdapterAndAcquire = DpiDxgkDdiDisplayMuxPreSwitchAwayGetPrivateData(
                          v27,
                          *((_DWORD *)this + 19),
                          v82,
                          v100,
                          (__int64)v103);
    if ( (unsigned __int8)CheckFailed(AdapterAndAcquire, 1034, (char *)this + 92, 782) )
      goto LABEL_68;
    v98 = v4;
    v101 = v103;
  }
  else
  {
    v101 = 0;
    v98 = 0;
  }
  if ( (unsigned __int8)CheckForMdmFaultOrDelayInjection(8, 1035, (char *)this + 92) )
    goto LABEL_68;
  AdapterAndAcquire = DISPLAY_MUX_MGR::SwitchMux(
                        qword_14015F448,
                        *(struct _LUID *)((char *)this + 80),
                        *((_DWORD *)this + 22));
  if ( (unsigned __int8)CheckFailed(AdapterAndAcquire, 1035, (char *)this + 92, 798) )
    goto LABEL_68;
  if ( !*(_BYTE *)(v27 + 2716) )
    qword_14015F128 = *(_QWORD *)(v71 + 24);
  if ( (unsigned __int8)CheckForMdmFaultOrDelayInjection(9, 1037, (char *)this + 92) )
    goto LABEL_68;
  AdapterAndAcquire = DISPLAY_MUX_MGR::SetDisableQueryConnectionDdiStatus(qword_14015F448, *v6, 0);
  if ( (unsigned __int8)CheckFailed(AdapterAndAcquire, 1037, (char *)this + 92, 817) )
    goto LABEL_68;
  DXGKCALLONEXIT__lambda_b3b73720c9a5b94f1e3275d94b86d9de____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(&v94);
  if ( (unsigned __int8)CheckForMdmFaultOrDelayInjection(10, 1038, (char *)this + 92) )
  {
    CInterfaceCallContext::~CInterfaceCallContext((CInterfaceCallContext *)&v90);
    DXGKCALLONEXIT__lambda_5bf16074e78eca97c9745c10e52e39f7____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(v88);
    if ( v81 )
    {
      v47 = v79;
      v48 = v80;
      if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
        McTemplateK0pqq_EtwWriteTransfer(v45, (unsigned int)Dxgk_ReportPowerComponentState, v46, v80, v79, 0);
      v49 = *(_QWORD *)(v48 + 3344);
      if ( v49 )
        PoFxIdleComponent(v49, v47, 0);
    }
  }
  else
  {
    AdapterAndAcquire = QueryConnectionChanges(
                          v90,
                          *(struct _LUID *)((char *)this + 68),
                          (struct _GUID *)((char *)this + 92),
                          (struct _GUID *)((char *)this + 108));
    DISPLAY_MUX_MGR::SetAdapterAllowedToReportDisplayMuxHpd(qword_14015F448, 0);
    if ( !(unsigned __int8)CheckFailed(AdapterAndAcquire, 1038, (char *)this + 92, 832) )
    {
      v51 = *((unsigned int *)qword_14015F448 + 32);
      v52 = *((unsigned int *)qword_14015F448 + 29);
      v53 = *((unsigned int *)qword_14015F448 + 31);
      v54 = *((unsigned int *)qword_14015F448 + 33);
      v93 = *((_DWORD *)qword_14015F448 + 30);
      if ( (_DWORD)v51 )
      {
        v5 |= (unsigned __int8)((__int64 (*)(void))DpiAcpiIsLidOpen)() == 0;
        if ( v5 )
        {
          WdLogSingleEntry1(2);
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
          WdLogSingleEntry1(2);
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
        || *((_DWORD *)this + 18) != v93
        || *((_DWORD *)this + 19) != (_DWORD)v53 )
      {
        v5 |= (unsigned __int8)((__int64 (*)(void))DpiAcpiIsLidOpen)() == 0;
        if ( v5 )
        {
          WdLogSingleEntry2(2, v52);
          WdLogGlobalForLineNumber = 910;
        }
        else
        {
          WdLogSingleEntry5(0, 484, 52, 4, v52, v53);
          WdLogGlobalForLineNumber = 904;
        }
      }
      CInterfaceCallContext::~CInterfaceCallContext((CInterfaceCallContext *)&v90);
      CInterfaceCallContext::CInterfaceCallContext(&v90, v71);
      if ( !(unsigned __int8)CheckFailed(v92, 1039, (char *)this + 92, 919)
        && !(unsigned __int8)CheckForMdmFaultOrDelayInjection(11, 1040, (char *)this + 92) )
      {
        if ( v70
          || (AdapterAndAcquire = DpiSetIntegratedEdidSizeForDisplayMuxTarget(
                                    v90,
                                    *((unsigned int *)this + 22),
                                    (unsigned __int16)v97),
              !(unsigned __int8)CheckFailed(v92, 1050, (char *)this + 92, 934)) )
        {
          if ( !(unsigned __int8)CheckForMdmFaultOrDelayInjection(12, 1041, (char *)this + 92) )
          {
            v55 = (__int64)v101;
            v56 = *((_DWORD *)this + 22);
            v57 = (int)v98;
            v58 = v82;
            v59 = v91;
            *((_BYTE *)this + 32) = 1;
            AdapterAndAcquire = DpiDxgkDdiDisplayMuxPostSwitchToPhase1(v59, v56, v58, v57, v55);
            if ( !(unsigned __int8)CheckFailed(AdapterAndAcquire, 1041, (char *)this + 92, 952) )
            {
              v95 = &v90;
              v94 = this;
              v96 = 1;
              AdapterAndAcquire = DpiQueryIntegratedDescriptorWrapper(v90);
              if ( (unsigned __int8)CheckFailed(AdapterAndAcquire, 1040, (char *)this + 92, 978)
                || (unsigned __int8)CheckForMdmFaultOrDelayInjection(13, 1042, (char *)this + 92) )
              {
                DXGKCALLONEXIT__lambda_81c4496798e6cbc83c2bde0911ff3b32____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(&v94);
              }
              else
              {
                DXGKCALLONEXIT__lambda_81c4496798e6cbc83c2bde0911ff3b32____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(&v94);
                DISPLAY_MUX_MGR::SetAdapterAllowedToReportDisplayMuxHpd(
                  qword_14015F448,
                  (DISPLAY_MUX_SWITCH_OPERATION *)((char *)this + 80));
                AdapterAndAcquire = QueryConnectionChanges(
                                      v90,
                                      *(struct _LUID *)((char *)this + 80),
                                      (struct _GUID *)((char *)this + 92),
                                      (struct _GUID *)((char *)this + 108));
                DISPLAY_MUX_MGR::SetAdapterAllowedToReportDisplayMuxHpd(qword_14015F448, 0);
                if ( !(unsigned __int8)CheckFailed(AdapterAndAcquire, 1042, (char *)this + 92, 995) )
                {
                  v60 = qword_14015F448;
                  v61 = *((unsigned int *)qword_14015F448 + 32);
                  v62 = *((unsigned int *)qword_14015F448 + 33);
                  if ( *((_DWORD *)this + 20) != *((_DWORD *)qword_14015F448 + 29)
                    || *((_DWORD *)this + 21) != *((_DWORD *)qword_14015F448 + 30)
                    || *((_DWORD *)this + 22) != *((_DWORD *)qword_14015F448 + 31) )
                  {
                    v63 = ((__int64 (*)(void))DpiAcpiIsLidOpen)();
                    v64 = *((unsigned int *)this + 20);
                    v5 |= v63 == 0;
                    if ( v5 )
                    {
                      WdLogSingleEntry2(2, v64);
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
                        WdLogSingleEntry2(2, v65);
                        WdLogGlobalForLineNumber = 1048;
                      }
                      else
                      {
                        WdLogSingleEntry5(0, 484, 52, 5, v51, v65);
                        WdLogGlobalForLineNumber = 1042;
                      }
                    }
                    *v102 = 1;
                  }
                  else if ( (_DWORD)v61 == (_DWORD)v51 )
                  {
                    if ( (_DWORD)v62 != (_DWORD)v54 + 1 )
                    {
                      if ( (unsigned __int8)v5 | ((unsigned __int8)DpiAcpiIsLidOpen(v60, v62, v54) == 0) )
                      {
                        WdLogSingleEntry2(2, v66);
                        WdLogGlobalForLineNumber = 1075;
                      }
                      else
                      {
                        WdLogSingleEntry5(0, 484, 52, 6, v54, v66);
                        WdLogGlobalForLineNumber = 1069;
                      }
                    }
                    *v102 = 0;
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
      CInterfaceCallContext::~CInterfaceCallContext((CInterfaceCallContext *)&v90);
      DXGKCALLONEXIT__lambda_5bf16074e78eca97c9745c10e52e39f7____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(v88);
      TARGET_POWER_REFERENCE::ReleaseReference((TARGET_POWER_REFERENCE *)&v77);
      TARGET_POWER_REFERENCE::ReleaseReference((TARGET_POWER_REFERENCE *)&v83);
      DXGKCALLONEXIT__lambda_8e64b2d4059ca463867f9c5833a46b2d____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(&v75);
      AUTO_REMOVE_LOCK::Release((AUTO_REMOVE_LOCK *)&v71);
      AUTO_REMOVE_LOCK::Release((AUTO_REMOVE_LOCK *)&v73);
      v50 = v67[0] == 0;
      goto LABEL_151;
    }
    CInterfaceCallContext::~CInterfaceCallContext((CInterfaceCallContext *)&v90);
    DXGKCALLONEXIT__lambda_5bf16074e78eca97c9745c10e52e39f7____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(v88);
    TARGET_POWER_REFERENCE::ReleaseReference((TARGET_POWER_REFERENCE *)&v77);
  }
  TARGET_POWER_REFERENCE::ReleaseReference((TARGET_POWER_REFERENCE *)&v83);
  DXGKCALLONEXIT__lambda_8e64b2d4059ca463867f9c5833a46b2d____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(&v75);
  AUTO_REMOVE_LOCK::Release((AUTO_REMOVE_LOCK *)&v71);
  AUTO_REMOVE_LOCK::Release((AUTO_REMOVE_LOCK *)&v73);
  v50 = v67[0] == 0;
LABEL_151:
  if ( !v50 )
    ReleaseMiniportListMutex();
  wistd::unique_ptr<_KEY_VALUE_PARTIAL_INFORMATION,DxgMonitor::byte_array_deleter<_KEY_VALUE_PARTIAL_INFORMATION>>::reset(
    &v100,
    0);
}

```

## disassembly

```asm
0x140064250  mov     [rsp-8+arg_18], rbx
0x140064255  mov     [rsp-8+arg_8], rdx
0x14006425a  push    rbp
0x14006425b  push    rsi
0x14006425c  push    rdi
0x14006425d  push    r12
0x14006425f  push    r13
0x140064261  push    r14
0x140064263  push    r15
0x140064265  lea     rbp, [rsp-250h]
0x14006426d  sub     rsp, 350h
0x140064274  mov     rax, cs:__security_cookie
0x14006427b  xor     rax, rsp
0x14006427e  mov     [rbp+280h+var_40], rax
0x140064285  xor     ebx, ebx
0x140064287  mov     [rbp+280h+var_220], r8
0x14006428b  mov     rsi, rcx
0x14006428e  mov     [rsp+380h+var_34C], ebx
0x140064292  xorps   xmm0, xmm0
0x140064295  mov     [rbp+280h+var_230], rbx
0x140064299  lea     rcx, [rsp+380h+var_350]; this
0x14006429e  mov     [rbp+280h+var_2E8], ebx
0x1400642a1  mov     r14d, ebx
0x1400642a4  movups  [rbp+280h+var_218], xmm0
0x1400642a8  call    ??0MINIPORT_LIST_AUTO_LOCK@@QEAA@_N@Z; MINIPORT_LIST_AUTO_LOCK::MINIPORT_LIST_AUTO_LOCK(bool)
0x1400642ad  mov     r15b, cs:byte_14015F4F1
0x1400642b4  lea     r12, [rsi+44h]
0x1400642b8  mov     rdx, r12; struct _LUID *
0x1400642bb  mov     [rsp+380h+var_330], rbx
0x1400642c0  lea     rcx, [rsp+380h+var_330]; this
0x1400642c5  mov     [rsp+380h+var_328], bl
0x1400642c9  call    ?FindAdapterAndAcquire@AUTO_REMOVE_LOCK@@QEAAJPEAU_LUID@@@Z; AUTO_REMOVE_LOCK::FindAdapterAndAcquire(_LUID *)
0x1400642ce  lea     rdi, [rsi+5Ch]
0x1400642d2  mov     [rsp+380h+var_34C], eax
0x1400642d6  mov     r8, rdi
0x1400642d9  mov     r9d, 21Eh
0x1400642df  mov     edx, 414h
0x1400642e4  mov     ecx, eax
0x1400642e6  call    ?CheckFailed@@YA_NJW4_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE@@AEAU_DISPLAYMUX_SWITCH_CONTEXT@@IPEAD@Z; CheckFailed(long,_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE,_DISPLAYMUX_SWITCH_CONTEXT &,uint,char *)
0x1400642eb  test    al, al
0x1400642ed  jz      short loc_140064302
0x1400642ef  lea     rcx, [rsp+380h+var_330]; this
0x1400642f4  call    ?Release@AUTO_REMOVE_LOCK@@QEAAXXZ; AUTO_REMOVE_LOCK::Release(void)
0x1400642f9  cmp     [rsp+380h+var_350], bl
0x1400642fd  jmp     loc_14006498F
0x140064302  lea     rdx, [rsi+50h]; struct _LUID *
0x140064306  mov     [rsp+380h+var_340], rbx
0x14006430b  lea     rcx, [rsp+380h+var_340]; this
0x140064310  mov     [rsp+380h+var_338], bl
0x140064314  call    ?FindAdapterAndAcquire@AUTO_REMOVE_LOCK@@QEAAJPEAU_LUID@@@Z; AUTO_REMOVE_LOCK::FindAdapterAndAcquire(_LUID *)
0x140064319  mov     r9d, 226h
0x14006431f  mov     [rsp+380h+var_34C], eax
0x140064323  mov     r8, rdi
0x140064326  mov     edx, 415h
0x14006432b  mov     ecx, eax
0x14006432d  call    ?CheckFailed@@YA_NJW4_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE@@AEAU_DISPLAYMUX_SWITCH_CONTEXT@@IPEAD@Z; CheckFailed(long,_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE,_DISPLAYMUX_SWITCH_CONTEXT &,uint,char *)
0x140064332  test    al, al
0x140064334  jz      short loc_14006434C
0x140064336  lea     rcx, [rsp+380h+var_340]; this
0x14006433b  call    ?Release@AUTO_REMOVE_LOCK@@QEAAXXZ; AUTO_REMOVE_LOCK::Release(void)
0x140064340  jmp     short loc_1400642EF
0x140064342  call    ?ReleaseMiniportListMutex@@YAXXZ; ReleaseMiniportListMutex(void)
0x140064347  jmp     loc_1400652A7
0x14006434c  xor     eax, eax
0x14006434e  mov     [rsp+380h+var_320], rsi
0x140064353  or      ecx, 0FFFFFFFFh
0x140064356  mov     [rbp+280h+var_2E0], rax
0x14006435a  xorps   xmm0, xmm0
0x14006435d  mov     [rbp+280h+var_2D4], ecx
0x140064360  mov     r13d, 1
0x140064366  mov     [rsp+380h+var_304], ecx
0x14006436a  mov     rcx, cs:qword_14015F448; this
0x140064371  mov     dl, r13b; bool
0x140064374  mov     [rsp+380h+var_318], r13b
0x140064379  mov     [rbp+280h+var_2D8], eax
0x14006437c  movdqu  [rbp+280h+var_2D0], xmm0
0x140064381  mov     [rbp+280h+var_2C0], bl
0x140064384  mov     [rsp+380h+var_310], rax
0x140064389  mov     [rsp+380h+var_308], eax
0x14006438d  movdqu  [rbp+280h+var_300], xmm0
0x140064392  mov     [rbp+280h+var_2F0], bl
0x140064395  call    ?SetDisableProcessingDisplayBatchesStatus@DISPLAY_MUX_MGR@@QEAAX_N@Z; DISPLAY_MUX_MGR::SetDisableProcessingDisplayBatchesStatus(bool)
0x14006439a  lea     rax, [rsp+380h+var_34C]
0x14006439f  mov     [rbp+280h+var_2B0], rsi
0x1400643a3  mov     [rbp+280h+var_2B8], rax
0x1400643a7  lea     rcx, [rbp+280h+var_200]; void *
0x1400643ae  lea     rax, [rbp+280h+arg_8]
0x1400643b5  mov     [rbp+280h+var_2A0], r13b
0x1400643b9  xor     edx, edx; Val
0x1400643bb  mov     [rbp+280h+var_2A8], rax
0x1400643bf  mov     r8d, 0D1h; Size
0x1400643c5  mov     [rbp+280h+var_248], ebx
0x1400643c8  mov     word ptr [rsp+380h+var_348], bx
0x1400643cd  call    memset
0x1400643d2  mov     r13, [rsp+380h+var_330]
0x1400643d7  xor     r9d, r9d; Alertable
0x1400643da  xor     r8d, r8d; WaitMode
0x1400643dd  mov     [rsp+380h+Timeout], r14; Timeout
0x1400643e2  xor     edx, edx; WaitReason
0x1400643e4  lea     rbx, [r13+11B8h]
0x1400643eb  mov     rcx, rbx; Object
0x1400643ee  call    cs:__imp_KeWaitForSingleObject
0x1400643f5  nop     dword ptr [rax+rax+00h]
0x1400643fa  mov     eax, [r13+11B0h]
0x140064401  mov     ecx, 3
0x140064406  cmp     [r13+12CAh], cx
0x14006440e  mov     ecx, 1
0x140064413  mov     [rbp+280h+var_268], eax
0x140064416  movzx   eax, [rbp+280h+var_200]
0x14006441d  cmovz   eax, ecx
0x140064420  xor     edx, edx; Wait
0x140064422  mov     rcx, rbx; Mutex
0x140064425  mov     [rbp+280h+var_200], al
0x14006442b  call    cs:__imp_KeReleaseMutex
0x140064432  nop     dword ptr [rax+rax+00h]
0x140064437  mov     rdx, [rsp+380h+var_340]
0x14006443c  lea     rcx, [rbp+280h+var_298]
0x140064440  call    ??0CInterfaceCallContext@@QEAA@PEAU_FDO_CONTEXT@@W4LocksToAcquire@@@Z; CInterfaceCallContext::CInterfaceCallContext(_FDO_CONTEXT *,LocksToAcquire)
0x140064445  mov     ecx, [rbp+280h+var_278]
0x140064448  mov     r9d, 266h
0x14006444e  mov     r8, rdi
0x140064451  mov     edx, 404h
0x140064456  call    ?CheckFailed@@YA_NJW4_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE@@AEAU_DISPLAYMUX_SWITCH_CONTEXT@@IPEAD@Z; CheckFailed(long,_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE,_DISPLAYMUX_SWITCH_CONTEXT &,uint,char *)
0x14006445b  test    al, al
0x14006445d  jnz     loc_1400644EC
0x140064463  mov     rbx, [rbp+280h+var_290]
0x140064467  cmp     [rbx+1929h], r14b
0x14006446e  jnz     short loc_1400644D6
0x140064470  xor     edx, edx; Val
0x140064472  lea     rcx, [rbp+280h+var_120]; void *
0x140064479  mov     r8d, 0D1h; Size
0x14006447f  call    memset
0x140064484  mov     rcx, cs:qword_14015F448; this
0x14006448b  lea     rdx, [rbp+280h+var_120]; struct _DXGK_DISPLAYMUX_SET_INTERNAL_PANEL_INFO *
0x140064492  call    ?GetInternalPanelInfo@DISPLAY_MUX_MGR@@QEBA_NPEAU_DXGK_DISPLAYMUX_SET_INTERNAL_PANEL_INFO@@@Z; DISPLAY_MUX_MGR::GetInternalPanelInfo(_DXGK_DISPLAYMUX_SET_INTERNAL_PANEL_INFO *)
0x140064497  test    al, al
0x140064499  jz      loc_140064526
0x14006449f  mov     edx, [rsi+58h]
0x1400644a2  lea     r8, [rbp+280h+var_120]
0x1400644a9  mov     rcx, rbx
0x1400644ac  call    DpiDxgkDdiDisplayMuxSetInternalPanelInfo
0x1400644b1  mov     ecx, [rbp+280h+var_278]
0x1400644b4  mov     r9d, 274h
0x1400644ba  mov     r8, rdi
0x1400644bd  mov     [rsp+380h+var_34C], eax
0x1400644c1  mov     edx, 419h
0x1400644c6  call    ?CheckFailed@@YA_NJW4_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE@@AEAU_DISPLAYMUX_SWITCH_CONTEXT@@IPEAD@Z; CheckFailed(long,_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE,_DISPLAYMUX_SWITCH_CONTEXT &,uint,char *)
0x1400644cb  test    al, al
0x1400644cd  jnz     short loc_1400644EC
0x1400644cf  mov     byte ptr [rbx+1929h], 1
0x1400644d6  mov     r8, rdi
0x1400644d9  mov     edx, 403h
0x1400644de  mov     ecx, 4
0x1400644e3  call    ?CheckForMdmFaultOrDelayInjection@@YA_NW4_D3DKMT_DISPLAYMUX_SWITCH_INJECTION_STAGE@@W4_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE@@AEAU_DISPLAYMUX_SWITCH_CONTEXT@@@Z; CheckForMdmFaultOrDelayInjection(_D3DKMT_DISPLAYMUX_SWITCH_INJECTION_STAGE,_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE,_DISPLAYMUX_SWITCH_CONTEXT &)
0x1400644e8  test    al, al
0x1400644ea  jz      short loc_140064540
0x1400644ec  lea     rcx, [rbp+280h+var_298]; this
0x1400644f0  call    ??1CInterfaceCallContext@@QEAA@XZ; CInterfaceCallContext::~CInterfaceCallContext(void)
0x1400644f5  lea     rcx, [rbp+280h+var_2B8]
0x1400644f9  call    _DXGKCALLONEXIT__lambda_5bf16074e78eca97c9745c10e52e39f7_______2___DXGKCALLONEXIT___DXGKCALLONEXIT
0x1400644fe  lea     rcx, [rsp+380h+var_320]
0x140064503  call    _DXGKCALLONEXIT__lambda_8e64b2d4059ca463867f9c5833a46b2d_______2___DXGKCALLONEXIT___DXGKCALLONEXIT
0x140064508  lea     rcx, [rsp+380h+var_340]; this
0x14006450d  call    ?Release@AUTO_REMOVE_LOCK@@QEAAXXZ; AUTO_REMOVE_LOCK::Release(void)
0x140064512  lea     rcx, [rsp+380h+var_330]; this
0x140064517  call    ?Release@AUTO_REMOVE_LOCK@@QEAAXXZ; AUTO_REMOVE_LOCK::Release(void)
0x14006451c  cmp     [rsp+380h+var_350], r14b
0x140064521  jmp     loc_14006498F
0x140064526  mov     r9d, 27Dh
0x14006452c  mov     r8, rdi
0x14006452f  mov     edx, 41Bh
0x140064534  mov     ecx, 0C0000001h
0x140064539  call    ?CheckFailed@@YA_NJW4_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE@@AEAU_DISPLAYMUX_SWITCH_CONTEXT@@IPEAD@Z; CheckFailed(long,_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE,_DISPLAYMUX_SWITCH_CONTEXT &,uint,char *)
0x14006453e  jmp     short loc_1400644EC
0x140064540  movsd   xmm0, qword ptr [rsi+50h]
0x140064545  lea     r8, [rbp+280h+var_240]
0x140064549  mov     eax, [rsi+58h]
0x14006454c  lea     rcx, [rsp+380h+var_310]
0x140064551  mov     rdx, [rbx+0FC0h]
0x140064558  movsd   [rbp+280h+var_240], xmm0
0x14006455d  mov     [rbp+280h+var_238], eax
0x140064560  call    ?TakePowerReference@TARGET_POWER_REFERENCE@@QEAAXQEAXU_DISPLAYCONFIG_DISPLAYMUX_TARGET@@@Z; TARGET_POWER_REFERENCE::TakePowerReference(void * const,_DISPLAYCONFIG_DISPLAYMUX_TARGET)
0x140064565  mov     rax, [rsi+50h]
0x140064569  mov     rcx, rbx
0x14006456c  mov     edx, [rsi+58h]
0x14006456f  mov     r8d, [rbp+280h+var_268]
0x140064573  mov     [rsi+14h], rax
0x140064577  mov     [rsi+1Ch], edx
0x14006457a  call    DpiDxgkDdiDisplayMuxPreSwitchTo
0x14006457f  test    eax, eax
0x140064581  js      short loc_14006458A
0x140064583  mov     dword ptr [rsi+4], 2
0x14006458a  mov     r9d, 28Dh
0x140064590  mov     [rsp+380h+var_34C], eax
0x140064594  mov     r8, rdi
0x140064597  mov     edx, 403h
0x14006459c  mov     ecx, eax
0x14006459e  call    ?CheckFailed@@YA_NJW4_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE@@AEAU_DISPLAYMUX_SWITCH_CONTEXT@@IPEAD@Z; CheckFailed(long,_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE,_DISPLAYMUX_SWITCH_CONTEXT &,uint,char *)
0x1400645a3  lea     rcx, [rbp+280h+var_298]; this
0x1400645a7  test    al, al
0x1400645a9  jz      short loc_1400645B5
0x1400645ab  call    ??1CInterfaceCallContext@@QEAA@XZ; CInterfaceCallContext::~CInterfaceCallContext(void)
0x1400645b0  jmp     loc_140064664
0x1400645b5  mov     bl, [rbx+1928h]
0x1400645bb  mov     [rsp+380h+var_344], bl
0x1400645bf  call    ??1CInterfaceCallContext@@QEAA@XZ; CInterfaceCallContext::~CInterfaceCallContext(void)
0x1400645c4  test    bl, bl
0x1400645c6  jnz     loc_1400646F3
0x1400645cc  mov     ebx, 417h
0x1400645d1  cmp     [rbp+280h+var_200], r14b
0x1400645d8  jz      short loc_140064635
0x1400645da  mov     edx, [rsi+4Ch]; unsigned int
0x1400645dd  lea     r8, [rbp+280h+var_1FF]; struct _DXGK_BRIGHTNESS_CAPS *
0x1400645e4  mov     rcx, [r13+18h]; void *
0x1400645e8  call    ?DpiBrightness3GetCaps@@YAJPEAXKPEAU_DXGK_BRIGHTNESS_CAPS@@@Z; DpiBrightness3GetCaps(void *,ulong,_DXGK_BRIGHTNESS_CAPS *)
0x1400645ed  mov     r9d, 2A0h
0x1400645f3  mov     [rsp+380h+var_34C], eax
0x1400645f7  mov     r8, rdi
0x1400645fa  lea     edx, [rbx-1]
0x1400645fd  mov     ecx, eax
0x1400645ff  call    ?CheckFailed@@YA_NJW4_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE@@AEAU_DISPLAYMUX_SWITCH_CONTEXT@@IPEAD@Z; CheckFailed(long,_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE,_DISPLAYMUX_SWITCH_CONTEXT &,uint,char *)
0x140064604  test    al, al
0x140064606  jnz     short loc_140064664
0x140064608  mov     edx, [rsi+4Ch]; unsigned int
0x14006460b  lea     r8, [rbp+280h+var_1FB]; struct _DXGK_BRIGHTNESS_GET_NIT_RANGES_OUT *
0x140064612  mov     rcx, [r13+18h]; void *
0x140064616  call    ?DpiBrightness3GetNitRanges@@YAJPEAXKPEAU_DXGK_BRIGHTNESS_GET_NIT_RANGES_OUT@@@Z; DpiBrightness3GetNitRanges(void *,ulong,_DXGK_BRIGHTNESS_GET_NIT_RANGES_OUT *)
0x14006461b  mov     r9d, 2A6h
0x140064621  mov     [rsp+380h+var_34C], eax
0x140064625  mov     r8, rdi
0x140064628  mov     edx, ebx
0x14006462a  mov     ecx, eax
0x14006462c  call    ?CheckFailed@@YA_NJW4_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE@@AEAU_DISPLAYMUX_SWITCH_CONTEXT@@IPEAD@Z; CheckFailed(long,_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE,_DISPLAYMUX_SWITCH_CONTEXT &,uint,char *)
0x140064631  test    al, al
0x140064633  jnz     short loc_140064664
0x140064635  mov     edx, [rsi+4Ch]
0x140064638  lea     r8, [rsp+380h+var_348]
0x14006463d  mov     rcx, [r13+18h]
0x140064641  call    DpiGetIntegratedEdidSizeForDisplayMuxTarget
0x140064646  mov     r9d, 2AEh
0x14006464c  mov     [rsp+380h+var_34C], eax
0x140064650  mov     r8, rdi
0x140064653  mov     edx, ebx
0x140064655  mov     ecx, eax
0x140064657  call    ?CheckFailed@@YA_NJW4_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE@@AEAU_DISPLAYMUX_SWITCH_CONTEXT@@IPEAD@Z; CheckFailed(long,_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE,_DISPLAYMUX_SWITCH_CONTEXT &,uint,char *)
0x14006465c  test    al, al
0x14006465e  jz      loc_1400646EB
0x140064664  lea     rcx, [rbp+280h+var_2B8]
0x140064668  call    _DXGKCALLONEXIT__lambda_5bf16074e78eca97c9745c10e52e39f7_______2___DXGKCALLONEXIT___DXGKCALLONEXIT
0x14006466d  xor     esi, esi
0x14006466f  cmp     [rbp+280h+var_2F0], sil
0x140064673  jz      short loc_1400646C3
0x140064675  cmp     cs:bTracingEnabled, sil
0x14006467c  mov     rbx, qword ptr [rbp+280h+var_300]
0x140064680  mov     edi, [rsp+380h+var_304]
0x140064684  jz      short loc_1400646A6
0x140064686  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 2
0x14006468d  jz      short loc_1400646A6
0x14006468f  mov     dword ptr [rsp+380h+var_358], esi
0x140064693  lea     rdx, Dxgk_ReportPowerComponentState
0x14006469a  mov     r9, rbx
0x14006469d  mov     dword ptr [rsp+380h+Timeout], edi
0x1400646a1  call    McTemplateK0pqq_EtwWriteTransfer
0x1400646a6  mov     rcx, [rbx+0D10h]
0x1400646ad  test    rcx, rcx
0x1400646b0  jz      short loc_1400646C3
0x1400646b2  xor     r8d, r8d
0x1400646b5  mov     edx, edi
0x1400646b7  call    cs:__imp_PoFxIdleComponent
0x1400646be  nop     dword ptr [rax+rax+00h]
0x1400646c3  lea     rcx, [rsp+380h+var_320]
0x1400646c8  call    _DXGKCALLONEXIT__lambda_8e64b2d4059ca463867f9c5833a46b2d_______2___DXGKCALLONEXIT___DXGKCALLONEXIT
0x1400646cd  lea     rcx, [rsp+380h+var_340]; this
0x1400646d2  call    ?Release@AUTO_REMOVE_LOCK@@QEAAXXZ; AUTO_REMOVE_LOCK::Release(void)
0x1400646d7  lea     rcx, [rsp+380h+var_330]; this
0x1400646dc  call    ?Release@AUTO_REMOVE_LOCK@@QEAAXXZ; AUTO_REMOVE_LOCK::Release(void)
0x1400646e1  cmp     [rsp+380h+var_350], sil
0x1400646e6  jmp     loc_14006498F
0x1400646eb  movzx   eax, word ptr [rsp+380h+var_348]
0x1400646f0  mov     [rbp+280h+var_248], eax
0x1400646f3  mov     rdx, r13
0x1400646f6  lea     rcx, [rbp+280h+var_298]
0x1400646fa  call    ??0CInterfaceCallContext@@QEAA@PEAU_FDO_CONTEXT@@W4LocksToAcquire@@@Z; CInterfaceCallContext::CInterfaceCallContext(_FDO_CONTEXT *,LocksToAcquire)
0x1400646ff  mov     ecx, [rbp+280h+var_278]
0x140064702  mov     r9d, 2B8h
0x140064708  mov     r8, rdi
0x14006470b  mov     edx, 405h
0x140064710  call    ?CheckFailed@@YA_NJW4_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE@@AEAU_DISPLAYMUX_SWITCH_CONTEXT@@IPEAD@Z; CheckFailed(long,_D3DKMT_DISPLAYMUX_SWITCH_ERROR_STAGE,_DISPLAYMUX_SWITCH_CONTEXT &,uint,char *)
0x140064715  xor     r13d, r13d
0x140064718  test    al, al
0x14006471a  jz      short loc_140064745
0x14006471c  lea     rcx, [rbp+280h+var_298]; this
0x140064720  call    ??1CInterfaceCallContext@@QEAA@XZ; CInterfaceCallContext::~CInterfaceCallContext(void)
0x140064725  lea     rcx, [rbp+280h+var_2B8]
0x140064729  call    _DXGKCALLONEXIT__lambda_5bf16074e78eca97c9745c10e52e39f7_______2___DXGKCALLONEXIT___DXGKCALLONEXIT
0x14006472e  cmp     [rbp+280h+var_2F0], r13b
0x140064732  jz      loc_14006496C
0x140064738  mov     edi, [rsp+380h+var_304]
0x14006473c  mov     rbx, qword ptr [rbp+280h+var_300]
0x140064740  jmp     loc_140064925
  ... truncated ...
```
