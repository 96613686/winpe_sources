# DXGCONTEXT::Present(DXGK_PRESENT_PARAMS const *,COREDEVICEACCESS *,DXGADAPTERSTOPRESETLOCKSHARED *,CWin32kLocks *,DXGCONTEXT * *,VIDSCH_SUBMIT_DATA_BASE *)

- ea: `0x140399ce0`
- end: `0x14039eb67`
- name: `?Present@DXGCONTEXT@@QEAAJPEBUDXGK_PRESENT_PARAMS@@PEAVCOREDEVICEACCESS@@PEAVDXGADAPTERSTOPRESETLOCKSHARED@@PEAVCWin32kLocks@@PEAPEAV1@PEAUVIDSCH_SUBMIT_DATA_BASE@@@Z`
- size: `20103`
- prototype: `__int64 __usercall@<rax>(DXGCONTEXT *__hidden this@<rcx>, const struct DXGK_PRESENT_PARAMS *@<rdx>, struct COREDEVICEACCESS *@<r8>, struct DXGADAPTERSTOPRESETLOCKSHARED *@<r9>, struct CWin32kLocks *, struct DXGCONTEXT **, struct VIDSCH_SUBMIT_DATA_BASE *)`
- caller_count: `3`
- callee_count: `82`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14024f688`
- `0x140342930`
- `0x1403981e0`

## callees

- `0x140014c4c`
- `0x1400158b0`
- `0x140015dbc`
- `0x140016830`
- `0x14001b890`
- `0x14001bc50`
- `0x14001bdec`
- `0x14001d070`
- `0x14001d0e4`
- `0x14001dc4c`
- `0x14001e47c`
- `0x14001e8dc`
- `0x14001f120`
- `0x140021cc0`
- `0x14002d9f0`
- `0x1400339e0`
- `0x140033d38`
- `0x140033e60`
- `0x140033eb0`
- `0x140034740`
- `0x140037dbc`
- `0x140038bfc`
- `0x1400391ac`
- `0x14003c5e4`
- `0x140040744`
- `0x140040c1c`
- `0x140041fc4`
- `0x1400421c0`
- `0x1400428d4`
- `0x140043ef0`
- `0x1400475cc`
- `0x14004d2a4`
- `0x1400502a4`
- `0x1400555e4`
- `0x140057858`
- `0x1400605c8`
- `0x140079990`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0540`
- `0x140198f50`
- `0x14024fd98`
- `0x140252dac`
- `0x14028bed8`
- `0x140313c5c`
- `0x140317868`
- `0x140323854`
- `0x140327c10`
- `0x140329000`
- `0x140340858`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14039a39e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14039a4c2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14039c139`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14039a39e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14039a4c2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14039c139`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14039a392`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14039a4b6`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14039c12d`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14039a392`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14039a4b6`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14039c12d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14039a6ea`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14039a6ea`
- `ntoskrnl!RtlCompareMemory` at `0x14039c9f9`
- `ntoskrnl!RtlCompareMemory` at `0x14039cf98`
- `ntoskrnl!RtlCompareMemory` at `0x14039c9f9`
- `ntoskrnl!RtlCompareMemory` at `0x14039cf98`
- `watchdog!WdLogSingleEntry4` at `0x14039c56e`
- `watchdog!WdLogSingleEntry4` at `0x14039c5a9`
- `watchdog!WdLogSingleEntry4` at `0x14039c56e`
- `watchdog!WdLogSingleEntry4` at `0x14039c5a9`
- `watchdog!WdLogSingleEntry2` at `0x14039a8df`
- `watchdog!WdLogSingleEntry2` at `0x14039b565`
- `watchdog!WdLogSingleEntry2` at `0x14039b983`
- `watchdog!WdLogSingleEntry2` at `0x14039c4c9`
- `watchdog!WdLogSingleEntry2` at `0x14039c4f6`
- `watchdog!WdLogSingleEntry2` at `0x14039ce4a`
- `watchdog!WdLogSingleEntry2` at `0x14039d1e6`
- `watchdog!WdLogSingleEntry2` at `0x14039d65a`
- `watchdog!WdLogSingleEntry2` at `0x14039d68e`
- `watchdog!WdLogSingleEntry2` at `0x14039d789`
- `watchdog!WdLogSingleEntry2` at `0x14039d831`
- `watchdog!WdLogSingleEntry2` at `0x14039dd91`
- `watchdog!WdLogSingleEntry2` at `0x14039df48`
- `watchdog!WdLogSingleEntry2` at `0x14039e0d5`
- `watchdog!WdLogSingleEntry2` at `0x14039e59a`
- `watchdog!WdLogSingleEntry2` at `0x14039e5c0`
- `watchdog!WdLogSingleEntry2` at `0x14039e739`
- `watchdog!WdLogSingleEntry2` at `0x14039a8df`
- `watchdog!WdLogSingleEntry2` at `0x14039b565`
- `watchdog!WdLogSingleEntry2` at `0x14039b983`
- `watchdog!WdLogSingleEntry2` at `0x14039c4c9`
- `watchdog!WdLogSingleEntry2` at `0x14039c4f6`
- `watchdog!WdLogSingleEntry2` at `0x14039ce4a`
- `watchdog!WdLogSingleEntry2` at `0x14039d1e6`
- `watchdog!WdLogSingleEntry2` at `0x14039d65a`
- `watchdog!WdLogSingleEntry2` at `0x14039d68e`
- `watchdog!WdLogSingleEntry2` at `0x14039d789`
- `watchdog!WdLogSingleEntry2` at `0x14039d831`
- `watchdog!WdLogSingleEntry2` at `0x14039dd91`
- `watchdog!WdLogSingleEntry2` at `0x14039df48`
- `watchdog!WdLogSingleEntry2` at `0x14039e0d5`
- `watchdog!WdLogSingleEntry2` at `0x14039e59a`
- `watchdog!WdLogSingleEntry2` at `0x14039e5c0`
- `watchdog!WdLogSingleEntry2` at `0x14039e739`
- `watchdog!WdLogSingleEntry3` at `0x14039a85a`
- `watchdog!WdLogSingleEntry3` at `0x14039b30d`
- `watchdog!WdLogSingleEntry3` at `0x14039c536`
- `watchdog!WdLogSingleEntry3` at `0x14039c606`
- `watchdog!WdLogSingleEntry3` at `0x14039d3db`
- `watchdog!WdLogSingleEntry3` at `0x14039d474`
- `watchdog!WdLogSingleEntry3` at `0x14039d9ab`
- `watchdog!WdLogSingleEntry3` at `0x14039da32`
- `watchdog!WdLogSingleEntry3` at `0x14039dbde`
- `watchdog!WdLogSingleEntry3` at `0x14039dce2`
- `watchdog!WdLogSingleEntry3` at `0x14039dd12`
- `watchdog!WdLogSingleEntry3` at `0x14039dd50`
- `watchdog!WdLogSingleEntry3` at `0x14039a85a`
- `watchdog!WdLogSingleEntry3` at `0x14039b30d`
- `watchdog!WdLogSingleEntry3` at `0x14039c536`
- `watchdog!WdLogSingleEntry3` at `0x14039c606`
- `watchdog!WdLogSingleEntry3` at `0x14039d3db`
- `watchdog!WdLogSingleEntry3` at `0x14039d474`
- `watchdog!WdLogSingleEntry3` at `0x14039d9ab`
- `watchdog!WdLogSingleEntry3` at `0x14039da32`
- `watchdog!WdLogSingleEntry3` at `0x14039dbde`
- `watchdog!WdLogSingleEntry3` at `0x14039dce2`
- `watchdog!WdLogSingleEntry3` at `0x14039dd12`
- `watchdog!WdLogSingleEntry3` at `0x14039dd50`
- `watchdog!WdLogSingleEntry0` at `0x14039a9b0`
- `watchdog!WdLogSingleEntry0` at `0x14039aa26`
- `watchdog!WdLogSingleEntry0` at `0x14039aa7a`
- `watchdog!WdLogSingleEntry0` at `0x14039c0cd`
- `watchdog!WdLogSingleEntry0` at `0x14039c151`
- `watchdog!WdLogSingleEntry0` at `0x14039c423`
- `watchdog!WdLogSingleEntry0` at `0x14039c46e`
- `watchdog!WdLogSingleEntry0` at `0x14039c7d4`
- `watchdog!WdLogSingleEntry0` at `0x14039d126`
- `watchdog!WdLogSingleEntry0` at `0x14039d230`
- `watchdog!WdLogSingleEntry0` at `0x14039d27e`
- `watchdog!WdLogSingleEntry0` at `0x14039d370`
- `watchdog!WdLogSingleEntry0` at `0x14039d3b3`
- `watchdog!WdLogSingleEntry0` at `0x14039d416`
- `watchdog!WdLogSingleEntry0` at `0x14039d442`
- `watchdog!WdLogSingleEntry0` at `0x14039d87e`
- `watchdog!WdLogSingleEntry0` at `0x14039db17`
- `watchdog!WdLogSingleEntry0` at `0x14039def1`
- `watchdog!WdLogSingleEntry0` at `0x14039df75`
- `watchdog!WdLogSingleEntry0` at `0x14039e1c4`
- `watchdog!WdLogSingleEntry0` at `0x14039e254`
- `watchdog!WdLogSingleEntry0` at `0x14039e2a5`
- `watchdog!WdLogSingleEntry0` at `0x14039e3be`
- `watchdog!WdLogSingleEntry0` at `0x14039e46e`
- `watchdog!WdLogSingleEntry0` at `0x14039e4e1`
- `watchdog!WdLogSingleEntry0` at `0x14039e53c`
- `watchdog!WdLogSingleEntry0` at `0x14039e66e`
- `watchdog!WdLogSingleEntry0` at `0x14039e78f`
- `watchdog!WdLogSingleEntry0` at `0x14039e7bc`
- `watchdog!WdLogSingleEntry0` at `0x14039e9b1`
- `watchdog!WdLogSingleEntry0` at `0x14039ea31`
- `watchdog!WdLogSingleEntry0` at `0x14039eaae`
- `watchdog!WdLogSingleEntry0` at `0x14039eaff`
- `watchdog!WdLogSingleEntry0` at `0x14039a9b0`
- `watchdog!WdLogSingleEntry0` at `0x14039aa26`
- `watchdog!WdLogSingleEntry0` at `0x14039aa7a`
- `watchdog!WdLogSingleEntry0` at `0x14039c0cd`
- `watchdog!WdLogSingleEntry0` at `0x14039c151`
- `watchdog!WdLogSingleEntry0` at `0x14039c423`
- `watchdog!WdLogSingleEntry0` at `0x14039c46e`
- `watchdog!WdLogSingleEntry0` at `0x14039c7d4`
- `watchdog!WdLogSingleEntry0` at `0x14039d126`
- `watchdog!WdLogSingleEntry0` at `0x14039d230`
- `watchdog!WdLogSingleEntry0` at `0x14039d27e`
- `watchdog!WdLogSingleEntry0` at `0x14039d370`
- `watchdog!WdLogSingleEntry0` at `0x14039d3b3`
- `watchdog!WdLogSingleEntry0` at `0x14039d416`
- `watchdog!WdLogSingleEntry0` at `0x14039d442`
- `watchdog!WdLogSingleEntry0` at `0x14039d87e`
- `watchdog!WdLogSingleEntry0` at `0x14039db17`
- `watchdog!WdLogSingleEntry0` at `0x14039def1`
- `watchdog!WdLogSingleEntry0` at `0x14039df75`
- `watchdog!WdLogSingleEntry0` at `0x14039e1c4`
- `watchdog!WdLogSingleEntry0` at `0x14039e254`
- `watchdog!WdLogSingleEntry0` at `0x14039e2a5`
- `watchdog!WdLogSingleEntry0` at `0x14039e3be`
- `watchdog!WdLogSingleEntry0` at `0x14039e46e`
- `watchdog!WdLogSingleEntry0` at `0x14039e4e1`
- `watchdog!WdLogSingleEntry0` at `0x14039e53c`
- `watchdog!WdLogSingleEntry0` at `0x14039e66e`
- `watchdog!WdLogSingleEntry0` at `0x14039e78f`
- `watchdog!WdLogSingleEntry0` at `0x14039e7bc`
- `watchdog!WdLogSingleEntry0` at `0x14039e9b1`
- `watchdog!WdLogSingleEntry0` at `0x14039ea31`
- `watchdog!WdLogSingleEntry0` at `0x14039eaae`
- `watchdog!WdLogSingleEntry0` at `0x14039eaff`
- `watchdog!WdLogSingleEntry5` at `0x140399ee1`
- `watchdog!WdLogSingleEntry5` at `0x14039a2f0`
- `watchdog!WdLogSingleEntry5` at `0x14039b0b2`
- `watchdog!WdLogSingleEntry5` at `0x14039c6a1`
- `watchdog!WdLogSingleEntry5` at `0x14039c709`
- `watchdog!WdLogSingleEntry5` at `0x14039c74e`
- `watchdog!WdLogSingleEntry5` at `0x14039c897`
- `watchdog!WdLogSingleEntry5` at `0x14039c918`
- `watchdog!WdLogSingleEntry5` at `0x14039ca3a`
- `watchdog!WdLogSingleEntry5` at `0x14039cabc`
- `watchdog!WdLogSingleEntry5` at `0x14039cb02`
- `watchdog!WdLogSingleEntry5` at `0x14039cb84`
- `watchdog!WdLogSingleEntry5` at `0x14039cd2f`
- `watchdog!WdLogSingleEntry5` at `0x14039cd99`
- `watchdog!WdLogSingleEntry5` at `0x14039ce2d`
- `watchdog!WdLogSingleEntry5` at `0x14039ce8d`
- `watchdog!WdLogSingleEntry5` at `0x14039cfd3`
- `watchdog!WdLogSingleEntry5` at `0x14039d09f`
- `watchdog!WdLogSingleEntry5` at `0x14039d0da`
- `watchdog!WdLogSingleEntry5` at `0x14039d189`
- `watchdog!WdLogSingleEntry5` at `0x14039d306`
- `watchdog!WdLogSingleEntry5` at `0x14039d80b`
- `watchdog!WdLogSingleEntry5` at `0x14039dde5`
- `watchdog!WdLogSingleEntry5` at `0x14039de69`
- `watchdog!WdLogSingleEntry5` at `0x14039ded1`
- `watchdog!WdLogSingleEntry5` at `0x140399ee1`
- `watchdog!WdLogSingleEntry5` at `0x14039a2f0`
- `watchdog!WdLogSingleEntry5` at `0x14039b0b2`
- `watchdog!WdLogSingleEntry5` at `0x14039c6a1`
- `watchdog!WdLogSingleEntry5` at `0x14039c709`
- `watchdog!WdLogSingleEntry5` at `0x14039c74e`
- `watchdog!WdLogSingleEntry5` at `0x14039c897`
- `watchdog!WdLogSingleEntry5` at `0x14039c918`
- `watchdog!WdLogSingleEntry5` at `0x14039ca3a`
- `watchdog!WdLogSingleEntry5` at `0x14039cabc`
- `watchdog!WdLogSingleEntry5` at `0x14039cb02`
- `watchdog!WdLogSingleEntry5` at `0x14039cb84`
- `watchdog!WdLogSingleEntry5` at `0x14039cd2f`
- `watchdog!WdLogSingleEntry5` at `0x14039cd99`
- `watchdog!WdLogSingleEntry5` at `0x14039ce2d`
- `watchdog!WdLogSingleEntry5` at `0x14039ce8d`
- `watchdog!WdLogSingleEntry5` at `0x14039cfd3`
- `watchdog!WdLogSingleEntry5` at `0x14039d09f`
- `watchdog!WdLogSingleEntry5` at `0x14039d0da`
- `watchdog!WdLogSingleEntry5` at `0x14039d189`
- `watchdog!WdLogSingleEntry5` at `0x14039d306`
- `watchdog!WdLogSingleEntry5` at `0x14039d80b`
- `watchdog!WdLogSingleEntry5` at `0x14039dde5`
- `watchdog!WdLogSingleEntry5` at `0x14039de69`
- `watchdog!WdLogSingleEntry5` at `0x14039ded1`
- `watchdog!WdLogSingleEntry1` at `0x14039d0fe`
- `watchdog!WdLogSingleEntry1` at `0x14039d4c0`
- `watchdog!WdLogSingleEntry1` at `0x14039d515`
- `watchdog!WdLogSingleEntry1` at `0x14039e0ae`

## string_xrefs

- `0x14039d241`: `FlipStereoTemporaryMono and FlipStereo cannot be set together. STATUS_INVALID_PARAMETER`
- `0x14039d453`: `FlipStereoTemporaryMono cannot be used with FlipStereoPreferRight. STATUS_INVALID_PARAMETER`
- `0x14039d381`: `FlipStereoTemporaryMono and FlipStereo can only be used with stereo primary allocations. STATUS_INVALID_PARAMETER`
- `0x14039e9c2`: `!NT_SUCCESS(ntStatus) || !m_pPresent->BltViaGDI() || m_pPresent->IsBltEmpty() || pPresent->Flags.ColorFill`
- `0x14039eabf`: `GetRenderCore()->IsCoreResourceSharedOwner() || ntStatus == STATUS_DEVICE_REMOVED`

## pseudocode

```c
__int64 __fastcall DXGCONTEXT::Present(
        DXGCONTEXT *this,
        const struct DXGK_PRESENT_PARAMS *a2,
        struct COREDEVICEACCESS *a3,
        struct DXGADAPTERSTOPRESETLOCKSHARED *a4,
        struct CWin32kLocks *a5,
        struct DXGCONTEXT **a6,
        struct VIDSCH_SUBMIT_DATA_BASE *a7)
{
  DXGCONTEXT *v7; // r15
  __int64 v9; // rcx
  ADAPTER_RENDER *v10; // rcx
  const struct _DXGKWIN32KENG_INTERFACE *Win32kInterface; // rax
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  unsigned int v15; // ebx
  UINT Width; // r14d
  bool v17; // zf
  signed int v18; // ebx
  UINT Height; // edi
  struct DXGALLOCATION *v20; // rdx
  __int64 v21; // r10
  __int64 v22; // r9
  __int64 v23; // rsi
  int v24; // r12d
  int v25; // eax
  struct COREDEVICEACCESS *v26; // r14
  struct DXGADAPTERSTOPRESETLOCKSHARED *v27; // rdi
  int v28; // eax
  __int64 v29; // rbx
  __int64 v31; // rax
  DXGADAPTER *v32; // rcx
  unsigned int v33; // edi
  DXGADAPTER *v34; // rcx
  __int64 v35; // rdx
  int v36; // r8d
  int v37; // edx
  unsigned __int8 IsFullWDDMDevice; // al
  struct VIDSCH_SUBMIT_DATA_BASE *v39; // r12
  __int64 v40; // rdx
  int v41; // eax
  UINT v42; // eax
  __int64 v43; // r8
  unsigned int v44; // ebx
  __int64 v45; // rdi
  unsigned int v46; // eax
  __int64 v47; // r8
  int v48; // ecx
  struct DXGALLOCATION *v49; // rdx
  __int64 v50; // rdi
  unsigned int v51; // eax
  __int64 v52; // r8
  int v53; // ecx
  struct DXGALLOCATION *v54; // rdx
  int v55; // eax
  unsigned int v56; // r8d
  char v57; // dl
  UINT v58; // edx
  DXGPRESENT *v59; // rcx
  char v60; // dl
  DXGADAPTER *v61; // rcx
  struct COREDEVICEACCESS *v62; // rdi
  int v63; // eax
  BOOL v64; // ebx
  DXGADAPTERSTOPRESETLOCKSHARED *v65; // rsi
  int v66; // r14d
  HANDLE CurrentThreadId; // rax
  __int64 v68; // r8
  CWin32kLocks *v69; // rsi
  int v70; // ebx
  HDC v71; // rdi
  HDC v72; // r8
  HDEV v73; // rsi
  __int64 v74; // rcx
  __int64 v75; // rax
  int v76; // ecx
  struct DXGALLOCATION *v77; // rax
  const wchar_t *v78; // r9
  struct VIDMM_DMA_BUFFER *v79; // rdx
  __int64 v80; // rcx
  unsigned int v81; // eax
  __int64 v82; // rcx
  int v83; // eax
  HDC v84; // rdi
  DXGPROCESS *Current; // rax
  const struct _DXGKWIN32KENG_INTERFACE *v86; // rax
  const struct _DXGKWIN32KENG_INTERFACE *v87; // rbx
  DXGADAPTERSTOPRESETLOCKSHARED *v88; // r14
  unsigned int v89; // edx
  __int64 v90; // r8
  int v91; // eax
  int v92; // ebx
  unsigned int j; // edi
  unsigned int v94; // ecx
  unsigned int v95; // eax
  struct tagRECT *v96; // r8
  RECT *v97; // rcx
  struct COREDEVICEACCESS *v98; // rsi
  int v99; // eax
  __int128 v100; // xmm0
  int v101; // esi
  LONG v102; // eax
  struct tagRECT *DdiSubRectList; // rax
  __int64 v104; // rcx
  unsigned int v105; // ebx
  unsigned int i; // ebx
  int v107; // eax
  ADAPTER_RENDER *v108; // rcx
  int v109; // eax
  __int64 v110; // rax
  __int64 v111; // rdi
  unsigned int v112; // r9d
  _OWORD *v113; // rcx
  _OWORD *v114; // rax
  __int128 v115; // xmm1
  int v116; // eax
  char v117; // r12
  void *v118; // rax
  const RECT *pDstSubRects; // r14
  UINT SubRectCnt; // esi
  UINT v121; // ebx
  int v122; // r15d
  __int64 v123; // r9
  unsigned int v124; // r8d
  unsigned int v125; // r10d
  UINT k; // edx
  __int64 v127; // rcx
  int v128; // eax
  struct VIDSCH_SUBMIT_DATA_BASE *v129; // rbx
  int v130; // ecx
  int v131; // eax
  int v132; // ecx
  int v133; // eax
  int v134; // ecx
  int v135; // edx
  int v136; // eax
  int v137; // edx
  UINT v138; // ecx
  int v139; // ecx
  __int64 v140; // rdx
  D3DDDI_FLIPINTERVAL_TYPE *v141; // rbx
  int DeviceFlipMode; // eax
  const struct DXGALLOCATION *DisplayedPrimary; // rax
  __int64 v144; // rax
  int v145; // ecx
  unsigned int v146; // edx
  int v147; // ebx
  DXGDEVICE *v148; // rbx
  char v149; // bl
  CWin32kLocks *v150; // r14
  DXGADAPTERSTOPRESETLOCKSHARED *v151; // rbx
  struct DXGDEVICE *v152; // rdi
  __int64 v153; // rbx
  struct DXGPROCESS *v154; // rax
  int v155; // eax
  const struct _DXGKWIN32KENG_INTERFACE *v156; // rbx
  int v157; // eax
  struct DXGADAPTERSTOPRESETLOCKSHARED *v158; // rsi
  struct DXGDEVICE *v159; // rdi
  __int64 v160; // rbx
  struct DXGPROCESS *v161; // rax
  unsigned int (__fastcall *v162)(const struct DXGK_PRESENT_PARAMS *, HDC, _QWORD, const RECT *, void *, int, unsigned int, unsigned int, int, int, int, void (__fastcall *)(const struct tagRECT *, const struct tagRECT *, struct tagRECT *, const struct tagRECT *, unsigned int, unsigned int), __int64 (__fastcall *)(struct tagRECT *, struct tagRECT *, const struct tagRECT *, const struct tagRECT *)); // r14
  int v163; // ebx
  int v164; // edi
  bool v165; // si
  HDC v166; // rax
  int v167; // r8d
  char v168; // al
  char v169; // r12
  CWin32kLocks *v170; // rax
  const RECT *v171; // r14
  UINT v172; // esi
  UINT v173; // ebx
  int v174; // r15d
  __int64 v175; // r9
  unsigned int v176; // r8d
  unsigned int v177; // r10d
  struct DXGPROCESS *v178; // rax
  unsigned int v179; // edi
  struct DXGPROCESS *v180; // rbx
  __int64 v181; // rcx
  __int64 v182; // r8
  int v183; // edx
  struct DXGALLOCATION *v184; // rdx
  __int64 v185; // rax
  unsigned int v186; // r12d
  unsigned __int8 *v187; // rsi
  unsigned int v188; // r14d
  __int64 v189; // rdx
  struct DXGHWQUEUE **v190; // rax
  __int64 v191; // rdi
  struct DXGHWQUEUE *v192; // rbx
  char v193; // r14
  char v194; // r12
  const RECT *v195; // rsi
  UINT v196; // edi
  UINT v197; // ebx
  unsigned int v198; // r15d
  __int64 v199; // r9
  unsigned int v200; // r8d
  unsigned int v201; // r10d
  __int64 v202; // rbx
  struct DXGALLOCATION *v203; // rax
  __int64 v204; // r8
  __int64 v205; // rcx
  __int64 v206; // rcx
  unsigned int v207; // edi
  DXGADAPTER *v208; // rcx
  unsigned int v209; // ecx
  int v210; // eax
  unsigned __int64 v211; // rcx
  int v212; // edx
  __int64 v213; // rcx
  signed int v214; // eax
  int v215; // r8d
  unsigned int m; // esi
  unsigned int v217; // r9d
  __int64 v218; // rbx
  __int64 v219; // r14
  __int64 v220; // rsi
  __int64 v221; // r10
  int v222; // r8d
  int v223; // r11d
  int v224; // edx
  unsigned int v225; // ebx
  const RECT *v226; // r8
  int v227; // r10d
  int v228; // r11d
  __int64 v229; // rdx
  RECT v230; // xmm0
  UINT Value; // edx
  unsigned int v232; // esi
  __int64 v233; // rcx
  __int64 v234; // r8
  int v235; // eax
  unsigned int v236; // edx
  int v237; // r8d
  int v238; // r9d
  int v239; // ecx
  const wchar_t *v240; // r9
  __int64 v241; // rax
  struct _DXGKARG_PRESENT *v242; // rbx
  int v243; // edx
  __int64 v244; // rax
  int v245; // ecx
  int v246; // edx
  unsigned __int8 v247; // al
  DXGDEVICE *v248; // rcx
  unsigned int v249; // edx
  int v250; // eax
  const struct _DXGKWIN32KENG_INTERFACE *v251; // rsi
  int v252; // ebx
  int v253; // eax
  int v254; // ecx
  int v255; // eax
  DXGPRESENTMUTEX *v256; // rcx
  __int64 v257; // rbx
  const struct _CDDDXGK_INTERFACE *CddInterface; // rax
  int v259; // eax
  struct VIDMM_DMA_BUFFER *v260; // rdx
  unsigned __int8 v261; // al
  __int64 v262; // rax
  int v263; // eax
  struct VIDMM_DMA_BUFFER *v264; // rdx
  int v265; // eax
  __int64 v266; // rcx
  struct VIDMM_GLOBAL *v267; // rdx
  VIDMM_EXPORT *v268; // rcx
  struct DXGALLOCATION *v269; // rsi
  unsigned int v270; // edx
  __int128 v271; // xmm0
  __int64 v272; // rax
  int v273; // eax
  UINT v274; // ecx
  enum _D3DDDIFORMAT v275; // ebx
  __int64 v276; // rcx
  __int64 v277; // rdx
  __int64 v278; // rdx
  int v279; // eax
  unsigned int v280; // edx
  COREDEVICEACCESS *v281; // rcx
  unsigned __int8 v282; // di
  int v283; // ebx
  LONG v284; // ecx
  LONG v285; // ecx
  LONG v286; // eax
  struct DXGPROCESS *v287; // rax
  D3DKMT_HANDLE v288; // eax
  DXGDEVICE *v289; // rbx
  int v290; // edi
  unsigned __int8 v291; // al
  char v292; // bl
  const struct _DXGKWIN32KENG_INTERFACE *v293; // rbx
  int v294; // eax
  int v295; // eax
  unsigned int (__fastcall *v296)(HDC, _QWORD, __int64, _QWORD, _DWORD); // r14
  unsigned int v297; // edi
  __int64 v298; // rsi
  HDC v299; // rax
  int v300; // eax
  __int64 v301; // rax
  const wchar_t *v302; // r9
  __int64 v303; // rcx
  unsigned __int8 v304; // r8
  int CurrentOrientation; // eax
  __int64 v306; // rsi
  unsigned int v307; // r14d
  unsigned int v308; // r12d
  struct DXGHWQUEUE **v309; // rax
  struct DXGHWQUEUE *v310; // rbx
  struct DXGPROCESS *v311; // rax
  __int64 v312; // [rsp+20h] [rbp-100h]
  struct _DXGKARG_PRESENT *v313; // [rsp+20h] [rbp-100h]
  __int64 v314; // [rsp+28h] [rbp-F8h]
  __int64 v315; // [rsp+28h] [rbp-F8h]
  __int64 v316; // [rsp+30h] [rbp-F0h]
  __int64 v317; // [rsp+30h] [rbp-F0h]
  __int64 v318; // [rsp+38h] [rbp-E8h]
  __int64 v319; // [rsp+38h] [rbp-E8h]
  __int64 v320; // [rsp+40h] [rbp-E0h]
  int v321; // [rsp+40h] [rbp-E0h]
  __int64 v322; // [rsp+40h] [rbp-E0h]
  int v323; // [rsp+48h] [rbp-D8h]
  struct VIDSCH_SUBMIT_DATA_BASE *v324; // [rsp+58h] [rbp-C8h]
  enum _D3DDDIFORMAT v325; // [rsp+60h] [rbp-C0h]
  struct DXGALLOCATION *v327; // [rsp+A8h] [rbp-78h] BYREF
  char v328; // [rsp+B0h] [rbp-70h]
  unsigned int v329; // [rsp+B4h] [rbp-6Ch] BYREF
  unsigned int v330; // [rsp+B8h] [rbp-68h]
  char v331; // [rsp+BCh] [rbp-64h]
  unsigned int v332; // [rsp+C0h] [rbp-60h]
  CWin32kLocks *v333; // [rsp+C8h] [rbp-58h]
  struct DXGALLOCATION *v334; // [rsp+D0h] [rbp-50h] BYREF
  unsigned int v335; // [rsp+D8h] [rbp-48h]
  DXGADAPTERSTOPRESETLOCKSHARED *v336; // [rsp+E0h] [rbp-40h]
  enum _D3DDDIFORMAT Format; // [rsp+E8h] [rbp-38h]
  unsigned int v338[2]; // [rsp+F0h] [rbp-30h]
  const struct _DXGKWIN32KENG_INTERFACE *v339; // [rsp+F8h] [rbp-28h]
  struct VIDSCH_SUBMIT_DATA_BASE *v340; // [rsp+100h] [rbp-20h]
  unsigned int v341[2]; // [rsp+108h] [rbp-18h]
  unsigned int v342; // [rsp+110h] [rbp-10h]
  __int64 v343; // [rsp+118h] [rbp-8h] BYREF
  _BYTE v344[24]; // [rsp+120h] [rbp+0h] BYREF
  struct DXGCONTEXT **v345; // [rsp+138h] [rbp+18h]
  __int64 v346; // [rsp+140h] [rbp+20h] BYREF
  DXGCONTEXT *v347; // [rsp+148h] [rbp+28h]
  char v348[8]; // [rsp+150h] [rbp+30h] BYREF
  char v349[8]; // [rsp+158h] [rbp+38h] BYREF
  char v350[8]; // [rsp+160h] [rbp+40h] BYREF
  char v351[8]; // [rsp+168h] [rbp+48h] BYREF
  __int64 v352; // [rsp+170h] [rbp+50h] BYREF
  _D3DKMT_UNLOCK2 v353; // [rsp+178h] [rbp+58h] BYREF
  struct _D3DKMT_UNLOCK v354; // [rsp+180h] [rbp+60h] BYREF
  struct _DXGKARG_DESCRIBEALLOCATION v355; // [rsp+190h] [rbp+70h] BYREF
  struct _DXGKARG_DESCRIBEALLOCATION v356; // [rsp+1C0h] [rbp+A0h] BYREF
  _BYTE v357[24]; // [rsp+1F0h] [rbp+D0h] BYREF
  struct _D3DKMT_LOCK2 v358; // [rsp+208h] [rbp+E8h] BYREF
  _BYTE v359[24]; // [rsp+220h] [rbp+100h] BYREF
  struct _D3DKMT_LOCK v360; // [rsp+238h] [rbp+118h] BYREF
  struct _DXGKARG_DESCRIBEALLOCATION v361; // [rsp+268h] [rbp+148h] BYREF
  enum _D3DDDIFORMAT v362[4]; // [rsp+2A0h] [rbp+180h]
  _DWORD v363[8]; // [rsp+2F0h] [rbp+1D0h] BYREF
  _QWORD v364[70]; // [rsp+310h] [rbp+1F0h] BYREF
  struct _DXGKARG_PRESENT v365; // [rsp+540h] [rbp+420h] BYREF
  struct tagRECT v366; // [rsp+5F0h] [rbp+4D0h] BYREF
  struct tagRECT v367; // [rsp+600h] [rbp+4E0h] BYREF
  __int128 v368; // [rsp+610h] [rbp+4F0h] BYREF
  struct tagRECT Source1; // [rsp+620h] [rbp+500h] BYREF
  struct tagRECT v370; // [rsp+630h] [rbp+510h] BYREF
  int v371; // [rsp+640h] [rbp+520h]
  unsigned int v372; // [rsp+644h] [rbp+524h]
  _QWORD v373[39]; // [rsp+648h] [rbp+528h] BYREF
  _DWORD v374[16]; // [rsp+780h] [rbp+660h] BYREF
  _DWORD v375[16]; // [rsp+7C0h] [rbp+6A0h] BYREF
  _DWORD v376[16]; // [rsp+800h] [rbp+6E0h] BYREF
  _DWORD v377[16]; // [rsp+840h] [rbp+720h] BYREF
  _DWORD v378[16]; // [rsp+880h] [rbp+760h] BYREF
  _DWORD v379[16]; // [rsp+8C0h] [rbp+7A0h] BYREF
  _DWORD v380[16]; // [rsp+900h] [rbp+7E0h] BYREF
  _DWORD v381[16]; // [rsp+940h] [rbp+820h] BYREF
  _DWORD v382[16]; // [rsp+980h] [rbp+860h] BYREF
  _DWORD v383[16]; // [rsp+9C0h] [rbp+8A0h] BYREF
  _DWORD v384[16]; // [rsp+A00h] [rbp+8E0h] BYREF
  _DWORD v385[16]; // [rsp+A40h] [rbp+920h] BYREF

