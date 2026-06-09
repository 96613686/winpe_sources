# DxgkEscape

- ea: `0x14035a530`
- end: `0x14035d3bf`
- name: `DxgkEscape`
- size: `11919`
- prototype: `__int64 __fastcall(_D3DKMT_ESCAPE *Src, __int64, __int64)`
- caller_count: `1`
- callee_count: `89`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x14028c8f0`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x140012540`
- `0x140012cd4`
- `0x140013a20`
- `0x1400157bc`
- `0x140015940`
- `0x140015a70`
- `0x140015b60`
- `0x140015bc0`
- `0x1400164c0`
- `0x1400169f0`
- `0x140017010`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001cd10`
- `0x14001d1a0`
- `0x14001d214`
- `0x14001f258`
- `0x14001f630`
- `0x14002ee60`
- `0x1400309f0`
- `0x140030a70`
- `0x140033a40`
- `0x140033d80`
- `0x140035f90`
- `0x14003fdc8`
- `0x140041db4`
- `0x1400426f8`
- `0x140042cc0`
- `0x140044dd4`
- `0x140046d28`
- `0x1400480b4`
- `0x14004d93c`
- `0x140050484`
- `0x14005fad8`
- `0x140060a74`
- `0x14006187c`
- `0x140061988`
- `0x1400624e0`
- `0x1400674c4`
- `0x14006df00`
- `0x1400750c4`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a0d00`
- `0x1400a1000`
- `0x1401931c8`
- `0x14019951c`
- `0x14019af20`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14035abe2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14035abe2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14035ac3b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14035b392`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14035ac3b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14035b392`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14035cb9b`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14035cb9b`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14035ac2f`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14035b386`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14035ac2f`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14035b386`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14035abf4`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14035abf4`
- `ntoskrnl!KeDelayExecutionThread` at `0x14035c3c6`
- `ntoskrnl!KeDelayExecutionThread` at `0x14035c3c6`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x14035a5d0`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x14035a5d0`
- `watchdog!WdLogSingleEntry2` at `0x14035aa31`
- `watchdog!WdLogSingleEntry2` at `0x14035ad65`
- `watchdog!WdLogSingleEntry2` at `0x14035aea7`
- `watchdog!WdLogSingleEntry2` at `0x14035b485`
- `watchdog!WdLogSingleEntry2` at `0x14035b66b`
- `watchdog!WdLogSingleEntry2` at `0x14035b6c0`
- `watchdog!WdLogSingleEntry2` at `0x14035b6fc`
- `watchdog!WdLogSingleEntry2` at `0x14035b73d`
- `watchdog!WdLogSingleEntry2` at `0x14035b8cf`
- `watchdog!WdLogSingleEntry2` at `0x14035b926`
- `watchdog!WdLogSingleEntry2` at `0x14035bb64`
- `watchdog!WdLogSingleEntry2` at `0x14035be86`
- `watchdog!WdLogSingleEntry2` at `0x14035c33d`
- `watchdog!WdLogSingleEntry2` at `0x14035c61e`
- `watchdog!WdLogSingleEntry2` at `0x14035c6ca`
- `watchdog!WdLogSingleEntry2` at `0x14035cbb2`
- `watchdog!WdLogSingleEntry2` at `0x14035cd17`
- `watchdog!WdLogSingleEntry2` at `0x14035d259`
- `watchdog!WdLogSingleEntry2` at `0x14035aa31`
- `watchdog!WdLogSingleEntry2` at `0x14035ad65`
- `watchdog!WdLogSingleEntry2` at `0x14035aea7`
- `watchdog!WdLogSingleEntry2` at `0x14035b485`
- `watchdog!WdLogSingleEntry2` at `0x14035b66b`
- `watchdog!WdLogSingleEntry2` at `0x14035b6c0`
- `watchdog!WdLogSingleEntry2` at `0x14035b6fc`
- `watchdog!WdLogSingleEntry2` at `0x14035b73d`
- `watchdog!WdLogSingleEntry2` at `0x14035b8cf`
- `watchdog!WdLogSingleEntry2` at `0x14035b926`
- `watchdog!WdLogSingleEntry2` at `0x14035bb64`
- `watchdog!WdLogSingleEntry2` at `0x14035be86`
- `watchdog!WdLogSingleEntry2` at `0x14035c33d`
- `watchdog!WdLogSingleEntry2` at `0x14035c61e`
- `watchdog!WdLogSingleEntry2` at `0x14035c6ca`
- `watchdog!WdLogSingleEntry2` at `0x14035cbb2`
- `watchdog!WdLogSingleEntry2` at `0x14035cd17`
- `watchdog!WdLogSingleEntry2` at `0x14035d259`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14035c576`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14035c5da`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14035c576`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14035c5da`
- `watchdog!WdLogSingleEntry3` at `0x14035b051`
- `watchdog!WdLogSingleEntry3` at `0x14035c781`
- `watchdog!WdLogSingleEntry3` at `0x14035b051`
- `watchdog!WdLogSingleEntry3` at `0x14035c781`
- `watchdog!WdLogSingleEntry0` at `0x14035ae12`
- `watchdog!WdLogSingleEntry0` at `0x14035afd9`
- `watchdog!WdLogSingleEntry0` at `0x14035b121`
- `watchdog!WdLogSingleEntry0` at `0x14035b325`
- `watchdog!WdLogSingleEntry0` at `0x14035b9c2`
- `watchdog!WdLogSingleEntry0` at `0x14035bc57`
- `watchdog!WdLogSingleEntry0` at `0x14035befc`
- `watchdog!WdLogSingleEntry0` at `0x14035c8ab`
- `watchdog!WdLogSingleEntry0` at `0x14035caf9`
- `watchdog!WdLogSingleEntry0` at `0x14035ce51`
- `watchdog!WdLogSingleEntry0` at `0x14035cf3e`
- `watchdog!WdLogSingleEntry0` at `0x14035d013`
- `watchdog!WdLogSingleEntry0` at `0x14035d0a8`
- `watchdog!WdLogSingleEntry0` at `0x14035d1b0`
- `watchdog!WdLogSingleEntry0` at `0x14035ae12`
- `watchdog!WdLogSingleEntry0` at `0x14035afd9`
- `watchdog!WdLogSingleEntry0` at `0x14035b121`
- `watchdog!WdLogSingleEntry0` at `0x14035b325`
- `watchdog!WdLogSingleEntry0` at `0x14035b9c2`
- `watchdog!WdLogSingleEntry0` at `0x14035bc57`
- `watchdog!WdLogSingleEntry0` at `0x14035befc`
- `watchdog!WdLogSingleEntry0` at `0x14035c8ab`
- `watchdog!WdLogSingleEntry0` at `0x14035caf9`
- `watchdog!WdLogSingleEntry0` at `0x14035ce51`
- `watchdog!WdLogSingleEntry0` at `0x14035cf3e`
- `watchdog!WdLogSingleEntry0` at `0x14035d013`
- `watchdog!WdLogSingleEntry0` at `0x14035d0a8`
- `watchdog!WdLogSingleEntry0` at `0x14035d1b0`
- `watchdog!WdLogSingleEntry1` at `0x14035a727`
- `watchdog!WdLogSingleEntry1` at `0x14035b1b6`
- `watchdog!WdLogSingleEntry1` at `0x14035b3d3`
- `watchdog!WdLogSingleEntry1` at `0x14035b7be`
- `watchdog!WdLogSingleEntry1` at `0x14035b85d`
- `watchdog!WdLogSingleEntry1` at `0x14035ba79`
- `watchdog!WdLogSingleEntry1` at `0x14035bbb1`
- `watchdog!WdLogSingleEntry1` at `0x14035bdf0`
- `watchdog!WdLogSingleEntry1` at `0x14035c1d0`
- `watchdog!WdLogSingleEntry1` at `0x14035c219`
- `watchdog!WdLogSingleEntry1` at `0x14035c29c`
- `watchdog!WdLogSingleEntry1` at `0x14035c822`
- `watchdog!WdLogSingleEntry1` at `0x14035cdce`
- `watchdog!WdLogSingleEntry1` at `0x14035cdf8`
- `watchdog!WdLogSingleEntry1` at `0x14035cf0e`
- `watchdog!WdLogSingleEntry1` at `0x14035cfe3`
- `watchdog!WdLogSingleEntry1` at `0x14035d077`
- `watchdog!WdLogSingleEntry1` at `0x14035d142`
- `watchdog!WdLogSingleEntry1` at `0x14035d33e`
- `watchdog!WdLogSingleEntry1` at `0x14035a727`
- `watchdog!WdLogSingleEntry1` at `0x14035b1b6`
- `watchdog!WdLogSingleEntry1` at `0x14035b3d3`
- `watchdog!WdLogSingleEntry1` at `0x14035b7be`
- `watchdog!WdLogSingleEntry1` at `0x14035b85d`
- `watchdog!WdLogSingleEntry1` at `0x14035ba79`
- `watchdog!WdLogSingleEntry1` at `0x14035bbb1`
- `watchdog!WdLogSingleEntry1` at `0x14035bdf0`
- `watchdog!WdLogSingleEntry1` at `0x14035c1d0`
- `watchdog!WdLogSingleEntry1` at `0x14035c219`
- `watchdog!WdLogSingleEntry1` at `0x14035c29c`
- `watchdog!WdLogSingleEntry1` at `0x14035c822`
- `watchdog!WdLogSingleEntry1` at `0x14035cdce`
- `watchdog!WdLogSingleEntry1` at `0x14035cdf8`
- `watchdog!WdLogSingleEntry1` at `0x14035cf0e`
- `watchdog!WdLogSingleEntry1` at `0x14035cfe3`
- `watchdog!WdLogSingleEntry1` at `0x14035d077`
- `watchdog!WdLogSingleEntry1` at `0x14035d142`
- `watchdog!WdLogSingleEntry1` at `0x14035d33e`

## string_xrefs

