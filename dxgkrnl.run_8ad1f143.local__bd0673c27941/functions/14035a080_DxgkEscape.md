# DxgkEscape

- ea: `0x14035a080`
- end: `0x14035cf0f`
- name: `DxgkEscape`
- size: `11919`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `89`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x140285ce0`

## callees

- `0x140009030`
- `0x14000d7d0`
- `0x140012380`
- `0x140012b14`
- `0x140013860`
- `0x1400155fc`
- `0x140015780`
- `0x1400158b0`
- `0x1400159a0`
- `0x140015a00`
- `0x140016300`
- `0x140016830`
- `0x140016e50`
- `0x14001ab20`
- `0x14001b890`
- `0x14001cbe0`
- `0x14001d070`
- `0x14001d0e4`
- `0x14001f088`
- `0x14001f460`
- `0x14002ec90`
- `0x140030820`
- `0x1400308a0`
- `0x140033870`
- `0x140033bb0`
- `0x140035dc0`
- `0x14003fb68`
- `0x140041b54`
- `0x140042498`
- `0x140042a60`
- `0x140044b74`
- `0x140046ac8`
- `0x140047eb4`
- `0x14004d73c`
- `0x140050284`
- `0x14005f728`
- `0x1400606c4`
- `0x1400614cc`
- `0x1400615d8`
- `0x140062130`
- `0x1400670a4`
- `0x14006d9a0`
- `0x140074a84`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0240`
- `0x1400a0540`
- `0x14018f1c8`
- `0x14019551c`
- `0x140196f20`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14035a732`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14035a732`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14035a78b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14035aee2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14035a78b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14035aee2`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14035c6eb`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14035c6eb`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14035a77f`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14035aed6`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14035a77f`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14035aed6`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14035a744`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14035a744`
- `ntoskrnl!KeDelayExecutionThread` at `0x14035bf16`
- `ntoskrnl!KeDelayExecutionThread` at `0x14035bf16`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x14035a120`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x14035a120`
- `watchdog!WdLogSingleEntry2` at `0x14035a581`
- `watchdog!WdLogSingleEntry2` at `0x14035a8b5`
- `watchdog!WdLogSingleEntry2` at `0x14035a9f7`
- `watchdog!WdLogSingleEntry2` at `0x14035afd5`
- `watchdog!WdLogSingleEntry2` at `0x14035b1bb`
- `watchdog!WdLogSingleEntry2` at `0x14035b210`
- `watchdog!WdLogSingleEntry2` at `0x14035b24c`
- `watchdog!WdLogSingleEntry2` at `0x14035b28d`
- `watchdog!WdLogSingleEntry2` at `0x14035b41f`
- `watchdog!WdLogSingleEntry2` at `0x14035b476`
- `watchdog!WdLogSingleEntry2` at `0x14035b6b4`
- `watchdog!WdLogSingleEntry2` at `0x14035b9d6`
- `watchdog!WdLogSingleEntry2` at `0x14035be8d`
- `watchdog!WdLogSingleEntry2` at `0x14035c16e`
- `watchdog!WdLogSingleEntry2` at `0x14035c21a`
- `watchdog!WdLogSingleEntry2` at `0x14035c702`
- `watchdog!WdLogSingleEntry2` at `0x14035c867`
- `watchdog!WdLogSingleEntry2` at `0x14035cda9`
- `watchdog!WdLogSingleEntry2` at `0x14035a581`
- `watchdog!WdLogSingleEntry2` at `0x14035a8b5`
- `watchdog!WdLogSingleEntry2` at `0x14035a9f7`
- `watchdog!WdLogSingleEntry2` at `0x14035afd5`
- `watchdog!WdLogSingleEntry2` at `0x14035b1bb`
- `watchdog!WdLogSingleEntry2` at `0x14035b210`
- `watchdog!WdLogSingleEntry2` at `0x14035b24c`
- `watchdog!WdLogSingleEntry2` at `0x14035b28d`
- `watchdog!WdLogSingleEntry2` at `0x14035b41f`
- `watchdog!WdLogSingleEntry2` at `0x14035b476`
- `watchdog!WdLogSingleEntry2` at `0x14035b6b4`
- `watchdog!WdLogSingleEntry2` at `0x14035b9d6`
- `watchdog!WdLogSingleEntry2` at `0x14035be8d`
- `watchdog!WdLogSingleEntry2` at `0x14035c16e`
- `watchdog!WdLogSingleEntry2` at `0x14035c21a`
- `watchdog!WdLogSingleEntry2` at `0x14035c702`
- `watchdog!WdLogSingleEntry2` at `0x14035c867`
- `watchdog!WdLogSingleEntry2` at `0x14035cda9`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14035c0c6`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14035c12a`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14035c0c6`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14035c12a`
- `watchdog!WdLogSingleEntry3` at `0x14035aba1`
- `watchdog!WdLogSingleEntry3` at `0x14035c2d1`
- `watchdog!WdLogSingleEntry3` at `0x14035aba1`
- `watchdog!WdLogSingleEntry3` at `0x14035c2d1`
- `watchdog!WdLogSingleEntry0` at `0x14035a962`
- `watchdog!WdLogSingleEntry0` at `0x14035ab29`
- `watchdog!WdLogSingleEntry0` at `0x14035ac71`
- `watchdog!WdLogSingleEntry0` at `0x14035ae75`
- `watchdog!WdLogSingleEntry0` at `0x14035b512`
- `watchdog!WdLogSingleEntry0` at `0x14035b7a7`
- `watchdog!WdLogSingleEntry0` at `0x14035ba4c`
- `watchdog!WdLogSingleEntry0` at `0x14035c3fb`
- `watchdog!WdLogSingleEntry0` at `0x14035c649`
- `watchdog!WdLogSingleEntry0` at `0x14035c9a1`
- `watchdog!WdLogSingleEntry0` at `0x14035ca8e`
- `watchdog!WdLogSingleEntry0` at `0x14035cb63`
- `watchdog!WdLogSingleEntry0` at `0x14035cbf8`
- `watchdog!WdLogSingleEntry0` at `0x14035cd00`
- `watchdog!WdLogSingleEntry0` at `0x14035a962`
- `watchdog!WdLogSingleEntry0` at `0x14035ab29`
- `watchdog!WdLogSingleEntry0` at `0x14035ac71`
- `watchdog!WdLogSingleEntry0` at `0x14035ae75`
- `watchdog!WdLogSingleEntry0` at `0x14035b512`
- `watchdog!WdLogSingleEntry0` at `0x14035b7a7`
- `watchdog!WdLogSingleEntry0` at `0x14035ba4c`
- `watchdog!WdLogSingleEntry0` at `0x14035c3fb`
- `watchdog!WdLogSingleEntry0` at `0x14035c649`
- `watchdog!WdLogSingleEntry0` at `0x14035c9a1`
- `watchdog!WdLogSingleEntry0` at `0x14035ca8e`
- `watchdog!WdLogSingleEntry0` at `0x14035cb63`
- `watchdog!WdLogSingleEntry0` at `0x14035cbf8`
- `watchdog!WdLogSingleEntry0` at `0x14035cd00`
- `watchdog!WdLogSingleEntry1` at `0x14035a277`
- `watchdog!WdLogSingleEntry1` at `0x14035ad06`
- `watchdog!WdLogSingleEntry1` at `0x14035af23`
- `watchdog!WdLogSingleEntry1` at `0x14035b30e`
- `watchdog!WdLogSingleEntry1` at `0x14035b3ad`
- `watchdog!WdLogSingleEntry1` at `0x14035b5c9`
- `watchdog!WdLogSingleEntry1` at `0x14035b701`
- `watchdog!WdLogSingleEntry1` at `0x14035b940`
- `watchdog!WdLogSingleEntry1` at `0x14035bd20`
- `watchdog!WdLogSingleEntry1` at `0x14035bd69`
- `watchdog!WdLogSingleEntry1` at `0x14035bdec`
- `watchdog!WdLogSingleEntry1` at `0x14035c372`
- `watchdog!WdLogSingleEntry1` at `0x14035c91e`
- `watchdog!WdLogSingleEntry1` at `0x14035c948`
- `watchdog!WdLogSingleEntry1` at `0x14035ca5e`
- `watchdog!WdLogSingleEntry1` at `0x14035cb33`
- `watchdog!WdLogSingleEntry1` at `0x14035cbc7`
- `watchdog!WdLogSingleEntry1` at `0x14035cc92`
- `watchdog!WdLogSingleEntry1` at `0x14035ce8e`
- `watchdog!WdLogSingleEntry1` at `0x14035a277`
- `watchdog!WdLogSingleEntry1` at `0x14035ad06`
- `watchdog!WdLogSingleEntry1` at `0x14035af23`
- `watchdog!WdLogSingleEntry1` at `0x14035b30e`
- `watchdog!WdLogSingleEntry1` at `0x14035b3ad`
- `watchdog!WdLogSingleEntry1` at `0x14035b5c9`
- `watchdog!WdLogSingleEntry1` at `0x14035b701`
- `watchdog!WdLogSingleEntry1` at `0x14035b940`
- `watchdog!WdLogSingleEntry1` at `0x14035bd20`
- `watchdog!WdLogSingleEntry1` at `0x14035bd69`
- `watchdog!WdLogSingleEntry1` at `0x14035bdec`
- `watchdog!WdLogSingleEntry1` at `0x14035c372`
- `watchdog!WdLogSingleEntry1` at `0x14035c91e`
- `watchdog!WdLogSingleEntry1` at `0x14035c948`
- `watchdog!WdLogSingleEntry1` at `0x14035ca5e`
- `watchdog!WdLogSingleEntry1` at `0x14035cb33`
- `watchdog!WdLogSingleEntry1` at `0x14035cbc7`
- `watchdog!WdLogSingleEntry1` at `0x14035cc92`
- `watchdog!WdLogSingleEntry1` at `0x14035ce8e`

## string_xrefs

- `0x14035bd9c`: `Driver Common Escape is block for (0x%I64x)`

## pseudocode

```c
__int64 __fastcall DxgkEscape(_D3DKMT_ESCAPE *Src, __int64 a2, __int64 a3)
{
  struct DXGPROCESS *Current; // r12
  char CurrentThreadPreviousMode; // al
  UINT PrivateDriverDataSize; // eax
  size_t v7; // rbx
  unsigned int *p_Srca; // r15
  __int64 v9; // r13
  __int64 hAdapter; // rdx
  __int64 v11; // rbx
  __int64 v12; // rcx
  __int64 hContext; // r9
  unsigned __int64 v14; // rdx
  __int64 v15; // rsi
  DXGADAPTER *v16; // rbx
  bool v17; // r8
  __int64 v18; // r9
  unsigned __int64 v19; // rdx
  ADAPTER_RENDER **v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // r8
  DXGPROCESS *v24; // rsi
  unsigned __int8 IsVmProcessOrVmValidation; // al
  __int64 v26; // rbx
  struct DXGPROCESS_RENDER_ADAPTER_INFO *RenderAdapterInfo; // rax
  _DXGKARG_ESCAPE *v28; // rdx
  DXGADAPTER *v29; // rcx
  int InvalidModesForTestPurposes; // eax
  int v31; // eax
  DXGPROCESS *v32; // r8
  int v33; // r8d
  bool v34; // al
  __int64 v35; // rbx
  unsigned __int8 v36; // al
  int v37; // eax
  int v38; // ebx
  __int64 v39; // rcx
  __int64 v40; // r8
  D3DKMT_HANDLE v41; // eax
  __int64 v42; // rdx
  DXGPROCESS *v43; // r8
  int v44; // r8d
  bool v45; // al
  __int64 v46; // rdx
  __int64 v47; // rcx
  D3DKMT_HANDLE v48; // r12d
  D3DKMT_HANDLE v49; // ebx
  DXGPROCESS *v50; // rcx
  unsigned int v51; // ecx
  bool v52; // al
  __int64 v53; // rcx
  _DWORD *v54; // rax
  unsigned int v55; // ecx
  __int64 v57; // rcx
  __int64 v58; // rax
  __int64 v59; // rcx
  __int64 v60; // r8
  ADAPTER_DISPLAY *v61; // rcx
  const wchar_t *v62; // r9
  __int64 v63; // rcx
  __int64 v64; // r8
  __int64 v65; // rcx
  __int64 v66; // r8
  __int64 v67; // rcx
  __int64 v68; // r8
  __int64 v69; // rcx
  __int64 v70; // r8
  __int64 v71; // rcx
  __int64 v72; // r8
  __int64 v73; // rcx
  __int64 v74; // rcx
  unsigned __int64 v75; // rcx
  __int64 v76; // rdx
  unsigned __int64 v77; // rcx
  __int64 v78; // rdx
  unsigned int v79; // eax
  struct DXGPROCESS *v80; // rax
  struct DXGADAPTER *v81; // rbx
  DXGGLOBAL *Global; // rax
  DXGGLOBAL *v83; // rax
  unsigned __int64 v84; // rcx
  __int64 v85; // rdx
  void *v86; // r9
  int v87; // eax
  void *v88; // r9
  int v89; // eax
  unsigned int v90; // ecx
  __int64 v91; // rcx
  char v92; // al
  unsigned int v93; // esi
  unsigned int v94; // ebx
  unsigned int HostProcess; // eax
  int v96; // eax
  unsigned __int64 v97; // rdx
  unsigned int v98; // eax
  unsigned int v99; // eax
  __int64 v100; // rcx
  struct _D3DKMT_VIDSCH_ESCAPE *v101; // r8
  struct _VIDSCH_GLOBAL *v102; // rdx
  __int64 v103; // rcx
  __int64 v104; // rdx
  _QWORD *v105; // rbx
  struct DXGADAPTER *v106; // rbx
  int v107; // eax
  DXGDEVICE *v108; // r10
  char v109; // r9
  unsigned int NumDifferentPhysicalAdapters; // eax
  unsigned int v111; // r8d
  int v112; // eax
  __int64 v113; // rax
  const wchar_t *v114; // r9
  __int64 v115; // rax
  __int64 v116; // rcx
  int DiagnosticsBuffer; // eax
  unsigned int v118; // [rsp+50h] [rbp-528h] BYREF
  __int64 v119; // [rsp+58h] [rbp-520h]
  char v120; // [rsp+60h] [rbp-518h]
  unsigned __int8 v121; // [rsp+68h] [rbp-510h] BYREF
  char v122; // [rsp+69h] [rbp-50Fh]
  enum _D3DKMT_ESCAPETYPE v123[2]; // [rsp+70h] [rbp-508h] BYREF
  __int64 v124; // [rsp+78h] [rbp-500h] BYREF
  _D3DKMT_ESCAPE v125; // [rsp+80h] [rbp-4F8h] BYREF
  DXGADAPTER *v126[2]; // [rsp+A0h] [rbp-4D8h] BYREF
  unsigned __int64 v127; // [rsp+B0h] [rbp-4C8h] BYREF
  bool v128; // [rsp+B8h] [rbp-4C0h]
  DXGPROCESS *v129; // [rsp+C0h] [rbp-4B8h]
  DXGADAPTER *v130[2]; // [rsp+C8h] [rbp-4B0h] BYREF
  DXGADAPTER *v131; // [rsp+D8h] [rbp-4A0h] BYREF
  DXGDEVICE *v132; // [rsp+E0h] [rbp-498h]
  char v133[8]; // [rsp+E8h] [rbp-490h] BYREF
  __int64 v134; // [rsp+F0h] [rbp-488h]
  char v135; // [rsp+F8h] [rbp-480h]
  __int64 v136; // [rsp+100h] [rbp-478h]
  __int64 v137; // [rsp+108h] [rbp-470h]
  struct DXGADAPTER *pPrivateDriverData; // [rsp+110h] [rbp-468h]
  union _LARGE_INTEGER Interval; // [rsp+118h] [rbp-460h] BYREF
  __int64 v140; // [rsp+120h] [rbp-458h]
  unsigned int *v141; // [rsp+128h] [rbp-450h]
  _DXGKARG_ESCAPE v142; // [rsp+130h] [rbp-448h] BYREF
  unsigned __int64 v143; // [rsp+168h] [rbp-410h] BYREF
  char v144[8]; // [rsp+170h] [rbp-408h] BYREF
  struct _DXGK_DISPLAY_SCENARIO_CONTEXT *v145; // [rsp+178h] [rbp-400h]
  _BYTE v146[24]; // [rsp+180h] [rbp-3F8h] BYREF
  __int64 v147; // [rsp+198h] [rbp-3E0h] BYREF
  struct _D3DDDI_ESCAPEFLAGS::$DB860278E5E511C34FE0F76D94154466::$9A2C51F7B5B2EC690ABA117774D32C3A v148; // [rsp+1A0h] [rbp-3D8h]
  int v149; // [rsp+1A4h] [rbp-3D4h]
  unsigned int *v150; // [rsp+1A8h] [rbp-3D0h]
  UINT v151; // [rsp+1B0h] [rbp-3C8h]
  int v152; // [rsp+1B4h] [rbp-3C4h]
  __int64 v153; // [rsp+1B8h] [rbp-3C0h]
  __int64 v154; // [rsp+1C0h] [rbp-3B8h]
  __int64 v155; // [rsp+1C8h] [rbp-3B0h] BYREF
  struct _D3DDDI_ESCAPEFLAGS::$DB860278E5E511C34FE0F76D94154466::$9A2C51F7B5B2EC690ABA117774D32C3A Value; // [rsp+1D0h] [rbp-3A8h]
  int v157; // [rsp+1D4h] [rbp-3A4h]
  unsigned int *v158; // [rsp+1D8h] [rbp-3A0h]
  UINT v159; // [rsp+1E0h] [rbp-398h]
  int v160; // [rsp+1E4h] [rbp-394h]
  __int64 v161; // [rsp+1E8h] [rbp-390h]
  __int64 v162; // [rsp+1F0h] [rbp-388h]
  _BYTE v163[24]; // [rsp+1F8h] [rbp-380h] BYREF
  _BYTE v164[64]; // [rsp+210h] [rbp-368h] BYREF
  _BYTE v165[144]; // [rsp+250h] [rbp-328h] BYREF
  _OWORD v166[3]; // [rsp+2E0h] [rbp-298h] BYREF
  _OWORD v167[3]; // [rsp+310h] [rbp-268h] BYREF
  char Srca; // [rsp+340h] [rbp-238h] BYREF

  v118 = -1;
  v119 = 0;
  if ( (qword_14015C500 & 2) != 0 )
  {
    v120 = 1;
    v118 = 2016;
    if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(Src, EventProfilerEnter, a3, 2016);
  }
  else
  {
    v120 = 0;
  }
  DXGETWPROFILER_BASE::PushProfilerEntry(&v118, 2016);
  Current = DXGPROCESS::GetCurrent();
  v129 = Current;
  memset(&v125, 0, sizeof(v125));
  CurrentThreadPreviousMode = PsGetCurrentThreadPreviousMode();
  v122 = CurrentThreadPreviousMode;
  if ( !Current )
  {
    LODWORD(v15) = -1073741811;
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 1477;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Invalid process context, returning 0x%I64x",
      -1073741811,
      0,
      0,
      0,
      0);
    goto LABEL_69;
  }
  if ( CurrentThreadPreviousMode == 1 )
    RtlCopyFromUser(&v125, Src, 0x20u);
  else
    v125 = *Src;
  if ( v125.Type == D3DKMT_ESCAPE_WIN32K_BDD_FALLBACK )
  {
    if ( !(*(unsigned int (**)(void))(*((_QWORD *)Current + 11) + 440LL))() )
    {
LABEL_202:
      DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v118);
      if ( v120 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
        McTemplateK0q_EtwWriteTransfer(v65, EventProfilerExit, v66, v118);
      return 3221225506LL;
    }
  }
  else if ( v125.Type >= D3DKMT_ESCAPE_WIN32K_START )
  {
    v38 = (*(__int64 (__fastcall **)(_D3DKMT_ESCAPE *))(*((_QWORD *)Current + 11) + 432LL))(&v125);
    goto LABEL_127;
  }
  if ( (v125.Type == D3DKMT_ESCAPE_VIDMM || v125.Type == D3DKMT_ESCAPE_VIDSCH || (unsigned int)(v125.Type - 28) < 2)
    && !InternalEscapeEnabled() )
  {
    WdLogSingleEntry1(3);
    WdLogGlobalForLineNumber = 1520;
    goto LABEL_202;
  }
  if ( v125.Type == D3DKMT_ESCAPE_VIDMM && v125.PrivateDriverDataSize < 0x840 )
    goto LABEL_189;
  *(_OWORD *)v126 = 0;
  PrivateDriverDataSize = v125.PrivateDriverDataSize;
  if ( v125.Type == D3DKMT_ESCAPE_VIDSCH && v125.PrivateDriverDataSize <= 0x30 )
    PrivateDriverDataSize = 48;
  v7 = PrivateDriverDataSize;
  if ( PrivateDriverDataSize > 0x200 )
  {
    p_Srca = (unsigned int *)operator new[](PrivateDriverDataSize, 1265072196, 258);
    v126[0] = (DXGADAPTER *)p_Srca;
  }
  else
  {
    p_Srca = (unsigned int *)&Srca;
  }
  v141 = p_Srca;
  if ( !p_Srca )
  {
    LODWORD(v15) = -1073741801;
    WdLogSingleEntry2(6, v7);
    WdLogGlobalForLineNumber = 1588;
    DxgkLogInternalTriageEvent(
      0,
      262145,
      -1,
      (unsigned int)L"Out of memory allocating private driver data (size 0x%I64x), returning 0x%I64x",
      v7,
      -1073741801,
      0,
      0,
      0);
LABEL_250:
    DxgkEscape_::_2_::ENSURE_DATA_DELETION::_ENSURE_DATA_DELETION(v126);
LABEL_69:
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v118);
    if ( v120 )
    {
      if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
        McTemplateK0q_EtwWriteTransfer(v21, EventProfilerExit, v22, v118);
    }
    return (unsigned int)v15;
  }
  if ( v125.Type == D3DKMT_ESCAPE_VIDSCH )
    memset(p_Srca, 0, v7);
  if ( v122 == 1 )
    RtlCopyFromUser(p_Srca, v125.pPrivateDriverData, v125.PrivateDriverDataSize);
  else
    memmove(p_Srca, v125.pPrivateDriverData, v125.PrivateDriverDataSize);
  if ( (*(_BYTE *)&v125.Flags.0 & 0x40) != 0 && (v125.Type || !v125.hAdapter || (*(_BYTE *)&v125.Flags.0 & 1) != 0) )
  {
    WdLogSingleEntry0(3);
    WdLogGlobalForLineNumber = 1619;
    goto LABEL_188;
  }
  if ( v125.Type > D3DKMT_ESCAPE_SOFTGPU_ENABLE_DISABLE_HMD )
  {
    switch ( v125.Type )
    {
      case D3DKMT_ESCAPE_IDD_REQUEST:
        goto LABEL_121;
      case D3DKMT_ESCAPE_LOG_CODEPOINT_PACKET:
        if ( v125.PrivateDriverDataSize != 16 )
          goto LABEL_188;
        v141 = 0;
        DxgkLogCodePointPacket(*p_Srca, p_Srca[1], p_Srca[2]);
LABEL_206:
        DxgkEscape_::_2_::ENSURE_DATA_DELETION::_ENSURE_DATA_DELETION(v126);
        DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v118);
        if ( v120 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
          McTemplateK0q_EtwWriteTransfer(v67, EventProfilerExit, v68, v118);
        return 0;
      case D3DKMT_ESCAPE_LOG_USERMODE_DAIG_PACKET:
        if ( v125.PrivateDriverDataSize < 0x30 || v125.PrivateDriverDataSize < p_Srca[1] )
          goto LABEL_188;
        v31 = DxgkWriteUserModeDiagEntry((struct _DXGK_DIAG_HEADER *)p_Srca);
        break;
      case D3DKMT_ESCAPE_GET_EXTERNAL_DIAGNOSTICS:
        goto LABEL_558;
      case D3DKMT_ESCAPE_GET_DISPLAY_CONFIGURATIONS|D3DKMT_ESCAPE_TDRDBGCTRL:
        if ( v125.PrivateDriverDataSize < 4 )
          goto LABEL_188;
        v31 = DxgkHandleCcdDatabaseRequests(*p_Srca, v125.PrivateDriverDataSize, p_Srca);
        break;
      case D3DKMT_ESCAPE_WIN32K_BDD_FALLBACK:
        v31 = DxgkpProcessBddFallbackRequest();
        break;
      default:
        goto LABEL_31;
    }
LABEL_273:
    v38 = v31;
    goto LABEL_201;
  }
  switch ( v125.Type )
  {
    case D3DKMT_ESCAPE_SOFTGPU_ENABLE_DISABLE_HMD:
      if ( g_OSTestSigningEnabled )
      {
        if ( v125.PrivateDriverDataSize != 200 )
          goto LABEL_188;
        v80 = DXGPROCESS::GetCurrent();
        if ( !v80 )
        {
          WdLogSingleEntry0(2);
          WdLogGlobalForLineNumber = 1824;
          DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Invalid process context", 1824, 0, 0, 0, 0);
          goto LABEL_188;
        }
        DXGUSERCRIT::DXGUSERCRIT((DXGUSERCRIT *)v163, v80);
        DXGUSERCRIT::Acquire((DXGUSERCRIT *)v163, 1);
        v144[0] = 0;
        CDisplayScenarioContextScope::ContextScopeConstructor((CDisplayScenarioContextScope *)v144, 0, 0x2Eu, 0);
        v38 = DxgkEnableDisableTargetAsHMD(
                (struct _D3DKMT_SOFTGPU_LUID_TARGET *)p_Srca,
                p_Srca[48],
                *((_BYTE *)p_Srca + 196),
                v145);
        CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)v144);
        DXGUSERCRIT::~DXGUSERCRIT((DXGUSERCRIT *)v163);
        goto LABEL_201;
      }
      goto LABEL_326;
    case D3DKMT_ESCAPE_VIDMM:
      v79 = *p_Srca;
      if ( *p_Srca == 5 )
      {
        v31 = DxgEscapeEvict((struct _D3DKMT_VIDMM_ESCAPE *)p_Srca);
      }
      else if ( v79 == 6 )
      {
        v31 = DxgEscapeEvictByNtHandle((struct _D3DKMT_VIDMM_ESCAPE *)p_Srca);
      }
      else
      {
        if ( v79 != 13 )
        {
          if ( v79 == 20 && (p_Srca[2] & 1) != 0 )
            *((_BYTE *)DXGGLOBAL::GetGlobal() + 305952) = 1;
          break;
        }
        v31 = DxgEscapeEvictByCriteria((struct _D3DKMT_VIDMM_ESCAPE *)p_Srca);
      }
      goto LABEL_273;
    case D3DKMT_ESCAPE_DRT_TEST:
      if ( v125.PrivateDriverDataSize < 0xC || v125.PrivateDriverDataSize < p_Srca[1] || *p_Srca != 1484026436 )
      {
        WdLogSingleEntry1(3);
        WdLogGlobalForLineNumber = 1675;
        goto LABEL_188;
      }
      if ( !InternalEscapeEnabled() )
      {
        WdLogSingleEntry1(3);
        WdLogGlobalForLineNumber = 1680;
        goto LABEL_326;
      }
      v75 = p_Srca[2];
      if ( (_DWORD)v75 || v125.hAdapter )
      {
        if ( (unsigned int)v75 > 0x34 || (v76 = 0x14001093482000LL, !_bittest64(&v76, v75)) )
        {
          if ( (_DWORD)v75 != 54
            || !(unsigned int)Feature_DisplayMux_PostGA_BugBundle_3__private_IsEnabledDeviceUsageNoInline() )
          {
            v77 = p_Srca[2];
            if ( (unsigned int)v77 > 0x2F || (v78 = 0xA00800000000LL, !_bittest64(&v78, v77)) )
            {
              if ( (_DWORD)v77 != 53
                || !(unsigned int)Feature_DisplayMux_PostGA_BugBundle_3__private_IsEnabledDeviceUsageNoInline() )
              {
                break;
              }
            }
            v38 = DxgkDrtTestEscape(0, (struct _D3DKMT_DRT_ESCAPE_HEAD *)p_Srca, 0);
            if ( v38 < 0 )
              goto LABEL_201;
            if ( v122 == 1 )
            {
LABEL_280:
              RtlCopyToUser(v125.pPrivateDriverData, p_Srca, v125.PrivateDriverDataSize);
              goto LABEL_201;
            }
LABEL_281:
            memmove(v125.pPrivateDriverData, p_Srca, v125.PrivateDriverDataSize);
            goto LABEL_201;
          }
        }
      }
      v31 = DxgkDrtTestEscape(0, (struct _D3DKMT_DRT_ESCAPE_HEAD *)p_Srca, 0);
      goto LABEL_273;
    case D3DKMT_ESCAPE_DIAGNOSTICS:
