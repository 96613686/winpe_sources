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
  int v21; // r10d
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
  int v35; // r8d
  int v36; // edx
  unsigned __int8 IsFullWDDMDevice; // al
  struct VIDSCH_SUBMIT_DATA_BASE *v38; // r12
  __int64 v39; // rdx
  int v40; // eax
  UINT v41; // eax
  __int64 v42; // r8
  unsigned int v43; // ebx
  __int64 v44; // rdi
  unsigned int v45; // eax
  __int64 v46; // r8
  int v47; // ecx
  struct DXGALLOCATION *v48; // rdx
  __int64 v49; // rdi
  unsigned int v50; // eax
  __int64 v51; // r8
  int v52; // ecx
  struct DXGALLOCATION *v53; // rdx
  int v54; // eax
  unsigned int v55; // r8d
  char v56; // dl
  UINT v57; // edx
  DXGPRESENT *v58; // rcx
  char v59; // dl
  DXGADAPTER *v60; // rcx
  struct COREDEVICEACCESS *v61; // rdi
  int v62; // eax
  BOOL v63; // ebx
  DXGADAPTERSTOPRESETLOCKSHARED *v64; // rsi
  int v65; // r14d
  HANDLE CurrentThreadId; // rax
  __int64 v67; // r8
  CWin32kLocks *v68; // rsi
  int v69; // ebx
  HDC v70; // rdi
  HDC v71; // r8
  HDEV v72; // rsi
  __int64 v73; // rcx
  __int64 v74; // rax
  int v75; // ecx
  struct DXGALLOCATION *v76; // rax
  const wchar_t *v77; // r9
  struct VIDMM_DMA_BUFFER *v78; // rdx
  unsigned int v79; // eax
  __int64 v80; // rcx
  int v81; // eax
  HDC v82; // rdi
  DXGPROCESS *Current; // rax
  const struct _DXGKWIN32KENG_INTERFACE *v84; // rax
  const struct _DXGKWIN32KENG_INTERFACE *v85; // rbx
  DXGADAPTERSTOPRESETLOCKSHARED *v86; // r14
  unsigned int v87; // edx
  __int64 v88; // r8
  int v89; // eax
  int v90; // ebx
  unsigned int j; // edi
  unsigned int v92; // ecx
  unsigned int v93; // eax
  struct tagRECT *v94; // r8
  RECT *v95; // rcx
  struct COREDEVICEACCESS *v96; // rsi
  int v97; // eax
  __int128 v98; // xmm0
  int v99; // esi
  LONG v100; // eax
  struct tagRECT *DdiSubRectList; // rax
  __int64 v102; // rcx
  unsigned int v103; // ebx
  unsigned int i; // ebx
  int v105; // eax
  ADAPTER_RENDER *v106; // rcx
  int v107; // eax
  __int64 v108; // rax
  __int64 v109; // rdi
  unsigned int v110; // r9d
  _OWORD *v111; // rcx
  _OWORD *v112; // rax
  __int128 v113; // xmm1
  int v114; // eax
  int v115; // eax
  void *v116; // rax
  const RECT *pDstSubRects; // r14
  UINT SubRectCnt; // esi
  UINT v119; // ebx
  int v120; // r15d
  __int64 v121; // r9
  unsigned int v122; // r8d
  unsigned int v123; // r10d
  UINT k; // edx
  __int64 v125; // rcx
  int v126; // eax
  struct VIDSCH_SUBMIT_DATA_BASE *v127; // rbx
  int v128; // ecx
  int v129; // eax
  int v130; // ecx
  int v131; // eax
  int v132; // ecx
  int v133; // edx
  int v134; // eax
  int v135; // edx
  UINT v136; // ecx
  int v137; // ecx
  __int64 v138; // rdx
  D3DDDI_FLIPINTERVAL_TYPE *v139; // rbx
  int DeviceFlipMode; // eax
  const struct DXGALLOCATION *DisplayedPrimary; // rax
  __int64 v142; // rax
  int v143; // ecx
  __int64 v144; // rdx
  unsigned int v145; // edx
  int v146; // ebx
  DXGDEVICE *v147; // rbx
  char v148; // bl
  CWin32kLocks *v149; // r14
  DXGADAPTERSTOPRESETLOCKSHARED *v150; // rbx
  struct DXGDEVICE *v151; // rdi
  __int64 v152; // rbx
  struct DXGPROCESS *v153; // rax
  int v154; // eax
  const struct _DXGKWIN32KENG_INTERFACE *v155; // rbx
  int v156; // eax
  struct DXGADAPTERSTOPRESETLOCKSHARED *v157; // rsi
  struct DXGDEVICE *v158; // rdi
  __int64 v159; // rbx
  struct DXGPROCESS *v160; // rax
  unsigned int (__fastcall *v161)(const struct DXGK_PRESENT_PARAMS *, HDC, _QWORD, const RECT *); // r14
  HDC v162; // rax
  int v163; // r8d
  char v164; // al
  CWin32kLocks *v165; // rax
  const RECT *v166; // r14
  UINT v167; // esi
  UINT v168; // ebx
  int v169; // r15d
  __int64 v170; // r9
  unsigned int v171; // r8d
  unsigned int v172; // r10d
  struct DXGPROCESS *v173; // rax
  unsigned int v174; // edi
  struct DXGPROCESS *v175; // rbx
  __int64 v176; // rcx
  __int64 v177; // r8
  int v178; // edx
  struct DXGALLOCATION *v179; // rdx
  __int64 v180; // rax
  unsigned int v181; // r12d
  unsigned __int8 *v182; // rsi
  unsigned int v183; // r14d
  __int64 v184; // rdx
  struct DXGHWQUEUE **v185; // rax
  __int64 v186; // rdi
  struct DXGHWQUEUE *v187; // rbx
  const RECT *v188; // rsi
  UINT v189; // edi
  UINT v190; // ebx
  unsigned int v191; // r15d
  __int64 v192; // r9
  unsigned int v193; // r8d
  unsigned int v194; // r10d
  __int64 v195; // rbx
  struct DXGALLOCATION *v196; // rax
  __int64 v197; // r8
  unsigned int v198; // edi
  DXGADAPTER *v199; // rcx
  int v200; // eax
  unsigned int v201; // ecx
  signed int v202; // edx
  int v203; // ecx
  signed int v204; // eax
  int v205; // r8d
  unsigned int m; // esi
  unsigned int v207; // r9d
  __int64 v208; // rbx
  __int64 v209; // r14
  __int64 v210; // r10
  int v211; // r8d
  int v212; // r11d
  int v213; // edx
  unsigned int v214; // ebx
  const RECT *v215; // r8
  int v216; // r10d
  int v217; // r11d
  __int64 v218; // rdx
  RECT v219; // xmm0
  UINT Value; // edx
  unsigned int v221; // esi
  int v222; // ecx
  __int64 v223; // r8
  int v224; // eax
  unsigned int v225; // edx
  int v226; // r8d
  int v227; // r9d
  int v228; // ecx
  const wchar_t *v229; // r9
  __int64 v230; // rax
  struct _DXGKARG_PRESENT *v231; // rbx
  int v232; // edx
  __int64 v233; // rax
  int v234; // ecx
  int v235; // edx
  int v236; // eax
  unsigned __int8 v237; // al
  DXGDEVICE *v238; // rcx
  unsigned int v239; // edx
  int v240; // eax
  const struct _DXGKWIN32KENG_INTERFACE *v241; // rsi
  int v242; // ebx
  int v243; // eax
  int v244; // ecx
  int v245; // eax
  DXGPRESENTMUTEX *v246; // rcx
  __int64 v247; // rbx
  const struct _CDDDXGK_INTERFACE *CddInterface; // rax
  int v249; // eax
  struct VIDMM_DMA_BUFFER *v250; // rdx
  unsigned __int8 v251; // al
  __int64 v252; // rax
  int v253; // eax
  struct VIDMM_DMA_BUFFER *v254; // rdx
  int v255; // eax
  __int64 v256; // rcx
  struct VIDMM_GLOBAL *v257; // rdx
  VIDMM_EXPORT *v258; // rcx
  struct DXGALLOCATION *v259; // rsi
  unsigned int v260; // edx
  __int128 v261; // xmm0
  __int64 v262; // rax
  int v263; // eax
  UINT v264; // ecx
  enum _D3DDDIFORMAT v265; // ebx
  __int64 v266; // rcx
  __int64 v267; // rdx
  __int64 v268; // r8
  int v269; // eax
  unsigned int v270; // edx
  COREDEVICEACCESS *v271; // rcx
  unsigned __int8 v272; // di
  int v273; // ebx
  LONG v274; // ecx
  LONG v275; // ecx
  LONG v276; // eax
  struct DXGPROCESS *v277; // rax
  D3DKMT_HANDLE v278; // eax
  DXGDEVICE *v279; // rbx
  int v280; // edi
  unsigned __int8 v281; // al
  char v282; // bl
  const struct _DXGKWIN32KENG_INTERFACE *v283; // rbx
  int v284; // eax
  int v285; // eax
  unsigned int (__fastcall *v286)(HDC, _QWORD, __int64, _QWORD); // r14
  unsigned int v287; // edi
  __int64 v288; // rsi
  HDC v289; // rax
  int v290; // eax
  __int64 v291; // rax
  const wchar_t *v292; // r9
  __int64 v293; // rcx
  unsigned __int8 v294; // r8
  int CurrentOrientation; // eax
  __int64 v296; // rsi
  unsigned int v297; // r14d
  unsigned int v298; // r12d
  struct DXGHWQUEUE **v299; // rax
  struct DXGHWQUEUE *v300; // rbx
  struct DXGPROCESS *v301; // rax
  char pData; // [rsp+20h] [rbp-100h]
  char v303; // [rsp+20h] [rbp-100h]
  __int64 v304; // [rsp+20h] [rbp-100h]
  struct _DXGKARG_PRESENT *v305; // [rsp+20h] [rbp-100h]
  __int64 v306; // [rsp+28h] [rbp-F8h]
  __int64 v307; // [rsp+28h] [rbp-F8h]
  __int64 v308; // [rsp+30h] [rbp-F0h]
  __int64 v309; // [rsp+30h] [rbp-F0h]
  __int64 v310; // [rsp+38h] [rbp-E8h]
  __int64 v311; // [rsp+38h] [rbp-E8h]
  __int64 v312; // [rsp+40h] [rbp-E0h]
  __int64 v313; // [rsp+40h] [rbp-E0h]
  struct VIDSCH_SUBMIT_DATA_BASE *v314; // [rsp+58h] [rbp-C8h]
  enum _D3DDDIFORMAT v315; // [rsp+60h] [rbp-C0h]
  struct DXGALLOCATION *v317; // [rsp+A8h] [rbp-78h] BYREF
  char v318; // [rsp+B0h] [rbp-70h]
  unsigned int v319; // [rsp+B4h] [rbp-6Ch] BYREF
  unsigned int v320; // [rsp+B8h] [rbp-68h]
  char v321; // [rsp+BCh] [rbp-64h]
  unsigned int v322; // [rsp+C0h] [rbp-60h]
  CWin32kLocks *v323; // [rsp+C8h] [rbp-58h]
  struct DXGALLOCATION *v324; // [rsp+D0h] [rbp-50h] BYREF
  unsigned int v325; // [rsp+D8h] [rbp-48h]
  DXGADAPTERSTOPRESETLOCKSHARED *v326; // [rsp+E0h] [rbp-40h]
  enum _D3DDDIFORMAT Format; // [rsp+E8h] [rbp-38h]
  unsigned int v328[2]; // [rsp+F0h] [rbp-30h]
  const struct _DXGKWIN32KENG_INTERFACE *v329; // [rsp+F8h] [rbp-28h]
  struct VIDSCH_SUBMIT_DATA_BASE *v330; // [rsp+100h] [rbp-20h]
  unsigned int v331[2]; // [rsp+108h] [rbp-18h]
  unsigned int v332; // [rsp+110h] [rbp-10h]
  __int64 v333; // [rsp+118h] [rbp-8h] BYREF
  _BYTE v334[24]; // [rsp+120h] [rbp+0h] BYREF
  struct DXGCONTEXT **v335; // [rsp+138h] [rbp+18h]
  __int64 v336; // [rsp+140h] [rbp+20h] BYREF
  DXGCONTEXT *v337; // [rsp+148h] [rbp+28h]
  char v338[8]; // [rsp+150h] [rbp+30h] BYREF
  char v339[8]; // [rsp+158h] [rbp+38h] BYREF
  char v340[8]; // [rsp+160h] [rbp+40h] BYREF
  char v341[8]; // [rsp+168h] [rbp+48h] BYREF
  __int64 v342; // [rsp+170h] [rbp+50h] BYREF
  _D3DKMT_UNLOCK2 v343; // [rsp+178h] [rbp+58h] BYREF
  struct _D3DKMT_UNLOCK v344; // [rsp+180h] [rbp+60h] BYREF
  struct _DXGKARG_DESCRIBEALLOCATION v345; // [rsp+190h] [rbp+70h] BYREF
  struct _DXGKARG_DESCRIBEALLOCATION v346; // [rsp+1C0h] [rbp+A0h] BYREF
  _BYTE v347[24]; // [rsp+1F0h] [rbp+D0h] BYREF
  struct _D3DKMT_LOCK2 v348; // [rsp+208h] [rbp+E8h] BYREF
  _BYTE v349[24]; // [rsp+220h] [rbp+100h] BYREF
  struct _D3DKMT_LOCK v350; // [rsp+238h] [rbp+118h] BYREF
  struct _DXGKARG_DESCRIBEALLOCATION v351; // [rsp+268h] [rbp+148h] BYREF
  enum _D3DDDIFORMAT v352[4]; // [rsp+2A0h] [rbp+180h]
  _DWORD v353[8]; // [rsp+2F0h] [rbp+1D0h] BYREF
  _QWORD v354[70]; // [rsp+310h] [rbp+1F0h] BYREF
  struct _DXGKARG_PRESENT v355; // [rsp+540h] [rbp+420h] BYREF
  struct tagRECT v356; // [rsp+5F0h] [rbp+4D0h] BYREF
  struct tagRECT v357; // [rsp+600h] [rbp+4E0h] BYREF
  __int128 v358; // [rsp+610h] [rbp+4F0h] BYREF
  struct tagRECT Source1; // [rsp+620h] [rbp+500h] BYREF
  struct tagRECT v360; // [rsp+630h] [rbp+510h] BYREF
  int v361; // [rsp+640h] [rbp+520h]
  unsigned int v362; // [rsp+644h] [rbp+524h]
  _QWORD v363[39]; // [rsp+648h] [rbp+528h] BYREF
  _DWORD v364[16]; // [rsp+780h] [rbp+660h] BYREF
  _DWORD v365[16]; // [rsp+7C0h] [rbp+6A0h] BYREF
  _DWORD v366[16]; // [rsp+800h] [rbp+6E0h] BYREF
  _DWORD v367[16]; // [rsp+840h] [rbp+720h] BYREF
  _DWORD v368[16]; // [rsp+880h] [rbp+760h] BYREF
  _DWORD v369[16]; // [rsp+8C0h] [rbp+7A0h] BYREF
  _DWORD v370[16]; // [rsp+900h] [rbp+7E0h] BYREF
  _DWORD v371[16]; // [rsp+940h] [rbp+820h] BYREF
  _DWORD v372[16]; // [rsp+980h] [rbp+860h] BYREF
  _DWORD v373[16]; // [rsp+9C0h] [rbp+8A0h] BYREF
  _DWORD v374[16]; // [rsp+A00h] [rbp+8E0h] BYREF
  _DWORD v375[16]; // [rsp+A40h] [rbp+920h] BYREF

  v7 = this;
  v337 = this;
  v9 = *((_QWORD *)this + 2);
  v323 = a5;
  v326 = a4;
  v10 = *(ADAPTER_RENDER **)(v9 + 16);
  v330 = a7;
  v335 = a6;
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
  v329 = Win32kInterface;
  if ( (v12 & 0x12000) == 0x12000 )
  {
    v24 = -1073741811;
    WdLogSingleEntry2(3, v7, -1073741811);
    WdLogGlobalForLineNumber = 4250;
    return (unsigned int)v24;
  }
  memset(&v355, 0, sizeof(v355));
  v325 = *((_DWORD *)a2 + 5);
  v319 = *((_DWORD *)a2 + 6);
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
  DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v317, 0);
  DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v324, 0);
  DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v333, 0);
  v15 = *((_DWORD *)a2 + 6);
  if ( v15 )
  {
    v49 = *(_QWORD *)(*((_QWORD *)v7 + 2) + 40LL);
    DXGPUSHLOCK::AcquireShared((DXGPUSHLOCK *)(v49 + 248));
    v50 = (v15 >> 6) & 0xFFFFFF;
    if ( v50 < *(_DWORD *)(v49 + 296)
      && (v51 = *(_QWORD *)(v49 + 280), ((v15 >> 25) & 0x60) == (*(_BYTE *)(v51 + 16LL * v50 + 8) & 0x60))
      && (*(_DWORD *)(v51 + 16LL * v50 + 8) & 0x2000) == 0
      && (v52 = *(_DWORD *)(v51 + 16LL * v50 + 8) & 0x1F) != 0 )
    {
      if ( v52 == 5 )
      {
        v53 = *(struct DXGALLOCATION **)(v51 + 16LL * v50);
      }
      else
      {
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 318;
        DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
        v53 = 0;
      }
    }
    else
    {
      v53 = 0;
    }
    DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v338, v53);
    _InterlockedDecrement((volatile signed __int32 *)(v49 + 264));
    ExReleasePushLockSharedEx(v49 + 248, 0);
    KeLeaveCriticalRegion();
    DXGALLOCATIONREFERENCE::MoveAssign(&v324, v338);
    DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v338);
    if ( !v324 )
    {
      v24 = -1073741811;
      WdLogSingleEntry3(3, -1073741811, v7, *((unsigned int *)a2 + 6));
      WdLogGlobalForLineNumber = 4305;
      goto LABEL_34;
    }
    if ( *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v324 + 1) + 16LL) + 16LL) != *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2)
                                                                                                + 16LL)
                                                                                    + 16LL) )
    {
      v24 = -1073741811;
      WdLogSingleEntry3(2, *((_QWORD *)v7 + 2), v324, -1073741811);
      v76 = v324;
      WdLogGlobalForLineNumber = 4315;
      goto LABEL_119;
    }
    memset(&v351, 0, sizeof(v351));
    v351.hAllocation = *(HANDLE *)(*((_QWORD *)v324 + 6) + 16LL);
    v54 = ADAPTER_RENDER::DdiDescribeAllocation(*(ADAPTER_RENDER **)(*((_QWORD *)v7 + 2) + 16LL), &v351);
    v24 = v54;
    if ( v54 < 0 )
    {
      v195 = v54;
      WdLogSingleEntry4(2, v54, v7, *(_QWORD *)(*((_QWORD *)v324 + 6) + 16LL), v324);
      v196 = v324;
      WdLogGlobalForLineNumber = 4328;
      goto LABEL_352;
    }
    Width = v351.Width;
    v331[0] = v351.Height;
  }
  else
  {
    Width = 0;
    v331[0] = 0;
  }
  v17 = (*((_DWORD *)a2 + 22) & 0x8002) == 0;
  v328[0] = Width;
  if ( v17 )
  {
    v43 = *((_DWORD *)a2 + 5);
    v44 = *(_QWORD *)(*((_QWORD *)v7 + 2) + 40LL);
    DXGPUSHLOCK::AcquireShared((DXGPUSHLOCK *)(v44 + 248));
    v45 = (v43 >> 6) & 0xFFFFFF;
    if ( v45 < *(_DWORD *)(v44 + 296)
      && (v46 = *(_QWORD *)(v44 + 280), ((v43 >> 25) & 0x60) == (*(_BYTE *)(v46 + 16LL * v45 + 8) & 0x60))
      && (*(_DWORD *)(v46 + 16LL * v45 + 8) & 0x2000) == 0
      && (v47 = *(_DWORD *)(v46 + 16LL * v45 + 8) & 0x1F) != 0 )
    {
      if ( v47 == 5 )
      {
        v48 = *(struct DXGALLOCATION **)(v46 + 16LL * v45);
      }
      else
      {
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 318;
        DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
        v48 = 0;
      }
    }
    else
    {
      v48 = 0;
    }
    DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v339, v48);
    _InterlockedDecrement((volatile signed __int32 *)(v44 + 264));
    ExReleasePushLockSharedEx(v44 + 248, 0);
    KeLeaveCriticalRegion();
    DXGALLOCATIONREFERENCE::MoveAssign(&v317, v339);
    DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v339);
    v20 = v317;
    if ( !v317 )
    {
      v24 = -1073741811;
      WdLogSingleEntry3(3, -1073741811, v7, *((unsigned int *)a2 + 5));
      WdLogGlobalForLineNumber = 4343;
      goto LABEL_34;
    }
    memset(&v346, 0, sizeof(v346));
    v346.hAllocation = *(HANDLE *)(*((_QWORD *)v317 + 6) + 16LL);
    if ( (*((_DWORD *)a2 + 22) & 0x10000000) != 0 )
    {
      v18 = *((_DWORD *)a2 + 379);
      v346.Width = v18;
      Height = *((_DWORD *)a2 + 380);
      v346.Height = Height;
      Format = *((_DWORD *)a2 + 381);
      v346.Format = Format;
      goto LABEL_18;
    }
    v106 = *(ADAPTER_RENDER **)(*((_QWORD *)v7 + 2) + 16LL);
    if ( *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v317 + 1) + 16LL) + 16LL) == *((_QWORD *)v106 + 2) )
    {
      v107 = ADAPTER_RENDER::DdiDescribeAllocation(v106, &v346);
      v24 = v107;
      if ( v107 >= 0 )
      {
        Height = v346.Height;
        v18 = v346.Width;
        Format = v346.Format;
        goto LABEL_17;
      }
      v195 = v107;
      WdLogSingleEntry4(2, v107, v7, *(_QWORD *)(*((_QWORD *)v317 + 6) + 16LL), v317);
      v196 = v317;
      WdLogGlobalForLineNumber = 4382;
LABEL_352:
      v77 = L"ret = 0x%I64x Context 0x%I64x: DdiDescribeAllocation failed 0x%I64x 0x%I64x";
      v312 = 0;
      v310 = (__int64)v196;
      v308 = *(_QWORD *)(*((_QWORD *)v196 + 6) + 16LL);
      v306 = (__int64)v7;
      v304 = v195;
      goto LABEL_120;
    }
    v24 = -1073741811;
    WdLogSingleEntry3(2, *((_QWORD *)v7 + 2), v317, -1073741811);
    v76 = v317;
    WdLogGlobalForLineNumber = 4371;