- `0x14035c24c`: `Driver Common Escape is block for (0x%I64x)`

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
  D3DKMT_HANDLE hDevice; // r9d
  __int64 v13; // rcx
  __int64 hContext; // r9
  unsigned __int64 v15; // rdx
  __int64 v16; // rsi
  DXGADAPTER *v17; // rbx
  bool v18; // r8
  __int64 v19; // r9
  unsigned __int64 v20; // rdx
  ADAPTER_RENDER **v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // r8
  DXGPROCESS *v25; // rsi
  unsigned __int8 IsVmProcessOrVmValidation; // al
  __int64 v27; // rbx
  struct DXGPROCESS_RENDER_ADAPTER_INFO *RenderAdapterInfo; // rax
  _DXGKARG_ESCAPE *v29; // rdx
  DXGADAPTER *v30; // rcx
  int InvalidModesForTestPurposes; // eax
  int v32; // eax
  DXGPROCESS *v33; // r8
  int v34; // r8d
  bool v35; // al
  __int64 v36; // rbx
  unsigned __int8 v37; // al
  int v38; // eax
  int v39; // ebx
  __int64 v40; // rcx
  __int64 v41; // r8
  D3DKMT_HANDLE v42; // eax
  __int64 v43; // rdx
  DXGPROCESS *v44; // r8
  int v45; // r8d
  bool v46; // al
  __int64 v47; // rdx
  __int64 v48; // rcx
  D3DKMT_HANDLE v49; // r12d
  D3DKMT_HANDLE v50; // ebx
  DXGPROCESS *v51; // rcx
  unsigned int v52; // ecx
  bool v53; // al
  __int64 v54; // rcx
  _DWORD *v55; // rax
  unsigned int v56; // ecx
  __int64 v58; // rcx
  __int64 v59; // rax
  __int64 v60; // rcx
  __int64 v61; // r8
  ADAPTER_DISPLAY *v62; // rcx
  const wchar_t *v63; // r9
  __int64 v64; // rcx
  __int64 v65; // r8
  __int64 v66; // rcx
  __int64 v67; // r8
  __int64 v68; // rcx
  __int64 v69; // r8
  __int64 v70; // rcx
  __int64 v71; // r8
  __int64 v72; // rcx
  __int64 v73; // r8
  __int64 v74; // rcx
  __int64 v75; // rcx
  unsigned __int64 v76; // rcx
  __int64 v77; // rdx
  unsigned __int64 v78; // rcx
  __int64 v79; // rdx
  unsigned int v80; // eax
  struct DXGPROCESS *v81; // rax
  struct DXGADAPTER *v82; // rbx
  DXGGLOBAL *Global; // rax
  DXGGLOBAL *v84; // rax
  unsigned __int64 v85; // rcx
  __int64 v86; // rdx
  void *v87; // r9
  int v88; // eax
  void *v89; // r9
  int v90; // eax
  unsigned int v91; // ecx
  __int64 v92; // rcx
  char v93; // al
  unsigned int v94; // esi
  unsigned int v95; // ebx
  unsigned int HostProcess; // eax
  int v97; // eax
  unsigned __int64 v98; // rdx
  unsigned int v99; // eax
  unsigned int v100; // eax
  __int64 v101; // rcx
  struct _D3DKMT_VIDSCH_ESCAPE *v102; // r8
  struct _VIDSCH_GLOBAL *v103; // rdx
  __int64 v104; // rcx
  __int64 v105; // rdx
  _QWORD *v106; // rbx
  struct DXGADAPTER *v107; // rbx
  int v108; // eax
  unsigned int CurrentProcessSessionId; // eax
  DXGDEVICE *v110; // r10
  char v111; // r9
  unsigned int NumDifferentPhysicalAdapters; // eax
  unsigned int v113; // r8d
  int v114; // eax
  __int64 v115; // rax
  const wchar_t *v116; // r9
  __int64 v117; // rax
  __int64 v118; // rcx
  int DiagnosticsBuffer; // eax
  unsigned int v120; // [rsp+50h] [rbp-528h] BYREF
  __int64 v121; // [rsp+58h] [rbp-520h]
  char v122; // [rsp+60h] [rbp-518h]
  unsigned __int8 v123; // [rsp+68h] [rbp-510h] BYREF
  char v124; // [rsp+69h] [rbp-50Fh]
  enum _D3DKMT_ESCAPETYPE v125[2]; // [rsp+70h] [rbp-508h] BYREF
  __int64 v126; // [rsp+78h] [rbp-500h] BYREF
  _D3DKMT_ESCAPE v127; // [rsp+80h] [rbp-4F8h] BYREF
  DXGADAPTER *v128[2]; // [rsp+A0h] [rbp-4D8h] BYREF
  unsigned __int64 v129; // [rsp+B0h] [rbp-4C8h] BYREF
  bool v130; // [rsp+B8h] [rbp-4C0h]
  DXGPROCESS *v131; // [rsp+C0h] [rbp-4B8h]
  DXGADAPTER *v132[2]; // [rsp+C8h] [rbp-4B0h] BYREF
  DXGADAPTER *v133; // [rsp+D8h] [rbp-4A0h] BYREF
  DXGDEVICE *v134; // [rsp+E0h] [rbp-498h]
  char v135[8]; // [rsp+E8h] [rbp-490h] BYREF
  __int64 v136; // [rsp+F0h] [rbp-488h]
  char v137; // [rsp+F8h] [rbp-480h]
  __int64 v138; // [rsp+100h] [rbp-478h]
  __int64 v139; // [rsp+108h] [rbp-470h]
  struct DXGADAPTER *pPrivateDriverData; // [rsp+110h] [rbp-468h]
  union _LARGE_INTEGER Interval; // [rsp+118h] [rbp-460h] BYREF
  __int64 v142; // [rsp+120h] [rbp-458h]
  unsigned int *v143; // [rsp+128h] [rbp-450h]
  _DXGKARG_ESCAPE v144; // [rsp+130h] [rbp-448h] BYREF
  unsigned __int64 v145; // [rsp+168h] [rbp-410h] BYREF
  char v146[8]; // [rsp+170h] [rbp-408h] BYREF
  struct _DXGK_DISPLAY_SCENARIO_CONTEXT *v147; // [rsp+178h] [rbp-400h]
  _BYTE v148[24]; // [rsp+180h] [rbp-3F8h] BYREF
  __int64 v149; // [rsp+198h] [rbp-3E0h] BYREF
  struct _D3DDDI_ESCAPEFLAGS::$DB860278E5E511C34FE0F76D94154466::$9A2C51F7B5B2EC690ABA117774D32C3A v150; // [rsp+1A0h] [rbp-3D8h]
  int v151; // [rsp+1A4h] [rbp-3D4h]
  unsigned int *v152; // [rsp+1A8h] [rbp-3D0h]
  UINT v153; // [rsp+1B0h] [rbp-3C8h]
  int v154; // [rsp+1B4h] [rbp-3C4h]
  __int64 v155; // [rsp+1B8h] [rbp-3C0h]
  __int64 v156; // [rsp+1C0h] [rbp-3B8h]
  __int64 v157; // [rsp+1C8h] [rbp-3B0h] BYREF
  struct _D3DDDI_ESCAPEFLAGS::$DB860278E5E511C34FE0F76D94154466::$9A2C51F7B5B2EC690ABA117774D32C3A Value; // [rsp+1D0h] [rbp-3A8h]
  int v159; // [rsp+1D4h] [rbp-3A4h]
  unsigned int *v160; // [rsp+1D8h] [rbp-3A0h]
  UINT v161; // [rsp+1E0h] [rbp-398h]
  int v162; // [rsp+1E4h] [rbp-394h]
  __int64 v163; // [rsp+1E8h] [rbp-390h]
  __int64 v164; // [rsp+1F0h] [rbp-388h]
  _BYTE v165[24]; // [rsp+1F8h] [rbp-380h] BYREF
  _BYTE v166[64]; // [rsp+210h] [rbp-368h] BYREF
  _BYTE v167[144]; // [rsp+250h] [rbp-328h] BYREF
  _OWORD v168[3]; // [rsp+2E0h] [rbp-298h] BYREF
  _OWORD v169[3]; // [rsp+310h] [rbp-268h] BYREF
  char Srca; // [rsp+340h] [rbp-238h] BYREF

  v120 = -1;
  v121 = 0;
  if ( (qword_1401604F0 & 2) != 0 )
  {
    v122 = 1;
    v120 = 2016;
    if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(Src, EventProfilerEnter, a3, 2016);
  }
  else
  {
    v122 = 0;
  }
  DXGETWPROFILER_BASE::PushProfilerEntry(&v120, 2016);
  Current = DXGPROCESS::GetCurrent();
  v131 = Current;
  memset(&v127, 0, sizeof(v127));
  CurrentThreadPreviousMode = PsGetCurrentThreadPreviousMode();
  v124 = CurrentThreadPreviousMode;
  if ( !Current )
  {
    LODWORD(v16) = -1073741811;
    WdLogSingleEntry1(2, -1073741811);
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
    RtlCopyFromUser(&v127, Src, 0x20u);
  else
    v127 = *Src;
  if ( v127.Type == D3DKMT_ESCAPE_WIN32K_BDD_FALLBACK )
  {
    if ( !(*(unsigned int (**)(void))(*((_QWORD *)Current + 11) + 440LL))() )
    {
LABEL_202:
      DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v120);
      if ( v122 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
        McTemplateK0q_EtwWriteTransfer(v66, EventProfilerExit, v67, v120);
      return 3221225506LL;
    }
  }
  else if ( v127.Type >= D3DKMT_ESCAPE_WIN32K_START )
  {
    v39 = (*(__int64 (__fastcall **)(_D3DKMT_ESCAPE *))(*((_QWORD *)Current + 11) + 432LL))(&v127);
    goto LABEL_127;
  }
  if ( (v127.Type == D3DKMT_ESCAPE_VIDMM || v127.Type == D3DKMT_ESCAPE_VIDSCH || (unsigned int)(v127.Type - 28) < 2)
    && !InternalEscapeEnabled() )
  {
    WdLogSingleEntry1(3, v127.Type);
    WdLogGlobalForLineNumber = 1520;
    goto LABEL_202;
  }
  if ( v127.Type == D3DKMT_ESCAPE_VIDMM && v127.PrivateDriverDataSize < 0x840 )
    goto LABEL_189;
  *(_OWORD *)v128 = 0;
  PrivateDriverDataSize = v127.PrivateDriverDataSize;
  if ( v127.Type == D3DKMT_ESCAPE_VIDSCH && v127.PrivateDriverDataSize <= 0x30 )
    PrivateDriverDataSize = 48;
  v7 = PrivateDriverDataSize;
  if ( PrivateDriverDataSize > 0x200 )
  {
    p_Srca = (unsigned int *)operator new[](PrivateDriverDataSize, 1265072196, 258);
    v128[0] = (DXGADAPTER *)p_Srca;
  }
  else
  {
    p_Srca = (unsigned int *)&Srca;
  }
  v143 = p_Srca;
  if ( !p_Srca )
  {
    LODWORD(v16) = -1073741801;
    WdLogSingleEntry2(6, v7, -1073741801);
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
    DxgkEscape_::_2_::ENSURE_DATA_DELETION::_ENSURE_DATA_DELETION(v128);
LABEL_69:
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v120);
    if ( v122 )
    {
      if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
        McTemplateK0q_EtwWriteTransfer(v22, EventProfilerExit, v23, v120);
    }
    return (unsigned int)v16;
  }
  if ( v127.Type == D3DKMT_ESCAPE_VIDSCH )
    memset(p_Srca, 0, v7);
  if ( v124 == 1 )
    RtlCopyFromUser(p_Srca, v127.pPrivateDriverData, v127.PrivateDriverDataSize);
  else
    memmove(p_Srca, v127.pPrivateDriverData, v127.PrivateDriverDataSize);
  if ( (*(_BYTE *)&v127.Flags.0 & 0x40) != 0 && (v127.Type || !v127.hAdapter || (*(_BYTE *)&v127.Flags.0 & 1) != 0) )
  {
    WdLogSingleEntry0(3);
    WdLogGlobalForLineNumber = 1619;
    goto LABEL_188;
  }
  if ( v127.Type > D3DKMT_ESCAPE_SOFTGPU_ENABLE_DISABLE_HMD )
  {
    switch ( v127.Type )
    {
      case D3DKMT_ESCAPE_IDD_REQUEST:
        goto LABEL_121;
      case D3DKMT_ESCAPE_LOG_CODEPOINT_PACKET:
        if ( v127.PrivateDriverDataSize != 16 )
          goto LABEL_188;
        v143 = 0;
        DxgkLogCodePointPacket(*p_Srca, p_Srca[1], p_Srca[2], p_Srca[3], 0);
LABEL_206:
        ((void (*)(void))DxgkEscape_::_2_::ENSURE_DATA_DELETION::_ENSURE_DATA_DELETION)();
        DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v120);
        if ( v122 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
          McTemplateK0q_EtwWriteTransfer(v68, EventProfilerExit, v69, v120);
        return 0;
      case D3DKMT_ESCAPE_LOG_USERMODE_DAIG_PACKET:
        if ( v127.PrivateDriverDataSize < 0x30 || v127.PrivateDriverDataSize < p_Srca[1] )
          goto LABEL_188;
        v32 = DxgkWriteUserModeDiagEntry((struct _DXGK_DIAG_HEADER *)p_Srca);
        break;
      case D3DKMT_ESCAPE_GET_EXTERNAL_DIAGNOSTICS:
        goto LABEL_558;
      case D3DKMT_ESCAPE_GET_DISPLAY_CONFIGURATIONS|D3DKMT_ESCAPE_TDRDBGCTRL:
        if ( v127.PrivateDriverDataSize < 4 )
          goto LABEL_188;
        v32 = DxgkHandleCcdDatabaseRequests(*p_Srca, v127.PrivateDriverDataSize, p_Srca);
        break;
      case D3DKMT_ESCAPE_WIN32K_BDD_FALLBACK:
        v32 = DxgkpProcessBddFallbackRequest();
        break;
      default:
        goto LABEL_31;
    }
LABEL_273:
    v39 = v32;
    goto LABEL_201;
  }
  switch ( v127.Type )
  {
    case D3DKMT_ESCAPE_SOFTGPU_ENABLE_DISABLE_HMD:
      if ( g_OSTestSigningEnabled )
      {
        if ( v127.PrivateDriverDataSize != 200 )
          goto LABEL_188;
        v81 = DXGPROCESS::GetCurrent();
        if ( !v81 )
        {
          WdLogSingleEntry0(2);
          WdLogGlobalForLineNumber = 1824;
          DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Invalid process context", 1824, 0, 0, 0, 0);
          goto LABEL_188;
        }
        DXGUSERCRIT::DXGUSERCRIT((DXGUSERCRIT *)v165, v81);
        DXGUSERCRIT::Acquire((DXGUSERCRIT *)v165, 1);
        v146[0] = 0;
        CDisplayScenarioContextScope::ContextScopeConstructor((CDisplayScenarioContextScope *)v146, 0, 0x2Eu, 0);
        v39 = DxgkEnableDisableTargetAsHMD(
                (struct _D3DKMT_SOFTGPU_LUID_TARGET *)p_Srca,
                p_Srca[48],
                *((_BYTE *)p_Srca + 196),
                v147);
        CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)v146);
        DXGUSERCRIT::~DXGUSERCRIT((DXGUSERCRIT *)v165);
        goto LABEL_201;
      }
      goto LABEL_326;
    case D3DKMT_ESCAPE_VIDMM:
      v80 = *p_Srca;
      if ( *p_Srca == 5 )
      {
        v32 = DxgEscapeEvict((struct _D3DKMT_VIDMM_ESCAPE *)p_Srca);
      }
      else if ( v80 == 6 )
      {
        v32 = DxgEscapeEvictByNtHandle((struct _D3DKMT_VIDMM_ESCAPE *)p_Srca);
      }
      else
      {
        if ( v80 != 13 )
        {
          if ( v80 == 20 && (p_Srca[2] & 1) != 0 )
            *((_BYTE *)DXGGLOBAL::GetGlobal() + 305952) = 1;
          break;
        }
        v32 = DxgEscapeEvictByCriteria((struct _D3DKMT_VIDMM_ESCAPE *)p_Srca);
      }
      goto LABEL_273;
    case D3DKMT_ESCAPE_DRT_TEST:
      if ( v127.PrivateDriverDataSize < 0xC || v127.PrivateDriverDataSize < p_Srca[1] || *p_Srca != 1484026436 )
      {
        WdLogSingleEntry1(3, v127.Type);
        WdLogGlobalForLineNumber = 1675;
        goto LABEL_188;
      }
      if ( !InternalEscapeEnabled() )
      {
        WdLogSingleEntry1(3, v127.Type);
        WdLogGlobalForLineNumber = 1680;
        goto LABEL_326;
      }
      v76 = p_Srca[2];
      if ( (_DWORD)v76 || v127.hAdapter )
      {
        if ( (unsigned int)v76 > 0x34 || (v77 = 0x14001093482000LL, !_bittest64(&v77, v76)) )
        {
          if ( (_DWORD)v76 != 54
            || !(unsigned int)Feature_DisplayMux_PostGA_BugBundle_3__private_IsEnabledDeviceUsageNoInline() )
          {
            v78 = p_Srca[2];
            if ( (unsigned int)v78 > 0x2F || (v79 = 0xA00800000000LL, !_bittest64(&v79, v78)) )
            {
              if ( (_DWORD)v78 != 53
                || !(unsigned int)Feature_DisplayMux_PostGA_BugBundle_3__private_IsEnabledDeviceUsageNoInline() )
              {
                break;
              }
            }
            v39 = DxgkDrtTestEscape(0, (struct _D3DKMT_DRT_ESCAPE_HEAD *)p_Srca, 0);
            if ( v39 < 0 )
              goto LABEL_201;
            if ( v124 == 1 )
            {
LABEL_280:
              RtlCopyToUser(v127.pPrivateDriverData, p_Srca, v127.PrivateDriverDataSize);
              goto LABEL_201;
            }
LABEL_281:
            memmove(v127.pPrivateDriverData, p_Srca, v127.PrivateDriverDataSize);
            goto LABEL_201;
          }
        }
      }
      v32 = DxgkDrtTestEscape(0, (struct _D3DKMT_DRT_ESCAPE_HEAD *)p_Srca, 0);
      goto LABEL_273;
    case D3DKMT_ESCAPE_DIAGNOSTICS:
LABEL_558:
      DiagnosticsBuffer = GetDiagnosticsBuffer(
                            (struct _D3DKMT_DXGK_DIAGNOSTICS *)p_Srca,
                            v127.PrivateDriverDataSize,
                            v127.Type == D3DKMT_ESCAPE_DIAGNOSTICS);
      v39 = DiagnosticsBuffer;
      if ( (int)(DiagnosticsBuffer + 0x80000000) >= 0 && DiagnosticsBuffer != -2147483643 )
        goto LABEL_201;
      if ( v124 == 1 )
        goto LABEL_280;
      goto LABEL_281;
    case D3DKMT_ESCAPE_MIRACAST_DISPLAY_REQUEST:
LABEL_121:
      if ( v127.Type == D3DKMT_ESCAPE_IDD_REQUEST )
        v38 = DxgkHandleIndirectEscape(v127.PrivateDriverDataSize, p_Srca);
      else
        v38 = DxgkHandleMiracastEscape(v127.PrivateDriverDataSize, p_Srca);
      v39 = v38;
      if ( (int)(v38 + 0x80000000) < 0 || v38 == -2147483643 )
      {
        if ( v124 == 1 )
          RtlCopyToUser(v127.pPrivateDriverData, p_Srca, v127.PrivateDriverDataSize);
        else
          memmove(v127.pPrivateDriverData, p_Srca, v127.PrivateDriverDataSize);
      }
      if ( v128[0] )
        DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v128[0]);
      goto LABEL_127;
    case D3DKMT_ESCAPE_FORCE_BDDFALLBACK_HEADLESS:
      if ( g_OSTestSigningEnabled )
      {
        if ( v127.PrivateDriverDataSize != 1 )
          goto LABEL_188;
        byte_140162E5C = *(_BYTE *)p_Srca;
        goto LABEL_206;
      }
LABEL_326:
      DxgkEscape_::_2_::ENSURE_DATA_DELETION::_ENSURE_DATA_DELETION(v128);
      goto LABEL_202;
    case D3DKMT_ESCAPE_REQUEST_MACHINE_CRASH:
      if ( v127.PrivateDriverDataSize != 24 )
        goto LABEL_188;
      ((void (*)(void))DxgkEscape_::_2_::ENSURE_DATA_DELETION::_ENSURE_DATA_DELETION)();
      DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v120);
      if ( v122 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
        McTemplateK0q_EtwWriteTransfer(v70, EventProfilerExit, v71, v120);
      return 3221225473LL;
  }