  v7 = this;
  v347 = this;
  v9 = *((_QWORD *)this + 2);
  v333 = a5;
  v336 = a4;
  v10 = *(ADAPTER_RENDER **)(v9 + 16);
  v340 = a7;
  v345 = a6;
  if ( !ADAPTER_RENDER::IsCoreResourceSharedOwner(v10) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 3984;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"GetRenderCore()->IsCoreResourceSharedOwner()",
      3984,
      0,
      0,
      0,
      0);
  }
  if ( *((_QWORD *)v7 + 45) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 3985;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"m_pPresentDmaBuffer == NULL", 3985, 0, 0, 0, 0);
  }
  if ( (*((_DWORD *)a2 + 22) & 0x4000) != 0 )
  {
    v24 = -1073741811;
    WdLogSingleEntry2(3, v7);
    WdLogGlobalForLineNumber = 3991;
    return (unsigned int)v24;
  }
  Win32kInterface = DXGPROCESS::GetWin32kInterface(*(DXGPROCESS **)(*((_QWORD *)v7 + 2) + 40LL));
  v12 = *((_DWORD *)a2 + 22);
  v339 = Win32kInterface;
  if ( (v12 & 0x12000) == 0x12000 )
  {
    v24 = -1073741811;
    WdLogSingleEntry2(3, v7);
    WdLogGlobalForLineNumber = 4002;
    return (unsigned int)v24;
  }
  memset(&v365, 0, sizeof(v365));
  v335 = *((_DWORD *)a2 + 5);
  v329 = *((_DWORD *)a2 + 6);
  *(_DWORD *)a7 |= 0x10020u;
  v13 = *(_DWORD *)a7;
  if ( (*((_DWORD *)a2 + 22) & 0x10000) == 0 )
    v13 |= 1u;
  v14 = v13 | 0x100;
  *(_DWORD *)a7 = v14;
  *(_DWORD *)a7 = v14 ^ (v14 ^ (32 * *((_DWORD *)a2 + 22))) & 0x20000;
  if ( (*((_DWORD *)a2 + 22) & 0x1000) != 0 )
    *((_DWORD *)a7 + 28) = *((_DWORD *)a2 + 20);
  if ( *(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) != *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 16LL) )
    *((_DWORD *)a7 + 29) = 0;
  DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v327, 0);
  DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v334, 0);
  DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v343, 0);
  v15 = *((_DWORD *)a2 + 6);
  if ( v15 )
  {
    v50 = *(_QWORD *)(*((_QWORD *)v7 + 2) + 40LL);
    DXGPUSHLOCK::AcquireShared((DXGPUSHLOCK *)(v50 + 248));
    v51 = (v15 >> 6) & 0xFFFFFF;
    if ( v51 < *(_DWORD *)(v50 + 296)
      && (v52 = *(_QWORD *)(v50 + 280), ((v15 >> 25) & 0x60) == (*(_BYTE *)(v52 + 16LL * v51 + 8) & 0x60))
      && (*(_DWORD *)(v52 + 16LL * v51 + 8) & 0x2000) == 0
      && (v53 = *(_DWORD *)(v52 + 16LL * v51 + 8) & 0x1F) != 0 )
    {
      if ( v53 == 5 )
      {
        v54 = *(struct DXGALLOCATION **)(v52 + 16LL * v51);
      }
      else
      {
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 318;
        DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
        v54 = 0;
      }
    }
    else
    {
      v54 = 0;
    }
    DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v348, v54);
    _InterlockedDecrement((volatile signed __int32 *)(v50 + 264));
    ExReleasePushLockSharedEx(v50 + 248, 0);
    KeLeaveCriticalRegion();
    DXGALLOCATIONREFERENCE::MoveAssign(&v334, v348);
    DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v348);
    if ( !v334 )
    {
      v24 = -1073741811;
      WdLogSingleEntry3(3, -1073741811, v7, *((unsigned int *)a2 + 6));
      WdLogGlobalForLineNumber = 4057;
      goto LABEL_34;
    }
    if ( *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v334 + 1) + 16LL) + 16LL) != *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2)
                                                                                                + 16LL)
                                                                                    + 16LL) )
    {
      v24 = -1073741811;
      WdLogSingleEntry3(2, *((_QWORD *)v7 + 2), v334, -1073741811);
      v77 = v334;
      WdLogGlobalForLineNumber = 4067;
      goto LABEL_119;
    }
    memset(&v361, 0, sizeof(v361));
    v361.hAllocation = *(HANDLE *)(*((_QWORD *)v334 + 6) + 16LL);
    v55 = ADAPTER_RENDER::DdiDescribeAllocation(*(ADAPTER_RENDER **)(*((_QWORD *)v7 + 2) + 16LL), &v361);
    v24 = v55;
    if ( v55 < 0 )
    {
      v202 = v55;
      WdLogSingleEntry4(2, v55, v7, *(_QWORD *)(*((_QWORD *)v334 + 6) + 16LL), v334);
      v203 = v334;
      WdLogGlobalForLineNumber = 4080;
      goto LABEL_352;
    }
    Width = v361.Width;
    v341[0] = v361.Height;
  }
  else
  {
    Width = 0;
    v341[0] = 0;
  }
  v17 = (*((_DWORD *)a2 + 22) & 0x8002) == 0;
  v338[0] = Width;
  if ( v17 )
  {
    v44 = *((_DWORD *)a2 + 5);
    v45 = *(_QWORD *)(*((_QWORD *)v7 + 2) + 40LL);
    DXGPUSHLOCK::AcquireShared((DXGPUSHLOCK *)(v45 + 248));
    v46 = (v44 >> 6) & 0xFFFFFF;
    if ( v46 < *(_DWORD *)(v45 + 296)
      && (v47 = *(_QWORD *)(v45 + 280), ((v44 >> 25) & 0x60) == (*(_BYTE *)(v47 + 16LL * v46 + 8) & 0x60))
      && (*(_DWORD *)(v47 + 16LL * v46 + 8) & 0x2000) == 0
      && (v48 = *(_DWORD *)(v47 + 16LL * v46 + 8) & 0x1F) != 0 )
    {
      if ( v48 == 5 )
      {
        v49 = *(struct DXGALLOCATION **)(v47 + 16LL * v46);
      }
      else
      {
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 318;
        DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
        v49 = 0;
      }
    }
    else
    {
      v49 = 0;
    }
    DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v349, v49);
    _InterlockedDecrement((volatile signed __int32 *)(v45 + 264));
    ExReleasePushLockSharedEx(v45 + 248, 0);
    KeLeaveCriticalRegion();
    DXGALLOCATIONREFERENCE::MoveAssign(&v327, v349);
    DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v349);
    v20 = v327;
    if ( !v327 )
    {
      v24 = -1073741811;
      WdLogSingleEntry3(3, -1073741811, v7, *((unsigned int *)a2 + 5));
      WdLogGlobalForLineNumber = 4095;
      goto LABEL_34;
    }
    memset(&v356, 0, sizeof(v356));
    v356.hAllocation = *(HANDLE *)(*((_QWORD *)v327 + 6) + 16LL);
    if ( (*((_DWORD *)a2 + 22) & 0x10000000) != 0 )
    {
      v18 = *((_DWORD *)a2 + 379);
      v356.Width = v18;
      Height = *((_DWORD *)a2 + 380);
      v356.Height = Height;
      Format = *((_DWORD *)a2 + 381);
      v356.Format = Format;
      goto LABEL_18;
    }
    v108 = *(ADAPTER_RENDER **)(*((_QWORD *)v7 + 2) + 16LL);
    if ( *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v327 + 1) + 16LL) + 16LL) == *((_QWORD *)v108 + 2) )
    {
      v109 = ADAPTER_RENDER::DdiDescribeAllocation(v108, &v356);
      v24 = v109;
      if ( v109 >= 0 )
      {
        Height = v356.Height;
        v18 = v356.Width;
        Format = v356.Format;
        goto LABEL_17;
      }
      v202 = v109;
      WdLogSingleEntry4(2, v109, v7, *(_QWORD *)(*((_QWORD *)v327 + 6) + 16LL), v327);
      v203 = v327;
      WdLogGlobalForLineNumber = 4134;
LABEL_352:
      v78 = L"ret = 0x%I64x Context 0x%I64x: DdiDescribeAllocation failed 0x%I64x 0x%I64x";
      v320 = 0;
      v318 = (__int64)v203;
      v316 = *(_QWORD *)(*((_QWORD *)v203 + 6) + 16LL);
      v314 = (__int64)v7;
      v312 = v202;
      goto LABEL_120;
    }
    v24 = -1073741811;
    WdLogSingleEntry3(2, *((_QWORD *)v7 + 2), v327, -1073741811);
    v77 = v327;
    WdLogGlobalForLineNumber = 4123;