LABEL_119:
    v312 = 0;
    v77 = L"Device 0x%p does not match allocation 0x%p owner, returning 0x%I64x";
    v310 = 0;
    v308 = -1073741811;
    v306 = (__int64)v76;
    v304 = *((_QWORD *)v7 + 2);
    goto LABEL_120;
  }
  v18 = 0;
  Format = D3DDDIFMT_UNKNOWN;
  Height = 0;
LABEL_17:
  v20 = v317;
LABEL_18:
  v21 = *((_DWORD *)a2 + 6);
  v320 = v18;
  v322 = Height;
  if ( v21 )
  {
    LODWORD(v22) = *((_DWORD *)a2 + 22);
    if ( (v22 & 0x10000) == 0 )
      goto LABEL_355;
  }
  v22 = *((unsigned int *)a2 + 22);
  if ( (v22 & 4) == 0 )
  {
    v332 = 0;
    if ( (v22 & 1) == 0 )
    {
      v23 = 2;
      if ( (v22 & 2) == 0 )
      {
        if ( (v22 & 0x8000) == 0 )
        {
          v24 = -1073741811;
          WdLogSingleEntry5(3, -1073741811, v7);
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
            v27 = v326;
            v28 = SubmitPresentHistoryTokenPreparation(
                    v326,
                    a3,
                    *(struct DXGADAPTER **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 16LL),
                    (struct _D3DKMT_PRESENTHISTORYTOKEN *)((char *)a2 + 360),
                    *((_QWORD *)a2 + 44),
                    (v22 & 0x10) != 0);
            if ( v28 >= 0 )
            {
              TOKEN_BINDING_GUARD::TOKEN_BINDING_GUARD(
                (TOKEN_BINDING_GUARD *)v353,
                (struct _D3DKMT_PRESENTHISTORYTOKEN *)((char *)a2 + 360),
                v27,
                a3);
              v353[0] = SubmitPresentHistoryToken(
                          (struct _D3DKMT_PRESENTHISTORYTOKEN *)((char *)a2 + 360),
                          a3,
                          v27,
                          v323,
                          1,
                          0,
                          a2,
                          v330,
                          v7,
                          0,
                          0);
              v24 = v353[0];
              TOKEN_BINDING_GUARD::~TOKEN_BINDING_GUARD((TOKEN_BINDING_GUARD *)v353);
              if ( v24 >= 0 )
              {
LABEL_30:
                v29 = v333;
                if ( v333 )
                {
                  if ( (*((_DWORD *)a2 + 22) & 0x10000000) == 0 )
                  {
                    v108 = *((_QWORD *)v7 + 2);
                    v109 = *(_QWORD *)(v108 + 1896);
                    if ( v109 )
                    {
                      if ( (*(_DWORD *)(*(_QWORD *)(v108 + 40) + 408LL) & 4) == 0 )
                      {
                        memset(v363, 0, 0x130u);
                        v110 = v332;
                        v361 = *(_DWORD *)a2;
                        v362 = v332;
                        LODWORD(v363[0]) = (*(_DWORD *)(*(_QWORD *)(v333 + 48) + 4LL) >> 6) & 0xF;
                        v111 = &v363[1];
                        HIDWORD(v363[0]) = *((_DWORD *)a2 + 23);
                        v112 = (_OWORD *)((char *)a2 + 96);
                        do
                        {
                          *v111 = *v112;
                          v111[1] = v112[1];
                          v111[2] = v112[2];
                          v111[3] = v112[3];
                          v111[4] = v112[4];
                          v111[5] = v112[5];
                          v111[6] = v112[6];
                          v113 = v112[7];
                          v112 += 8;
                          v111[7] = v113;
                          v111 += 8;
                          --v23;
                        }
                        while ( v23 );
                        LODWORD(v363[33]) = 0;
                        LODWORD(v363[37]) = 4;
                        LODWORD(v363[35]) = 0;
                        v114 = OUTPUTDUPL_MGR::ProcessPresent(
                                 *(OUTPUTDUPL_MGR **)(*(_QWORD *)(v109 + 3248) + 120LL),
                                 v7,
                                 (struct _D3DKMT_OUTPUTDUPLPRESENTFLAGS)4,
                                 v110,
                                 HIDWORD(v363[0]),
                                 (struct _D3DKMT_PRESENT_RGNS *)&v363[33],
                                 a2,
                                 (*(_DWORD *)(*(_QWORD *)(v29 + 48) + 4LL) >> 6) & 0xF,
                                 v335,
                                 v26);
                        if ( v114 == 259 )
                          v114 = 0;
                        v24 = v114;
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
      v266 = *((_QWORD *)v7 + 2);
      if ( !*(_QWORD *)(v266 + 1896) )
      {
        v24 = -1073741811;
        WdLogSingleEntry2(3, *((_QWORD *)v7 + 2), -1073741811);
        WdLogGlobalForLineNumber = 5398;
        goto LABEL_34;
      }
      v267 = *((unsigned int *)a2 + 4);
      v268 = *(unsigned int *)(v266 + 1904);
      if ( (unsigned int)v268 <= (unsigned int)v267 )
      {
        WdLogSingleEntry2(3, v267, v268);
        WdLogGlobalForLineNumber = 5404;
        goto LABEL_416;
      }
    }
    v42 = *((_QWORD *)a2 + 9);
    if ( (((unsigned int)v22 >> 1) & 1) != 0 )
    {
      if ( !v42 || !*((_DWORD *)a2 + 16) || (v22 & 0x86BC) != 0 || (v22 & 1) != 0 )
      {
        v24 = -1073741811;
        WdLogSingleEntry5(3, v7, v42);
        WdLogGlobalForLineNumber = 5426;
        goto LABEL_34;
      }
      v325 = 0;
    }
    else
    {
      if ( !v42 || !*((_DWORD *)a2 + 16) || !v18 || !Height || (v22 & 0x802C) != 0 )
      {
        v24 = -1073741811;
        WdLogSingleEntry5(3, v7, v42);
        WdLogGlobalForLineNumber = 5446;
        goto LABEL_34;
      }
      if ( (((unsigned int)v22 >> 9) & 1) != 0 || (v22 & 0x400) != 0 )
      {
        if ( (((unsigned int)v22 >> 9) & 1) == (((unsigned int)v22 >> 10) & 1) )
        {
          v24 = -1073741811;
          WdLogSingleEntry5(3, -1073741811, v7);
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
          WdLogSingleEntry5(3, v7, *((_QWORD *)a2 + 9));
          WdLogGlobalForLineNumber = 5467;
          goto LABEL_34;
        }
      }
    }
    v55 = *((_DWORD *)a2 + 22);
    v56 = v55 ^ (v55 & 2 | *(_BYTE *)&v355.Flags.0 & 0xFD);
    v55 >>= 5;
    v57 = (*((_DWORD *)a2 + 22) & 2 | v355.Flags.Value & 0xFFFFFFFD) ^ v56 & 1;
    v355.Flags.Value = v57
                     ^ ((unsigned __int8)v57
                      ^ (unsigned __int8)v55)
                     & 0x10
                     ^ ((unsigned __int8)(v57 ^ (v57 ^ v55) & 0x10)
                      ^ (unsigned __int8)v55)
                     & 0x20
                     ^ ((unsigned __int8)(v57 ^ (v57 ^ v55) & 0x10 ^ (v57 ^ (v57 ^ v55) & 0x10 ^ v55) & 0x20)
                      ^ (unsigned __int8)v55)
                     & 0x40;
    v355.Color = *((_DWORD *)a2 + 7);
    v24 = DXGPRESENT::CheckInput(*((DXGPRESENT **)v7 + 19), (const struct _D3DKMT_PRESENT *)a2, v18, Height);
    if ( v24 < 0 )
      goto LABEL_31;
    v58 = (DXGPRESENT *)*((_QWORD *)v7 + 19);
    v59 = 0;
    v318 = 0;
    if ( (*((_DWORD *)v58 + 1) & 4) != 0 )
    {
LABEL_638:
      if ( bTracingEnabled && !v59 && (Microsoft_Windows_DxgKrnlEnableBits & 0x20) != 0 )
        McTemplateK0p_EtwWriteTransfer(&DxgkControlGuid_Context, EventBlitCancel, 0, *((_QWORD *)a2 + 1));
      v26 = a3;
      goto LABEL_63;
    }
    DXGPRESENT::CheckOutput(v58, Width, v331[0]);
    v60 = *(DXGADAPTER **)(*((_QWORD *)v7 + 2) + 1896LL);
    if ( !v60 || DXGADAPTER::IsDisplayOnlyAdapter(v60) )
    {
      v61 = a3;
      v62 = DXGCONTEXT::WaitForQueuedPresentLimit(v7, 0, (*((_DWORD *)a2 + 22) & 0x10) == 0, a3);
      v24 = v62;
      if ( v62 < 0 )
      {
        WdLogSingleEntry2(4, v62, v7);
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
      v61 = a3;
      for ( i = 0; i < *(_DWORD *)(*((_QWORD *)v7 + 2) + 1904LL); ++i )
      {
        v105 = DXGCONTEXT::WaitForQueuedPresentLimit(v7, i, (*((_DWORD *)a2 + 22) & 0x10) == 0, a3);
        v24 = v105;
        if ( v105 < 0 )
        {
          WdLogSingleEntry2(4, v105, v7);
          WdLogGlobalForLineNumber = 5502;
          goto LABEL_34;
        }
      }
    }
    v24 = DXGCONTEXT::AcquireDmaBuffer(v7, (struct VIDMM_DMA_BUFFER **)v7 + 45, v61, 0);
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
      (DXGPRESENTMUTEX *)v334,
      *(struct ADAPTER_RENDER *const *)(*((_QWORD *)v7 + 2) + 16LL));
    if ( (*((_DWORD *)a2 + 22) & 0x10000) != 0 )
    {
      v63 = 0;
      if ( *((_DWORD *)a2 + 6) )
      {
        v80 = *((_QWORD *)v324 + 6);
        v81 = *(_DWORD *)(v80 + 4);
        *(_DWORD *)(v80 + 4) = v81 | 0x400;
        v63 = (v81 & 0x400) == 0;
      }
      v64 = v326;
    }
    else
    {
      COREDEVICEACCESS::Release(v61);
      v64 = v326;
      DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v326);
      DXGPRESENTMUTEX::Acquire((DXGPRESENTMUTEX *)v334);
      DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v64);
      v269 = COREDEVICEACCESS::AcquireShared(v61, 0);
      v24 = v269;
      if ( v269 < 0 )
      {
        WdLogSingleEntry2(4, v269, v7);
        WdLogGlobalForLineNumber = 5551;
        goto LABEL_476;
      }
      v63 = 0;
    }
    v65 = (*((__int64 (**)(void))v329 + 1))();
    CurrentThreadId = PsGetCurrentThreadId();
    v17 = *((_BYTE *)v7 + 434) == 0;
    *(_QWORD *)v328 = CurrentThreadId;
    if ( v17 )
    {
      VIDSCH_EXPORT::VidSchGetMonitorPowerState(
        *(VIDSCH_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 736LL),
        *(struct _VIDSCH_GLOBAL **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 744LL));
      CurrentThreadId = *(HANDLE *)v328;
    }
    v67 = *((_QWORD *)v7 + 19);
    if ( *(_DWORD *)(v67 + 8) == v65
      && *(HANDLE *)(v67 + 56) == CurrentThreadId
      && *(_QWORD *)(v67 + 48) == *((_QWORD *)a2 + 1)
      && !*(_DWORD *)(v67 + 64)
      && !v63 )
    {
      v270 = *(_DWORD *)(v67 + 4);
      if ( !(((v270 & 8) != 0) | BYTE1(v270) & 1) )
      {
        if ( (v270 & 1) != 0 )
        {
          v24 = -1071775738;
        }
        else if ( (((*((_DWORD *)a2 + 22) & 0x10000) == 0) & (unsigned __int8)~(unsigned __int8)(v270 >> 4)) != 0 )
        {
          DXGDEVICE::SynchronizePresentToPrimary(*((DXGDEVICE **)v7 + 2), v7, (struct DXGPRESENTMUTEX *)v334, 0);
        }
        goto LABEL_571;
      }
    }
    DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v334);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v64);
    COREDEVICEACCESS::Release(v61);
    v68 = v323;
    v69 = CWin32kLocks::Lock(v323, *((HWND *)a2 + 1), *((_WORD *)a2 + 45) & 1, 1, 0);
    if ( _bittest((const signed __int32 *)a2 + 22, 0x10u) )
    {
      v342 = 0;
      (*((void (__fastcall **)(_QWORD, __int64 *))v329 + 31))(*(_QWORD *)v68, &v342);
      *(_QWORD *)(*((_QWORD *)v7 + 19) + 440LL) = v342;
    }
    if ( !_bittest((const signed __int32 *)a2 + 22, 0x10u) )
      DXGPRESENTMUTEX::Acquire((DXGPRESENTMUTEX *)v334);
    DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v326);
    v24 = COREDEVICEACCESS::AcquireShared(v61, 0);
    if ( v24 >= 0 )
    {
      v24 = 0;
      if ( v69 < 0 )
      {
        v24 = v69;
        goto LABEL_115;
      }
      if ( (*((_DWORD *)a2 + 22) & 0x10000) != 0 && *((_DWORD *)a2 + 6) && !*(_QWORD *)(*((_QWORD *)v7 + 19) + 440LL) )
      {
        WdLogSingleEntry2(4, 0, v7);
        WdLogGlobalForLineNumber = 5674;
        v78 = (struct VIDMM_DMA_BUFFER *)*((_QWORD *)v7 + 45);
        if ( v78 )
        {
          VIDMM_EXPORT::VidMmReleaseDmaBuffer(*(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL), v78);
          *((_QWORD *)v7 + 45) = 0;
        }
        goto LABEL_477;
      }
      v70 = *(HDC *)v68;
      v71 = *(HDC *)v68;
      v72 = (HDEV)*((_QWORD *)v68 + 2);
      v24 = DXGPRESENT::CheckVisRgn(
              *((DXGPRESENT **)v7 + 19),
              (const struct _D3DKMT_PRESENT *)a2,
              v71,
              v72,
              *((const struct DXGDEVICE **)v7 + 2),
              v320,
              v322,
              Format,
              1);
      if ( v24 == 261 )
      {
        DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v334);
        COREDEVICEACCESS::Release(a3);
        DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v326);
        if ( DXGPRESENT::CheckOcclusion(*((DXGPRESENT **)v7 + 19)) )
          v24 = -1071775738;
        if ( (*((_DWORD *)a2 + 22) & 0x10000) == 0 )
          DXGPRESENTMUTEX::Acquire((DXGPRESENTMUTEX *)v334);
        DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v326);
        v115 = COREDEVICEACCESS::AcquireShared(a3, 0);
        v90 = v115;
        if ( v115 < 0 )
        {
          WdLogSingleEntry1(4, v115);
          v271 = a3;
          WdLogGlobalForLineNumber = 5717;
          goto LABEL_565;
        }
        if ( v24 != -1071775738 )
          v24 = DXGPRESENT::CheckVisRgn(
                  *((DXGPRESENT **)v7 + 19),
                  (const struct _D3DKMT_PRESENT *)a2,
                  v70,
                  v72,
                  *((const struct DXGDEVICE **)v7 + 2),
                  v320,
                  v322,
                  Format,
                  0);
      }
      v73 = *((_QWORD *)v7 + 19);
      if ( v24 < 0 )
      {
        v61 = a3;
        v68 = v323;
        if ( (*(_BYTE *)(v73 + 4) & 1) != 0 )
        {
          *(_QWORD *)(v73 + 56) = *(_QWORD *)v328;
          *(_DWORD *)(*((_QWORD *)v7 + 19) + 8LL) = v65;
        }
LABEL_115:
        v74 = *((_QWORD *)v7 + 19);
        v321 = 0;
        v75 = *(_DWORD *)(v74 + 4);
        if ( (v75 & 0x10) == 0 )
        {
          if ( v24 >= 0 && (v75 & 2) == 0 )
          {
            if ( (*((unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD))v329 + 30))(0, 0, 0) )
            {
              if ( (*((_DWORD *)a2 + 22) & 0x12100) != 0x10000 )
              {
                WdLogSingleEntry0(1);
                v291 = 6163;
                v292 = L"((pPresent->Flags.RedirectedBlt) && (!pPresent->Flags.RestrictVidPnSource) && (!pPresent->Flags.Rotate))";
LABEL_620:
                WdLogGlobalForLineNumber = v291;
                DxgkLogInternalTriageEvent(0, 262146, -1, (_DWORD)v292, v291, 0, 0, 0, 0);
              }
            }
            else if ( !*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) && (*((_DWORD *)a2 + 22) & 0x4000000) == 0 )
            {
              WdLogSingleEntry0(1);
              v291 = 6168;
              v292 = L"GetDisplayAdapter() != NULL || pPresent->Flags.CrossAdapter";
              goto LABEL_620;
            }
            if ( (*((_DWORD *)a2 + 22) & 0x10000) == 0 )
              goto LABEL_143;
            v82 = *(HDC *)v68;
            Current = DXGPROCESS::GetCurrent();
            v84 = DXGPROCESS::GetWin32kInterface(Current);
            v85 = v84;
            if ( !v82 || !v84 || *(_DWORD *)(*((_QWORD *)v7 + 19) + 440LL) != *((_DWORD *)a2 + 96) )
              goto LABEL_143;
            v86 = v326;
            DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v326);
            COREDEVICEACCESS::Release(a3);
            memset(v354, 0, 0x228u);
            LODWORD(v354[0]) = DXGPRESENT::GetDdiSubRectCnt(*((DXGPRESENT **)v7 + 19), 0);
            v354[1] = DXGPRESENT::GetDdiSubRectList(*((DXGPRESENT **)v7 + 19), 0);
            v87 = 1;
            v88 = 0;
            v354[3] = *((unsigned int *)v7 + 6);
            for ( LODWORD(v354[2]) = 1; (unsigned int)v88 < *((_DWORD *)a2 + 23); ++LODWORD(v354[2]) )
            {
              v293 = *((unsigned int *)a2 + v88 + 24);
              v88 = (unsigned int)(v88 + 1);
              v354[v87 + 3] = v293;
              v87 = LODWORD(v354[2]) + 1;
            }
            if ( !*((_BYTE *)v7 + 434)
              && VIDSCH_EXPORT::VidSchGetNumUnorderedWaitsInDevice(
                   *(VIDSCH_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 736LL),
                   *(struct _VIDSCH_DEVICE **)(*((_QWORD *)v7 + 2) + 800LL)) )
            {
              v321 = 1;
              LOBYTE(v354[68]) = 1;
            }
            (*((void (__fastcall **)(HDC, _QWORD *))v85 + 32))(v82, v354);
            DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v86);
            v89 = COREDEVICEACCESS::AcquireShared(a3, 0);
            v90 = v89;
            if ( v89 >= 0 )
            {
LABEL_143:
              for ( j = 0; ; ++j )
              {
                if ( (*((_DWORD *)a2 + 22) & 0x10000) != 0 )
                  v92 = 1;
                else
                  v92 = *(_DWORD *)(*((_QWORD *)v7 + 2) + 1904LL);
                if ( j >= v92 )
                  goto LABEL_174;
                v355.SubRectCnt = DXGPRESENT::GetDdiSubRectCnt(*((DXGPRESENT **)v7 + 19), j);
                if ( v355.SubRectCnt )
                {
                  if ( (*((_DWORD *)a2 + 22) & 0x10000) != 0 )
                  {
                    v93 = v319;
                  }
                  else
                  {
                    if ( *((_BYTE *)v7 + 432) || (v294 = 0, *((_BYTE *)v7 + 433)) )
                      v294 = 1;
                    v93 = DXGDEVICE::OpenCddPrimaryHandle(*((DXGDEVICE **)v7 + 2), j, v294, *((_DWORD *)v7 + 97));
                    v319 = v93;
                  }
                  if ( v93 )
                    break;
                }
LABEL_161:
                ;
              }
              v355.pDstSubRects = DXGPRESENT::GetDdiSubRectList(*((DXGPRESENT **)v7 + 19), j);
              if ( (*((_DWORD *)a2 + 22) & 0x2000) != 0 )
              {
                CurrentOrientation = ADAPTER_DISPLAY::GetCurrentOrientation(
                                       *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3248LL),
                                       j,
                                       1);
                v355.Flags.Value = v355.Flags.Value & 0xFFFFFF7F | (CurrentOrientation != 1 ? 0x80 : 0);
              }
              v360 = 0;
              if ( (*((_DWORD *)a2 + 22) & 0x10000) != 0 )
                v94 = &v360;
              else
                v94 = (struct tagRECT *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3248LL)
                                                   + 128LL)
                                       + 4024LL * j
                                       + 628);
              v95 = (RECT *)*((_QWORD *)v7 + 19);
              v355.SrcRect = v95[9];
              DXGPRESENT::GetDdiDstRect((DXGPRESENT *)v95, &v355.DstRect, v94);
              if ( !bTracingEnabled || !*((_QWORD *)v7 + 45) )
              {
LABEL_157:
                if ( *((_BYTE *)v7 + 434) )
                {
                  v296 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 16LL);
                  v297 = *((_DWORD *)v324 + 5);
                  v298 = *((_DWORD *)v317 + 5);
                  v299 = (struct DXGHWQUEUE **)*((_QWORD *)a2 + 188);
                  if ( v299 )
                    v300 = *v299;
                  else
                    v300 = 0;
                  v301 = DXGPROCESS::GetCurrent();
                  v97 = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendBlt(
                          (DXG_GUEST_VIRTUALGPU_VMBUS *)(v296 + 4792),
                          v301,
                          v7,
                          v300,
                          v298,
                          v297,
                          &v355.SrcRect,
                          &v355.DstRect,
                          v355.SubRectCnt,
                          v355.pDstSubRects,
                          v355.PrivateDriverDataSize,
                          (unsigned __int8 *)v355.pPrivateDriverData);
                  v96 = a3;
                }
                else
                {
                  v96 = a3;
                  v315 = Format;
                  v314 = v330;
                  *((_DWORD *)v330 + 29) = j;
                  v97 = DXGCONTEXT::SubmitPresent(
                          v7,
                          (const struct _D3DKMT_PRESENT *)a2,
                          *((struct DXGHWQUEUE ***)a2 + 188),
                          *((_DWORD *)a2 + 23),
                          v335,
                          v317,
                          v325,
                          v319,
                          &v355,
                          0,
                          *((struct VIDMM_DMA_BUFFER **)v7 + 45),
                          v314,
                          v315,
                          a3);
                }
                *((_QWORD *)v7 + 45) = 0;
                v24 = v97;
                if ( (*((_DWORD *)a2 + 22) & 0x10000) != 0
                  && *(_DWORD *)(*((_QWORD *)v7 + 19) + 440LL) == *((_DWORD *)a2 + 96) )
                {
                  *((_DWORD *)a2 + 90) = 3;
                  *((_QWORD *)a2 + 48) = *(_QWORD *)(*((_QWORD *)v7 + 19) + 440LL);
                  if ( v355.SubRectCnt <= 0x10 )
                  {
                    *((_DWORD *)a2 + 100) = v355.SubRectCnt;
                    for ( k = 0; k < v355.SubRectCnt; *(RECT *)((char *)a2 + 16 * v125 + 404) = v355.pDstSubRects[v125] )
                      v125 = k++;
                  }
                  else
                  {
                    *((_DWORD *)a2 + 100) = 1;
                    *(RECT *)((char *)a2 + 404) = v355.DstRect;
                  }
                  *((_DWORD *)a2 + 91) = 16 * (*((_DWORD *)a2 + 100) + 3);
                  DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v334);
                  v24 = SubmitPresentHistoryToken(
                          (struct _D3DKMT_PRESENTHISTORYTOKEN *)((char *)a2 + 360),
                          v96,
                          v326,
                          v323,
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
              VIDMM_EXPORT::VidMmETWAllocationHandle(
                *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 768LL),
                v319);
              v116 = VIDMM_EXPORT::VidMmETWAllocationHandle(
                       *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                       *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 768LL),
                       v325);
              pDstSubRects = v355.pDstSubRects;
              SubRectCnt = v355.SubRectCnt;
              *(_QWORD *)v328 = v116;
              v329 = (const struct _DXGKWIN32KENG_INTERFACE *)*((_QWORD *)v7 + 45);
              if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x20) != 0 )
                McTemplateK0ppxppttqddddddddq_EtwWriteTransfer(
                  (unsigned int)&DxgkControlGuid_Context,
                  (unsigned int)EventBlit,
                  0,
                  *((_QWORD *)a2 + 1),
                  (char)v329);
              v119 = 0;
              if ( !SubRectCnt )
              {
LABEL_225:
                v318 = 1;
                goto LABEL_157;
              }
              v120 = (int)v329;
              while ( 1 )
              {
                v121 = 0;
                v122 = SubRectCnt - v119;
                if ( SubRectCnt - v119 > 0x10 )
                  break;
                v123 = SubRectCnt - v119;
                if ( v122 )
                  goto LABEL_220;
LABEL_221:
                if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x40) != 0 )
                  McTemplateK0ptqDR2DR2DR2DR2_EtwWriteTransfer(
                    (unsigned int)&DxgkControlGuid_Context,
                    (unsigned int)EventBlitRect,
                    0,
                    v120,
                    v122 <= 0x10,
                    v123,
                    (__int64)v374,
                    (__int64)v373,
                    (__int64)v372,
                    (__int64)v375);
                v119 += 16;
                if ( v119 >= SubRectCnt )
                {
                  v7 = v337;
                  goto LABEL_225;
                }
              }
              v123 = 16;
              do
              {
LABEL_220:
                v374[v121] = pDstSubRects[(unsigned int)v121 + v119].left;
                v373[v121] = pDstSubRects[(unsigned int)v121 + v119].right;
                v372[v121] = pDstSubRects[(unsigned int)v121 + v119].top;
                v375[v121] = pDstSubRects[(unsigned int)v121 + v119].bottom;
                v121 = (unsigned int)(v121 + 1);
              }
              while ( (unsigned int)v121 < v123 );
              goto LABEL_221;
            }
            WdLogSingleEntry2(4, v89, v7);
            v271 = a3;
            WdLogGlobalForLineNumber = 6218;