LABEL_558:
      DiagnosticsBuffer = GetDiagnosticsBuffer(
                            (struct _D3DKMT_DXGK_DIAGNOSTICS *)p_Srca,
                            v125.PrivateDriverDataSize,
                            v125.Type == D3DKMT_ESCAPE_DIAGNOSTICS);
      v38 = DiagnosticsBuffer;
      if ( (int)(DiagnosticsBuffer + 0x80000000) >= 0 && DiagnosticsBuffer != -2147483643 )
        goto LABEL_201;
      if ( v122 == 1 )
        goto LABEL_280;
      goto LABEL_281;
    case D3DKMT_ESCAPE_MIRACAST_DISPLAY_REQUEST:
LABEL_121:
      if ( v125.Type == D3DKMT_ESCAPE_IDD_REQUEST )
        v37 = DxgkHandleIndirectEscape(v125.PrivateDriverDataSize, p_Srca);
      else
        v37 = DxgkHandleMiracastEscape(v125.PrivateDriverDataSize, p_Srca);
      v38 = v37;
      if ( (int)(v37 + 0x80000000) < 0 || v37 == -2147483643 )
      {
        if ( v122 == 1 )
          RtlCopyToUser(v125.pPrivateDriverData, p_Srca, v125.PrivateDriverDataSize);
        else
          memmove(v125.pPrivateDriverData, p_Srca, v125.PrivateDriverDataSize);
      }
      if ( v126[0] )
        DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v126[0]);
      goto LABEL_127;
    case D3DKMT_ESCAPE_FORCE_BDDFALLBACK_HEADLESS:
      if ( g_OSTestSigningEnabled )
      {
        if ( v125.PrivateDriverDataSize != 1 )
          goto LABEL_188;
        byte_14015EDDC = *(_BYTE *)p_Srca;
        goto LABEL_206;
      }