LABEL_119:
    v320 = 0;
    v78 = L"Device 0x%p does not match allocation 0x%p owner, returning 0x%I64x";
    v318 = 0;
    v316 = -1073741811;
    v314 = (__int64)v77;
    v312 = *((_QWORD *)v7 + 2);
    goto LABEL_120;
  }
  v18 = 0;
  Format = D3DDDIFMT_UNKNOWN;
  Height = 0;
LABEL_17:
  v20 = v327;
LABEL_18:
  v21 = *((unsigned int *)a2 + 6);
  v330 = v18;
  v332 = Height;
  if ( (_DWORD)v21 )
  {
    LODWORD(v22) = *((_DWORD *)a2 + 22);
    if ( (v22 & 0x10000) == 0 )
      goto LABEL_355;
  }
  v22 = *((unsigned int *)a2 + 22);
  if ( (v22 & 4) == 0 )
  {
    v342 = 0;
    if ( (v22 & 1) == 0 )
    {
      v23 = 2;
      if ( (v22 & 2) == 0 )
      {
        if ( (v22 & 0x8000) == 0 )
        {
          v24 = -1073741811;
          WdLogSingleEntry5(3, -1073741811, v7, *((_QWORD *)a2 + 9), *((unsigned int *)a2 + 16), v22);
          WdLogGlobalForLineNumber = 6237;
          goto LABEL_31;
        }
        if ( (v22 & 6) == 0 && (v22 & 0x27E8) == 0 )
        {
          v25 = *((_DWORD *)a2 + 90);
          if ( v25 == 2 )
          {
            if ( *((_DWORD *)a2 + 293) <= 0x10u )
              goto LABEL_28;
          }
          else if ( ((v25 - 7) & 0xFFFFFFFD) == 0 )
          {
LABEL_28:
            v26 = a3;
            v27 = v336;
            v28 = SubmitPresentHistoryTokenPreparation(
                    v336,
                    a3,
                    *(struct DXGADAPTER **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 16LL),
                    (struct _D3DKMT_PRESENTHISTORYTOKEN *)((char *)a2 + 360),
                    *((void **)a2 + 44),
                    (v22 & 0x10) != 0);
            if ( v28 >= 0 )
            {
              TOKEN_BINDING_GUARD::TOKEN_BINDING_GUARD(
                (TOKEN_BINDING_GUARD *)v363,
                (struct _D3DKMT_PRESENTHISTORYTOKEN *)((char *)a2 + 360),
                v27,
                a3);
              v363[0] = SubmitPresentHistoryToken(
                          (const struct _D3DKMT_PRESENTHISTORYTOKEN *)((char *)a2 + 360),
                          a3,
                          v27,
                          v333,
                          1,
                          0,
                          a2,
                          v340,
                          v7,
                          0,
                          0);
              v24 = v363[0];
              TOKEN_BINDING_GUARD::~TOKEN_BINDING_GUARD((TOKEN_BINDING_GUARD *)v363);
              if ( v24 >= 0 )
              {
LABEL_30:
                v29 = v343;
                if ( v343 )
                {
                  if ( (*((_DWORD *)a2 + 22) & 0x10000000) == 0 )
                  {
                    v110 = *((_QWORD *)v7 + 2);
                    v111 = *(_QWORD *)(v110 + 1896);
                    if ( v111 )
                    {
                      if ( (*(_DWORD *)(*(_QWORD *)(v110 + 40) + 408LL) & 4) == 0 )
                      {
                        memset(v373, 0, 0x130u);
                        v112 = v342;
                        v371 = *(_DWORD *)a2;
                        v372 = v342;
                        LODWORD(v373[0]) = (*(_DWORD *)(*(_QWORD *)(v343 + 48) + 4LL) >> 6) & 0xF;
                        v113 = &v373[1];
                        HIDWORD(v373[0]) = *((_DWORD *)a2 + 23);
                        v114 = (_OWORD *)((char *)a2 + 96);
                        do
                        {
                          *v113 = *v114;
                          v113[1] = v114[1];
                          v113[2] = v114[2];
                          v113[3] = v114[3];
                          v113[4] = v114[4];
                          v113[5] = v114[5];
                          v113[6] = v114[6];
                          v115 = v114[7];
                          v114 += 8;
                          v113[7] = v115;
                          v113 += 8;
                          --v23;
                        }
                        while ( v23 );
                        LODWORD(v373[33]) = 0;
                        LODWORD(v373[37]) = 4;
                        LODWORD(v373[35]) = 0;
                        v116 = OUTPUTDUPL_MGR::ProcessPresent(
                                 *(OUTPUTDUPL_MGR **)(*(_QWORD *)(v111 + 3232) + 120LL),
                                 v7,
                                 (struct _D3DKMT_OUTPUTDUPLPRESENTFLAGS)4,
                                 v112,
                                 HIDWORD(v373[0]),
                                 (struct _D3DKMT_PRESENT_RGNS *)&v373[33],
                                 a2,
                                 (*(_DWORD *)(*(_QWORD *)(v29 + 48) + 4LL) >> 6) & 0xF,
                                 v345,
                                 v26);
                        if ( v116 == 259 )
                          v116 = 0;
                        v24 = v116;
                      }
                    }
                  }
                }
                goto LABEL_31;
              }
              goto LABEL_31;
            }
            goto LABEL_408;
          }
        }
        v24 = -1073741811;
        WdLogSingleEntry3(3, v7, v22, -1073741811);
        WdLogGlobalForLineNumber = 6201;
        goto LABEL_34;
      }
    }
    if ( (v22 & 0x100) != 0 )
    {
      v276 = *((_QWORD *)v7 + 2);
      if ( !*(_QWORD *)(v276 + 1896) )
      {
        v24 = -1073741811;
        WdLogSingleEntry2(3, *((_QWORD *)v7 + 2));
        WdLogGlobalForLineNumber = 5150;
        goto LABEL_34;
      }
      v277 = *((unsigned int *)a2 + 4);
      if ( *(_DWORD *)(v276 + 1904) <= (unsigned int)v277 )
      {
        WdLogSingleEntry2(3, v277);
        WdLogGlobalForLineNumber = 5156;
        goto LABEL_416;
      }
    }
    v43 = *((_QWORD *)a2 + 9);
    if ( (((unsigned int)v22 >> 1) & 1) != 0 )
    {
      if ( !v43 || !*((_DWORD *)a2 + 16) || (v22 & 0x86BC) != 0 || (v22 & 1) != 0 )
      {
        v24 = -1073741811;
        WdLogSingleEntry5(3, v7, v43, *((unsigned int *)a2 + 16), v22, -1073741811);
        WdLogGlobalForLineNumber = 5178;
        goto LABEL_34;
      }
      v335 = 0;
    }
    else
    {
      if ( !v43 || (v278 = *((unsigned int *)a2 + 16), !(_DWORD)v278) || !v18 || !Height || (v22 & 0x802C) != 0 )
      {
        v24 = -1073741811;
        WdLogSingleEntry5(3, v7, v43, *((unsigned int *)a2 + 16), *((unsigned int *)a2 + 22), -1073741811);
        WdLogGlobalForLineNumber = 5198;
        goto LABEL_34;
      }
      if ( (((unsigned int)v22 >> 9) & 1) != 0 || (v22 & 0x400) != 0 )
      {
        if ( (((unsigned int)v22 >> 9) & 1) == (((unsigned int)v22 >> 10) & 1) )
        {
          v24 = -1073741811;
          WdLogSingleEntry5(3, -1073741811, v7, v43, v278, v22);
          WdLogGlobalForLineNumber = 5210;
          goto LABEL_34;
        }
        if ( (v22 & 0x100) == 0
          || !ADAPTER_DISPLAY::IsVidPnSourceOwner(
                *(ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3232LL),
                *((const struct DXGDEVICE **)v7 + 2),
                *((_DWORD *)a2 + 4)) )
        {
          v24 = -1073741811;
          WdLogSingleEntry5(
            3,
            v7,
            *((_QWORD *)a2 + 9),
            *((unsigned int *)a2 + 16),
            *((unsigned int *)a2 + 22),
            -1073741811);
          WdLogGlobalForLineNumber = 5219;
          goto LABEL_34;
        }
      }
    }
    v56 = *((_DWORD *)a2 + 22);
    v57 = v56 ^ (v56 & 2 | *(_BYTE *)&v365.Flags.0 & 0xFD);
    v56 >>= 5;
    v58 = (*((_DWORD *)a2 + 22) & 2 | v365.Flags.Value & 0xFFFFFFFD) ^ v57 & 1;
    v365.Flags.Value = v58
                     ^ ((unsigned __int8)v58
                      ^ (unsigned __int8)v56)
                     & 0x10
                     ^ ((unsigned __int8)(v58 ^ (v58 ^ v56) & 0x10)
                      ^ (unsigned __int8)v56)
                     & 0x20
                     ^ ((unsigned __int8)(v58 ^ (v58 ^ v56) & 0x10 ^ (v58 ^ (v58 ^ v56) & 0x10 ^ v56) & 0x20)
                      ^ (unsigned __int8)v56)
                     & 0x40;
    v365.Color = *((_DWORD *)a2 + 7);
    v24 = DXGPRESENT::CheckInput(*((DXGPRESENT **)v7 + 19), (const struct _D3DKMT_PRESENT *)a2, v18, Height);
    if ( v24 < 0 )
      goto LABEL_31;
    v59 = (DXGPRESENT *)*((_QWORD *)v7 + 19);
    v60 = 0;
    v328 = 0;
    if ( (*((_DWORD *)v59 + 1) & 4) != 0 )
    {
LABEL_638:
      if ( bTracingEnabled && !v60 && (Microsoft_Windows_DxgKrnlEnableBits & 0x20) != 0 )
        McTemplateK0p_EtwWriteTransfer(&DxgkControlGuid_Context, EventBlitCancel, 0, *((_QWORD *)a2 + 1));
      v26 = a3;
      goto LABEL_63;
    }
    DXGPRESENT::CheckOutput(v59, Width, v341[0]);
    v61 = *(DXGADAPTER **)(*((_QWORD *)v7 + 2) + 1896LL);
    if ( !v61 || DXGADAPTER::IsDisplayOnlyAdapter(v61) )
    {
      v62 = a3;
      v63 = DXGCONTEXT::WaitForQueuedPresentLimit(v7, 0, (*((_DWORD *)a2 + 22) & 0x10) == 0, a3);
      v24 = v63;
      if ( v63 < 0 )
      {
        WdLogSingleEntry2(4, v63);
        WdLogGlobalForLineNumber = 5268;
        goto LABEL_34;
      }
    }
    else
    {
      if ( *(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) != *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 16LL) )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 5244;
        DxgkLogInternalTriageEvent(
          0,
          262146,
          -1,
          (unsigned int)L"GetDisplayAdapter() == GetRenderAdapter()",
          5244,
          0,
          0,
          0,
          0);
      }
      v62 = a3;
      for ( i = 0; i < *(_DWORD *)(*((_QWORD *)v7 + 2) + 1904LL); ++i )
      {
        v107 = DXGCONTEXT::WaitForQueuedPresentLimit(v7, i, (*((_DWORD *)a2 + 22) & 0x10) == 0, a3);
        v24 = v107;
        if ( v107 < 0 )
        {
          WdLogSingleEntry2(4, v107);
          WdLogGlobalForLineNumber = 5254;
          goto LABEL_34;
        }
      }
    }
    v24 = DXGCONTEXT::AcquireDmaBuffer(v7, (struct VIDMM_DMA_BUFFER **)v7 + 45, v62, 0);
    if ( v24 < 0 )
      goto LABEL_31;
    if ( !*((_QWORD *)v7 + 45) && !*((_BYTE *)v7 + 434) )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 5282;
      DxgkLogInternalTriageEvent(
        0,
        262146,
        -1,
        (unsigned int)L"m_pPresentDmaBuffer || IsParavirtualized()",
        5282,
        0,
        0,
        0,
        0);
    }
    DXGPRESENTMUTEX::DXGPRESENTMUTEX(
      (DXGPRESENTMUTEX *)v344,
      *(struct ADAPTER_RENDER *const *)(*((_QWORD *)v7 + 2) + 16LL));
    if ( (*((_DWORD *)a2 + 22) & 0x10000) != 0 )
    {
      v64 = 0;
      if ( *((_DWORD *)a2 + 6) )
      {
        v82 = *((_QWORD *)v334 + 6);
        v83 = *(_DWORD *)(v82 + 4);
        *(_DWORD *)(v82 + 4) = v83 | 0x400;
        v64 = (v83 & 0x400) == 0;
      }
      v65 = v336;
    }
    else
    {
      COREDEVICEACCESS::Release(v62);
      v65 = v336;
      DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v336);
      DXGPRESENTMUTEX::Acquire((DXGPRESENTMUTEX *)v344);
      DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v65);
      v279 = COREDEVICEACCESS::AcquireShared(v62, 0);
      v24 = v279;
      if ( v279 < 0 )
      {
        WdLogSingleEntry2(4, v279);
        WdLogGlobalForLineNumber = 5303;
        goto LABEL_476;
      }
      v64 = 0;
    }
    v66 = (*((__int64 (**)(void))v339 + 1))();
    CurrentThreadId = PsGetCurrentThreadId();
    v17 = *((_BYTE *)v7 + 434) == 0;
    *(_QWORD *)v338 = CurrentThreadId;
    if ( v17 )
    {
      VIDSCH_EXPORT::VidSchGetMonitorPowerState(
        *(VIDSCH_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 736LL),
        *(struct _VIDSCH_GLOBAL **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 744LL));
      CurrentThreadId = *(HANDLE *)v338;
    }
    v68 = *((_QWORD *)v7 + 19);
    if ( *(_DWORD *)(v68 + 8) == v66
      && *(HANDLE *)(v68 + 56) == CurrentThreadId
      && *(_QWORD *)(v68 + 48) == *((_QWORD *)a2 + 1)
      && !*(_DWORD *)(v68 + 64)
      && !v64 )
    {
      v280 = *(_DWORD *)(v68 + 4);
      if ( !(((v280 & 8) != 0) | BYTE1(v280) & 1) )
      {
        if ( (v280 & 1) != 0 )
        {
          v24 = -1071775738;
        }
        else if ( (((*((_DWORD *)a2 + 22) & 0x10000) == 0) & (unsigned __int8)~(unsigned __int8)(v280 >> 4)) != 0 )
        {
          DXGDEVICE::SynchronizePresentToPrimary(*((DXGDEVICE **)v7 + 2), v7, (struct DXGPRESENTMUTEX *)v344, 0);
        }
        goto LABEL_571;
      }
    }
    DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v344);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v65);
    COREDEVICEACCESS::Release(v62);
    v69 = v333;
    v70 = CWin32kLocks::Lock(v333, *((HWND *)a2 + 1), *((_WORD *)a2 + 45) & 1, 1, 0);
    if ( _bittest((const signed __int32 *)a2 + 22, 0x10u) )
    {
      v352 = 0;
      (*((void (__fastcall **)(_QWORD, __int64 *))v339 + 31))(*(_QWORD *)v69, &v352);
      *(_QWORD *)(*((_QWORD *)v7 + 19) + 440LL) = v352;
    }
    if ( !_bittest((const signed __int32 *)a2 + 22, 0x10u) )
      DXGPRESENTMUTEX::Acquire((DXGPRESENTMUTEX *)v344);
    DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v336);
    v24 = COREDEVICEACCESS::AcquireShared(v62, 0);
    if ( v24 >= 0 )
    {
      v24 = 0;
      if ( v70 < 0 )
      {
        v24 = v70;
        goto LABEL_115;
      }
      if ( (*((_DWORD *)a2 + 22) & 0x10000) != 0 && *((_DWORD *)a2 + 6) && !*(_QWORD *)(*((_QWORD *)v7 + 19) + 440LL) )
      {
        WdLogSingleEntry2(4, 0);
        WdLogGlobalForLineNumber = 5426;
        v79 = (struct VIDMM_DMA_BUFFER *)*((_QWORD *)v7 + 45);
        if ( v79 )
        {
          VIDMM_EXPORT::VidMmReleaseDmaBuffer(*(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL), v79);
          *((_QWORD *)v7 + 45) = 0;
        }
        goto LABEL_477;
      }
      v71 = *(HDC *)v69;
      v72 = *(HDC *)v69;
      v73 = (HDEV)*((_QWORD *)v69 + 2);
      v24 = DXGPRESENT::CheckVisRgn(
              *((DXGPRESENT **)v7 + 19),
              (const struct _D3DKMT_PRESENT *)a2,
              v72,
              v73,
              *((const struct DXGDEVICE **)v7 + 2),
              v330,
              v332,
              Format,
              1);
      if ( v24 == 261 )
      {
        DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v344);
        COREDEVICEACCESS::Release(a3);
        DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v336);
        if ( DXGPRESENT::CheckOcclusion(*((DXGPRESENT **)v7 + 19)) )
          v24 = -1071775738;
        if ( (*((_DWORD *)a2 + 22) & 0x10000) == 0 )
          DXGPRESENTMUTEX::Acquire((DXGPRESENTMUTEX *)v344);
        DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v336);
        v92 = COREDEVICEACCESS::AcquireShared(a3, 0);
        if ( v92 < 0 )
        {
          WdLogSingleEntry1(4);
          v281 = a3;
          WdLogGlobalForLineNumber = 5469;
          goto LABEL_565;
        }
        if ( v24 != -1071775738 )
          v24 = DXGPRESENT::CheckVisRgn(
                  *((DXGPRESENT **)v7 + 19),
                  (const struct _D3DKMT_PRESENT *)a2,
                  v71,
                  v73,
                  *((const struct DXGDEVICE **)v7 + 2),
                  v330,
                  v332,
                  Format,
                  0);
      }
      v74 = *((_QWORD *)v7 + 19);
      if ( v24 < 0 )
      {
        v62 = a3;
        v69 = v333;
        if ( (*(_BYTE *)(v74 + 4) & 1) != 0 )
        {
          *(_QWORD *)(v74 + 56) = *(_QWORD *)v338;
          *(_DWORD *)(*((_QWORD *)v7 + 19) + 8LL) = v66;
        }
LABEL_115:
        v75 = *((_QWORD *)v7 + 19);
        v331 = 0;
        v76 = *(_DWORD *)(v75 + 4);
        if ( (v76 & 0x10) == 0 )
        {
          if ( v24 >= 0 && (v76 & 2) == 0 )
          {
            if ( (*((unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD))v339 + 30))(0, 0, 0) )
            {
              if ( (*((_DWORD *)a2 + 22) & 0x12100) != 0x10000 )
              {
                WdLogSingleEntry0(1);
                v301 = 5915;
                v302 = L"((pPresent->Flags.RedirectedBlt) && (!pPresent->Flags.RestrictVidPnSource) && (!pPresent->Flags.Rotate))";
LABEL_620:
                WdLogGlobalForLineNumber = v301;
                DxgkLogInternalTriageEvent(0, 262146, -1, (_DWORD)v302, v301, 0, 0, 0, 0);
              }
            }
            else if ( !*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) && (*((_DWORD *)a2 + 22) & 0x4000000) == 0 )
            {
              WdLogSingleEntry0(1);
              v301 = 5920;
              v302 = L"GetDisplayAdapter() != NULL || pPresent->Flags.CrossAdapter";
              goto LABEL_620;
            }
            if ( (*((_DWORD *)a2 + 22) & 0x10000) == 0 )
              goto LABEL_143;
            v84 = *(HDC *)v69;
            Current = DXGPROCESS::GetCurrent();
            v86 = DXGPROCESS::GetWin32kInterface(Current);
            v87 = v86;
            if ( !v84 || !v86 || *(_DWORD *)(*((_QWORD *)v7 + 19) + 440LL) != *((_DWORD *)a2 + 96) )
              goto LABEL_143;
            v88 = v336;
            DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v336);
            COREDEVICEACCESS::Release(a3);
            memset(v364, 0, 0x228u);
            LODWORD(v364[0]) = DXGPRESENT::GetDdiSubRectCnt(*((DXGPRESENT **)v7 + 19), 0);
            v364[1] = DXGPRESENT::GetDdiSubRectList(*((DXGPRESENT **)v7 + 19), 0);
            v89 = 1;
            v90 = 0;
            v364[3] = *((unsigned int *)v7 + 6);
            for ( LODWORD(v364[2]) = 1; (unsigned int)v90 < *((_DWORD *)a2 + 23); ++LODWORD(v364[2]) )
            {
              v303 = *((unsigned int *)a2 + v90 + 24);
              v90 = (unsigned int)(v90 + 1);
              v364[v89 + 3] = v303;
              v89 = LODWORD(v364[2]) + 1;
            }
            if ( !*((_BYTE *)v7 + 434)
              && VIDSCH_EXPORT::VidSchGetNumUnorderedWaitsInDevice(
                   *(VIDSCH_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 736LL),
                   *(struct _VIDSCH_DEVICE **)(*((_QWORD *)v7 + 2) + 800LL)) )
            {
              v331 = 1;
              LOBYTE(v364[68]) = 1;
            }
            (*((void (__fastcall **)(HDC, _QWORD *))v87 + 32))(v84, v364);
            DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v88);
            v91 = COREDEVICEACCESS::AcquireShared(a3, 0);
            v92 = v91;
            if ( v91 >= 0 )
            {
LABEL_143:
              for ( j = 0; ; ++j )
              {
                if ( (*((_DWORD *)a2 + 22) & 0x10000) != 0 )
                  v94 = 1;
                else
                  v94 = *(_DWORD *)(*((_QWORD *)v7 + 2) + 1904LL);
                if ( j >= v94 )
                  goto LABEL_174;
                v365.SubRectCnt = DXGPRESENT::GetDdiSubRectCnt(*((DXGPRESENT **)v7 + 19), j);
                if ( v365.SubRectCnt )
                {
                  if ( (*((_DWORD *)a2 + 22) & 0x10000) != 0 )
                  {
                    v95 = v329;
                  }
                  else
                  {
                    if ( *((_BYTE *)v7 + 432) || (v304 = 0, *((_BYTE *)v7 + 433)) )
                      v304 = 1;
                    v95 = DXGDEVICE::OpenCddPrimaryHandle(*((DXGDEVICE **)v7 + 2), j, v304, *((_DWORD *)v7 + 97));
                    v329 = v95;
                  }
                  if ( v95 )
                    break;
                }
LABEL_161:
                ;
              }
              v365.pDstSubRects = DXGPRESENT::GetDdiSubRectList(*((DXGPRESENT **)v7 + 19), j);
              if ( (*((_DWORD *)a2 + 22) & 0x2000) != 0 )
              {
                CurrentOrientation = ADAPTER_DISPLAY::GetCurrentOrientation(
                                       *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3232LL),
                                       j,
                                       1);
                v365.Flags.Value = v365.Flags.Value & 0xFFFFFF7F | (CurrentOrientation != 1 ? 0x80 : 0);
              }
              v370 = 0;
              if ( (*((_DWORD *)a2 + 22) & 0x10000) != 0 )
                v96 = &v370;
              else
                v96 = (struct tagRECT *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3232LL)
                                                   + 128LL)
                                       + 4024LL * j
                                       + 628);
              v97 = (RECT *)*((_QWORD *)v7 + 19);
              v365.SrcRect = v97[9];
              DXGPRESENT::GetDdiDstRect((DXGPRESENT *)v97, &v365.DstRect, v96);
              if ( !bTracingEnabled || !*((_QWORD *)v7 + 45) )
              {
LABEL_157:
                if ( *((_BYTE *)v7 + 434) )
                {
                  v306 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 16LL);
                  v307 = *((_DWORD *)v334 + 5);
                  v308 = *((_DWORD *)v327 + 5);
                  v309 = (struct DXGHWQUEUE **)*((_QWORD *)a2 + 188);
                  if ( v309 )
                    v310 = *v309;
                  else
                    v310 = 0;
                  v311 = DXGPROCESS::GetCurrent();
                  v99 = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendBlt(
                          (DXG_GUEST_VIRTUALGPU_VMBUS *)(v306 + 4776),
                          v311,
                          v7,
                          v310,
                          v308,
                          v307,
                          &v365.SrcRect,
                          &v365.DstRect,
                          v365.SubRectCnt,
                          v365.pDstSubRects,
                          v365.PrivateDriverDataSize,
                          (unsigned __int8 *)v365.pPrivateDriverData);
                  v98 = a3;
                }
                else
                {
                  v98 = a3;
                  v325 = Format;
                  v324 = v340;
                  *((_DWORD *)v340 + 29) = j;
                  v99 = DXGCONTEXT::SubmitPresent(
                          v7,
                          (const struct _D3DKMT_PRESENT *)a2,
                          *((struct DXGHWQUEUE ***)a2 + 188),
                          *((_DWORD *)a2 + 23),
                          v345,
                          v327,
                          v335,
                          v329,
                          &v365,
                          0,
                          *((struct VIDMM_DMA_BUFFER **)v7 + 45),
                          v324,
                          v325,
                          a3);
                }
                *((_QWORD *)v7 + 45) = 0;
                v24 = v99;
                if ( (*((_DWORD *)a2 + 22) & 0x10000) != 0
                  && *(_DWORD *)(*((_QWORD *)v7 + 19) + 440LL) == *((_DWORD *)a2 + 96) )
                {
                  *((_DWORD *)a2 + 90) = 3;
                  *((_QWORD *)a2 + 48) = *(_QWORD *)(*((_QWORD *)v7 + 19) + 440LL);
                  if ( v365.SubRectCnt <= 0x10 )
                  {
                    *((_DWORD *)a2 + 100) = v365.SubRectCnt;
                    for ( k = 0; k < v365.SubRectCnt; *(RECT *)((char *)a2 + 16 * v127 + 404) = v365.pDstSubRects[v127] )
                      v127 = k++;
                  }
                  else
                  {
                    *((_DWORD *)a2 + 100) = 1;
                    *(RECT *)((char *)a2 + 404) = v365.DstRect;
                  }
                  *((_DWORD *)a2 + 91) = 16 * (*((_DWORD *)a2 + 100) + 3);
                  DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v344);
                  v24 = SubmitPresentHistoryToken(
                          (const struct _D3DKMT_PRESENTHISTORYTOKEN *)((char *)a2 + 360),
                          v98,
                          v336,
                          v333,
                          0,
                          0,
                          a2,
                          0,
                          v7,
                          0,
                          0);
                }
                if ( v24 < 0 )
                  goto LABEL_174;
                goto LABEL_161;
              }
              v117 = (unsigned __int8)VIDMM_EXPORT::VidMmETWAllocationHandle(
                                        *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                                        *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 768LL),
                                        v329);
              v118 = VIDMM_EXPORT::VidMmETWAllocationHandle(
                       *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                       *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 768LL),
                       v335);
              pDstSubRects = v365.pDstSubRects;
              SubRectCnt = v365.SubRectCnt;
              *(_QWORD *)v338 = v118;
              v339 = (const struct _DXGKWIN32KENG_INTERFACE *)*((_QWORD *)v7 + 45);
              if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x20) != 0 )
                McTemplateK0ppxppttqddddddddq_EtwWriteTransfer(
                  (unsigned int)&DxgkControlGuid_Context,
                  (unsigned int)EventBlit,
                  0,
                  *((_QWORD *)a2 + 1),
                  (char)v339,
                  0,
                  v338[0],
                  v117,
                  1,
                  0,
                  *(_BYTE *)&v365.Flags.0,
                  v365.SrcRect.left,
                  v365.SrcRect.right,
                  v365.SrcRect.top,
                  v365.SrcRect.bottom,
                  v365.DstRect.left,
                  v365.DstRect.right,
                  v365.DstRect.top,
                  v365.DstRect.bottom,
                  v365.SubRectCnt);
              v121 = 0;
              if ( !SubRectCnt )
              {
LABEL_225:
                v328 = 1;
                goto LABEL_157;
              }
              v122 = (int)v339;
              while ( 1 )
              {
                v123 = 0;
                v124 = SubRectCnt - v121;
                if ( SubRectCnt - v121 > 0x10 )
                  break;
                v125 = SubRectCnt - v121;
                if ( v124 )
                  goto LABEL_220;
LABEL_221:
                if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x40) != 0 )
                  McTemplateK0ptqDR2DR2DR2DR2_EtwWriteTransfer(
                    (unsigned int)&DxgkControlGuid_Context,
                    (unsigned int)EventBlitRect,
                    0,
                    v122,
                    v124 <= 0x10,
                    v125,
                    (__int64)v384,
                    (__int64)v383,
                    (__int64)v382,
                    (__int64)v385);
                v121 += 16;
                if ( v121 >= SubRectCnt )
                {
                  v7 = v347;
                  goto LABEL_225;
                }
              }
              v125 = 16;
              do
              {
LABEL_220:
                v384[v123] = pDstSubRects[(unsigned int)v123 + v121].left;
                v383[v123] = pDstSubRects[(unsigned int)v123 + v121].right;
                v382[v123] = pDstSubRects[(unsigned int)v123 + v121].top;
                v385[v123] = pDstSubRects[(unsigned int)v123 + v121].bottom;
                v123 = (unsigned int)(v123 + 1);
              }
              while ( (unsigned int)v123 < v125 );
              goto LABEL_221;
            }
            WdLogSingleEntry2(4, v91);
            v281 = a3;
            WdLogGlobalForLineNumber = 5970;