LABEL_565:
            COREDEVICEACCESS::AcquireSharedUncheck(v271, 0);
            DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v334);
            v24 = v90;
            goto LABEL_34;
          }
          goto LABEL_174;
        }
        DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v334);
        if ( v24 < 0 )
        {
LABEL_174:
          v61 = a3;
LABEL_175:
          DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v334);
          if ( v321 )
          {
            CWin32kLocks::Unlock(v323);
            COREDEVICEACCESS::Release(v61);
            DXGDEVICE::FlushScheduler(*((_QWORD *)v7 + 2), 7, 4294967293LL, 0, pData);
            v24 = COREDEVICEACCESS::AcquireShared(v61, 0);
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
          DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v334);
          if ( v24 < 0 )
            goto LABEL_31;
          v59 = v318;
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
        v358 = 0;
        if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
          McTemplateK0q_EtwWriteTransfer(&DxgkControlGuid_Context, EventPerformanceWarning, 0, 0);
        v163 = *((_DWORD *)a2 + 22);
        if ( (v163 & 0x100) != 0 )
        {
          v98 = *(_OWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3248LL) + 128LL)
                          + 4024LL * *((unsigned int *)a2 + 4)
                          + 628);
          *(_QWORD *)v331 = &v358;
          v358 = v98;
        }
        else
        {
          *(_QWORD *)v331 = 0;
        }
        if ( (v163 & 1) != 0 )
        {
          v99 = 0;
          if ( (v163 & 0x80u) != 0 )
          {
            v274 = *((_DWORD *)a2 + 13);
            if ( v274 < 0 )
              v274 = 0;
            v355.SrcRect.top = v274;
            v275 = *((_DWORD *)a2 + 12);
            if ( v275 < 0 )
              v275 = 0;
            v355.SrcRect.left = v275;
            v276 = *((_DWORD *)a2 + 15);
            if ( (int)v322 < v276 )
              v276 = v322;
            v355.SrcRect.bottom = v276;
            v100 = *((_DWORD *)a2 + 14);
            if ( (int)v320 < v100 )
              v100 = v320;
          }
          else
          {
            v355.SrcRect.bottom = v322;
            v100 = v320;
            *(_QWORD *)&v355.SrcRect.left = 0;
          }
          v355.SrcRect.right = v100;
          v355.DstRect = v355.SrcRect;
          v355.Flags.Value = v355.Flags.Value & 0xFFFFF7FF | (*((_DWORD *)a2 + 22) >> 9) & 0x800;
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
          v102 = 0;
          v103 = 0;
          v355.SubRectCnt = 0;
          v355.pDstSubRects = DdiSubRectList;
          if ( !*((_DWORD *)a2 + 16) )
            goto LABEL_174;
          while ( 1 )
          {
            if ( DXGPRESENT::IntersectRect(
                   &DdiSubRectList[v102],
                   (const struct tagRECT *)(*((_QWORD *)a2 + 9) + 16LL * v103),
                   &v355.SrcRect) )
            {
              v102 = ++v355.SubRectCnt;
            }
            else
            {
              v102 = v355.SubRectCnt;
            }
            if ( ++v103 >= *((_DWORD *)a2 + 16) )
              break;
            DdiSubRectList = (struct tagRECT *)v355.pDstSubRects;
          }
          if ( !(_DWORD)v102 )
            goto LABEL_174;
          if ( DXGPRESENT::PrepareStagingBuffer(
                 *((DXGPRESENT **)v7 + 19),
                 *((struct DXGDEVICE **)v7 + 2),
                 *((_DWORD *)a2 + 5),
                 v61,
                 &v319) < 0 )
            goto LABEL_266;
          if ( !*((_BYTE *)v7 + 434) )
          {
            v145 = v319;
            if ( !v319 )
            {
              WdLogSingleEntry0(1);
              WdLogGlobalForLineNumber = 5913;
              DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"hDestinationAllocation", 5913, 0, 0, 0, 0);
              v145 = v319;
            }
            if ( !bTracingEnabled )
              goto LABEL_271;
            VIDMM_EXPORT::VidMmETWAllocationHandle(
              *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
              *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 768LL),
              v145);
            VIDMM_EXPORT::VidMmETWAllocationHandle(
              *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
              *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 768LL),
              v325);
            v188 = v355.pDstSubRects;
            v189 = v355.SubRectCnt;
            *(_QWORD *)v328 = *((_QWORD *)v7 + 45);
            if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x20) != 0 )
              McTemplateK0ppxppttqddddddddq_EtwWriteTransfer(
                (unsigned int)&DxgkControlGuid_Context,
                (unsigned int)EventBlit,
                0,
                *((_QWORD *)a2 + 1),
                v328[0]);
            v190 = 0;
            if ( !v189 )
            {
LABEL_343:
              v145 = v319;
              v99 = 0;
              v61 = a3;
              v318 = 1;
LABEL_271:
              v146 = DXGCONTEXT::SubmitPresent(
                       v7,
                       (const struct _D3DKMT_PRESENT *)a2,
                       *((struct DXGHWQUEUE ***)a2 + 188),
                       *((_DWORD *)a2 + 23),
                       v335,
                       v317,
                       v325,
                       v145,
                       &v355,
                       0,
                       *((struct VIDMM_DMA_BUFFER **)v7 + 45),
                       v330,
                       Format,
                       v61);
              *((_QWORD *)v7 + 45) = 0;
              goto LABEL_272;
            }
            v191 = v328[0];
            while ( 1 )
            {
              v192 = 0;
              v193 = v189 - v190;
              if ( v189 - v190 > 0x10 )
                break;
              v194 = v189 - v190;
              if ( v193 )
                goto LABEL_338;
LABEL_339:
              if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x40) != 0 )
                McTemplateK0ptqDR2DR2DR2DR2_EtwWriteTransfer(
                  (unsigned int)&DxgkControlGuid_Context,
                  (unsigned int)EventBlitRect,
                  0,
                  v191,
                  v193 <= 0x10,
                  v194,
                  (__int64)v370,
                  (__int64)v369,
                  (__int64)v368,
                  (__int64)v367);
              v190 += 16;
              if ( v190 >= v189 )
              {
                v7 = v337;
                goto LABEL_343;
              }
            }
            v194 = 16;
            do
            {
LABEL_338:
              v370[v192] = v188[(unsigned int)v192 + v190].left;
              v369[v192] = v188[(unsigned int)v192 + v190].right;
              v368[v192] = v188[(unsigned int)v192 + v190].top;
              v367[v192] = v188[(unsigned int)v192 + v190].bottom;
              v192 = (unsigned int)(v192 + 1);
            }
            while ( (unsigned int)v192 < v194 );
            goto LABEL_339;
          }
          v173 = DXGPROCESS::GetCurrent();
          v174 = v319;
          v175 = v173;
          DXGPUSHLOCK::AcquireShared((struct DXGPROCESS *)((char *)v173 + 248));
          v176 = (v174 >> 6) & 0xFFFFFF;
          if ( (unsigned int)v176 < *((_DWORD *)v175 + 74) )
          {
            v177 = *((_QWORD *)v175 + 35);
            v178 = *(_DWORD *)(v177 + 16 * v176 + 8);
            if ( ((v174 >> 25) & 0x60) == (v178 & 0x60) && (v178 & 0x2000) == 0 && (v178 & 0x1F) != 0 )
            {
              if ( (*(_BYTE *)(v177 + 16 * (((unsigned __int64)v174 >> 6) & 0xFFFFFF) + 8) & 0x1F) == 5 )
              {
                v179 = *(struct DXGALLOCATION **)(v177 + 16 * (((unsigned __int64)v174 >> 6) & 0xFFFFFF));
                goto LABEL_325;
              }
              WdLogSingleEntry0(2);
              WdLogGlobalForLineNumber = 318;
              DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
            }
          }
          v179 = 0;