LABEL_326:
      DxgkEscape_::_2_::ENSURE_DATA_DELETION::_ENSURE_DATA_DELETION(v126);
      goto LABEL_202;
    case D3DKMT_ESCAPE_REQUEST_MACHINE_CRASH:
      if ( v125.PrivateDriverDataSize != 24 )
        goto LABEL_188;
      DxgkEscape_::_2_::ENSURE_DATA_DELETION::_ENSURE_DATA_DELETION(v126);
      DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v118);
      if ( v120 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
        McTemplateK0q_EtwWriteTransfer(v69, EventProfilerExit, v70, v118);
      return 3221225473LL;
  }
LABEL_31:
  v131 = 0;
  pPrivateDriverData = 0;
  if ( v125.Type != D3DKMT_ESCAPE_BDD_FALLBACK )
    goto LABEL_32;
  v81 = 0;
  pPrivateDriverData = 0;
  if ( IsCurrentConsoleSession() || IsCurrentProcessAdmin() )
  {
    if ( (unsigned int)Feature_BasicDisplayDeviceEscape_Fix__private_IsEnabledDeviceUsageNoInline() )
    {
      Global = DXGGLOBAL::GetGlobal();
      v81 = DXGGLOBAL::ReferenceBddFallbackAdapter(Global, &v127);
      pPrivateDriverData = v81;
    }
    else
    {
      v83 = DXGGLOBAL::GetGlobal();
      DXGGLOBAL::ReferenceBddFallbackAdapter(v83, &v127);
    }
  }
  if ( v81 )
  {
    v126[1] = v81;
LABEL_32:
    v9 = 0;
    v136 = 0;
    DXGHANDLETABLELOCKSHARED::DXGHANDLETABLELOCKSHARED((DXGHANDLETABLELOCKSHARED *)v146, Current);
    hAdapter = v125.hAdapter;
    if ( !v125.hAdapter )
    {
LABEL_33:
      if ( v9 )
      {
        v11 = 0;
        v132 = 0;
        v140 = 0;
        if ( v125.hDevice )
        {
          v32 = v129;
          if ( ((v125.hDevice >> 6) & 0xFFFFFF) >= *((_DWORD *)v129 + 74) )
          {
            v34 = 0;
          }
          else
          {
            v33 = *(_DWORD *)(*((_QWORD *)v129 + 35) + 16LL * ((v125.hDevice >> 6) & 0xFFFFFF) + 8);
            v34 = ((v125.hDevice >> 25) & 0x60) == (v33 & 0x60) && (v33 & 0x2000) == 0 && (v33 & 0x1F) != 0;
            v32 = v129;
          }
          if ( v34 )
          {
            v35 = *((_QWORD *)v32 + 35);
            if ( (*(_BYTE *)(v35 + 16LL * ((v125.hDevice >> 6) & 0xFFFFFF) + 8) & 0x1F) == 3 )
            {
              v11 = *(_QWORD *)(v35 + 16LL * ((v125.hDevice >> 6) & 0xFFFFFF));
            }
            else
            {
              WdLogSingleEntry0(2);
              WdLogGlobalForLineNumber = 318;
              DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
              v11 = 0;
            }
          }
          else
          {
            v11 = 0;
          }
          v132 = (DXGDEVICE *)v11;
          if ( !v11 || (v140 = v11, v9 != *(_QWORD *)(*(_QWORD *)(v11 + 16) + 16LL)) && v9 != *(_QWORD *)(v11 + 1896) )
          {
            WdLogSingleEntry2(3, v9);
            WdLogGlobalForLineNumber = 1974;
LABEL_143:
            DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v146);
LABEL_188:
            DxgkEscape_::_2_::ENSURE_DATA_DELETION::_ENSURE_DATA_DELETION(v126);
LABEL_189:
            DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v118);
            if ( v120 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
              McTemplateK0q_EtwWriteTransfer(v59, EventProfilerExit, v60, v118);
            LODWORD(v15) = -1073741811;
            return (unsigned int)v15;
          }
        }
        v12 = 0;
        v137 = 0;
        hContext = v125.hContext;
        if ( v125.hContext )
        {
          v41 = (v125.hContext >> 6) & 0xFFFFFF;
          v42 = v41;
          v43 = v129;
          if ( v41 >= *((_DWORD *)v129 + 74) )
          {
            v45 = 0;
          }
          else
          {
            v44 = *(_DWORD *)(*((_QWORD *)v129 + 35) + 16LL * v41 + 8);
            v45 = ((v125.hContext >> 25) & 0x60) == (v44 & 0x60) && (v44 & 0x2000) == 0 && (v44 & 0x1F) != 0;
            v43 = v129;
          }
          if ( v45 )
          {
            v46 = 2 * v42;
            v47 = *((_QWORD *)v43 + 35);
            if ( (*(_BYTE *)(v47 + 8 * v46 + 8) & 0x1F) == 7 )
            {
              v12 = *(_QWORD *)(v47 + 8 * v46);
            }
            else
            {
              WdLogSingleEntry0(2);
              WdLogGlobalForLineNumber = 318;
              DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
              v12 = 0;
              hContext = v125.hContext;
            }
          }
          else
          {
            v12 = 0;
          }
          v137 = v12;
          if ( !v12 || !v11 || v11 != *(_QWORD *)(v12 + 16) )
          {
            WdLogSingleEntry3(3, v9, v11, hContext);
            WdLogGlobalForLineNumber = 1997;
            goto LABEL_143;
          }
        }
        if ( v11 )
        {
          _InterlockedAdd64((volatile signed __int64 *)(v11 + 64), 1u);
          v9 = *(_QWORD *)(*(_QWORD *)(v11 + 16) + 16LL);
          v136 = v9;
        }
        if ( v12 )
          _InterlockedAdd64((volatile signed __int64 *)(v12 + 32), 1u);
        _InterlockedAdd64((volatile signed __int64 *)(v9 + 24), 1u);
        DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v146);
        if ( *(_DWORD *)(v9 + 2392) >= 0x5023u )
        {
          if ( (*(_BYTE *)&v125.Flags.0 & 0x10) != 0 || (v125.Flags.Value & 0xFFFFFF00) != 0 )
          {
            WdLogSingleEntry1(3);
            WdLogGlobalForLineNumber = 2022;
            goto LABEL_188;
          }
          if ( (*(_BYTE *)&v125.Flags.0 & 0x20) != 0 )
          {
            WdLogSingleEntry1(3);
            WdLogGlobalForLineNumber = 2027;
            goto LABEL_188;
          }
        }
        v130[0] = (DXGADAPTER *)v9;
        v130[1] = (DXGADAPTER *)-1LL;
        *(_QWORD *)v123 = v11;
        v124 = v137;
        LODWORD(v15) = DxgkpGetPairingAdapters((struct DXGADAPTER *)v9, 0, &v131, &v143, 0, 0, 0);
        v16 = v131;
        if ( (int)v15 >= 0 )
          DXGADAPTER::ReleaseReference(v131, v14);
        if ( v125.Type != D3DKMT_ESCAPE_VIDMM )
        {
          if ( v125.Type == D3DKMT_ESCAPE_DRT_TEST )
          {
            v84 = p_Srca[2];
            if ( (unsigned int)v84 <= 0x2E )
            {
              v85 = 0x512744204000LL;
              if ( _bittest64(&v85, v84) )
              {
                if ( (_DWORD)v84 == 33 || (_DWORD)v84 == 32 )
                {
                  v38 = -1073741823;
                }
                else
                {
                  v38 = DxgkDrtTestEscape((struct DXGADAPTER *)v9, (struct _D3DKMT_DRT_ESCAPE_HEAD *)p_Srca, 0);
                  if ( v38 >= 0 )
                  {
                    if ( v122 == 1 )
                      RtlCopyToUser(v125.pPrivateDriverData, p_Srca, v125.PrivateDriverDataSize);
                    else
                      memmove(v125.pPrivateDriverData, p_Srca, v125.PrivateDriverDataSize);
                  }
                }
                goto LABEL_200;
              }
            }
          }
LABEL_45:
          COREADAPTERACCESS::COREADAPTERACCESS((COREADAPTERACCESS *)v165, (struct DXGADAPTER *const)v9, 0);
          COREACCESS::COREACCESS((COREACCESS *)v164, pPrivateDriverData, v17);
          LODWORD(v131) = 0;
          v134 = v9;
          v135 = 0;
          if ( v125.Type == D3DKMT_ESCAPE_BDD_FALLBACK )
          {
            COREACCESS::AcquireShared((COREACCESS *)v164, 0);
            goto LABEL_47;
          }
          if ( (*(_BYTE *)&v125.Flags.0 & 1) != 0 )
          {
            if ( v125.Type == D3DKMT_ESCAPE_DRIVERPRIVATE
              || (LOBYTE(v89) = 0, v125.Type == D3DKMT_ESCAPE_VIDSCH) && *p_Srca == 3 )
            {
              LOBYTE(v89) = 1;
            }
            v89 = (unsigned __int8)v89;
            if ( *(_QWORD *)(v9 + 3240) )
              v89 = 1;
            LODWORD(v131) = v89;
            LODWORD(v15) = COREADAPTERACCESS::AcquireExclusive(v165, (unsigned int)(unsigned __int8)v89 + 2, 2);
            if ( (int)v15 < 0 )
              goto LABEL_60;
            if ( !(_BYTE)v131 )
            {
              v73 = *(_QWORD *)(v9 + 3240);
              if ( v73 )
                ADAPTER_RENDER::FlushScheduler(v73, 2, 0xFFFFFFFFLL);
            }
            LODWORD(v131) = 1;
            goto LABEL_47;
          }
          if ( v125.Type == D3DKMT_ESCAPE_DRT_TEST )
          {
            v90 = p_Srca[2];
            if ( v90 != 23 || (v36 = 1, p_Srca[3] - 2 > 1) )
              v36 = 0;
            v128 = v90 == 55;
          }
          else
          {
            v36 = 0;
            v128 = 0;
          }
          v121 = v36;
          if ( v125.Type == D3DKMT_ESCAPE_DRIVERPRIVATE )
          {
            LODWORD(v54) = DXGADAPTER::GetAdapterType((DXGADAPTER *)v9);
            if ( (*v54 & 0x10) != 0
              || *(_BYTE *)&v125.Flags.0 < 0
              || *(_DWORD *)(v9 + 2392) >= 0x5023u && (*(_BYTE *)&v125.Flags.0 & 8) != 0 )
            {
              DXGADAPTERSTOPRESETLOCKSHARED::Acquire((DXGADAPTERSTOPRESETLOCKSHARED *)v133);
              if ( *(_DWORD *)(v9 + 200) != 1 )
              {
LABEL_117:
                LODWORD(v15) = -1073741130;
                goto LABEL_60;
              }
LABEL_47:
              if ( v125.hDevice && *((_DWORD *)v132 + 152) != 1 )
                goto LABEL_117;
              v121 = 1;
              if ( v125.Type == D3DKMT_ESCAPE_DRIVERPRIVATE && (*(_BYTE *)&v125.Flags.0 & 0x40) != 0 )
              {
                if ( !v16 )
                  goto LABEL_348;
                LODWORD(v15) = DxgkpDriverKnownEscape(v129, v16, p_Srca, v125.PrivateDriverDataSize, &v121);
                if ( (int)v15 < 0 )
                  goto LABEL_59;
              }
              if ( v16 && *((_BYTE *)v16 + 209) )
              {
                v9 = (__int64)v16;
                v136 = (__int64)v16;
                if ( v125.Type == D3DKMT_ESCAPE_DRIVERPRIVATE && v121
                  || v125.Type <= (unsigned int)(D3DKMT_ESCAPE_LOG_CODEPOINT_PACKET|D3DKMT_ESCAPE_DRT_TEST)
                  && (v91 = 0x1001000000ALL, _bittest64(&v91, v125.Type))
                  || (v92 = 0, v125.Type == D3DKMT_ESCAPE_ADAPTER_VERIFIER_OPTION) )
                {
                  v92 = 1;
                }
                if ( v125.Type == D3DKMT_ESCAPE_DRT_TEST && p_Srca[2] == 49 )
                {
                  LODWORD(v15) = DxgkDrtTestEscape(
                                   v16,
                                   (struct _D3DKMT_DRT_ESCAPE_HEAD *)p_Srca,
                                   (struct COREADAPTERACCESS *)v165);
                  if ( (int)v15 < 0 )
                    goto LABEL_59;
                  v92 = 1;
                }
                if ( v92 )
                {
                  v123[0] = v125.Type;
                  if ( v137 )
                    LODWORD(v131) = *(_DWORD *)(v137 + 28);
                  else
                    LODWORD(v131) = 0;
                  if ( v132 )
                    v93 = *((_DWORD *)v132 + 118);
                  else
                    v93 = 0;
                  v94 = *((_DWORD *)v16 + 1216);
                  HostProcess = DXGPROCESS::GetHostProcess(v129);
                  v96 = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendEscape(
                          (DXG_GUEST_VIRTUALGPU_VMBUS *)(v9 + 4776),
                          HostProcess,
                          v94,
                          v93,
                          (unsigned int)v131,
                          v123[0],
                          v125.Flags,
                          v125.PrivateDriverDataSize,
                          (unsigned __int8 *)p_Srca);
                  v15 = v96;
                  if ( v96 < 0 )
                  {
                    WdLogSingleEntry1(2);
                    WdLogGlobalForLineNumber = 2411;
                    DxgkLogInternalTriageEvent(
                      0,
                      0x40000,
                      -1,
                      (unsigned int)L"Paravirtualized escape failed: 0x%I64x",
                      v15,
                      0,
                      0,
                      0,
                      0);
                  }
                  goto LABEL_59;
                }
              }
              if ( v125.Type <= D3DKMT_ESCAPE_MODES_PRUNED_OUT )
              {
                if ( v125.Type == D3DKMT_ESCAPE_MODES_PRUNED_OUT )
                {
                  if ( !*(_QWORD *)(v9 + 3232) )
                  {
                    WdLogSingleEntry2(2, v9);
                    WdLogGlobalForLineNumber = 2954;
                    v62 = L"Try to call D3DKMT_ESCAPE_MODES_PRUNED_OUT on a render only adapter 0x%I64x (Status = 0x%I64x)!";
                    goto LABEL_195;
                  }
                  if ( v125.PrivateDriverDataSize >= 8
                    && v125.PrivateDriverDataSize >= 44 * (unsigned __int64)p_Srca[1] + 8 )
                  {
                    InvalidModesForTestPurposes = ADAPTER_DISPLAY::GetInvalidModesForTestPurposes(
                                                    *(ADAPTER_DISPLAY **)(v9 + 3232),
                                                    (struct _D3DKMT_DISPLAYMODELIST *)p_Srca);
                    goto LABEL_88;
                  }
                  goto LABEL_348;
                }
                if ( v125.Type <= D3DKMT_ESCAPE_DEBUG_SNAPSHOT )
                {
                  if ( v125.Type == D3DKMT_ESCAPE_DEBUG_SNAPSHOT )
                  {
                    if ( v125.PrivateDriverDataSize >= 8 )
                    {
                      InvalidModesForTestPurposes = DxgDbgTakeSnapshot(
                                                      p_Srca + 1,
                                                      v125.PrivateDriverDataSize - 4,
                                                      p_Srca);
                      goto LABEL_88;
                    }
                    goto LABEL_348;
                  }
                  if ( v125.Type == D3DKMT_ESCAPE_DRIVERPRIVATE )
                  {
                    memset(&v142, 0, sizeof(v142));
                    if ( v121 )
                    {
                      if ( *(__int64 (__fastcall **)(void *const, const struct _DXGKARG_ESCAPE *))(v9 + 592) == DXGADAPTER::DefaultDdiEscape )
                      {
                        WdLogSingleEntry2(3, v9);
                        WdLogGlobalForLineNumber = 2488;
LABEL_58:
                        LODWORD(v15) = -1073741637;
                        goto LABEL_59;
                      }
                      if ( !v125.PrivateDriverDataSize || !v125.pPrivateDriverData )
                      {
                        LODWORD(v15) = -1073741811;
                        WdLogSingleEntry3(3, v125.PrivateDriverDataSize, v125.pPrivateDriverData, -1073741811);
                        WdLogGlobalForLineNumber = 2479;
                        goto LABEL_59;
                      }
                      if ( v132 )
                        v142.hDevice = (HANDLE)*((_QWORD *)v132 + 77);
                      if ( v137 )
                        v142.hContext = *(HANDLE *)(v137 + 184);
                      else
                        v142.hContext = 0;
                      v142.Flags.Value = v125.Flags.Value;
                      if ( (*(_DWORD *)(v9 + 444) & 8) == 0
                        && *(_DWORD *)(v9 + 420) == 4098
                        && !(unsigned int)IsAMDDriverEscapeAllowed(p_Srca, v125.PrivateDriverDataSize) )
                      {
                        goto LABEL_170;
                      }
                      if ( *(_BYTE *)&v125.Flags.0 < 0 )
                      {
                        LODWORD(v15) = -1073741637;
                        WdLogSingleEntry1(2);
                        WdLogGlobalForLineNumber = 2449;
                        DxgkLogInternalTriageEvent(
                          0,
                          0x40000,
                          -1,
                          (unsigned int)L"Driver Common Escape is block for (0x%I64x)",
                          -1073741637,
                          0,
                          0,
                          0,
                          0);
                        goto LABEL_59;
                      }
                      v24 = v129;
                      IsVmProcessOrVmValidation = DXGPROCESS::IsVmProcessOrVmValidation(v129, (struct DXGADAPTER *)v9);
                      v142.Flags.Value = v142.Flags.Value & 0xFFFFFFDF | (32 * (IsVmProcessOrVmValidation & 1));
                      v142.PrivateDriverDataSize = v125.PrivateDriverDataSize;
                      v142.pPrivateDriverData = p_Srca;
                      v26 = *(_QWORD *)(v9 + 3240);
                      if ( v26 )
                      {
                        KeEnterCriticalRegion();
                        ExAcquirePushLockSharedEx(v26 + 72, 0);
                        _InterlockedAdd((volatile signed __int32 *)(v26 + 88), 1u);
                        RenderAdapterInfo = DXGPROCESS::GetRenderAdapterInfo(v24, *(_DWORD *)(v9 + 240));
                        if ( RenderAdapterInfo )
                          v142.hKmdProcessHandle = (HANDLE)*((_QWORD *)RenderAdapterInfo + 6);
                        _InterlockedDecrement((volatile signed __int32 *)(v26 + 88));
                        ExReleasePushLockSharedEx(v26 + 72, 0);
                        KeLeaveCriticalRegion();
                      }
                      v28 = &v142;
                      v29 = (DXGADAPTER *)v9;
                      goto LABEL_87;
                    }
LABEL_394:
                    LODWORD(v15) = 0;
                    goto LABEL_119;
                  }
                  if ( v125.Type != D3DKMT_ESCAPE_VIDMM )
                  {
                    if ( v125.Type == D3DKMT_ESCAPE_TDRDBGCTRL )
                    {
                      if ( !v125.pPrivateDriverData )
                        goto LABEL_415;
                      if ( v125.PrivateDriverDataSize < 4 )
                        goto LABEL_233;
                      if ( *p_Srca )
                      {
                        switch ( *p_Srca )
                        {
                          case 1u:
                            v103 = 2;
                            break;
                          case 2u:
                            v103 = 1;
                            break;
                          case 3u:
                            v103 = 3;
                            break;
                          case 4u:
                          case 5u:
                            if ( !v16 )
                            {
                              *(_QWORD *)(WdLogNewEntry5_WdTrace() + 24) = 0;
                              WdLogGlobalForLineNumber = 2697;
                              goto LABEL_58;
                            }
                            if ( *((_BYTE *)v16 + 209) )
                            {
LABEL_170:
                              LODWORD(v15) = -1073741637;
                              goto LABEL_60;
                            }
                            LODWORD(v15) = TdrDbgCtrl(4);
                            if ( (int)v15 < 0 )
                              goto LABEL_59;
                            v102 = *(struct _VIDSCH_GLOBAL **)(*((_QWORD *)v16 + 405) + 744LL);
                            memset(v167, 0, sizeof(v167));
                            LODWORD(v167[0]) = 2;
                            DWORD1(v167[0]) = *p_Srca;
                            v100 = *((_QWORD *)v16 + 405);
                            v101 = (struct _D3DKMT_VIDSCH_ESCAPE *)v167;
                            goto LABEL_396;
                          case 6u:
                            v103 = 5;
                            break;
                          case 7u:
                            v103 = 6;
                            break;
                          case 8u:
                            if ( v125.PrivateDriverDataSize >= 8 )
                            {
                              if ( !v16 )
                              {
                                *(_QWORD *)(WdLogNewEntry5_WdTrace() + 24) = v9;
                                WdLogGlobalForLineNumber = 2735;
                                goto LABEL_58;
                              }
                              if ( *((_BYTE *)v16 + 209) )
                                goto LABEL_170;
                              LODWORD(v15) = TdrDbgCtrl(4);
                              if ( (int)v15 < 0 )
                                goto LABEL_59;
                              v102 = *(struct _VIDSCH_GLOBAL **)(*((_QWORD *)v16 + 405) + 744LL);
                              memset(v166, 0, sizeof(v166));
                              LODWORD(v166[0]) = 2;
                              *(_QWORD *)((char *)v166 + 4) = *(_QWORD *)p_Srca;
                              v100 = *((_QWORD *)v16 + 405);
                              v101 = (struct _D3DKMT_VIDSCH_ESCAPE *)v166;
                              goto LABEL_396;
                            }
LABEL_348:
                            LODWORD(v15) = -1073741811;
LABEL_60:
                            DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v133);
                            COREACCESS::~COREACCESS((COREACCESS *)v164);
                            COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v165);
                            ENSURE_CONTEXT_DEREFERENCE::~ENSURE_CONTEXT_DEREFERENCE((ENSURE_CONTEXT_DEREFERENCE *)&v124);
                            v20 = (ADAPTER_RENDER **)v132;
                            if ( v132
                              && _InterlockedExchangeAdd64((volatile signed __int64 *)v132 + 8, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
                            {
                              ADAPTER_RENDER::DestroyDeviceNoLocks(v20[2], (struct DXGDEVICE *)v20);
                            }
                            if ( v130[0] )
                              DXGADAPTER::ReleaseReference(v130[0], v19);
                            if ( v126[0] )
                              DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v126[0]);
                            if ( v126[1] )
                              DXGADAPTER::ReleaseReference(v126[1], v19);
                            goto LABEL_69;
                          default:
                            goto LABEL_233;
                        }
                      }
                      else
                      {
LABEL_415:
                        v103 = 0;
                      }
                      InvalidModesForTestPurposes = TdrDbgCtrl(v103);
                      goto LABEL_88;
                    }
                    if ( v125.Type != D3DKMT_ESCAPE_VIDSCH )
                    {
                      if ( v125.Type == D3DKMT_ESCAPE_DEVICE )
                      {
                        if ( v125.PrivateDriverDataSize >= 0xC && v132 )
                        {
                          InvalidModesForTestPurposes = DXGDEVICE::Escape(v132, (struct _D3DKMT_DEVICE_ESCAPE *)p_Srca);
                          goto LABEL_88;
                        }
                      }
                      else
                      {
                        if ( v125.Type != D3DKMT_ESCAPE_DMM )
                        {
LABEL_375:
                          LODWORD(v15) = -1073741811;
                          WdLogSingleEntry1(3);
                          WdLogGlobalForLineNumber = 3377;
                          goto LABEL_59;
                        }
                        if ( !*(_QWORD *)(v9 + 3232) )
                        {
                          WdLogSingleEntry2(2, v9);
                          WdLogGlobalForLineNumber = 2504;
                          v62 = L"Try to call D3DKMT_ESCAPE_DMM on a render only adapter 0x%I64x (Status = 0x%I64x)!";
LABEL_195:
                          DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v62, v9, -1073741637, 0, 0, 0);
                          goto LABEL_196;
                        }
                        if ( v125.PrivateDriverDataSize >= 0x80 )
                        {
                          v97 = *((_QWORD *)p_Srca + 1);
                          if ( v97 <= 0x19000 && (v125.PrivateDriverDataSize == v97 + 127 || !v97) )
                          {
                            InvalidModesForTestPurposes = DmmEscape(
                                                            (struct DXGADAPTER *const)v9,
                                                            (struct _D3DKMT_DMM_ESCAPE_INTERNAL *const)p_Srca);
                            goto LABEL_88;
                          }
                        }
                      }
LABEL_233:
                      LODWORD(v15) = -1073741811;
                      goto LABEL_59;
                    }
                    if ( !v16 )
                    {
                      WdLogSingleEntry2(2, v9);
                      WdLogGlobalForLineNumber = 2594;
                      v62 = L"Try to call D3DKMT_ESCAPE_VIDSCH on a display only adapter 0x%I64x (Status = 0x%I64x)!";
                      goto LABEL_195;
                    }
                    if ( !*((_BYTE *)v16 + 209) )
                    {
                      if ( *p_Srca != 2 )
                      {
                        if ( *p_Srca == 3 )
                        {
                          if ( (_DWORD)v131 )
                          {
                            Interval.QuadPart = 0;
                            v98 = 5000000;
                            if ( p_Srca[1] < 0x4C4B40 )
                              v98 = p_Srca[1];
                            Interval.QuadPart = -(__int64)v98;
                            KeDelayExecutionThread(0, 0, &Interval);
                            goto LABEL_394;
                          }
                          goto LABEL_233;
                        }
                        v100 = *((_QWORD *)v16 + 405);
                        v101 = (struct _D3DKMT_VIDSCH_ESCAPE *)p_Srca;
                        v102 = *(struct _VIDSCH_GLOBAL **)(v100 + 744);
LABEL_396:
                        InvalidModesForTestPurposes = VIDSCH_EXPORT::VidSchEscape(
                                                        *(VIDSCH_EXPORT **)(v100 + 736),
                                                        v102,
                                                        v101);
                        goto LABEL_88;
                      }
                      goto LABEL_348;
                    }
                    goto LABEL_196;
                  }
                  if ( !v16 )
                  {
                    WdLogSingleEntry2(2, v9);
                    WdLogGlobalForLineNumber = 2532;
                    v62 = L"Try to call D3DKMT_ESCAPE_VIDMM on a display only adapter 0x%I64x (Status = 0x%I64x)!";
                    goto LABEL_195;
                  }
                  if ( v132 )
                    v104 = *((_QWORD *)v132 + 99);
                  else
                    v104 = 0;
                  if ( *p_Srca == 16 )
                  {
                    v105 = p_Srca + 6;
                    LODWORD(v15) = DxgkpEscapeVidMmDelayExecution(
                                     v132,
                                     p_Srca[3],
                                     p_Srca[2],
                                     p_Srca[4],
                                     (unsigned __int64 *)p_Srca + 3);
                    if ( (int)v15 >= 0 )
                    {
                      pPrivateDriverData = (struct DXGADAPTER *)v125.pPrivateDriverData;
                      if ( v122 == 1 )
                        RtlWriteULong64ToUser((char *)v125.pPrivateDriverData + 24, *v105);
                      else
                        *((_QWORD *)v125.pPrivateDriverData + 3) = *v105;
                    }
LABEL_59:
                    if ( (int)v15 < 0 )
                      goto LABEL_60;
LABEL_119:
                    if ( v122 == 1 )
                      RtlCopyToUser(v125.pPrivateDriverData, p_Srca, v125.PrivateDriverDataSize);
                    else
                      memmove(v125.pPrivateDriverData, p_Srca, v125.PrivateDriverDataSize);
                    goto LABEL_60;
                  }
                  LOBYTE(v18) = (_BYTE)v131;
                  InvalidModesForTestPurposes = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned int *, __int64))(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v16 + 405) + 760LL) + 8LL) + 32LL))(
                                                  *(_QWORD *)(*((_QWORD *)v16 + 405) + 768LL),
                                                  v104,
                                                  p_Srca,
                                                  v18);