LABEL_565:
            COREDEVICEACCESS::AcquireSharedUncheck(v281, 0);
            DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v344);
            v24 = v92;
            goto LABEL_34;
          }
          goto LABEL_174;
        }
        DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v344);
        if ( v24 < 0 )
        {
LABEL_174:
          v62 = a3;
LABEL_175:
          DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v344);
          if ( v331 )
          {
            CWin32kLocks::Unlock(v333);
            COREDEVICEACCESS::Release(v62);
            DXGDEVICE::FlushScheduler(*((_QWORD *)v7 + 2), 7, 4294967293LL);
            v24 = COREDEVICEACCESS::AcquireShared(v62, 0);
          }
          if ( *((_QWORD *)v7 + 45) )
          {
            if ( v24 >= 0
              && (((*((_BYTE *)a2 + 88) & 2) == 0)
                & (unsigned __int8)((*(_DWORD *)(*((_QWORD *)v7 + 19) + 4LL) >> 4)
                                  & ~(unsigned __int8)(*(_DWORD *)(*((_QWORD *)v7 + 19) + 4LL) >> 1))) != 0 )
            {
              WdLogSingleEntry0(1);
              WdLogGlobalForLineNumber = 6161;
              DxgkLogInternalTriageEvent(
                0,
                262146,
                -1,
                (unsigned int)L"!NT_SUCCESS(ntStatus) || !m_pPresent->BltViaGDI() || m_pPresent->IsBltEmpty() || pPresent-"
                               ">Flags.ColorFill",
                6161,
                0,
                0,
                0,
                0);
            }
            VIDMM_EXPORT::VidMmReleaseDmaBuffer(
              *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
              *((struct VIDMM_DMA_BUFFER **)v7 + 45));
            *((_QWORD *)v7 + 45) = 0;
          }
          if ( (*(_DWORD *)(*((_QWORD *)v7 + 19) + 4LL) & 0x80) != 0 )
          {
            if ( (unsigned int)(v24 + 1071775738) > 1 )
            {
              WdLogSingleEntry0(1);
              WdLogGlobalForLineNumber = 6169;
              DxgkLogInternalTriageEvent(
                0,
                262146,
                -1,
                (unsigned int)L"ntStatus == STATUS_GRAPHICS_PRESENT_OCCLUDED || ntStatus == STATUS_GRAPHICS_PRESENT_DENIED",
                6169,
                0,
                0,
                0,
                0);
            }
            v24 = 0;
          }
          DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v344);
          if ( v24 < 0 )
            goto LABEL_31;
          v60 = v328;
          goto LABEL_638;
        }
        if ( (*(_DWORD *)(*((_QWORD *)v7 + 19) + 4LL) & 2) == 0 && *((_DWORD *)a2 + 23) )
        {
          WdLogSingleEntry0(2);
          WdLogGlobalForLineNumber = 5564;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Present via GDI cannot be broadcasted",
            5564,
            0,
            0,
            0,
            0);
          v24 = -1071774910;
          goto LABEL_174;
        }
        if ( (*(_DWORD *)(*((_QWORD *)v7 + 19) + 4LL) & 2) != 0 )
          goto LABEL_174;
        if ( (*((_DWORD *)a2 + 22) & 0x10000) != 0 && *((_DWORD *)a2 + 6) )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 5570;
          DxgkLogInternalTriageEvent(
            0,
            262146,
            -1,
            (unsigned int)L"!pPresent->Flags.RedirectedBlt || pPresent->hDestination == NULL",
            5570,
            0,
            0,
            0,
            0);
        }
        v368 = 0;
        if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
          McTemplateK0q_EtwWriteTransfer(&DxgkControlGuid_Context, EventPerformanceWarning, 0, 0);
        v167 = *((_DWORD *)a2 + 22);
        if ( (v167 & 0x100) != 0 )
        {
          v100 = *(_OWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3232LL) + 128LL)
                           + 4024LL * *((unsigned int *)a2 + 4)
                           + 628);
          *(_QWORD *)v341 = &v368;
          v368 = v100;
        }
        else
        {
          *(_QWORD *)v341 = 0;
        }
        if ( (v167 & 1) != 0 )
        {
          v101 = 0;
          if ( (v167 & 0x80u) != 0 )
          {
            v284 = *((_DWORD *)a2 + 13);
            if ( v284 < 0 )
              v284 = 0;
            v365.SrcRect.top = v284;
            v285 = *((_DWORD *)a2 + 12);
            if ( v285 < 0 )
              v285 = 0;
            v365.SrcRect.left = v285;
            v286 = *((_DWORD *)a2 + 15);
            if ( (int)v332 < v286 )
              v286 = v332;
            v365.SrcRect.bottom = v286;
            v102 = *((_DWORD *)a2 + 14);
            if ( (int)v330 < v102 )
              v102 = v330;
          }
          else
          {
            v365.SrcRect.bottom = v332;
            v102 = v330;
            *(_QWORD *)&v365.SrcRect.left = 0;
          }
          v365.SrcRect.right = v102;
          v365.DstRect = v365.SrcRect;
          v365.Flags.Value = v365.Flags.Value & 0xFFFFF7FF | (*((_DWORD *)a2 + 22) >> 9) & 0x800;
          if ( !*((_DWORD *)a2 + 16) )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 5617;
            DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pPresent->SubRectCnt", 5617, 0, 0, 0, 0);
          }
          if ( !*((_QWORD *)a2 + 9) )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 5618;
            DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pPresent->pSrcSubRects", 5618, 0, 0, 0, 0);
          }
          v24 = DXGPRESENT::GrowRectList(*((DXGPRESENT **)v7 + 19), *((_DWORD *)a2 + 16));
          if ( v24 < 0 )
            goto LABEL_174;
          DdiSubRectList = DXGPRESENT::GetDdiSubRectList(*((DXGPRESENT **)v7 + 19), 0);
          v104 = 0;
          v105 = 0;
          v365.SubRectCnt = 0;
          v365.pDstSubRects = DdiSubRectList;
          if ( !*((_DWORD *)a2 + 16) )
            goto LABEL_174;
          while ( 1 )
          {
            if ( DXGPRESENT::IntersectRect(
                   &DdiSubRectList[v104],
                   (const struct tagRECT *)(*((_QWORD *)a2 + 9) + 16LL * v105),
                   &v365.SrcRect) )
            {
              v104 = ++v365.SubRectCnt;
            }
            else
            {
              v104 = v365.SubRectCnt;
            }
            if ( ++v105 >= *((_DWORD *)a2 + 16) )
              break;
            DdiSubRectList = (struct tagRECT *)v365.pDstSubRects;
          }
          if ( !(_DWORD)v104 )
            goto LABEL_174;
          if ( DXGPRESENT::PrepareStagingBuffer(
                 *((DXGPRESENT **)v7 + 19),
                 *((struct DXGDEVICE **)v7 + 2),
                 *((_DWORD *)a2 + 5),
                 v62,
                 &v329) < 0 )
            goto LABEL_266;
          if ( !*((_BYTE *)v7 + 434) )
          {
            v146 = v329;
            if ( !v329 )
            {
              WdLogSingleEntry0(1);
              WdLogGlobalForLineNumber = 5665;
              DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"hDestinationAllocation", 5665, 0, 0, 0, 0);
              v146 = v329;
            }
            if ( !bTracingEnabled )
              goto LABEL_271;
            v193 = (unsigned __int8)VIDMM_EXPORT::VidMmETWAllocationHandle(
                                      *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                                      *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 768LL),
                                      v146);
            v194 = (unsigned __int8)VIDMM_EXPORT::VidMmETWAllocationHandle(
                                      *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                                      *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 768LL),
                                      v335);
            v195 = v365.pDstSubRects;
            v196 = v365.SubRectCnt;
            *(_QWORD *)v338 = *((_QWORD *)v7 + 45);
            if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x20) != 0 )
              McTemplateK0ppxppttqddddddddq_EtwWriteTransfer(
                (unsigned int)&DxgkControlGuid_Context,
                (unsigned int)EventBlit,
                0,
                *((_QWORD *)a2 + 1),
                v338[0],
                0,
                v194,
                v193,
                1,
                0,
                *(_BYTE *)&v365.Flags.0,
                v365.SrcRect.left,
                v365.SrcRect.right,
                v365.SrcRect.top,
                v365.SrcRect.bottom,
                v365.DstRect.left,
                v365.DstRect.right,
                v365.DstRect.top,
                v365.DstRect.bottom,
                v365.SubRectCnt);
            v197 = 0;
            if ( !v196 )
            {
LABEL_343:
              v146 = v329;
              v101 = 0;
              v62 = a3;
              v328 = 1;
LABEL_271:
              v147 = DXGCONTEXT::SubmitPresent(
                       v7,
                       (const struct _D3DKMT_PRESENT *)a2,
                       *((struct DXGHWQUEUE ***)a2 + 188),
                       *((_DWORD *)a2 + 23),
                       v345,
                       v327,
                       v335,
                       v146,
                       &v365,
                       0,
                       *((struct VIDMM_DMA_BUFFER **)v7 + 45),
                       v340,
                       Format,
                       v62);
              *((_QWORD *)v7 + 45) = 0;
              goto LABEL_272;
            }
            v198 = v338[0];
            while ( 1 )
            {
              v199 = 0;
              v200 = v196 - v197;
              if ( v196 - v197 > 0x10 )
                break;
              v201 = v196 - v197;
              if ( v200 )
                goto LABEL_338;
LABEL_339:
              if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x40) != 0 )
                McTemplateK0ptqDR2DR2DR2DR2_EtwWriteTransfer(
                  (unsigned int)&DxgkControlGuid_Context,
                  (unsigned int)EventBlitRect,
                  0,
                  v198,
                  v200 <= 0x10,
                  v201,
                  (__int64)v380,
                  (__int64)v379,
                  (__int64)v378,
                  (__int64)v377);
              v197 += 16;
              if ( v197 >= v196 )
              {
                v7 = v347;
                goto LABEL_343;
              }
            }
            v201 = 16;
            do
            {
LABEL_338:
              v380[v199] = v195[(unsigned int)v199 + v197].left;
              v379[v199] = v195[(unsigned int)v199 + v197].right;
              v378[v199] = v195[(unsigned int)v199 + v197].top;
              v377[v199] = v195[(unsigned int)v199 + v197].bottom;
              v199 = (unsigned int)(v199 + 1);
            }
            while ( (unsigned int)v199 < v201 );
            goto LABEL_339;
          }
          v178 = DXGPROCESS::GetCurrent();
          v179 = v329;
          v180 = v178;
          DXGPUSHLOCK::AcquireShared((struct DXGPROCESS *)((char *)v178 + 248));
          v181 = (v179 >> 6) & 0xFFFFFF;
          if ( (unsigned int)v181 < *((_DWORD *)v180 + 74) )
          {
            v182 = *((_QWORD *)v180 + 35);
            v183 = *(_DWORD *)(v182 + 16 * v181 + 8);
            if ( ((v179 >> 25) & 0x60) == (v183 & 0x60) && (v183 & 0x2000) == 0 && (v183 & 0x1F) != 0 )
            {
              if ( (*(_BYTE *)(v182 + 16 * (((unsigned __int64)v179 >> 6) & 0xFFFFFF) + 8) & 0x1F) == 5 )
              {
                v184 = *(struct DXGALLOCATION **)(v182 + 16 * (((unsigned __int64)v179 >> 6) & 0xFFFFFF));
                goto LABEL_325;
              }
              WdLogSingleEntry0(2);
              WdLogGlobalForLineNumber = 318;
              DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
            }
          }
          v184 = 0;