LABEL_325:
          DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v336, v179);
          _InterlockedDecrement((volatile signed __int32 *)v175 + 66);
          ExReleasePushLockSharedEx((char *)v175 + 248, 0);
          KeLeaveCriticalRegion();
          v180 = v336;
          if ( !v336 )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 5898;
            DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"AllocRef.m_pAllocation != NULL", 5898, 0, 0, 0, 0);
            v180 = v336;
          }
          v181 = *(_DWORD *)(v180 + 20);
          v182 = (unsigned __int8 *)*((_QWORD *)a2 + 185);
          v183 = *((_DWORD *)a2 + 368);
          v184 = *(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL);
          v328[0] = *((_DWORD *)v317 + 5);
          v185 = (struct DXGHWQUEUE **)*((_QWORD *)a2 + 188);
          v186 = *(_QWORD *)(v184 + 16);
          if ( v185 )
            v187 = *v185;
          else
            v187 = 0;
          v277 = DXGPROCESS::GetCurrent();
          v146 = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendBlt(
                   (DXG_GUEST_VIRTUALGPU_VMBUS *)(v186 + 4792),
                   v277,
                   v7,
                   v187,
                   v328[0],
                   v181,
                   &v355.SrcRect,
                   &v355.DstRect,
                   v355.SubRectCnt,
                   v355.pDstSubRects,
                   v183,
                   v182);
          DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v336);
          v61 = a3;
          v99 = 0;