LABEL_88:
                  LODWORD(v15) = InvalidModesForTestPurposes;
                  goto LABEL_59;
                }
                switch ( v125.Type )
                {
                  case D3DKMT_ESCAPE_DRT_TEST:
                    InvalidModesForTestPurposes = DxgkDrtTestEscape(
                                                    (struct DXGADAPTER *)v9,
                                                    (struct _D3DKMT_DRT_ESCAPE_HEAD *)p_Srca,
                                                    (struct COREADAPTERACCESS *)v165);
                    goto LABEL_88;
                  case D3DKMT_ESCAPE_OUTPUTDUPL_SNAPSHOT:
                    if ( !*(_QWORD *)(v9 + 3232) )
                    {
                      WdLogSingleEntry2(2, v9);
                      WdLogGlobalForLineNumber = 2812;
                      v62 = L"Try to call D3DKMT_ESCAPE_OUTPUTDUPL_SNAPSHOT on a render only adapter 0x%I64x (Status = 0x%I64x)!";
                      goto LABEL_195;
                    }
                    if ( v125.PrivateDriverDataSize >= 0x18 && v125.PrivateDriverDataSize == *p_Srca )
                    {
                      InvalidModesForTestPurposes = OutputDuplGetDebugInfo(
                                                      (struct DXGADAPTER *)v9,
                                                      (struct _D3DKMT_OUTPUTDUPL_SNAPSHOT *)p_Srca);
                      goto LABEL_88;
                    }
                    goto LABEL_348;
                  case D3DKMT_ESCAPE_OUTPUTDUPL_DIAGNOSTICS:
                    if ( !*(_QWORD *)(v9 + 3232) )
                    {
                      WdLogSingleEntry2(2, v9);
                      WdLogGlobalForLineNumber = 2845;
                      v62 = L"Try to call D3DKMT_ESCAPE_OUTPUTDUPL_DIAGNOSTICS on a render only adapter 0x%I64x (Status = 0x%I64x)!";
                      goto LABEL_195;
                    }
                    if ( v125.PrivateDriverDataSize >= 8 && v125.PrivateDriverDataSize == p_Srca[1] + 8LL )
                    {
                      InvalidModesForTestPurposes = OutputDuplGetDiagnosticBuffer((struct DXGADAPTER *)v9);
                      goto LABEL_88;
                    }
                    goto LABEL_348;
                  case D3DKMT_ESCAPE_BDD_PNP:
                    if ( (*(_DWORD *)(v9 + 444) & 0x20) == 0 || DXGADAPTER::IsBddFallbackDriver((DXGADAPTER *)v9) )
                    {
                      LODWORD(v15) = -1071775742;
                      goto LABEL_59;
                    }
                    v157 = 0;
                    v160 = 0;
                    v162 = 0;
                    v155 = 0;
                    v161 = 0;
                    Value = (struct _D3DDDI_ESCAPEFLAGS::$DB860278E5E511C34FE0F76D94154466::$9A2C51F7B5B2EC690ABA117774D32C3A)v125.Flags.Value;
                    v159 = v125.PrivateDriverDataSize;
                    v158 = p_Srca;
                    v28 = (_DXGKARG_ESCAPE *)&v155;
                    break;
                  case D3DKMT_ESCAPE_BDD_FALLBACK:
                    v106 = pPrivateDriverData;
                    if ( !DXGADAPTER::IsBddFallbackDriver(pPrivateDriverData) )
                    {
                      WdLogSingleEntry0(1);
                      WdLogGlobalForLineNumber = 2874;
                      DxgkLogInternalTriageEvent(
                        0,
                        262146,
                        -1,
                        (unsigned int)L"pBddAdapter->IsBddFallbackDriver()",
                        2874,
                        0,
                        0,
                        0,
                        0);
                    }
                    v149 = 0;
                    v152 = 0;
                    v154 = 0;
                    v147 = 0;
                    v153 = 0;
                    v148 = (struct _D3DDDI_ESCAPEFLAGS::$DB860278E5E511C34FE0F76D94154466::$9A2C51F7B5B2EC690ABA117774D32C3A)v125.Flags.Value;
                    v151 = v125.PrivateDriverDataSize;
                    v150 = p_Srca;
                    v28 = (_DXGKARG_ESCAPE *)&v147;
                    v29 = v106;
                    break;
                  case D3DKMT_ESCAPE_ACTIVATE_SPECIFIC_DIAG:
                    if ( v125.PrivateDriverDataSize != 8 )
                      goto LABEL_348;
                    if ( *p_Srca )
                    {
                      if ( *p_Srca == 15 )
                      {
                        v61 = *(ADAPTER_DISPLAY **)(v9 + 3232);
                        if ( v61 )
                        {
                          InvalidModesForTestPurposes = ADAPTER_DISPLAY::ActivateStoringInvalidModesForTestPurposes(
                                                          v61,
                                                          p_Srca[1]);
                          goto LABEL_88;
                        }
                        WdLogSingleEntry2(2, v9);
                        WdLogGlobalForLineNumber = 2925;
                        v62 = L"Try to activate D3DKMT_ESCAPE_MODES_PRUNED_OUT on a render only adapter 0x%I64x (Status = 0x%I64x)!";
                        goto LABEL_195;
                      }
                      WdLogSingleEntry1(1);
                      WdLogGlobalForLineNumber = 2941;
                      DxgkLogInternalTriageEvent(
                        0,
                        262146,
                        -1,
                        (unsigned int)L"%I64d is not an escape type that needs (de)activation",
                        (int)*p_Srca,
                        0,
                        0,
                        0,
                        0);
                      goto LABEL_233;
                    }
                    *((_BYTE *)DXGGLOBAL::GetGlobal() + 1360) = p_Srca[1] != 0;
LABEL_235:
                    LODWORD(v15) = 0;
                    goto LABEL_59;
                  default:
                    goto LABEL_375;
                }