LABEL_325:
          DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v346, v184);
          _InterlockedDecrement((volatile signed __int32 *)v180 + 66);
          ExReleasePushLockSharedEx((char *)v180 + 248, 0);
          KeLeaveCriticalRegion();
          v185 = v346;
          if ( !v346 )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 5650;
            DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"AllocRef.m_pAllocation != NULL", 5650, 0, 0, 0, 0);
            v185 = v346;
          }
          v186 = *(_DWORD *)(v185 + 20);
          v187 = (unsigned __int8 *)*((_QWORD *)a2 + 185);
          v188 = *((_DWORD *)a2 + 368);
          v189 = *(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL);
          v338[0] = *((_DWORD *)v327 + 5);
          v190 = (struct DXGHWQUEUE **)*((_QWORD *)a2 + 188);
          v191 = *(_QWORD *)(v189 + 16);
          if ( v190 )
            v192 = *v190;
          else
            v192 = 0;
          v287 = DXGPROCESS::GetCurrent();
          v147 = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendBlt(
                   (DXG_GUEST_VIRTUALGPU_VMBUS *)(v191 + 4776),
                   v287,
                   v7,
                   v192,
                   v338[0],
                   v186,
                   &v365.SrcRect,
                   &v365.DstRect,
                   v365.SubRectCnt,
                   v365.pDstSubRects,
                   v188,
                   v187);
          DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v346);
          v62 = a3;
          v101 = 0;
LABEL_272:
          if ( v147 < 0 )
          {
LABEL_266:
            WdLogSingleEntry2(3, -1071775738);
            WdLogGlobalForLineNumber = 5847;
            v24 = -1071775738;
            goto LABEL_174;
          }
          v148 = (DXGDEVICE *)*((_QWORD *)v7 + 2);
          if ( (*((_DWORD *)a2 + 22) & 0x100) != 0
            && ADAPTER_DISPLAY::IsVidPnSourceOwner(
                 *(ADAPTER_DISPLAY **)(*((_QWORD *)v148 + 237) + 3232LL),
                 *((const struct DXGDEVICE **)v7 + 2),
                 *((_DWORD *)a2 + 4)) )
          {
            v101 = 1;
          }
          else if ( !DXGDEVICE::AllowLegacyPresent(v148, 0) )
          {
            v149 = 0;
            v101 = 0;
LABEL_276:
            DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v336);
            COREDEVICEACCESS::Release(v62);
            if ( !v149 && DXGPRESENT::CheckOcclusion(*((DXGPRESENT **)v7 + 19)) )
            {
              COREDEVICEACCESS::AcquireSharedUncheck(v62, 0);
              v24 = -1071775738;
              goto LABEL_174;
            }
            v150 = v333;
            CWin32kLocks::Unlock(v333);
            v151 = v336;
            DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v336);
            v24 = COREDEVICEACCESS::AcquireShared(v62, 0);
            if ( v24 >= 0 )
            {
              memset(&v360, 0, sizeof(v360));
              if ( *((_BYTE *)v7 + 434) )
              {
                memset(&v358, 0, sizeof(v358));
                v358.hAllocation = v329;
                v152 = (struct DXGDEVICE *)*((_QWORD *)v7 + 2);
                v153 = *(_QWORD *)(*((_QWORD *)v152 + 2) + 16LL);
                v154 = DXGPROCESS::GetCurrent();
                v155 = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendLock2(
                         (DXG_GUEST_VIRTUALGPU_VMBUS *)(v153 + 4776),
                         v154,
                         v152,
                         &v358,
                         0,
                         0,
                         0);
                v62 = a3;
                v24 = v155;
                v151 = v336;
                v360.pData = v358.pData;
              }
              else
              {
                v288 = v329;
                if ( !v329 )
                {
                  WdLogSingleEntry0(1);
                  WdLogGlobalForLineNumber = 5743;
                  DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"hDestinationAllocation", 5743, 0, 0, 0, 0);
                  v288 = v329;
                }
                v360.hAllocation = v288;
                v24 = DXGDEVICE::Lock(*((DXGDEVICE **)v7 + 2), &v360, v62, 0);
              }
              if ( v24 < 0 )
                goto LABEL_174;
              DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v151);
              COREDEVICEACCESS::Release(v62);
              if ( !v360.pData )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 5756;
                DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"LockData.pData", 5756, 0, 0, 0, 0);
              }
              if ( (*((_DWORD *)a2 + 22) & 0x10000) != 0 && *((_DWORD *)a2 + 6) )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 5757;
                DxgkLogInternalTriageEvent(
                  0,
                  262146,
                  -1,
                  (unsigned int)L"!pPresent->Flags.RedirectedBlt || pPresent->hDestination == NULL",
                  5757,
                  0,
                  0,
                  0,
                  0);
              }
              v156 = v339;
              v157 = (*((__int64 (__fastcall **)(_QWORD))v339 + 40))(0);
              v24 = CWin32kLocks::Lock(v150, *((HWND *)a2 + 1), 0, 0, v101 & (unsigned int)-(v157 != 0));
              if ( v24 >= 0 )
              {
                v162 = (unsigned int (__fastcall *)(const struct DXGK_PRESENT_PARAMS *, HDC, _QWORD, const RECT *, void *, int, unsigned int, unsigned int, int, int, int, void (__fastcall *)(const struct tagRECT *, const struct tagRECT *, struct tagRECT *, const struct tagRECT *, unsigned int, unsigned int), __int64 (__fastcall *)(struct tagRECT *, struct tagRECT *, const struct tagRECT *, const struct tagRECT *)))*((_QWORD *)v156 + 18);
                v163 = *(_DWORD *)(*((_QWORD *)v7 + 19) + 424LL);
                v164 = *((_DWORD *)a2 + 7);
                v165 = (*((_DWORD *)a2 + 22) & 0x200) != 0;
                v166 = CWin32kLocks::hDestDc(v333);
                LOBYTE(v323) = v165;
                LOBYTE(v321) = 0;
                if ( !v162(
                        a2,
                        v166,
                        *(_QWORD *)v341,
                        v365.pDstSubRects,
                        v360.pData,
                        v163,
                        v330,
                        v332,
                        v321,
                        v323,
                        v164,
                        DXGPRESENT::XformRect,
                        DXGPRESENT::ClipRects) )
                {
                  v24 = -1071775737;
                  WdLogSingleEntry2(4, -1071775737);
                  WdLogGlobalForLineNumber = 5768;
                }
                v150 = v333;
                v62 = a3;
              }
              v158 = v336;
              DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v336);
              v92 = COREDEVICEACCESS::AcquireShared(v62, 0);
              if ( v92 >= 0 )
              {
                if ( *((_BYTE *)v7 + 434) )
                {
                  v353.hDevice = 0;
                  v353.hAllocation = v329;
                  v159 = (struct DXGDEVICE *)*((_QWORD *)v7 + 2);
                  v160 = *(_QWORD *)(*((_QWORD *)v159 + 2) + 16LL);
                  v161 = DXGPROCESS::GetCurrent();
                  DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendUnlock2(
                    (DXG_GUEST_VIRTUALGPU_VMBUS *)(v160 + 4776),
                    v161,
                    v159,
                    &v353,
                    0);
                  v62 = a3;
                }
                else
                {
                  v354.hDevice = 0;
                  v354.NumAllocations = 1;
                  v354.phAllocations = &v360.hAllocation;
                  DXGDEVICE::Unlock(*((DXGDEVICE **)v7 + 2), &v354, 0);
                }
                if ( v24 >= 0 && (*((_DWORD *)a2 + 22) & 0x10000) != 0 )
                {
                  *((_DWORD *)a2 + 90) = 3;
                  *((_QWORD *)a2 + 48) = *(_QWORD *)(*((_QWORD *)v7 + 19) + 440LL);
                  *((_DWORD *)a2 + 100) = 0;
                  *((_DWORD *)a2 + 91) = 48;
                  DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v344);
                  v24 = SubmitPresentHistoryToken(
                          (const struct _D3DKMT_PRESENTHISTORYTOKEN *)((char *)a2 + 360),
                          v62,
                          v158,
                          v150,
                          0,
                          0,
                          a2,
                          0,
                          v7,
                          0,
                          0);
                }
                goto LABEL_174;
              }
LABEL_600:
              v281 = v62;
              goto LABEL_565;
            }
            goto LABEL_476;
          }
          v149 = 1;
          goto LABEL_276;
        }
        if ( (v167 & 2) == 0 )
          goto LABEL_174;
        v289 = (DXGDEVICE *)*((_QWORD *)v7 + 2);
        if ( (v167 & 0x100) != 0
          && ADAPTER_DISPLAY::IsVidPnSourceOwner(
               *(ADAPTER_DISPLAY **)(*((_QWORD *)v289 + 237) + 3232LL),
               *((const struct DXGDEVICE **)v7 + 2),
               *((_DWORD *)a2 + 4)) )
        {
          v290 = 1;
        }
        else
        {
          v290 = 0;
          v291 = DXGDEVICE::AllowLegacyPresent(v289, 0);
          v292 = 0;
          if ( !v291 )
            goto LABEL_607;
        }
        v292 = 1;
LABEL_607:
        DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v336);
        COREDEVICEACCESS::Release(a3);
        if ( v292 || !DXGPRESENT::CheckOcclusion(*((DXGPRESENT **)v7 + 19)) )
        {
          if ( (*((_DWORD *)a2 + 22) & 0x10000) != 0 )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 5877;
            DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"!pPresent->Flags.RedirectedBlt", 5877, 0, 0, 0, 0);
          }
          CWin32kLocks::Unlock(v69);
          v293 = v339;
          v294 = (*((__int64 (__fastcall **)(_QWORD))v339 + 40))(0);
          v295 = CWin32kLocks::Lock(v69, *((HWND *)a2 + 1), 0, 0, v290 & (unsigned int)-(v294 != 0));
          v296 = (unsigned int (__fastcall *)(HDC, _QWORD, __int64, _QWORD, _DWORD))*((_QWORD *)v293 + 19);
          v24 = v295;
          LODWORD(v293) = *((_DWORD *)a2 + 7);
          v297 = *((_DWORD *)a2 + 16);
          v298 = *((_QWORD *)a2 + 9);
          v299 = CWin32kLocks::hDestDc(v333);
          if ( !v296(v299, *(_QWORD *)v341, v298, v297, (_DWORD)v293) )
          {
            v24 = -1071775737;
            WdLogSingleEntry2(4, -1071775737);
            WdLogGlobalForLineNumber = 5887;
          }
        }
        else
        {
          v24 = -1071775738;
        }
        DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v336);
        v62 = a3;
        v300 = COREDEVICEACCESS::AcquireShared(a3, 0);
        v92 = v300;
        if ( v300 >= 0 )
          goto LABEL_175;
        WdLogSingleEntry2(4, v300);
        WdLogGlobalForLineNumber = 5896;
        goto LABEL_600;
      }
      *(_QWORD *)(v74 + 56) = *(_QWORD *)v338;
      if ( (*((_DWORD *)a2 + 22) & 0x10000) == 0 )
      {
        *(_DWORD *)(*((_QWORD *)v7 + 19) + 8LL) = v66;
        DXGDEVICE::FlushScheduler(*((_QWORD *)v7 + 2), 2, 4294967293LL);
        v282 = 0;
        v283 = *(_DWORD *)(*((_QWORD *)v7 + 19) + 8LL);
        if ( v283 != (*((unsigned int (**)(void))v339 + 1))() )
        {
          *(_DWORD *)(*((_QWORD *)v7 + 19) + 8LL) = v66;
          ADAPTER_RENDER::FlushScheduler(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL), 3, 0xFFFFFFFFLL);
          v282 = 1;
        }
        DXGDEVICE::SynchronizePresentToPrimary(*((DXGDEVICE **)v7 + 2), v7, (struct DXGPRESENTMUTEX *)v344, v282);
      }
      v62 = a3;
LABEL_571:
      v69 = v333;
      goto LABEL_115;
    }
LABEL_476:
    COREDEVICEACCESS::AcquireSharedUncheck(v62, 0);