LABEL_272:
          if ( v146 < 0 )
          {
LABEL_266:
            WdLogSingleEntry2(3, -1071775738, v7);
            WdLogGlobalForLineNumber = 6095;
            v24 = -1071775738;
            goto LABEL_174;
          }
          v147 = (DXGDEVICE *)*((_QWORD *)v7 + 2);
          if ( (*((_DWORD *)a2 + 22) & 0x100) != 0
            && ADAPTER_DISPLAY::IsVidPnSourceOwner(
                 *(ADAPTER_DISPLAY **)(*((_QWORD *)v147 + 237) + 3248LL),
                 *((const struct DXGDEVICE **)v7 + 2),
                 *((_DWORD *)a2 + 4)) )
          {
            v99 = 1;
          }
          else if ( !DXGDEVICE::AllowLegacyPresent(v147, 0) )
          {
            v148 = 0;
            v99 = 0;
LABEL_276:
            DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v326);
            COREDEVICEACCESS::Release(v61);
            if ( !v148 && DXGPRESENT::CheckOcclusion(*((DXGPRESENT **)v7 + 19)) )
            {
              COREDEVICEACCESS::AcquireSharedUncheck(v61, 0);
              v24 = -1071775738;
              goto LABEL_174;
            }
            v149 = v323;
            CWin32kLocks::Unlock(v323);
            v150 = v326;
            DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v326);
            v24 = COREDEVICEACCESS::AcquireShared(v61, 0);
            if ( v24 >= 0 )
            {
              memset(&v350, 0, sizeof(v350));
              if ( *((_BYTE *)v7 + 434) )
              {
                memset(&v348, 0, sizeof(v348));
                v348.hAllocation = v319;
                v151 = (struct DXGDEVICE *)*((_QWORD *)v7 + 2);
                v152 = *(_QWORD *)(*((_QWORD *)v151 + 2) + 16LL);
                v153 = DXGPROCESS::GetCurrent();
                v154 = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendLock2(
                         (DXG_GUEST_VIRTUALGPU_VMBUS *)(v152 + 4792),
                         v153,
                         v151,
                         &v348,
                         0,
                         0,
                         0);
                v61 = a3;
                v24 = v154;
                v150 = v326;
                v350.pData = v348.pData;
              }
              else
              {
                v278 = v319;
                if ( !v319 )
                {
                  WdLogSingleEntry0(1);
                  WdLogGlobalForLineNumber = 5991;
                  DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"hDestinationAllocation", 5991, 0, 0, 0, 0);
                  v278 = v319;
                }
                v350.hAllocation = v278;
                v24 = DXGDEVICE::Lock(*((DXGDEVICE **)v7 + 2), &v350, v61, 0);
              }
              if ( v24 < 0 )
                goto LABEL_174;
              DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v150);
              COREDEVICEACCESS::Release(v61);
              if ( !v350.pData )
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
              v155 = v329;
              v156 = (*((__int64 (__fastcall **)(_QWORD))v329 + 40))(0);
              v24 = CWin32kLocks::Lock(v149, *((HWND *)a2 + 1), 0, 0, v99 & (unsigned int)-(v156 != 0));
              if ( v24 >= 0 )
              {
                v161 = (unsigned int (__fastcall *)(const struct DXGK_PRESENT_PARAMS *, HDC, _QWORD, const RECT *))*((_QWORD *)v155 + 18);
                v162 = CWin32kLocks::hDestDc(v323);
                pData = (char)v350.pData;
                if ( !v161(a2, v162, *(_QWORD *)v331, v355.pDstSubRects) )
                {
                  v24 = -1071775737;
                  WdLogSingleEntry2(4, -1071775737, v7);
                  WdLogGlobalForLineNumber = 6016;
                }
                v149 = v323;
                v61 = a3;
              }
              v157 = v326;
              DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v326);
              v90 = COREDEVICEACCESS::AcquireShared(v61, 0);
              if ( v90 >= 0 )
              {
                if ( *((_BYTE *)v7 + 434) )
                {
                  v343.hDevice = 0;
                  v343.hAllocation = v319;
                  v158 = (struct DXGDEVICE *)*((_QWORD *)v7 + 2);
                  v159 = *(_QWORD *)(*((_QWORD *)v158 + 2) + 16LL);
                  v160 = DXGPROCESS::GetCurrent();
                  DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendUnlock2(
                    (DXG_GUEST_VIRTUALGPU_VMBUS *)(v159 + 4792),
                    v160,
                    v158,
                    &v343,
                    0);
                  v61 = a3;
                }
                else
                {
                  v344.hDevice = 0;
                  v344.NumAllocations = 1;
                  v344.phAllocations = &v350.hAllocation;
                  DXGDEVICE::Unlock(*((DXGDEVICE **)v7 + 2), &v344, 0);
                }
                if ( v24 >= 0 && (*((_DWORD *)a2 + 22) & 0x10000) != 0 )
                {
                  *((_DWORD *)a2 + 90) = 3;
                  *((_QWORD *)a2 + 48) = *(_QWORD *)(*((_QWORD *)v7 + 19) + 440LL);
                  *((_DWORD *)a2 + 100) = 0;
                  *((_DWORD *)a2 + 91) = 48;
                  DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v334);
                  v24 = SubmitPresentHistoryToken(
                          (struct _D3DKMT_PRESENTHISTORYTOKEN *)((char *)a2 + 360),
                          v61,
                          v157,
                          v149,
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
              v271 = v61;
              goto LABEL_565;
            }
            goto LABEL_476;
          }
          v148 = 1;
          goto LABEL_276;
        }
        if ( (v163 & 2) == 0 )
          goto LABEL_174;
        v279 = (DXGDEVICE *)*((_QWORD *)v7 + 2);
        if ( (v163 & 0x100) != 0
          && ADAPTER_DISPLAY::IsVidPnSourceOwner(
               *(ADAPTER_DISPLAY **)(*((_QWORD *)v279 + 237) + 3248LL),
               *((const struct DXGDEVICE **)v7 + 2),
               *((_DWORD *)a2 + 4)) )
        {
          v280 = 1;
        }
        else
        {
          v280 = 0;
          v281 = DXGDEVICE::AllowLegacyPresent(v279, 0);
          v282 = 0;
          if ( !v281 )
            goto LABEL_607;
        }
        v282 = 1;
LABEL_607:
        DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v326);
        COREDEVICEACCESS::Release(a3);
        if ( v282 || !DXGPRESENT::CheckOcclusion(*((DXGPRESENT **)v7 + 19)) )
        {
          if ( (*((_DWORD *)a2 + 22) & 0x10000) != 0 )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 6125;
            DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"!pPresent->Flags.RedirectedBlt", 6125, 0, 0, 0, 0);
          }
          CWin32kLocks::Unlock(v68);
          v283 = v329;
          v284 = (*((__int64 (__fastcall **)(_QWORD))v329 + 40))(0);
          v285 = CWin32kLocks::Lock(v68, *((HWND *)a2 + 1), 0, 0, v280 & (unsigned int)-(v284 != 0));
          v286 = (unsigned int (__fastcall *)(HDC, _QWORD, __int64, _QWORD))*((_QWORD *)v283 + 19);
          v24 = v285;
          LODWORD(v283) = *((_DWORD *)a2 + 7);
          v287 = *((_DWORD *)a2 + 16);
          v288 = *((_QWORD *)a2 + 9);
          v289 = CWin32kLocks::hDestDc(v323);
          pData = (char)v283;
          if ( !v286(v289, *(_QWORD *)v331, v288, v287) )
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
        DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v326);
        v61 = a3;
        v290 = COREDEVICEACCESS::AcquireShared(a3, 0);
        v90 = v290;
        if ( v290 >= 0 )
          goto LABEL_175;
        WdLogSingleEntry2(4, v290, v7);
        WdLogGlobalForLineNumber = 6144;
        goto LABEL_600;
      }
      *(_QWORD *)(v73 + 56) = *(_QWORD *)v328;
      if ( (*((_DWORD *)a2 + 22) & 0x10000) == 0 )
      {
        *(_DWORD *)(*((_QWORD *)v7 + 19) + 8LL) = v65;
        DXGDEVICE::FlushScheduler(*((_QWORD *)v7 + 2), 2, 4294967293LL, 0, pData);
        v272 = 0;
        v273 = *(_DWORD *)(*((_QWORD *)v7 + 19) + 8LL);
        if ( v273 != (*((unsigned int (**)(void))v329 + 1))() )
        {
          *(_DWORD *)(*((_QWORD *)v7 + 19) + 8LL) = v65;
          ADAPTER_RENDER::FlushScheduler(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL), 3, 0xFFFFFFFFLL);
          v272 = 1;
        }
        DXGDEVICE::SynchronizePresentToPrimary(*((DXGDEVICE **)v7 + 2), v7, (struct DXGPRESENTMUTEX *)v334, v272);
      }
      v61 = a3;
LABEL_571:
      v68 = v323;
      goto LABEL_115;
    }
LABEL_476:
    COREDEVICEACCESS::AcquireSharedUncheck(v61, 0);
LABEL_477:
    v246 = (DXGPRESENTMUTEX *)v334;
    goto LABEL_478;
  }
  if ( !v21 )
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
              v20 = v317;