LABEL_87:
                InvalidModesForTestPurposes = DXGADAPTER::DdiEscape(v29, v28);
                goto LABEL_88;
              }
              if ( v125.Type <= D3DKMT_ESCAPE_ADAPTER_VERIFIER_OPTION )
              {
                if ( v125.Type != D3DKMT_ESCAPE_ADAPTER_VERIFIER_OPTION )
                {
                  switch ( v125.Type )
                  {
                    case D3DKMT_ESCAPE_WHQL_INFO:
                      if ( v125.PrivateDriverDataSize >= 4 )
                      {
                        *p_Srca = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v9 + 216) + 64LL) + 2744LL);
                        goto LABEL_394;
                      }
                      goto LABEL_348;
                    case D3DKMT_ESCAPE_BRIGHTNESS:
                      if ( (*(_BYTE *)&v125.Flags.0 & 1) == 0 || v125.PrivateDriverDataSize < 0x60C )
                        goto LABEL_348;
                      if ( DXGPROCESS::IsRemoteConnection(v129) )
                      {
                        LODWORD(v15) = -1073741790;
                        WdLogSingleEntry2(3, v9);
                        WdLogGlobalForLineNumber = 3012;
                        goto LABEL_59;
                      }
                      InvalidModesForTestPurposes = DpiBrightnessEscape(
                                                      *(struct _DEVICE_OBJECT **)(v9 + 216),
                                                      (struct _D3DKMT_BRIGHTNESS_INFO *)p_Srca);
                      goto LABEL_88;
                    case D3DKMT_ESCAPE_EDID_CACHE:
                      if ( v125.PrivateDriverDataSize < 4 || v125.PrivateDriverDataSize != *p_Srca + 4LL )
                        goto LABEL_233;
                      if ( !IsCurrentConsoleSession() && !IsCurrentProcessAdmin() )
                      {
                        memset(p_Srca, 0, v125.PrivateDriverDataSize);
                        goto LABEL_59;
                      }
                      InvalidModesForTestPurposes = (*(__int64 (__fastcall **)(DxgMonitor::EDIDCACHE *, unsigned int *))(*(_QWORD *)DxgMonitor::EDIDCACHE::s_pEdidCache + 16LL))(
                                                      DxgMonitor::EDIDCACHE::s_pEdidCache,
                                                      p_Srca);
                      goto LABEL_88;
                    case D3DKMT_ESCAPE_HISTORY_BUFFER_STATUS:
                      if ( v125.PrivateDriverDataSize >= 8 )
                      {
                        if ( v16 )
                        {
                          v108 = v132;
                          if ( v132 )
                          {
                            v109 = 0;
                            if ( (qword_14015C500 & 0x461C8ED7) != 0
                              && (qword_14015C508 & 0xFFFFFFFFB9E37128uLL) == 0
                              && (qword_14015C500 & 0x4000) != 0 )
                            {
                              while ( 1 )
                              {
                                NumDifferentPhysicalAdapters = DXGADAPTER::GetNumDifferentPhysicalAdapters(v16);
                                if ( v111 >= NumDifferentPhysicalAdapters )
                                  break;
                                if ( *(_QWORD *)(352LL * v111
                                               + *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v16 + 405) + 16LL) + 3104LL)
                                               + 40) )
                                {
                                  v109 = 1;
                                  break;
                                }
                              }
                            }
                            *((_BYTE *)v108 + 1912) = v109;
                            *(_BYTE *)p_Srca = v109;
                            p_Srca[1] = 0;
                            goto LABEL_394;
                          }
                        }
                      }
                      break;
                    case D3DKMT_ESCAPE_MIRACAST_ADAPTER_DIAG_INFO:
                      if ( v125.PrivateDriverDataSize == 32 )
                      {
                        if ( !DXGADAPTER::IsDiagnosticAllowed((DXGADAPTER *)v9) )
                        {
                          PsGetCurrentProcessSessionId();
                          WdLogSingleEntry2(3, v9);
                          WdLogGlobalForLineNumber = 3071;
                          LODWORD(v15) = -1073741790;
                          goto LABEL_59;
                        }
                        DxgkGetAdapterMiracastInfo(*(_QWORD *)(v9 + 216), p_Srca);
                        goto LABEL_394;
                      }
                      goto LABEL_348;
                    case D3DKMT_ESCAPE_PROCESS_VERIFIER_OPTION:
                      if ( v125.PrivateDriverDataSize >= 0x20 )
                      {
                        v107 = p_Srca[3];
                        if ( v107 <= 1 && !*(_QWORD *)p_Srca )
                        {
                          if ( !v107 )
                            *((_OWORD *)p_Srca + 1) = 0;
                          if ( p_Srca[2] == 1000 || p_Srca[2] == 1001 )
                          {
                            if ( v16 )
                            {
                              InvalidModesForTestPurposes = VIDMM_EXPORT::VidMmProcessVerifierOption(
                                                              *(VIDMM_EXPORT **)(*((_QWORD *)v16 + 405) + 760LL),
                                                              *(struct VIDMM_GLOBAL **)(*((_QWORD *)v16 + 405) + 768LL),
                                                              v129,
                                                              (enum _D3DKMT_VERIFIER_OPTION_MODE)p_Srca[3],
                                                              (enum _D3DKMT_PROCESS_VERIFIER_OPTION_TYPE)p_Srca[2],
                                                              (union _D3DKMT_PROCESS_VERIFIER_OPTION_DATA *)p_Srca + 1);
                              goto LABEL_88;
                            }
                            WdLogSingleEntry0(2);
                            WdLogGlobalForLineNumber = 3164;
                            DxgkLogInternalTriageEvent(
                              0,
                              0x40000,
                              -1,
                              (unsigned int)L"D3DKMT_ESCAPE_PROCESS_VERIFIER_OPTION for VidMm option must supply a render adapter",
                              3164,
                              0,
                              0,
                              0,
                              0);
                            goto LABEL_196;
                          }
                        }
                      }
                      break;
                    default:
                      goto LABEL_375;
                  }
                  goto LABEL_186;
                }
                if ( v125.PrivateDriverDataSize < 0x30 || (v112 = p_Srca[1], v112 > 1) )
                {
LABEL_186:
                  DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v133);
                  COREACCESS::~COREACCESS((COREACCESS *)v164);
                  COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v165);