LABEL_31:
  v133 = 0;
  pPrivateDriverData = 0;
  if ( v127.Type != D3DKMT_ESCAPE_BDD_FALLBACK )
    goto LABEL_32;
  v82 = 0;
  pPrivateDriverData = 0;
  if ( IsCurrentConsoleSession() || IsCurrentProcessAdmin() )
  {
    if ( (unsigned int)Feature_BasicDisplayDeviceEscape_Fix__private_IsEnabledDeviceUsageNoInline() )
    {
      Global = DXGGLOBAL::GetGlobal();
      v82 = DXGGLOBAL::ReferenceBddFallbackAdapter(Global, &v129);
      pPrivateDriverData = v82;
    }
    else
    {
      v84 = DXGGLOBAL::GetGlobal();
      DXGGLOBAL::ReferenceBddFallbackAdapter(v84, &v129);
    }
  }
  if ( v82 )
  {
    v128[1] = v82;
LABEL_32:
    v9 = 0;
    v138 = 0;
    DXGHANDLETABLELOCKSHARED::DXGHANDLETABLELOCKSHARED((DXGHANDLETABLELOCKSHARED *)v148, Current);
    hAdapter = v127.hAdapter;
    if ( !v127.hAdapter )
    {
LABEL_33:
      if ( v9 )
      {
        v11 = 0;
        v134 = 0;
        v142 = 0;
        hDevice = v127.hDevice;
        if ( v127.hDevice )
        {
          v33 = v131;
          if ( ((v127.hDevice >> 6) & 0xFFFFFF) >= *((_DWORD *)v131 + 74) )
          {
            v35 = 0;
          }
          else
          {
            v34 = *(_DWORD *)(*((_QWORD *)v131 + 35) + 16LL * ((v127.hDevice >> 6) & 0xFFFFFF) + 8);
            v35 = ((v127.hDevice >> 25) & 0x60) == (v34 & 0x60) && (v34 & 0x2000) == 0 && (v34 & 0x1F) != 0;
            v33 = v131;
          }
          if ( v35 )
          {
            v36 = *((_QWORD *)v33 + 35);
            if ( (*(_BYTE *)(v36 + 16LL * ((v127.hDevice >> 6) & 0xFFFFFF) + 8) & 0x1F) == 3 )
            {
              v11 = *(_QWORD *)(v36 + 16LL * ((v127.hDevice >> 6) & 0xFFFFFF));
            }
            else
            {
              WdLogSingleEntry0(2);
              WdLogGlobalForLineNumber = 318;
              DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
              v11 = 0;
              hDevice = v127.hDevice;
            }
          }
          else
          {
            v11 = 0;
          }
          v134 = (DXGDEVICE *)v11;
          if ( !v11 || (v142 = v11, v9 != *(_QWORD *)(*(_QWORD *)(v11 + 16) + 16LL)) && v9 != *(_QWORD *)(v11 + 1896) )
          {
            WdLogSingleEntry2(3, v9, hDevice);
            WdLogGlobalForLineNumber = 1974;
LABEL_143:
            DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v148);
LABEL_188:
            DxgkEscape_::_2_::ENSURE_DATA_DELETION::_ENSURE_DATA_DELETION(v128);
LABEL_189:
            DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v120);
            if ( v122 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
              McTemplateK0q_EtwWriteTransfer(v60, EventProfilerExit, v61, v120);
            LODWORD(v16) = -1073741811;
            return (unsigned int)v16;
          }
        }
        v13 = 0;
        v139 = 0;
        hContext = v127.hContext;
        if ( v127.hContext )
        {
          v42 = (v127.hContext >> 6) & 0xFFFFFF;
          v43 = v42;
          v44 = v131;
          if ( v42 >= *((_DWORD *)v131 + 74) )
          {
            v46 = 0;
          }
          else
          {
            v45 = *(_DWORD *)(*((_QWORD *)v131 + 35) + 16LL * v42 + 8);
            v46 = ((v127.hContext >> 25) & 0x60) == (v45 & 0x60) && (v45 & 0x2000) == 0 && (v45 & 0x1F) != 0;
            v44 = v131;
          }
          if ( v46 )
          {
            v47 = 2 * v43;
            v48 = *((_QWORD *)v44 + 35);
            if ( (*(_BYTE *)(v48 + 8 * v47 + 8) & 0x1F) == 7 )
            {
              v13 = *(_QWORD *)(v48 + 8 * v47);
            }
            else
            {
              WdLogSingleEntry0(2);
              WdLogGlobalForLineNumber = 318;
              DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
              v13 = 0;
              hContext = v127.hContext;
            }
          }
          else
          {
            v13 = 0;
          }
          v139 = v13;
          if ( !v13 || !v11 || v11 != *(_QWORD *)(v13 + 16) )
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
          v138 = v9;
        }
        if ( v13 )
          _InterlockedAdd64((volatile signed __int64 *)(v13 + 32), 1u);
        _InterlockedAdd64((volatile signed __int64 *)(v9 + 24), 1u);
        DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v148);
        if ( *(_DWORD *)(v9 + 2408) >= 0x5023u )
        {
          if ( (*(_BYTE *)&v127.Flags.0 & 0x10) != 0 || (v127.Flags.Value & 0xFFFFFF00) != 0 )
          {
            WdLogSingleEntry1(3, v9);
            WdLogGlobalForLineNumber = 2022;
            goto LABEL_188;
          }
          if ( (*(_BYTE *)&v127.Flags.0 & 0x20) != 0 )
          {
            WdLogSingleEntry1(3, v9);
            WdLogGlobalForLineNumber = 2027;
            goto LABEL_188;
          }
        }
        v132[0] = (DXGADAPTER *)v9;
        v132[1] = (DXGADAPTER *)-1LL;
        *(_QWORD *)v125 = v11;
        v126 = v139;
        LODWORD(v16) = DxgkpGetPairingAdapters((struct DXGADAPTER *)v9, 0, &v133, &v145, 0, 0, 0);
        v17 = v133;
        if ( (int)v16 >= 0 )
          DXGADAPTER::ReleaseReference(v133, v15);
        if ( v127.Type != D3DKMT_ESCAPE_VIDMM )
        {
          if ( v127.Type == D3DKMT_ESCAPE_DRT_TEST )
          {
            v85 = p_Srca[2];
            if ( (unsigned int)v85 <= 0x2E )
            {
              v86 = 0x512744204000LL;
              if ( _bittest64(&v86, v85) )
              {
                if ( (_DWORD)v85 == 33 || (_DWORD)v85 == 32 )
                {
                  v39 = -1073741823;
                }
                else
                {
                  v39 = DxgkDrtTestEscape((struct DXGADAPTER *)v9, (struct _D3DKMT_DRT_ESCAPE_HEAD *)p_Srca, 0);
                  if ( v39 >= 0 )
                  {
                    if ( v124 == 1 )
                      RtlCopyToUser(v127.pPrivateDriverData, p_Srca, v127.PrivateDriverDataSize);
                    else
                      memmove(v127.pPrivateDriverData, p_Srca, v127.PrivateDriverDataSize);
                  }
                }
                goto LABEL_200;
              }
            }
          }
LABEL_45:
          COREADAPTERACCESS::COREADAPTERACCESS((COREADAPTERACCESS *)v167, (struct DXGADAPTER *const)v9, 0);
          COREACCESS::COREACCESS((COREACCESS *)v166, pPrivateDriverData, v18);
          LODWORD(v133) = 0;
          v136 = v9;
          v137 = 0;
          if ( v127.Type == D3DKMT_ESCAPE_BDD_FALLBACK )
          {
            COREACCESS::AcquireShared((COREACCESS *)v166, 0);
            goto LABEL_47;
          }
          if ( (*(_BYTE *)&v127.Flags.0 & 1) != 0 )
          {
            if ( v127.Type == D3DKMT_ESCAPE_DRIVERPRIVATE
              || (LOBYTE(v90) = 0, v127.Type == D3DKMT_ESCAPE_VIDSCH) && *p_Srca == 3 )
            {
              LOBYTE(v90) = 1;
            }
            v90 = (unsigned __int8)v90;
            if ( *(_QWORD *)(v9 + 3256) )
              v90 = 1;
            LODWORD(v133) = v90;
            LODWORD(v16) = COREADAPTERACCESS::AcquireExclusive(v167, (unsigned int)(unsigned __int8)v90 + 2, 2);
            if ( (int)v16 < 0 )
              goto LABEL_60;
            if ( !(_BYTE)v133 )
            {
              v74 = *(_QWORD *)(v9 + 3256);
              if ( v74 )
                ADAPTER_RENDER::FlushScheduler(v74, 2, 0xFFFFFFFFLL);
            }
            LODWORD(v133) = 1;
            goto LABEL_47;
          }
          if ( v127.Type == D3DKMT_ESCAPE_DRT_TEST )
          {
            v91 = p_Srca[2];
            if ( v91 != 23 || (v37 = 1, p_Srca[3] - 2 > 1) )
              v37 = 0;
            v130 = v91 == 55;
          }
          else
          {
            v37 = 0;
            v130 = 0;
          }
          v123 = v37;
          if ( v127.Type == D3DKMT_ESCAPE_DRIVERPRIVATE )
          {
            LODWORD(v55) = DXGADAPTER::GetAdapterType((DXGADAPTER *)v9);
            if ( (*v55 & 0x10) != 0
              || *(_BYTE *)&v127.Flags.0 < 0
              || *(_DWORD *)(v9 + 2408) >= 0x5023u && (*(_BYTE *)&v127.Flags.0 & 8) != 0 )
            {
              DXGADAPTERSTOPRESETLOCKSHARED::Acquire((DXGADAPTERSTOPRESETLOCKSHARED *)v135);
              if ( *(_DWORD *)(v9 + 200) != 1 )
              {
LABEL_117:
                LODWORD(v16) = -1073741130;
                goto LABEL_60;
              }
LABEL_47:
              if ( v127.hDevice && *((_DWORD *)v134 + 152) != 1 )
                goto LABEL_117;
              v123 = 1;
              if ( v127.Type == D3DKMT_ESCAPE_DRIVERPRIVATE && (*(_BYTE *)&v127.Flags.0 & 0x40) != 0 )
              {
                if ( !v17 )
                  goto LABEL_348;
                LODWORD(v16) = DxgkpDriverKnownEscape(v131, v17, p_Srca, v127.PrivateDriverDataSize, &v123);
                if ( (int)v16 < 0 )
                  goto LABEL_59;
              }
              if ( v17 && *((_BYTE *)v17 + 209) )
              {
                v9 = (__int64)v17;
                v138 = (__int64)v17;
                if ( v127.Type == D3DKMT_ESCAPE_DRIVERPRIVATE && v123
                  || v127.Type <= (unsigned int)(D3DKMT_ESCAPE_LOG_CODEPOINT_PACKET|D3DKMT_ESCAPE_DRT_TEST)
                  && (v92 = 0x1001000000ALL, _bittest64(&v92, v127.Type))
                  || (v93 = 0, v127.Type == D3DKMT_ESCAPE_ADAPTER_VERIFIER_OPTION) )
                {
                  v93 = 1;
                }
                if ( v127.Type == D3DKMT_ESCAPE_DRT_TEST && p_Srca[2] == 49 )
                {
                  LODWORD(v16) = DxgkDrtTestEscape(
                                   v17,
                                   (struct _D3DKMT_DRT_ESCAPE_HEAD *)p_Srca,
                                   (struct COREADAPTERACCESS *)v167);
                  if ( (int)v16 < 0 )
                    goto LABEL_59;
                  v93 = 1;
                }
                if ( v93 )
                {
                  v125[0] = v127.Type;
                  if ( v139 )
                    LODWORD(v133) = *(_DWORD *)(v139 + 28);
                  else
                    LODWORD(v133) = 0;
                  if ( v134 )
                    v94 = *((_DWORD *)v134 + 118);
                  else
                    v94 = 0;
                  v95 = *((_DWORD *)v17 + 1220);
                  HostProcess = DXGPROCESS::GetHostProcess(v131);
                  v97 = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendEscape(
                          (DXG_GUEST_VIRTUALGPU_VMBUS *)(v9 + 4792),
                          HostProcess,
                          v95,
                          v94,
                          (unsigned int)v133,
                          v125[0],
                          v127.Flags,
                          v127.PrivateDriverDataSize,
                          (unsigned __int8 *)p_Srca);
                  v16 = v97;
                  if ( v97 < 0 )
                  {
                    WdLogSingleEntry1(2, v97);
                    WdLogGlobalForLineNumber = 2411;
                    DxgkLogInternalTriageEvent(
                      0,
                      0x40000,
                      -1,
                      (unsigned int)L"Paravirtualized escape failed: 0x%I64x",
                      v16,
                      0,
                      0,
                      0,
                      0);
                  }
                  goto LABEL_59;
                }
              }
              if ( v127.Type <= D3DKMT_ESCAPE_MODES_PRUNED_OUT )
              {
                if ( v127.Type == D3DKMT_ESCAPE_MODES_PRUNED_OUT )
                {
                  if ( !*(_QWORD *)(v9 + 3248) )
                  {
                    WdLogSingleEntry2(2, v9, -1073741637);
                    WdLogGlobalForLineNumber = 2954;
                    v63 = L"Try to call D3DKMT_ESCAPE_MODES_PRUNED_OUT on a render only adapter 0x%I64x (Status = 0x%I64x)!";
                    goto LABEL_195;
                  }
                  if ( v127.PrivateDriverDataSize >= 8
                    && v127.PrivateDriverDataSize >= 44 * (unsigned __int64)p_Srca[1] + 8 )
                  {
                    InvalidModesForTestPurposes = ADAPTER_DISPLAY::GetInvalidModesForTestPurposes(
                                                    *(ADAPTER_DISPLAY **)(v9 + 3248),
                                                    (struct _D3DKMT_DISPLAYMODELIST *)p_Srca);
                    goto LABEL_88;
                  }
                  goto LABEL_348;
                }
                if ( v127.Type <= D3DKMT_ESCAPE_DEBUG_SNAPSHOT )
                {
                  if ( v127.Type == D3DKMT_ESCAPE_DEBUG_SNAPSHOT )
                  {
                    if ( v127.PrivateDriverDataSize >= 8 )
                    {
                      InvalidModesForTestPurposes = DxgDbgTakeSnapshot(
                                                      p_Srca + 1,
                                                      v127.PrivateDriverDataSize - 4,
                                                      p_Srca);
                      goto LABEL_88;
                    }
                    goto LABEL_348;
                  }
                  if ( v127.Type == D3DKMT_ESCAPE_DRIVERPRIVATE )
                  {
                    memset(&v144, 0, sizeof(v144));
                    if ( v123 )
                    {
                      if ( *(__int64 (__fastcall **)(void *const, const struct _DXGKARG_ESCAPE *))(v9 + 592) == DXGADAPTER::DefaultDdiEscape )
                      {
                        WdLogSingleEntry2(3, v9, -1073741637);
                        WdLogGlobalForLineNumber = 2488;
LABEL_58:
                        LODWORD(v16) = -1073741637;
                        goto LABEL_59;
                      }
                      if ( !v127.PrivateDriverDataSize || !v127.pPrivateDriverData )
                      {
                        LODWORD(v16) = -1073741811;
                        WdLogSingleEntry3(3, v127.PrivateDriverDataSize, v127.pPrivateDriverData, -1073741811);
                        WdLogGlobalForLineNumber = 2479;
                        goto LABEL_59;
                      }
                      if ( v134 )
                        v144.hDevice = (HANDLE)*((_QWORD *)v134 + 77);
                      if ( v139 )
                        v144.hContext = *(HANDLE *)(v139 + 184);
                      else
                        v144.hContext = 0;
                      v144.Flags.Value = v127.Flags.Value;
                      if ( (*(_DWORD *)(v9 + 444) & 8) == 0
                        && *(_DWORD *)(v9 + 420) == 4098
                        && !(unsigned int)IsAMDDriverEscapeAllowed(p_Srca, v127.PrivateDriverDataSize) )
                      {
                        goto LABEL_170;
                      }
                      if ( *(_BYTE *)&v127.Flags.0 < 0 )
                      {
                        LODWORD(v16) = -1073741637;
                        WdLogSingleEntry1(2, -1073741637);
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
                      v25 = v131;
                      IsVmProcessOrVmValidation = DXGPROCESS::IsVmProcessOrVmValidation(v131, (struct DXGADAPTER *)v9);
                      v144.Flags.Value = v144.Flags.Value & 0xFFFFFFDF | (32 * (IsVmProcessOrVmValidation & 1));
                      v144.PrivateDriverDataSize = v127.PrivateDriverDataSize;
                      v144.pPrivateDriverData = p_Srca;
                      v27 = *(_QWORD *)(v9 + 3256);
                      if ( v27 )
                      {
                        KeEnterCriticalRegion();
                        ExAcquirePushLockSharedEx(v27 + 72, 0);
                        _InterlockedAdd((volatile signed __int32 *)(v27 + 88), 1u);
                        RenderAdapterInfo = DXGPROCESS::GetRenderAdapterInfo(v25, *(_DWORD *)(v9 + 240));
                        if ( RenderAdapterInfo )
                          v144.hKmdProcessHandle = (HANDLE)*((_QWORD *)RenderAdapterInfo + 6);
                        _InterlockedDecrement((volatile signed __int32 *)(v27 + 88));
                        ExReleasePushLockSharedEx(v27 + 72, 0);
                        KeLeaveCriticalRegion();
                      }
                      v29 = &v144;
                      v30 = (DXGADAPTER *)v9;
                      goto LABEL_87;
                    }
LABEL_394:
                    LODWORD(v16) = 0;
                    goto LABEL_119;
                  }
                  if ( v127.Type != D3DKMT_ESCAPE_VIDMM )
                  {
                    if ( v127.Type == D3DKMT_ESCAPE_TDRDBGCTRL )
                    {
                      if ( !v127.pPrivateDriverData )
                        goto LABEL_415;
                      if ( v127.PrivateDriverDataSize < 4 )
                        goto LABEL_233;
                      if ( *p_Srca )
                      {
                        switch ( *p_Srca )
                        {
                          case 1u:
                            v104 = 2;
                            break;
                          case 2u:
                            v104 = 1;
                            break;
                          case 3u:
                            v104 = 3;
                            break;
                          case 4u:
                          case 5u:
                            if ( !v17 )
                            {
                              *(_QWORD *)(WdLogNewEntry5_WdTrace() + 24) = 0;
                              WdLogGlobalForLineNumber = 2697;
                              goto LABEL_58;
                            }
                            if ( *((_BYTE *)v17 + 209) )
                            {
LABEL_170:
                              LODWORD(v16) = -1073741637;
                              goto LABEL_60;
                            }
                            LODWORD(v16) = TdrDbgCtrl(4);
                            if ( (int)v16 < 0 )
                              goto LABEL_59;
                            v103 = *(struct _VIDSCH_GLOBAL **)(*((_QWORD *)v17 + 407) + 744LL);
                            memset(v169, 0, sizeof(v169));
                            LODWORD(v169[0]) = 2;
                            DWORD1(v169[0]) = *p_Srca;
                            v101 = *((_QWORD *)v17 + 407);
                            v102 = (struct _D3DKMT_VIDSCH_ESCAPE *)v169;
                            goto LABEL_396;
                          case 6u:
                            v104 = 5;
                            break;
                          case 7u:
                            v104 = 6;
                            break;
                          case 8u:
                            if ( v127.PrivateDriverDataSize >= 8 )
                            {
                              if ( !v17 )
                              {
                                *(_QWORD *)(WdLogNewEntry5_WdTrace() + 24) = v9;
                                WdLogGlobalForLineNumber = 2735;
                                goto LABEL_58;
                              }
                              if ( *((_BYTE *)v17 + 209) )
                                goto LABEL_170;
                              LODWORD(v16) = TdrDbgCtrl(4);
                              if ( (int)v16 < 0 )
                                goto LABEL_59;
                              v103 = *(struct _VIDSCH_GLOBAL **)(*((_QWORD *)v17 + 407) + 744LL);
                              memset(v168, 0, sizeof(v168));
                              LODWORD(v168[0]) = 2;
                              *(_QWORD *)((char *)v168 + 4) = *(_QWORD *)p_Srca;
                              v101 = *((_QWORD *)v17 + 407);
                              v102 = (struct _D3DKMT_VIDSCH_ESCAPE *)v168;
                              goto LABEL_396;
                            }
LABEL_348:
                            LODWORD(v16) = -1073741811;
LABEL_60:
                            DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v135);
                            COREACCESS::~COREACCESS((COREACCESS *)v166);
                            COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v167);
                            ENSURE_CONTEXT_DEREFERENCE::~ENSURE_CONTEXT_DEREFERENCE((ENSURE_CONTEXT_DEREFERENCE *)&v126);
                            v21 = (ADAPTER_RENDER **)v134;
                            if ( v134
                              && _InterlockedExchangeAdd64((volatile signed __int64 *)v134 + 8, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
                            {
                              ADAPTER_RENDER::DestroyDeviceNoLocks(v21[2], (struct DXGDEVICE *)v21);
                            }
                            if ( v132[0] )
                              DXGADAPTER::ReleaseReference(v132[0], v20);
                            if ( v128[0] )
                              DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v128[0]);
                            if ( v128[1] )
                              DXGADAPTER::ReleaseReference(v128[1], v20);
                            goto LABEL_69;
                          default:
                            goto LABEL_233;
                        }
                      }
                      else
                      {
LABEL_415:
                        v104 = 0;
                      }
                      InvalidModesForTestPurposes = TdrDbgCtrl(v104);
                      goto LABEL_88;
                    }
                    if ( v127.Type != D3DKMT_ESCAPE_VIDSCH )
                    {
                      if ( v127.Type == D3DKMT_ESCAPE_DEVICE )
                      {
                        if ( v127.PrivateDriverDataSize >= 0xC && v134 )
                        {
                          InvalidModesForTestPurposes = DXGDEVICE::Escape(v134, (struct _D3DKMT_DEVICE_ESCAPE *)p_Srca);
                          goto LABEL_88;
                        }
                      }
                      else
                      {
                        if ( v127.Type != D3DKMT_ESCAPE_DMM )
                        {
LABEL_375:
                          LODWORD(v16) = -1073741811;
                          WdLogSingleEntry1(3, v127.Type);
                          WdLogGlobalForLineNumber = 3377;
                          goto LABEL_59;
                        }
                        if ( !*(_QWORD *)(v9 + 3248) )
                        {
                          WdLogSingleEntry2(2, v9, -1073741637);
                          WdLogGlobalForLineNumber = 2504;
                          v63 = L"Try to call D3DKMT_ESCAPE_DMM on a render only adapter 0x%I64x (Status = 0x%I64x)!";
LABEL_195:
                          DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v63, v9, -1073741637, 0, 0, 0);
                          goto LABEL_196;
                        }
                        if ( v127.PrivateDriverDataSize >= 0x80 )
                        {
                          v98 = *((_QWORD *)p_Srca + 1);
                          if ( v98 <= 0x19000 && (v127.PrivateDriverDataSize == v98 + 127 || !v98) )
                          {
                            InvalidModesForTestPurposes = DmmEscape(
                                                            (struct DXGADAPTER *const)v9,
                                                            (struct _D3DKMT_DMM_ESCAPE_INTERNAL *const)p_Srca);
                            goto LABEL_88;
                          }
                        }
                      }
LABEL_233:
                      LODWORD(v16) = -1073741811;
                      goto LABEL_59;
                    }
                    if ( !v17 )
                    {
                      WdLogSingleEntry2(2, v9, -1073741637);
                      WdLogGlobalForLineNumber = 2594;
                      v63 = L"Try to call D3DKMT_ESCAPE_VIDSCH on a display only adapter 0x%I64x (Status = 0x%I64x)!";
                      goto LABEL_195;
                    }
                    if ( !*((_BYTE *)v17 + 209) )
                    {
                      if ( *p_Srca != 2 )
                      {
                        if ( *p_Srca == 3 )
                        {
                          if ( (_DWORD)v133 )
                          {
                            Interval.QuadPart = 0;
                            v99 = 5000000;
                            if ( p_Srca[1] < 0x4C4B40 )
                              v99 = p_Srca[1];
                            Interval.QuadPart = -(__int64)v99;
                            KeDelayExecutionThread(0, 0, &Interval);
                            goto LABEL_394;
                          }
                          goto LABEL_233;
                        }
                        v101 = *((_QWORD *)v17 + 407);
                        v102 = (struct _D3DKMT_VIDSCH_ESCAPE *)p_Srca;
                        v103 = *(struct _VIDSCH_GLOBAL **)(v101 + 744);
LABEL_396:
                        InvalidModesForTestPurposes = VIDSCH_EXPORT::VidSchEscape(
                                                        *(VIDSCH_EXPORT **)(v101 + 736),
                                                        v103,
                                                        v102);
                        goto LABEL_88;
                      }
                      goto LABEL_348;
                    }
                    goto LABEL_196;
                  }
                  if ( !v17 )
                  {
                    WdLogSingleEntry2(2, v9, -1073741637);
                    WdLogGlobalForLineNumber = 2532;
                    v63 = L"Try to call D3DKMT_ESCAPE_VIDMM on a display only adapter 0x%I64x (Status = 0x%I64x)!";
                    goto LABEL_195;
                  }
                  if ( v134 )
                    v105 = *((_QWORD *)v134 + 99);
                  else
                    v105 = 0;
                  if ( *p_Srca == 16 )
                  {
                    v106 = p_Srca + 6;
                    LODWORD(v16) = DxgkpEscapeVidMmDelayExecution(
                                     v134,
                                     p_Srca[3],
                                     p_Srca[2],
                                     p_Srca[4],
                                     (unsigned __int64 *)p_Srca + 3);
                    if ( (int)v16 >= 0 )
                    {
                      pPrivateDriverData = (struct DXGADAPTER *)v127.pPrivateDriverData;
                      if ( v124 == 1 )
                        RtlWriteULong64ToUser((char *)v127.pPrivateDriverData + 24, *v106);
                      else
                        *((_QWORD *)v127.pPrivateDriverData + 3) = *v106;
                    }
LABEL_59:
                    if ( (int)v16 < 0 )
                      goto LABEL_60;
LABEL_119:
                    if ( v124 == 1 )
                      RtlCopyToUser(v127.pPrivateDriverData, p_Srca, v127.PrivateDriverDataSize);
                    else
                      memmove(v127.pPrivateDriverData, p_Srca, v127.PrivateDriverDataSize);
                    goto LABEL_60;
                  }
                  LOBYTE(v19) = (_BYTE)v133;
                  InvalidModesForTestPurposes = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned int *, __int64))(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v17 + 407) + 760LL) + 8LL) + 32LL))(
                                                  *(_QWORD *)(*((_QWORD *)v17 + 407) + 768LL),
                                                  v105,
                                                  p_Srca,
                                                  v19);
