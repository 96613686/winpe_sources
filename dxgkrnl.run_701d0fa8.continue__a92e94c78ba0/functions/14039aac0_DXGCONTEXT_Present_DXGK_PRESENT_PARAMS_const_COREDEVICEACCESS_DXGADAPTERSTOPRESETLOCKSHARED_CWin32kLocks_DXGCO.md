# DXGCONTEXT::Present(DXGK_PRESENT_PARAMS const *,COREDEVICEACCESS *,DXGADAPTERSTOPRESETLOCKSHARED *,CWin32kLocks *,DXGCONTEXT * *,VIDSCH_SUBMIT_DATA_BASE *)

- ea: `0x14039aac0`
- end: `0x14039f947`
- name: `?Present@DXGCONTEXT@@QEAAJPEBUDXGK_PRESENT_PARAMS@@PEAVCOREDEVICEACCESS@@PEAVDXGADAPTERSTOPRESETLOCKSHARED@@PEAVCWin32kLocks@@PEAPEAV1@PEAUVIDSCH_SUBMIT_DATA_BASE@@@Z`
- size: `20103`
- prototype: `__int64 __usercall@<rax>(DXGCONTEXT *__hidden this@<rcx>, const struct DXGK_PRESENT_PARAMS *@<rdx>, struct COREDEVICEACCESS *@<r8>, struct DXGADAPTERSTOPRESETLOCKSHARED *@<r9>, struct CWin32kLocks *, struct DXGCONTEXT **, struct VIDSCH_SUBMIT_DATA_BASE *)`
- caller_count: `3`
- callee_count: `82`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140252c68`
- `0x140385120`
- `0x140398fc0`

## callees

- `0x140014e0c`
- `0x140015a70`
- `0x140015f7c`
- `0x1400169f0`
- `0x14001b9c0`
- `0x14001bd80`
- `0x14001bf1c`
- `0x14001d1a0`
- `0x14001d214`
- `0x14001de1c`
- `0x14001e64c`
- `0x14001eaac`
- `0x14001f2f0`
- `0x140021e90`
- `0x14002dbc0`
- `0x140033bb0`
- `0x140033f08`
- `0x140034030`
- `0x140034080`
- `0x140034910`
- `0x140037f8c`
- `0x140038e5c`
- `0x14003940c`
- `0x14003c844`
- `0x1400409a4`
- `0x140040e7c`
- `0x140042224`
- `0x140042420`
- `0x140042b34`
- `0x140044150`
- `0x1400477c4`
- `0x14004d4a4`
- `0x1400504a4`
- `0x140055854`
- `0x140057ac8`
- `0x140060978`
- `0x14007a0a0`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a1000`
- `0x14019cf50`
- `0x140253378`
- `0x1402564e0`
- `0x140292838`
- `0x14031a9cc`
- `0x14031e5d8`
- `0x14032a5c4`
- `0x14032e980`
- `0x14032fd70`
- `0x14034aed4`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14039b17e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14039b2a2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14039cf19`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14039b17e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14039b2a2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14039cf19`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14039b172`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14039b296`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14039cf0d`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14039b172`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14039b296`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14039cf0d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14039b4ca`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14039b4ca`
- `ntoskrnl!RtlCompareMemory` at `0x14039d7d9`
- `ntoskrnl!RtlCompareMemory` at `0x14039dd78`
- `ntoskrnl!RtlCompareMemory` at `0x14039d7d9`
- `ntoskrnl!RtlCompareMemory` at `0x14039dd78`
- `watchdog!WdLogSingleEntry4` at `0x14039d34e`
- `watchdog!WdLogSingleEntry4` at `0x14039d389`
- `watchdog!WdLogSingleEntry4` at `0x14039d34e`
- `watchdog!WdLogSingleEntry4` at `0x14039d389`
- `watchdog!WdLogSingleEntry2` at `0x14039b6bf`
- `watchdog!WdLogSingleEntry2` at `0x14039c345`
- `watchdog!WdLogSingleEntry2` at `0x14039c763`
- `watchdog!WdLogSingleEntry2` at `0x14039d2a9`
- `watchdog!WdLogSingleEntry2` at `0x14039d2d6`
- `watchdog!WdLogSingleEntry2` at `0x14039dc2a`
- `watchdog!WdLogSingleEntry2` at `0x14039dfc6`
- `watchdog!WdLogSingleEntry2` at `0x14039e43a`
- `watchdog!WdLogSingleEntry2` at `0x14039e46e`
- `watchdog!WdLogSingleEntry2` at `0x14039e569`
- `watchdog!WdLogSingleEntry2` at `0x14039e611`
- `watchdog!WdLogSingleEntry2` at `0x14039eb71`
- `watchdog!WdLogSingleEntry2` at `0x14039ed28`
- `watchdog!WdLogSingleEntry2` at `0x14039eeb5`
- `watchdog!WdLogSingleEntry2` at `0x14039f37a`
- `watchdog!WdLogSingleEntry2` at `0x14039f3a0`
- `watchdog!WdLogSingleEntry2` at `0x14039f519`
- `watchdog!WdLogSingleEntry2` at `0x14039b6bf`
- `watchdog!WdLogSingleEntry2` at `0x14039c345`
- `watchdog!WdLogSingleEntry2` at `0x14039c763`
- `watchdog!WdLogSingleEntry2` at `0x14039d2a9`
- `watchdog!WdLogSingleEntry2` at `0x14039d2d6`
- `watchdog!WdLogSingleEntry2` at `0x14039dc2a`
- `watchdog!WdLogSingleEntry2` at `0x14039dfc6`
- `watchdog!WdLogSingleEntry2` at `0x14039e43a`
- `watchdog!WdLogSingleEntry2` at `0x14039e46e`
- `watchdog!WdLogSingleEntry2` at `0x14039e569`
- `watchdog!WdLogSingleEntry2` at `0x14039e611`
- `watchdog!WdLogSingleEntry2` at `0x14039eb71`
- `watchdog!WdLogSingleEntry2` at `0x14039ed28`
- `watchdog!WdLogSingleEntry2` at `0x14039eeb5`
- `watchdog!WdLogSingleEntry2` at `0x14039f37a`
- `watchdog!WdLogSingleEntry2` at `0x14039f3a0`
- `watchdog!WdLogSingleEntry2` at `0x14039f519`
- `watchdog!WdLogSingleEntry3` at `0x14039b63a`
- `watchdog!WdLogSingleEntry3` at `0x14039c0ed`
- `watchdog!WdLogSingleEntry3` at `0x14039d316`
- `watchdog!WdLogSingleEntry3` at `0x14039d3e6`
- `watchdog!WdLogSingleEntry3` at `0x14039e1bb`
- `watchdog!WdLogSingleEntry3` at `0x14039e254`
- `watchdog!WdLogSingleEntry3` at `0x14039e78b`
- `watchdog!WdLogSingleEntry3` at `0x14039e812`
- `watchdog!WdLogSingleEntry3` at `0x14039e9be`
- `watchdog!WdLogSingleEntry3` at `0x14039eac2`
- `watchdog!WdLogSingleEntry3` at `0x14039eaf2`
- `watchdog!WdLogSingleEntry3` at `0x14039eb30`
- `watchdog!WdLogSingleEntry3` at `0x14039b63a`
- `watchdog!WdLogSingleEntry3` at `0x14039c0ed`
- `watchdog!WdLogSingleEntry3` at `0x14039d316`
- `watchdog!WdLogSingleEntry3` at `0x14039d3e6`
- `watchdog!WdLogSingleEntry3` at `0x14039e1bb`
- `watchdog!WdLogSingleEntry3` at `0x14039e254`
- `watchdog!WdLogSingleEntry3` at `0x14039e78b`
- `watchdog!WdLogSingleEntry3` at `0x14039e812`
- `watchdog!WdLogSingleEntry3` at `0x14039e9be`
- `watchdog!WdLogSingleEntry3` at `0x14039eac2`
- `watchdog!WdLogSingleEntry3` at `0x14039eaf2`
- `watchdog!WdLogSingleEntry3` at `0x14039eb30`
- `watchdog!WdLogSingleEntry0` at `0x14039b790`
- `watchdog!WdLogSingleEntry0` at `0x14039b806`
- `watchdog!WdLogSingleEntry0` at `0x14039b85a`
- `watchdog!WdLogSingleEntry0` at `0x14039cead`
- `watchdog!WdLogSingleEntry0` at `0x14039cf31`
- `watchdog!WdLogSingleEntry0` at `0x14039d203`
- `watchdog!WdLogSingleEntry0` at `0x14039d24e`
- `watchdog!WdLogSingleEntry0` at `0x14039d5b4`
- `watchdog!WdLogSingleEntry0` at `0x14039df06`
- `watchdog!WdLogSingleEntry0` at `0x14039e010`
- `watchdog!WdLogSingleEntry0` at `0x14039e05e`
- `watchdog!WdLogSingleEntry0` at `0x14039e150`
- `watchdog!WdLogSingleEntry0` at `0x14039e193`
- `watchdog!WdLogSingleEntry0` at `0x14039e1f6`
- `watchdog!WdLogSingleEntry0` at `0x14039e222`
- `watchdog!WdLogSingleEntry0` at `0x14039e65e`
- `watchdog!WdLogSingleEntry0` at `0x14039e8f7`
- `watchdog!WdLogSingleEntry0` at `0x14039ecd1`
- `watchdog!WdLogSingleEntry0` at `0x14039ed55`
- `watchdog!WdLogSingleEntry0` at `0x14039efa4`
- `watchdog!WdLogSingleEntry0` at `0x14039f034`
- `watchdog!WdLogSingleEntry0` at `0x14039f085`
- `watchdog!WdLogSingleEntry0` at `0x14039f19e`
- `watchdog!WdLogSingleEntry0` at `0x14039f24e`
- `watchdog!WdLogSingleEntry0` at `0x14039f2c1`
- `watchdog!WdLogSingleEntry0` at `0x14039f31c`
- `watchdog!WdLogSingleEntry0` at `0x14039f44e`
- `watchdog!WdLogSingleEntry0` at `0x14039f56f`
- `watchdog!WdLogSingleEntry0` at `0x14039f59c`
- `watchdog!WdLogSingleEntry0` at `0x14039f791`
- `watchdog!WdLogSingleEntry0` at `0x14039f811`
- `watchdog!WdLogSingleEntry0` at `0x14039f88e`
- `watchdog!WdLogSingleEntry0` at `0x14039f8df`
- `watchdog!WdLogSingleEntry0` at `0x14039b790`
- `watchdog!WdLogSingleEntry0` at `0x14039b806`
- `watchdog!WdLogSingleEntry0` at `0x14039b85a`
- `watchdog!WdLogSingleEntry0` at `0x14039cead`
- `watchdog!WdLogSingleEntry0` at `0x14039cf31`
- `watchdog!WdLogSingleEntry0` at `0x14039d203`
- `watchdog!WdLogSingleEntry0` at `0x14039d24e`
- `watchdog!WdLogSingleEntry0` at `0x14039d5b4`
- `watchdog!WdLogSingleEntry0` at `0x14039df06`
- `watchdog!WdLogSingleEntry0` at `0x14039e010`
- `watchdog!WdLogSingleEntry0` at `0x14039e05e`
- `watchdog!WdLogSingleEntry0` at `0x14039e150`
- `watchdog!WdLogSingleEntry0` at `0x14039e193`
- `watchdog!WdLogSingleEntry0` at `0x14039e1f6`
- `watchdog!WdLogSingleEntry0` at `0x14039e222`
- `watchdog!WdLogSingleEntry0` at `0x14039e65e`
- `watchdog!WdLogSingleEntry0` at `0x14039e8f7`
- `watchdog!WdLogSingleEntry0` at `0x14039ecd1`
- `watchdog!WdLogSingleEntry0` at `0x14039ed55`
- `watchdog!WdLogSingleEntry0` at `0x14039efa4`
- `watchdog!WdLogSingleEntry0` at `0x14039f034`
- `watchdog!WdLogSingleEntry0` at `0x14039f085`
- `watchdog!WdLogSingleEntry0` at `0x14039f19e`
- `watchdog!WdLogSingleEntry0` at `0x14039f24e`
- `watchdog!WdLogSingleEntry0` at `0x14039f2c1`
- `watchdog!WdLogSingleEntry0` at `0x14039f31c`
- `watchdog!WdLogSingleEntry0` at `0x14039f44e`
- `watchdog!WdLogSingleEntry0` at `0x14039f56f`
- `watchdog!WdLogSingleEntry0` at `0x14039f59c`
- `watchdog!WdLogSingleEntry0` at `0x14039f791`
- `watchdog!WdLogSingleEntry0` at `0x14039f811`
- `watchdog!WdLogSingleEntry0` at `0x14039f88e`
- `watchdog!WdLogSingleEntry0` at `0x14039f8df`
- `watchdog!WdLogSingleEntry5` at `0x14039acc1`
- `watchdog!WdLogSingleEntry5` at `0x14039b0d0`
- `watchdog!WdLogSingleEntry5` at `0x14039be92`
- `watchdog!WdLogSingleEntry5` at `0x14039d481`
- `watchdog!WdLogSingleEntry5` at `0x14039d4e9`
- `watchdog!WdLogSingleEntry5` at `0x14039d52e`
- `watchdog!WdLogSingleEntry5` at `0x14039d677`
- `watchdog!WdLogSingleEntry5` at `0x14039d6f8`
- `watchdog!WdLogSingleEntry5` at `0x14039d81a`
- `watchdog!WdLogSingleEntry5` at `0x14039d89c`
- `watchdog!WdLogSingleEntry5` at `0x14039d8e2`
- `watchdog!WdLogSingleEntry5` at `0x14039d964`
- `watchdog!WdLogSingleEntry5` at `0x14039db0f`
- `watchdog!WdLogSingleEntry5` at `0x14039db79`
- `watchdog!WdLogSingleEntry5` at `0x14039dc0d`
- `watchdog!WdLogSingleEntry5` at `0x14039dc6d`
- `watchdog!WdLogSingleEntry5` at `0x14039ddb3`
- `watchdog!WdLogSingleEntry5` at `0x14039de7f`
- `watchdog!WdLogSingleEntry5` at `0x14039deba`
- `watchdog!WdLogSingleEntry5` at `0x14039df69`
- `watchdog!WdLogSingleEntry5` at `0x14039e0e6`
- `watchdog!WdLogSingleEntry5` at `0x14039e5eb`
- `watchdog!WdLogSingleEntry5` at `0x14039ebc5`
- `watchdog!WdLogSingleEntry5` at `0x14039ec49`
- `watchdog!WdLogSingleEntry5` at `0x14039ecb1`
- `watchdog!WdLogSingleEntry5` at `0x14039acc1`
- `watchdog!WdLogSingleEntry5` at `0x14039b0d0`
- `watchdog!WdLogSingleEntry5` at `0x14039be92`
- `watchdog!WdLogSingleEntry5` at `0x14039d481`
- `watchdog!WdLogSingleEntry5` at `0x14039d4e9`
- `watchdog!WdLogSingleEntry5` at `0x14039d52e`
- `watchdog!WdLogSingleEntry5` at `0x14039d677`
- `watchdog!WdLogSingleEntry5` at `0x14039d6f8`
- `watchdog!WdLogSingleEntry5` at `0x14039d81a`
- `watchdog!WdLogSingleEntry5` at `0x14039d89c`
- `watchdog!WdLogSingleEntry5` at `0x14039d8e2`
- `watchdog!WdLogSingleEntry5` at `0x14039d964`
- `watchdog!WdLogSingleEntry5` at `0x14039db0f`
- `watchdog!WdLogSingleEntry5` at `0x14039db79`
- `watchdog!WdLogSingleEntry5` at `0x14039dc0d`
- `watchdog!WdLogSingleEntry5` at `0x14039dc6d`
- `watchdog!WdLogSingleEntry5` at `0x14039ddb3`
- `watchdog!WdLogSingleEntry5` at `0x14039de7f`
- `watchdog!WdLogSingleEntry5` at `0x14039deba`
- `watchdog!WdLogSingleEntry5` at `0x14039df69`
- `watchdog!WdLogSingleEntry5` at `0x14039e0e6`
- `watchdog!WdLogSingleEntry5` at `0x14039e5eb`
- `watchdog!WdLogSingleEntry5` at `0x14039ebc5`
- `watchdog!WdLogSingleEntry5` at `0x14039ec49`
- `watchdog!WdLogSingleEntry5` at `0x14039ecb1`
- `watchdog!WdLogSingleEntry1` at `0x14039dede`
- `watchdog!WdLogSingleEntry1` at `0x14039e2a0`
- `watchdog!WdLogSingleEntry1` at `0x14039e2f5`
- `watchdog!WdLogSingleEntry1` at `0x14039ee8e`

## string_xrefs

- `0x14039e233`: `FlipStereoTemporaryMono cannot be used with FlipStereoPreferRight. STATUS_INVALID_PARAMETER`
- `0x14039e021`: `FlipStereoTemporaryMono and FlipStereo cannot be set together. STATUS_INVALID_PARAMETER`
- `0x14039e161`: `FlipStereoTemporaryMono and FlipStereo can only be used with stereo primary allocations. STATUS_INVALID_PARAMETER`
- `0x14039f7a2`: `!NT_SUCCESS(ntStatus) || !m_pPresent->BltViaGDI() || m_pPresent->IsBltEmpty() || pPresent->Flags.ColorFill`
- `0x14039f89f`: `GetRenderCore()->IsCoreResourceSharedOwner() || ntStatus == STATUS_DEVICE_REMOVED`

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
  int v117; // eax
  char v118; // r12
  void *v119; // rax
  const RECT *pDstSubRects; // r14
  UINT SubRectCnt; // esi
  UINT v122; // ebx
  int v123; // r15d
  __int64 v124; // r9
  unsigned int v125; // r8d
  unsigned int v126; // r10d
  UINT k; // edx
  __int64 v128; // rcx
  int v129; // eax
  struct VIDSCH_SUBMIT_DATA_BASE *v130; // rbx
  int v131; // ecx
  int v132; // eax
  int v133; // ecx
  int v134; // eax
  int v135; // ecx
  int v136; // edx
  int v137; // eax
  int v138; // edx
  UINT v139; // ecx
  int v140; // ecx
  __int64 v141; // rdx
  D3DDDI_FLIPINTERVAL_TYPE *v142; // rbx
  int DeviceFlipMode; // eax
  const struct DXGALLOCATION *DisplayedPrimary; // rax
  __int64 v145; // rax
  int v146; // ecx
  __int64 v147; // rdx
  unsigned int v148; // edx
  int v149; // ebx
  DXGDEVICE *v150; // rbx
  char v151; // bl
  CWin32kLocks *v152; // r14
  DXGADAPTERSTOPRESETLOCKSHARED *v153; // rbx
  struct DXGDEVICE *v154; // rdi
  __int64 v155; // rbx
  struct DXGPROCESS *v156; // rax
  int v157; // eax
  const struct _DXGKWIN32KENG_INTERFACE *v158; // rbx
  int v159; // eax
  struct DXGADAPTERSTOPRESETLOCKSHARED *v160; // rsi
  struct DXGDEVICE *v161; // rdi
  __int64 v162; // rbx
  struct DXGPROCESS *v163; // rax
  unsigned int (__fastcall *v164)(const struct DXGK_PRESENT_PARAMS *, HDC, _QWORD, const RECT *, void *, int, unsigned int, unsigned int, int, int, int, void (__fastcall *)(const struct tagRECT *, const struct tagRECT *, struct tagRECT *, const struct tagRECT *, unsigned int, unsigned int), __int64 (__fastcall *)(struct tagRECT *, struct tagRECT *, const struct tagRECT *, const struct tagRECT *)); // r14
  int v165; // ebx
  int v166; // edi
  bool v167; // si
  HDC v168; // rax
  int v169; // r8d
  char v170; // al
  char v171; // r12
  CWin32kLocks *v172; // rax
  const RECT *v173; // r14
  UINT v174; // esi
  UINT v175; // ebx
  int v176; // r15d
  __int64 v177; // r9
  unsigned int v178; // r8d
  unsigned int v179; // r10d
  struct DXGPROCESS *v180; // rax
  unsigned int v181; // edi
  struct DXGPROCESS *v182; // rbx
  __int64 v183; // rcx
  __int64 v184; // r8
  int v185; // edx
  struct DXGALLOCATION *v186; // rdx
  __int64 v187; // rax
  unsigned int v188; // r12d
  unsigned __int8 *v189; // rsi
  unsigned int v190; // r14d
  __int64 v191; // rdx
  struct DXGHWQUEUE **v192; // rax
  __int64 v193; // rdi
  struct DXGHWQUEUE *v194; // rbx
  char v195; // r14
  char v196; // r12
  const RECT *v197; // rsi
  UINT v198; // edi
  UINT v199; // ebx
  unsigned int v200; // r15d
  __int64 v201; // r9
  unsigned int v202; // r8d
  unsigned int v203; // r10d
  __int64 v204; // rbx
  struct DXGALLOCATION *v205; // rax
  __int64 v206; // r8
  __int64 v207; // rcx
  __int64 v208; // rcx
  unsigned int v209; // edi
  DXGADAPTER *v210; // rcx
  unsigned int v211; // ecx
  int v212; // eax
  unsigned __int64 v213; // rcx
  int v214; // edx
  __int64 v215; // rcx
  signed int v216; // eax
  int v217; // r8d
  unsigned int m; // esi
  unsigned int v219; // r9d
  __int64 v220; // rbx
  __int64 v221; // r14
  __int64 v222; // rsi
  __int64 v223; // r10
  int v224; // r8d
  int v225; // r11d
  int v226; // edx
  unsigned int v227; // ebx
  const RECT *v228; // r8
  int v229; // r10d
  int v230; // r11d
  __int64 v231; // rdx
  RECT v232; // xmm0
  UINT Value; // edx
  unsigned int v234; // esi
  __int64 v235; // rcx
  __int64 v236; // r8
  int v237; // eax
  unsigned int v238; // edx
  int v239; // r8d
  int v240; // r9d
  int v241; // ecx
  const wchar_t *v242; // r9
  __int64 v243; // rax
  struct _DXGKARG_PRESENT *v244; // rbx
  int v245; // edx
  __int64 v246; // rax
  int v247; // ecx
  int v248; // edx
  int v249; // eax
  unsigned __int8 v250; // al
  DXGDEVICE *v251; // rcx
  unsigned int v252; // edx
  int v253; // eax
  const struct _DXGKWIN32KENG_INTERFACE *v254; // rsi
  int v255; // ebx
  int v256; // eax
  int v257; // ecx
  int v258; // eax
  DXGPRESENTMUTEX *v259; // rcx
  __int64 v260; // rbx
  const struct _CDDDXGK_INTERFACE *CddInterface; // rax
  int v262; // eax
  struct VIDMM_DMA_BUFFER *v263; // rdx
  unsigned __int8 v264; // al
  __int64 v265; // rax
  int v266; // eax
  struct VIDMM_DMA_BUFFER *v267; // rdx
  int v268; // eax
  __int64 v269; // rcx
  struct VIDMM_GLOBAL *v270; // rdx
  VIDMM_EXPORT *v271; // rcx
  struct DXGALLOCATION *v272; // rsi
  unsigned int v273; // edx
  __int128 v274; // xmm0
  __int64 v275; // rax
  int v276; // eax
  UINT v277; // ecx
  enum _D3DDDIFORMAT v278; // ebx
  __int64 v279; // rcx
  __int64 v280; // rdx
  __int64 v281; // r8
  __int64 v282; // rdx
  int v283; // eax
  unsigned int v284; // edx
  COREDEVICEACCESS *v285; // rcx
  unsigned __int8 v286; // di
  int v287; // ebx
  LONG v288; // ecx
  LONG v289; // ecx
  LONG v290; // eax
  struct DXGPROCESS *v291; // rax
  D3DKMT_HANDLE v292; // eax
  DXGDEVICE *v293; // rbx
  int v294; // edi
  unsigned __int8 v295; // al
  char v296; // bl
  const struct _DXGKWIN32KENG_INTERFACE *v297; // rbx
  int v298; // eax
  int v299; // eax
  unsigned int (__fastcall *v300)(HDC, _QWORD, __int64, _QWORD, _DWORD); // r14
  unsigned int v301; // edi
  __int64 v302; // rsi
  HDC v303; // rax
  int v304; // eax
  __int64 v305; // rax
  const wchar_t *v306; // r9
  __int64 v307; // rcx
  unsigned __int8 v308; // r8
  int CurrentOrientation; // eax
  __int64 v310; // rsi
  unsigned int v311; // r14d
  unsigned int v312; // r12d
  struct DXGHWQUEUE **v313; // rax
  struct DXGHWQUEUE *v314; // rbx
  struct DXGPROCESS *v315; // rax
  __int64 v316; // [rsp+20h] [rbp-100h]
  struct _DXGKARG_PRESENT *v317; // [rsp+20h] [rbp-100h]
  __int64 v318; // [rsp+28h] [rbp-F8h]
  __int64 v319; // [rsp+28h] [rbp-F8h]
  __int64 v320; // [rsp+30h] [rbp-F0h]
  __int64 v321; // [rsp+30h] [rbp-F0h]
  __int64 v322; // [rsp+38h] [rbp-E8h]
  __int64 v323; // [rsp+38h] [rbp-E8h]
  __int64 v324; // [rsp+40h] [rbp-E0h]
  int v325; // [rsp+40h] [rbp-E0h]
  __int64 v326; // [rsp+40h] [rbp-E0h]
  int v327; // [rsp+48h] [rbp-D8h]
  struct VIDSCH_SUBMIT_DATA_BASE *v328; // [rsp+58h] [rbp-C8h]
  enum _D3DDDIFORMAT v329; // [rsp+60h] [rbp-C0h]
  struct DXGALLOCATION *v331; // [rsp+A8h] [rbp-78h] BYREF
  char v332; // [rsp+B0h] [rbp-70h]
  unsigned int v333; // [rsp+B4h] [rbp-6Ch] BYREF
  unsigned int v334; // [rsp+B8h] [rbp-68h]
  char v335; // [rsp+BCh] [rbp-64h]
  unsigned int v336; // [rsp+C0h] [rbp-60h]
  CWin32kLocks *v337; // [rsp+C8h] [rbp-58h]
  struct DXGALLOCATION *v338; // [rsp+D0h] [rbp-50h] BYREF
  unsigned int v339; // [rsp+D8h] [rbp-48h]
  DXGADAPTERSTOPRESETLOCKSHARED *v340; // [rsp+E0h] [rbp-40h]
  enum _D3DDDIFORMAT Format; // [rsp+E8h] [rbp-38h]
  unsigned int v342[2]; // [rsp+F0h] [rbp-30h]
  const struct _DXGKWIN32KENG_INTERFACE *v343; // [rsp+F8h] [rbp-28h]
  struct VIDSCH_SUBMIT_DATA_BASE *v344; // [rsp+100h] [rbp-20h]
  unsigned int v345[2]; // [rsp+108h] [rbp-18h]
  unsigned int v346; // [rsp+110h] [rbp-10h]
  __int64 v347; // [rsp+118h] [rbp-8h] BYREF
  _BYTE v348[24]; // [rsp+120h] [rbp+0h] BYREF
  struct DXGCONTEXT **v349; // [rsp+138h] [rbp+18h]
  __int64 v350; // [rsp+140h] [rbp+20h] BYREF
  DXGCONTEXT *v351; // [rsp+148h] [rbp+28h]
  char v352[8]; // [rsp+150h] [rbp+30h] BYREF
  char v353[8]; // [rsp+158h] [rbp+38h] BYREF
  char v354[8]; // [rsp+160h] [rbp+40h] BYREF
  char v355[8]; // [rsp+168h] [rbp+48h] BYREF
  __int64 v356; // [rsp+170h] [rbp+50h] BYREF
  _D3DKMT_UNLOCK2 v357; // [rsp+178h] [rbp+58h] BYREF
  struct _D3DKMT_UNLOCK v358; // [rsp+180h] [rbp+60h] BYREF
  struct _DXGKARG_DESCRIBEALLOCATION v359; // [rsp+190h] [rbp+70h] BYREF
  struct _DXGKARG_DESCRIBEALLOCATION v360; // [rsp+1C0h] [rbp+A0h] BYREF
  _BYTE v361[24]; // [rsp+1F0h] [rbp+D0h] BYREF
  struct _D3DKMT_LOCK2 v362; // [rsp+208h] [rbp+E8h] BYREF
  _BYTE v363[24]; // [rsp+220h] [rbp+100h] BYREF
  struct _D3DKMT_LOCK v364; // [rsp+238h] [rbp+118h] BYREF
  struct _DXGKARG_DESCRIBEALLOCATION v365; // [rsp+268h] [rbp+148h] BYREF
  enum _D3DDDIFORMAT v366[4]; // [rsp+2A0h] [rbp+180h]
  _DWORD v367[8]; // [rsp+2F0h] [rbp+1D0h] BYREF
  _QWORD v368[70]; // [rsp+310h] [rbp+1F0h] BYREF
  struct _DXGKARG_PRESENT v369; // [rsp+540h] [rbp+420h] BYREF
  struct tagRECT v370; // [rsp+5F0h] [rbp+4D0h] BYREF
  struct tagRECT v371; // [rsp+600h] [rbp+4E0h] BYREF
  __int128 v372; // [rsp+610h] [rbp+4F0h] BYREF
  struct tagRECT Source1; // [rsp+620h] [rbp+500h] BYREF
  struct tagRECT v374; // [rsp+630h] [rbp+510h] BYREF
  int v375; // [rsp+640h] [rbp+520h]
  unsigned int v376; // [rsp+644h] [rbp+524h]
  _QWORD v377[39]; // [rsp+648h] [rbp+528h] BYREF
  _DWORD v378[16]; // [rsp+780h] [rbp+660h] BYREF
  _DWORD v379[16]; // [rsp+7C0h] [rbp+6A0h] BYREF
  _DWORD v380[16]; // [rsp+800h] [rbp+6E0h] BYREF
  _DWORD v381[16]; // [rsp+840h] [rbp+720h] BYREF
  _DWORD v382[16]; // [rsp+880h] [rbp+760h] BYREF
  _DWORD v383[16]; // [rsp+8C0h] [rbp+7A0h] BYREF
  _DWORD v384[16]; // [rsp+900h] [rbp+7E0h] BYREF
  _DWORD v385[16]; // [rsp+940h] [rbp+820h] BYREF
  _DWORD v386[16]; // [rsp+980h] [rbp+860h] BYREF
  _DWORD v387[16]; // [rsp+9C0h] [rbp+8A0h] BYREF
  _DWORD v388[16]; // [rsp+A00h] [rbp+8E0h] BYREF
  _DWORD v389[16]; // [rsp+A40h] [rbp+920h] BYREF

  v7 = this;
  v351 = this;
  v9 = *((_QWORD *)this + 2);
  v337 = a5;
  v340 = a4;
  v10 = *(ADAPTER_RENDER **)(v9 + 16);
  v344 = a7;
  v349 = a6;
  if ( !ADAPTER_RENDER::IsCoreResourceSharedOwner(v10) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4232;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"GetRenderCore()->IsCoreResourceSharedOwner()",
      4232,
      0,
      0,
      0,
      0);
  }
  if ( *((_QWORD *)v7 + 45) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4233;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"m_pPresentDmaBuffer == NULL", 4233, 0, 0, 0, 0);
  }
  if ( (*((_DWORD *)a2 + 22) & 0x4000) != 0 )
  {
    v24 = -1073741811;
    WdLogSingleEntry2(3, v7, -1073741811);
    WdLogGlobalForLineNumber = 4239;
    return (unsigned int)v24;
  }
  Win32kInterface = DXGPROCESS::GetWin32kInterface(*(DXGPROCESS **)(*((_QWORD *)v7 + 2) + 40LL));
  v12 = *((_DWORD *)a2 + 22);
  v343 = Win32kInterface;
  if ( (v12 & 0x12000) == 0x12000 )
  {
    v24 = -1073741811;
    WdLogSingleEntry2(3, v7, -1073741811);
    WdLogGlobalForLineNumber = 4250;
    return (unsigned int)v24;
  }
  memset(&v369, 0, sizeof(v369));
  v339 = *((_DWORD *)a2 + 5);
  v333 = *((_DWORD *)a2 + 6);
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
  DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v331, 0);
  DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v338, 0);
  DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v347, 0);
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
    DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v352, v54);
    _InterlockedDecrement((volatile signed __int32 *)(v50 + 264));
    ExReleasePushLockSharedEx(v50 + 248, 0);
    KeLeaveCriticalRegion();
    DXGALLOCATIONREFERENCE::MoveAssign(&v338, v352);
    DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v352);
    if ( !v338 )
    {
      v24 = -1073741811;
      WdLogSingleEntry3(3, -1073741811, v7, *((unsigned int *)a2 + 6));
      WdLogGlobalForLineNumber = 4305;
      goto LABEL_34;
    }
    if ( *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v338 + 1) + 16LL) + 16LL) != *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2)
                                                                                                + 16LL)
                                                                                    + 16LL) )
    {
      v24 = -1073741811;
      WdLogSingleEntry3(2, *((_QWORD *)v7 + 2), v338, -1073741811);
      v77 = v338;
      WdLogGlobalForLineNumber = 4315;
      goto LABEL_119;
    }
    memset(&v365, 0, sizeof(v365));
    v365.hAllocation = *(HANDLE *)(*((_QWORD *)v338 + 6) + 16LL);
    v55 = ADAPTER_RENDER::DdiDescribeAllocation(*(ADAPTER_RENDER **)(*((_QWORD *)v7 + 2) + 16LL), &v365);
    v24 = v55;
    if ( v55 < 0 )
    {
      v204 = v55;
      WdLogSingleEntry4(2, v55, v7, *(_QWORD *)(*((_QWORD *)v338 + 6) + 16LL), v338);
      v205 = v338;
      WdLogGlobalForLineNumber = 4328;
      goto LABEL_352;
    }
    Width = v365.Width;
    v345[0] = v365.Height;
  }
  else
  {
    Width = 0;
    v345[0] = 0;
  }
  v17 = (*((_DWORD *)a2 + 22) & 0x8002) == 0;
  v342[0] = Width;
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
    DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v353, v49);
    _InterlockedDecrement((volatile signed __int32 *)(v45 + 264));
    ExReleasePushLockSharedEx(v45 + 248, 0);
    KeLeaveCriticalRegion();
    DXGALLOCATIONREFERENCE::MoveAssign(&v331, v353);
    DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v353);
    v20 = v331;
    if ( !v331 )
    {
      v24 = -1073741811;
      WdLogSingleEntry3(3, -1073741811, v7, *((unsigned int *)a2 + 5));
      WdLogGlobalForLineNumber = 4343;
      goto LABEL_34;
    }
    memset(&v360, 0, sizeof(v360));
    v360.hAllocation = *(HANDLE *)(*((_QWORD *)v331 + 6) + 16LL);
    if ( (*((_DWORD *)a2 + 22) & 0x10000000) != 0 )
    {
      v18 = *((_DWORD *)a2 + 379);
      v360.Width = v18;
      Height = *((_DWORD *)a2 + 380);
      v360.Height = Height;
      Format = *((_DWORD *)a2 + 381);
      v360.Format = Format;
      goto LABEL_18;
    }
    v108 = *(ADAPTER_RENDER **)(*((_QWORD *)v7 + 2) + 16LL);
    if ( *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v331 + 1) + 16LL) + 16LL) == *((_QWORD *)v108 + 2) )
    {
      v109 = ADAPTER_RENDER::DdiDescribeAllocation(v108, &v360);
      v24 = v109;
      if ( v109 >= 0 )
      {
        Height = v360.Height;
        v18 = v360.Width;
        Format = v360.Format;
        goto LABEL_17;
      }
      v204 = v109;
      WdLogSingleEntry4(2, v109, v7, *(_QWORD *)(*((_QWORD *)v331 + 6) + 16LL), v331);
      v205 = v331;
      WdLogGlobalForLineNumber = 4382;
LABEL_352:
      v78 = L"ret = 0x%I64x Context 0x%I64x: DdiDescribeAllocation failed 0x%I64x 0x%I64x";
      v324 = 0;
      v322 = (__int64)v205;
      v320 = *(_QWORD *)(*((_QWORD *)v205 + 6) + 16LL);
      v318 = (__int64)v7;
      v316 = v204;
      goto LABEL_120;
    }
    v24 = -1073741811;
    WdLogSingleEntry3(2, *((_QWORD *)v7 + 2), v331, -1073741811);
    v77 = v331;
    WdLogGlobalForLineNumber = 4371;
LABEL_119:
    v324 = 0;
    v78 = L"Device 0x%p does not match allocation 0x%p owner, returning 0x%I64x";
    v322 = 0;
    v320 = -1073741811;
    v318 = (__int64)v77;
    v316 = *((_QWORD *)v7 + 2);
    goto LABEL_120;
  }
  v18 = 0;
  Format = D3DDDIFMT_UNKNOWN;
  Height = 0;
LABEL_17:
  v20 = v331;
LABEL_18:
  v21 = *((unsigned int *)a2 + 6);
  v334 = v18;
  v336 = Height;
  if ( (_DWORD)v21 )
  {
    LODWORD(v22) = *((_DWORD *)a2 + 22);
    if ( (v22 & 0x10000) == 0 )
      goto LABEL_355;
  }
  v22 = *((unsigned int *)a2 + 22);
  if ( (v22 & 4) == 0 )
  {
    v346 = 0;
    if ( (v22 & 1) == 0 )
    {
      v23 = 2;
      if ( (v22 & 2) == 0 )
      {
        if ( (v22 & 0x8000) == 0 )
        {
          v24 = -1073741811;
          WdLogSingleEntry5(3, -1073741811, v7, *((_QWORD *)a2 + 9), *((unsigned int *)a2 + 16), v22);
          WdLogGlobalForLineNumber = 6485;
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
            v27 = v340;
            v28 = SubmitPresentHistoryTokenPreparation(
                    v340,
                    a3,
                    *(struct DXGADAPTER **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 16LL),
                    (struct _D3DKMT_PRESENTHISTORYTOKEN *)((char *)a2 + 360),
                    *((void **)a2 + 44),
                    (v22 & 0x10) != 0);
            if ( v28 >= 0 )
            {
              TOKEN_BINDING_GUARD::TOKEN_BINDING_GUARD(
                (TOKEN_BINDING_GUARD *)v367,
                (struct _D3DKMT_PRESENTHISTORYTOKEN *)((char *)a2 + 360),
                v27,
                a3);
              v367[0] = SubmitPresentHistoryToken(
                          (const struct _D3DKMT_PRESENTHISTORYTOKEN *)((char *)a2 + 360),
                          a3,
                          v27,
                          v337,
                          1,
                          0,
                          a2,
                          v344,
                          v7,
                          0,
                          0);
              v24 = v367[0];
              TOKEN_BINDING_GUARD::~TOKEN_BINDING_GUARD((TOKEN_BINDING_GUARD *)v367);
              if ( v24 >= 0 )
              {
LABEL_30:
                v29 = v347;
                if ( v347 )
                {
                  if ( (*((_DWORD *)a2 + 22) & 0x10000000) == 0 )
                  {
                    v110 = *((_QWORD *)v7 + 2);
                    v111 = *(_QWORD *)(v110 + 1896);
                    if ( v111 )
                    {
                      if ( (*(_DWORD *)(*(_QWORD *)(v110 + 40) + 408LL) & 4) == 0 )
                      {
                        memset(v377, 0, 0x130u);
                        v112 = v346;
                        v375 = *(_DWORD *)a2;
                        v376 = v346;
                        LODWORD(v377[0]) = (*(_DWORD *)(*(_QWORD *)(v347 + 48) + 4LL) >> 6) & 0xF;
                        v113 = &v377[1];
                        HIDWORD(v377[0]) = *((_DWORD *)a2 + 23);
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
                        LODWORD(v377[33]) = 0;
                        LODWORD(v377[37]) = 4;
                        LODWORD(v377[35]) = 0;
                        v116 = OUTPUTDUPL_MGR::ProcessPresent(
                                 *(OUTPUTDUPL_MGR **)(*(_QWORD *)(v111 + 3248) + 120LL),
                                 v7,
                                 (struct _D3DKMT_OUTPUTDUPLPRESENTFLAGS)4,
                                 v112,
                                 HIDWORD(v377[0]),
                                 (struct _D3DKMT_PRESENT_RGNS *)&v377[33],
                                 a2,
                                 (*(_DWORD *)(*(_QWORD *)(v29 + 48) + 4LL) >> 6) & 0xF,
                                 v349,
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
        WdLogGlobalForLineNumber = 6449;
        goto LABEL_34;
      }
    }
    if ( (v22 & 0x100) != 0 )
    {
      v279 = *((_QWORD *)v7 + 2);
      if ( !*(_QWORD *)(v279 + 1896) )
      {
        v24 = -1073741811;
        WdLogSingleEntry2(3, *((_QWORD *)v7 + 2), -1073741811);
        WdLogGlobalForLineNumber = 5398;
        goto LABEL_34;
      }
      v280 = *((unsigned int *)a2 + 4);
      v281 = *(unsigned int *)(v279 + 1904);
      if ( (unsigned int)v281 <= (unsigned int)v280 )
      {
        WdLogSingleEntry2(3, v280, v281);
        WdLogGlobalForLineNumber = 5404;
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
        WdLogGlobalForLineNumber = 5426;
        goto LABEL_34;
      }
      v339 = 0;
    }
    else
    {
      if ( !v43 || (v282 = *((unsigned int *)a2 + 16), !(_DWORD)v282) || !v18 || !Height || (v22 & 0x802C) != 0 )
      {
        v24 = -1073741811;
        WdLogSingleEntry5(3, v7, v43, *((unsigned int *)a2 + 16), *((unsigned int *)a2 + 22), -1073741811);
        WdLogGlobalForLineNumber = 5446;
        goto LABEL_34;
      }
      if ( (((unsigned int)v22 >> 9) & 1) != 0 || (v22 & 0x400) != 0 )
      {
        if ( (((unsigned int)v22 >> 9) & 1) == (((unsigned int)v22 >> 10) & 1) )
        {
          v24 = -1073741811;
          WdLogSingleEntry5(3, -1073741811, v7, v43, v282, v22);
          WdLogGlobalForLineNumber = 5458;
          goto LABEL_34;
        }
        if ( (v22 & 0x100) == 0
          || !ADAPTER_DISPLAY::IsVidPnSourceOwner(
                *(ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3248LL),
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
          WdLogGlobalForLineNumber = 5467;
          goto LABEL_34;
        }
      }
    }
    v56 = *((_DWORD *)a2 + 22);
    v57 = v56 ^ (v56 & 2 | *(_BYTE *)&v369.Flags.0 & 0xFD);
    v56 >>= 5;
    v58 = (*((_DWORD *)a2 + 22) & 2 | v369.Flags.Value & 0xFFFFFFFD) ^ v57 & 1;
    v369.Flags.Value = v58
                     ^ ((unsigned __int8)v58
                      ^ (unsigned __int8)v56)
                     & 0x10
                     ^ ((unsigned __int8)(v58 ^ (v58 ^ v56) & 0x10)
                      ^ (unsigned __int8)v56)
                     & 0x20
                     ^ ((unsigned __int8)(v58 ^ (v58 ^ v56) & 0x10 ^ (v58 ^ (v58 ^ v56) & 0x10 ^ v56) & 0x20)
                      ^ (unsigned __int8)v56)
                     & 0x40;
    v369.Color = *((_DWORD *)a2 + 7);
    v24 = DXGPRESENT::CheckInput(*((DXGPRESENT **)v7 + 19), (const struct _D3DKMT_PRESENT *)a2, v18, Height);
    if ( v24 < 0 )
      goto LABEL_31;
    v59 = (DXGPRESENT *)*((_QWORD *)v7 + 19);
    v60 = 0;
    v332 = 0;
    if ( (*((_DWORD *)v59 + 1) & 4) != 0 )
    {
LABEL_638:
      if ( bTracingEnabled && !v60 && (Microsoft_Windows_DxgKrnlEnableBits & 0x20) != 0 )
        McTemplateK0p_EtwWriteTransfer(&DxgkControlGuid_Context, EventBlitCancel, 0, *((_QWORD *)a2 + 1));
      v26 = a3;
      goto LABEL_63;
    }
    DXGPRESENT::CheckOutput(v59, Width, v345[0]);
    v61 = *(DXGADAPTER **)(*((_QWORD *)v7 + 2) + 1896LL);
    if ( !v61 || DXGADAPTER::IsDisplayOnlyAdapter(v61) )
    {
      v62 = a3;
      v63 = DXGCONTEXT::WaitForQueuedPresentLimit(v7, 0, (*((_DWORD *)a2 + 22) & 0x10) == 0, a3);
      v24 = v63;
      if ( v63 < 0 )
      {
        WdLogSingleEntry2(4, v63, v7);
        WdLogGlobalForLineNumber = 5516;
        goto LABEL_34;
      }
    }
    else
    {
      if ( *(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) != *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 16LL) )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 5492;
        DxgkLogInternalTriageEvent(
          0,
          262146,
          -1,
          (unsigned int)L"GetDisplayAdapter() == GetRenderAdapter()",
          5492,
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
          WdLogSingleEntry2(4, v107, v7);
          WdLogGlobalForLineNumber = 5502;
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
      WdLogGlobalForLineNumber = 5530;
      DxgkLogInternalTriageEvent(
        0,
        262146,
        -1,
        (unsigned int)L"m_pPresentDmaBuffer || IsParavirtualized()",
        5530,
        0,
        0,
        0,
        0);
    }
    DXGPRESENTMUTEX::DXGPRESENTMUTEX(
      (DXGPRESENTMUTEX *)v348,
      *(struct ADAPTER_RENDER *const *)(*((_QWORD *)v7 + 2) + 16LL));
    if ( (*((_DWORD *)a2 + 22) & 0x10000) != 0 )
    {
      v64 = 0;
      if ( *((_DWORD *)a2 + 6) )
      {
        v82 = *((_QWORD *)v338 + 6);
        v83 = *(_DWORD *)(v82 + 4);
        *(_DWORD *)(v82 + 4) = v83 | 0x400;
        v64 = (v83 & 0x400) == 0;
      }
      v65 = v340;
    }
    else
    {
      COREDEVICEACCESS::Release(v62);
      v65 = v340;
      DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v340);
      DXGPRESENTMUTEX::Acquire((DXGPRESENTMUTEX *)v348);
      DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v65);
      v283 = COREDEVICEACCESS::AcquireShared(v62, 0);
      v24 = v283;
      if ( v283 < 0 )
      {
        WdLogSingleEntry2(4, v283, v7);
        WdLogGlobalForLineNumber = 5551;
        goto LABEL_476;
      }
      v64 = 0;
    }
    v66 = (*((__int64 (**)(void))v343 + 1))();
    CurrentThreadId = PsGetCurrentThreadId();
    v17 = *((_BYTE *)v7 + 434) == 0;
    *(_QWORD *)v342 = CurrentThreadId;
    if ( v17 )
    {
      VIDSCH_EXPORT::VidSchGetMonitorPowerState(
        *(VIDSCH_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 736LL),
        *(struct _VIDSCH_GLOBAL **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 744LL));
      CurrentThreadId = *(HANDLE *)v342;
    }
    v68 = *((_QWORD *)v7 + 19);
    if ( *(_DWORD *)(v68 + 8) == v66
      && *(HANDLE *)(v68 + 56) == CurrentThreadId
      && *(_QWORD *)(v68 + 48) == *((_QWORD *)a2 + 1)
      && !*(_DWORD *)(v68 + 64)
      && !v64 )
    {
      v284 = *(_DWORD *)(v68 + 4);
      if ( !(((v284 & 8) != 0) | BYTE1(v284) & 1) )
      {
        if ( (v284 & 1) != 0 )
        {
          v24 = -1071775738;
        }
        else if ( (((*((_DWORD *)a2 + 22) & 0x10000) == 0) & (unsigned __int8)~(unsigned __int8)(v284 >> 4)) != 0 )
        {
          DXGDEVICE::SynchronizePresentToPrimary(*((DXGDEVICE **)v7 + 2), v7, (struct DXGPRESENTMUTEX *)v348, 0);
        }
        goto LABEL_571;
      }
    }
    DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v348);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v65);
    COREDEVICEACCESS::Release(v62);
    v69 = v337;
    v70 = CWin32kLocks::Lock(v337, *((HWND *)a2 + 1), *((_WORD *)a2 + 45) & 1, 1, 0);
    if ( _bittest((const signed __int32 *)a2 + 22, 0x10u) )
    {
      v356 = 0;
      (*((void (__fastcall **)(_QWORD, __int64 *))v343 + 31))(*(_QWORD *)v69, &v356);
      *(_QWORD *)(*((_QWORD *)v7 + 19) + 440LL) = v356;
    }
    if ( !_bittest((const signed __int32 *)a2 + 22, 0x10u) )
      DXGPRESENTMUTEX::Acquire((DXGPRESENTMUTEX *)v348);
    DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v340);
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
        WdLogSingleEntry2(4, 0, v7);
        WdLogGlobalForLineNumber = 5674;
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
              v334,
              v336,
              Format,
              1);
      if ( v24 == 261 )
      {
        DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v348);
        COREDEVICEACCESS::Release(a3);
        DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v340);
        if ( DXGPRESENT::CheckOcclusion(*((DXGPRESENT **)v7 + 19)) )
          v24 = -1071775738;
        if ( (*((_DWORD *)a2 + 22) & 0x10000) == 0 )
          DXGPRESENTMUTEX::Acquire((DXGPRESENTMUTEX *)v348);
        DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v340);
        v117 = COREDEVICEACCESS::AcquireShared(a3, 0);
        v92 = v117;
        if ( v117 < 0 )
        {
          WdLogSingleEntry1(4, v117);
          v285 = a3;
          WdLogGlobalForLineNumber = 5717;
          goto LABEL_565;
        }
        if ( v24 != -1071775738 )
          v24 = DXGPRESENT::CheckVisRgn(
                  *((DXGPRESENT **)v7 + 19),
                  (const struct _D3DKMT_PRESENT *)a2,
                  v71,
                  v73,
                  *((const struct DXGDEVICE **)v7 + 2),
                  v334,
                  v336,
                  Format,
                  0);
      }
      v74 = *((_QWORD *)v7 + 19);
      if ( v24 < 0 )
      {
        v62 = a3;
        v69 = v337;
        if ( (*(_BYTE *)(v74 + 4) & 1) != 0 )
        {
          *(_QWORD *)(v74 + 56) = *(_QWORD *)v342;
          *(_DWORD *)(*((_QWORD *)v7 + 19) + 8LL) = v66;
        }
LABEL_115:
        v75 = *((_QWORD *)v7 + 19);
        v335 = 0;
        v76 = *(_DWORD *)(v75 + 4);
        if ( (v76 & 0x10) == 0 )
        {
          if ( v24 >= 0 && (v76 & 2) == 0 )
          {
            if ( (*((unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD))v343 + 30))(0, 0, 0) )
            {
              if ( (*((_DWORD *)a2 + 22) & 0x12100) != 0x10000 )
              {
                WdLogSingleEntry0(1);
                v305 = 6163;
                v306 = L"((pPresent->Flags.RedirectedBlt) && (!pPresent->Flags.RestrictVidPnSource) && (!pPresent->Flags.Rotate))";
LABEL_620:
                WdLogGlobalForLineNumber = v305;
                DxgkLogInternalTriageEvent(0, 262146, -1, (_DWORD)v306, v305, 0, 0, 0, 0);
              }
            }
            else if ( !*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) && (*((_DWORD *)a2 + 22) & 0x4000000) == 0 )
            {
              WdLogSingleEntry0(1);
              v305 = 6168;
              v306 = L"GetDisplayAdapter() != NULL || pPresent->Flags.CrossAdapter";
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
            v88 = v340;
            DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v340);
            COREDEVICEACCESS::Release(a3);
            memset(v368, 0, 0x228u);
            LODWORD(v368[0]) = DXGPRESENT::GetDdiSubRectCnt(*((DXGPRESENT **)v7 + 19), 0);
            v368[1] = DXGPRESENT::GetDdiSubRectList(*((DXGPRESENT **)v7 + 19), 0);
            v89 = 1;
            v90 = 0;
            v368[3] = *((unsigned int *)v7 + 6);
            for ( LODWORD(v368[2]) = 1; (unsigned int)v90 < *((_DWORD *)a2 + 23); ++LODWORD(v368[2]) )
            {
              v307 = *((unsigned int *)a2 + v90 + 24);
              v90 = (unsigned int)(v90 + 1);
              v368[v89 + 3] = v307;
              v89 = LODWORD(v368[2]) + 1;
            }
            if ( !*((_BYTE *)v7 + 434)
              && VIDSCH_EXPORT::VidSchGetNumUnorderedWaitsInDevice(
                   *(VIDSCH_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 736LL),
                   *(struct _VIDSCH_DEVICE **)(*((_QWORD *)v7 + 2) + 800LL)) )
            {
              v335 = 1;
              LOBYTE(v368[68]) = 1;
            }
            (*((void (__fastcall **)(HDC, _QWORD *))v87 + 32))(v84, v368);
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
                v369.SubRectCnt = DXGPRESENT::GetDdiSubRectCnt(*((DXGPRESENT **)v7 + 19), j);
                if ( v369.SubRectCnt )
                {
                  if ( (*((_DWORD *)a2 + 22) & 0x10000) != 0 )
                  {
                    v95 = v333;
                  }
                  else
                  {
                    if ( *((_BYTE *)v7 + 432) || (v308 = 0, *((_BYTE *)v7 + 433)) )
                      v308 = 1;
                    v95 = DXGDEVICE::OpenCddPrimaryHandle(*((DXGDEVICE **)v7 + 2), j, v308, *((_DWORD *)v7 + 97));
                    v333 = v95;
                  }
                  if ( v95 )
                    break;
                }
LABEL_161:
                ;
              }
              v369.pDstSubRects = DXGPRESENT::GetDdiSubRectList(*((DXGPRESENT **)v7 + 19), j);
              if ( (*((_DWORD *)a2 + 22) & 0x2000) != 0 )
              {
                CurrentOrientation = ADAPTER_DISPLAY::GetCurrentOrientation(
                                       *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3248LL),
                                       j,
                                       1);
                v369.Flags.Value = v369.Flags.Value & 0xFFFFFF7F | (CurrentOrientation != 1 ? 0x80 : 0);
              }
              v374 = 0;
              if ( (*((_DWORD *)a2 + 22) & 0x10000) != 0 )
                v96 = &v374;
              else
                v96 = (struct tagRECT *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3248LL)
                                                   + 128LL)
                                       + 4024LL * j
                                       + 628);
              v97 = (RECT *)*((_QWORD *)v7 + 19);
              v369.SrcRect = v97[9];
              DXGPRESENT::GetDdiDstRect((DXGPRESENT *)v97, &v369.DstRect, v96);
              if ( !bTracingEnabled || !*((_QWORD *)v7 + 45) )
              {
LABEL_157:
                if ( *((_BYTE *)v7 + 434) )
                {
                  v310 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 16LL);
                  v311 = *((_DWORD *)v338 + 5);
                  v312 = *((_DWORD *)v331 + 5);
                  v313 = (struct DXGHWQUEUE **)*((_QWORD *)a2 + 188);
                  if ( v313 )
                    v314 = *v313;
                  else
                    v314 = 0;
                  v315 = DXGPROCESS::GetCurrent();
                  v99 = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendBlt(
                          (DXG_GUEST_VIRTUALGPU_VMBUS *)(v310 + 4792),
                          v315,
                          v7,
                          v314,
                          v312,
                          v311,
                          &v369.SrcRect,
                          &v369.DstRect,
                          v369.SubRectCnt,
                          v369.pDstSubRects,
                          v369.PrivateDriverDataSize,
                          (unsigned __int8 *)v369.pPrivateDriverData);
                  v98 = a3;
                }
                else
                {
                  v98 = a3;
                  v329 = Format;
                  v328 = v344;
                  *((_DWORD *)v344 + 29) = j;
                  v99 = DXGCONTEXT::SubmitPresent(
                          v7,
                          (const struct _D3DKMT_PRESENT *)a2,
                          *((struct DXGHWQUEUE ***)a2 + 188),
                          *((_DWORD *)a2 + 23),
                          v349,
                          v331,
                          v339,
                          v333,
                          &v369,
                          0,
                          *((struct VIDMM_DMA_BUFFER **)v7 + 45),
                          v328,
                          v329,
                          a3);
                }
                *((_QWORD *)v7 + 45) = 0;
                v24 = v99;
                if ( (*((_DWORD *)a2 + 22) & 0x10000) != 0
                  && *(_DWORD *)(*((_QWORD *)v7 + 19) + 440LL) == *((_DWORD *)a2 + 96) )
                {
                  *((_DWORD *)a2 + 90) = 3;
                  *((_QWORD *)a2 + 48) = *(_QWORD *)(*((_QWORD *)v7 + 19) + 440LL);
                  if ( v369.SubRectCnt <= 0x10 )
                  {
                    *((_DWORD *)a2 + 100) = v369.SubRectCnt;
                    for ( k = 0; k < v369.SubRectCnt; *(RECT *)((char *)a2 + 16 * v128 + 404) = v369.pDstSubRects[v128] )
                      v128 = k++;
                  }
                  else
                  {
                    *((_DWORD *)a2 + 100) = 1;
                    *(RECT *)((char *)a2 + 404) = v369.DstRect;
                  }
                  *((_DWORD *)a2 + 91) = 16 * (*((_DWORD *)a2 + 100) + 3);
                  DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v348);
                  v24 = SubmitPresentHistoryToken(
                          (const struct _D3DKMT_PRESENTHISTORYTOKEN *)((char *)a2 + 360),
                          v98,
                          v340,
                          v337,
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
              v118 = (unsigned __int8)VIDMM_EXPORT::VidMmETWAllocationHandle(
                                        *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                                        *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 768LL),
                                        v333);
              v119 = VIDMM_EXPORT::VidMmETWAllocationHandle(
                       *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                       *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 768LL),
                       v339);
              pDstSubRects = v369.pDstSubRects;
              SubRectCnt = v369.SubRectCnt;
              *(_QWORD *)v342 = v119;
              v343 = (const struct _DXGKWIN32KENG_INTERFACE *)*((_QWORD *)v7 + 45);
              if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x20) != 0 )
                McTemplateK0ppxppttqddddddddq_EtwWriteTransfer(
                  (unsigned int)&DxgkControlGuid_Context,
                  (unsigned int)EventBlit,
                  0,
                  *((_QWORD *)a2 + 1),
                  (char)v343,
                  0,
                  v342[0],
                  v118,
                  1,
                  0,
                  *(_BYTE *)&v369.Flags.0,
                  v369.SrcRect.left,
                  v369.SrcRect.right,
                  v369.SrcRect.top,
                  v369.SrcRect.bottom,
                  v369.DstRect.left,
                  v369.DstRect.right,
                  v369.DstRect.top,
                  v369.DstRect.bottom,
                  v369.SubRectCnt);
              v122 = 0;
              if ( !SubRectCnt )
              {
LABEL_225:
                v332 = 1;
                goto LABEL_157;
              }
              v123 = (int)v343;
              while ( 1 )
              {
                v124 = 0;
                v125 = SubRectCnt - v122;
                if ( SubRectCnt - v122 > 0x10 )
                  break;
                v126 = SubRectCnt - v122;
                if ( v125 )
                  goto LABEL_220;
LABEL_221:
                if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x40) != 0 )
                  McTemplateK0ptqDR2DR2DR2DR2_EtwWriteTransfer(
                    (unsigned int)&DxgkControlGuid_Context,
                    (unsigned int)EventBlitRect,
                    0,
                    v123,
                    v125 <= 0x10,
                    v126,
                    (__int64)v388,
                    (__int64)v387,
                    (__int64)v386,
                    (__int64)v389);
                v122 += 16;
                if ( v122 >= SubRectCnt )
                {
                  v7 = v351;
                  goto LABEL_225;
                }
              }
              v126 = 16;
              do
              {
LABEL_220:
                v388[v124] = pDstSubRects[(unsigned int)v124 + v122].left;
                v387[v124] = pDstSubRects[(unsigned int)v124 + v122].right;
                v386[v124] = pDstSubRects[(unsigned int)v124 + v122].top;
                v389[v124] = pDstSubRects[(unsigned int)v124 + v122].bottom;
                v124 = (unsigned int)(v124 + 1);
              }
              while ( (unsigned int)v124 < v126 );
              goto LABEL_221;
            }
            WdLogSingleEntry2(4, v91, v7);
            v285 = a3;
            WdLogGlobalForLineNumber = 6218;
LABEL_565:
            COREDEVICEACCESS::AcquireSharedUncheck(v285, 0);
            DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v348);
            v24 = v92;
            goto LABEL_34;
          }
          goto LABEL_174;
        }
        DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v348);
        if ( v24 < 0 )
        {
LABEL_174:
          v62 = a3;
LABEL_175:
          DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v348);
          if ( v335 )
          {
            CWin32kLocks::Unlock(v337);
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
              WdLogGlobalForLineNumber = 6409;
              DxgkLogInternalTriageEvent(
                0,
                262146,
                -1,
                (unsigned int)L"!NT_SUCCESS(ntStatus) || !m_pPresent->BltViaGDI() || m_pPresent->IsBltEmpty() || pPresent-"
                               ">Flags.ColorFill",
                6409,
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
              WdLogGlobalForLineNumber = 6417;
              DxgkLogInternalTriageEvent(
                0,
                262146,
                -1,
                (unsigned int)L"ntStatus == STATUS_GRAPHICS_PRESENT_OCCLUDED || ntStatus == STATUS_GRAPHICS_PRESENT_DENIED",
                6417,
                0,
                0,
                0,
                0);
            }
            v24 = 0;
          }
          DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v348);
          if ( v24 < 0 )
            goto LABEL_31;
          v60 = v332;
          goto LABEL_638;
        }
        if ( (*(_DWORD *)(*((_QWORD *)v7 + 19) + 4LL) & 2) == 0 && *((_DWORD *)a2 + 23) )
        {
          WdLogSingleEntry0(2);
          WdLogGlobalForLineNumber = 5812;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Present via GDI cannot be broadcasted",
            5812,
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
          WdLogGlobalForLineNumber = 5818;
          DxgkLogInternalTriageEvent(
            0,
            262146,
            -1,
            (unsigned int)L"!pPresent->Flags.RedirectedBlt || pPresent->hDestination == NULL",
            5818,
            0,
            0,
            0,
            0);
        }
        v372 = 0;
        if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
          McTemplateK0q_EtwWriteTransfer(&DxgkControlGuid_Context, EventPerformanceWarning, 0, 0);
        v169 = *((_DWORD *)a2 + 22);
        if ( (v169 & 0x100) != 0 )
        {
          v100 = *(_OWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3248LL) + 128LL)
                           + 4024LL * *((unsigned int *)a2 + 4)
                           + 628);
          *(_QWORD *)v345 = &v372;
          v372 = v100;
        }
        else
        {
          *(_QWORD *)v345 = 0;
        }
        if ( (v169 & 1) != 0 )
        {
          v101 = 0;
          if ( (v169 & 0x80u) != 0 )
          {
            v288 = *((_DWORD *)a2 + 13);
            if ( v288 < 0 )
              v288 = 0;
            v369.SrcRect.top = v288;
            v289 = *((_DWORD *)a2 + 12);
            if ( v289 < 0 )
              v289 = 0;
            v369.SrcRect.left = v289;
            v290 = *((_DWORD *)a2 + 15);
            if ( (int)v336 < v290 )
              v290 = v336;
            v369.SrcRect.bottom = v290;
            v102 = *((_DWORD *)a2 + 14);
            if ( (int)v334 < v102 )
              v102 = v334;
          }
          else
          {
            v369.SrcRect.bottom = v336;
            v102 = v334;
            *(_QWORD *)&v369.SrcRect.left = 0;
          }
          v369.SrcRect.right = v102;
          v369.DstRect = v369.SrcRect;
          v369.Flags.Value = v369.Flags.Value & 0xFFFFF7FF | (*((_DWORD *)a2 + 22) >> 9) & 0x800;
          if ( !*((_DWORD *)a2 + 16) )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 5865;
            DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pPresent->SubRectCnt", 5865, 0, 0, 0, 0);
          }
          if ( !*((_QWORD *)a2 + 9) )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 5866;
            DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pPresent->pSrcSubRects", 5866, 0, 0, 0, 0);
          }
          v24 = DXGPRESENT::GrowRectList(*((DXGPRESENT **)v7 + 19), *((_DWORD *)a2 + 16));
          if ( v24 < 0 )
            goto LABEL_174;
          DdiSubRectList = DXGPRESENT::GetDdiSubRectList(*((DXGPRESENT **)v7 + 19), 0);
          v104 = 0;
          v105 = 0;
          v369.SubRectCnt = 0;
          v369.pDstSubRects = DdiSubRectList;
          if ( !*((_DWORD *)a2 + 16) )
            goto LABEL_174;
          while ( 1 )
          {
            if ( DXGPRESENT::IntersectRect(
                   &DdiSubRectList[v104],
                   (const struct tagRECT *)(*((_QWORD *)a2 + 9) + 16LL * v105),
                   &v369.SrcRect) )
            {
              v104 = ++v369.SubRectCnt;
            }
            else
            {
              v104 = v369.SubRectCnt;
            }
            if ( ++v105 >= *((_DWORD *)a2 + 16) )
              break;
            DdiSubRectList = (struct tagRECT *)v369.pDstSubRects;
          }
          if ( !(_DWORD)v104 )
            goto LABEL_174;
          if ( DXGPRESENT::PrepareStagingBuffer(
                 *((DXGPRESENT **)v7 + 19),
                 *((struct DXGDEVICE **)v7 + 2),
                 *((_DWORD *)a2 + 5),
                 v62,
                 &v333) < 0 )
            goto LABEL_266;
          if ( !*((_BYTE *)v7 + 434) )
          {
            v148 = v333;
            if ( !v333 )
            {
              WdLogSingleEntry0(1);
              WdLogGlobalForLineNumber = 5913;
              DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"hDestinationAllocation", 5913, 0, 0, 0, 0);
              v148 = v333;
            }
            if ( !bTracingEnabled )
              goto LABEL_271;
            v195 = (unsigned __int8)VIDMM_EXPORT::VidMmETWAllocationHandle(
                                      *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                                      *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 768LL),
                                      v148);
            v196 = (unsigned __int8)VIDMM_EXPORT::VidMmETWAllocationHandle(
                                      *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                                      *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 768LL),
                                      v339);
            v197 = v369.pDstSubRects;
            v198 = v369.SubRectCnt;
            *(_QWORD *)v342 = *((_QWORD *)v7 + 45);
            if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x20) != 0 )
              McTemplateK0ppxppttqddddddddq_EtwWriteTransfer(
                (unsigned int)&DxgkControlGuid_Context,
                (unsigned int)EventBlit,
                0,
                *((_QWORD *)a2 + 1),
                v342[0],
                0,
                v196,
                v195,
                1,
                0,
                *(_BYTE *)&v369.Flags.0,
                v369.SrcRect.left,
                v369.SrcRect.right,
                v369.SrcRect.top,
                v369.SrcRect.bottom,
                v369.DstRect.left,
                v369.DstRect.right,
                v369.DstRect.top,
                v369.DstRect.bottom,
                v369.SubRectCnt);
            v199 = 0;
            if ( !v198 )
            {
LABEL_343:
              v148 = v333;
              v101 = 0;
              v62 = a3;
              v332 = 1;
LABEL_271:
              v149 = DXGCONTEXT::SubmitPresent(
                       v7,
                       (const struct _D3DKMT_PRESENT *)a2,
                       *((struct DXGHWQUEUE ***)a2 + 188),
                       *((_DWORD *)a2 + 23),
                       v349,
                       v331,
                       v339,
                       v148,
                       &v369,
                       0,
                       *((struct VIDMM_DMA_BUFFER **)v7 + 45),
                       v344,
                       Format,
                       v62);
              *((_QWORD *)v7 + 45) = 0;
              goto LABEL_272;
            }
            v200 = v342[0];
            while ( 1 )
            {
              v201 = 0;
              v202 = v198 - v199;
              if ( v198 - v199 > 0x10 )
                break;
              v203 = v198 - v199;
              if ( v202 )
                goto LABEL_338;
LABEL_339:
              if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x40) != 0 )
                McTemplateK0ptqDR2DR2DR2DR2_EtwWriteTransfer(
                  (unsigned int)&DxgkControlGuid_Context,
                  (unsigned int)EventBlitRect,
                  0,
                  v200,
                  v202 <= 0x10,
                  v203,
                  (__int64)v384,
                  (__int64)v383,
                  (__int64)v382,
                  (__int64)v381);
              v199 += 16;
              if ( v199 >= v198 )
              {
                v7 = v351;
                goto LABEL_343;
              }
            }
            v203 = 16;
            do
            {
LABEL_338:
              v384[v201] = v197[(unsigned int)v201 + v199].left;
              v383[v201] = v197[(unsigned int)v201 + v199].right;
              v382[v201] = v197[(unsigned int)v201 + v199].top;
              v381[v201] = v197[(unsigned int)v201 + v199].bottom;
              v201 = (unsigned int)(v201 + 1);
            }
            while ( (unsigned int)v201 < v203 );
            goto LABEL_339;
          }
          v180 = DXGPROCESS::GetCurrent();
          v181 = v333;
          v182 = v180;
          DXGPUSHLOCK::AcquireShared((struct DXGPROCESS *)((char *)v180 + 248));
          v183 = (v181 >> 6) & 0xFFFFFF;
          if ( (unsigned int)v183 < *((_DWORD *)v182 + 74) )
          {
            v184 = *((_QWORD *)v182 + 35);
            v185 = *(_DWORD *)(v184 + 16 * v183 + 8);
            if ( ((v181 >> 25) & 0x60) == (v185 & 0x60) && (v185 & 0x2000) == 0 && (v185 & 0x1F) != 0 )
            {
              if ( (*(_BYTE *)(v184 + 16 * (((unsigned __int64)v181 >> 6) & 0xFFFFFF) + 8) & 0x1F) == 5 )
              {
                v186 = *(struct DXGALLOCATION **)(v184 + 16 * (((unsigned __int64)v181 >> 6) & 0xFFFFFF));
                goto LABEL_325;
              }
              WdLogSingleEntry0(2);
              WdLogGlobalForLineNumber = 318;
              DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
            }
          }
          v186 = 0;
LABEL_325:
          DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v350, v186);
          _InterlockedDecrement((volatile signed __int32 *)v182 + 66);
          ExReleasePushLockSharedEx((char *)v182 + 248, 0);
          KeLeaveCriticalRegion();
          v187 = v350;
          if ( !v350 )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 5898;
            DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"AllocRef.m_pAllocation != NULL", 5898, 0, 0, 0, 0);
            v187 = v350;
          }
          v188 = *(_DWORD *)(v187 + 20);
          v189 = (unsigned __int8 *)*((_QWORD *)a2 + 185);
          v190 = *((_DWORD *)a2 + 368);
          v191 = *(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL);
          v342[0] = *((_DWORD *)v331 + 5);
          v192 = (struct DXGHWQUEUE **)*((_QWORD *)a2 + 188);
          v193 = *(_QWORD *)(v191 + 16);
          if ( v192 )
            v194 = *v192;
          else
            v194 = 0;
          v291 = DXGPROCESS::GetCurrent();
          v149 = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendBlt(
                   (DXG_GUEST_VIRTUALGPU_VMBUS *)(v193 + 4792),
                   v291,
                   v7,
                   v194,
                   v342[0],
                   v188,
                   &v369.SrcRect,
                   &v369.DstRect,
                   v369.SubRectCnt,
                   v369.pDstSubRects,
                   v190,
                   v189);
          DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v350);
          v62 = a3;
          v101 = 0;
LABEL_272:
          if ( v149 < 0 )
          {
LABEL_266:
            WdLogSingleEntry2(3, -1071775738, v7);
            WdLogGlobalForLineNumber = 6095;
            v24 = -1071775738;
            goto LABEL_174;
          }
          v150 = (DXGDEVICE *)*((_QWORD *)v7 + 2);
          if ( (*((_DWORD *)a2 + 22) & 0x100) != 0
            && ADAPTER_DISPLAY::IsVidPnSourceOwner(
                 *(ADAPTER_DISPLAY **)(*((_QWORD *)v150 + 237) + 3248LL),
                 *((const struct DXGDEVICE **)v7 + 2),
                 *((_DWORD *)a2 + 4)) )
          {
            v101 = 1;
          }
          else if ( !DXGDEVICE::AllowLegacyPresent(v150, 0) )
          {
            v151 = 0;
            v101 = 0;
LABEL_276:
            DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v340);
            COREDEVICEACCESS::Release(v62);
            if ( !v151 && DXGPRESENT::CheckOcclusion(*((DXGPRESENT **)v7 + 19)) )
            {
              COREDEVICEACCESS::AcquireSharedUncheck(v62, 0);
              v24 = -1071775738;
              goto LABEL_174;
            }
            v152 = v337;
            CWin32kLocks::Unlock(v337);
            v153 = v340;
            DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v340);
            v24 = COREDEVICEACCESS::AcquireShared(v62, 0);
            if ( v24 >= 0 )
            {
              memset(&v364, 0, sizeof(v364));
              if ( *((_BYTE *)v7 + 434) )
              {
                memset(&v362, 0, sizeof(v362));
                v362.hAllocation = v333;
                v154 = (struct DXGDEVICE *)*((_QWORD *)v7 + 2);
                v155 = *(_QWORD *)(*((_QWORD *)v154 + 2) + 16LL);
                v156 = DXGPROCESS::GetCurrent();
                v157 = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendLock2(
                         (DXG_GUEST_VIRTUALGPU_VMBUS *)(v155 + 4792),
                         v156,
                         v154,
                         &v362,
                         0,
                         0,
                         0);
                v62 = a3;
                v24 = v157;
                v153 = v340;
                v364.pData = v362.pData;
              }
              else
              {
                v292 = v333;
                if ( !v333 )
                {
                  WdLogSingleEntry0(1);
                  WdLogGlobalForLineNumber = 5991;
                  DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"hDestinationAllocation", 5991, 0, 0, 0, 0);
                  v292 = v333;
                }
                v364.hAllocation = v292;
                v24 = DXGDEVICE::Lock(*((DXGDEVICE **)v7 + 2), &v364, v62, 0);
              }
              if ( v24 < 0 )
                goto LABEL_174;
              DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v153);
              COREDEVICEACCESS::Release(v62);
              if ( !v364.pData )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 6004;
                DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"LockData.pData", 6004, 0, 0, 0, 0);
              }
              if ( (*((_DWORD *)a2 + 22) & 0x10000) != 0 && *((_DWORD *)a2 + 6) )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 6005;
                DxgkLogInternalTriageEvent(
                  0,
                  262146,
                  -1,
                  (unsigned int)L"!pPresent->Flags.RedirectedBlt || pPresent->hDestination == NULL",
                  6005,
                  0,
                  0,
                  0,
                  0);
              }
              v158 = v343;
              v159 = (*((__int64 (__fastcall **)(_QWORD))v343 + 40))(0);
              v24 = CWin32kLocks::Lock(v152, *((HWND *)a2 + 1), 0, 0, v101 & (unsigned int)-(v159 != 0));
              if ( v24 >= 0 )
              {
                v164 = (unsigned int (__fastcall *)(const struct DXGK_PRESENT_PARAMS *, HDC, _QWORD, const RECT *, void *, int, unsigned int, unsigned int, int, int, int, void (__fastcall *)(const struct tagRECT *, const struct tagRECT *, struct tagRECT *, const struct tagRECT *, unsigned int, unsigned int), __int64 (__fastcall *)(struct tagRECT *, struct tagRECT *, const struct tagRECT *, const struct tagRECT *)))*((_QWORD *)v158 + 18);
                v165 = *(_DWORD *)(*((_QWORD *)v7 + 19) + 424LL);
                v166 = *((_DWORD *)a2 + 7);
                v167 = (*((_DWORD *)a2 + 22) & 0x200) != 0;
                v168 = CWin32kLocks::hDestDc(v337);
                LOBYTE(v327) = v167;
                LOBYTE(v325) = 0;
                if ( !v164(
                        a2,
                        v168,
                        *(_QWORD *)v345,
                        v369.pDstSubRects,
                        v364.pData,
                        v165,
                        v334,
                        v336,
                        v325,
                        v327,
                        v166,
                        DXGPRESENT::XformRect,
                        DXGPRESENT::ClipRects) )
                {
                  v24 = -1071775737;
                  WdLogSingleEntry2(4, -1071775737, v7);
                  WdLogGlobalForLineNumber = 6016;
                }
                v152 = v337;
                v62 = a3;
              }
              v160 = v340;
              DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v340);
              v92 = COREDEVICEACCESS::AcquireShared(v62, 0);
              if ( v92 >= 0 )
              {
                if ( *((_BYTE *)v7 + 434) )
                {
                  v357.hDevice = 0;
                  v357.hAllocation = v333;
                  v161 = (struct DXGDEVICE *)*((_QWORD *)v7 + 2);
                  v162 = *(_QWORD *)(*((_QWORD *)v161 + 2) + 16LL);
                  v163 = DXGPROCESS::GetCurrent();
                  DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendUnlock2(
                    (DXG_GUEST_VIRTUALGPU_VMBUS *)(v162 + 4792),
                    v163,
                    v161,
                    &v357,
                    0);
                  v62 = a3;
                }
                else
                {
                  v358.hDevice = 0;
                  v358.NumAllocations = 1;
                  v358.phAllocations = &v364.hAllocation;
                  DXGDEVICE::Unlock(*((DXGDEVICE **)v7 + 2), &v358, 0);
                }
                if ( v24 >= 0 && (*((_DWORD *)a2 + 22) & 0x10000) != 0 )
                {
                  *((_DWORD *)a2 + 90) = 3;
                  *((_QWORD *)a2 + 48) = *(_QWORD *)(*((_QWORD *)v7 + 19) + 440LL);
                  *((_DWORD *)a2 + 100) = 0;
                  *((_DWORD *)a2 + 91) = 48;
                  DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v348);
                  v24 = SubmitPresentHistoryToken(
                          (const struct _D3DKMT_PRESENTHISTORYTOKEN *)((char *)a2 + 360),
                          v62,
                          v160,
                          v152,
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
              v285 = v62;
              goto LABEL_565;
            }
            goto LABEL_476;
          }
          v151 = 1;
          goto LABEL_276;
        }
        if ( (v169 & 2) == 0 )
          goto LABEL_174;
        v293 = (DXGDEVICE *)*((_QWORD *)v7 + 2);
        if ( (v169 & 0x100) != 0
          && ADAPTER_DISPLAY::IsVidPnSourceOwner(
               *(ADAPTER_DISPLAY **)(*((_QWORD *)v293 + 237) + 3248LL),
               *((const struct DXGDEVICE **)v7 + 2),
               *((_DWORD *)a2 + 4)) )
        {
          v294 = 1;
        }
        else
        {
          v294 = 0;
          v295 = DXGDEVICE::AllowLegacyPresent(v293, 0);
          v296 = 0;
          if ( !v295 )
            goto LABEL_607;
        }
        v296 = 1;
LABEL_607:
        DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v340);
        COREDEVICEACCESS::Release(a3);
        if ( v296 || !DXGPRESENT::CheckOcclusion(*((DXGPRESENT **)v7 + 19)) )
        {
          if ( (*((_DWORD *)a2 + 22) & 0x10000) != 0 )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 6125;
            DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"!pPresent->Flags.RedirectedBlt", 6125, 0, 0, 0, 0);
          }
          CWin32kLocks::Unlock(v69);
          v297 = v343;
          v298 = (*((__int64 (__fastcall **)(_QWORD))v343 + 40))(0);
          v299 = CWin32kLocks::Lock(v69, *((HWND *)a2 + 1), 0, 0, v294 & (unsigned int)-(v298 != 0));
          v300 = (unsigned int (__fastcall *)(HDC, _QWORD, __int64, _QWORD, _DWORD))*((_QWORD *)v297 + 19);
          v24 = v299;
          LODWORD(v297) = *((_DWORD *)a2 + 7);
          v301 = *((_DWORD *)a2 + 16);
          v302 = *((_QWORD *)a2 + 9);
          v303 = CWin32kLocks::hDestDc(v337);
          if ( !v300(v303, *(_QWORD *)v345, v302, v301, (_DWORD)v297) )
          {
            v24 = -1071775737;
            WdLogSingleEntry2(4, -1071775737, v7);
            WdLogGlobalForLineNumber = 6135;
          }
        }
        else
        {
          v24 = -1071775738;
        }
        DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v340);
        v62 = a3;
        v304 = COREDEVICEACCESS::AcquireShared(a3, 0);
        v92 = v304;
        if ( v304 >= 0 )
          goto LABEL_175;
        WdLogSingleEntry2(4, v304, v7);
        WdLogGlobalForLineNumber = 6144;
        goto LABEL_600;
      }
      *(_QWORD *)(v74 + 56) = *(_QWORD *)v342;
      if ( (*((_DWORD *)a2 + 22) & 0x10000) == 0 )
      {
        *(_DWORD *)(*((_QWORD *)v7 + 19) + 8LL) = v66;
        DXGDEVICE::FlushScheduler(*((_QWORD *)v7 + 2), 2, 4294967293LL);
        v286 = 0;
        v287 = *(_DWORD *)(*((_QWORD *)v7 + 19) + 8LL);
        if ( v287 != (*((unsigned int (**)(void))v343 + 1))() )
        {
          *(_DWORD *)(*((_QWORD *)v7 + 19) + 8LL) = v66;
          ADAPTER_RENDER::FlushScheduler(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL), 3, 0xFFFFFFFFLL);
          v286 = 1;
        }
        DXGDEVICE::SynchronizePresentToPrimary(*((DXGDEVICE **)v7 + 2), v7, (struct DXGPRESENTMUTEX *)v348, v286);
      }
      v62 = a3;
LABEL_571:
      v69 = v337;
      goto LABEL_115;
    }
LABEL_476:
    COREDEVICEACCESS::AcquireSharedUncheck(v62, 0);
LABEL_477:
    v259 = (DXGPRESENTMUTEX *)v348;
    goto LABEL_478;
  }
  if ( !(_DWORD)v21 )
  {
    if ( (v22 & 0x10A7C3) != 0 )
    {
      v24 = -1073741811;
      WdLogSingleEntry3(3, v7, *((unsigned int *)a2 + 22), -1073741811);
      WdLogGlobalForLineNumber = 4725;
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
            if ( v33 < *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3248LL) + 96LL) )
            {
              v20 = v331;
LABEL_45:
              DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v355, v20);
              DXGALLOCATIONREFERENCE::MoveAssign(&v347, v355);
              DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v355);
              v346 = *((_DWORD *)a2 + 5);
              v34 = *(DXGADAPTER **)(*((_QWORD *)v7 + 2) + 1896LL);
              if ( !v34
                || !DXGADAPTER::IsDisplayAdapter(v34)
                || !ADAPTER_DISPLAY::IsCoreResourceSharedOwner(*(ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)v7 + 2)
                                                                                               + 1896LL)
                                                                                   + 3248LL)) )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 4776;
                DxgkLogInternalTriageEvent(
                  0,
                  262146,
                  -1,
                  (unsigned int)L"(GetDisplayAdapter(VidPnSourceId) == GetDisplayAdapter(0)) && (GetDisplayAdapter(VidPnSo"
                                 "urceId) != NULL) && GetDisplayAdapter(VidPnSourceId)->IsDisplayAdapter() && GetDisplayA"
                                 "dapter(VidPnSourceId)->GetDisplayCore()->IsCoreResourceSharedOwner()",
                  4776,
                  0,
                  0,
                  0,
                  0);
              }
              v35 = *((_QWORD *)v331 + 6);
              v36 = *(_DWORD *)(v35 + 4);
              if ( (v36 & 0x2000) != 0 && (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 40LL) + 408LL) & 4) == 0 )
              {
                v24 = -1073741811;
                WdLogSingleEntry5(2, -1073741811, v7, v331, v35, *((unsigned int *)a2 + 5));
                WdLogGlobalForLineNumber = 4784;
                v78 = L"0x%I64x 0x%I64x DirectFlip Presents are only supported from the DWM process 0x%I64x 0x%I64x 0x%I64x";
                v324 = *((unsigned int *)a2 + 5);
                v322 = *((_QWORD *)v331 + 6);
                v320 = (__int64)v331;
                v318 = (__int64)v7;
                v316 = -1073741811;
                goto LABEL_120;
              }
              v37 = *((_DWORD *)a2 + 22);
              if ( (v37 & 0x40000) == 0 && (v37 & 0x20000) == 0 )
                goto LABEL_51;
              if ( (v37 & 0x20000) != 0 && (v37 & 0x40000) != 0 )
              {
                WdLogSingleEntry0(2);
                v246 = 4795;
                v242 = L"FlipStereoTemporaryMono and FlipStereo cannot be set together. STATUS_INVALID_PARAMETER";
              }
              else if ( (v36 & 0x1000) != 0 )
              {
                v247 = *((_DWORD *)ADAPTER_DISPLAY::GetDisplayModeInfo(
                                     *(ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3248LL),
                                     v33)
                       + 10);
                if ( (v247 & 0x10) == 0 )
                {
                  WdLogSingleEntry0(3);
                  WdLogGlobalForLineNumber = 4808;
                  goto LABEL_452;
                }
                v248 = *((_DWORD *)a2 + 22);
                if ( (v247 & 0x20) == 0 && (v248 & 0x40000) != 0 )
                {
                  WdLogSingleEntry0(3);
                  WdLogGlobalForLineNumber = 4814;
                  goto LABEL_452;
                }
                if ( (v248 & 0xC0000) != 0xC0000 )
                {
LABEL_51:
                  IsFullWDDMDevice = DXGDEVICE::IsFullWDDMDevice(*((DXGDEVICE **)v7 + 2), v33);
                  v39 = v344;
                  if ( !IsFullWDDMDevice )
                  {
                    v26 = a3;
                    goto LABEL_53;
                  }
                  v131 = *(_DWORD *)v344 ^ (*((_DWORD *)a2 + 22) ^ *(_DWORD *)v344) & 4;
                  *(_DWORD *)v344 = v131;
                  v132 = v131 ^ (*((_DWORD *)a2 + 22) ^ v131) & 8;
                  *(_DWORD *)v39 = v132;
                  v133 = v132 ^ ((unsigned __int8)v132 ^ (unsigned __int8)(*((_DWORD *)a2 + 22) >> 1)) & 0x10;
                  *(_DWORD *)v39 = v133;
                  v134 = v133 ^ (v133 ^ (4 * *((_DWORD *)a2 + 22))) & 0x80000;
                  *(_DWORD *)v39 = v134;
                  v135 = v134 ^ (v134 ^ (4 * *((_DWORD *)a2 + 22))) & 0x100000;
                  *(_DWORD *)v39 = v135;
                  v136 = v135 ^ (v135 ^ (4 * *((_DWORD *)a2 + 22))) & 0x200000;
                  *(_DWORD *)v39 = v136;
                  if ( (*((_DWORD *)a2 + 22) & 0x8000000) != 0 )
                    v137 = *((_DWORD *)a2 + 363);
                  else
                    v137 = 0;
                  *((_DWORD *)v39 + 36) = v137;
                  *((_DWORD *)v39 + 38) = 1;
                  *(_DWORD *)v39 = v136 ^ (*((_DWORD *)a2 + 22) ^ v136) & 0x20000000;
                  v138 = *((_DWORD *)a2 + 22) >> 9;
                  v139 = *((_DWORD *)a2 + 22) & 4 | v369.Flags.Value & 0xFFFFFFFB;
                  v140 = v139
                       ^ ((unsigned __int16)v139
                        ^ (unsigned __int16)v138)
                       & 0x100
                       ^ ((unsigned __int16)v138
                        ^ (unsigned __int16)(v139 ^ (v139 ^ v138) & 0x100))
                       & 0x200;
                  v369.Flags.Value = v140 ^ (v138 ^ v140) & 0x400;
                  v141 = *((_QWORD *)a2 + 180);
                  if ( v141
                    && !*(_DWORD *)(v141 + 16)
                    && (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 40LL) + 408LL) & 4) != 0 )
                  {
                    v369.SubRectCnt = *(_DWORD *)v141;
                    v369.pDstSubRects = *(const RECT **)(v141 + 8);
                  }
                  v142 = (D3DDDI_FLIPINTERVAL_TYPE *)((char *)a2 + 84);
                  DeviceFlipMode = VIDSCH_EXPORT::VidSchGetDeviceFlipMode(
                                     *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 736LL),
                                     *(_QWORD *)(*((_QWORD *)v7 + 2) + 800LL),
                                     v33,
                                     (char *)a2 + 84);
                  *((_DWORD *)v39 + 30) = DeviceFlipMode;
                  if ( !DeviceFlipMode )
                  {
                    v24 = -1073741811;
                    WdLogSingleEntry3(3, v7, *(int *)v142, -1073741811);
                    WdLogGlobalForLineNumber = 4867;
                    goto LABEL_34;
                  }
                  if ( ((DeviceFlipMode - 1) & 0xFFFFFFFD) != 0 )
                  {
                    v369.FlipInterval = *v142;
                    if ( DeviceFlipMode == 2 )
                    {
LABEL_255:
                      *((D3DDDI_FLIPINTERVAL_TYPE *)v39 + 31) = *v142;
                      *((_DWORD *)v39 + 29) = v33;
                      DisplayedPrimary = DXGDEVICE::GetDisplayedPrimary(*((DXGDEVICE **)v7 + 2), v33);
                      if ( DisplayedPrimary )
                      {
                        v145 = *((_QWORD *)DisplayedPrimary + 6);
                        if ( _bittest((const signed __int32 *)(*((_QWORD *)v331 + 6) + 4LL), 0xDu) )
                        {
                          if ( !_bittest((const signed __int32 *)(v145 + 4), 0xDu) )
                            goto LABEL_258;
                        }
                        else if ( _bittest((const signed __int32 *)(v145 + 4), 0xDu) )
                        {
LABEL_258:
                          *(_DWORD *)v39 |= 0x400000u;
                          goto LABEL_259;
                        }
                      }
                      *(_DWORD *)v39 &= ~0x400000u;
LABEL_259:
                      v146 = *((_DWORD *)v39 + 30);
                      if ( !v146 || (v147 = *((_QWORD *)v7 + 2), v146 == *(_DWORD *)(v147 + 4LL * v33 + 1832)) )
                      {
                        v26 = a3;
LABEL_262:
                        v18 = v334;
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
                              v250 = DXGDEVICE::IsFullWDDMDevice(*((DXGDEVICE **)v7 + 2), v33);
                              v251 = (DXGDEVICE *)*((_QWORD *)v7 + 2);
                              v252 = v33;
                              if ( v250 )
                              {
                                DXGDEVICE::ClearDisplayedAllMultiPlaneOverlaysUnsafe(v251, v33);
                                DXGDEVICE::SetDisplayedPrimary(
                                  *((DXGDEVICE **)v7 + 2),
                                  v33,
                                  v331,
                                  *((_DWORD *)v39 + 34),
                                  1u);
                                v253 = *((_DWORD *)v39 + 30);
LABEL_498:
                                *(_DWORD *)(*((_QWORD *)v7 + 2) + 4LL * v33 + 1832) = v253;
                                goto LABEL_500;
                              }
LABEL_499:
                              DXGDEVICE::SetDisplayedPrimary(v251, v252, v331, 0, 1u);
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
                                           v336),
                                   v28 >= 0) )
                        {
                          if ( !ADAPTER_DISPLAY::GetCddPrimaryAllocation(
                                  *(ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3248LL),
                                  v33,
                                  0) )
                          {
                            if ( (*(_DWORD *)(*((_QWORD *)v7 + 2) + 4LL * v33 + 1240) & 0x200) == 0
                              && (*((_DWORD *)a2 + 22) & 0x10000000) == 0 )
                            {
                              WdLogSingleEntry5(3, -1071775739, v7, *((unsigned int *)a2 + 5), v331, v33);
                              WdLogGlobalForLineNumber = 5066;
                              goto LABEL_452;
                            }
LABEL_57:
                            if ( !DXGDEVICE::IsFullWDDMDevice(*((DXGDEVICE **)v7 + 2), v33) )
                            {
                              v40 = *((_QWORD *)v7 + 2);
                              if ( !*(_QWORD *)(v40 + 1896) )
                              {
                                WdLogSingleEntry2(1, v40, -1073741822);
                                v326 = 0;
                                v242 = L"DxgkPresent is called for flip on a render only device 0x%I64x, returning 0x%I64x.";
                                v323 = 0;
                                v245 = 262146;
                                v321 = 0;
                                WdLogGlobalForLineNumber = 5377;
                                v319 = -1073741822;
                                v317 = (struct _DXGKARG_PRESENT *)*((_QWORD *)v7 + 2);
                                goto LABEL_442;
                              }
                              *(_QWORD *)&v370.right = 0;
                              *(_QWORD *)&v370.left = 0;
                              v41 = *((_DWORD *)a2 + 22);
                              if ( (v41 & 0x10000000) != 0 )
                              {
                                v370.right = *((_DWORD *)a2 + 379);
                                v42 = *((_DWORD *)a2 + 380);
                                goto LABEL_61;
                              }
                              v272 = v338;
                              if ( (v41 & 4) != 0 )
                                v272 = v331;
                              v273 = *(_DWORD *)(*((_QWORD *)v272 + 6) + 4LL);
                              if ( (v273 & 0x10) != 0 )
                              {
                                WdLogSingleEntry3(4, -1071775482, v7, v272);
                                WdLogGlobalForLineNumber = 5297;
                                v24 = -1071775482;
                                goto LABEL_34;
                              }
                              v274 = *(_OWORD *)ADAPTER_DISPLAY::GetDisplayModeInfo(
                                                  *(ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL)
                                                                      + 3248LL),
                                                  (v273 >> 6) & 0xF);
                              v359.Flags.Value = 1;
                              memset(&v359, 0, 40);
                              v359.Rotation = -1;
                              v275 = *((_QWORD *)v272 + 6);
                              *(_OWORD *)v366 = v274;
                              v359.hAllocation = *(HANDLE *)(v275 + 16);
                              v276 = ADAPTER_RENDER::DdiDescribeAllocation(
                                       *(ADAPTER_RENDER **)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 16LL)
                                                          + 3256LL),
                                       &v359);
                              if ( v276 >= 0 )
                              {
                                v277 = v359.Width;
                                if ( v359.Width != v366[0] || (v42 = v359.Height, v359.Height != v366[1]) )
                                {
                                  WdLogSingleEntry3(4, -1071775482, v7, v272);
                                  WdLogGlobalForLineNumber = 5328;
                                  goto LABEL_452;
                                }
                                if ( *((_BYTE *)v7 + 434) )
                                  goto LABEL_527;
                                v278 = RemoveAlphaChannel(v366[2]);
                                if ( RemoveAlphaChannel(v359.Format) == v278 )
                                {
                                  v42 = v359.Height;
                                  v277 = v359.Width;
LABEL_527:
                                  v370.right = v277;
LABEL_61:
                                  v370.bottom = v42;
                                  v24 = ADAPTER_DISPLAY::PresentDisplayOnly(
                                          *(ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3248LL),
                                          v7,
                                          v33,
                                          (const struct _D3DKMT_PRESENT *)a2,
                                          &v369,
                                          v26,
                                          &v370);
                                  if ( v24 >= 0 )
                                  {
                                    if ( (*((_DWORD *)a2 + 22) & 4) == 0 )
                                    {
LABEL_63:
                                      v23 = 2;
                                      goto LABEL_30;
                                    }
                                    DXGDEVICE::ClearDisplayedAllMultiPlaneOverlaysUnsafe(*((DXGDEVICE **)v7 + 2), v33);
                                    DXGDEVICE::SetDisplayedPrimary(*((DXGDEVICE **)v7 + 2), v33, v331, 0, 1u);
LABEL_516:
                                    UpdatePostComposition(
                                      v33,
                                      0,
                                      0,
                                      0,
                                      *(struct ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3248LL));
                                    goto LABEL_63;
                                  }
LABEL_31:
                                  if ( !ADAPTER_RENDER::IsCoreResourceSharedOwner(*(ADAPTER_RENDER **)(*((_QWORD *)v7 + 2) + 16LL))
                                    && v24 != -1073741130 )
                                  {
                                    WdLogSingleEntry0(1);
                                    WdLogGlobalForLineNumber = 6533;
                                    DxgkLogInternalTriageEvent(
                                      0,
                                      262146,
                                      -1,
                                      (unsigned int)L"GetRenderCore()->IsCoreResourceSharedOwner() || ntStatus == STATUS_DEVICE_REMOVED",
                                      6533,
                                      0,
                                      0,
                                      0,
                                      0);
                                  }
                                  if ( *((_QWORD *)v7 + 45) )
                                  {
                                    WdLogSingleEntry0(1);
                                    WdLogGlobalForLineNumber = 6534;
                                    DxgkLogInternalTriageEvent(
                                      0,
                                      262146,
                                      -1,
                                      (unsigned int)L"m_pPresentDmaBuffer == NULL",
                                      6534,
                                      0,
                                      0,
                                      0,
                                      0);
                                  }
                                  goto LABEL_34;
                                }
                                WdLogSingleEntry3(4, -1071775482, v7, v272);
                                WdLogGlobalForLineNumber = 5342;
LABEL_452:
                                v24 = -1071775739;
                                goto LABEL_34;
                              }
                              v244 = (struct _DXGKARG_PRESENT *)v276;
                              WdLogSingleEntry5(
                                2,
                                v276,
                                v7,
                                *((unsigned int *)v272 + 4),
                                v272,
                                (*(_DWORD *)(*((_QWORD *)v272 + 6) + 4LL) >> 6) & 0xF);
                              WdLogGlobalForLineNumber = 5319;
                              v242 = L"ret = 0x%I64x Device 0x%I64x: DdiDescribeAllocation failed 0x%I64x 0x%I64x 0x%I64x";
                              v326 = (*(_DWORD *)(*((_QWORD *)v272 + 6) + 4LL) >> 6) & 0xF;
                              v323 = (__int64)v272;
                              v321 = *((unsigned int *)v272 + 4);
                              v319 = (__int64)v7;
                              v317 = v244;
LABEL_438:
                              v245 = 0x40000;
LABEL_442:
                              DxgkLogInternalTriageEvent(
                                0,
                                v245,
                                -1,
                                (_DWORD)v242,
                                (__int64)v317,
                                v319,
                                v321,
                                v323,
                                v326);
                              goto LABEL_416;
                            }
                            v129 = DXGCONTEXT::WaitForQueuedPresentLimit(
                                     v7,
                                     v33,
                                     (*((_DWORD *)a2 + 22) & 0x10) == 0,
                                     v26);
                            v24 = v129;
                            if ( v129 < 0 )
                            {
                              WdLogSingleEntry2(4, v129, v7);
                              WdLogGlobalForLineNumber = 5081;
                              goto LABEL_34;
                            }
                            v130 = v344;
                            if ( ((*((_DWORD *)v344 + 30) - 3) & 0xFFFFFFFD) != 0 )
                            {
                              v24 = DXGCONTEXT::AcquireDmaBuffer(v7, (struct VIDMM_DMA_BUFFER **)v7 + 45, v26, 0);
                              if ( v24 < 0 )
                                goto LABEL_31;
                              if ( !*((_QWORD *)v7 + 45) )
                              {
                                WdLogSingleEntry0(1);
                                WdLogGlobalForLineNumber = 5099;
                                DxgkLogInternalTriageEvent(
                                  0,
                                  262146,
                                  -1,
                                  (unsigned int)L"m_pPresentDmaBuffer",
                                  5099,
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
                                if ( v331 )
                                {
                                  v265 = *((_QWORD *)v331 + 6);
                                  if ( v265 )
                                  {
                                    if ( (*(_DWORD *)(v265 + 4) & 0x2000) != 0 )
                                    {
                                      if ( !DXGDEVICE::IsDirectFlipAllocationRequestedPinned(
                                              *((DXGDEVICE **)v7 + 2),
                                              v331) )
                                      {
                                        WdLogSingleEntry3(4, -1071775739, v7, v331);
                                        WdLogGlobalForLineNumber = 5151;
                                        goto LABEL_509;
                                      }
                                      if ( !VIDMM_EXPORT::VidMmIsAllocationPinned(
                                              *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                                              *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 768LL),
                                              *((struct VIDMM_MULTI_ALLOC **)v331 + 3)) )
                                      {
                                        v266 = VIDMM_EXPORT::VidMmPinAllocation(
                                                 *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                                                 *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL)
                                                                         + 768LL),
                                                 *((struct VIDMM_MULTI_ALLOC **)v331 + 3),
                                                 0,
                                                 0);
                                        if ( v266 < 0 )
                                        {
                                          WdLogSingleEntry3(4, v331, *((_QWORD *)v331 + 6), v266);
                                          WdLogGlobalForLineNumber = 5176;
LABEL_509:
                                          v267 = (struct VIDMM_DMA_BUFFER *)*((_QWORD *)v7 + 45);
                                          if ( v267 )
                                          {
                                            VIDMM_EXPORT::VidMmReleaseDmaBuffer(
                                              *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                                              v267);
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
                                v268 = ADAPTER_DISPLAY::GetCurrentOrientation(
                                         *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3248LL),
                                         v33,
                                         1);
                                v369.Flags.Value = (v268 != 1 ? 0x80 : 0) | v369.Flags.Value & 0xFFFFFF7F;
                              }
                              if ( !bTracingEnabled )
                              {
LABEL_241:
                                v24 = DXGCONTEXT::SubmitPresent(
                                        v7,
                                        (const struct _D3DKMT_PRESENT *)a2,
                                        *((struct DXGHWQUEUE ***)a2 + 188),
                                        *((_DWORD *)a2 + 23),
                                        v349,
                                        v331,
                                        v339,
                                        v333,
                                        &v369,
                                        *((struct _D3DKMT_PRESENT_RGNS **)a2 + 180),
                                        *((struct VIDMM_DMA_BUFFER **)v7 + 45),
                                        v130,
                                        Format,
                                        v26);
                                if ( v24 >= 0
                                  && *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL)
                                                                       + 3248LL)
                                                           + 128LL)
                                               + 4024LL * v33
                                               + 1072) == -1 )
                                {
                                  WdLogSingleEntry0(1);
                                  WdLogGlobalForLineNumber = 5245;
                                  DxgkLogInternalTriageEvent(
                                    0,
                                    262146,
                                    -1,
                                    (unsigned int)L"!NT_SUCCESS(ntStatus) || (GetDisplayAdapter(VidPnSourceId)->GetDisplay"
                                                   "Core()->MapVidPnSourceToVidPnTarget(VidPnSourceId) != D3DDDI_ID_UNINITIALIZED)",
                                    5245,
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
                                  v331,
                                  *((_DWORD *)v130 + 34),
                                  1u);
                                *(_DWORD *)(*((_QWORD *)v7 + 2) + 4LL * v33 + 1832) = *((_DWORD *)v130 + 30);
                                goto LABEL_516;
                              }
                              v269 = *(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL);
                              v270 = *(struct VIDMM_GLOBAL **)(v269 + 768);
                              v271 = *(VIDMM_EXPORT **)(v269 + 760);
                              if ( (*((_DWORD *)a2 + 22) & 4) != 0 )
                              {
                                v170 = (unsigned __int8)VIDMM_EXPORT::VidMmETWAllocationHandle(v271, v270, v339);
                                if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x80u) != 0LL )
                                  McTemplateK0pqpqtt_EtwWriteTransfer(
                                    (unsigned int)&DxgkControlGuid_Context,
                                    (unsigned int)EventFlip,
                                    0,
                                    *((_QWORD *)v7 + 45),
                                    v33,
                                    v170,
                                    v369.FlipInterval,
                                    (*(_BYTE *)&v369.Flags.0 & 8) != 0,
                                    *((_QWORD *)v7 + 45) == 0);
                                goto LABEL_241;
                              }
                              v171 = (unsigned __int8)VIDMM_EXPORT::VidMmETWAllocationHandle(v271, v270, v333);
                              v172 = (CWin32kLocks *)VIDMM_EXPORT::VidMmETWAllocationHandle(
                                                       *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                                                       *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL)
                                                                               + 768LL),
                                                       v339);
                              v173 = v369.pDstSubRects;
                              v174 = v369.SubRectCnt;
                              v337 = v172;
                              v343 = (const struct _DXGKWIN32KENG_INTERFACE *)*((_QWORD *)v7 + 45);
                              if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x20) != 0 )
                                McTemplateK0ppxppttqddddddddq_EtwWriteTransfer(
                                  (unsigned int)&DxgkControlGuid_Context,
                                  (unsigned int)EventBlit,
                                  0,
                                  *((_QWORD *)a2 + 1),
                                  (char)v343,
                                  0,
                                  (char)v337,
                                  v171,
                                  1,
                                  0,
                                  *(_BYTE *)&v369.Flags.0,
                                  v369.SrcRect.left,
                                  v369.SrcRect.right,
                                  v369.SrcRect.top,
                                  v369.SrcRect.bottom,
                                  v369.DstRect.left,
                                  v369.DstRect.right,
                                  v369.DstRect.top,
                                  v369.DstRect.bottom,
                                  v369.SubRectCnt);
                              v175 = 0;
                              if ( !v174 )
                              {
LABEL_315:
                                v130 = v344;
                                v26 = a3;
                                goto LABEL_241;
                              }
                              v176 = (int)v343;
                              while ( 1 )
                              {
                                v177 = 0;
                                v178 = v174 - v175;
                                if ( v174 - v175 > 0x10 )
                                  break;
                                v179 = v174 - v175;
                                if ( v178 )
                                  goto LABEL_310;
LABEL_311:
                                if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x40) != 0 )
                                  McTemplateK0ptqDR2DR2DR2DR2_EtwWriteTransfer(
                                    (unsigned int)&DxgkControlGuid_Context,
                                    (unsigned int)EventBlitRect,
                                    0,
                                    v176,
                                    v178 <= 0x10,
                                    v179,
                                    (__int64)v380,
                                    (__int64)v379,
                                    (__int64)v385,
                                    (__int64)v378);
                                v175 += 16;
                                if ( v175 >= v174 )
                                {
                                  v7 = v351;
                                  goto LABEL_315;
                                }
                              }
                              v179 = 16;
                              do
                              {
LABEL_310:
                                v380[v177] = v173[(unsigned int)v177 + v175].left;
                                v379[v177] = v173[(unsigned int)v177 + v175].right;
                                v385[v177] = v173[(unsigned int)v177 + v175].top;
                                v378[v177] = v173[(unsigned int)v177 + v175].bottom;
                                v177 = (unsigned int)(v177 + 1);
                              }
                              while ( (unsigned int)v177 < v179 );
                              goto LABEL_311;
                            }
                            v263 = (struct VIDMM_DMA_BUFFER *)*((_QWORD *)v7 + 45);
                            if ( v263 )
                            {
                              VIDMM_EXPORT::VidMmReleaseDmaBuffer(
                                *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                                v263);
                              *((_QWORD *)v7 + 45) = 0;
                            }
                            if ( v24 != -1071774920 )
                              goto LABEL_31;
                            if ( (*((_DWORD *)a2 + 22) & 4) != 0 )
                            {
                              v264 = DXGDEVICE::IsFullWDDMDevice(*((DXGDEVICE **)v7 + 2), v33);
                              v251 = (DXGDEVICE *)*((_QWORD *)v7 + 2);
                              v252 = v33;
                              if ( v264 )
                              {
                                DXGDEVICE::ClearDisplayedAllMultiPlaneOverlaysUnsafe(v251, v33);
                                DXGDEVICE::SetDisplayedPrimary(
                                  *((DXGDEVICE **)v7 + 2),
                                  v33,
                                  v331,
                                  *((_DWORD *)v130 + 34),
                                  1u);
                                v253 = *((_DWORD *)v130 + 30);
                                goto LABEL_498;
                              }
                              goto LABEL_499;
                            }
                            goto LABEL_500;
                          }
                          v254 = v343;
                          v255 = *(_DWORD *)(*((_QWORD *)v7 + 19) + 8LL);
                          v256 = (*((__int64 (**)(void))v343 + 1))();
                          v257 = *((_DWORD *)a2 + 22) & 4;
                          if ( v255 != v256 )
                          {
                            if ( !v257 )
                            {
                              DXGDEVICE::FlushScheduler(*((_QWORD *)v7 + 2), 2, 4294967293LL);
                              DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v340);
                              COREDEVICEACCESS::Release(v26);
                              DXGPRESENTMUTEX::DXGPRESENTMUTEX(
                                (DXGPRESENTMUTEX *)v363,
                                *(struct ADAPTER_RENDER *const *)(*((_QWORD *)v7 + 2) + 16LL));
                              DXGPRESENTMUTEX::Acquire((DXGPRESENTMUTEX *)v363);
                              DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v340);
                              v258 = COREDEVICEACCESS::AcquireShared(v26, 0);
                              v24 = v258;
                              if ( v258 < 0 )
                              {
                                WdLogSingleEntry2(4, v258, v7);
                                WdLogGlobalForLineNumber = 5016;
                                COREDEVICEACCESS::AcquireSharedUncheck(v26, 0);
                                v259 = (DXGPRESENTMUTEX *)v363;
                                goto LABEL_478;
                              }
                              DXGDEVICE::SynchronizePresentToPrimary(
                                *((DXGDEVICE **)v7 + 2),
                                v7,
                                (struct DXGPRESENTMUTEX *)v363,
                                1u);
                              DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v363);
                            }
                            v260 = *((_QWORD *)v7 + 19);
                            *(_DWORD *)(v260 + 8) = (*((__int64 (**)(void))v254 + 1))();
                            CddInterface = ADAPTER_DISPLAY::GetCddInterface(
                                             *(ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3248LL),
                                             v33);
                            if ( CddInterface )
                              (*((void (__fastcall **)(_QWORD, _QWORD))CddInterface + 1))(*(_QWORD *)CddInterface, 0);
                            goto LABEL_57;
                          }
                          if ( v257 )
                            goto LABEL_57;
                          COREDEVICEACCESS::Release(v26);
                          DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v340);
                          DXGPRESENTMUTEX::DXGPRESENTMUTEX(
                            (DXGPRESENTMUTEX *)v361,
                            *(struct ADAPTER_RENDER *const *)(*((_QWORD *)v7 + 2) + 16LL));
                          DXGPRESENTMUTEX::Acquire((DXGPRESENTMUTEX *)v361);
                          DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v340);
                          v262 = COREDEVICEACCESS::AcquireShared(v26, 0);
                          v24 = v262;
                          if ( v262 >= 0 )
                          {
                            DXGDEVICE::SynchronizePresentToPrimary(
                              *((DXGDEVICE **)v7 + 2),
                              v7,
                              (struct DXGPRESENTMUTEX *)v361,
                              0);
                            DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v361);
                            goto LABEL_57;
                          }
                          WdLogSingleEntry2(4, v262, v7);
                          WdLogGlobalForLineNumber = 5049;
                          COREDEVICEACCESS::AcquireSharedUncheck(v26, 0);
                          v259 = (DXGPRESENTMUTEX *)v361;
LABEL_478:
                          DXGPRESENTMUTEX::Release(v259);
                          goto LABEL_34;
                        }
LABEL_408:
                        v24 = v28;
                        goto LABEL_34;
                      }
                      WdLogSingleEntry1(4, v147);
                      v26 = a3;
                      WdLogGlobalForLineNumber = 4923;
                      COREDEVICEACCESS::Release(a3);
                      DXGDEVICE::FlushScheduler(*((_QWORD *)v7 + 2), 3, 4294967293LL);
                      v249 = COREDEVICEACCESS::AcquireShared(a3, 0);
                      v24 = v249;
                      if ( v249 < 0 )
                      {
                        WdLogSingleEntry1(4, v249);
                        WdLogGlobalForLineNumber = 4931;
                        COREDEVICEACCESS::AcquireSharedUncheck(a3, 0);
                        goto LABEL_34;
                      }
LABEL_431:
                      v39 = v344;
                      goto LABEL_262;
                    }
                  }
                  else
                  {
                    v369.FlipInterval = D3DDDI_FLIPINTERVAL_IMMEDIATE;
                  }
                  v369.Flags.Value |= 8u;
                  goto LABEL_255;
                }
                WdLogSingleEntry0(2);
                v246 = 4820;
                v242 = L"FlipStereoTemporaryMono cannot be used with FlipStereoPreferRight. STATUS_INVALID_PARAMETER";
              }
              else
              {
                WdLogSingleEntry0(2);
                v246 = 4801;
                v242 = L"FlipStereoTemporaryMono and FlipStereo can only be used with stereo primary allocations. STATUS_I"
                        "NVALID_PARAMETER";
              }
              v326 = 0;
              v323 = 0;
              v245 = 0x40000;
              v321 = 0;
              v319 = 0;
              v317 = (struct _DXGKARG_PRESENT *)v246;
              WdLogGlobalForLineNumber = v246;
              goto LABEL_442;
            }
          }
        }
        WdLogSingleEntry1(2, *((unsigned int *)a2 + 4));
        WdLogGlobalForLineNumber = 4760;
        v242 = L"An invalid VidPn source ID was supplied to an indirect present (%I64d)";
        v243 = *((unsigned int *)a2 + 4);
      }
      else
      {
        WdLogSingleEntry0(2);
        v243 = 4735;
        v242 = L"Expecting indirect display presents to be a shared surface";
        WdLogGlobalForLineNumber = 4735;
      }
      v326 = 0;
      v323 = 0;
      v321 = 0;
      v319 = 0;
      v317 = (struct _DXGKARG_PRESENT *)v243;
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
    WdLogGlobalForLineNumber = 4745;
    v78 = L"0x%I64x 0x%I64x Source of Flip must be primary 0x%I64x 0x%I64x 0x%I64x";
    v324 = *((unsigned int *)a2 + 5);
    v322 = *((_QWORD *)v331 + 6);
    v320 = (__int64)v331;
    v318 = (__int64)v7;
    v316 = -1073741811;
LABEL_120:
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v78, v316, v318, v320, v322, v324);
    goto LABEL_34;
  }
LABEL_355:
  v206 = *((_QWORD *)a2 + 9);
  if ( !v206
    || (v207 = *((unsigned int *)a2 + 16), !(_DWORD)v207)
    || (v22 & 1) == 0 && (v22 & 2) == 0
    || (v22 & 0x100E803C) != 0 )
  {
    v24 = -1073741811;
    WdLogSingleEntry5(3, v7, v206, *((unsigned int *)a2 + 16), (unsigned int)v22, -1073741811);
    WdLogGlobalForLineNumber = 4423;
    goto LABEL_34;
  }
  if ( (v22 & 2) != 0 )
  {
    if ( (v22 & 1) != 0 || (v22 & 0x100680) != 0 )
    {
      v24 = -1073741811;
      WdLogSingleEntry5(3, v7, v206, *((unsigned int *)a2 + 16), (unsigned int)v22, -1073741811);
      WdLogGlobalForLineNumber = 4438;
      goto LABEL_34;
    }
  }
  else
  {
    if ( !v18 || !Height || (v22 & 0x82) != 0x80 )
    {
      v24 = -1073741811;
      WdLogSingleEntry5(3, v7, v206, *((unsigned int *)a2 + 16), (unsigned int)v22, -1073741811);
      WdLogGlobalForLineNumber = 4452;
      goto LABEL_34;
    }
    if ( (v22 & 0x600) == 0x600 )
    {
      v24 = -1073741811;
      WdLogSingleEntry5(3, -1073741811, v7, v206, v207, (unsigned int)v22);
      WdLogGlobalForLineNumber = 4461;
      goto LABEL_34;
    }
  }
  v208 = *((_QWORD *)v338 + 6);
  v209 = *(_DWORD *)(v208 + 4);
  if ( (v209 & 3) == 0 )
  {
    v24 = -1073741811;
    WdLogSingleEntry5(2, -1073741811, v7, v338, v208, v21);
    WdLogGlobalForLineNumber = 4472;
    v78 = L"0x%I64x 0x%I64x destination must be primary 0x%I64x 0x%I64x 0x%I64x";
    v324 = *((unsigned int *)a2 + 6);
    v322 = *((_QWORD *)v338 + 6);
    v320 = (__int64)v338;
    v318 = (__int64)v7;
    v316 = -1073741811;
    goto LABEL_120;
  }
  v33 = (v209 >> 6) & 0xF;
  v210 = *(DXGADAPTER **)(*((_QWORD *)v7 + 2) + 1896LL);
  if ( !v210
    || !DXGADAPTER::IsDisplayAdapter(v210)
    || !ADAPTER_DISPLAY::IsCoreResourceSharedOwner(*(ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL)
                                                                       + 3248LL)) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4484;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"(GetDisplayAdapter(VidPnSourceId) == GetDisplayAdapter(0)) && (GetDisplayAdapter(VidPnSourceId) != N"
                     "ULL) && GetDisplayAdapter(VidPnSourceId)->IsDisplayAdapter() && GetDisplayAdapter(VidPnSourceId)->G"
                     "etDisplayCore()->IsCoreResourceSharedOwner()",
      4484,
      0,
      0,
      0,
      0);
  }
  *((_DWORD *)v344 + 29) = v33;
  DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v354, v338);
  DXGALLOCATIONREFERENCE::MoveAssign(&v347, v354);
  DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v354);
  v211 = *((_DWORD *)a2 + 6);
  v212 = *((_DWORD *)a2 + 22);
  v346 = v211;
  if ( (v212 & 1) != 0 )
  {
    if ( v338 == v331 )
    {
      v24 = -1073741811;
      WdLogSingleEntry5(2, -1073741811, v7, v331, *((unsigned int *)a2 + 5), v211);
      WdLogGlobalForLineNumber = 4496;
      v78 = L"0x%I64x 0x%I64x Source and destination must be different 0x%I64x 0x%I64x 0x%I64x";
      v324 = *((unsigned int *)a2 + 6);
      v322 = *((unsigned int *)a2 + 5);
      v320 = (__int64)v331;
      v318 = (__int64)v7;
      v316 = -1073741811;
      goto LABEL_120;
    }
    v213 = *(unsigned int *)(*((_QWORD *)v331 + 6) + 4LL);
    if ( (v213 & 3) != 0 && (((unsigned int)v213 >> 6) & 0xF) != v33 )
    {
      v24 = -1073741811;
      WdLogSingleEntry5(2, -1073741811, v7, v331, (v213 >> 6) & 0xF, v33);
      v78 = L"0x%I64x 0x%I64x primary source has different VidPnSourceId 0x%I64x 0x%I64x != 0x%I64x";
      v324 = v33;
      WdLogGlobalForLineNumber = 4509;
      v322 = (*(_DWORD *)(*((_QWORD *)v331 + 6) + 4LL) >> 6) & 0xF;
      v320 = (__int64)v331;
      v318 = (__int64)v7;
      v316 = -1073741811;
      goto LABEL_120;
    }
    v214 = *((_DWORD *)a2 + 12);
    v215 = *((int *)a2 + 14);
    if ( (int)v215 <= v214
      || (v216 = *((_DWORD *)a2 + 13), v217 = *((_DWORD *)a2 + 15), v217 <= v216)
      || v214 >= v18
      || v216 >= (int)v336
      || (int)v215 <= 0
      || v217 <= 0 )
    {
      v24 = -1073741811;
      WdLogSingleEntry5(2, -1073741811, *((int *)a2 + 12), *((int *)a2 + 13), v215, *((int *)a2 + 15));
      WdLogGlobalForLineNumber = 4529;
      v78 = L"0x%I64x Invalid Source Rect [0x%I64x 0x%I64x 0x%I64x 0x%I64x]";
      v324 = *((int *)a2 + 15);
      v322 = *((int *)a2 + 14);
      v320 = *((int *)a2 + 13);
      v318 = *((int *)a2 + 12);
      v316 = -1073741811;
      goto LABEL_120;
    }
    for ( m = 0; ; ++m )
    {
      v219 = *((_DWORD *)a2 + 16);
      if ( m >= v219 )
        break;
      Source1 = 0;
      v220 = 16LL * m;
      v221 = m;
      if ( !DXGPRESENT::IntersectRect(
              &Source1,
              (const struct tagRECT *)(v220 + *((_QWORD *)a2 + 9)),
              (const struct tagRECT *)a2 + 3)
        || RtlCompareMemory(&Source1, (const void *)(v220 + *((_QWORD *)a2 + 9)), 0x10u) != 16 )
      {
        v24 = -1073741811;
        WdLogSingleEntry5(2, -1073741811, *((int *)a2 + 12), *((int *)a2 + 13), *((int *)a2 + 14), *((int *)a2 + 15));
        WdLogGlobalForLineNumber = 4547;
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
          *(int *)(*((_QWORD *)a2 + 9) + v220),
          *(int *)(*((_QWORD *)a2 + 9) + v220 + 4),
          *(int *)(*((_QWORD *)a2 + 9) + v220 + 8),
          *(int *)(*((_QWORD *)a2 + 9) + v220 + 12));
        WdLogGlobalForLineNumber = 4555;
        goto LABEL_394;
      }
    }
    v222 = *((unsigned int *)a2 + 22);
    if ( (v222 & 0x40) != 0 )
    {
      v223 = *((int *)a2 + 8);
      v224 = *((_DWORD *)a2 + 10);
      if ( v224 <= (int)v223
        || (v225 = *((_DWORD *)a2 + 9), v226 = *((_DWORD *)a2 + 11), v226 <= v225)
        || (int)v223 >= (int)v342[0]
        || v225 >= (int)v345[0]
        || v224 <= 0
        || v226 <= 0 )
      {
        v24 = -1073741811;
        WdLogSingleEntry5(3, -1073741811, v223, *((int *)a2 + 9), *((int *)a2 + 10), *((int *)a2 + 11));
        WdLogGlobalForLineNumber = 4577;
        goto LABEL_34;
      }
      if ( *((_DWORD *)a2 + 14) - *((_DWORD *)a2 + 12) != v224 - (_DWORD)v223
        || *((_DWORD *)a2 + 15) - *((_DWORD *)a2 + 13) != v226 - v225 )
      {
        v24 = -1073741811;
        WdLogSingleEntry5(2, -1073741811, v7, v222, v338, v33);
        v78 = L"0x%I64x 0x%I64x specified destination RECT has different size from source RECT 0x%I64x 0x%I64x 0x%I64x";
        v324 = v33;
        v322 = (__int64)v338;
        WdLogGlobalForLineNumber = 4589;
        v320 = *((unsigned int *)a2 + 22);
        v318 = (__int64)v7;
        v316 = -1073741811;
        goto LABEL_120;
      }
      v28 = DXGPRESENT::GrowRectList(*((DXGPRESENT **)v7 + 19), v219);
      if ( v28 < 0 )
        goto LABEL_408;
      v227 = 0;
      v228 = DXGPRESENT::GetDdiSubRectList(*((DXGPRESENT **)v7 + 19), 0);
      v229 = *((_DWORD *)a2 + 8) - *((_DWORD *)a2 + 12);
      v230 = *((_DWORD *)a2 + 9) - *((_DWORD *)a2 + 13);
      v219 = *((_DWORD *)a2 + 16);
      if ( v219 )
      {
        do
        {
          v231 = v227++;
          v231 *= 2;
          *(&v228->left + 2 * v231) = v229 + *(_DWORD *)(*((_QWORD *)a2 + 9) + 8 * v231);
          *(&v228->right + 2 * v231) = v229 + *(_DWORD *)(*((_QWORD *)a2 + 9) + 8 * v231 + 8);
          *(&v228->top + 2 * v231) = v230 + *(_DWORD *)(*((_QWORD *)a2 + 9) + 8 * v231 + 4);
          *(&v228->bottom + 2 * v231) = v230 + *(_DWORD *)(*((_QWORD *)a2 + 9) + 8 * v231 + 12);
          v219 = *((_DWORD *)a2 + 16);
        }
        while ( v227 < v219 );
      }
      v232 = (RECT)*((_OWORD *)a2 + 2);
      v369.pDstSubRects = v228;
      v369.DstRect = v232;
    }
    else
    {
      if ( v342[0] != v334 || v345[0] != v336 )
      {
        WdLogSingleEntry5(3, v7, v342[0], v345[0], v334, v336);
        WdLogGlobalForLineNumber = 4625;
LABEL_416:
        v24 = -1073741811;
        goto LABEL_34;
      }
      v369.DstRect = (RECT)*((_OWORD *)a2 + 3);
      v369.pDstSubRects = (const RECT *)*((_QWORD *)a2 + 9);
    }
    v369.SrcRect = (RECT)*((_OWORD *)a2 + 3);
    Value = v369.Flags.Value & 0xFFFFF7FF | (*((_DWORD *)a2 + 22) >> 9) & 0x800;
    v369.Flags.Value = Value;
    goto LABEL_430;
  }
  v234 = 0;
  *(_QWORD *)&v369.DstRect.left = 0;
  v369.DstRect.right = Width;
  v369.DstRect.bottom = v345[0];
  if ( (v212 & 0x40) == 0 )
    goto LABEL_424;
  v235 = *((int *)a2 + 10);
  v236 = *((int *)a2 + 8);
  if ( (int)v235 <= (int)v236
    || (v237 = *((_DWORD *)a2 + 11), v237 <= *((_DWORD *)a2 + 9))
    || (int)v235 <= 0
    || v237 <= 0 )
  {
    v24 = -1073741811;
    WdLogSingleEntry5(3, -1073741811, v236, *((int *)a2 + 9), v235, *((int *)a2 + 11));
    WdLogGlobalForLineNumber = 4658;
    goto LABEL_34;
  }
  if ( !DXGPRESENT::IntersectRect(&v369.DstRect, (const struct tagRECT *)a2 + 2, &v369.DstRect) )
    goto LABEL_500;
  while ( 1 )
  {
LABEL_424:
    v219 = *((_DWORD *)a2 + 16);
    if ( v234 >= v219 )
    {
      Value = v369.Flags.Value;
      v369.SrcRect = v369.DstRect;
      v369.pDstSubRects = (const RECT *)*((_QWORD *)a2 + 9);
LABEL_430:
      v26 = a3;
      v369.SubRectCnt = v219;
      v238 = *((_DWORD *)a2 + 22) & 1 | Value & 0xFFFFFFFE;
      v239 = *((_DWORD *)a2 + 22) >> 5;
      v240 = *((_DWORD *)a2 + 22) >> 9;
      v241 = v238
           ^ ((unsigned __int8)v238
            ^ (unsigned __int8)*((_DWORD *)a2 + 22))
           & 2
           ^ ((unsigned __int8)v239
            ^ (unsigned __int8)(v238 ^ (v238 ^ *((_DWORD *)a2 + 22)) & 2))
           & 0x10
           ^ ((unsigned __int8)v239
            ^ (unsigned __int8)(v238
                              ^ (v238
                               ^ *((_DWORD *)a2 + 22))
                              & 2
                              ^ (v239
                               ^ v238
                               ^ (v238
                                ^ *((_DWORD *)a2 + 22))
                               & 2)
                              & 0x10))
           & 0x20;
      LOBYTE(v238) = v238
                   ^ (v238
                    ^ *((_DWORD *)a2 + 22))
                   & 2
                   ^ (v239
                    ^ v238
                    ^ (v238
                     ^ *((_DWORD *)a2 + 22))
                    & 2)
                   & 0x10
                   ^ (v239
                    ^ v238
                    ^ (v238
                     ^ *((_DWORD *)a2 + 22))
                    & 2
                    ^ (v239
                     ^ v238
                     ^ (v238
                      ^ *((_DWORD *)a2 + 22))
                     & 2)
                    & 0x10)
                   & 0x20;
      v369.Color = *((_DWORD *)a2 + 7);
      v369.Flags.Value = v241
                       ^ ((unsigned __int8)v239
                        ^ (unsigned __int8)v238)
                       & 0x40
                       ^ (v241
                        ^ ((unsigned __int8)v239
                         ^ (unsigned __int8)v238)
                        & 0x40
                        ^ v240)
                       & 0x800;
      goto LABEL_431;
    }
    v371 = 0;
    v220 = 16LL * v234;
    v221 = v234;
    if ( !DXGPRESENT::IntersectRect(&v371, (const struct tagRECT *)(v220 + *((_QWORD *)a2 + 9)), &v369.DstRect)
      || RtlCompareMemory(&v371, (const void *)(v220 + *((_QWORD *)a2 + 9)), 0x10u) != 16 )
    {
      break;
    }
    ++v234;
  }
  v24 = -1073741811;
  WdLogSingleEntry5(2, -1073741811, *((int *)a2 + 8), *((int *)a2 + 9), *((int *)a2 + 10), *((int *)a2 + 11));
  WdLogGlobalForLineNumber = 4682;
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
    v234,
    *(int *)(*((_QWORD *)a2 + 9) + v220),
    *(int *)(*((_QWORD *)a2 + 9) + v220 + 4),
    *(int *)(*((_QWORD *)a2 + 9) + v220 + 8),
    *(int *)(*((_QWORD *)a2 + 9) + v220 + 12));
  WdLogGlobalForLineNumber = 4690;
LABEL_394:
  DxgkLogInternalTriageEvent(
    0,
    0x40000,
    -1,
    (unsigned int)L"SubRect 0x%I64x is invalid 0x%I64x 0x%I64x 0x%I64x 0x%I64x",
    v221,
    *(int *)(*((_QWORD *)a2 + 9) + v220),
    *(int *)(*((_QWORD *)a2 + 9) + v220 + 4),
    *(int *)(*((_QWORD *)a2 + 9) + v220 + 8),
    *(int *)(*((_QWORD *)a2 + 9) + v220 + 12));
LABEL_34:
  DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v347);
  DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v338);
  DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v331);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x14039aac0  push    rbp
0x14039aac2  push    rbx
0x14039aac3  push    rsi
0x14039aac4  push    rdi
0x14039aac5  push    r12
0x14039aac7  push    r13
0x14039aac9  push    r14
0x14039aacb  push    r15
0x14039aacd  lea     rbp, [rsp-978h]
0x14039aad5  sub     rsp, 0A98h
0x14039aadc  mov     rax, cs:__security_cookie
0x14039aae3  xor     rax, rsp
0x14039aae6  mov     [rbp+9B0h+var_50], rax
0x14039aaed  mov     rax, [rbp+9B0h+arg_20]
0x14039aaf4  mov     r15, rcx
0x14039aaf7  mov     rbx, [rbp+9B0h+arg_30]
0x14039aafe  mov     r13, rdx
0x14039ab01  mov     [rbp+9B0h+var_988], rcx
0x14039ab05  mov     rcx, [rcx+10h]
0x14039ab09  mov     [rbp+9B0h+var_A08], rax
0x14039ab0d  mov     rax, [rbp+9B0h+arg_28]
0x14039ab14  mov     [rbp+9B0h+var_9F0], r9
0x14039ab18  mov     rcx, [rcx+10h]; this
0x14039ab1c  mov     [rbp+9B0h+var_A30], r8
0x14039ab20  mov     [rbp+9B0h+var_9D0], rbx
0x14039ab24  mov     [rbp+9B0h+var_998], rax
0x14039ab28  call    ?IsCoreResourceSharedOwner@ADAPTER_RENDER@@QEBAEXZ; ADAPTER_RENDER::IsCoreResourceSharedOwner(void)
0x14039ab2d  or      r12d, 0FFFFFFFFh
0x14039ab31  xor     esi, esi
0x14039ab33  mov     edi, 1
0x14039ab38  mov     r14d, 40002h
0x14039ab3e  test    al, al
0x14039ab40  jz      loc_14039D201
0x14039ab46  cmp     [r15+168h], rsi
0x14039ab4d  jnz     loc_14039D24C
0x14039ab53  test    dword ptr [r13+58h], 4000h
0x14039ab5b  jnz     loc_14039D297
0x14039ab61  mov     rcx, [r15+10h]
0x14039ab65  mov     rcx, [rcx+28h]; this
0x14039ab69  call    ?GetWin32kInterface@DXGPROCESS@@QEBAQEBU_DXGKWIN32KENG_INTERFACE@@XZ; DXGPROCESS::GetWin32kInterface(void)
0x14039ab6e  mov     ecx, [r13+58h]
0x14039ab72  mov     [rbp+9B0h+var_9D8], rax
0x14039ab76  mov     eax, 12000h
0x14039ab7b  and     ecx, eax
0x14039ab7d  cmp     ecx, eax
0x14039ab7f  jz      loc_14039D2C4
0x14039ab85  xor     edx, edx; Val
0x14039ab87  lea     rcx, [rbp+9B0h+var_590]; void *
0x14039ab8e  mov     r8d, 0A8h; Size
0x14039ab94  call    memset
0x14039ab99  mov     eax, [r13+14h]
0x14039ab9d  mov     [rbp+9B0h+var_9F8], eax
0x14039aba0  mov     eax, [r13+18h]
0x14039aba4  mov     [rbp+9B0h+var_A1C], eax
0x14039aba7  or      dword ptr [rbx], 10020h
0x14039abad  test    dword ptr [r13+58h], 10000h
0x14039abb5  mov     ecx, [rbx]
0x14039abb7  jz      loc_14039D2F1
0x14039abbd  bts     ecx, 8
0x14039abc1  mov     [rbx], ecx
0x14039abc3  mov     eax, [r13+58h]
0x14039abc7  shl     eax, 5
0x14039abca  xor     eax, ecx
0x14039abcc  and     eax, 20000h
0x14039abd1  xor     eax, ecx
0x14039abd3  mov     [rbx], eax
0x14039abd5  test    dword ptr [r13+58h], 1000h
0x14039abdd  jnz     loc_14039B68D
0x14039abe3  mov     rdx, [r15+10h]
0x14039abe7  mov     rax, [rdx+10h]
0x14039abeb  mov     rcx, [rax+10h]
0x14039abef  cmp     [rdx+768h], rcx
0x14039abf6  jnz     loc_14039D2F8
0x14039abfc  xor     edx, edx; struct DXGALLOCATION *
0x14039abfe  lea     rcx, [rbp+9B0h+var_A28]; this
0x14039ac02  call    ??0DXGALLOCATIONREFERENCE@@QEAA@PEAVDXGALLOCATION@@@Z; DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE(DXGALLOCATION *)
0x14039ac07  xor     edx, edx; struct DXGALLOCATION *
0x14039ac09  lea     rcx, [rbp+9B0h+var_A00]; this
0x14039ac0d  call    ??0DXGALLOCATIONREFERENCE@@QEAA@PEAVDXGALLOCATION@@@Z; DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE(DXGALLOCATION *)
0x14039ac12  xor     edx, edx; struct DXGALLOCATION *
0x14039ac14  lea     rcx, [rbp+9B0h+var_9B8]; this
0x14039ac18  call    ??0DXGALLOCATIONREFERENCE@@QEAA@PEAVDXGALLOCATION@@@Z; DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE(DXGALLOCATION *)
0x14039ac1d  mov     ebx, [r13+18h]
0x14039ac21  mov     r14d, 2
0x14039ac27  test    ebx, ebx
0x14039ac29  jnz     loc_14039B213
0x14039ac2f  mov     r14d, esi
0x14039ac32  mov     [rbp+9B0h+var_9C8], esi
0x14039ac35  test    dword ptr [r13+58h], 8002h
0x14039ac3d  mov     [rbp+9B0h+var_9E0], r14d
0x14039ac41  jz      loc_14039B0EB
0x14039ac47  mov     ebx, esi
0x14039ac49  mov     [rbp+9B0h+var_9E8], esi
0x14039ac4c  mov     edi, esi
0x14039ac4e  mov     rdx, [rbp+9B0h+var_A28]
0x14039ac52  mov     r10d, [r13+18h]
0x14039ac56  mov     [rbp+9B0h+var_A18], ebx
0x14039ac59  mov     [rbp+9B0h+var_A10], edi
0x14039ac5c  test    r10d, r10d
0x14039ac5f  jnz     loc_14039D401
0x14039ac65  mov     r9d, [r13+58h]
0x14039ac69  test    r9b, 4
0x14039ac6d  jnz     loc_14039AE17
0x14039ac73  mov     eax, r9d
0x14039ac76  mov     [rbp+9B0h+var_9C0], esi
0x14039ac79  shr     eax, 1
0x14039ac7b  mov     r12d, 1
0x14039ac81  test    r12b, r9b
0x14039ac84  jnz     loc_14039B081
0x14039ac8a  lea     esi, [r12+1]
0x14039ac8f  test    sil, r9b
0x14039ac92  jnz     loc_14039EB4B
0x14039ac98  bt      r9d, 0Fh
0x14039ac9d  jb      short loc_14039ACDC
0x14039ac9f  mov     ecx, [r13+40h]
0x14039aca3  mov     r12, 0FFFFFFFFC000000Dh
0x14039acaa  mov     [rsp+0AD0h+var_AA8], r9
0x14039acaf  mov     r8, r15
0x14039acb2  mov     r9, [r13+48h]
0x14039acb6  mov     rdx, r12
0x14039acb9  mov     [rsp+0AD0h+var_AB0], rcx
0x14039acbe  lea     ecx, [rsi+1]
0x14039acc1  call    cs:__imp_WdLogSingleEntry5
0x14039acc8  nop     dword ptr [rax+rax+00h]
0x14039accd  mov     cs:WdLogGlobalForLineNumber, 1955h
0x14039acd7  jmp     loc_14039ADCF
0x14039acdc  test    r9b, 6
0x14039ace0  jnz     loc_14039EB1B
0x14039ace6  test    r9d, 27E8h
0x14039aced  jnz     loc_14039EB1B
0x14039acf3  lea     rbx, [r13+168h]
0x14039acfa  mov     eax, [rbx]
0x14039acfc  cmp     eax, esi
0x14039acfe  jnz     loc_14039EB0D
0x14039ad04  cmp     dword ptr [r13+494h], 10h
0x14039ad0c  ja      loc_14039EB1B
0x14039ad12  mov     rax, [r15+10h]
0x14039ad16  mov     r14, [rbp+9B0h+var_A30]
0x14039ad1a  mov     rdi, [rbp+9B0h+var_9F0]
0x14039ad1e  mov     rdx, r14; struct COREDEVICEACCESS *
0x14039ad21  shr     r9d, 4
0x14039ad25  mov     rcx, rdi; this
0x14039ad28  mov     r8, [rax+10h]
0x14039ad2c  and     r9b, r12b
0x14039ad2f  mov     rax, [r13+160h]
0x14039ad36  mov     byte ptr [rsp+0AD0h+var_AA8], r9b; bool
0x14039ad3b  mov     r9, rbx; struct _D3DKMT_PRESENTHISTORYTOKEN *
0x14039ad3e  mov     [rsp+0AD0h+var_AB0], rax; void *
0x14039ad43  mov     r8, [r8+10h]; struct DXGADAPTER *
0x14039ad47  call    ?SubmitPresentHistoryTokenPreparation@@YAJPEAVDXGADAPTERSTOPRESETLOCKSHARED@@PEAVCOREDEVICEACCESS@@PEAVDXGADAPTER@@PEAU_D3DKMT_PRESENTHISTORYTOKEN@@PEAX_N@Z; SubmitPresentHistoryTokenPreparation(DXGADAPTERSTOPRESETLOCKSHARED *,COREDEVICEACCESS *,DXGADAPTER *,_D3DKMT_PRESENTHISTORYTOKEN *,void *,bool)
0x14039ad4c  xor     r12d, r12d
0x14039ad4f  test    eax, eax
0x14039ad51  js      loc_14039DAE2
0x14039ad57  mov     r9, r14; struct COREDEVICEACCESS *
0x14039ad5a  lea     rcx, [rbp+9B0h+var_7E0]; this
0x14039ad61  mov     r8, rdi; struct DXGADAPTERSTOPRESETLOCKSHARED *
0x14039ad64  mov     rdx, rbx; struct _D3DKMT_PRESENTHISTORYTOKEN *
0x14039ad67  call    ??0TOKEN_BINDING_GUARD@@QEAA@PEAU_D3DKMT_PRESENTHISTORYTOKEN@@PEAVDXGADAPTERSTOPRESETLOCKSHARED@@PEAVCOREDEVICEACCESS@@@Z; TOKEN_BINDING_GUARD::TOKEN_BINDING_GUARD(_D3DKMT_PRESENTHISTORYTOKEN *,DXGADAPTERSTOPRESETLOCKSHARED *,COREDEVICEACCESS *)
0x14039ad6c  mov     rax, [rbp+9B0h+var_9D0]
0x14039ad70  mov     r8, rdi; struct DXGADAPTERSTOPRESETLOCKSHARED *
0x14039ad73  mov     r9, [rbp+9B0h+var_A08]; struct CWin32kLocks *
0x14039ad77  mov     rdx, r14; struct COREDEVICEACCESS *
0x14039ad7a  mov     [rsp+0AD0h+var_A80], r12; char *
0x14039ad7f  mov     rcx, rbx; struct _D3DKMT_PRESENTHISTORYTOKEN *
0x14039ad82  mov     [rsp+0AD0h+var_A88], r12; struct _PRESENT_REDIRECTED_PARAMS *
0x14039ad87  mov     [rsp+0AD0h+var_A90], r15; struct DXGCONTEXT *
0x14039ad8c  mov     qword ptr [rsp+0AD0h+var_A98], rax; struct VIDSCH_SUBMIT_DATA_BASE *
0x14039ad91  mov     [rsp+0AD0h+var_AA0], r13; struct DXGK_PRESENT_PARAMS *
0x14039ad96  mov     [rsp+0AD0h+var_AA8], r12; union _LARGE_INTEGER *
0x14039ad9b  mov     dword ptr [rsp+0AD0h+var_AB0], 1; int
0x14039ada3  call    ?SubmitPresentHistoryToken@@YAJPEBU_D3DKMT_PRESENTHISTORYTOKEN@@PEAVCOREDEVICEACCESS@@PEAVDXGADAPTERSTOPRESETLOCKSHARED@@PEAVCWin32kLocks@@HPEAT_LARGE_INTEGER@@PEAUDXGK_PRESENT_PARAMS@@PEAUVIDSCH_SUBMIT_DATA_BASE@@PEAVDXGCONTEXT@@PEAU_PRESENT_REDIRECTED_PARAMS@@PEBD@Z; SubmitPresentHistoryToken(_D3DKMT_PRESENTHISTORYTOKEN const *,COREDEVICEACCESS *,DXGADAPTERSTOPRESETLOCKSHARED *,CWin32kLocks *,int,_LARGE_INTEGER *,DXGK_PRESENT_PARAMS *,VIDSCH_SUBMIT_DATA_BASE *,DXGCONTEXT *,_PRESENT_REDIRECTED_PARAMS *,char const *)
0x14039ada8  lea     rcx, [rbp+9B0h+var_7E0]; this
0x14039adaf  mov     [rbp+9B0h+var_7E0], eax
0x14039adb5  mov     r12d, eax
0x14039adb8  call    ??1TOKEN_BINDING_GUARD@@QEAA@XZ; TOKEN_BINDING_GUARD::~TOKEN_BINDING_GUARD(void)
0x14039adbd  test    r12d, r12d
0x14039adc0  js      short loc_14039ADCF
0x14039adc2  mov     rbx, [rbp+9B0h+var_9B8]
0x14039adc6  test    rbx, rbx
0x14039adc9  jnz     loc_14039BED9
0x14039adcf  xor     esi, esi
0x14039add1  mov     rcx, [r15+10h]
0x14039add5  mov     rcx, [rcx+10h]; this
0x14039add9  call    ?IsCoreResourceSharedOwner@ADAPTER_RENDER@@QEBAEXZ; ADAPTER_RENDER::IsCoreResourceSharedOwner(void)
0x14039adde  test    al, al
0x14039ade0  jz      loc_14039F87C
0x14039ade6  cmp     [r15+168h], rsi
0x14039aded  jnz     loc_14039F8DA
0x14039adf3  lea     rcx, [rbp+9B0h+var_9B8]; this
0x14039adf7  call    ??1DXGALLOCATIONREFERENCE@@QEAA@XZ; DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE(void)
0x14039adfc  lea     rcx, [rbp+9B0h+var_A00]; this
0x14039ae00  call    ??1DXGALLOCATIONREFERENCE@@QEAA@XZ; DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE(void)
0x14039ae05  lea     rcx, [rbp+9B0h+var_A28]; this
0x14039ae09  call    ??1DXGALLOCATIONREFERENCE@@QEAA@XZ; DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE(void)
0x14039ae0e  mov     eax, r12d
0x14039ae11  jmp     loc_14039F924
0x14039ae17  test    r10d, r10d
0x14039ae1a  jnz     loc_14039D410
0x14039ae20  test    r9d, 10A7C3h
0x14039ae27  jnz     loc_14039EADD
0x14039ae2d  bt      r9d, 1Ch
0x14039ae32  jnb     loc_14039B705
0x14039ae38  mov     rax, [rdx+28h]
0x14039ae3c  test    rax, rax
0x14039ae3f  jz      loc_14039DF01
0x14039ae45  cmp     [rax+38h], rsi
0x14039ae49  jz      loc_14039DF01
0x14039ae4f  mov     rax, [r15+10h]
0x14039ae53  mov     rcx, [rax+768h]; this
0x14039ae5a  test    rcx, rcx
0x14039ae5d  jz      loc_14039DED5
0x14039ae63  call    ?IsDisplayAdapter@DXGADAPTER@@QEBAEXZ; DXGADAPTER::IsDisplayAdapter(void)
0x14039ae68  test    al, al
0x14039ae6a  jz      loc_14039DED5
0x14039ae70  mov     rax, [r15+10h]
0x14039ae74  mov     edi, [r13+10h]
0x14039ae78  mov     rcx, [rax+768h]
0x14039ae7f  mov     rax, [rcx+0CB0h]
0x14039ae86  cmp     edi, [rax+60h]
0x14039ae89  jnb     loc_14039DED5
0x14039ae8f  mov     rdx, [rbp+9B0h+var_A28]; struct DXGALLOCATION *
0x14039ae93  lea     rcx, [rbp+9B0h+var_968]; this
0x14039ae97  call    ??0DXGALLOCATIONREFERENCE@@QEAA@PEAVDXGALLOCATION@@@Z; DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE(DXGALLOCATION *)
0x14039ae9c  lea     rdx, [rbp+9B0h+var_968]
0x14039aea0  lea     rcx, [rbp+9B0h+var_9B8]
0x14039aea4  call    ?MoveAssign@DXGALLOCATIONREFERENCE@@QEAAAEAV1@$$QEAV1@@Z; DXGALLOCATIONREFERENCE::MoveAssign(DXGALLOCATIONREFERENCE &&)
0x14039aea9  lea     rcx, [rbp+9B0h+var_968]; this
0x14039aead  call    ??1DXGALLOCATIONREFERENCE@@QEAA@XZ; DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE(void)
0x14039aeb2  mov     eax, [r13+14h]
0x14039aeb6  mov     [rbp+9B0h+var_9C0], eax
0x14039aeb9  mov     rax, [r15+10h]
0x14039aebd  mov     rcx, [rax+768h]; this
0x14039aec4  test    rcx, rcx
0x14039aec7  jz      loc_14039E059
0x14039aecd  call    ?IsDisplayAdapter@DXGADAPTER@@QEBAEXZ; DXGADAPTER::IsDisplayAdapter(void)
0x14039aed2  test    al, al
0x14039aed4  jz      loc_14039E059
0x14039aeda  mov     rax, [r15+10h]
0x14039aede  mov     rcx, [rax+768h]
0x14039aee5  mov     rcx, [rcx+0CB0h]; this
0x14039aeec  call    ?IsCoreResourceSharedOwner@ADAPTER_DISPLAY@@QEBAEXZ; ADAPTER_DISPLAY::IsCoreResourceSharedOwner(void)
0x14039aef1  test    al, al
0x14039aef3  jz      loc_14039E059
0x14039aef9  or      r14d, 0FFFFFFFFh
0x14039aefd  mov     r9, [rbp+9B0h+var_A28]
0x14039af01  mov     rdx, [r9+30h]
0x14039af05  mov     r8d, [rdx+4]
0x14039af09  bt      r8d, 0Dh
0x14039af0e  jb      loc_14039E0AD
0x14039af14  mov     edx, [r13+58h]
0x14039af18  mov     r12d, 40000h
0x14039af1e  mov     eax, edx
0x14039af20  shr     eax, 11h
0x14039af23  test    r12d, edx
0x14039af26  jnz     loc_14039E130
0x14039af2c  test    al, 1
0x14039af2e  jnz     loc_14039E130
0x14039af34  mov     rcx, [r15+10h]; this
0x14039af38  mov     edx, edi; unsigned int
0x14039af3a  call    ?IsFullWDDMDevice@DXGDEVICE@@QEBA?BEI@Z; DXGDEVICE::IsFullWDDMDevice(uint)
0x14039af3f  mov     r12, [rbp+9B0h+var_9D0]
0x14039af43  test    al, al
0x14039af45  jnz     loc_14039C539
0x14039af4b  mov     r14, [rbp+9B0h+var_A30]
0x14039af4f  mov     edx, [r13+58h]
0x14039af53  xor     r9d, r9d; int
0x14039af56  mov     r8d, edx
0x14039af59  mov     dword ptr [rsp+0AD0h+var_AB0], edi; unsigned int
0x14039af5d  shr     r8d, 1Ch
0x14039af61  mov     rcx, r15; this
0x14039af64  shr     edx, 2
0x14039af67  and     r8d, 1; int
0x14039af6b  and     edx, 1; int
0x14039af6e  call    ?CheckDevicePresentSettings@DXGCONTEXT@@QEAAJHHHI@Z; DXGCONTEXT::CheckDevicePresentSettings(int,int,int,uint)
0x14039af73  test    eax, eax
0x14039af75  js      loc_14039E31A
0x14039af7b  mov     eax, [r13+58h]
0x14039af7f  test    al, 4
0x14039af81  jnz     loc_14039E375
0x14039af87  mov     rax, [r15+10h]
0x14039af8b  xor     r8d, r8d; unsigned __int8
0x14039af8e  mov     edx, edi; unsigned int
0x14039af90  mov     rcx, [rax+768h]
0x14039af97  mov     rcx, [rcx+0CB0h]; this
0x14039af9e  call    ?GetCddPrimaryAllocation@ADAPTER_DISPLAY@@QEBAPEAVDXGADAPTERALLOCATION@@IE@Z; ADAPTER_DISPLAY::GetCddPrimaryAllocation(uint,uchar)
0x14039afa3  test    rax, rax
0x14039afa6  jnz     loc_14039E3A1
0x14039afac  mov     rax, [r15+10h]
0x14039afb0  mov     edx, edi
0x14039afb2  mov     ecx, [rax+rdx*4+4D8h]
0x14039afb9  shr     ecx, 9
0x14039afbc  test    cl, 1
0x14039afbf  jz      loc_14039E5BC
0x14039afc5  mov     rcx, [r15+10h]; this
0x14039afc9  mov     edx, edi; unsigned int
0x14039afcb  call    ?IsFullWDDMDevice@DXGDEVICE@@QEBA?BEI@Z; DXGDEVICE::IsFullWDDMDevice(uint)
0x14039afd0  test    al, al
0x14039afd2  jnz     loc_14039C3D3
0x14039afd8  mov     rdx, [r15+10h]
0x14039afdc  cmp     [rdx+768h], rsi
  ... truncated ...
```