LABEL_187:
                  ENSURE_CONTEXT_DEREFERENCE::~ENSURE_CONTEXT_DEREFERENCE((ENSURE_CONTEXT_DEREFERENCE *)&v124);
                  ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v123);
                  DXGADAPTERBYHANDLE::~DXGADAPTERBYHANDLE((DXGADAPTERBYHANDLE *)v130);
                  goto LABEL_188;
                }
                if ( !v112 )
                {
                  *(_OWORD *)(p_Srca + 2) = 0;
                  *(_OWORD *)(p_Srca + 6) = 0;
                  *((_QWORD *)p_Srca + 5) = 0;
                }
                if ( *p_Srca == 1000 || *p_Srca - 1001 < 2 )
                {
                  if ( v16 )
                  {
                    if ( !*((_BYTE *)v16 + 209) )
                    {
                      InvalidModesForTestPurposes = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v16 + 405) + 760LL) + 8LL)
                                                                                              + 1072LL))(
                                                      *(_QWORD *)(*((_QWORD *)v16 + 405) + 768LL),
                                                      p_Srca[1]);
                      goto LABEL_88;
                    }
                  }
                  else
                  {
                    WdLogSingleEntry0(2);
                    WdLogGlobalForLineNumber = 3215;
                    DxgkLogInternalTriageEvent(
                      0,
                      0x40000,
                      -1,
                      (unsigned int)L"D3DKMT_ESCAPE_ADAPTER_VERIFIER_OPTION for VidMm option must supply a render adapter",
                      3215,
                      0,
                      0,
                      0,
                      0);
                  }
                  goto LABEL_196;
                }
                WdLogSingleEntry1(2);
                WdLogGlobalForLineNumber = 3233;
                v113 = (int)*p_Srca;
                v114 = L"Unknown verifier Type for D3DKMT_ESCAPE_ADAPTER_VERIFIER_OPTION, Type=%d";
LABEL_520:
                DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v114, v113, 0, 0, 0, 0);
                goto LABEL_186;
              }
              switch ( v125.Type )
              {
                case D3DKMT_ESCAPE_DOD_SET_DIRTYRECT_MODE:
                  if ( v125.PrivateDriverDataSize == 4 )
                  {
                    if ( !*(_QWORD *)(v9 + 3240) )
                    {
                      v74 = *(_QWORD *)(v9 + 3232);
                      if ( !*(_QWORD *)(v74 + 464) )
                        goto LABEL_233;
                      *(_DWORD *)(v74 + 472) = *p_Srca;
                      goto LABEL_235;
                    }
                    WdLogSingleEntry1(3);
                    WdLogGlobalForLineNumber = 3251;
                    goto LABEL_186;
                  }
                  WdLogSingleEntry1(2);
                  WdLogGlobalForLineNumber = 3244;
                  v113 = v125.PrivateDriverDataSize;
                  v114 = L"Supplied Buffer size for D3DKMT_ESCAPE_DOD_SET_DIRTYRECT_MODE (0x%I64x) was not the correct size";
                  goto LABEL_520;
                case D3DKMT_ESCAPE_GET_DISPLAY_CONFIGURATIONS:
                  if ( DXGADAPTER::IsFullWDDMAdapter((DXGADAPTER *)v9) )
                  {
                    InvalidModesForTestPurposes = ADAPTER_DISPLAY::ReportDisplayState(
                                                    *(ADAPTER_DISPLAY **)(v9 + 3232),
                                                    (struct _D3DKMT_DXGK_DIAGNOSTICS *)p_Srca,
                                                    v125.PrivateDriverDataSize);
                    goto LABEL_88;
                  }
                  WdLogSingleEntry1(3);
                  WdLogGlobalForLineNumber = 3265;
                  goto LABEL_186;
                case D3DKMT_ESCAPE_QUERY_IOMMU_STATUS:
                  if ( !v125.PrivateDriverDataSize )
                  {
                    WdLogSingleEntry1(2);
                    WdLogGlobalForLineNumber = 3281;
                    v113 = v125.PrivateDriverDataSize;
                    v114 = L"Supplied Buffer size for D3DKMT_ESCAPE_QUERY_IOMMU_STATUS (0x%I64x) was to small";
                    goto LABEL_520;
                  }
                  if ( !v16 )
                  {
                    WdLogSingleEntry0(2);
                    WdLogGlobalForLineNumber = 3287;
                    DxgkLogInternalTriageEvent(
                      0,
                      0x40000,
                      -1,
                      (unsigned int)L"D3DKMT_ESCAPE_QUERY_IOMMU_STATUS must supply a render adapter",
                      3287,
                      0,
                      0,
                      0,
                      0);
                    break;
                  }
                  if ( !*((_BYTE *)v16 + 209) )
                  {
                    LODWORD(v131) = 0;
                    SysMmQueryIommuState(*((const struct SYSMM_ADAPTER **)v16 + 28), (union SYSMM_IOMMU_STATE *)&v131);
                    LOBYTE(v99) = (_BYTE)v131;
                    goto LABEL_393;
                  }
                  break;
                case D3DKMT_ESCAPE_QUERY_IOMMU_STATUS|D3DKMT_ESCAPE_TDRDBGCTRL:
                  if ( !v125.PrivateDriverDataSize )
                  {
                    WdLogSingleEntry1(2);
                    WdLogGlobalForLineNumber = 3312;
                    v113 = v125.PrivateDriverDataSize;
                    v114 = L"Supplied Buffer size for D3DKMT_ESCAPE_QUERY_DMA_REMAPPING_STATUS (0x%I64x) was to small";
                    goto LABEL_520;
                  }
                  if ( !v16 )
                  {
                    WdLogSingleEntry0(2);
                    WdLogGlobalForLineNumber = 3318;
                    DxgkLogInternalTriageEvent(
                      0,
                      0x40000,
                      -1,
                      (unsigned int)L"D3DKMT_ESCAPE_QUERY_DMA_REMAPPING_STATUS must supply a render adapter",
                      3318,
                      0,
                      0,
                      0,
                      0);
                    break;
                  }
                  if ( !*((_BYTE *)v16 + 209) )
                  {
                    LODWORD(v131) = 0;
                    SysMmQueryIommuState(*((const struct SYSMM_ADAPTER **)v16 + 28), (union SYSMM_IOMMU_STATE *)&v131);
                    v99 = (unsigned int)v131 >> 1;
LABEL_393:
                    *(_BYTE *)p_Srca = v99 & 1;
                    goto LABEL_394;
                  }
                  break;
                case D3DKMT_ESCAPE_LOG_CODEPOINT_PACKET|D3DKMT_ESCAPE_DRT_TEST:
                  if ( v125.PrivateDriverDataSize >= 0xC )
                  {
                    if ( !v16 )
                    {
                      WdLogSingleEntry0(2);
                      WdLogGlobalForLineNumber = 3348;
                      DxgkLogInternalTriageEvent(
                        0,
                        0x40000,
                        -1,
                        (unsigned int)L"D3DKMT_QUERY_PHYSICAL_ADAPTER must supply a render adapter",
                        3348,
                        0,
                        0,
                        0,
                        0);
                      break;
                    }
                    v115 = *p_Srca;
                    if ( (unsigned int)v115 < *((_DWORD *)v16 + 74) )
                    {
                      v116 = *((_QWORD *)v16 + 388);
                      p_Srca[1] = *(unsigned __int16 *)(352 * v115 + v116);
                      p_Srca[2] = *(unsigned __int16 *)(352 * v115 + v116 + 2);
                      if ( v125.PrivateDriverDataSize >= 0x10 )
                        p_Srca[3] = -((*((_BYTE *)v16 + 2564) & 4) == 0);
                      goto LABEL_394;
                    }
                    goto LABEL_186;
                  }
                  WdLogSingleEntry1(2);
                  WdLogGlobalForLineNumber = 3343;
                  v113 = v125.PrivateDriverDataSize;
                  v114 = L"Supplied Buffer size for D3DKMT_QUERY_PHYSICAL_ADAPTER (0x%I64x) was to small";
                  goto LABEL_520;
                default:
                  goto LABEL_375;
              }