LABEL_45:
              DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v341, v20);
              DXGALLOCATIONREFERENCE::MoveAssign(&v333, v341);
              DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v341);
              v332 = *((_DWORD *)a2 + 5);
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
              v35 = *(_DWORD *)(*((_QWORD *)v317 + 6) + 4LL);
              if ( (v35 & 0x2000) != 0 && (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 40LL) + 408LL) & 4) == 0 )
              {
                v24 = -1073741811;
                WdLogSingleEntry5(2, -1073741811, v7);
                WdLogGlobalForLineNumber = 4784;
                v77 = L"0x%I64x 0x%I64x DirectFlip Presents are only supported from the DWM process 0x%I64x 0x%I64x 0x%I64x";
                v312 = *((unsigned int *)a2 + 5);
                v310 = *((_QWORD *)v317 + 6);
                v308 = (__int64)v317;
                v306 = (__int64)v7;
                v304 = -1073741811;
                goto LABEL_120;
              }
              v36 = *((_DWORD *)a2 + 22);
              if ( (v36 & 0x40000) == 0 && (v36 & 0x20000) == 0 )
                goto LABEL_51;
              if ( (v36 & 0x20000) != 0 && (v36 & 0x40000) != 0 )
              {
                WdLogSingleEntry0(2);
                v233 = 4795;
                v229 = L"FlipStereoTemporaryMono and FlipStereo cannot be set together. STATUS_INVALID_PARAMETER";
              }
              else if ( (v35 & 0x1000) != 0 )
              {
                v234 = *((_DWORD *)ADAPTER_DISPLAY::GetDisplayModeInfo(
                                     *(ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3248LL),
                                     v33)
                       + 10);
                if ( (v234 & 0x10) == 0 )
                {
                  WdLogSingleEntry0(3);
                  WdLogGlobalForLineNumber = 4808;
                  goto LABEL_452;
                }
                v235 = *((_DWORD *)a2 + 22);
                if ( (v234 & 0x20) == 0 && (v235 & 0x40000) != 0 )
                {
                  WdLogSingleEntry0(3);
                  WdLogGlobalForLineNumber = 4814;
                  goto LABEL_452;
                }
                if ( (v235 & 0xC0000) != 0xC0000 )
                {
LABEL_51:
                  IsFullWDDMDevice = DXGDEVICE::IsFullWDDMDevice(*((DXGDEVICE **)v7 + 2), v33);
                  v38 = v330;
                  if ( !IsFullWDDMDevice )
                  {
                    v26 = a3;
                    goto LABEL_53;
                  }
                  v128 = *(_DWORD *)v330 ^ (*((_DWORD *)a2 + 22) ^ *(_DWORD *)v330) & 4;
                  *(_DWORD *)v330 = v128;
                  v129 = v128 ^ (*((_DWORD *)a2 + 22) ^ v128) & 8;
                  *(_DWORD *)v38 = v129;
                  v130 = v129 ^ ((unsigned __int8)v129 ^ (unsigned __int8)(*((_DWORD *)a2 + 22) >> 1)) & 0x10;
                  *(_DWORD *)v38 = v130;
                  v131 = v130 ^ (v130 ^ (4 * *((_DWORD *)a2 + 22))) & 0x80000;
                  *(_DWORD *)v38 = v131;
                  v132 = v131 ^ (v131 ^ (4 * *((_DWORD *)a2 + 22))) & 0x100000;
                  *(_DWORD *)v38 = v132;
                  v133 = v132 ^ (v132 ^ (4 * *((_DWORD *)a2 + 22))) & 0x200000;
                  *(_DWORD *)v38 = v133;
                  if ( (*((_DWORD *)a2 + 22) & 0x8000000) != 0 )
                    v134 = *((_DWORD *)a2 + 363);
                  else
                    v134 = 0;
                  *((_DWORD *)v38 + 36) = v134;
                  *((_DWORD *)v38 + 38) = 1;
                  *(_DWORD *)v38 = v133 ^ (*((_DWORD *)a2 + 22) ^ v133) & 0x20000000;
                  v135 = *((_DWORD *)a2 + 22) >> 9;
                  v136 = *((_DWORD *)a2 + 22) & 4 | v355.Flags.Value & 0xFFFFFFFB;
                  v137 = v136
                       ^ ((unsigned __int16)v136
                        ^ (unsigned __int16)v135)
                       & 0x100
                       ^ ((unsigned __int16)v135
                        ^ (unsigned __int16)(v136 ^ (v136 ^ v135) & 0x100))
                       & 0x200;
                  v355.Flags.Value = v137 ^ (v135 ^ v137) & 0x400;
                  v138 = *((_QWORD *)a2 + 180);
                  if ( v138
                    && !*(_DWORD *)(v138 + 16)
                    && (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 40LL) + 408LL) & 4) != 0 )
                  {
                    v355.SubRectCnt = *(_DWORD *)v138;
                    v355.pDstSubRects = *(const RECT **)(v138 + 8);
                  }
                  v139 = (D3DDDI_FLIPINTERVAL_TYPE *)((char *)a2 + 84);
                  DeviceFlipMode = VIDSCH_EXPORT::VidSchGetDeviceFlipMode(
                                     *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 736LL),
                                     *(_QWORD *)(*((_QWORD *)v7 + 2) + 800LL),
                                     v33,
                                     (char *)a2 + 84);
                  *((_DWORD *)v38 + 30) = DeviceFlipMode;
                  if ( !DeviceFlipMode )
                  {
                    v24 = -1073741811;
                    WdLogSingleEntry3(3, v7, *(int *)v139, -1073741811);
                    WdLogGlobalForLineNumber = 4867;
                    goto LABEL_34;
                  }
                  if ( ((DeviceFlipMode - 1) & 0xFFFFFFFD) != 0 )
                  {
                    v355.FlipInterval = *v139;
                    if ( DeviceFlipMode == 2 )
                    {
LABEL_255:
                      *((D3DDDI_FLIPINTERVAL_TYPE *)v38 + 31) = *v139;
                      *((_DWORD *)v38 + 29) = v33;
                      DisplayedPrimary = DXGDEVICE::GetDisplayedPrimary(*((DXGDEVICE **)v7 + 2), v33);
                      if ( DisplayedPrimary )
                      {
                        v142 = *((_QWORD *)DisplayedPrimary + 6);
                        if ( _bittest((const signed __int32 *)(*((_QWORD *)v317 + 6) + 4LL), 0xDu) )
                        {
                          if ( !_bittest((const signed __int32 *)(v142 + 4), 0xDu) )
                            goto LABEL_258;
                        }
                        else if ( _bittest((const signed __int32 *)(v142 + 4), 0xDu) )
                        {
LABEL_258:
                          *(_DWORD *)v38 |= 0x400000u;
                          goto LABEL_259;
                        }
                      }
                      *(_DWORD *)v38 &= ~0x400000u;
LABEL_259:
                      v143 = *((_DWORD *)v38 + 30);
                      if ( !v143 || (v144 = *((_QWORD *)v7 + 2), v143 == *(_DWORD *)(v144 + 4LL * v33 + 1832)) )
                      {
                        v26 = a3;
LABEL_262:
                        v18 = v320;
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
                              v237 = DXGDEVICE::IsFullWDDMDevice(*((DXGDEVICE **)v7 + 2), v33);
                              v238 = (DXGDEVICE *)*((_QWORD *)v7 + 2);
                              v239 = v33;
                              if ( v237 )
                              {
                                DXGDEVICE::ClearDisplayedAllMultiPlaneOverlaysUnsafe(v238, v33);
                                DXGDEVICE::SetDisplayedPrimary(
                                  *((DXGDEVICE **)v7 + 2),
                                  v33,
                                  v317,
                                  *((_DWORD *)v38 + 34),
                                  1u);
                                v240 = *((_DWORD *)v38 + 30);
LABEL_498:
                                *(_DWORD *)(*((_QWORD *)v7 + 2) + 4LL * v33 + 1832) = v240;
                                goto LABEL_500;
                              }
LABEL_499:
                              DXGDEVICE::SetDisplayedPrimary(v238, v239, v317, 0, 1u);
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
                                           v322),
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
                              WdLogSingleEntry5(3, -1071775739, v7);
                              WdLogGlobalForLineNumber = 5066;
                              goto LABEL_452;
                            }
LABEL_57:
                            if ( !DXGDEVICE::IsFullWDDMDevice(*((DXGDEVICE **)v7 + 2), v33) )
                            {
                              v39 = *((_QWORD *)v7 + 2);
                              if ( !*(_QWORD *)(v39 + 1896) )
                              {
                                WdLogSingleEntry2(1, v39, -1073741822);
                                v313 = 0;
                                v229 = L"DxgkPresent is called for flip on a render only device 0x%I64x, returning 0x%I64x.";
                                v311 = 0;
                                v232 = 262146;
                                v309 = 0;
                                WdLogGlobalForLineNumber = 5377;
                                v307 = -1073741822;
                                v305 = (struct _DXGKARG_PRESENT *)*((_QWORD *)v7 + 2);
                                goto LABEL_442;
                              }
                              *(_QWORD *)&v356.right = 0;
                              *(_QWORD *)&v356.left = 0;
                              v40 = *((_DWORD *)a2 + 22);
                              if ( (v40 & 0x10000000) != 0 )
                              {
                                v356.right = *((_DWORD *)a2 + 379);
                                v41 = *((_DWORD *)a2 + 380);
                                goto LABEL_61;
                              }
                              v259 = v324;
                              if ( (v40 & 4) != 0 )
                                v259 = v317;
                              v260 = *(_DWORD *)(*((_QWORD *)v259 + 6) + 4LL);
                              if ( (v260 & 0x10) != 0 )
                              {
                                WdLogSingleEntry3(4, -1071775482, v7, v259);
                                WdLogGlobalForLineNumber = 5297;
                                v24 = -1071775482;
                                goto LABEL_34;
                              }
                              v261 = *(_OWORD *)ADAPTER_DISPLAY::GetDisplayModeInfo(
                                                  *(ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL)
                                                                      + 3248LL),
                                                  (v260 >> 6) & 0xF);
                              v345.Flags.Value = 1;
                              memset(&v345, 0, 40);
                              v345.Rotation = -1;
                              v262 = *((_QWORD *)v259 + 6);
                              *(_OWORD *)v352 = v261;
                              v345.hAllocation = *(HANDLE *)(v262 + 16);
                              v263 = ADAPTER_RENDER::DdiDescribeAllocation(
                                       *(ADAPTER_RENDER **)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 16LL)
                                                          + 3256LL),
                                       &v345);
                              if ( v263 >= 0 )
                              {
                                v264 = v345.Width;
                                if ( v345.Width != v352[0] || (v41 = v345.Height, v345.Height != v352[1]) )
                                {
                                  WdLogSingleEntry3(4, -1071775482, v7, v259);
                                  WdLogGlobalForLineNumber = 5328;
                                  goto LABEL_452;
                                }
                                if ( *((_BYTE *)v7 + 434) )
                                  goto LABEL_527;
                                v265 = RemoveAlphaChannel(v352[2]);
                                if ( RemoveAlphaChannel(v345.Format) == v265 )
                                {
                                  v41 = v345.Height;
                                  v264 = v345.Width;
LABEL_527:
                                  v356.right = v264;
LABEL_61:
                                  v356.bottom = v41;
                                  v24 = ADAPTER_DISPLAY::PresentDisplayOnly(
                                          *(ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3248LL),
                                          v7,
                                          v33,
                                          (const struct _D3DKMT_PRESENT *)a2,
                                          &v355,
                                          v26,
                                          &v356);
                                  if ( v24 >= 0 )
                                  {
                                    if ( (*((_DWORD *)a2 + 22) & 4) == 0 )
                                    {
LABEL_63:
                                      v23 = 2;
                                      goto LABEL_30;
                                    }
                                    DXGDEVICE::ClearDisplayedAllMultiPlaneOverlaysUnsafe(*((DXGDEVICE **)v7 + 2), v33);
                                    DXGDEVICE::SetDisplayedPrimary(*((DXGDEVICE **)v7 + 2), v33, v317, 0, 1u);
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
                                WdLogSingleEntry3(4, -1071775482, v7, v259);
                                WdLogGlobalForLineNumber = 5342;
LABEL_452:
                                v24 = -1071775739;
                                goto LABEL_34;
                              }
                              v231 = (struct _DXGKARG_PRESENT *)v263;
                              WdLogSingleEntry5(2, v263, v7);
                              WdLogGlobalForLineNumber = 5319;
                              v229 = L"ret = 0x%I64x Device 0x%I64x: DdiDescribeAllocation failed 0x%I64x 0x%I64x 0x%I64x";
                              v313 = (*(_DWORD *)(*((_QWORD *)v259 + 6) + 4LL) >> 6) & 0xF;
                              v311 = (__int64)v259;
                              v309 = *((unsigned int *)v259 + 4);
                              v307 = (__int64)v7;
                              v305 = v231;
LABEL_438:
                              v232 = 0x40000;
LABEL_442:
                              DxgkLogInternalTriageEvent(
                                0,
                                v232,
                                -1,
                                (_DWORD)v229,
                                (__int64)v305,
                                v307,
                                v309,
                                v311,
                                v313);
                              goto LABEL_416;
                            }
                            v126 = DXGCONTEXT::WaitForQueuedPresentLimit(
                                     v7,
                                     v33,
                                     (*((_DWORD *)a2 + 22) & 0x10) == 0,
                                     v26);
                            v24 = v126;
                            if ( v126 < 0 )
                            {
                              WdLogSingleEntry2(4, v126, v7);
                              WdLogGlobalForLineNumber = 5081;
                              goto LABEL_34;
                            }
                            v127 = v330;
                            if ( ((*((_DWORD *)v330 + 30) - 3) & 0xFFFFFFFD) != 0 )
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
                                if ( v317 )
                                {
                                  v252 = *((_QWORD *)v317 + 6);
                                  if ( v252 )
                                  {
                                    if ( (*(_DWORD *)(v252 + 4) & 0x2000) != 0 )
                                    {
                                      if ( !DXGDEVICE::IsDirectFlipAllocationRequestedPinned(
                                              *((DXGDEVICE **)v7 + 2),
                                              v317) )
                                      {
                                        WdLogSingleEntry3(4, -1071775739, v7, v317);
                                        WdLogGlobalForLineNumber = 5151;
                                        goto LABEL_509;
                                      }
                                      if ( !VIDMM_EXPORT::VidMmIsAllocationPinned(
                                              *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                                              *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 768LL),
                                              *((struct VIDMM_MULTI_ALLOC **)v317 + 3)) )
                                      {
                                        v253 = VIDMM_EXPORT::VidMmPinAllocation(
                                                 *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                                                 *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL)
                                                                         + 768LL),
                                                 *((struct VIDMM_MULTI_ALLOC **)v317 + 3),
                                                 0,
                                                 0);
                                        if ( v253 < 0 )
                                        {
                                          WdLogSingleEntry3(4, v317, *((_QWORD *)v317 + 6), v253);
                                          WdLogGlobalForLineNumber = 5176;
LABEL_509:
                                          v254 = (struct VIDMM_DMA_BUFFER *)*((_QWORD *)v7 + 45);
                                          if ( v254 )
                                          {
                                            VIDMM_EXPORT::VidMmReleaseDmaBuffer(
                                              *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                                              v254);
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
                                v255 = ADAPTER_DISPLAY::GetCurrentOrientation(
                                         *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3248LL),
                                         v33,
                                         1);
                                v355.Flags.Value = (v255 != 1 ? 0x80 : 0) | v355.Flags.Value & 0xFFFFFF7F;
                              }
                              if ( !bTracingEnabled )
                              {
LABEL_241:
                                v24 = DXGCONTEXT::SubmitPresent(
                                        v7,
                                        (const struct _D3DKMT_PRESENT *)a2,
                                        *((struct DXGHWQUEUE ***)a2 + 188),
                                        *((_DWORD *)a2 + 23),
                                        v335,
                                        v317,
                                        v325,
                                        v319,
                                        &v355,
                                        *((struct _D3DKMT_PRESENT_RGNS **)a2 + 180),
                                        *((struct VIDMM_DMA_BUFFER **)v7 + 45),
                                        v127,
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
                                  v317,
                                  *((_DWORD *)v127 + 34),
                                  1u);
                                *(_DWORD *)(*((_QWORD *)v7 + 2) + 4LL * v33 + 1832) = *((_DWORD *)v127 + 30);
                                goto LABEL_516;
                              }
                              v256 = *(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL);
                              v257 = *(struct VIDMM_GLOBAL **)(v256 + 768);
                              v258 = *(VIDMM_EXPORT **)(v256 + 760);
                              if ( (*((_DWORD *)a2 + 22) & 4) != 0 )
                              {
                                v164 = (unsigned __int8)VIDMM_EXPORT::VidMmETWAllocationHandle(v258, v257, v325);
                                if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x80u) != 0LL )
                                  McTemplateK0pqpqtt_EtwWriteTransfer(
                                    (unsigned int)&DxgkControlGuid_Context,
                                    (unsigned int)EventFlip,
                                    0,
                                    *((_QWORD *)v7 + 45),
                                    v33,
                                    v164,
                                    v355.FlipInterval,
                                    (*(_BYTE *)&v355.Flags.0 & 8) != 0,
                                    *((_QWORD *)v7 + 45) == 0);
                                goto LABEL_241;
                              }
                              VIDMM_EXPORT::VidMmETWAllocationHandle(v258, v257, v319);
                              v165 = (CWin32kLocks *)VIDMM_EXPORT::VidMmETWAllocationHandle(
                                                       *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                                                       *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL)
                                                                               + 768LL),
                                                       v325);
                              v166 = v355.pDstSubRects;
                              v167 = v355.SubRectCnt;
                              v323 = v165;
                              v329 = (const struct _DXGKWIN32KENG_INTERFACE *)*((_QWORD *)v7 + 45);
                              if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x20) != 0 )
                                McTemplateK0ppxppttqddddddddq_EtwWriteTransfer(
                                  (unsigned int)&DxgkControlGuid_Context,
                                  (unsigned int)EventBlit,
                                  0,
                                  *((_QWORD *)a2 + 1),
                                  (char)v329);
                              v168 = 0;
                              if ( !v167 )
                              {
LABEL_315:
                                v127 = v330;
                                v26 = a3;
                                goto LABEL_241;
                              }
                              v169 = (int)v329;
                              while ( 1 )
                              {
                                v170 = 0;
                                v171 = v167 - v168;
                                if ( v167 - v168 > 0x10 )
                                  break;
                                v172 = v167 - v168;
                                if ( v171 )
                                  goto LABEL_310;
LABEL_311:
                                if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x40) != 0 )
                                  McTemplateK0ptqDR2DR2DR2DR2_EtwWriteTransfer(
                                    (unsigned int)&DxgkControlGuid_Context,
                                    (unsigned int)EventBlitRect,
                                    0,
                                    v169,
                                    v171 <= 0x10,
                                    v172,
                                    (__int64)v366,
                                    (__int64)v365,
                                    (__int64)v371,
                                    (__int64)v364);
                                v168 += 16;
                                if ( v168 >= v167 )
                                {
                                  v7 = v337;
                                  goto LABEL_315;
                                }
                              }
                              v172 = 16;
                              do
                              {
LABEL_310:
                                v366[v170] = v166[(unsigned int)v170 + v168].left;
                                v365[v170] = v166[(unsigned int)v170 + v168].right;
                                v371[v170] = v166[(unsigned int)v170 + v168].top;
                                v364[v170] = v166[(unsigned int)v170 + v168].bottom;
                                v170 = (unsigned int)(v170 + 1);
                              }
                              while ( (unsigned int)v170 < v172 );
                              goto LABEL_311;
                            }
                            v250 = (struct VIDMM_DMA_BUFFER *)*((_QWORD *)v7 + 45);
                            if ( v250 )
                            {
                              VIDMM_EXPORT::VidMmReleaseDmaBuffer(
                                *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                                v250);
                              *((_QWORD *)v7 + 45) = 0;
                            }
                            if ( v24 != -1071774920 )
                              goto LABEL_31;
                            if ( (*((_DWORD *)a2 + 22) & 4) != 0 )
                            {
                              v251 = DXGDEVICE::IsFullWDDMDevice(*((DXGDEVICE **)v7 + 2), v33);
                              v238 = (DXGDEVICE *)*((_QWORD *)v7 + 2);
                              v239 = v33;
                              if ( v251 )
                              {
                                DXGDEVICE::ClearDisplayedAllMultiPlaneOverlaysUnsafe(v238, v33);
                                DXGDEVICE::SetDisplayedPrimary(
                                  *((DXGDEVICE **)v7 + 2),
                                  v33,
                                  v317,
                                  *((_DWORD *)v127 + 34),
                                  1u);
                                v240 = *((_DWORD *)v127 + 30);
                                goto LABEL_498;
                              }
                              goto LABEL_499;
                            }
                            goto LABEL_500;
                          }
                          v241 = v329;
                          v242 = *(_DWORD *)(*((_QWORD *)v7 + 19) + 8LL);
                          v243 = (*((__int64 (**)(void))v329 + 1))();
                          v244 = *((_DWORD *)a2 + 22) & 4;
                          if ( v242 != v243 )
                          {
                            if ( !v244 )
                            {
                              DXGDEVICE::FlushScheduler(*((_QWORD *)v7 + 2), 2, 4294967293LL, 0, v303);
                              DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v326);
                              COREDEVICEACCESS::Release(v26);
                              DXGPRESENTMUTEX::DXGPRESENTMUTEX(
                                (DXGPRESENTMUTEX *)v349,
                                *(struct ADAPTER_RENDER *const *)(*((_QWORD *)v7 + 2) + 16LL));
                              DXGPRESENTMUTEX::Acquire((DXGPRESENTMUTEX *)v349);
                              DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v326);
                              v245 = COREDEVICEACCESS::AcquireShared(v26, 0);
                              v24 = v245;
                              if ( v245 < 0 )
                              {
                                WdLogSingleEntry2(4, v245, v7);
                                WdLogGlobalForLineNumber = 5016;
                                COREDEVICEACCESS::AcquireSharedUncheck(v26, 0);
                                v246 = (DXGPRESENTMUTEX *)v349;
                                goto LABEL_478;
                              }
                              DXGDEVICE::SynchronizePresentToPrimary(
                                *((DXGDEVICE **)v7 + 2),
                                v7,
                                (struct DXGPRESENTMUTEX *)v349,
                                1u);
                              DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v349);
                            }
                            v247 = *((_QWORD *)v7 + 19);
                            *(_DWORD *)(v247 + 8) = (*((__int64 (**)(void))v241 + 1))();
                            CddInterface = ADAPTER_DISPLAY::GetCddInterface(
                                             *(ADAPTER_DISPLAY **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 1896LL) + 3248LL),
                                             v33);
                            if ( CddInterface )
                              (*((void (__fastcall **)(_QWORD, _QWORD))CddInterface + 1))(*(_QWORD *)CddInterface, 0);
                            goto LABEL_57;
                          }
                          if ( v244 )
                            goto LABEL_57;
                          COREDEVICEACCESS::Release(v26);
                          DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v326);
                          DXGPRESENTMUTEX::DXGPRESENTMUTEX(
                            (DXGPRESENTMUTEX *)v347,
                            *(struct ADAPTER_RENDER *const *)(*((_QWORD *)v7 + 2) + 16LL));
                          DXGPRESENTMUTEX::Acquire((DXGPRESENTMUTEX *)v347);
                          DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v326);
                          v249 = COREDEVICEACCESS::AcquireShared(v26, 0);
                          v24 = v249;
                          if ( v249 >= 0 )
                          {
                            DXGDEVICE::SynchronizePresentToPrimary(
                              *((DXGDEVICE **)v7 + 2),
                              v7,
                              (struct DXGPRESENTMUTEX *)v347,
                              0);
                            DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v347);
                            goto LABEL_57;
                          }
                          WdLogSingleEntry2(4, v249, v7);
                          WdLogGlobalForLineNumber = 5049;
                          COREDEVICEACCESS::AcquireSharedUncheck(v26, 0);
                          v246 = (DXGPRESENTMUTEX *)v347;