LABEL_477:
    v256 = (DXGPRESENTMUTEX *)v344;
    goto LABEL_478;
  }
  if ( !(_DWORD)v21 )
  {
    if ( (v22 & 0x10A7C3) != 0 )
    {
      v24 = -1073741811;
      WdLogSingleEntry3(3, v7, *((unsigned int *)a2 + 22), -1073741811);
      WdLogGlobalForLineNumber = 4477;
      goto LABEL_34;
    }
    if ( (v22 & 0x10000000) != 0 )
    {
      v31 = *((_QWORD *)v20 + 5);
      if ( v31 && *(_QWORD *)(v31 + 56) )
      {
        v32 = *(DXGADAPTER **)(*((_QWORD *)v7 + 2) + 1896LL);
        if ( v32 )
        {
          if ( DXGADAPTER::IsDisplayAdapter(v32) )
          {
            v33 = *((_DWORD *)a2 + 4);
            if ( v33 < *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3232LL) + 96LL) )
            {
              v20 = v327;
LABEL_45:
              DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v351, v20);
              DXGALLOCATIONREFERENCE::MoveAssign(&v343, v351);
              DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v351);
              v342 = *((_DWORD *)a2 + 5);
              v34 = *(DXGADAPTER **)(*((_QWORD *)v7 + 2) + 1896LL);
              if ( !v34
                || !DXGADAPTER::IsDisplayAdapter(v34)
                || !ADAPTER_DISPLAY::IsCoreResourceSharedOwner(*(ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)v7 + 2)
                                                                                               + 1896LL)
                                                                                   + 3232LL)) )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 4528;
                DxgkLogInternalTriageEvent(
                  0,
                  262146,
                  -1,
                  (unsigned int)L"(GetDisplayAdapter(VidPnSourceId) == GetDisplayAdapter(0)) && (GetDisplayAdapter(VidPnSo"
                                 "urceId) != NULL) && GetDisplayAdapter(VidPnSourceId)->IsDisplayAdapter() && GetDisplayA"
                                 "dapter(VidPnSourceId)->GetDisplayCore()->IsCoreResourceSharedOwner()",
                  4528,
                  0,
                  0,
                  0,
                  0);
              }
              v35 = *((_QWORD *)v327 + 6);
              v36 = *(_DWORD *)(v35 + 4);
              if ( (v36 & 0x2000) != 0 && (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 40LL) + 408LL) & 4) == 0 )
              {
                v24 = -1073741811;
                WdLogSingleEntry5(2, -1073741811, v7, v327, v35, *((unsigned int *)a2 + 5));
                WdLogGlobalForLineNumber = 4536;
                v78 = L"0x%I64x 0x%I64x DirectFlip Presents are only supported from the DWM process 0x%I64x 0x%I64x 0x%I64x";
                v320 = *((unsigned int *)a2 + 5);
                v318 = *((_QWORD *)v327 + 6);
                v316 = (__int64)v327;
                v314 = (__int64)v7;
                v312 = -1073741811;
                goto LABEL_120;
              }
              v37 = *((_DWORD *)a2 + 22);
              if ( (v37 & 0x40000) == 0 && (v37 & 0x20000) == 0 )
                goto LABEL_51;
              if ( (v37 & 0x20000) != 0 && (v37 & 0x40000) != 0 )
              {
                WdLogSingleEntry0(2);
                v244 = 4547;
                v240 = L"FlipStereoTemporaryMono and FlipStereo cannot be set together. STATUS_INVALID_PARAMETER";
              }
              else if ( (v36 & 0x1000) != 0 )
              {
                v245 = *((_DWORD *)ADAPTER_DISPLAY::GetDisplayModeInfo(
                                     *(ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3232LL),
                                     v33)
                       + 10);
                if ( (v245 & 0x10) == 0 )
                {
                  WdLogSingleEntry0(3);
                  WdLogGlobalForLineNumber = 4560;
                  goto LABEL_452;
                }
                v246 = *((_DWORD *)a2 + 22);
                if ( (v245 & 0x20) == 0 && (v246 & 0x40000) != 0 )
                {
                  WdLogSingleEntry0(3);
                  WdLogGlobalForLineNumber = 4566;
                  goto LABEL_452;
                }
                if ( (v246 & 0xC0000) != 0xC0000 )
                {
LABEL_51:
                  IsFullWDDMDevice = DXGDEVICE::IsFullWDDMDevice(*((DXGDEVICE **)v7 + 2), v33);
                  v39 = v340;
                  if ( !IsFullWDDMDevice )
                  {
                    v26 = a3;
                    goto LABEL_53;
                  }
                  v130 = *(_DWORD *)v340 ^ (*((_DWORD *)a2 + 22) ^ *(_DWORD *)v340) & 4;
                  *(_DWORD *)v340 = v130;
                  v131 = v130 ^ (*((_DWORD *)a2 + 22) ^ v130) & 8;
                  *(_DWORD *)v39 = v131;
                  v132 = v131 ^ ((unsigned __int8)v131 ^ (unsigned __int8)(*((_DWORD *)a2 + 22) >> 1)) & 0x10;
                  *(_DWORD *)v39 = v132;
                  v133 = v132 ^ (v132 ^ (4 * *((_DWORD *)a2 + 22))) & 0x80000;
                  *(_DWORD *)v39 = v133;
                  v134 = v133 ^ (v133 ^ (4 * *((_DWORD *)a2 + 22))) & 0x100000;
                  *(_DWORD *)v39 = v134;
                  v135 = v134 ^ (v134 ^ (4 * *((_DWORD *)a2 + 22))) & 0x200000;
                  *(_DWORD *)v39 = v135;
                  if ( (*((_DWORD *)a2 + 22) & 0x8000000) != 0 )
                    v136 = *((_DWORD *)a2 + 363);
                  else
                    v136 = 0;
                  *((_DWORD *)v39 + 36) = v136;
                  *((_DWORD *)v39 + 38) = 1;
                  *(_DWORD *)v39 = v135 ^ (*((_DWORD *)a2 + 22) ^ v135) & 0x20000000;
                  v137 = *((_DWORD *)a2 + 22) >> 9;
                  v138 = *((_DWORD *)a2 + 22) & 4 | v365.Flags.Value & 0xFFFFFFFB;
                  v139 = v138
                       ^ ((unsigned __int16)v138
                        ^ (unsigned __int16)v137)
                       & 0x100
                       ^ ((unsigned __int16)v137
                        ^ (unsigned __int16)(v138 ^ (v138 ^ v137) & 0x100))
                       & 0x200;
                  v365.Flags.Value = v139 ^ (v137 ^ v139) & 0x400;
                  v140 = *((_QWORD *)a2 + 180);
                  if ( v140
                    && !*(_DWORD *)(v140 + 16)
                    && (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 40LL) + 408LL) & 4) != 0 )
                  {
                    v365.SubRectCnt = *(_DWORD *)v140;
                    v365.pDstSubRects = *(const RECT **)(v140 + 8);
                  }
                  v141 = (D3DDDI_FLIPINTERVAL_TYPE *)((char *)a2 + 84);
                  DeviceFlipMode = VIDSCH_EXPORT::VidSchGetDeviceFlipMode(
                                     *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 736LL),
                                     *(_QWORD *)(*((_QWORD *)v7 + 2) + 800LL),
                                     v33,
                                     (char *)a2 + 84);
                  *((_DWORD *)v39 + 30) = DeviceFlipMode;
                  if ( !DeviceFlipMode )
                  {
                    v24 = -1073741811;
                    WdLogSingleEntry3(3, v7, *(int *)v141, -1073741811);
                    WdLogGlobalForLineNumber = 4619;
                    goto LABEL_34;
                  }
                  if ( ((DeviceFlipMode - 1) & 0xFFFFFFFD) != 0 )
                  {
                    v365.FlipInterval = *v141;
                    if ( DeviceFlipMode == 2 )
                    {
LABEL_255:
                      *((D3DDDI_FLIPINTERVAL_TYPE *)v39 + 31) = *v141;
                      *((_DWORD *)v39 + 29) = v33;
                      DisplayedPrimary = DXGDEVICE::GetDisplayedPrimary(*((DXGDEVICE **)v7 + 2), v33);
                      if ( DisplayedPrimary )
                      {
                        v144 = *((_QWORD *)DisplayedPrimary + 6);
                        if ( _bittest((const signed __int32 *)(*((_QWORD *)v327 + 6) + 4LL), 0xDu) )
                        {
                          if ( !_bittest((const signed __int32 *)(v144 + 4), 0xDu) )
                            goto LABEL_258;
                        }
                        else if ( _bittest((const signed __int32 *)(v144 + 4), 0xDu) )
                        {
LABEL_258:
                          *(_DWORD *)v39 |= 0x400000u;
                          goto LABEL_259;
                        }
                      }
                      *(_DWORD *)v39 &= ~0x400000u;
LABEL_259:
                      v145 = *((_DWORD *)v39 + 30);
                      if ( !v145 || v145 == *(_DWORD *)(*((_QWORD *)v7 + 2) + 4LL * v33 + 1832) )
                      {
                        v26 = a3;
LABEL_262:
                        v18 = v330;
LABEL_53:
                        v28 = DXGCONTEXT::CheckDevicePresentSettings(
                                v7,
                                (*((_DWORD *)a2 + 22) >> 2) & 1,
                                (*((_DWORD *)a2 + 22) >> 28) & 1,
                                0,
                                v33);
                        if ( v28 < 0 )
                        {
                          if ( v28 == -1071774920 )
                          {
                            if ( (*((_DWORD *)a2 + 22) & 4) != 0 )
                            {
                              v247 = DXGDEVICE::IsFullWDDMDevice(*((DXGDEVICE **)v7 + 2), v33);
                              v248 = (DXGDEVICE *)*((_QWORD *)v7 + 2);
                              v249 = v33;
                              if ( v247 )
                              {
                                DXGDEVICE::ClearDisplayedAllMultiPlaneOverlaysUnsafe(v248, v33);
                                DXGDEVICE::SetDisplayedPrimary(
                                  *((DXGDEVICE **)v7 + 2),
                                  v33,
                                  v327,
                                  *((_DWORD *)v39 + 34),
                                  1u);
                                v250 = *((_DWORD *)v39 + 30);
LABEL_498:
                                *(_DWORD *)(*((_QWORD *)v7 + 2) + 4LL * v33 + 1832) = v250;
                                goto LABEL_500;
                              }
LABEL_499:
                              DXGDEVICE::SetDisplayedPrimary(v248, v249, v327, 0, 1u);
                            }
LABEL_500:
                            v24 = 0;
                            goto LABEL_34;
                          }
                        }
                        else if ( (*((_DWORD *)a2 + 22) & 4) == 0
                               || !*((_QWORD *)a2 + 180)
                               || (v28 = DXGCONTEXT::ValidatePresentRegions(
                                           v7,
                                           (const struct _D3DKMT_PRESENT *)a2,
                                           v18,
                                           v332),
                                   v28 >= 0) )
                        {
                          if ( !ADAPTER_DISPLAY::GetCddPrimaryAllocation(
                                  *(ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3232LL),
                                  v33,
                                  0) )
                          {
                            if ( (*(_DWORD *)(*((_QWORD *)v7 + 2) + 4LL * v33 + 1240) & 0x200) == 0
                              && (*((_DWORD *)a2 + 22) & 0x10000000) == 0 )
                            {
                              WdLogSingleEntry5(3, -1071775739, v7, *((unsigned int *)a2 + 5), v327, v33);
                              WdLogGlobalForLineNumber = 4818;
                              goto LABEL_452;
                            }
LABEL_57:
                            if ( !DXGDEVICE::IsFullWDDMDevice(*((DXGDEVICE **)v7 + 2), v33) )
                            {
                              v40 = *((_QWORD *)v7 + 2);
                              if ( !*(_QWORD *)(v40 + 1896) )
                              {
                                WdLogSingleEntry2(1, v40);
                                v322 = 0;
                                v240 = L"DxgkPresent is called for flip on a render only device 0x%I64x, returning 0x%I64x.";
                                v319 = 0;
                                v243 = 262146;
                                v317 = 0;
                                WdLogGlobalForLineNumber = 5129;
                                v315 = -1073741822;
                                v313 = (struct _DXGKARG_PRESENT *)*((_QWORD *)v7 + 2);
                                goto LABEL_442;
                              }
                              *(_QWORD *)&v366.right = 0;
                              *(_QWORD *)&v366.left = 0;
                              v41 = *((_DWORD *)a2 + 22);
                              if ( (v41 & 0x10000000) != 0 )
                              {
                                v366.right = *((_DWORD *)a2 + 379);
                                v42 = *((_DWORD *)a2 + 380);
                                goto LABEL_61;
                              }
                              v269 = v334;
                              if ( (v41 & 4) != 0 )
                                v269 = v327;
                              v270 = *(_DWORD *)(*((_QWORD *)v269 + 6) + 4LL);
                              if ( (v270 & 0x10) != 0 )
                              {
                                WdLogSingleEntry3(4, -1071775482, v7, v269);
                                WdLogGlobalForLineNumber = 5049;
                                v24 = -1071775482;
                                goto LABEL_34;
                              }
                              v271 = *(_OWORD *)ADAPTER_DISPLAY::GetDisplayModeInfo(
                                                  *(ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL)
                                                                      + 3232LL),
                                                  (v270 >> 6) & 0xF);
                              v355.Flags.Value = 1;
                              memset(&v355, 0, 40);
                              v355.Rotation = -1;
                              v272 = *((_QWORD *)v269 + 6);
                              *(_OWORD *)v362 = v271;
                              v355.hAllocation = *(HANDLE *)(v272 + 16);
                              v273 = ADAPTER_RENDER::DdiDescribeAllocation(
                                       *(ADAPTER_RENDER **)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 16LL)
                                                          + 3240LL),
                                       &v355);
                              if ( v273 >= 0 )
                              {
                                v274 = v355.Width;
                                if ( v355.Width != v362[0] || (v42 = v355.Height, v355.Height != v362[1]) )
                                {
                                  WdLogSingleEntry3(4, -1071775482, v7, v269);
                                  WdLogGlobalForLineNumber = 5080;
                                  goto LABEL_452;
                                }
                                if ( *((_BYTE *)v7 + 434) )
                                  goto LABEL_527;
                                v275 = RemoveAlphaChannel(v362[2]);
                                if ( RemoveAlphaChannel(v355.Format) == v275 )
                                {
                                  v42 = v355.Height;
                                  v274 = v355.Width;
LABEL_527:
                                  v366.right = v274;
LABEL_61:
                                  v366.bottom = v42;
                                  v24 = ADAPTER_DISPLAY::PresentDisplayOnly(
                                          *(ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3232LL),
                                          v7,
                                          v33,
                                          (const struct _D3DKMT_PRESENT *)a2,
                                          &v365,
                                          v26,
                                          &v366);
                                  if ( v24 >= 0 )
                                  {
                                    if ( (*((_DWORD *)a2 + 22) & 4) == 0 )
                                    {
LABEL_63:
                                      v23 = 2;
                                      goto LABEL_30;
                                    }
                                    DXGDEVICE::ClearDisplayedAllMultiPlaneOverlaysUnsafe(*((DXGDEVICE **)v7 + 2), v33);
                                    DXGDEVICE::SetDisplayedPrimary(*((DXGDEVICE **)v7 + 2), v33, v327, 0, 1u);
LABEL_516:
                                    UpdatePostComposition(
                                      v33,
                                      0,
                                      0,
                                      0,
                                      *(struct ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3232LL));
                                    goto LABEL_63;
                                  }
LABEL_31:
                                  if ( !ADAPTER_RENDER::IsCoreResourceSharedOwner(*(ADAPTER_RENDER **)(*((_QWORD *)v7 + 2) + 16LL))
                                    && v24 != -1073741130 )
                                  {
                                    WdLogSingleEntry0(1);
                                    WdLogGlobalForLineNumber = 6285;
                                    DxgkLogInternalTriageEvent(
                                      0,
                                      262146,
                                      -1,
                                      (unsigned int)L"GetRenderCore()->IsCoreResourceSharedOwner() || ntStatus == STATUS_DEVICE_REMOVED",
                                      6285,
                                      0,
                                      0,
                                      0,
                                      0);
                                  }
                                  if ( *((_QWORD *)v7 + 45) )
                                  {
                                    WdLogSingleEntry0(1);
                                    WdLogGlobalForLineNumber = 6286;
                                    DxgkLogInternalTriageEvent(
                                      0,
                                      262146,
                                      -1,
                                      (unsigned int)L"m_pPresentDmaBuffer == NULL",
                                      6286,
                                      0,
                                      0,
                                      0,
                                      0);
                                  }
                                  goto LABEL_34;
                                }
                                WdLogSingleEntry3(4, -1071775482, v7, v269);
                                WdLogGlobalForLineNumber = 5094;
LABEL_452:
                                v24 = -1071775739;
                                goto LABEL_34;
                              }
                              v242 = (struct _DXGKARG_PRESENT *)v273;
                              WdLogSingleEntry5(
                                2,
                                v273,
                                v7,
                                *((unsigned int *)v269 + 4),
                                v269,
                                (*(_DWORD *)(*((_QWORD *)v269 + 6) + 4LL) >> 6) & 0xF);
                              WdLogGlobalForLineNumber = 5071;
                              v240 = L"ret = 0x%I64x Device 0x%I64x: DdiDescribeAllocation failed 0x%I64x 0x%I64x 0x%I64x";
                              v322 = (*(_DWORD *)(*((_QWORD *)v269 + 6) + 4LL) >> 6) & 0xF;
                              v319 = (__int64)v269;
                              v317 = *((unsigned int *)v269 + 4);
                              v315 = (__int64)v7;
                              v313 = v242;
LABEL_438:
                              v243 = 0x40000;
LABEL_442:
                              DxgkLogInternalTriageEvent(
                                0,
                                v243,
                                -1,
                                (_DWORD)v240,
                                (__int64)v313,
                                v315,
                                v317,
                                v319,
                                v322);
                              goto LABEL_416;
                            }
                            v128 = DXGCONTEXT::WaitForQueuedPresentLimit(
                                     v7,
                                     v33,
                                     (*((_DWORD *)a2 + 22) & 0x10) == 0,
                                     v26);
                            v24 = v128;
                            if ( v128 < 0 )
                            {
                              WdLogSingleEntry2(4, v128);
                              WdLogGlobalForLineNumber = 4833;
                              goto LABEL_34;
                            }
                            v129 = v340;
                            if ( ((*((_DWORD *)v340 + 30) - 3) & 0xFFFFFFFD) != 0 )
                            {
                              v24 = DXGCONTEXT::AcquireDmaBuffer(v7, (struct VIDMM_DMA_BUFFER **)v7 + 45, v26, 0);
                              if ( v24 < 0 )
                                goto LABEL_31;
                              if ( !*((_QWORD *)v7 + 45) )
                              {
                                WdLogSingleEntry0(1);
                                WdLogGlobalForLineNumber = 4851;
                                DxgkLogInternalTriageEvent(
                                  0,
                                  262146,
                                  -1,
                                  (unsigned int)L"m_pPresentDmaBuffer",
                                  4851,
                                  0,
                                  0,
                                  0,
                                  0);
                              }
                            }
                            v24 = DXGCONTEXT::CheckDevicePresentSettings(
                                    v7,
                                    (*((_DWORD *)a2 + 22) >> 2) & 1,
                                    (*((_DWORD *)a2 + 22) >> 28) & 1,
                                    0,
                                    v33);
                            if ( v24 >= 0 )
                            {
                              if ( (*((_DWORD *)a2 + 22) & 4) != 0 )
                              {
                                if ( v327 )
                                {
                                  v262 = *((_QWORD *)v327 + 6);
                                  if ( v262 )
                                  {
                                    if ( (*(_DWORD *)(v262 + 4) & 0x2000) != 0 )
                                    {
                                      if ( !DXGDEVICE::IsDirectFlipAllocationRequestedPinned(
                                              *((DXGDEVICE **)v7 + 2),
                                              v327) )
                                      {
                                        WdLogSingleEntry3(4, -1071775739, v7, v327);
                                        WdLogGlobalForLineNumber = 4903;
                                        goto LABEL_509;
                                      }
                                      if ( !VIDMM_EXPORT::VidMmIsAllocationPinned(
                                              *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                                              *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 768LL),
                                              *((struct VIDMM_MULTI_ALLOC **)v327 + 3)) )
                                      {
                                        v263 = VIDMM_EXPORT::VidMmPinAllocation(
                                                 *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                                                 *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL)
                                                                         + 768LL),
                                                 *((struct VIDMM_MULTI_ALLOC **)v327 + 3),
                                                 0,
                                                 0);
                                        if ( v263 < 0 )
                                        {
                                          WdLogSingleEntry3(4, v327, *((_QWORD *)v327 + 6), v263);
                                          WdLogGlobalForLineNumber = 4928;
LABEL_509:
                                          v264 = (struct VIDMM_DMA_BUFFER *)*((_QWORD *)v7 + 45);
                                          if ( v264 )
                                          {
                                            VIDMM_EXPORT::VidMmReleaseDmaBuffer(
                                              *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                                              v264);
                                            *((_QWORD *)v7 + 45) = 0;
                                          }
                                          goto LABEL_452;
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                              if ( (*((_DWORD *)a2 + 22) & 0x2000) != 0 )
                              {
                                v265 = ADAPTER_DISPLAY::GetCurrentOrientation(
                                         *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3232LL),
                                         v33,
                                         1);
                                v365.Flags.Value = (v265 != 1 ? 0x80 : 0) | v365.Flags.Value & 0xFFFFFF7F;
                              }
                              if ( !bTracingEnabled )
                              {
LABEL_241:
                                v24 = DXGCONTEXT::SubmitPresent(
                                        v7,
                                        (const struct _D3DKMT_PRESENT *)a2,
                                        *((struct DXGHWQUEUE ***)a2 + 188),
                                        *((_DWORD *)a2 + 23),
                                        v345,
                                        v327,
                                        v335,
                                        v329,
                                        &v365,
                                        *((struct _D3DKMT_PRESENT_RGNS **)a2 + 180),
                                        *((struct VIDMM_DMA_BUFFER **)v7 + 45),
                                        v129,
                                        Format,
                                        v26);
                                if ( v24 >= 0
                                  && *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL)
                                                                       + 3232LL)
                                                           + 128LL)
                                               + 4024LL * v33
                                               + 1072) == -1 )
                                {
                                  WdLogSingleEntry0(1);
                                  WdLogGlobalForLineNumber = 4997;
                                  DxgkLogInternalTriageEvent(
                                    0,
                                    262146,
                                    -1,
                                    (unsigned int)L"!NT_SUCCESS(ntStatus) || (GetDisplayAdapter(VidPnSourceId)->GetDisplay"
                                                   "Core()->MapVidPnSourceToVidPnTarget(VidPnSourceId) != D3DDDI_ID_UNINITIALIZED)",
                                    4997,
                                    0,
                                    0,
                                    0,
                                    0);
                                }
                                *((_QWORD *)v7 + 45) = 0;
                                if ( v24 < 0 )
                                  goto LABEL_31;
                                if ( (*((_DWORD *)a2 + 22) & 4) == 0 )
                                  goto LABEL_63;
                                DXGDEVICE::ClearDisplayedAllMultiPlaneOverlaysUnsafe(*((DXGDEVICE **)v7 + 2), v33);
                                DXGDEVICE::SetDisplayedPrimary(
                                  *((DXGDEVICE **)v7 + 2),
                                  v33,
                                  v327,
                                  *((_DWORD *)v129 + 34),
                                  1u);
                                *(_DWORD *)(*((_QWORD *)v7 + 2) + 4LL * v33 + 1832) = *((_DWORD *)v129 + 30);
                                goto LABEL_516;
                              }
                              v266 = *(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL);
                              v267 = *(struct VIDMM_GLOBAL **)(v266 + 768);
                              v268 = *(VIDMM_EXPORT **)(v266 + 760);
                              if ( (*((_DWORD *)a2 + 22) & 4) != 0 )
                              {
                                v168 = (unsigned __int8)VIDMM_EXPORT::VidMmETWAllocationHandle(v268, v267, v335);
                                if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x80u) != 0LL )
                                  McTemplateK0pqpqtt_EtwWriteTransfer(
                                    (unsigned int)&DxgkControlGuid_Context,
                                    (unsigned int)EventFlip,
                                    0,
                                    *((_QWORD *)v7 + 45),
                                    v33,
                                    v168,
                                    v365.FlipInterval,
                                    (*(_BYTE *)&v365.Flags.0 & 8) != 0,
                                    *((_QWORD *)v7 + 45) == 0);
                                goto LABEL_241;
                              }
                              v169 = (unsigned __int8)VIDMM_EXPORT::VidMmETWAllocationHandle(v268, v267, v329);
                              v170 = (CWin32kLocks *)VIDMM_EXPORT::VidMmETWAllocationHandle(
                                                       *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                                                       *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL)
                                                                               + 768LL),
                                                       v335);
                              v171 = v365.pDstSubRects;
                              v172 = v365.SubRectCnt;
                              v333 = v170;
                              v339 = (const struct _DXGKWIN32KENG_INTERFACE *)*((_QWORD *)v7 + 45);
                              if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x20) != 0 )
                                McTemplateK0ppxppttqddddddddq_EtwWriteTransfer(
                                  (unsigned int)&DxgkControlGuid_Context,
                                  (unsigned int)EventBlit,
                                  0,
                                  *((_QWORD *)a2 + 1),
                                  (char)v339,
                                  0,
                                  (char)v333,
                                  v169,
                                  1,
                                  0,
                                  *(_BYTE *)&v365.Flags.0,
                                  v365.SrcRect.left,
                                  v365.SrcRect.right,
                                  v365.SrcRect.top,
                                  v365.SrcRect.bottom,
                                  v365.DstRect.left,
                                  v365.DstRect.right,
                                  v365.DstRect.top,
                                  v365.DstRect.bottom,
                                  v365.SubRectCnt);
                              v173 = 0;
                              if ( !v172 )
                              {
LABEL_315:
                                v129 = v340;
                                v26 = a3;
                                goto LABEL_241;
                              }
                              v174 = (int)v339;
                              while ( 1 )
                              {
                                v175 = 0;
                                v176 = v172 - v173;
                                if ( v172 - v173 > 0x10 )
                                  break;
                                v177 = v172 - v173;
                                if ( v176 )
                                  goto LABEL_310;
LABEL_311:
                                if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x40) != 0 )
                                  McTemplateK0ptqDR2DR2DR2DR2_EtwWriteTransfer(
                                    (unsigned int)&DxgkControlGuid_Context,
                                    (unsigned int)EventBlitRect,
                                    0,
                                    v174,
                                    v176 <= 0x10,
                                    v177,
                                    (__int64)v376,
                                    (__int64)v375,
                                    (__int64)v381,
                                    (__int64)v374);
                                v173 += 16;
                                if ( v173 >= v172 )
                                {
                                  v7 = v347;
                                  goto LABEL_315;
                                }
                              }
                              v177 = 16;
                              do
                              {
LABEL_310:
                                v376[v175] = v171[(unsigned int)v175 + v173].left;
                                v375[v175] = v171[(unsigned int)v175 + v173].right;
                                v381[v175] = v171[(unsigned int)v175 + v173].top;
                                v374[v175] = v171[(unsigned int)v175 + v173].bottom;
                                v175 = (unsigned int)(v175 + 1);
                              }
                              while ( (unsigned int)v175 < v177 );
                              goto LABEL_311;
                            }
                            v260 = (struct VIDMM_DMA_BUFFER *)*((_QWORD *)v7 + 45);
                            if ( v260 )
                            {
                              VIDMM_EXPORT::VidMmReleaseDmaBuffer(
                                *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                                v260);
                              *((_QWORD *)v7 + 45) = 0;
                            }
                            if ( v24 != -1071774920 )
                              goto LABEL_31;
                            if ( (*((_DWORD *)a2 + 22) & 4) != 0 )
                            {
                              v261 = DXGDEVICE::IsFullWDDMDevice(*((DXGDEVICE **)v7 + 2), v33);
                              v248 = (DXGDEVICE *)*((_QWORD *)v7 + 2);
                              v249 = v33;
                              if ( v261 )
                              {
                                DXGDEVICE::ClearDisplayedAllMultiPlaneOverlaysUnsafe(v248, v33);
                                DXGDEVICE::SetDisplayedPrimary(
                                  *((DXGDEVICE **)v7 + 2),
                                  v33,
                                  v327,
                                  *((_DWORD *)v129 + 34),
                                  1u);
                                v250 = *((_DWORD *)v129 + 30);
                                goto LABEL_498;
                              }
                              goto LABEL_499;
                            }
                            goto LABEL_500;
                          }
                          v251 = v339;
                          v252 = *(_DWORD *)(*((_QWORD *)v7 + 19) + 8LL);
                          v253 = (*((__int64 (**)(void))v339 + 1))();
                          v254 = *((_DWORD *)a2 + 22) & 4;
                          if ( v252 != v253 )
                          {
                            if ( !v254 )
                            {
                              DXGDEVICE::FlushScheduler(*((_QWORD *)v7 + 2), 2, 4294967293LL);
                              DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v336);
                              COREDEVICEACCESS::Release(v26);
                              DXGPRESENTMUTEX::DXGPRESENTMUTEX(
                                (DXGPRESENTMUTEX *)v359,
                                *(struct ADAPTER_RENDER *const *)(*((_QWORD *)v7 + 2) + 16LL));
                              DXGPRESENTMUTEX::Acquire((DXGPRESENTMUTEX *)v359);
                              DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v336);
                              v255 = COREDEVICEACCESS::AcquireShared(v26, 0);
                              v24 = v255;
                              if ( v255 < 0 )
                              {
                                WdLogSingleEntry2(4, v255);
                                WdLogGlobalForLineNumber = 4768;
                                COREDEVICEACCESS::AcquireSharedUncheck(v26, 0);
                                v256 = (DXGPRESENTMUTEX *)v359;
                                goto LABEL_478;
                              }
                              DXGDEVICE::SynchronizePresentToPrimary(
                                *((DXGDEVICE **)v7 + 2),
                                v7,
                                (struct DXGPRESENTMUTEX *)v359,
                                1u);
                              DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v359);
                            }
                            v257 = *((_QWORD *)v7 + 19);
                            *(_DWORD *)(v257 + 8) = (*((__int64 (**)(void))v251 + 1))();
                            CddInterface = ADAPTER_DISPLAY::GetCddInterface(
                                             *(ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3232LL),
                                             v33);
                            if ( CddInterface )
                              (*((void (__fastcall **)(_QWORD, _QWORD))CddInterface + 1))(*(_QWORD *)CddInterface, 0);
                            goto LABEL_57;
                          }
                          if ( v254 )
                            goto LABEL_57;
                          COREDEVICEACCESS::Release(v26);
                          DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v336);
                          DXGPRESENTMUTEX::DXGPRESENTMUTEX(
                            (DXGPRESENTMUTEX *)v357,
                            *(struct ADAPTER_RENDER *const *)(*((_QWORD *)v7 + 2) + 16LL));
                          DXGPRESENTMUTEX::Acquire((DXGPRESENTMUTEX *)v357);
                          DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v336);
                          v259 = COREDEVICEACCESS::AcquireShared(v26, 0);
                          v24 = v259;
                          if ( v259 >= 0 )
                          {
                            DXGDEVICE::SynchronizePresentToPrimary(
                              *((DXGDEVICE **)v7 + 2),
                              v7,
                              (struct DXGPRESENTMUTEX *)v357,
                              0);
                            DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v357);
                            goto LABEL_57;
                          }
                          WdLogSingleEntry2(4, v259);
                          WdLogGlobalForLineNumber = 4801;
                          COREDEVICEACCESS::AcquireSharedUncheck(v26, 0);
                          v256 = (DXGPRESENTMUTEX *)v357;