LABEL_196:
              DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v133);
              COREACCESS::~COREACCESS((COREACCESS *)v164);
              COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v165);
              ENSURE_CONTEXT_DEREFERENCE::~ENSURE_CONTEXT_DEREFERENCE((ENSURE_CONTEXT_DEREFERENCE *)&v124);
              ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v123);
              DXGADAPTERBYHANDLE::~DXGADAPTERBYHANDLE((DXGADAPTERBYHANDLE *)v130);
              DxgkEscape_::_2_::ENSURE_DATA_DELETION::_ENSURE_DATA_DELETION(v126);
              DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v118);
              if ( v120 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
                McTemplateK0q_EtwWriteTransfer(v63, EventProfilerExit, v64, v118);
              return 3221225659LL;
            }
            v36 = v121;
          }
          if ( !v36 && !v128 )
          {
            LODWORD(v15) = COREADAPTERACCESS::AcquireShared((COREADAPTERACCESS *)v165, 0);
            if ( (int)v15 < 0 )
              goto LABEL_60;
          }
          goto LABEL_47;
        }
        if ( !v16 )
        {
          WdLogSingleEntry0(3);
          WdLogGlobalForLineNumber = 2193;
          goto LABEL_187;
        }
        if ( *p_Srca == 9 )
        {
          if ( !p_Srca[4] && !(unsigned __int8)DxgkpIsDrtEnabled((unsigned int)(v125.Type - 1)) )
          {
            WdLogSingleEntry0(3);
            WdLogGlobalForLineNumber = 2173;
            ENSURE_CONTEXT_DEREFERENCE::~ENSURE_CONTEXT_DEREFERENCE((ENSURE_CONTEXT_DEREFERENCE *)&v124);
            ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v123);
            DXGADAPTERBYHANDLE::~DXGADAPTERBYHANDLE((DXGADAPTERBYHANDLE *)v130);
            goto LABEL_326;
          }
          v86 = (void *)*((_QWORD *)p_Srca + 1);
          *((_QWORD *)p_Srca + 1) = 0;
          v87 = DxgEscapeSuspendResumeProcess(&v125, p_Srca, v16, v86, 1, p_Srca[4] != 0);
        }
        else
        {
          if ( *p_Srca != 10 )
            goto LABEL_45;
          v88 = (void *)*((_QWORD *)p_Srca + 1);
          *((_QWORD *)p_Srca + 1) = 0;
          v87 = DxgEscapeSuspendResumeProcess(&v125, p_Srca, v16, v88, 0, 0);
        }
        v38 = v87;
LABEL_200:
        ENSURE_CONTEXT_DEREFERENCE::~ENSURE_CONTEXT_DEREFERENCE((ENSURE_CONTEXT_DEREFERENCE *)&v124);
        ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v123);
        DXGADAPTERBYHANDLE::~DXGADAPTERBYHANDLE((DXGADAPTERBYHANDLE *)v130);
LABEL_201:
        DxgkEscape_::_2_::ENSURE_DATA_DELETION::_ENSURE_DATA_DELETION(v126);
LABEL_127:
        DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v118);
        if ( v120 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
          McTemplateK0q_EtwWriteTransfer(v39, EventProfilerExit, v40, v118);
        return (unsigned int)v38;
      }
      LODWORD(v15) = -1073741811;
      WdLogSingleEntry2(3, hAdapter);
      WdLogGlobalForLineNumber = 1957;
      DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v146);
      goto LABEL_250;
    }
    v48 = (v125.hAdapter >> 6) & 0xFFFFFF;
    v49 = v125.hAdapter >> 30;
    v50 = v129;
    if ( (*((_DWORD *)v129 + 102) & 0x100) != 0 )
    {
      v140 = *((_QWORD *)v129 + 75);
      v136 = v140 + 248;
      DXGPUSHLOCK::AcquireShared((DXGPUSHLOCK *)(v140 + 248));
      if ( v48 < *(_DWORD *)(v140 + 296)
        && (v55 = *(_DWORD *)(*(_QWORD *)(v140 + 280) + 16LL * v48 + 8), v49 == ((v55 >> 5) & 3))
        && (v55 & 0x2000) == 0
        && (v55 & 0x1F) != 0 )
      {
        v57 = *(_QWORD *)(v140 + 280);
        if ( (*(_BYTE *)(v57 + 16LL * v48 + 8) & 0x1F) == 1 )
        {
          v9 = *(_QWORD *)(v57 + 16LL * v48);
        }
        else
        {
          WdLogSingleEntry0(2);
          WdLogGlobalForLineNumber = 318;
          DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
          v9 = 0;
        }
      }
      else
      {
        v9 = 0;
      }
      v58 = v136;
      _InterlockedDecrement((volatile signed __int32 *)(v136 + 16));
      ExReleasePushLockSharedEx(v58, 0);
      KeLeaveCriticalRegion();
    }
    else
    {
      if ( v48 >= *((_DWORD *)v129 + 74) )
      {
        v52 = 0;
      }
      else
      {
        v51 = *(_DWORD *)(*((_QWORD *)v129 + 35) + 16LL * ((v125.hAdapter >> 6) & 0xFFFFFF) + 8);
        v52 = v49 == ((v51 >> 5) & 3) && (v51 & 0x2000) == 0 && (v51 & 0x1F) != 0;
        v50 = v129;
      }
      if ( !v52 )
      {
        v9 = 0;
        goto LABEL_156;
      }
      v53 = *((_QWORD *)v50 + 35);
      if ( (*(_BYTE *)(v53 + 16LL * ((v125.hAdapter >> 6) & 0xFFFFFF) + 8) & 0x1F) == 1 )
      {
        v9 = *(_QWORD *)(v53 + 16LL * ((v125.hAdapter >> 6) & 0xFFFFFF));
        goto LABEL_156;
      }
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 318;
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
      v9 = 0;
    }
    hAdapter = v125.hAdapter;
LABEL_156:
    v136 = v9;
    goto LABEL_33;
  }
  DxgkEscape_::_2_::ENSURE_DATA_DELETION::_ENSURE_DATA_DELETION(v126);
  DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v118);
  if ( v120 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
    McTemplateK0q_EtwWriteTransfer(v71, EventProfilerExit, v72, v118);
  return 3221226021LL;
}