LABEL_478:
                          DXGPRESENTMUTEX::Release(v246);
                          goto LABEL_34;
                        }
LABEL_408:
                        v24 = v28;
                        goto LABEL_34;
                      }
                      WdLogSingleEntry1(4, v144);
                      v26 = a3;
                      WdLogGlobalForLineNumber = 4923;
                      COREDEVICEACCESS::Release(a3);
                      DXGDEVICE::FlushScheduler(*((_QWORD *)v7 + 2), 3, 4294967293LL, 0, pData);
                      v236 = COREDEVICEACCESS::AcquireShared(a3, 0);
                      v24 = v236;
                      if ( v236 < 0 )
                      {
                        WdLogSingleEntry1(4, v236);
                        WdLogGlobalForLineNumber = 4931;
                        COREDEVICEACCESS::AcquireSharedUncheck(a3, 0);
                        goto LABEL_34;
                      }
LABEL_431:
                      v38 = v330;
                      goto LABEL_262;
                    }
                  }
                  else
                  {
                    v355.FlipInterval = D3DDDI_FLIPINTERVAL_IMMEDIATE;
                  }
                  v355.Flags.Value |= 8u;
                  goto LABEL_255;
                }
                WdLogSingleEntry0(2);
                v233 = 4820;
                v229 = L"FlipStereoTemporaryMono cannot be used with FlipStereoPreferRight. STATUS_INVALID_PARAMETER";
              }
              else
              {
                WdLogSingleEntry0(2);
                v233 = 4801;
                v229 = L"FlipStereoTemporaryMono and FlipStereo can only be used with stereo primary allocations. STATUS_I"
                        "NVALID_PARAMETER";
              }
              v313 = 0;
              v311 = 0;
              v232 = 0x40000;
              v309 = 0;
              v307 = 0;
              v305 = (struct _DXGKARG_PRESENT *)v233;
              WdLogGlobalForLineNumber = v233;
              goto LABEL_442;
            }
          }
        }
        WdLogSingleEntry1(2, *((unsigned int *)a2 + 4));
        WdLogGlobalForLineNumber = 4760;
        v229 = L"An invalid VidPn source ID was supplied to an indirect present (%I64d)";
        v230 = *((unsigned int *)a2 + 4);
      }
      else
      {
        WdLogSingleEntry0(2);
        v230 = 4735;
        v229 = L"Expecting indirect display presents to be a shared surface";
        WdLogGlobalForLineNumber = 4735;
      }
      v313 = 0;
      v311 = 0;
      v309 = 0;
      v307 = 0;
      v305 = (struct _DXGKARG_PRESENT *)v230;
      goto LABEL_438;
    }
    v79 = *(_DWORD *)(*((_QWORD *)v20 + 6) + 4LL);
    if ( (v79 & 0x2003) != 0 )
    {
      v33 = (v79 >> 6) & 0xF;
      goto LABEL_45;
    }
    v24 = -1073741811;
    WdLogSingleEntry5(2, -1073741811, v7);
    WdLogGlobalForLineNumber = 4745;
    v77 = L"0x%I64x 0x%I64x Source of Flip must be primary 0x%I64x 0x%I64x 0x%I64x";
    v312 = *((unsigned int *)a2 + 5);
    v310 = *((_QWORD *)v317 + 6);
    v308 = (__int64)v317;
    v306 = (__int64)v7;
    v304 = -1073741811;
LABEL_120:
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v77, v304, v306, v308, v310, v312);
    goto LABEL_34;
  }