LABEL_88:
                  LODWORD(v16) = InvalidModesForTestPurposes;
                  goto LABEL_59;
                }
                switch ( v127.Type )
                {
                  case D3DKMT_ESCAPE_DRT_TEST:
                    InvalidModesForTestPurposes = DxgkDrtTestEscape(
                                                    (struct DXGADAPTER *)v9,
                                                    (struct _D3DKMT_DRT_ESCAPE_HEAD *)p_Srca,
                                                    (struct COREADAPTERACCESS *)v167);
                    goto LABEL_88;
                  case D3DKMT_ESCAPE_OUTPUTDUPL_SNAPSHOT:
                    if ( !*(_QWORD *)(v9 + 3248) )
                    {
                      WdLogSingleEntry2(2, v9, -1073741637);
                      WdLogGlobalForLineNumber = 2812;
                      v63 = L"Try to call D3DKMT_ESCAPE_OUTPUTDUPL_SNAPSHOT on a render only adapter 0x%I64x (Status = 0x%I64x)!";
                      goto LABEL_195;
                    }
                    if ( v127.PrivateDriverDataSize >= 0x18 && v127.PrivateDriverDataSize == *p_Srca )
                    {
                      InvalidModesForTestPurposes = OutputDuplGetDebugInfo(
                                                      (struct DXGADAPTER *)v9,
                                                      (struct _D3DKMT_OUTPUTDUPL_SNAPSHOT *)p_Srca);
                      goto LABEL_88;
                    }
                    goto LABEL_348;
                  case D3DKMT_ESCAPE_OUTPUTDUPL_DIAGNOSTICS:
                    if ( !*(_QWORD *)(v9 + 3248) )
                    {
                      WdLogSingleEntry2(2, v9, -1073741637);
                      WdLogGlobalForLineNumber = 2845;
                      v63 = L"Try to call D3DKMT_ESCAPE_OUTPUTDUPL_DIAGNOSTICS on a render only adapter 0x%I64x (Status = 0x%I64x)!";
                      goto LABEL_195;
                    }
                    if ( v127.PrivateDriverDataSize >= 8 && v127.PrivateDriverDataSize == p_Srca[1] + 8LL )
                    {
                      InvalidModesForTestPurposes = OutputDuplGetDiagnosticBuffer((struct DXGADAPTER *)v9);
                      goto LABEL_88;
                    }
                    goto LABEL_348;
                  case D3DKMT_ESCAPE_BDD_PNP:
                    if ( (*(_DWORD *)(v9 + 444) & 0x20) == 0 || DXGADAPTER::IsBddFallbackDriver((DXGADAPTER *)v9) )
                    {
                      LODWORD(v16) = -1071775742;
                      goto LABEL_59;
                    }
                    v159 = 0;
                    v162 = 0;
                    v164 = 0;
                    v157 = 0;
                    v163 = 0;
                    Value = (struct _D3DDDI_ESCAPEFLAGS::$DB860278E5E511C34FE0F76D94154466::$9A2C51F7B5B2EC690ABA117774D32C3A)v127.Flags.Value;
                    v161 = v127.PrivateDriverDataSize;
                    v160 = p_Srca;
                    v29 = (_DXGKARG_ESCAPE *)&v157;
                    break;
                  case D3DKMT_ESCAPE_BDD_FALLBACK:
                    v107 = pPrivateDriverData;
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
                    v151 = 0;
                    v154 = 0;
                    v156 = 0;
                    v149 = 0;
                    v155 = 0;
                    v150 = (struct _D3DDDI_ESCAPEFLAGS::$DB860278E5E511C34FE0F76D94154466::$9A2C51F7B5B2EC690ABA117774D32C3A)v127.Flags.Value;
                    v153 = v127.PrivateDriverDataSize;
                    v152 = p_Srca;
                    v29 = (_DXGKARG_ESCAPE *)&v149;
                    v30 = v107;
                    break;
                  case D3DKMT_ESCAPE_ACTIVATE_SPECIFIC_DIAG:
                    if ( v127.PrivateDriverDataSize != 8 )
                      goto LABEL_348;
                    if ( *p_Srca )
                    {
                      if ( *p_Srca == 15 )
                      {
                        v62 = *(ADAPTER_DISPLAY **)(v9 + 3248);
                        if ( v62 )
                        {
                          InvalidModesForTestPurposes = ADAPTER_DISPLAY::ActivateStoringInvalidModesForTestPurposes(
                                                          v62,
                                                          p_Srca[1]);
                          goto LABEL_88;
                        }
                        WdLogSingleEntry2(2, v9, -1073741637);
                        WdLogGlobalForLineNumber = 2925;
                        v63 = L"Try to activate D3DKMT_ESCAPE_MODES_PRUNED_OUT on a render only adapter 0x%I64x (Status = 0x%I64x)!";
                        goto LABEL_195;
                      }
                      WdLogSingleEntry1(1, (int)*p_Srca);
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
                    LODWORD(v16) = 0;
                    goto LABEL_59;
                  default:
                    goto LABEL_375;
                }
LABEL_87:
                InvalidModesForTestPurposes = DXGADAPTER::DdiEscape(v30, v29);
                goto LABEL_88;
              }
              if ( v127.Type <= D3DKMT_ESCAPE_ADAPTER_VERIFIER_OPTION )
              {
                if ( v127.Type != D3DKMT_ESCAPE_ADAPTER_VERIFIER_OPTION )
                {
                  switch ( v127.Type )
                  {
                    case D3DKMT_ESCAPE_WHQL_INFO:
                      if ( v127.PrivateDriverDataSize >= 4 )
                      {
                        *p_Srca = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v9 + 216) + 64LL) + 2744LL);
                        goto LABEL_394;
                      }
                      goto LABEL_348;
                    case D3DKMT_ESCAPE_BRIGHTNESS:
                      if ( (*(_BYTE *)&v127.Flags.0 & 1) == 0 || v127.PrivateDriverDataSize < 0x60C )
                        goto LABEL_348;
                      if ( DXGPROCESS::IsRemoteConnection(v131) )
                      {
                        LODWORD(v16) = -1073741790;
                        WdLogSingleEntry2(3, v9, -1073741790);
                        WdLogGlobalForLineNumber = 3012;
                        goto LABEL_59;
                      }
                      InvalidModesForTestPurposes = DpiBrightnessEscape(
                                                      *(struct _DEVICE_OBJECT **)(v9 + 216),
                                                      (struct _D3DKMT_BRIGHTNESS_INFO *)p_Srca);
                      goto LABEL_88;
                    case D3DKMT_ESCAPE_EDID_CACHE:
                      if ( v127.PrivateDriverDataSize < 4 || v127.PrivateDriverDataSize != *p_Srca + 4LL )
                        goto LABEL_233;
                      if ( !IsCurrentConsoleSession() && !IsCurrentProcessAdmin() )
                      {
                        memset(p_Srca, 0, v127.PrivateDriverDataSize);
                        goto LABEL_59;
                      }
                      InvalidModesForTestPurposes = (*(__int64 (__fastcall **)(DxgMonitor::EDIDCACHE *, unsigned int *))(*(_QWORD *)DxgMonitor::EDIDCACHE::s_pEdidCache + 16LL))(
                                                      DxgMonitor::EDIDCACHE::s_pEdidCache,
                                                      p_Srca);
                      goto LABEL_88;
                    case D3DKMT_ESCAPE_HISTORY_BUFFER_STATUS:
                      if ( v127.PrivateDriverDataSize >= 8 )
                      {
                        if ( v17 )
                        {
                          v110 = v134;
                          if ( v134 )
                          {
                            v111 = 0;
                            if ( (qword_1401604F0 & 0x461C8ED7) != 0
                              && (qword_1401604F8 & 0xFFFFFFFFB9E37128uLL) == 0
                              && (qword_1401604F0 & 0x4000) != 0 )
                            {
                              while ( 1 )
                              {
                                NumDifferentPhysicalAdapters = DXGADAPTER::GetNumDifferentPhysicalAdapters(v17);
                                if ( v113 >= NumDifferentPhysicalAdapters )
                                  break;
                                if ( *(_QWORD *)(352LL * v113
                                               + *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v17 + 407) + 16LL) + 3120LL)
                                               + 40) )
                                {
                                  v111 = 1;
                                  break;
                                }
                              }
                            }
                            *((_BYTE *)v110 + 1912) = v111;
                            *(_BYTE *)p_Srca = v111;
                            p_Srca[1] = 0;
                            goto LABEL_394;
                          }
                        }
                      }
                      break;
                    case D3DKMT_ESCAPE_MIRACAST_ADAPTER_DIAG_INFO:
                      if ( v127.PrivateDriverDataSize == 32 )
                      {
                        if ( !DXGADAPTER::IsDiagnosticAllowed((DXGADAPTER *)v9) )
                        {
                          CurrentProcessSessionId = PsGetCurrentProcessSessionId();
                          WdLogSingleEntry2(3, v9, CurrentProcessSessionId);
                          WdLogGlobalForLineNumber = 3071;
                          LODWORD(v16) = -1073741790;
                          goto LABEL_59;
                        }
                        DxgkGetAdapterMiracastInfo(*(_QWORD *)(v9 + 216), p_Srca);
                        goto LABEL_394;
                      }
                      goto LABEL_348;
                    case D3DKMT_ESCAPE_PROCESS_VERIFIER_OPTION:
                      if ( v127.PrivateDriverDataSize >= 0x20 )
                      {
                        v108 = p_Srca[3];
                        if ( v108 <= 1 && !*(_QWORD *)p_Srca )
                        {
                          if ( !v108 )
                            *((_OWORD *)p_Srca + 1) = 0;
                          if ( p_Srca[2] == 1000 || p_Srca[2] == 1001 )
                          {
                            if ( v17 )
                            {
                              InvalidModesForTestPurposes = VIDMM_EXPORT::VidMmProcessVerifierOption(
                                                              *(VIDMM_EXPORT **)(*((_QWORD *)v17 + 407) + 760LL),
                                                              *(struct VIDMM_GLOBAL **)(*((_QWORD *)v17 + 407) + 768LL),
                                                              v131,
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
                if ( v127.PrivateDriverDataSize < 0x30 || (v114 = p_Srca[1], v114 > 1) )
                {
LABEL_186:
                  DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v135);
                  COREACCESS::~COREACCESS((COREACCESS *)v166);
                  COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v167);
LABEL_187:
                  ENSURE_CONTEXT_DEREFERENCE::~ENSURE_CONTEXT_DEREFERENCE((ENSURE_CONTEXT_DEREFERENCE *)&v126);
                  ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v125);
                  DXGADAPTERBYHANDLE::~DXGADAPTERBYHANDLE((DXGADAPTERBYHANDLE *)v132);
                  goto LABEL_188;
                }
                if ( !v114 )
                {
                  *(_OWORD *)(p_Srca + 2) = 0;
                  *(_OWORD *)(p_Srca + 6) = 0;
                  *((_QWORD *)p_Srca + 5) = 0;
                }
                if ( *p_Srca == 1000 || *p_Srca - 1001 < 2 )
                {
                  if ( v17 )
                  {
                    if ( !*((_BYTE *)v17 + 209) )
                    {
                      InvalidModesForTestPurposes = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v17 + 407) + 760LL) + 8LL)
                                                                                              + 1072LL))(
                                                      *(_QWORD *)(*((_QWORD *)v17 + 407) + 768LL),
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
                WdLogSingleEntry1(2, (int)*p_Srca);
                WdLogGlobalForLineNumber = 3233;
                v115 = (int)*p_Srca;
                v116 = L"Unknown verifier Type for D3DKMT_ESCAPE_ADAPTER_VERIFIER_OPTION, Type=%d";
LABEL_520:
                DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v116, v115, 0, 0, 0, 0);
                goto LABEL_186;
              }
              switch ( v127.Type )
              {
                case D3DKMT_ESCAPE_DOD_SET_DIRTYRECT_MODE:
                  if ( v127.PrivateDriverDataSize == 4 )
                  {
                    if ( !*(_QWORD *)(v9 + 3256) )
                    {
                      v75 = *(_QWORD *)(v9 + 3248);
                      if ( !*(_QWORD *)(v75 + 464) )
                        goto LABEL_233;
                      *(_DWORD *)(v75 + 472) = *p_Srca;
                      goto LABEL_235;
                    }
                    WdLogSingleEntry1(3, v9);
                    WdLogGlobalForLineNumber = 3251;
                    goto LABEL_186;
                  }
                  WdLogSingleEntry1(2, v127.PrivateDriverDataSize);
                  WdLogGlobalForLineNumber = 3244;
                  v115 = v127.PrivateDriverDataSize;
                  v116 = L"Supplied Buffer size for D3DKMT_ESCAPE_DOD_SET_DIRTYRECT_MODE (0x%I64x) was not the correct size";
                  goto LABEL_520;
                case D3DKMT_ESCAPE_GET_DISPLAY_CONFIGURATIONS:
                  if ( DXGADAPTER::IsFullWDDMAdapter((DXGADAPTER *)v9) )
                  {
                    InvalidModesForTestPurposes = ADAPTER_DISPLAY::ReportDisplayState(
                                                    *(ADAPTER_DISPLAY **)(v9 + 3248),
                                                    (struct _D3DKMT_DXGK_DIAGNOSTICS *)p_Srca,
                                                    v127.PrivateDriverDataSize);
                    goto LABEL_88;
                  }
                  WdLogSingleEntry1(3, v9);
                  WdLogGlobalForLineNumber = 3265;
                  goto LABEL_186;
                case D3DKMT_ESCAPE_QUERY_IOMMU_STATUS:
                  if ( !v127.PrivateDriverDataSize )
                  {
                    WdLogSingleEntry1(2, 0);
                    WdLogGlobalForLineNumber = 3281;
                    v115 = v127.PrivateDriverDataSize;
                    v116 = L"Supplied Buffer size for D3DKMT_ESCAPE_QUERY_IOMMU_STATUS (0x%I64x) was to small";
                    goto LABEL_520;
                  }
                  if ( !v17 )
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
                  if ( !*((_BYTE *)v17 + 209) )
                  {
                    LODWORD(v133) = 0;
                    SysMmQueryIommuState(*((const struct SYSMM_ADAPTER **)v17 + 28), (union SYSMM_IOMMU_STATE *)&v133);
                    LOBYTE(v100) = (_BYTE)v133;
                    goto LABEL_393;
                  }
                  break;
                case D3DKMT_ESCAPE_QUERY_IOMMU_STATUS|D3DKMT_ESCAPE_TDRDBGCTRL:
                  if ( !v127.PrivateDriverDataSize )
                  {
                    WdLogSingleEntry1(2, 0);
                    WdLogGlobalForLineNumber = 3312;
                    v115 = v127.PrivateDriverDataSize;
                    v116 = L"Supplied Buffer size for D3DKMT_ESCAPE_QUERY_DMA_REMAPPING_STATUS (0x%I64x) was to small";
                    goto LABEL_520;
                  }
                  if ( !v17 )
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
                  if ( !*((_BYTE *)v17 + 209) )
                  {
                    LODWORD(v133) = 0;
                    SysMmQueryIommuState(*((const struct SYSMM_ADAPTER **)v17 + 28), (union SYSMM_IOMMU_STATE *)&v133);
                    v100 = (unsigned int)v133 >> 1;
LABEL_393:
                    *(_BYTE *)p_Srca = v100 & 1;
                    goto LABEL_394;
                  }
                  break;
                case D3DKMT_ESCAPE_LOG_CODEPOINT_PACKET|D3DKMT_ESCAPE_DRT_TEST:
                  if ( v127.PrivateDriverDataSize >= 0xC )
                  {
                    if ( !v17 )
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
                    v117 = *p_Srca;
                    if ( (unsigned int)v117 < *((_DWORD *)v17 + 74) )
                    {
                      v118 = *((_QWORD *)v17 + 390);
                      p_Srca[1] = *(unsigned __int16 *)(352 * v117 + v118);
                      p_Srca[2] = *(unsigned __int16 *)(352 * v117 + v118 + 2);
                      if ( v127.PrivateDriverDataSize >= 0x10 )
                        p_Srca[3] = -((*((_BYTE *)v17 + 2580) & 4) == 0);
                      goto LABEL_394;
                    }
                    goto LABEL_186;
                  }
                  WdLogSingleEntry1(2, v127.PrivateDriverDataSize);
                  WdLogGlobalForLineNumber = 3343;
                  v115 = v127.PrivateDriverDataSize;
                  v116 = L"Supplied Buffer size for D3DKMT_QUERY_PHYSICAL_ADAPTER (0x%I64x) was to small";
                  goto LABEL_520;
                default:
                  goto LABEL_375;
              }