LABEL_478:
                          DXGPRESENTMUTEX::Release(v256);
                          goto LABEL_34;
                        }
LABEL_408:
                        v24 = v28;
                        goto LABEL_34;
                      }
                      WdLogSingleEntry1(4);
                      v26 = a3;
                      WdLogGlobalForLineNumber = 4675;
                      COREDEVICEACCESS::Release(a3);
                      DXGDEVICE::FlushScheduler(*((_QWORD *)v7 + 2), 3, 4294967293LL);
                      v24 = COREDEVICEACCESS::AcquireShared(a3, 0);
                      if ( v24 < 0 )
                      {
                        WdLogSingleEntry1(4);
                        WdLogGlobalForLineNumber = 4683;
                        COREDEVICEACCESS::AcquireSharedUncheck(a3, 0);
                        goto LABEL_34;
                      }
LABEL_431:
                      v39 = v340;
                      goto LABEL_262;
                    }
                  }
                  else
                  {
                    v365.FlipInterval = D3DDDI_FLIPINTERVAL_IMMEDIATE;
                  }
                  v365.Flags.Value |= 8u;
                  goto LABEL_255;
                }
                WdLogSingleEntry0(2);
                v244 = 4572;
                v240 = L"FlipStereoTemporaryMono cannot be used with FlipStereoPreferRight. STATUS_INVALID_PARAMETER";
              }
              else
              {
                WdLogSingleEntry0(2);
                v244 = 4553;
                v240 = L"FlipStereoTemporaryMono and FlipStereo can only be used with stereo primary allocations. STATUS_I"
                        "NVALID_PARAMETER";
              }
              v322 = 0;
              v319 = 0;
              v243 = 0x40000;
              v317 = 0;
              v315 = 0;
              v313 = (struct _DXGKARG_PRESENT *)v244;
              WdLogGlobalForLineNumber = v244;
              goto LABEL_442;
            }
          }
        }
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 4512;
        v240 = L"An invalid VidPn source ID was supplied to an indirect present (%I64d)";
        v241 = *((unsigned int *)a2 + 4);
      }
      else
      {
        WdLogSingleEntry0(2);
        v241 = 4487;
        v240 = L"Expecting indirect display presents to be a shared surface";
        WdLogGlobalForLineNumber = 4487;
      }
      v322 = 0;
      v319 = 0;
      v317 = 0;
      v315 = 0;
      v313 = (struct _DXGKARG_PRESENT *)v241;
      goto LABEL_438;
    }
    v80 = *((_QWORD *)v20 + 6);
    v81 = *(_DWORD *)(v80 + 4);
    if ( (v81 & 0x2003) != 0 )
    {
      v33 = (v81 >> 6) & 0xF;
      goto LABEL_45;
    }
    v24 = -1073741811;
    WdLogSingleEntry5(2, -1073741811, v7, v20, v80, *((unsigned int *)a2 + 5));
    WdLogGlobalForLineNumber = 4497;
    v78 = L"0x%I64x 0x%I64x Source of Flip must be primary 0x%I64x 0x%I64x 0x%I64x";
    v320 = *((unsigned int *)a2 + 5);
    v318 = *((_QWORD *)v327 + 6);
    v316 = (__int64)v327;
    v314 = (__int64)v7;
    v312 = -1073741811;
LABEL_120:
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v78, v312, v314, v316, v318, v320);
    goto LABEL_34;
  }
LABEL_355:
  v204 = *((_QWORD *)a2 + 9);
  if ( !v204
    || (v205 = *((unsigned int *)a2 + 16), !(_DWORD)v205)
    || (v22 & 1) == 0 && (v22 & 2) == 0
    || (v22 & 0x100E803C) != 0 )
  {
    v24 = -1073741811;
    WdLogSingleEntry5(3, v7, v204, *((unsigned int *)a2 + 16), (unsigned int)v22, -1073741811);
    WdLogGlobalForLineNumber = 4175;
    goto LABEL_34;
  }
  if ( (v22 & 2) != 0 )
  {
    if ( (v22 & 1) != 0 || (v22 & 0x100680) != 0 )
    {
      v24 = -1073741811;
      WdLogSingleEntry5(3, v7, v204, *((unsigned int *)a2 + 16), (unsigned int)v22, -1073741811);
      WdLogGlobalForLineNumber = 4190;
      goto LABEL_34;
    }
  }
  else
  {
    if ( !v18 || !Height || (v22 & 0x82) != 0x80 )
    {
      v24 = -1073741811;
      WdLogSingleEntry5(3, v7, v204, *((unsigned int *)a2 + 16), (unsigned int)v22, -1073741811);
      WdLogGlobalForLineNumber = 4204;
      goto LABEL_34;
    }
    if ( (v22 & 0x600) == 0x600 )
    {
      v24 = -1073741811;
      WdLogSingleEntry5(3, -1073741811, v7, v204, v205, (unsigned int)v22);
      WdLogGlobalForLineNumber = 4213;
      goto LABEL_34;
    }
  }
  v206 = *((_QWORD *)v334 + 6);
  v207 = *(_DWORD *)(v206 + 4);
  if ( (v207 & 3) == 0 )
  {
    v24 = -1073741811;
    WdLogSingleEntry5(2, -1073741811, v7, v334, v206, v21);
    WdLogGlobalForLineNumber = 4224;
    v78 = L"0x%I64x 0x%I64x destination must be primary 0x%I64x 0x%I64x 0x%I64x";
    v320 = *((unsigned int *)a2 + 6);
    v318 = *((_QWORD *)v334 + 6);
    v316 = (__int64)v334;
    v314 = (__int64)v7;
    v312 = -1073741811;
    goto LABEL_120;
  }
  v33 = (v207 >> 6) & 0xF;
  v208 = *(DXGADAPTER **)(*((_QWORD *)v7 + 2) + 1896LL);
  if ( !v208
    || !DXGADAPTER::IsDisplayAdapter(v208)
    || !ADAPTER_DISPLAY::IsCoreResourceSharedOwner(*(ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL)
                                                                       + 3232LL)) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4236;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"(GetDisplayAdapter(VidPnSourceId) == GetDisplayAdapter(0)) && (GetDisplayAdapter(VidPnSourceId) != N"
                     "ULL) && GetDisplayAdapter(VidPnSourceId)->IsDisplayAdapter() && GetDisplayAdapter(VidPnSourceId)->G"
                     "etDisplayCore()->IsCoreResourceSharedOwner()",
      4236,
      0,
      0,
      0,
      0);
  }
  *((_DWORD *)v340 + 29) = v33;
  DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v350, v334);
  DXGALLOCATIONREFERENCE::MoveAssign(&v343, v350);
  DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v350);
  v209 = *((_DWORD *)a2 + 6);
  v210 = *((_DWORD *)a2 + 22);
  v342 = v209;
  if ( (v210 & 1) != 0 )
  {
    if ( v334 == v327 )
    {
      v24 = -1073741811;
      WdLogSingleEntry5(2, -1073741811, v7, v327, *((unsigned int *)a2 + 5), v209);
      WdLogGlobalForLineNumber = 4248;
      v78 = L"0x%I64x 0x%I64x Source and destination must be different 0x%I64x 0x%I64x 0x%I64x";
      v320 = *((unsigned int *)a2 + 6);
      v318 = *((unsigned int *)a2 + 5);
      v316 = (__int64)v327;
      v314 = (__int64)v7;
      v312 = -1073741811;
      goto LABEL_120;
    }
    v211 = *(unsigned int *)(*((_QWORD *)v327 + 6) + 4LL);
    if ( (v211 & 3) != 0 && (((unsigned int)v211 >> 6) & 0xF) != v33 )
    {
      v24 = -1073741811;
      WdLogSingleEntry5(2, -1073741811, v7, v327, (v211 >> 6) & 0xF, v33);
      v78 = L"0x%I64x 0x%I64x primary source has different VidPnSourceId 0x%I64x 0x%I64x != 0x%I64x";
      v320 = v33;
      WdLogGlobalForLineNumber = 4261;
      v318 = (*(_DWORD *)(*((_QWORD *)v327 + 6) + 4LL) >> 6) & 0xF;
      v316 = (__int64)v327;
      v314 = (__int64)v7;
      v312 = -1073741811;
      goto LABEL_120;
    }
    v212 = *((_DWORD *)a2 + 12);
    v213 = *((int *)a2 + 14);
    if ( (int)v213 <= v212
      || (v214 = *((_DWORD *)a2 + 13), v215 = *((_DWORD *)a2 + 15), v215 <= v214)
      || v212 >= v18
      || v214 >= (int)v332
      || (int)v213 <= 0
      || v215 <= 0 )
    {
      v24 = -1073741811;
      WdLogSingleEntry5(2, -1073741811, *((int *)a2 + 12), *((int *)a2 + 13), v213, *((int *)a2 + 15));
      WdLogGlobalForLineNumber = 4281;
      v78 = L"0x%I64x Invalid Source Rect [0x%I64x 0x%I64x 0x%I64x 0x%I64x]";
      v320 = *((int *)a2 + 15);
      v318 = *((int *)a2 + 14);
      v316 = *((int *)a2 + 13);
      v314 = *((int *)a2 + 12);
      v312 = -1073741811;
      goto LABEL_120;
    }
    for ( m = 0; ; ++m )
    {
      v217 = *((_DWORD *)a2 + 16);
      if ( m >= v217 )
        break;
      Source1 = 0;
      v218 = 16LL * m;
      v219 = m;
      if ( !DXGPRESENT::IntersectRect(
              &Source1,
              (const struct tagRECT *)(v218 + *((_QWORD *)a2 + 9)),
              (const struct tagRECT *)a2 + 3)
        || RtlCompareMemory(&Source1, (const void *)(v218 + *((_QWORD *)a2 + 9)), 0x10u) != 16 )
      {
        v24 = -1073741811;
        WdLogSingleEntry5(2, -1073741811, *((int *)a2 + 12), *((int *)a2 + 13), *((int *)a2 + 14), *((int *)a2 + 15));
        WdLogGlobalForLineNumber = 4299;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"0x%I64x Source Rect [0x%I64x 0x%I64x 0x%I64x 0x%I64x] contains an invalid subrect",
          -1073741811,
          *((int *)a2 + 12),
          *((int *)a2 + 13),
          *((int *)a2 + 14),
          *((int *)a2 + 15));
        WdLogSingleEntry5(
          2,
          m,
          *(int *)(*((_QWORD *)a2 + 9) + v218),
          *(int *)(*((_QWORD *)a2 + 9) + v218 + 4),
          *(int *)(*((_QWORD *)a2 + 9) + v218 + 8),
          *(int *)(*((_QWORD *)a2 + 9) + v218 + 12));
        WdLogGlobalForLineNumber = 4307;
        goto LABEL_394;
      }
    }
    v220 = *((unsigned int *)a2 + 22);
    if ( (v220 & 0x40) != 0 )
    {
      v221 = *((int *)a2 + 8);
      v222 = *((_DWORD *)a2 + 10);
      if ( v222 <= (int)v221
        || (v223 = *((_DWORD *)a2 + 9), v224 = *((_DWORD *)a2 + 11), v224 <= v223)
        || (int)v221 >= (int)v338[0]
        || v223 >= (int)v341[0]
        || v222 <= 0
        || v224 <= 0 )
      {
        v24 = -1073741811;
        WdLogSingleEntry5(3, -1073741811, v221, *((int *)a2 + 9), *((int *)a2 + 10), *((int *)a2 + 11));
        WdLogGlobalForLineNumber = 4329;
        goto LABEL_34;
      }
      if ( *((_DWORD *)a2 + 14) - *((_DWORD *)a2 + 12) != v222 - (_DWORD)v221
        || *((_DWORD *)a2 + 15) - *((_DWORD *)a2 + 13) != v224 - v223 )
      {
        v24 = -1073741811;
        WdLogSingleEntry5(2, -1073741811, v7, v220, v334, v33);
        v78 = L"0x%I64x 0x%I64x specified destination RECT has different size from source RECT 0x%I64x 0x%I64x 0x%I64x";
        v320 = v33;
        v318 = (__int64)v334;
        WdLogGlobalForLineNumber = 4341;
        v316 = *((unsigned int *)a2 + 22);
        v314 = (__int64)v7;
        v312 = -1073741811;
        goto LABEL_120;
      }
      v28 = DXGPRESENT::GrowRectList(*((DXGPRESENT **)v7 + 19), v217);
      if ( v28 < 0 )
        goto LABEL_408;
      v225 = 0;
      v226 = DXGPRESENT::GetDdiSubRectList(*((DXGPRESENT **)v7 + 19), 0);
      v227 = *((_DWORD *)a2 + 8) - *((_DWORD *)a2 + 12);
      v228 = *((_DWORD *)a2 + 9) - *((_DWORD *)a2 + 13);
      v217 = *((_DWORD *)a2 + 16);
      if ( v217 )
      {
        do
        {
          v229 = v225++;
          v229 *= 2;
          *(&v226->left + 2 * v229) = v227 + *(_DWORD *)(*((_QWORD *)a2 + 9) + 8 * v229);
          *(&v226->right + 2 * v229) = v227 + *(_DWORD *)(*((_QWORD *)a2 + 9) + 8 * v229 + 8);
          *(&v226->top + 2 * v229) = v228 + *(_DWORD *)(*((_QWORD *)a2 + 9) + 8 * v229 + 4);
          *(&v226->bottom + 2 * v229) = v228 + *(_DWORD *)(*((_QWORD *)a2 + 9) + 8 * v229 + 12);
          v217 = *((_DWORD *)a2 + 16);
        }
        while ( v225 < v217 );
      }
      v230 = (RECT)*((_OWORD *)a2 + 2);
      v365.pDstSubRects = v226;
      v365.DstRect = v230;
    }
    else
    {
      if ( v338[0] != v330 || v341[0] != v332 )
      {
        WdLogSingleEntry5(3, v7, v338[0], v341[0], v330, v332);
        WdLogGlobalForLineNumber = 4377;
LABEL_416:
        v24 = -1073741811;
        goto LABEL_34;
      }
      v365.DstRect = (RECT)*((_OWORD *)a2 + 3);
      v365.pDstSubRects = (const RECT *)*((_QWORD *)a2 + 9);
    }
    v365.SrcRect = (RECT)*((_OWORD *)a2 + 3);
    Value = v365.Flags.Value & 0xFFFFF7FF | (*((_DWORD *)a2 + 22) >> 9) & 0x800;
    v365.Flags.Value = Value;
    goto LABEL_430;
  }
  v232 = 0;
  *(_QWORD *)&v365.DstRect.left = 0;
  v365.DstRect.right = Width;
  v365.DstRect.bottom = v341[0];
  if ( (v210 & 0x40) == 0 )
    goto LABEL_424;
  v233 = *((int *)a2 + 10);
  v234 = *((int *)a2 + 8);
  if ( (int)v233 <= (int)v234
    || (v235 = *((_DWORD *)a2 + 11), v235 <= *((_DWORD *)a2 + 9))
    || (int)v233 <= 0
    || v235 <= 0 )
  {
    v24 = -1073741811;
    WdLogSingleEntry5(3, -1073741811, v234, *((int *)a2 + 9), v233, *((int *)a2 + 11));
    WdLogGlobalForLineNumber = 4410;
    goto LABEL_34;
  }
  if ( !DXGPRESENT::IntersectRect(&v365.DstRect, (const struct tagRECT *)a2 + 2, &v365.DstRect) )
    goto LABEL_500;
  while ( 1 )
  {
LABEL_424:
    v217 = *((_DWORD *)a2 + 16);
    if ( v232 >= v217 )
    {
      Value = v365.Flags.Value;
      v365.SrcRect = v365.DstRect;
      v365.pDstSubRects = (const RECT *)*((_QWORD *)a2 + 9);
LABEL_430:
      v26 = a3;
      v365.SubRectCnt = v217;
      v236 = *((_DWORD *)a2 + 22) & 1 | Value & 0xFFFFFFFE;
      v237 = *((_DWORD *)a2 + 22) >> 5;
      v238 = *((_DWORD *)a2 + 22) >> 9;
      v239 = v236
           ^ ((unsigned __int8)v236
            ^ (unsigned __int8)*((_DWORD *)a2 + 22))
           & 2
           ^ ((unsigned __int8)v237
            ^ (unsigned __int8)(v236 ^ (v236 ^ *((_DWORD *)a2 + 22)) & 2))
           & 0x10
           ^ ((unsigned __int8)v237
            ^ (unsigned __int8)(v236
                              ^ (v236
                               ^ *((_DWORD *)a2 + 22))
                              & 2
                              ^ (v237
                               ^ v236
                               ^ (v236
                                ^ *((_DWORD *)a2 + 22))
                               & 2)
                              & 0x10))
           & 0x20;
      LOBYTE(v236) = v236
                   ^ (v236
                    ^ *((_DWORD *)a2 + 22))
                   & 2
                   ^ (v237
                    ^ v236
                    ^ (v236
                     ^ *((_DWORD *)a2 + 22))
                    & 2)
                   & 0x10
                   ^ (v237
                    ^ v236
                    ^ (v236
                     ^ *((_DWORD *)a2 + 22))
                    & 2
                    ^ (v237
                     ^ v236
                     ^ (v236
                      ^ *((_DWORD *)a2 + 22))
                     & 2)
                    & 0x10)
                   & 0x20;
      v365.Color = *((_DWORD *)a2 + 7);
      v365.Flags.Value = v239
                       ^ ((unsigned __int8)v237
                        ^ (unsigned __int8)v236)
                       & 0x40
                       ^ (v239
                        ^ ((unsigned __int8)v237
                         ^ (unsigned __int8)v236)
                        & 0x40
                        ^ v238)
                       & 0x800;
      goto LABEL_431;
    }
    v367 = 0;
    v218 = 16LL * v232;
    v219 = v232;
    if ( !DXGPRESENT::IntersectRect(&v367, (const struct tagRECT *)(v218 + *((_QWORD *)a2 + 9)), &v365.DstRect)
      || RtlCompareMemory(&v367, (const void *)(v218 + *((_QWORD *)a2 + 9)), 0x10u) != 16 )
    {
      break;
    }
    ++v232;
  }
  v24 = -1073741811;
  WdLogSingleEntry5(2, -1073741811, *((int *)a2 + 8), *((int *)a2 + 9), *((int *)a2 + 10), *((int *)a2 + 11));
  WdLogGlobalForLineNumber = 4434;
  DxgkLogInternalTriageEvent(
    0,
    0x40000,
    -1,
    (unsigned int)L"0x%I64x Dest Rect [0x%I64x 0x%I64x 0x%I64x 0x%I64x] contains an invalid subrect",
    -1073741811,
    *((int *)a2 + 8),
    *((int *)a2 + 9),
    *((int *)a2 + 10),
    *((int *)a2 + 11));
  WdLogSingleEntry5(
    2,
    v232,
    *(int *)(*((_QWORD *)a2 + 9) + v218),
    *(int *)(*((_QWORD *)a2 + 9) + v218 + 4),
    *(int *)(*((_QWORD *)a2 + 9) + v218 + 8),
    *(int *)(*((_QWORD *)a2 + 9) + v218 + 12));
  WdLogGlobalForLineNumber = 4442;
LABEL_394:
  DxgkLogInternalTriageEvent(
    0,
    0x40000,
    -1,
    (unsigned int)L"SubRect 0x%I64x is invalid 0x%I64x 0x%I64x 0x%I64x 0x%I64x",
    v219,
    *(int *)(*((_QWORD *)a2 + 9) + v218),
    *(int *)(*((_QWORD *)a2 + 9) + v218 + 4),
    *(int *)(*((_QWORD *)a2 + 9) + v218 + 8),
    *(int *)(*((_QWORD *)a2 + 9) + v218 + 12));
LABEL_34:
  DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v343);
  DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v334);
  DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v327);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x140399ce0  push    rbp