LABEL_355:
  v197 = *((_QWORD *)a2 + 9);
  if ( !v197 || !*((_DWORD *)a2 + 16) || (v22 & 1) == 0 && (v22 & 2) == 0 || (v22 & 0x100E803C) != 0 )
  {
    v24 = -1073741811;
    WdLogSingleEntry5(3, v7, v197);
    WdLogGlobalForLineNumber = 4423;
    goto LABEL_34;
  }
  if ( (v22 & 2) != 0 )
  {
    if ( (v22 & 1) != 0 || (v22 & 0x100680) != 0 )
    {
      v24 = -1073741811;
      WdLogSingleEntry5(3, v7, v197);
      WdLogGlobalForLineNumber = 4438;
      goto LABEL_34;
    }
  }
  else
  {
    if ( !v18 || !Height || (v22 & 0x82) != 0x80 )
    {
      v24 = -1073741811;
      WdLogSingleEntry5(3, v7, v197);
      WdLogGlobalForLineNumber = 4452;
      goto LABEL_34;
    }
    if ( (v22 & 0x600) == 0x600 )
    {
      v24 = -1073741811;
      WdLogSingleEntry5(3, -1073741811, v7);
      WdLogGlobalForLineNumber = 4461;
      goto LABEL_34;
    }
  }
  v198 = *(_DWORD *)(*((_QWORD *)v324 + 6) + 4LL);
  if ( (v198 & 3) == 0 )
  {
    v24 = -1073741811;
    WdLogSingleEntry5(2, -1073741811, v7);
    WdLogGlobalForLineNumber = 4472;
    v77 = L"0x%I64x 0x%I64x destination must be primary 0x%I64x 0x%I64x 0x%I64x";
    v312 = *((unsigned int *)a2 + 6);
    v310 = *((_QWORD *)v324 + 6);
    v308 = (__int64)v324;
    v306 = (__int64)v7;
    v304 = -1073741811;
    goto LABEL_120;
  }
  v33 = (v198 >> 6) & 0xF;
  v199 = *(DXGADAPTER **)(*((_QWORD *)v7 + 2) + 1896LL);
  if ( !v199
    || !DXGADAPTER::IsDisplayAdapter(v199)
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
  *((_DWORD *)v330 + 29) = v33;
  DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v340, v324);
  DXGALLOCATIONREFERENCE::MoveAssign(&v333, v340);
  DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v340);
  v200 = *((_DWORD *)a2 + 22);
  v332 = *((_DWORD *)a2 + 6);
  if ( (v200 & 1) != 0 )
  {
    if ( v324 == v317 )
    {
      v24 = -1073741811;
      WdLogSingleEntry5(2, -1073741811, v7);
      WdLogGlobalForLineNumber = 4496;
      v77 = L"0x%I64x 0x%I64x Source and destination must be different 0x%I64x 0x%I64x 0x%I64x";
      v312 = *((unsigned int *)a2 + 6);
      v310 = *((unsigned int *)a2 + 5);
      v308 = (__int64)v317;
      v306 = (__int64)v7;
      v304 = -1073741811;
      goto LABEL_120;
    }
    v201 = *(_DWORD *)(*((_QWORD *)v317 + 6) + 4LL);
    if ( (v201 & 3) != 0 && ((v201 >> 6) & 0xF) != v33 )
    {
      v24 = -1073741811;
      WdLogSingleEntry5(2, -1073741811, v7);
      v77 = L"0x%I64x 0x%I64x primary source has different VidPnSourceId 0x%I64x 0x%I64x != 0x%I64x";
      v312 = v33;
      WdLogGlobalForLineNumber = 4509;
      v310 = (*(_DWORD *)(*((_QWORD *)v317 + 6) + 4LL) >> 6) & 0xF;
      v308 = (__int64)v317;
      v306 = (__int64)v7;
      v304 = -1073741811;
      goto LABEL_120;
    }
    v202 = *((_DWORD *)a2 + 12);
    v203 = *((_DWORD *)a2 + 14);
    if ( v203 <= v202
      || (v204 = *((_DWORD *)a2 + 13), v205 = *((_DWORD *)a2 + 15), v205 <= v204)
      || v202 >= v18
      || v204 >= (int)v322
      || v203 <= 0
      || v205 <= 0 )
    {
      v24 = -1073741811;
      WdLogSingleEntry5(2, -1073741811, *((int *)a2 + 12));
      WdLogGlobalForLineNumber = 4529;
      v77 = L"0x%I64x Invalid Source Rect [0x%I64x 0x%I64x 0x%I64x 0x%I64x]";
      v312 = *((int *)a2 + 15);
      v310 = *((int *)a2 + 14);
      v308 = *((int *)a2 + 13);
      v306 = *((int *)a2 + 12);
      v304 = -1073741811;
      goto LABEL_120;
    }
    for ( m = 0; ; ++m )
    {
      v207 = *((_DWORD *)a2 + 16);
      if ( m >= v207 )
        break;
      Source1 = 0;
      v208 = 16LL * m;
      v209 = m;
      if ( !DXGPRESENT::IntersectRect(
              &Source1,
              (const struct tagRECT *)(v208 + *((_QWORD *)a2 + 9)),
              (const struct tagRECT *)a2 + 3)
        || RtlCompareMemory(&Source1, (const void *)(v208 + *((_QWORD *)a2 + 9)), 0x10u) != 16 )
      {
        v24 = -1073741811;
        WdLogSingleEntry5(2, -1073741811, *((int *)a2 + 12));
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
        WdLogSingleEntry5(2, m, *(int *)(*((_QWORD *)a2 + 9) + 16LL * m));
        WdLogGlobalForLineNumber = 4555;
        goto LABEL_394;
      }
    }
    if ( (*((_DWORD *)a2 + 22) & 0x40) != 0 )
    {
      v210 = *((int *)a2 + 8);
      v211 = *((_DWORD *)a2 + 10);
      if ( v211 <= (int)v210
        || (v212 = *((_DWORD *)a2 + 9), v213 = *((_DWORD *)a2 + 11), v213 <= v212)
        || (int)v210 >= (int)v328[0]
        || v212 >= (int)v331[0]
        || v211 <= 0
        || v213 <= 0 )
      {
        v24 = -1073741811;
        WdLogSingleEntry5(3, -1073741811, v210);
        WdLogGlobalForLineNumber = 4577;
        goto LABEL_34;
      }
      if ( *((_DWORD *)a2 + 14) - *((_DWORD *)a2 + 12) != v211 - (_DWORD)v210
        || *((_DWORD *)a2 + 15) - *((_DWORD *)a2 + 13) != v213 - v212 )
      {
        v24 = -1073741811;
        WdLogSingleEntry5(2, -1073741811, v7);
        v77 = L"0x%I64x 0x%I64x specified destination RECT has different size from source RECT 0x%I64x 0x%I64x 0x%I64x";
        v312 = v33;
        v310 = (__int64)v324;
        WdLogGlobalForLineNumber = 4589;
        v308 = *((unsigned int *)a2 + 22);
        v306 = (__int64)v7;
        v304 = -1073741811;
        goto LABEL_120;
      }
      v28 = DXGPRESENT::GrowRectList(*((DXGPRESENT **)v7 + 19), v207);
      if ( v28 < 0 )
        goto LABEL_408;
      v214 = 0;
      v215 = DXGPRESENT::GetDdiSubRectList(*((DXGPRESENT **)v7 + 19), 0);
      v216 = *((_DWORD *)a2 + 8) - *((_DWORD *)a2 + 12);
      v217 = *((_DWORD *)a2 + 9) - *((_DWORD *)a2 + 13);
      v207 = *((_DWORD *)a2 + 16);
      if ( v207 )
      {
        do
        {
          v218 = v214++;
          v218 *= 2;
          *(&v215->left + 2 * v218) = v216 + *(_DWORD *)(*((_QWORD *)a2 + 9) + 8 * v218);
          *(&v215->right + 2 * v218) = v216 + *(_DWORD *)(*((_QWORD *)a2 + 9) + 8 * v218 + 8);
          *(&v215->top + 2 * v218) = v217 + *(_DWORD *)(*((_QWORD *)a2 + 9) + 8 * v218 + 4);
          *(&v215->bottom + 2 * v218) = v217 + *(_DWORD *)(*((_QWORD *)a2 + 9) + 8 * v218 + 12);
          v207 = *((_DWORD *)a2 + 16);
        }
        while ( v214 < v207 );
      }
      v219 = (RECT)*((_OWORD *)a2 + 2);
      v355.pDstSubRects = v215;
      v355.DstRect = v219;
    }
    else
    {
      if ( v328[0] != v320 || v331[0] != v322 )
      {
        WdLogSingleEntry5(3, v7, v328[0]);
        WdLogGlobalForLineNumber = 4625;
LABEL_416:
        v24 = -1073741811;
        goto LABEL_34;
      }
      v355.DstRect = (RECT)*((_OWORD *)a2 + 3);
      v355.pDstSubRects = (const RECT *)*((_QWORD *)a2 + 9);
    }
    v355.SrcRect = (RECT)*((_OWORD *)a2 + 3);
    Value = v355.Flags.Value & 0xFFFFF7FF | (*((_DWORD *)a2 + 22) >> 9) & 0x800;
    v355.Flags.Value = Value;
    goto LABEL_430;
  }
  v221 = 0;
  *(_QWORD *)&v355.DstRect.left = 0;
  v355.DstRect.right = Width;
  v355.DstRect.bottom = v331[0];
  if ( (v200 & 0x40) == 0 )
    goto LABEL_424;
  v222 = *((_DWORD *)a2 + 10);
  v223 = *((int *)a2 + 8);
  if ( v222 <= (int)v223 || (v224 = *((_DWORD *)a2 + 11), v224 <= *((_DWORD *)a2 + 9)) || v222 <= 0 || v224 <= 0 )
  {
    v24 = -1073741811;
    WdLogSingleEntry5(3, -1073741811, v223);
    WdLogGlobalForLineNumber = 4658;
    goto LABEL_34;
  }
  if ( !DXGPRESENT::IntersectRect(&v355.DstRect, (const struct tagRECT *)a2 + 2, &v355.DstRect) )
    goto LABEL_500;
  while ( 1 )
  {
LABEL_424:
    v207 = *((_DWORD *)a2 + 16);
    if ( v221 >= v207 )
    {
      Value = v355.Flags.Value;
      v355.SrcRect = v355.DstRect;
      v355.pDstSubRects = (const RECT *)*((_QWORD *)a2 + 9);
LABEL_430:
      v26 = a3;
      v355.SubRectCnt = v207;
      v225 = *((_DWORD *)a2 + 22) & 1 | Value & 0xFFFFFFFE;
      v226 = *((_DWORD *)a2 + 22) >> 5;
      v227 = *((_DWORD *)a2 + 22) >> 9;
      v228 = v225
           ^ ((unsigned __int8)v225
            ^ (unsigned __int8)*((_DWORD *)a2 + 22))
           & 2
           ^ ((unsigned __int8)v226
            ^ (unsigned __int8)(v225 ^ (v225 ^ *((_DWORD *)a2 + 22)) & 2))
           & 0x10
           ^ ((unsigned __int8)v226
            ^ (unsigned __int8)(v225
                              ^ (v225
                               ^ *((_DWORD *)a2 + 22))
                              & 2
                              ^ (v226
                               ^ v225
                               ^ (v225
                                ^ *((_DWORD *)a2 + 22))
                               & 2)
                              & 0x10))
           & 0x20;
      LOBYTE(v225) = v225
                   ^ (v225
                    ^ *((_DWORD *)a2 + 22))
                   & 2
                   ^ (v226
                    ^ v225
                    ^ (v225
                     ^ *((_DWORD *)a2 + 22))
                    & 2)
                   & 0x10
                   ^ (v226
                    ^ v225
                    ^ (v225
                     ^ *((_DWORD *)a2 + 22))
                    & 2
                    ^ (v226
                     ^ v225
                     ^ (v225
                      ^ *((_DWORD *)a2 + 22))
                     & 2)
                    & 0x10)
                   & 0x20;
      v355.Color = *((_DWORD *)a2 + 7);
      v355.Flags.Value = v228
                       ^ ((unsigned __int8)v226
                        ^ (unsigned __int8)v225)
                       & 0x40
                       ^ (v228
                        ^ ((unsigned __int8)v226
                         ^ (unsigned __int8)v225)
                        & 0x40
                        ^ v227)
                       & 0x800;
      goto LABEL_431;
    }
    v357 = 0;
    v208 = 16LL * v221;
    v209 = v221;
    if ( !DXGPRESENT::IntersectRect(&v357, (const struct tagRECT *)(v208 + *((_QWORD *)a2 + 9)), &v355.DstRect)
      || RtlCompareMemory(&v357, (const void *)(v208 + *((_QWORD *)a2 + 9)), 0x10u) != 16 )
    {
      break;
    }
    ++v221;
  }
  v24 = -1073741811;
  WdLogSingleEntry5(2, -1073741811, *((int *)a2 + 8));
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
  WdLogSingleEntry5(2, v221, *(int *)(*((_QWORD *)a2 + 9) + 16LL * v221));
  WdLogGlobalForLineNumber = 4690;
LABEL_394:
  DxgkLogInternalTriageEvent(
    0,
    0x40000,
    -1,
    (unsigned int)L"SubRect 0x%I64x is invalid 0x%I64x 0x%I64x 0x%I64x 0x%I64x",
    v209,
    *(int *)(*((_QWORD *)a2 + 9) + v208),
    *(int *)(*((_QWORD *)a2 + 9) + v208 + 4),
    *(int *)(*((_QWORD *)a2 + 9) + v208 + 8),
    *(int *)(*((_QWORD *)a2 + 9) + v208 + 12));
LABEL_34:
  DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v333);
  DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v324);
  DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v317);
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