LABEL_196:
              DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v135);
              COREACCESS::~COREACCESS((COREACCESS *)v166);
              COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v167);
              ENSURE_CONTEXT_DEREFERENCE::~ENSURE_CONTEXT_DEREFERENCE((ENSURE_CONTEXT_DEREFERENCE *)&v126);
              ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v125);
              DXGADAPTERBYHANDLE::~DXGADAPTERBYHANDLE((DXGADAPTERBYHANDLE *)v132);
              DxgkEscape_::_2_::ENSURE_DATA_DELETION::_ENSURE_DATA_DELETION(v128);
              DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v120);
              if ( v122 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
                McTemplateK0q_EtwWriteTransfer(v64, EventProfilerExit, v65, v120);
              return 3221225659LL;
            }
            v37 = v123;
          }
          if ( !v37 && !v130 )
          {
            LODWORD(v16) = COREADAPTERACCESS::AcquireShared((COREADAPTERACCESS *)v167, 0);
            if ( (int)v16 < 0 )
              goto LABEL_60;
          }
          goto LABEL_47;
        }
        if ( !v17 )
        {
          WdLogSingleEntry0(3);
          WdLogGlobalForLineNumber = 2193;
          goto LABEL_187;
        }
        if ( *p_Srca == 9 )
        {
          if ( !p_Srca[4] && !(unsigned __int8)DxgkpIsDrtEnabled((unsigned int)(v127.Type - 1)) )
          {
            WdLogSingleEntry0(3);
            WdLogGlobalForLineNumber = 2173;
            ENSURE_CONTEXT_DEREFERENCE::~ENSURE_CONTEXT_DEREFERENCE((ENSURE_CONTEXT_DEREFERENCE *)&v126);
            ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v125);
            DXGADAPTERBYHANDLE::~DXGADAPTERBYHANDLE((DXGADAPTERBYHANDLE *)v132);
            goto LABEL_326;
          }
          v87 = (void *)*((_QWORD *)p_Srca + 1);
          *((_QWORD *)p_Srca + 1) = 0;
          v88 = DxgEscapeSuspendResumeProcess(&v127, p_Srca, v17, v87, 1, p_Srca[4] != 0);
        }
        else
        {
          if ( *p_Srca != 10 )
            goto LABEL_45;
          v89 = (void *)*((_QWORD *)p_Srca + 1);
          *((_QWORD *)p_Srca + 1) = 0;
          v88 = DxgEscapeSuspendResumeProcess(&v127, p_Srca, v17, v89, 0, 0);
        }
        v39 = v88;