```

## disassembly

```asm
0x14035a080  mov     [rsp+arg_8], rbx
0x14035a085  mov     [rsp+arg_10], rsi
0x14035a08a  push    rdi
0x14035a08b  push    r12
0x14035a08d  push    r13
0x14035a08f  push    r14
0x14035a091  push    r15
0x14035a093  sub     rsp, 550h
0x14035a09a  mov     rax, cs:__security_cookie
0x14035a0a1  xor     rax, rsp
0x14035a0a4  mov     [rsp+578h+var_38], rax
0x14035a0ac  mov     rbx, rcx
0x14035a0af  mov     [rsp+578h+var_528], 0FFFFFFFFh
0x14035a0b7  xor     edi, edi
0x14035a0b9  mov     [rsp+578h+var_520], rdi
0x14035a0be  mov     rax, cs:qword_14015C500
0x14035a0c5  lea     r14d, [rdi+1]
0x14035a0c9  test    al, 2
0x14035a0cb  jnz     short loc_14035A0D4
0x14035a0cd  mov     [rsp+578h+var_518], dil
0x14035a0d2  jmp     short loc_14035A0EE
0x14035a0d4  mov     [rsp+578h+var_518], r14b
0x14035a0d9  mov     [rsp+578h+var_528], 7E0h
0x14035a0e1  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, r14b
0x14035a0e8  jnz     loc_14035B2E8
0x14035a0ee  mov     edx, 7E0h
0x14035a0f3  lea     rcx, [rsp+578h+var_528]
0x14035a0f8  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x14035a0fd  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x14035a102  mov     r12, rax
0x14035a105  mov     [rsp+578h+var_4B8], rax
0x14035a10d  xorps   xmm0, xmm0
0x14035a110  movups  xmmword ptr [rsp+578h+var_4F8.hAdapter], xmm0
0x14035a118  movups  xmmword ptr [rsp+578h+var_4F8.pPrivateDriverData], xmm0
0x14035a120  call    cs:__imp_PsGetCurrentThreadPreviousMode
0x14035a127  nop     dword ptr [rax+rax+00h]
0x14035a12c  mov     [rsp+578h+var_50F], al
0x14035a130  test    r12, r12
0x14035a133  jz      loc_14035B2FF
0x14035a139  cmp     al, r14b
0x14035a13c  jnz     loc_14035B359
0x14035a142  mov     r8d, 20h ; ' '; Size
0x14035a148  mov     rdx, rbx; Src
0x14035a14b  lea     rcx, [rsp+578h+var_4F8]; void *
0x14035a153  call    RtlCopyFromUser
0x14035a158  jmp     short loc_14035A18F
0x14035a15a  lea     rcx, [rsp+578h+var_528]; this
0x14035a15f  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x14035a164  cmp     [rsp+578h+var_518], 0
0x14035a169  jz      short loc_14035A185
0x14035a16b  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x14035a172  jz      short loc_14035A185
0x14035a174  mov     r9d, [rsp+578h+var_528]
0x14035a179  lea     rdx, EventProfilerExit
0x14035a180  call    McTemplateK0q_EtwWriteTransfer
0x14035a185  mov     eax, 0C000000Dh
0x14035a18a  jmp     loc_14035CEE2
0x14035a18f  cmp     [rsp+578h+var_4F8.Type], 405h
0x14035a19a  jz      loc_14035B375
0x14035a1a0  cmp     [rsp+578h+var_4F8.Type], 400h
0x14035a1ab  jge     loc_14035ADCE
0x14035a1b1  mov     ecx, [rsp+578h+var_4F8.Type]
0x14035a1b8  sub     ecx, 1
0x14035a1bb  jz      loc_14035B393
0x14035a1c1  sub     ecx, 2
0x14035a1c4  jz      loc_14035B393
0x14035a1ca  sub     ecx, 19h
0x14035a1cd  jz      loc_14035B393
0x14035a1d3  cmp     ecx, 1
0x14035a1d6  jz      loc_14035B393
0x14035a1dc  cmp     [rsp+578h+var_4F8.Type], 1
0x14035a1e4  jz      loc_14035B3C8
0x14035a1ea  xorps   xmm0, xmm0
0x14035a1ed  movdqu  xmmword ptr [rsp+578h+var_4D8], xmm0
0x14035a1f6  mov     eax, [rsp+578h+var_4F8.PrivateDriverDataSize]
0x14035a1fd  mov     esi, 3
0x14035a202  lea     r13d, [rsi+2Dh]
0x14035a206  cmp     [rsp+578h+var_4F8.Type], esi
0x14035a20d  jz      loc_14035B3DE
0x14035a213  mov     ebx, eax
0x14035a215  cmp     eax, 200h
0x14035a21a  ja      loc_14035B3EA
0x14035a220  lea     r15, [rsp+578h+Src]
0x14035a228  mov     [rsp+578h+var_450], r15
0x14035a230  test    r15, r15
0x14035a233  jz      loc_14035B40D
0x14035a239  cmp     [rsp+578h+var_4F8.Type], esi
0x14035a240  jz      loc_14035B4C1
0x14035a246  cmp     [rsp+578h+var_50F], r14b
0x14035a24b  jnz     loc_14035B4D3
0x14035a251  mov     r8d, [rsp+578h+var_4F8.PrivateDriverDataSize]; Size
0x14035a259  mov     rdx, [rsp+578h+var_4F8.pPrivateDriverData]; Src
0x14035a261  mov     rcx, r15; void *
0x14035a264  call    RtlCopyFromUser
0x14035a269  jmp     short loc_14035A2CF
0x14035a26b  mov     rdx, 0FFFFFFFFC000000Dh
0x14035a272  mov     ecx, 3
0x14035a277  call    cs:__imp_WdLogSingleEntry1
0x14035a27e  nop     dword ptr [rax+rax+00h]
0x14035a283  mov     cs:WdLogGlobalForLineNumber, 646h
0x14035a28d  lea     rcx, [rsp+578h+var_4D8]
0x14035a295  call    _DxgkEscape____2___ENSURE_DATA_DELETION___ENSURE_DATA_DELETION
0x14035a29a  lea     rcx, [rsp+578h+var_528]; this
0x14035a29f  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x14035a2a4  cmp     [rsp+578h+var_518], 0
0x14035a2a9  jz      short loc_14035A2C5
0x14035a2ab  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x14035a2b2  jz      short loc_14035A2C5
0x14035a2b4  mov     r9d, [rsp+578h+var_528]
0x14035a2b9  lea     rdx, EventProfilerExit
0x14035a2c0  call    McTemplateK0q_EtwWriteTransfer
0x14035a2c5  mov     eax, 0C000000Dh
0x14035a2ca  jmp     loc_14035CEE2
0x14035a2cf  test    byte ptr [rsp+578h+var_4F8.Flags], 40h
0x14035a2d7  jnz     loc_14035B4F0
0x14035a2dd  mov     edx, [rsp+578h+var_4F8.Type]
0x14035a2e4  cmp     edx, 1Bh
0x14035a2e7  jg      loc_14035A7AE
0x14035a2ed  jz      loc_14035B77C
0x14035a2f3  mov     ecx, edx
0x14035a2f5  sub     ecx, 1
0x14035a2f8  jz      loc_14035B71C
0x14035a2fe  sub     ecx, 7
0x14035a301  jz      loc_14035B58F
0x14035a307  sub     ecx, 1
0x14035a30a  jz      loc_14035CD3B
0x14035a310  sub     ecx, 0Bh
0x14035a313  jz      loc_14035AA2D
0x14035a319  sub     ecx, 4
0x14035a31c  jz      loc_14035B55E
0x14035a322  cmp     ecx, 1
0x14035a325  jz      loc_14035B52D
0x14035a32b  mov     [rsp+578h+var_4A0], rdi
0x14035a333  mov     [rsp+578h+var_468], rdi
0x14035a33b  cmp     [rsp+578h+var_4F8.Type], 0Dh
0x14035a343  jz      loc_14035B870
0x14035a349  mov     r13, rdi
0x14035a34c  mov     [rsp+578h+var_478], rdi
0x14035a354  mov     rdx, r12; struct DXGPROCESS *
0x14035a357  lea     rcx, [rsp+578h+var_3F8]; this
0x14035a35f  call    ??0DXGHANDLETABLELOCKSHARED@@QEAA@PEAVDXGPROCESS@@@Z; DXGHANDLETABLELOCKSHARED::DXGHANDLETABLELOCKSHARED(DXGPROCESS *)
0x14035a364  mov     edx, [rsp+578h+var_4F8.hAdapter]
0x14035a36b  test    edx, edx
0x14035a36d  jnz     loc_14035ABD9
0x14035a373  or      r12d, 0FFFFFFFFh
0x14035a377  test    r13, r13
0x14035a37a  jz      loc_14035B467
0x14035a380  mov     rbx, rdi
0x14035a383  mov     [rsp+578h+var_498], rbx
0x14035a38b  mov     [rsp+578h+var_458], rbx
0x14035a393  mov     r9d, [rsp+578h+var_4F8.hDevice]
0x14035a39b  test    r9d, r9d
0x14035a39e  jnz     loc_14035A7F3
0x14035a3a4  mov     rcx, rdi
0x14035a3a7  mov     [rsp+578h+var_470], rcx
0x14035a3af  mov     r9d, [rsp+578h+var_4F8.hContext]
0x14035a3b7  test    r9d, r9d
0x14035a3ba  jnz     loc_14035AA9A
0x14035a3c0  test    rbx, rbx
0x14035a3c3  jz      short loc_14035A3DA
0x14035a3c5  lock add [rbx+40h], r14
0x14035a3ca  mov     rax, [rbx+10h]
0x14035a3ce  mov     r13, [rax+10h]
0x14035a3d2  mov     [rsp+578h+var_478], r13
0x14035a3da  test    rcx, rcx
0x14035a3dd  jnz     loc_14035B931
0x14035a3e3  lock add [r13+18h], r14
0x14035a3e8  lea     rcx, [rsp+578h+var_3F8]; this
0x14035a3f0  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x14035a3f5  cmp     dword ptr [r13+958h], 5023h
0x14035a400  jnb     loc_14035ACDF
0x14035a406  mov     [rsp+578h+var_4B0], r13
0x14035a40e  mov     [rsp+578h+var_4A8], 0FFFFFFFFFFFFFFFFh
0x14035a41a  mov     qword ptr [rsp+578h+var_508], rbx
0x14035a41f  mov     rax, [rsp+578h+var_470]
0x14035a427  mov     [rsp+578h+var_500], rax
0x14035a42c  mov     byte ptr [rsp+578h+var_548], dil; unsigned __int8
0x14035a431  mov     qword ptr [rsp+578h+var_550], rdi; unsigned __int64 *
0x14035a436  mov     qword ptr [rsp+578h+var_558], rdi; struct DXGADAPTER **
0x14035a43b  lea     r9, [rsp+578h+var_410]; unsigned __int64 *
0x14035a443  lea     r8, [rsp+578h+var_4A0]; struct DXGADAPTER **
0x14035a44b  xor     edx, edx; unsigned int
0x14035a44d  mov     rcx, r13; this
0x14035a450  call    ?DxgkpGetPairingAdapters@@YAJPEAVDXGADAPTER@@IPEAPEAV1@PEA_K12E@Z; DxgkpGetPairingAdapters(DXGADAPTER *,uint,DXGADAPTER * *,unsigned __int64 *,DXGADAPTER * *,unsigned __int64 *,uchar)
0x14035a455  mov     esi, eax
0x14035a457  mov     rbx, [rsp+578h+var_4A0]
0x14035a45f  test    eax, eax
0x14035a461  js      short loc_14035A46B
0x14035a463  mov     rcx, rbx; this
0x14035a466  call    ?ReleaseReference@DXGADAPTER@@QEAAX_K@Z; DXGADAPTER::ReleaseReference(unsigned __int64)
0x14035a46b  mov     ecx, [rsp+578h+var_4F8.Type]
0x14035a472  sub     ecx, 1
0x14035a475  jz      loc_14035BA23
0x14035a47b  cmp     ecx, 7
0x14035a47e  jz      loc_14035B95B
0x14035a484  xor     r8d, r8d; struct DXGADAPTER *
0x14035a487  mov     rdx, r13; struct DXGADAPTER *
0x14035a48a  lea     rcx, [rsp+578h+var_328]; this
0x14035a492  call    ??0COREADAPTERACCESS@@QEAA@QEAVDXGADAPTER@@0@Z; COREADAPTERACCESS::COREADAPTERACCESS(DXGADAPTER * const,DXGADAPTER * const)
0x14035a497  mov     rdx, [rsp+578h+var_468]; struct DXGADAPTER *
0x14035a49f  lea     rcx, [rsp+578h+var_368]; this
0x14035a4a7  call    ??0COREACCESS@@QEAA@QEAVDXGADAPTER@@_N@Z; COREACCESS::COREACCESS(DXGADAPTER * const,bool)
0x14035a4ac  mov     dword ptr [rsp+578h+var_4A0], edi
0x14035a4b3  mov     [rsp+578h+var_488], r13
0x14035a4bb  mov     [rsp+578h+var_480], dil
0x14035a4c3  cmp     [rsp+578h+var_4F8.Type], 0Dh
0x14035a4cb  jnz     loc_14035A8D0
0x14035a4d1  xor     edx, edx; char *
0x14035a4d3  lea     rcx, [rsp+578h+var_368]; this
0x14035a4db  call    ?AcquireShared@COREACCESS@@QEAAXPEBD@Z; COREACCESS::AcquireShared(char const *)
0x14035a4e0  cmp     [rsp+578h+var_4F8.hDevice], edi
0x14035a4e7  jnz     loc_14035A93C
0x14035a4ed  mov     [rsp+578h+var_510], r14b
0x14035a4f2  cmp     [rsp+578h+var_4F8.Type], edi
0x14035a4f9  jz      loc_14035AD5E
0x14035a4ff  test    rbx, rbx
0x14035a502  jnz     loc_14035BBE3
0x14035a508  movsxd  rdx, [rsp+578h+var_4F8.Type]
0x14035a510  cmp     edx, 0Fh
0x14035a513  jg      loc_14035C5B3
0x14035a519  jz      loc_14035B26E
0x14035a51f  cmp     edx, 6
0x14035a522  jg      loc_14035C310
0x14035a528  jz      loc_14035C2EC
0x14035a52e  mov     ecx, edx
0x14035a530  test    edx, edx
0x14035a532  jnz     loc_14035BDB7
0x14035a538  xorps   xmm0, xmm0
0x14035a53b  movups  xmmword ptr [rsp+578h+var_448.hDevice], xmm0
0x14035a543  movups  xmmword ptr [rsp+578h+var_448.pPrivateDriverData], xmm0
0x14035a54b  movups  xmmword ptr [rsp+578h+var_448.hContext], xmm0
0x14035a553  cmp     [rsp+578h+var_510], dil
0x14035a558  jz      loc_14035BF4E
0x14035a55e  lea     rax, ?DefaultDdiEscape@DXGADAPTER@@CAJQEAXPEBU_DXGKARG_ESCAPE@@@Z; DXGADAPTER::DefaultDdiEscape(void * const,_DXGKARG_ESCAPE const *)
0x14035a565  cmp     [r13+250h], rax
0x14035a56c  jnz     loc_14035A65A
0x14035a572  mov     r8, 0FFFFFFFFC00000BBh
0x14035a579  mov     rdx, r13
0x14035a57c  mov     ecx, 3
0x14035a581  call    cs:__imp_WdLogSingleEntry2
0x14035a588  nop     dword ptr [rax+rax+00h]
0x14035a58d  mov     cs:WdLogGlobalForLineNumber, 9B8h
0x14035a597  mov     esi, 0C00000BBh
0x14035a59c  test    esi, esi
0x14035a59e  jns     loc_14035A9BB
0x14035a5a4  lea     rcx, [rsp+578h+var_490]; this
0x14035a5ac  call    ??1DXGADAPTERSTOPRESETLOCKSHARED@@QEAA@XZ; DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(void)
0x14035a5b1  lea     rcx, [rsp+578h+var_368]; this
0x14035a5b9  call    ??1COREACCESS@@QEAA@XZ; COREACCESS::~COREACCESS(void)
0x14035a5be  lea     rcx, [rsp+578h+var_328]; this
0x14035a5c6  call    ??1COREADAPTERACCESS@@QEAA@XZ; COREADAPTERACCESS::~COREADAPTERACCESS(void)
0x14035a5cb  lea     rcx, [rsp+578h+var_500]; this
0x14035a5d0  call    ??1ENSURE_CONTEXT_DEREFERENCE@@QEAA@XZ; ENSURE_CONTEXT_DEREFERENCE::~ENSURE_CONTEXT_DEREFERENCE(void)
0x14035a5d5  mov     rcx, [rsp+578h+var_498]
0x14035a5dd  test    rcx, rcx
0x14035a5e0  jz      short loc_14035A5FE
0x14035a5e2  or      rax, 0FFFFFFFFFFFFFFFFh
0x14035a5e6  lock xadd [rcx+40h], rax
0x14035a5ec  cmp     rax, 1
0x14035a5f0  jnz     short loc_14035A5FE
0x14035a5f2  mov     rdx, rcx; struct DXGDEVICE *
0x14035a5f5  mov     rcx, [rcx+10h]; this
0x14035a5f9  call    ?DestroyDeviceNoLocks@ADAPTER_RENDER@@QEAAXPEAVDXGDEVICE@@@Z; ADAPTER_RENDER::DestroyDeviceNoLocks(DXGDEVICE *)
0x14035a5fe  mov     rcx, [rsp+578h+var_4B0]; this
0x14035a606  test    rcx, rcx
0x14035a609  jz      short loc_14035A610
0x14035a60b  call    ?ReleaseReference@DXGADAPTER@@QEAAX_K@Z; DXGADAPTER::ReleaseReference(unsigned __int64)
0x14035a610  mov     rcx, [rsp+578h+var_4D8]; void *
0x14035a618  test    rcx, rcx
0x14035a61b  jz      short loc_14035A622
0x14035a61d  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x14035a622  mov     rcx, [rsp+578h+var_4D8+8]; this
0x14035a62a  test    rcx, rcx
0x14035a62d  jz      short loc_14035A634
0x14035a62f  call    ?ReleaseReference@DXGADAPTER@@QEAAX_K@Z; DXGADAPTER::ReleaseReference(unsigned __int64)
0x14035a634  lea     rcx, [rsp+578h+var_528]; this
0x14035a639  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x14035a63e  cmp     [rsp+578h+var_518], dil
0x14035a643  jz      short loc_14035A652
0x14035a645  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, r14b
0x14035a64c  jnz     loc_14035B4AB
0x14035a652  mov     eax, esi
0x14035a654  jmp     loc_14035CEE2
0x14035a65a  mov     ecx, [rsp+578h+var_4F8.PrivateDriverDataSize]
0x14035a661  test    ecx, ecx
0x14035a663  jz      loc_14035C2B7
0x14035a669  cmp     [rsp+578h+var_4F8.pPrivateDriverData], rdi
0x14035a671  jz      loc_14035C2B7
0x14035a677  mov     rax, [rsp+578h+var_498]
0x14035a67f  test    rax, rax
0x14035a682  jnz     loc_14035C296
0x14035a688  mov     rax, [rsp+578h+var_470]
0x14035a690  test    rax, rax
0x14035a693  jz      loc_14035C2AA
0x14035a699  mov     rax, [rax+0B8h]
0x14035a6a0  mov     [rsp+578h+var_448.hContext], rax
0x14035a6a8  mov     eax, dword ptr [rsp+578h+var_4F8.Flags]
0x14035a6af  mov     dword ptr [rsp+578h+var_448.Flags], eax
0x14035a6b6  mov     eax, [r13+1BCh]
0x14035a6bd  test    al, 8
  ... truncated ...
```