0x140399ce2  push    rbx
0x140399ce3  push    rsi
0x140399ce4  push    rdi
0x140399ce5  push    r12
0x140399ce7  push    r13
0x140399ce9  push    r14
0x140399ceb  push    r15
0x140399ced  lea     rbp, [rsp-978h]
0x140399cf5  sub     rsp, 0A98h
0x140399cfc  mov     rax, cs:__security_cookie
0x140399d03  xor     rax, rsp
0x140399d06  mov     [rbp+9B0h+var_50], rax
0x140399d0d  mov     rax, [rbp+9B0h+arg_20]
0x140399d14  mov     r15, rcx
0x140399d17  mov     rbx, [rbp+9B0h+arg_30]
0x140399d1e  mov     r13, rdx
0x140399d21  mov     [rbp+9B0h+var_988], rcx
0x140399d25  mov     rcx, [rcx+10h]
0x140399d29  mov     [rbp+9B0h+var_A08], rax
0x140399d2d  mov     rax, [rbp+9B0h+arg_28]
0x140399d34  mov     [rbp+9B0h+var_9F0], r9
0x140399d38  mov     rcx, [rcx+10h]; this
0x140399d3c  mov     [rbp+9B0h+var_A30], r8
0x140399d40  mov     [rbp+9B0h+var_9D0], rbx
0x140399d44  mov     [rbp+9B0h+var_998], rax
0x140399d48  call    ?IsCoreResourceSharedOwner@ADAPTER_RENDER@@QEBAEXZ; ADAPTER_RENDER::IsCoreResourceSharedOwner(void)
0x140399d4d  or      r12d, 0FFFFFFFFh
0x140399d51  xor     esi, esi
0x140399d53  mov     edi, 1
0x140399d58  mov     r14d, 40002h
0x140399d5e  test    al, al
0x140399d60  jz      loc_14039C421
0x140399d66  cmp     [r15+168h], rsi
0x140399d6d  jnz     loc_14039C46C
0x140399d73  test    dword ptr [r13+58h], 4000h
0x140399d7b  jnz     loc_14039C4B7
0x140399d81  mov     rcx, [r15+10h]
0x140399d85  mov     rcx, [rcx+28h]; this
0x140399d89  call    ?GetWin32kInterface@DXGPROCESS@@QEBAQEBU_DXGKWIN32KENG_INTERFACE@@XZ; DXGPROCESS::GetWin32kInterface(void)
0x140399d8e  mov     ecx, [r13+58h]
0x140399d92  mov     [rbp+9B0h+var_9D8], rax
0x140399d96  mov     eax, 12000h
0x140399d9b  and     ecx, eax
0x140399d9d  cmp     ecx, eax
0x140399d9f  jz      loc_14039C4E4
0x140399da5  xor     edx, edx; Val
0x140399da7  lea     rcx, [rbp+9B0h+var_590]; void *
0x140399dae  mov     r8d, 0A8h; Size
0x140399db4  call    memset
0x140399db9  mov     eax, [r13+14h]
0x140399dbd  mov     [rbp+9B0h+var_9F8], eax
0x140399dc0  mov     eax, [r13+18h]
0x140399dc4  mov     [rbp+9B0h+var_A1C], eax
0x140399dc7  or      dword ptr [rbx], 10020h
0x140399dcd  test    dword ptr [r13+58h], 10000h
0x140399dd5  mov     ecx, [rbx]
0x140399dd7  jz      loc_14039C511
0x140399ddd  bts     ecx, 8
0x140399de1  mov     [rbx], ecx
0x140399de3  mov     eax, [r13+58h]
0x140399de7  shl     eax, 5
0x140399dea  xor     eax, ecx
0x140399dec  and     eax, 20000h
0x140399df1  xor     eax, ecx
0x140399df3  mov     [rbx], eax
0x140399df5  test    dword ptr [r13+58h], 1000h
0x140399dfd  jnz     loc_14039A8AD
0x140399e03  mov     rdx, [r15+10h]
0x140399e07  mov     rax, [rdx+10h]
0x140399e0b  mov     rcx, [rax+10h]
0x140399e0f  cmp     [rdx+768h], rcx
0x140399e16  jnz     loc_14039C518
0x140399e1c  xor     edx, edx; struct DXGALLOCATION *
0x140399e1e  lea     rcx, [rbp+9B0h+var_A28]; this
0x140399e22  call    ??0DXGALLOCATIONREFERENCE@@QEAA@PEAVDXGALLOCATION@@@Z; DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE(DXGALLOCATION *)
0x140399e27  xor     edx, edx; struct DXGALLOCATION *
0x140399e29  lea     rcx, [rbp+9B0h+var_A00]; this
0x140399e2d  call    ??0DXGALLOCATIONREFERENCE@@QEAA@PEAVDXGALLOCATION@@@Z; DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE(DXGALLOCATION *)
0x140399e32  xor     edx, edx; struct DXGALLOCATION *
0x140399e34  lea     rcx, [rbp+9B0h+var_9B8]; this
0x140399e38  call    ??0DXGALLOCATIONREFERENCE@@QEAA@PEAVDXGALLOCATION@@@Z; DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE(DXGALLOCATION *)
0x140399e3d  mov     ebx, [r13+18h]
0x140399e41  mov     r14d, 2
0x140399e47  test    ebx, ebx
0x140399e49  jnz     loc_14039A433
0x140399e4f  mov     r14d, esi
0x140399e52  mov     [rbp+9B0h+var_9C8], esi
0x140399e55  test    dword ptr [r13+58h], 8002h
0x140399e5d  mov     [rbp+9B0h+var_9E0], r14d
0x140399e61  jz      loc_14039A30B
0x140399e67  mov     ebx, esi
0x140399e69  mov     [rbp+9B0h+var_9E8], esi
0x140399e6c  mov     edi, esi
0x140399e6e  mov     rdx, [rbp+9B0h+var_A28]
0x140399e72  mov     r10d, [r13+18h]
0x140399e76  mov     [rbp+9B0h+var_A18], ebx
0x140399e79  mov     [rbp+9B0h+var_A10], edi
0x140399e7c  test    r10d, r10d
0x140399e7f  jnz     loc_14039C621
0x140399e85  mov     r9d, [r13+58h]
0x140399e89  test    r9b, 4
0x140399e8d  jnz     loc_14039A037
0x140399e93  mov     eax, r9d
0x140399e96  mov     [rbp+9B0h+var_9C0], esi
0x140399e99  shr     eax, 1
0x140399e9b  mov     r12d, 1
0x140399ea1  test    r12b, r9b
0x140399ea4  jnz     loc_14039A2A1
0x140399eaa  lea     esi, [r12+1]
0x140399eaf  test    sil, r9b
0x140399eb2  jnz     loc_14039DD6B
0x140399eb8  bt      r9d, 0Fh
0x140399ebd  jb      short loc_140399EFC
0x140399ebf  mov     ecx, [r13+40h]
0x140399ec3  mov     r12, 0FFFFFFFFC000000Dh
0x140399eca  mov     [rsp+0AD0h+var_AA8], r9
0x140399ecf  mov     r8, r15
0x140399ed2  mov     r9, [r13+48h]
0x140399ed6  mov     rdx, r12
0x140399ed9  mov     [rsp+0AD0h+var_AB0], rcx
0x140399ede  lea     ecx, [rsi+1]
0x140399ee1  call    cs:__imp_WdLogSingleEntry5
0x140399ee8  nop     dword ptr [rax+rax+00h]
0x140399eed  mov     cs:WdLogGlobalForLineNumber, 185Dh
0x140399ef7  jmp     loc_140399FEF
0x140399efc  test    r9b, 6
0x140399f00  jnz     loc_14039DD3B
0x140399f06  test    r9d, 27E8h
0x140399f0d  jnz     loc_14039DD3B
0x140399f13  lea     rbx, [r13+168h]
0x140399f1a  mov     eax, [rbx]
0x140399f1c  cmp     eax, esi
0x140399f1e  jnz     loc_14039DD2D
0x140399f24  cmp     dword ptr [r13+494h], 10h
0x140399f2c  ja      loc_14039DD3B
0x140399f32  mov     rax, [r15+10h]
0x140399f36  mov     r14, [rbp+9B0h+var_A30]
0x140399f3a  mov     rdi, [rbp+9B0h+var_9F0]
0x140399f3e  mov     rdx, r14; struct COREDEVICEACCESS *
0x140399f41  shr     r9d, 4
0x140399f45  mov     rcx, rdi; this
0x140399f48  mov     r8, [rax+10h]
0x140399f4c  and     r9b, r12b
0x140399f4f  mov     rax, [r13+160h]
0x140399f56  mov     byte ptr [rsp+0AD0h+var_AA8], r9b; bool
0x140399f5b  mov     r9, rbx; struct _D3DKMT_PRESENTHISTORYTOKEN *
0x140399f5e  mov     [rsp+0AD0h+var_AB0], rax; void *
0x140399f63  mov     r8, [r8+10h]; struct DXGADAPTER *
0x140399f67  call    ?SubmitPresentHistoryTokenPreparation@@YAJPEAVDXGADAPTERSTOPRESETLOCKSHARED@@PEAVCOREDEVICEACCESS@@PEAVDXGADAPTER@@PEAU_D3DKMT_PRESENTHISTORYTOKEN@@PEAX_N@Z; SubmitPresentHistoryTokenPreparation(DXGADAPTERSTOPRESETLOCKSHARED *,COREDEVICEACCESS *,DXGADAPTER *,_D3DKMT_PRESENTHISTORYTOKEN *,void *,bool)
0x140399f6c  xor     r12d, r12d
0x140399f6f  test    eax, eax
0x140399f71  js      loc_14039CD02
0x140399f77  mov     r9, r14; struct COREDEVICEACCESS *
0x140399f7a  lea     rcx, [rbp+9B0h+var_7E0]; this
0x140399f81  mov     r8, rdi; struct DXGADAPTERSTOPRESETLOCKSHARED *
0x140399f84  mov     rdx, rbx; struct _D3DKMT_PRESENTHISTORYTOKEN *
0x140399f87  call    ??0TOKEN_BINDING_GUARD@@QEAA@PEAU_D3DKMT_PRESENTHISTORYTOKEN@@PEAVDXGADAPTERSTOPRESETLOCKSHARED@@PEAVCOREDEVICEACCESS@@@Z; TOKEN_BINDING_GUARD::TOKEN_BINDING_GUARD(_D3DKMT_PRESENTHISTORYTOKEN *,DXGADAPTERSTOPRESETLOCKSHARED *,COREDEVICEACCESS *)
0x140399f8c  mov     rax, [rbp+9B0h+var_9D0]
0x140399f90  mov     r8, rdi; struct DXGADAPTERSTOPRESETLOCKSHARED *
0x140399f93  mov     r9, [rbp+9B0h+var_A08]; struct CWin32kLocks *
0x140399f97  mov     rdx, r14; struct COREDEVICEACCESS *
0x140399f9a  mov     [rsp+0AD0h+var_A80], r12; char *
0x140399f9f  mov     rcx, rbx; struct _D3DKMT_PRESENTHISTORYTOKEN *
0x140399fa2  mov     [rsp+0AD0h+var_A88], r12; struct _PRESENT_REDIRECTED_PARAMS *
0x140399fa7  mov     [rsp+0AD0h+var_A90], r15; struct DXGCONTEXT *
0x140399fac  mov     qword ptr [rsp+0AD0h+var_A98], rax; struct VIDSCH_SUBMIT_DATA_BASE *
0x140399fb1  mov     [rsp+0AD0h+var_AA0], r13; struct DXGK_PRESENT_PARAMS *
0x140399fb6  mov     [rsp+0AD0h+var_AA8], r12; union _LARGE_INTEGER *
0x140399fbb  mov     dword ptr [rsp+0AD0h+var_AB0], 1; int
0x140399fc3  call    ?SubmitPresentHistoryToken@@YAJPEBU_D3DKMT_PRESENTHISTORYTOKEN@@PEAVCOREDEVICEACCESS@@PEAVDXGADAPTERSTOPRESETLOCKSHARED@@PEAVCWin32kLocks@@HPEAT_LARGE_INTEGER@@PEAUDXGK_PRESENT_PARAMS@@PEAUVIDSCH_SUBMIT_DATA_BASE@@PEAVDXGCONTEXT@@PEAU_PRESENT_REDIRECTED_PARAMS@@PEBD@Z; SubmitPresentHistoryToken(_D3DKMT_PRESENTHISTORYTOKEN const *,COREDEVICEACCESS *,DXGADAPTERSTOPRESETLOCKSHARED *,CWin32kLocks *,int,_LARGE_INTEGER *,DXGK_PRESENT_PARAMS *,VIDSCH_SUBMIT_DATA_BASE *,DXGCONTEXT *,_PRESENT_REDIRECTED_PARAMS *,char const *)
0x140399fc8  lea     rcx, [rbp+9B0h+var_7E0]; this
0x140399fcf  mov     [rbp+9B0h+var_7E0], eax
0x140399fd5  mov     r12d, eax
0x140399fd8  call    ??1TOKEN_BINDING_GUARD@@QEAA@XZ; TOKEN_BINDING_GUARD::~TOKEN_BINDING_GUARD(void)
0x140399fdd  test    r12d, r12d
0x140399fe0  js      short loc_140399FEF
0x140399fe2  mov     rbx, [rbp+9B0h+var_9B8]
0x140399fe6  test    rbx, rbx
0x140399fe9  jnz     loc_14039B0F9
0x140399fef  xor     esi, esi
0x140399ff1  mov     rcx, [r15+10h]
0x140399ff5  mov     rcx, [rcx+10h]; this
0x140399ff9  call    ?IsCoreResourceSharedOwner@ADAPTER_RENDER@@QEBAEXZ; ADAPTER_RENDER::IsCoreResourceSharedOwner(void)
0x140399ffe  test    al, al
0x14039a000  jz      loc_14039EA9C
0x14039a006  cmp     [r15+168h], rsi
0x14039a00d  jnz     loc_14039EAFA
0x14039a013  lea     rcx, [rbp+9B0h+var_9B8]; this
0x14039a017  call    ??1DXGALLOCATIONREFERENCE@@QEAA@XZ; DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE(void)
0x14039a01c  lea     rcx, [rbp+9B0h+var_A00]; this
0x14039a020  call    ??1DXGALLOCATIONREFERENCE@@QEAA@XZ; DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE(void)
0x14039a025  lea     rcx, [rbp+9B0h+var_A28]; this
0x14039a029  call    ??1DXGALLOCATIONREFERENCE@@QEAA@XZ; DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE(void)
0x14039a02e  mov     eax, r12d
0x14039a031  jmp     loc_14039EB44
0x14039a037  test    r10d, r10d
0x14039a03a  jnz     loc_14039C630
0x14039a040  test    r9d, 10A7C3h
0x14039a047  jnz     loc_14039DCFD
0x14039a04d  bt      r9d, 1Ch
0x14039a052  jnb     loc_14039A925
0x14039a058  mov     rax, [rdx+28h]
0x14039a05c  test    rax, rax
0x14039a05f  jz      loc_14039D121
0x14039a065  cmp     [rax+38h], rsi
0x14039a069  jz      loc_14039D121
0x14039a06f  mov     rax, [r15+10h]
0x14039a073  mov     rcx, [rax+768h]; this
0x14039a07a  test    rcx, rcx
0x14039a07d  jz      loc_14039D0F5
0x14039a083  call    ?IsDisplayAdapter@DXGADAPTER@@QEBAEXZ; DXGADAPTER::IsDisplayAdapter(void)
0x14039a088  test    al, al
0x14039a08a  jz      loc_14039D0F5
0x14039a090  mov     rax, [r15+10h]
0x14039a094  mov     edi, [r13+10h]
0x14039a098  mov     rcx, [rax+768h]
0x14039a09f  mov     rax, [rcx+0CA0h]
0x14039a0a6  cmp     edi, [rax+60h]
0x14039a0a9  jnb     loc_14039D0F5
0x14039a0af  mov     rdx, [rbp+9B0h+var_A28]; struct DXGALLOCATION *
0x14039a0b3  lea     rcx, [rbp+9B0h+var_968]; this
0x14039a0b7  call    ??0DXGALLOCATIONREFERENCE@@QEAA@PEAVDXGALLOCATION@@@Z; DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE(DXGALLOCATION *)
0x14039a0bc  lea     rdx, [rbp+9B0h+var_968]
0x14039a0c0  lea     rcx, [rbp+9B0h+var_9B8]
0x14039a0c4  call    ?MoveAssign@DXGALLOCATIONREFERENCE@@QEAAAEAV1@$$QEAV1@@Z; DXGALLOCATIONREFERENCE::MoveAssign(DXGALLOCATIONREFERENCE &&)
0x14039a0c9  lea     rcx, [rbp+9B0h+var_968]; this
0x14039a0cd  call    ??1DXGALLOCATIONREFERENCE@@QEAA@XZ; DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE(void)
0x14039a0d2  mov     eax, [r13+14h]
0x14039a0d6  mov     [rbp+9B0h+var_9C0], eax
0x14039a0d9  mov     rax, [r15+10h]
0x14039a0dd  mov     rcx, [rax+768h]; this
0x14039a0e4  test    rcx, rcx
0x14039a0e7  jz      loc_14039D279
0x14039a0ed  call    ?IsDisplayAdapter@DXGADAPTER@@QEBAEXZ; DXGADAPTER::IsDisplayAdapter(void)
0x14039a0f2  test    al, al
0x14039a0f4  jz      loc_14039D279
0x14039a0fa  mov     rax, [r15+10h]
0x14039a0fe  mov     rcx, [rax+768h]
0x14039a105  mov     rcx, [rcx+0CA0h]; this
0x14039a10c  call    ?IsCoreResourceSharedOwner@ADAPTER_DISPLAY@@QEBAEXZ; ADAPTER_DISPLAY::IsCoreResourceSharedOwner(void)
0x14039a111  test    al, al
0x14039a113  jz      loc_14039D279
0x14039a119  or      r14d, 0FFFFFFFFh
0x14039a11d  mov     r9, [rbp+9B0h+var_A28]
0x14039a121  mov     rdx, [r9+30h]
0x14039a125  mov     r8d, [rdx+4]
0x14039a129  bt      r8d, 0Dh
0x14039a12e  jb      loc_14039D2CD
0x14039a134  mov     edx, [r13+58h]
0x14039a138  mov     r12d, 40000h
0x14039a13e  mov     eax, edx
0x14039a140  shr     eax, 11h
0x14039a143  test    r12d, edx
0x14039a146  jnz     loc_14039D350
0x14039a14c  test    al, 1
0x14039a14e  jnz     loc_14039D350
0x14039a154  mov     rcx, [r15+10h]; this
0x14039a158  mov     edx, edi; unsigned int
0x14039a15a  call    ?IsFullWDDMDevice@DXGDEVICE@@QEBA?BEI@Z; DXGDEVICE::IsFullWDDMDevice(uint)
0x14039a15f  mov     r12, [rbp+9B0h+var_9D0]
0x14039a163  test    al, al
0x14039a165  jnz     loc_14039B759
0x14039a16b  mov     r14, [rbp+9B0h+var_A30]
0x14039a16f  mov     edx, [r13+58h]
0x14039a173  xor     r9d, r9d; int
0x14039a176  mov     r8d, edx
0x14039a179  mov     dword ptr [rsp+0AD0h+var_AB0], edi; unsigned int
0x14039a17d  shr     r8d, 1Ch
0x14039a181  mov     rcx, r15; this
0x14039a184  shr     edx, 2
0x14039a187  and     r8d, 1; int
0x14039a18b  and     edx, 1; int
0x14039a18e  call    ?CheckDevicePresentSettings@DXGCONTEXT@@QEAAJHHHI@Z; DXGCONTEXT::CheckDevicePresentSettings(int,int,int,uint)
0x14039a193  test    eax, eax
0x14039a195  js      loc_14039D53A
0x14039a19b  mov     eax, [r13+58h]
0x14039a19f  test    al, 4
0x14039a1a1  jnz     loc_14039D595
0x14039a1a7  mov     rax, [r15+10h]
0x14039a1ab  xor     r8d, r8d; unsigned __int8
0x14039a1ae  mov     edx, edi; unsigned int
0x14039a1b0  mov     rcx, [rax+768h]
0x14039a1b7  mov     rcx, [rcx+0CA0h]; this
0x14039a1be  call    ?GetCddPrimaryAllocation@ADAPTER_DISPLAY@@QEBAPEAVDXGADAPTERALLOCATION@@IE@Z; ADAPTER_DISPLAY::GetCddPrimaryAllocation(uint,uchar)
0x14039a1c3  test    rax, rax
0x14039a1c6  jnz     loc_14039D5C1
0x14039a1cc  mov     rax, [r15+10h]
0x14039a1d0  mov     edx, edi
0x14039a1d2  mov     ecx, [rax+rdx*4+4D8h]
0x14039a1d9  shr     ecx, 9
0x14039a1dc  test    cl, 1
0x14039a1df  jz      loc_14039D7DC
0x14039a1e5  mov     rcx, [r15+10h]; this
0x14039a1e9  mov     edx, edi; unsigned int
0x14039a1eb  call    ?IsFullWDDMDevice@DXGDEVICE@@QEBA?BEI@Z; DXGDEVICE::IsFullWDDMDevice(uint)
0x14039a1f0  test    al, al
0x14039a1f2  jnz     loc_14039B5F3
0x14039a1f8  mov     rdx, [r15+10h]
0x14039a1fc  cmp     [rdx+768h], rsi
  ... truncated ...
```