LABEL_200:
        ENSURE_CONTEXT_DEREFERENCE::~ENSURE_CONTEXT_DEREFERENCE((ENSURE_CONTEXT_DEREFERENCE *)&v126);
        ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v125);
        DXGADAPTERBYHANDLE::~DXGADAPTERBYHANDLE((DXGADAPTERBYHANDLE *)v132);
LABEL_201:
        DxgkEscape_::_2_::ENSURE_DATA_DELETION::_ENSURE_DATA_DELETION(v128);
LABEL_127:
        DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v120);
        if ( v122 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
          McTemplateK0q_EtwWriteTransfer(v40, EventProfilerExit, v41, v120);
        return (unsigned int)v39;
      }
      LODWORD(v16) = -1073741811;
      WdLogSingleEntry2(3, hAdapter, -1073741811);
      WdLogGlobalForLineNumber = 1957;
      DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v148);
      goto LABEL_250;
    }
    v49 = (v127.hAdapter >> 6) & 0xFFFFFF;
    v50 = v127.hAdapter >> 30;
    v51 = v131;
    if ( (*((_DWORD *)v131 + 102) & 0x100) != 0 )
    {
      v142 = *((_QWORD *)v131 + 75);
      v138 = v142 + 248;
      DXGPUSHLOCK::AcquireShared((DXGPUSHLOCK *)(v142 + 248));
      if ( v49 < *(_DWORD *)(v142 + 296)
        && (v56 = *(_DWORD *)(*(_QWORD *)(v142 + 280) + 16LL * v49 + 8), v50 == ((v56 >> 5) & 3))
        && (v56 & 0x2000) == 0
        && (v56 & 0x1F) != 0 )
      {
        v58 = *(_QWORD *)(v142 + 280);
        if ( (*(_BYTE *)(v58 + 16LL * v49 + 8) & 0x1F) == 1 )
        {
          v9 = *(_QWORD *)(v58 + 16LL * v49);
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
      v59 = v138;
      _InterlockedDecrement((volatile signed __int32 *)(v138 + 16));
      ExReleasePushLockSharedEx(v59, 0);
      KeLeaveCriticalRegion();
    }
    else
    {
      if ( v49 >= *((_DWORD *)v131 + 74) )
      {
        v53 = 0;
      }
      else
      {
        v52 = *(_DWORD *)(*((_QWORD *)v131 + 35) + 16LL * ((v127.hAdapter >> 6) & 0xFFFFFF) + 8);
        v53 = v50 == ((v52 >> 5) & 3) && (v52 & 0x2000) == 0 && (v52 & 0x1F) != 0;
        v51 = v131;
      }
      if ( !v53 )
      {
        v9 = 0;
        goto LABEL_156;
      }
      v54 = *((_QWORD *)v51 + 35);
      if ( (*(_BYTE *)(v54 + 16LL * ((v127.hAdapter >> 6) & 0xFFFFFF) + 8) & 0x1F) == 1 )
      {
        v9 = *(_QWORD *)(v54 + 16LL * ((v127.hAdapter >> 6) & 0xFFFFFF));
        goto LABEL_156;
      }
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 318;
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
      v9 = 0;
    }
    hAdapter = v127.hAdapter;
LABEL_156:
    v138 = v9;
    goto LABEL_33;
  }
  DxgkEscape_::_2_::ENSURE_DATA_DELETION::_ENSURE_DATA_DELETION(v128);
  DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v120);
  if ( v122 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
    McTemplateK0q_EtwWriteTransfer(v72, EventProfilerExit, v73, v120);
  return 3221226021LL;
}

```

## disassembly

```asm
0x14035a530  mov     [rsp+arg_8], rbx
0x14035a535  mov     [rsp+arg_10], rsi
0x14035a53a  push    rdi
0x14035a53b  push    r12
0x14035a53d  push    r13
0x14035a53f  push    r14
0x14035a541  push    r15
0x14035a543  sub     rsp, 550h
0x14035a54a  mov     rax, cs:__security_cookie
0x14035a551  xor     rax, rsp
0x14035a554  mov     [rsp+578h+var_38], rax
0x14035a55c  mov     rbx, rcx
0x14035a55f  mov     [rsp+578h+var_528], 0FFFFFFFFh
0x14035a567  xor     edi, edi
0x14035a569  mov     [rsp+578h+var_520], rdi
0x14035a56e  mov     rax, cs:qword_1401604F0
0x14035a575  lea     r14d, [rdi+1]
0x14035a579  test    al, 2
0x14035a57b  jnz     short loc_14035A584
0x14035a57d  mov     [rsp+578h+var_518], dil
0x14035a582  jmp     short loc_14035A59E
0x14035a584  mov     [rsp+578h+var_518], r14b
0x14035a589  mov     [rsp+578h+var_528], 7E0h
0x14035a591  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, r14b
0x14035a598  jnz     loc_14035B798
0x14035a59e  mov     edx, 7E0h
0x14035a5a3  lea     rcx, [rsp+578h+var_528]
0x14035a5a8  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x14035a5ad  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x14035a5b2  mov     r12, rax
0x14035a5b5  mov     [rsp+578h+var_4B8], rax
0x14035a5bd  xorps   xmm0, xmm0
0x14035a5c0  movups  xmmword ptr [rsp+578h+var_4F8.hAdapter], xmm0
0x14035a5c8  movups  xmmword ptr [rsp+578h+var_4F8.pPrivateDriverData], xmm0
0x14035a5d0  call    cs:__imp_PsGetCurrentThreadPreviousMode
0x14035a5d7  nop     dword ptr [rax+rax+00h]
0x14035a5dc  mov     [rsp+578h+var_50F], al
0x14035a5e0  test    r12, r12
0x14035a5e3  jz      loc_14035B7AF
0x14035a5e9  cmp     al, r14b
0x14035a5ec  jnz     loc_14035B809
0x14035a5f2  mov     r8d, 20h ; ' '; Size
0x14035a5f8  mov     rdx, rbx; Src
0x14035a5fb  lea     rcx, [rsp+578h+var_4F8]; void *
0x14035a603  call    RtlCopyFromUser
0x14035a608  jmp     short loc_14035A63F
0x14035a60a  lea     rcx, [rsp+578h+var_528]; this
0x14035a60f  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x14035a614  cmp     [rsp+578h+var_518], 0
0x14035a619  jz      short loc_14035A635
0x14035a61b  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x14035a622  jz      short loc_14035A635
0x14035a624  mov     r9d, [rsp+578h+var_528]
0x14035a629  lea     rdx, EventProfilerExit
0x14035a630  call    McTemplateK0q_EtwWriteTransfer
0x14035a635  mov     eax, 0C000000Dh
0x14035a63a  jmp     loc_14035D392
0x14035a63f  cmp     [rsp+578h+var_4F8.Type], 405h
0x14035a64a  jz      loc_14035B825
0x14035a650  cmp     [rsp+578h+var_4F8.Type], 400h
0x14035a65b  jge     loc_14035B27E
0x14035a661  mov     ecx, [rsp+578h+var_4F8.Type]
0x14035a668  sub     ecx, 1
0x14035a66b  jz      loc_14035B843
0x14035a671  sub     ecx, 2
0x14035a674  jz      loc_14035B843
0x14035a67a  sub     ecx, 19h
0x14035a67d  jz      loc_14035B843
0x14035a683  cmp     ecx, 1
0x14035a686  jz      loc_14035B843
0x14035a68c  cmp     [rsp+578h+var_4F8.Type], 1
0x14035a694  jz      loc_14035B878
0x14035a69a  xorps   xmm0, xmm0
0x14035a69d  movdqu  xmmword ptr [rsp+578h+var_4D8], xmm0
0x14035a6a6  mov     eax, [rsp+578h+var_4F8.PrivateDriverDataSize]
0x14035a6ad  mov     esi, 3
0x14035a6b2  lea     r13d, [rsi+2Dh]
0x14035a6b6  cmp     [rsp+578h+var_4F8.Type], esi
0x14035a6bd  jz      loc_14035B88E
0x14035a6c3  mov     ebx, eax
0x14035a6c5  cmp     eax, 200h
0x14035a6ca  ja      loc_14035B89A
0x14035a6d0  lea     r15, [rsp+578h+Src]
0x14035a6d8  mov     [rsp+578h+var_450], r15
0x14035a6e0  test    r15, r15
0x14035a6e3  jz      loc_14035B8BD
0x14035a6e9  cmp     [rsp+578h+var_4F8.Type], esi
0x14035a6f0  jz      loc_14035B971
0x14035a6f6  cmp     [rsp+578h+var_50F], r14b
0x14035a6fb  jnz     loc_14035B983
0x14035a701  mov     r8d, [rsp+578h+var_4F8.PrivateDriverDataSize]; Size
0x14035a709  mov     rdx, [rsp+578h+var_4F8.pPrivateDriverData]; Src
0x14035a711  mov     rcx, r15; void *
0x14035a714  call    RtlCopyFromUser
0x14035a719  jmp     short loc_14035A77F
0x14035a71b  mov     rdx, 0FFFFFFFFC000000Dh
0x14035a722  mov     ecx, 3
0x14035a727  call    cs:__imp_WdLogSingleEntry1
0x14035a72e  nop     dword ptr [rax+rax+00h]
0x14035a733  mov     cs:WdLogGlobalForLineNumber, 646h
0x14035a73d  lea     rcx, [rsp+578h+var_4D8]
0x14035a745  call    _DxgkEscape____2___ENSURE_DATA_DELETION___ENSURE_DATA_DELETION
0x14035a74a  lea     rcx, [rsp+578h+var_528]; this
0x14035a74f  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x14035a754  cmp     [rsp+578h+var_518], 0
0x14035a759  jz      short loc_14035A775
0x14035a75b  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x14035a762  jz      short loc_14035A775
0x14035a764  mov     r9d, [rsp+578h+var_528]
0x14035a769  lea     rdx, EventProfilerExit
0x14035a770  call    McTemplateK0q_EtwWriteTransfer
0x14035a775  mov     eax, 0C000000Dh
0x14035a77a  jmp     loc_14035D392
0x14035a77f  test    byte ptr [rsp+578h+var_4F8.Flags], 40h
0x14035a787  jnz     loc_14035B9A0
0x14035a78d  mov     edx, [rsp+578h+var_4F8.Type]
0x14035a794  cmp     edx, 1Bh
0x14035a797  jg      loc_14035AC5E
0x14035a79d  jz      loc_14035BC2C
0x14035a7a3  mov     ecx, edx
0x14035a7a5  sub     ecx, 1
0x14035a7a8  jz      loc_14035BBCC
0x14035a7ae  sub     ecx, 7
0x14035a7b1  jz      loc_14035BA3F
0x14035a7b7  sub     ecx, 1
0x14035a7ba  jz      loc_14035D1EB
0x14035a7c0  sub     ecx, 0Bh
0x14035a7c3  jz      loc_14035AEDD
0x14035a7c9  sub     ecx, 4
0x14035a7cc  jz      loc_14035BA0E
0x14035a7d2  cmp     ecx, 1
0x14035a7d5  jz      loc_14035B9DD
0x14035a7db  mov     [rsp+578h+var_4A0], rdi
0x14035a7e3  mov     [rsp+578h+var_468], rdi
0x14035a7eb  cmp     [rsp+578h+var_4F8.Type], 0Dh
0x14035a7f3  jz      loc_14035BD20
0x14035a7f9  mov     r13, rdi
0x14035a7fc  mov     [rsp+578h+var_478], rdi
0x14035a804  mov     rdx, r12; struct DXGPROCESS *
0x14035a807  lea     rcx, [rsp+578h+var_3F8]; this
0x14035a80f  call    ??0DXGHANDLETABLELOCKSHARED@@QEAA@PEAVDXGPROCESS@@@Z; DXGHANDLETABLELOCKSHARED::DXGHANDLETABLELOCKSHARED(DXGPROCESS *)
0x14035a814  mov     edx, [rsp+578h+var_4F8.hAdapter]
0x14035a81b  test    edx, edx
0x14035a81d  jnz     loc_14035B089
0x14035a823  or      r12d, 0FFFFFFFFh
0x14035a827  test    r13, r13
0x14035a82a  jz      loc_14035B917
0x14035a830  mov     rbx, rdi
0x14035a833  mov     [rsp+578h+var_498], rbx
0x14035a83b  mov     [rsp+578h+var_458], rbx
0x14035a843  mov     r9d, [rsp+578h+var_4F8.hDevice]
0x14035a84b  test    r9d, r9d
0x14035a84e  jnz     loc_14035ACA3
0x14035a854  mov     rcx, rdi
0x14035a857  mov     [rsp+578h+var_470], rcx
0x14035a85f  mov     r9d, [rsp+578h+var_4F8.hContext]
0x14035a867  test    r9d, r9d
0x14035a86a  jnz     loc_14035AF4A
0x14035a870  test    rbx, rbx
0x14035a873  jz      short loc_14035A88A
0x14035a875  lock add [rbx+40h], r14
0x14035a87a  mov     rax, [rbx+10h]
0x14035a87e  mov     r13, [rax+10h]
0x14035a882  mov     [rsp+578h+var_478], r13
0x14035a88a  test    rcx, rcx
0x14035a88d  jnz     loc_14035BDE1
0x14035a893  lock add [r13+18h], r14
0x14035a898  lea     rcx, [rsp+578h+var_3F8]; this
0x14035a8a0  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x14035a8a5  cmp     dword ptr [r13+968h], 5023h
0x14035a8b0  jnb     loc_14035B18F
0x14035a8b6  mov     [rsp+578h+var_4B0], r13
0x14035a8be  mov     [rsp+578h+var_4A8], 0FFFFFFFFFFFFFFFFh
0x14035a8ca  mov     qword ptr [rsp+578h+var_508], rbx
0x14035a8cf  mov     rax, [rsp+578h+var_470]
0x14035a8d7  mov     [rsp+578h+var_500], rax
0x14035a8dc  mov     byte ptr [rsp+578h+var_548], dil; unsigned __int8
0x14035a8e1  mov     qword ptr [rsp+578h+var_550], rdi; unsigned __int64 *
0x14035a8e6  mov     qword ptr [rsp+578h+var_558], rdi; struct DXGADAPTER **
0x14035a8eb  lea     r9, [rsp+578h+var_410]; unsigned __int64 *
0x14035a8f3  lea     r8, [rsp+578h+var_4A0]; struct DXGADAPTER **
0x14035a8fb  xor     edx, edx; unsigned int
0x14035a8fd  mov     rcx, r13; this
0x14035a900  call    ?DxgkpGetPairingAdapters@@YAJPEAVDXGADAPTER@@IPEAPEAV1@PEA_K12E@Z; DxgkpGetPairingAdapters(DXGADAPTER *,uint,DXGADAPTER * *,unsigned __int64 *,DXGADAPTER * *,unsigned __int64 *,uchar)
0x14035a905  mov     esi, eax
0x14035a907  mov     rbx, [rsp+578h+var_4A0]
0x14035a90f  test    eax, eax
0x14035a911  js      short loc_14035A91B
0x14035a913  mov     rcx, rbx; this
0x14035a916  call    ?ReleaseReference@DXGADAPTER@@QEAAX_K@Z; DXGADAPTER::ReleaseReference(unsigned __int64)
0x14035a91b  mov     ecx, [rsp+578h+var_4F8.Type]
0x14035a922  sub     ecx, 1
0x14035a925  jz      loc_14035BED3
0x14035a92b  cmp     ecx, 7
0x14035a92e  jz      loc_14035BE0B
0x14035a934  xor     r8d, r8d; struct DXGADAPTER *
0x14035a937  mov     rdx, r13; struct DXGADAPTER *
0x14035a93a  lea     rcx, [rsp+578h+var_328]; this
0x14035a942  call    ??0COREADAPTERACCESS@@QEAA@QEAVDXGADAPTER@@0@Z; COREADAPTERACCESS::COREADAPTERACCESS(DXGADAPTER * const,DXGADAPTER * const)
0x14035a947  mov     rdx, [rsp+578h+var_468]; struct DXGADAPTER *
0x14035a94f  lea     rcx, [rsp+578h+var_368]; this
0x14035a957  call    ??0COREACCESS@@QEAA@QEAVDXGADAPTER@@_N@Z; COREACCESS::COREACCESS(DXGADAPTER * const,bool)
0x14035a95c  mov     dword ptr [rsp+578h+var_4A0], edi
0x14035a963  mov     [rsp+578h+var_488], r13
0x14035a96b  mov     [rsp+578h+var_480], dil
0x14035a973  cmp     [rsp+578h+var_4F8.Type], 0Dh
0x14035a97b  jnz     loc_14035AD80
0x14035a981  xor     edx, edx; char *
0x14035a983  lea     rcx, [rsp+578h+var_368]; this
0x14035a98b  call    ?AcquireShared@COREACCESS@@QEAAXPEBD@Z; COREACCESS::AcquireShared(char const *)
0x14035a990  cmp     [rsp+578h+var_4F8.hDevice], edi
0x14035a997  jnz     loc_14035ADEC
0x14035a99d  mov     [rsp+578h+var_510], r14b
0x14035a9a2  cmp     [rsp+578h+var_4F8.Type], edi
0x14035a9a9  jz      loc_14035B20E
0x14035a9af  test    rbx, rbx
0x14035a9b2  jnz     loc_14035C093
0x14035a9b8  movsxd  rdx, [rsp+578h+var_4F8.Type]
0x14035a9c0  cmp     edx, 0Fh
0x14035a9c3  jg      loc_14035CA63
0x14035a9c9  jz      loc_14035B71E
0x14035a9cf  cmp     edx, 6
0x14035a9d2  jg      loc_14035C7C0
0x14035a9d8  jz      loc_14035C79C
0x14035a9de  mov     ecx, edx
0x14035a9e0  test    edx, edx
0x14035a9e2  jnz     loc_14035C267
0x14035a9e8  xorps   xmm0, xmm0
0x14035a9eb  movups  xmmword ptr [rsp+578h+var_448.hDevice], xmm0
0x14035a9f3  movups  xmmword ptr [rsp+578h+var_448.pPrivateDriverData], xmm0
0x14035a9fb  movups  xmmword ptr [rsp+578h+var_448.hContext], xmm0
0x14035aa03  cmp     [rsp+578h+var_510], dil
0x14035aa08  jz      loc_14035C3FE
0x14035aa0e  lea     rax, ?DefaultDdiEscape@DXGADAPTER@@CAJQEAXPEBU_DXGKARG_ESCAPE@@@Z; DXGADAPTER::DefaultDdiEscape(void * const,_DXGKARG_ESCAPE const *)
0x14035aa15  cmp     [r13+250h], rax
0x14035aa1c  jnz     loc_14035AB0A
0x14035aa22  mov     r8, 0FFFFFFFFC00000BBh
0x14035aa29  mov     rdx, r13
0x14035aa2c  mov     ecx, 3
0x14035aa31  call    cs:__imp_WdLogSingleEntry2
0x14035aa38  nop     dword ptr [rax+rax+00h]
0x14035aa3d  mov     cs:WdLogGlobalForLineNumber, 9B8h
0x14035aa47  mov     esi, 0C00000BBh
0x14035aa4c  test    esi, esi
0x14035aa4e  jns     loc_14035AE6B
0x14035aa54  lea     rcx, [rsp+578h+var_490]; this
0x14035aa5c  call    ??1DXGADAPTERSTOPRESETLOCKSHARED@@QEAA@XZ; DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(void)
0x14035aa61  lea     rcx, [rsp+578h+var_368]; this
0x14035aa69  call    ??1COREACCESS@@QEAA@XZ; COREACCESS::~COREACCESS(void)
0x14035aa6e  lea     rcx, [rsp+578h+var_328]; this
0x14035aa76  call    ??1COREADAPTERACCESS@@QEAA@XZ; COREADAPTERACCESS::~COREADAPTERACCESS(void)
0x14035aa7b  lea     rcx, [rsp+578h+var_500]; this
0x14035aa80  call    ??1ENSURE_CONTEXT_DEREFERENCE@@QEAA@XZ; ENSURE_CONTEXT_DEREFERENCE::~ENSURE_CONTEXT_DEREFERENCE(void)
0x14035aa85  mov     rcx, [rsp+578h+var_498]
0x14035aa8d  test    rcx, rcx
0x14035aa90  jz      short loc_14035AAAE
0x14035aa92  or      rax, 0FFFFFFFFFFFFFFFFh
0x14035aa96  lock xadd [rcx+40h], rax
0x14035aa9c  cmp     rax, 1
0x14035aaa0  jnz     short loc_14035AAAE
0x14035aaa2  mov     rdx, rcx; struct DXGDEVICE *
0x14035aaa5  mov     rcx, [rcx+10h]; this
0x14035aaa9  call    ?DestroyDeviceNoLocks@ADAPTER_RENDER@@QEAAXPEAVDXGDEVICE@@@Z; ADAPTER_RENDER::DestroyDeviceNoLocks(DXGDEVICE *)
0x14035aaae  mov     rcx, [rsp+578h+var_4B0]; this
0x14035aab6  test    rcx, rcx
0x14035aab9  jz      short loc_14035AAC0
0x14035aabb  call    ?ReleaseReference@DXGADAPTER@@QEAAX_K@Z; DXGADAPTER::ReleaseReference(unsigned __int64)
0x14035aac0  mov     rcx, [rsp+578h+var_4D8]; void *
0x14035aac8  test    rcx, rcx
0x14035aacb  jz      short loc_14035AAD2
0x14035aacd  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x14035aad2  mov     rcx, [rsp+578h+var_4D8+8]; this
0x14035aada  test    rcx, rcx
0x14035aadd  jz      short loc_14035AAE4
0x14035aadf  call    ?ReleaseReference@DXGADAPTER@@QEAAX_K@Z; DXGADAPTER::ReleaseReference(unsigned __int64)
0x14035aae4  lea     rcx, [rsp+578h+var_528]; this
0x14035aae9  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x14035aaee  cmp     [rsp+578h+var_518], dil
0x14035aaf3  jz      short loc_14035AB02
0x14035aaf5  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, r14b
0x14035aafc  jnz     loc_14035B95B
0x14035ab02  mov     eax, esi
0x14035ab04  jmp     loc_14035D392
0x14035ab0a  mov     ecx, [rsp+578h+var_4F8.PrivateDriverDataSize]
0x14035ab11  test    ecx, ecx
0x14035ab13  jz      loc_14035C767
0x14035ab19  cmp     [rsp+578h+var_4F8.pPrivateDriverData], rdi
0x14035ab21  jz      loc_14035C767
0x14035ab27  mov     rax, [rsp+578h+var_498]
0x14035ab2f  test    rax, rax
0x14035ab32  jnz     loc_14035C746
0x14035ab38  mov     rax, [rsp+578h+var_470]
0x14035ab40  test    rax, rax
0x14035ab43  jz      loc_14035C75A
0x14035ab49  mov     rax, [rax+0B8h]
0x14035ab50  mov     [rsp+578h+var_448.hContext], rax
0x14035ab58  mov     eax, dword ptr [rsp+578h+var_4F8.Flags]
0x14035ab5f  mov     dword ptr [rsp+578h+var_448.Flags], eax
0x14035ab66  mov     eax, [r13+1BCh]
0x14035ab6d  test    al, 8
  ... truncated ...
```
