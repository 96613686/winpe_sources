# PrepareIndependentFlipToken(_D3DKMT_PRESENTHISTORYTOKEN *,DXGK_PRESENT_PARAMS *,VIDSCH_SUBMIT_DATA_BASE *,DXGCONTEXT *,_PRESENT_REDIRECTED_PARAMS *,CRefCountedBuffer *)

- ea: `0x14037be6c`
- end: `0x14037e3bf`
- name: `?PrepareIndependentFlipToken@@YAJPEAU_D3DKMT_PRESENTHISTORYTOKEN@@PEAUDXGK_PRESENT_PARAMS@@PEAUVIDSCH_SUBMIT_DATA_BASE@@PEAVDXGCONTEXT@@PEAU_PRESENT_REDIRECTED_PARAMS@@PEAVCRefCountedBuffer@@@Z`
- size: `9555`
- prototype: `__int64 __fastcall(struct _D3DKMT_PRESENTHISTORYTOKEN *, struct DXGK_PRESENT_PARAMS *, struct VIDSCH_SUBMIT_DATA_BASE *, struct DXGCONTEXT *, struct _PRESENT_REDIRECTED_PARAMS *, struct CRefCountedBuffer *)`
- caller_count: `2`
- callee_count: `37`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14038fb34`
- `0x1403a3acc`

## callees

- `0x14000e728`
- `0x1400146ac`
- `0x140015290`
- `0x1400162a4`
- `0x14001b9c0`
- `0x14001c450`
- `0x14002ff90`
- `0x1400371f8`
- `0x14003940c`
- `0x14003c42c`
- `0x14003cd10`
- `0x140041194`
- `0x14004a698`
- `0x14004e700`
- `0x1400674c4`
- `0x140075f74`
- `0x14007a12c`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a1000`
- `0x1401f6470`
- `0x140247a0c`
- `0x140319abc`
- `0x14032a5c4`
- `0x14032e900`
- `0x14032e980`
- `0x14032edac`
- `0x140347dc0`
- `0x14037bde0`
- `0x14037be6c`
- `0x14037e3c8`
- `0x14037e3f0`
- `0x14037e4f4`
- `0x14037e684`
- `0x14037ecf0`
- `0x140393c1c`
- `0x1403bf5bc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14037ce2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14037d126`
- `ntoskrnl!ExFreePoolWithTag` at `0x14037d2bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14037d42d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14037ce2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14037d126`
- `ntoskrnl!ExFreePoolWithTag` at `0x14037d2bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14037d42d`
- `ntoskrnl!ExAllocatePool2` at `0x14037d0ff`
- `ntoskrnl!ExAllocatePool2` at `0x14037d0ff`
- `ntoskrnl!RtlCopyLuid` at `0x14037c25d`
- `ntoskrnl!RtlCopyLuid` at `0x14037c25d`
- `watchdog!WdLogSingleEntry4` at `0x14037d0aa`
- `watchdog!WdLogSingleEntry4` at `0x14037d7f9`
- `watchdog!WdLogSingleEntry4` at `0x14037d0aa`
- `watchdog!WdLogSingleEntry4` at `0x14037d7f9`
- `watchdog!WdLogSingleEntry2` at `0x14037de0f`
- `watchdog!WdLogSingleEntry2` at `0x14037e0cc`
- `watchdog!WdLogSingleEntry2` at `0x14037de0f`
- `watchdog!WdLogSingleEntry2` at `0x14037e0cc`
- `watchdog!WdLogSingleEntry3` at `0x14037dea6`
- `watchdog!WdLogSingleEntry3` at `0x14037dea6`
- `watchdog!WdLogSingleEntry0` at `0x14037d63a`
- `watchdog!WdLogSingleEntry0` at `0x14037db0b`
- `watchdog!WdLogSingleEntry0` at `0x14037dbf8`
- `watchdog!WdLogSingleEntry0` at `0x14037e1b3`
- `watchdog!WdLogSingleEntry0` at `0x14037d63a`
- `watchdog!WdLogSingleEntry0` at `0x14037db0b`
- `watchdog!WdLogSingleEntry0` at `0x14037dbf8`
- `watchdog!WdLogSingleEntry0` at `0x14037e1b3`
- `watchdog!WdLogSingleEntry5` at `0x14037cb01`
- `watchdog!WdLogSingleEntry5` at `0x14037e353`
- `watchdog!WdLogSingleEntry5` at `0x14037cb01`
- `watchdog!WdLogSingleEntry5` at `0x14037e353`
- `watchdog!WdLogSingleEntry1` at `0x14037d002`
- `watchdog!WdLogSingleEntry1` at `0x14037da2d`
- `watchdog!WdLogSingleEntry1` at `0x14037df46`
- `watchdog!WdLogSingleEntry1` at `0x14037d002`
- `watchdog!WdLogSingleEntry1` at `0x14037da2d`
- `watchdog!WdLogSingleEntry1` at `0x14037df46`

## string_xrefs

- `0x14037d031`: `Failed to read dirty rects data. Returning 0x%I64x`
- `0x14037df89`: `Encountered exception reading source allocation handle. Returning 0x%I64x`

## pseudocode

```c
__int64 __fastcall PrepareIndependentFlipToken(
        struct _D3DKMT_PRESENTHISTORYTOKEN *a1,
        unsigned __int64 a2,
        struct VIDSCH_SUBMIT_DATA_BASE *a3,
        struct DXGCONTEXT *a4,
        struct _PRESENT_REDIRECTED_PARAMS *a5,
        struct CRefCountedBuffer *a6)
{
  struct VIDSCH_SUBMIT_DATA_BASE *v7; // r13
  struct VIDSCH_SUBMIT_DATA_BASE *v10; // r15
  unsigned int v11; // r14d
  __int64 v12; // rdi
  struct DXGPROCESS *Current; // r9
  DXGADAPTER **v14; // rsi
  struct ADAPTER_DISPLAY *v15; // rax
  enum _D3DDDI_HDR_METADATA_TYPE v16; // eax
  _QWORD *v17; // rax
  __int64 v18; // rcx
  DXGADAPTER *v19; // rbx
  UINT64 CompositionBindingId; // rdi
  __int64 v21; // rax
  struct _LUID *v22; // rax
  struct DXGCONTEXT *v23; // rbx
  DXGADAPTER *v24; // rdi
  int v25; // eax
  char v26; // al
  int v27; // eax
  int *v28; // rbx
  int v29; // eax
  __int64 v30; // rdx
  char v31; // al
  struct ADAPTER_DISPLAY *v32; // rbx
  _DWORD *v33; // r8
  UINT v34; // edi
  bool IsDxgmms2; // al
  struct DXGCONTEXT *v36; // rbx
  _BYTE *Pool2; // rcx
  __int64 v39; // rdx
  struct VIDSCH_SUBMIT_DATA_BASE *v40; // rdx
  DXGADAPTER *v41; // rcx
  DXGADAPTER *v42; // r9
  int v43; // eax
  __int64 v44; // r8
  _QWORD *v45; // rdx
  int v46; // r8d
  _QWORD *v47; // r10
  unsigned __int64 v48; // rdx
  __int64 v49; // rcx
  bool v50; // al
  __int64 v51; // r9
  UINT64 v52; // rsi
  __int64 v53; // rdi
  unsigned int v54; // ebx
  __int64 v55; // rax
  DXGADAPTER *v56; // rdi
  unsigned int v57; // ebx
  int v58; // eax
  UINT v59; // r9d
  struct DXGK_PRESENT_PARAMS *v60; // r15
  char v61; // r13
  __int64 v62; // r8
  __int16 v63; // r10
  __int64 v64; // rdx
  _QWORD *v65; // r10
  DXGK_ALLOCATIONLIST *pAllocationList; // rbx
  unsigned __int64 AllocationGpuVirtualAddress; // rax
  void *v68; // rdx
  unsigned __int64 v69; // r8
  int v70; // eax
  int v71; // ecx
  int v72; // edx
  int v73; // eax
  __int64 v74; // rbx
  __int64 v75; // r8
  __int64 v76; // rax
  __int128 v77; // xmm1
  _QWORD *v78; // r9
  _QWORD *v79; // rax
  __int64 *v80; // rax
  __int64 **v81; // rdx
  struct DXGK_PRESENT_PARAMS *v82; // r11
  VIDSCH_EXPORT *v83; // rdi
  unsigned __int64 v84; // rbx
  const struct _LUID *v85; // rax
  VIDSCH_EXPORT *v86; // rdi
  unsigned __int64 v87; // rbx
  const struct _LUID *v88; // rax
  __int64 v89; // rdx
  _DWORD *v90; // rbx
  int v91; // ebx
  VIDSCH_EXPORT *v92; // rdi
  unsigned __int64 v93; // rbx
  const struct _LUID *v94; // rax
  __int64 v95; // rdx
  unsigned __int8 PostCompositionStretching; // al
  bool v97; // r9
  __int64 *v98; // rax
  __int64 *v99; // rdi
  VIDSCH_EXPORT *v100; // rdi
  unsigned __int64 v101; // rbx
  const struct _LUID *v102; // rax
  __int64 v103; // rdx
  unsigned int v104; // eax
  unsigned int v105; // eax
  __int64 v106; // rax
  _OWORD *v107; // rax
  __int64 AllocationSafe; // rax
  __int64 v109; // r9
  __int64 v110; // rdx
  _DWORD *v111; // rax
  _DWORD *v112; // rbx
  unsigned int v113; // edi
  enum _D3DDDI_HDR_METADATA_TYPE v114; // r15d
  struct DXGCONTEXT *v115; // rbx
  __int64 v116; // r13
  int v117; // ecx
  UINT64 v118; // rsi
  __int64 v119; // rdi
  unsigned int v120; // ebx
  __int64 v121; // rax
  __int64 v122; // rdx
  bool v123; // [rsp+20h] [rbp-3E8h]
  __int128 v124; // [rsp+80h] [rbp-388h] BYREF
  char v125; // [rsp+90h] [rbp-378h]
  enum _D3DDDI_HDR_METADATA_TYPE v126; // [rsp+94h] [rbp-374h] BYREF
  unsigned int v127; // [rsp+98h] [rbp-370h] BYREF
  int v128; // [rsp+9Ch] [rbp-36Ch]
  struct ADAPTER_DISPLAY *v129; // [rsp+A0h] [rbp-368h]
  struct CRefCountedBuffer *v130; // [rsp+A8h] [rbp-360h] BYREF
  int v131; // [rsp+B0h] [rbp-358h]
  _QWORD *v132; // [rsp+B8h] [rbp-350h] BYREF
  unsigned int v133; // [rsp+C0h] [rbp-348h] BYREF
  int v134; // [rsp+C4h] [rbp-344h]
  __int64 *v135; // [rsp+C8h] [rbp-340h]
  DXGADAPTER *v136; // [rsp+D0h] [rbp-338h]
  int v137; // [rsp+D8h] [rbp-330h]
  unsigned int v138; // [rsp+DCh] [rbp-32Ch] BYREF
  int v139; // [rsp+E0h] [rbp-328h]
  bool v140[8]; // [rsp+E8h] [rbp-320h]
  struct DXGCONTEXT *v141; // [rsp+F0h] [rbp-318h]
  struct DXGK_PRESENT_PARAMS *v142; // [rsp+F8h] [rbp-310h]
  __int64 v143; // [rsp+100h] [rbp-308h]
  _BYTE *v144; // [rsp+108h] [rbp-300h]
  int v145; // [rsp+110h] [rbp-2F8h]
  int v146; // [rsp+114h] [rbp-2F4h]
  int v147; // [rsp+118h] [rbp-2F0h]
  int v148; // [rsp+11Ch] [rbp-2ECh]
  struct _D3DKMT_PRESENTHISTORYTOKEN *v149; // [rsp+120h] [rbp-2E8h]
  _QWORD *v150; // [rsp+128h] [rbp-2E0h]
  _QWORD *v151; // [rsp+130h] [rbp-2D8h]
  struct VIDSCH_SUBMIT_DATA_BASE *v152; // [rsp+138h] [rbp-2D0h]
  int v153; // [rsp+140h] [rbp-2C8h] BYREF
  struct CRefCountedBuffer *v154; // [rsp+148h] [rbp-2C0h]
  unsigned __int64 v155; // [rsp+150h] [rbp-2B8h]
  __int64 v156; // [rsp+158h] [rbp-2B0h]
  unsigned int *v157; // [rsp+160h] [rbp-2A8h]
  UINT64 *p_CompositionBindingId; // [rsp+168h] [rbp-2A0h]
  struct DXGCONTEXT *v159; // [rsp+170h] [rbp-298h]
  struct _D3DDDI_HDR_METADATA_HDR10 v160; // [rsp+178h] [rbp-290h] BYREF
  __int64 v161; // [rsp+198h] [rbp-270h]
  __int64 v162; // [rsp+1A0h] [rbp-268h]
  __int64 v163; // [rsp+1A8h] [rbp-260h]
  struct VIDSCH_SUBMIT_DATA_BASE *v164; // [rsp+1B0h] [rbp-258h]
  struct VIDSCH_SUBMIT_DATA_BASE *v165; // [rsp+1B8h] [rbp-250h]
  struct tagRECT v166; // [rsp+1C0h] [rbp-248h] BYREF
  PVOID v167; // [rsp+1D0h] [rbp-238h]
  _BYTE v168[32]; // [rsp+1D8h] [rbp-230h] BYREF
  UINT v169; // [rsp+1F8h] [rbp-210h]
  DXGADAPTER **v170; // [rsp+200h] [rbp-208h]
  struct DXGPROCESS *v171; // [rsp+208h] [rbp-200h]
  struct VIDSCH_SUBMIT_DATA_BASE *v172; // [rsp+210h] [rbp-1F8h]
  struct _D3DKMT_PRESENTHISTORYTOKEN *v173; // [rsp+218h] [rbp-1F0h]
  unsigned __int64 v174; // [rsp+220h] [rbp-1E8h]
  DXGADAPTER **v175; // [rsp+228h] [rbp-1E0h]
  _DXGKARG_PRESENT v176; // [rsp+230h] [rbp-1D8h] BYREF
  __int128 v177; // [rsp+2E0h] [rbp-128h] BYREF
  struct tagRECT v178; // [rsp+2F0h] [rbp-118h] BYREF
  _QWORD v179[5]; // [rsp+300h] [rbp-108h] BYREF
  int v180; // [rsp+328h] [rbp-E0h]
  PVOID P; // [rsp+330h] [rbp-D8h] BYREF
  _BYTE v182[128]; // [rsp+338h] [rbp-D0h] BYREF
  int v183; // [rsp+3B8h] [rbp-50h]

  v141 = a4;
  v7 = a3;
  v165 = a3;
  v142 = (struct DXGK_PRESENT_PARAMS *)a2;
  v149 = a1;
  v172 = a3;
  v173 = a1;
  v174 = a2;
  v10 = a3;
  v164 = a3;
  v159 = a4;
  v130 = a5;
  v154 = a6;
  v11 = 0;
  if ( !CIFlipPresentHistoryToken::IsIFlipSupported(a1) || a4 && !a2 )
    return 0;
  v124 = 0;
  if ( a1->Model == D3DKMT_PM_REDIRECTED_FLIP )
  {
    CIFlipPresentHistoryTokenRedirectedFlip::CIFlipPresentHistoryTokenRedirectedFlip(
      (CIFlipPresentHistoryTokenRedirectedFlip *)&v124,
      &a1->Token.Flip);
  }
  else if ( a1->Model == D3DKMT_PM_FLIPMANAGER )
  {
    CIFlipPresentHistoryTokenFlipManager::CIFlipPresentHistoryTokenFlipManager(
      (CIFlipPresentHistoryTokenFlipManager *)&v124,
      (const struct _D3DKMT_FLIPMANAGER_PRESENTHISTORYTOKEN *)&a1->Token);
  }
  if ( a4 )
  {
    v151 = (_QWORD *)*((_QWORD *)a4 + 2);
    v12 = *(_QWORD *)(v151[2] + 16LL);
  }
  else
  {
    v12 = *((_QWORD *)a5 + 3);
    v151 = (_QWORD *)*((_QWORD *)a5 + 4);
  }
  v162 = v12;
  v136 = (DXGADAPTER *)v12;
  if ( !a4 && !*(_BYTE *)(v12 + 3185) )
    goto LABEL_51;
  *((_QWORD *)v7 + 3) = 0;
  Current = DXGPROCESS::GetCurrent();
  v171 = Current;
  v14 = *(DXGADAPTER ***)(v12 + 3256);
  v170 = v14;
  v15 = 0;
  if ( *(_QWORD *)(v12 + 3248) )
    v15 = *(struct ADAPTER_DISPLAY **)(v12 + 3248);
  v129 = v15;
  v155 = a2 & -(__int64)(a4 != 0);
  if ( a4 )
    v16 = *(_DWORD *)((a2 & -(__int64)(a4 != 0)) + 0x14);
  else
    v16 = *((_DWORD *)v130 + 1);
  v126 = v16;
  DXGPROCESS::GetAllocationSafe(Current, &v132, (unsigned int)v16);
  v17 = v132;
  if ( !v132 || *(_QWORD *)(*(_QWORD *)(v132[1] + 16LL) + 16LL) != *(_QWORD *)(v151[2] + 16LL) )
  {
LABEL_50:
    DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v132);
LABEL_51:
    CIFlipPresentHistoryToken::~CIFlipPresentHistoryToken((CIFlipPresentHistoryToken *)&v124);
    return 0;
  }
  v175 = v14;
  if ( v154 )
  {
    v39 = v132[5];
    if ( v39 )
    {
      if ( (*(_DWORD *)(v39 + 4) & 1) != 0 )
        *((_QWORD *)v7 + 3) = *(_QWORD *)(*(_QWORD *)(v39 + 56) + 176LL);
    }
  }
  if ( a4 )
    v18 = *((_QWORD *)v142 + 187);
  else
    v18 = 0;
  v163 = v18;
  v156 = v18;
  v133 = (*(_DWORD *)(v17[6] + 4LL) >> 6) & 0xF;
  v145 = 0;
  v139 = 0;
  v146 = 0;
  v147 = 0;
  v127 = 0;
  v161 = *(_QWORD *)(*(__int64 (__fastcall **)(__int128 *))(v124 + 24))(&v124);
  v137 = 0;
  v177 = 0;
  v178 = 0;
  *(_QWORD *)v140 = (char *)v7 + (*((_BYTE *)v7 + 356) != 0 ? 0xF0 : 0) + 528;
  v19 = v14[92];
  p_CompositionBindingId = &v149->CompositionBindingId;
  CompositionBindingId = v149->CompositionBindingId;
  v21 = (*(__int64 (__fastcall **)(__int128 *))(v124 + 16))(&v124);
  v123 = v140[0];
  (*(void (__fastcall **)(DXGADAPTER *, unsigned int *, __int64, UINT64))(*((_QWORD *)v19 + 1) + 432LL))(
    v14[93],
    &v133,
    v21,
    CompositionBindingId);
  (*(void (__fastcall **)(__int128 *, __int64))(v124 + 32))(&v124, v161);
  (*(void (__fastcall **)(__int128 *, _QWORD))(v124 + 48))(&v124, v133);
  *((_DWORD *)v7 + 29) = v133;
  v22 = (struct _LUID *)(*(__int64 (__fastcall **)(__int128 *))(v124 + 16))(&v124);
  RtlCopyLuid((PLUID)((char *)v7 + 156), v22);
  *((_QWORD *)v7 + 21) = *p_CompositionBindingId;
  *(_DWORD *)v7 &= ~0x10000u;
  v23 = v141;
  if ( v141 )
  {
    v69 = v155;
    v70 = *(_DWORD *)v7 ^ (*(_DWORD *)(v155 + 88) ^ *(_DWORD *)v7) & 4;
    *(_DWORD *)v7 = v70;
    v71 = v70 ^ (v70 ^ (4 * *(_DWORD *)(v69 + 88))) & 0x80000;
    *(_DWORD *)v7 = v71;
    v72 = v71 ^ (v71 ^ (4 * *(_DWORD *)(v69 + 88))) & 0x100000;
    *(_DWORD *)v7 = v72;
    *(_DWORD *)v7 = v72 ^ (v72 ^ (4 * *(_DWORD *)(v69 + 88))) & 0x200000;
  }
  *(_DWORD *)v7 ^= ((unsigned __int8)*(_DWORD *)v7
                  ^ (unsigned __int8)(8 * (*(__int64 (__fastcall **)(__int128 *))(v124 + 200))(&v124)))
                 & 8;
  *(_DWORD *)v7 ^= ((unsigned __int8)*(_DWORD *)v7
                  ^ (unsigned __int8)(16 * (*(__int64 (__fastcall **)(__int128 *))(v124 + 208))(&v124)))
                 & 0x10;
  *(_DWORD *)v7 ^= (*(_DWORD *)v7
                  ^ ((*(unsigned __int8 (__fastcall **)(__int128 *))(v124 + 216))(&v124) << 28))
                 & 0x10000000;
  *((_DWORD *)v7 + 1) ^= ((unsigned __int8)*((_DWORD *)v7 + 1)
                        ^ (unsigned __int8)((*(unsigned __int8 (__fastcall **)(__int128 *))(v124 + 224))(&v124) << 6))
                       & 0x40;
  *((_DWORD *)v7 + 1) ^= ((unsigned __int16)*((_DWORD *)v7 + 1)
                        ^ (unsigned __int16)((*(unsigned __int8 (__fastcall **)(__int128 *))(v124 + 320))(&v124) << 8))
                       & 0x100;
  *((_DWORD *)v7 + 1) ^= ((unsigned __int16)*((_DWORD *)v7 + 1)
                        ^ (unsigned __int16)((*(unsigned __int8 (__fastcall **)(__int128 *))(v124 + 328))(&v124) << 9))
                       & 0x200;
  v24 = v136;
  (*(void (__fastcall **)(__int128 *, DXGADAPTER *))(v124 + 56))(&v124, v136);
  *((_DWORD *)v7 + 28) = (*(__int64 (__fastcall **)(__int128 *))(v124 + 64))(&v124);
  *((_DWORD *)v7 + 48) = *(_DWORD *)(*(__int64 (__fastcall **)(__int128 *))(v124 + 72))(&v124);
  *(_DWORD *)v7 ^= (*(_DWORD *)v7
                  ^ ((*(unsigned __int8 (__fastcall **)(__int128 *))(v124 + 192))(&v124) << 25))
                 & 0x2000000;
  *((_DWORD *)v7 + 36) = (*(__int64 (__fastcall **)(__int128 *))(v124 + 80))(&v124);
  *((_DWORD *)v7 + 37) = (*(__int64 (__fastcall **)(__int128 *))(v124 + 88))(&v124);
  if ( v23 )
    v25 = *((_DWORD *)v23 + 96);
  else
    v25 = 1;
  *((_DWORD *)v7 + 34) = v25;
  v26 = *((_BYTE *)v7 + 356);
  if ( v26 )
    v157 = (unsigned int *)((char *)v7 + 616);
  else
    v157 = 0;
  if ( v26 )
    *((_DWORD *)v7 + 162) = -1;
  if ( bTracingEnabled )
    *((_QWORD *)v7 + 23) = VIDMM_EXPORT::VidMmETWAllocationHandle(v14[95], v14[96], v126);
  v27 = (*(__int64 (__fastcall **)(__int128 *))(v124 + 96))(&v124);
  v130 = (struct VIDSCH_SUBMIT_DATA_BASE *)((char *)v7 + 124);
  *((_DWORD *)v7 + 31) = v27;
  v28 = (int *)((char *)v7 + 124);
  v153 = 1;
  if ( !v27
    && (!(*(unsigned __int8 (__fastcall **)(__int128 *))(v124 + 216))(&v124) || (*((_DWORD *)v24 + 647) & 0x40) == 0) )
  {
    v28 = &v153;
  }
  v29 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *))(*((_QWORD *)v14[92] + 1) + 536LL))(v151[100], v133, v28);
  *((_DWORD *)v7 + 30) = v29;
  if ( v29 != 5 && *(_DWORD *)v130 )
  {
    (*(__int64 (__fastcall **)(__int128 *))(v124 + 64))(&v124);
    (*(void (__fastcall **)(__int128 *))(v124 + 104))(&v124);
    WdLogSingleEntry4(8, v149);
    WdLogGlobalForLineNumber = 2291;
    goto LABEL_59;
  }
  if ( !v145 )
  {
    if ( v146 )
    {
      v126 = D3DDDI_HDR_METADATA_TYPE_NONE;
      v130 = 0;
      v83 = v14[92];
      v84 = *((_QWORD *)v7 + 21);
      v85 = (const struct _LUID *)(*(__int64 (__fastcall **)(__int128 *))(v124 + 16))(&v124);
      VIDSCH_EXPORT::VidSchExitIndependentFlip(
        v83,
        v14[93],
        1 << *((_DWORD *)v7 + 29),
        v85,
        v84,
        &v127,
        0,
        0,
        (int *)&v126,
        (unsigned __int64 *)&v130);
      ADAPTER_DISPLAY::UpdateIndependentFlipState(v129, *((_DWORD *)v7 + 29), v127, 0);
    }
    else if ( !v147 )
    {
LABEL_59:
      DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v132);
      (*(void (__fastcall **)(__int128 *, __int64))v124)(&v124, 1);
      return 0;
    }
    LOBYTE(v30) = 1;
    (*(void (__fastcall **)(__int128 *, __int64))(v124 + 232))(&v124, v30);
    goto LABEL_59;
  }
  *((_QWORD *)v7 + 22) = *(_QWORD *)(*(__int64 (__fastcall **)(__int128 *))(v124 + 24))(&v124);
  if ( !(*(unsigned __int8 (__fastcall **)(__int128 *))(v124 + 240))(&v124) )
  {
    v126 = D3DDDI_HDR_METADATA_TYPE_NONE;
    v130 = 0;
    v86 = v14[92];
    v87 = *((_QWORD *)v7 + 21);
    v88 = (const struct _LUID *)(*(__int64 (__fastcall **)(__int128 *))(v124 + 16))(&v124);
    VIDSCH_EXPORT::VidSchExitIndependentFlip(
      v86,
      v14[93],
      1 << *((_DWORD *)v7 + 29),
      v88,
      v87,
      &v127,
      0,
      0,
      (int *)&v126,
      (unsigned __int64 *)&v130);
    LOBYTE(v89) = 1;
    (*(void (__fastcall **)(__int128 *, __int64))(v124 + 232))(&v124, v89);
    ADAPTER_DISPLAY::UpdateIndependentFlipState(v129, *((_DWORD *)v7 + 29), v127, 0);
    WdLogSingleEntry0(8);
    WdLogGlobalForLineNumber = 2360;
    goto LABEL_50;
  }
  if ( v139 || DXGADAPTER::SupportCheckMultiPlaneOverlaySupport3(v14[2]) )
  {
    v31 = (*(__int64 (__fastcall **)(__int128 *))(v124 + 248))(&v124);
    v32 = v129;
    if ( !v31 )
    {
      ADAPTER_DISPLAY::UpdateIndependentFlipState(v129, *((_DWORD *)v7 + 29), v127, 1u);
LABEL_34:
      *(_DWORD *)v7 = *(_DWORD *)v7 & 0x7BFFFFFF | ((v139 & 1 | (32 * v137)) << 26);
      *(_OWORD *)((char *)v7 + 436) = v177;
      *(struct tagRECT *)((char *)v7 + 452) = v178;
      goto LABEL_35;
    }
    DXGDISPLAYSTATEMUTEX::DXGDISPLAYSTATEMUTEX((DXGDISPLAYSTATEMUTEX *)&v160, v129);
    DXGAUTOMUTEX::Acquire((DXGAUTOMUTEX *)&v160);
    PostCompositionStretching = ADAPTER_DISPLAY::GetPostCompositionStretching(v32, *((_DWORD *)v7 + 29));
    v125 = PostCompositionStretching;
    if ( PostCompositionStretching )
    {
      if ( IsYUVAllocation(*(void **)(v132[6] + 16LL), (struct ADAPTER_RENDER *)v14)
        || DISPLAY_SOURCE::GetEnabledPlaneCountUnsafe((DISPLAY_SOURCE *)(*((_QWORD *)v32 + 16)
                                                                       + 4024LL * *((unsigned int *)v7 + 29))) > 1 )
      {
        PostCompositionStretching = 0;
        v125 = 0;
      }
      else
      {
        PostCompositionStretching = v125;
      }
    }
    v166 = 0;
    if ( v127 || (v97 = 1, !PostCompositionStretching) )
      v97 = 0;
    if ( CheckAndUpdateMultiPlaneOverlayFromInternalState(
           *((_DWORD *)v7 + 29),
           v127,
           (struct CIFlipPresentHistoryTokenData *)&v124,
           v97,
           (struct ADAPTER_RENDER *)v14,
           v32,
           &v166) )
    {
      v98 = (__int64 *)(*(__int64 (__fastcall **)(__int128 *))(v124 + 8))(&v124);
      v135 = v98;
      v99 = *(__int64 **)v140;
      **(_WORD **)v140 = *(_WORD *)v98;
      *((_WORD *)v99 + 2) = *((_WORD *)v98 + 2);
      *((_WORD *)v99 + 1) = *((_WORD *)v98 + 4);
      *((_WORD *)v99 + 3) = *((_WORD *)v98 + 6);
      *((_DWORD *)v99 + 6) = (*(__int64 (__fastcall **)(__int128 *))(v124 + 112))(&v124);
      if ( v125 )
      {
        v76 = *v99;
        v99[1] = *v99;
        v99[2] = v76;
        v77 = *(_OWORD *)v135;
        v177 = v77;
        v178 = v166;
        if ( (_DWORD)v77 != v166.left
          || __PAIR64__(DWORD2(v177), DWORD1(v77)) != *(_QWORD *)&v166.top
          || (v75 = 0, HIDWORD(v177) != v166.bottom) )
        {
          v75 = 1;
        }
        v137 = v75;
        if ( !(_DWORD)v75 )
        {
          v177 = 0;
          v178 = 0;
        }
        (*(void (__fastcall **)(DXGADAPTER *, _QWORD, __int64, __int128 *, struct tagRECT *))(*((_QWORD *)v14[92] + 1)
                                                                                            + 1008LL))(
          v14[93],
          *((unsigned int *)v7 + 29),
          v75,
          &v177,
          &v178);
        UpdatePostComposition(*((_DWORD *)v7 + 29), v137 != 0, DWORD2(v177) - v177, HIDWORD(v177) - DWORD1(v177), v32);
      }
      (*(void (__fastcall **)(DXGADAPTER *, _QWORD, __int64 *, _QWORD))(*((_QWORD *)v14[92] + 1) + 440LL))(
        v14[93],
        *((unsigned int *)v7 + 29),
        v99,
        v127);
      DXGAUTOMUTEX::Release((DXGAUTOMUTEX *)&v160);
      DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)&v160);
      goto LABEL_34;
    }
    DXGAUTOMUTEX::Release((DXGAUTOMUTEX *)&v160);
    v126 = D3DDDI_HDR_METADATA_TYPE_NONE;
    v130 = 0;
    v100 = v14[92];
    v101 = *((_QWORD *)v7 + 21);
    v102 = (const struct _LUID *)(*(__int64 (__fastcall **)(__int128 *))(v124 + 16))(&v124);
    VIDSCH_EXPORT::VidSchExitIndependentFlip(
      v100,
      v14[93],
      1 << *((_DWORD *)v7 + 29),
      v102,
      v101,
      &v127,
      0,
      0,
      (int *)&v126,
      (unsigned __int64 *)&v130);
    WdLogSingleEntry1(3, v127);
    WdLogGlobalForLineNumber = 2470;
    LOBYTE(v103) = 1;
    (*(void (__fastcall **)(__int128 *, __int64))(v124 + 232))(&v124, v103);
    ADAPTER_DISPLAY::UpdateIndependentFlipState(v129, *((_DWORD *)v7 + 29), v127, 0);
    DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)&v160);
    goto LABEL_50;
  }
  v90 = (_DWORD *)(*(__int64 (__fastcall **)(__int128 *))(v124 + 8))(&v124);
  *(_QWORD *)v140 = v90;
  if ( v90[2] - *v90 != (*(unsigned int (__fastcall **)(__int128 *))(v124 + 120))(&v124)
    || (v91 = v90[3] - v90[1], v91 != (*(unsigned int (__fastcall **)(__int128 *))(v124 + 128))(&v124))
    || (*(unsigned __int8 (__fastcall **)(__int128 *))(v124 + 248))(&v124) )
  {
    v126 = D3DDDI_HDR_METADATA_TYPE_NONE;
    v130 = 0;
    v92 = v14[92];
    v93 = *((_QWORD *)v7 + 21);
    v94 = (const struct _LUID *)(*(__int64 (__fastcall **)(__int128 *))(v124 + 16))(&v124);
    VIDSCH_EXPORT::VidSchExitIndependentFlip(
      v92,
      v14[93],
      1 << *((_DWORD *)v7 + 29),
      v94,
      v93,
      &v127,
      0,
      0,
      (int *)&v126,
      (unsigned __int64 *)&v130);
    (*(__int64 (__fastcall **)(__int128 *))(v124 + 128))(&v124);
    (*(void (__fastcall **)(__int128 *))(v124 + 120))(&v124);
    WdLogSingleEntry4(8, *(_DWORD *)(*(_QWORD *)v140 + 8LL) - **(_DWORD **)v140);
    WdLogGlobalForLineNumber = 2523;
    LOBYTE(v95) = 1;
    (*(void (__fastcall **)(__int128 *, __int64))(v124 + 232))(&v124, v95);
    ADAPTER_DISPLAY::UpdateIndependentFlipState(v129, *((_DWORD *)v7 + 29), 0, 0);
LABEL_149:
    DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v132);
    CIFlipPresentHistoryToken::~CIFlipPresentHistoryToken((CIFlipPresentHistoryToken *)&v124);
    return v11;
  }
  v32 = v129;
  ADAPTER_DISPLAY::UpdateIndependentFlipState(v129, *((_DWORD *)v7 + 29), 0, 1u);
LABEL_35:
  if ( v32 && (*((_DWORD *)v32 + 6) & 0x10) != 0 )
  {
    if ( !ADAPTER_DISPLAY::IsHdrEnabled(v32, v133) )
    {
      *((_DWORD *)v7 + 90) = 0;
LABEL_39:
      *(_DWORD *)v7 |= 0x40000000u;
      goto LABEL_40;
    }
    *(_DWORD *)v7 ^= (*(_DWORD *)v7
                    ^ ((*(unsigned __int8 (__fastcall **)(__int128 *))(v124 + 256))(&v124) << 30))
                   & 0x40000000;
    v104 = (*(__int64 (__fastcall **)(__int128 *))(v124 + 136))(&v124);
    *((_DWORD *)v7 + 90) = v104;
    if ( (*(_DWORD *)v7 & 0x40000000) != 0 )
    {
      if ( v104 )
      {
        v105 = v104 - 1;
        if ( v105 )
        {
          if ( v105 == 1 )
          {
            v106 = (*(__int64 (__fastcall **)(__int128 *))(v124 + 152))(&v124);
            *(_OWORD *)((char *)v7 + 364) = *(_OWORD *)v106;
            *(_OWORD *)((char *)v7 + 380) = *(_OWORD *)(v106 + 16);
            *(_OWORD *)((char *)v7 + 396) = *(_OWORD *)(v106 + 32);
            *(_OWORD *)((char *)v7 + 412) = *(_OWORD *)(v106 + 48);
            *(_QWORD *)((char *)v7 + 428) = *(_QWORD *)(v106 + 64);
          }
          else
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 2565;
            DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"FALSE", 2565, 0, 0, 0, 0);
            *(_DWORD *)v7 &= ~0x40000000u;
          }
        }
        else
        {
          v107 = (_OWORD *)(*(__int64 (__fastcall **)(__int128 *))(v124 + 144))(&v124);
          *(_OWORD *)((char *)v7 + 364) = *v107;
          *(_OWORD *)((char *)v7 + 376) = *(_OWORD *)((char *)v107 + 12);
        }
      }
    }
    else
    {
      if ( v104 > 2 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 2573;
        DxgkLogInternalTriageEvent(
          0,
          262146,
          -1,
          (unsigned int)L"D3DDDI_HDR_METADATA_TYPE_HDR10 == pVidSchSubmitData->HDRMetaDataType || D3DDDI_HDR_METADATA_TYPE"
                         "_HDR10PLUS == pVidSchSubmitData->HDRMetaDataType || D3DDDI_HDR_METADATA_TYPE_NONE == pVidSchSub"
                         "mitData->HDRMetaDataType",
          2573,
          0,
          0,
          0,
          0);
      }
      *(_DWORD *)v7 |= 0x40000000u;
      if ( *((_DWORD *)v7 + 90) == 1 )
      {
        *((_DWORD *)v7 + 90) = 134217729;
      }
      else if ( *((_DWORD *)v7 + 90) == 2 )
      {
        *((_DWORD *)v7 + 90) = -2147483646;
      }
    }
    if ( !*((_DWORD *)v7 + 90) )
    {
      v126 = D3DDDI_HDR_METADATA_TYPE_NONE;
      memset(&v160, 0, sizeof(v160));
      if ( !(unsigned int)PopulateHDRMetadataFromDisplay(*((_DWORD *)v7 + 29), v32, &v160, &v126) )
      {
        *(_OWORD *)((char *)v7 + 364) = *(_OWORD *)v160.RedPrimary;
        *(_OWORD *)((char *)v7 + 376) = *(_OWORD *)v160.WhitePoint;
        *((_DWORD *)v7 + 90) = v126;
        goto LABEL_39;
      }
    }
  }
LABEL_40:
  (*(void (__fastcall **)(__int128 *, _QWORD))(v124 + 160))(&v124, v127);
  v33 = (_DWORD *)((char *)v7 + 600);
  if ( !*((_BYTE *)v7 + 356) )
    v33 = (_DWORD *)((char *)v7 + 496);
  *v33 ^= ((unsigned __int16)*v33 ^ (unsigned __int16)(1 << v127)) & 0x3FF;
  v34 = 1;
  v131 = 1;
  IsDxgmms2 = DXGADAPTER::IsDxgmms2(v136);
  v36 = v141;
  if ( IsDxgmms2 && v141 )
  {
    v34 = *(_DWORD *)(v155 + 92) + 1;
    v131 = v34;
  }
  Pool2 = 0;
  v144 = 0;
  v167 = 0;
  v169 = 0;
  if ( v34 <= 4 )
  {
    Pool2 = v168;
    v144 = v168;
    v167 = v168;
    if ( !v34 )
    {
LABEL_47:
      v169 = v34;
      goto LABEL_48;
    }
    memset(v168, 0, 8LL * v34);
    Pool2 = v167;
LABEL_46:
    v144 = Pool2;
    goto LABEL_47;
  }
  if ( 0xFFFFFFFFFFFFFFFFuLL / v34 >= 8 )
  {
    Pool2 = (_BYTE *)ExAllocatePool2(256, 8LL * v34, 1265072196);
    v167 = Pool2;
    goto LABEL_46;
  }
LABEL_48:
  *(_QWORD *)v160.RedPrimary = Pool2;
  if ( !Pool2 )
  {
    v167 = 0;
    v169 = 0;
    DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v132);
    (*(void (__fastcall **)(__int128 *, __int64))v124)(&v124, 1);
    return 3221225495LL;
  }
  v179[0] = 0;
  v180 = 0;
  PagedPoolArray<DXGALLOCATIONREFERENCE,4>::AllocateElements(v179, v34);
  *(_QWORD *)v140 = v179[0];
  if ( !v179[0] )
  {
    PagedPoolArray<DXGALLOCATIONREFERENCE,4>::~PagedPoolArray<DXGALLOCATIONREFERENCE,4>(v179);
    if ( v167 != v168 && v167 )
      ExFreePoolWithTag(v167, 0);
    v167 = 0;
    v169 = 0;
    v11 = -1073741801;
    goto LABEL_149;
  }
  v40 = v7;
  v152 = v7;
  v41 = v136;
  v42 = v136;
  v129 = v136;
  v43 = 0;
  v128 = 0;
  v126 = D3DDDI_HDR_METADATA_TYPE_NONE;
  v44 = 0;
  while ( 1 )
  {
    v134 = v44;
    if ( (unsigned int)v44 >= v34 )
      break;
    if ( (_DWORD)v44 )
    {
      v143 = (unsigned int)v44;
      v128 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v142 + 187) + 8LL * (unsigned int)v44) + 388LL);
      v138 = 0;
      RtlCopyFromUser(&v138, (void *)(*(_QWORD *)(v155 + 1456) + 4LL * (unsigned int)(v44 - 1)), 4u);
      v135 = (__int64 *)(*(_QWORD *)v140 + 8 * v143);
      AllocationSafe = DXGPROCESS::GetAllocationSafe(v171, &v166, v138);
      DXGALLOCATIONREFERENCE::MoveAssign(v135, AllocationSafe);
      DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v166);
      v47 = (_QWORD *)*v135;
      v150 = v47;
      if ( !v47 )
      {
        WdLogSingleEntry2(2, v138, -1073741811);
        WdLogGlobalForLineNumber = 2686;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Invalid allocation handle in present: 0x%I64x. Returning 0x%I64x",
          v138,
          -1073741811,
          0,
          0,
          0);
        v43 = -1073741811;
        v128 = -1073741811;
        v148 = -1073741811;
        v42 = v129;
        break;
      }
      v82 = v142;
      v109 = 8 * v143;
      if ( *(_QWORD *)(*(_QWORD *)(v47[1] + 16LL) + 16LL) != *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v142 + 187) + 8 * v143)
                                                                                               + 16LL)
                                                                                   + 16LL)
                                                                       + 16LL) )
      {
        _mm_lfence();
        WdLogSingleEntry3(2, *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v142 + 187) + 8 * v143) + 16LL), v47, -1073741811);
        WdLogGlobalForLineNumber = 2695;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Device 0x%p does not match allocation 0x%p owner, returning 0x%I64x",
          *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v142 + 187) + 8 * v143) + 16LL),
          *v135,
          -1073741811,
          0,
          0);
        v43 = -1073741811;
        v128 = -1073741811;
        v148 = -1073741811;
        v42 = v129;
        break;
      }
      v46 = v134;
      if ( *((_BYTE *)v7 + 356) )
        v79 = (_QWORD *)((char *)v7
                       + 64 * (unsigned __int64)(unsigned int)(v134 * *((_DWORD *)v7 + 151))
                       + (unsigned int)(8 * *((_DWORD *)v7 + 151) * (*((_DWORD *)v7 + 152) + 28))
                       + 632);
      else
        v79 = (_QWORD *)((char *)v152 + 512);
      *v79 = *(_QWORD *)(v47[6] + 16LL);
      if ( !*((_BYTE *)v136 + 3185) )
      {
        v80 = *(__int64 **)(*(_QWORD *)(v109 + *((_QWORD *)v82 + 187)) + 184LL);
        v135 = v80;
        if ( *((_BYTE *)v7 + 356) )
        {
          v81 = (__int64 **)((char *)v7
                           + 64 * (unsigned __int64)(unsigned int)(v46 * *((_DWORD *)v7 + 151))
                           + *((_DWORD *)v7 + 151) * ((8 * *((_DWORD *)v7 + 152) + 231) & 0xFFFFFFF8)
                           + 624);
          v82 = v142;
          v80 = v135;
        }
        else
        {
          v81 = (__int64 **)((char *)v7 + 568);
        }
        *v81 = v80;
      }
      *((_DWORD *)v7 + 34) |= 1 << v128;
      v110 = *(_QWORD *)(v109 + *((_QWORD *)v82 + 187));
      if ( (*(_DWORD *)(v110 + 392) & 0x10) == 0 )
        *(_QWORD *)((char *)v7 + v109 + *((unsigned int *)v7 + 138)) = *(_QWORD *)(v110 + 256);
    }
    else
    {
      v150 = v132;
      if ( *((_BYTE *)v7 + 356) )
        v45 = (_QWORD *)((char *)v7 + (unsigned int)(8 * *((_DWORD *)v7 + 151) * (*((_DWORD *)v7 + 152) + 28)) + 632);
      else
        v45 = (_QWORD *)((char *)v40 + 512);
      *v45 = *(_QWORD *)(v132[6] + 16LL);
      if ( !*((_BYTE *)v41 + 3185) )
      {
        if ( *((_BYTE *)v7 + 356) )
          v78 = (_QWORD *)((char *)v7 + (unsigned int)(8 * *((_DWORD *)v7 + 151) * (*((_DWORD *)v7 + 152) + 28)) + 624);
        else
          v78 = (_QWORD *)((char *)v7 + 568);
        *v78 = *((_QWORD *)v36 + 23);
      }
      if ( DXGADAPTER::IsDxgmms2(v41) && v36 && (*((_DWORD *)v36 + 98) & 0x10) == 0 )
        *(_QWORD *)((char *)v7 + *((unsigned int *)v7 + 138)) = *((_QWORD *)v36 + 32);
      v143 = 0;
    }
    if ( *((_BYTE *)v7 + 356) )
      v48 = (unsigned __int64)v7
          + 64 * (unsigned __int64)(unsigned int)(v46 * *((_DWORD *)v7 + 151))
          + (unsigned int)(8 * *((_DWORD *)v7 + 151) * (*((_DWORD *)v7 + 152) + 28))
          + 656;
    else
      v48 = (unsigned __int64)v7 + 504;
    v135 = (__int64 *)v48;
    v128 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64, DXGADAPTER *, unsigned int *))(*((_QWORD *)v14[95] + 1) + 400LL))(
             v151[99],
             v47[3],
             v48,
             v14[96],
             v157);
    if ( v128 < 0 )
    {
      WdLogSingleEntry2(2, v150, -1073741811);
      WdLogGlobalForLineNumber = 2744;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Failed to reference allocation for submission (0x%I64x). Returning 0x%I64x",
        (__int64)v150,
        -1073741811,
        0,
        0,
        0);
      v43 = v128;
      v42 = v129;
      break;
    }
    *(_QWORD *)&v144[8 * v143] = *v135;
    ++v126;
    v49 = v150[5];
    if ( v49 )
      v50 = (*(_DWORD *)(v49 + 4) & 8) != 0;
    else
      v50 = 0;
    if ( v50 )
      v51 = *(_QWORD *)(*(_QWORD *)(v49 + 56) + 184LL);
    else
      v51 = 0;
    if ( *((_BYTE *)v7 + 356) )
      *(_QWORD *)((char *)v7
                + 64 * v134 * *((_DWORD *)v7 + 151)
                + *((_DWORD *)v7 + 151) * ((8 * *((_DWORD *)v7 + 152) + 231) & 0xFFFFFFF8)
                + 664) = v51;
    else
      *((_QWORD *)v7 + 72) = v51;
    *(_DWORD *)v7 |= 0x1000000u;
    v52 = *p_CompositionBindingId;
    v53 = *(_QWORD *)(*(__int64 (__fastcall **)(__int128 *))(v124 + 16))(&v124);
    v54 = (*(__int64 (__fastcall **)(__int128 *))(v124 + 64))(&v124);
    v55 = (*(__int64 (__fastcall **)(__int128 *))(v124 + 104))(&v124);
    WdLogSingleEntry5(8, v149, v55, v54, v53, v52);
    WdLogGlobalForLineNumber = 2767;
    if ( (*(unsigned __int8 (__fastcall **)(__int128 *))(v124 + 344))(&v124)
      && (*((_DWORD *)v7 + 1) |= 2u,
          *((_QWORD *)v7 + 60) = (*(__int64 (__fastcall **)(__int128 *))(v124 + 352))(&v124),
          v111 = (_DWORD *)(*(__int64 (__fastcall **)(__int128 *))(v124 + 360))(&v124),
          v112 = v111,
          (*((_QWORD *)v7 + 61) = v111) != 0)
      && !v111[1] )
    {
      if ( *v111 != 64 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 2781;
        DxgkLogInternalTriageEvent(
          0,
          262146,
          -1,
          (unsigned int)L"pAuxiliaryPresentInfo->size == sizeof(D3DKMT_FLIPMANAGER_AUXILIARYPRESENTINFO)",
          2781,
          0,
          0,
          0,
          0);
      }
      v112[8] = *((_DWORD *)v7 + 29);
      v42 = v129;
      *((_QWORD *)v112 + 3) = *(_QWORD *)((char *)v129 + 412);
    }
    else
    {
      v42 = v129;
    }
    v44 = (unsigned int)(v134 + 1);
    v14 = v170;
    v34 = v131;
    v36 = v141;
    v43 = v128;
    v41 = v136;
    v40 = v152;
  }
  *((_DWORD *)v10 + 35) = v34;
  if ( v43 < 0 || (*((_DWORD *)v42 + 647) & 0x20) == 0 )
  {
    v56 = v136;
LABEL_83:
    if ( v139 && (*(_DWORD *)v7 & 0x1000000) != 0 )
    {
      v130 = 0;
      if ( *((int *)v56 + 783) < 2500
        || (v73 = ReadPresentDirtyRectsData(v41, v127, (const struct CIFlipPresentHistoryTokenData *)&v124, &v130),
            v73 >= 0) )
      {
        *((_QWORD *)v10 + 4) = v130;
      }
      else
      {
        v74 = v73;
        WdLogSingleEntry1(2, v73);
        WdLogGlobalForLineNumber = 2868;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Failed to read dirty rects data. Returning 0x%I64x",
          v74,
          0,
          0,
          0,
          0);
      }
    }
    goto LABEL_84;
  }
  memset(&v176, 0, sizeof(v176));
  v176.Flags.Value = 0x2000;
  if ( v154 )
  {
    v176.PrivateDriverDataSize = *((_DWORD *)v154 + 2);
    v176.pPrivateDriverData = (char *)v154 + 16;
  }
  P = 0;
  v183 = 0;
  PagedPoolZeroedArray<_DXGK_PRESENTALLOCATIONINFO,4>::AllocateElements(&P, v34);
  v176.pAllocationList = (DXGK_ALLOCATIONLIST *)P;
  if ( P )
  {
    v58 = *((_DWORD *)v129 + 649);
    if ( (v58 & 0x80u) == 0 || (v125 = 1, (v58 & 0x40) != 0) )
      v125 = 0;
    v59 = 0;
    v131 = 0;
    if ( v34 )
    {
      v60 = v142;
      v61 = v125;
      do
      {
        v62 = 8LL * v59;
        if ( v36 )
          v63 = *(_WORD *)(*(_QWORD *)(v62 + *((_QWORD *)v60 + 187)) + 388LL);
        else
          v63 = 0;
        v64 = 32LL * v59;
        v159 = (struct DXGCONTEXT *)v64;
        *(_WORD *)((char *)&v176.pAllocationList[1].hDeviceSpecificAllocation + v64 + 2) = v63;
        if ( v59 )
          v65 = *(_QWORD **)(v62 + *(_QWORD *)v140);
        else
          v65 = v132;
        if ( v36 )
          v61 = *(_BYTE *)(*(_QWORD *)(v62 + *((_QWORD *)v60 + 187)) + 431LL);
        *((_QWORD *)&v176.pAllocationList->hDeviceSpecificAllocation + 4 * v59) = v65[4];
        pAllocationList = v176.pAllocationList;
        AllocationGpuVirtualAddress = VIDMM_EXPORT::VidMmGetAllocationGpuVirtualAddress(
                                        v14[95],
                                        (const struct VIDMM_MULTI_ALLOC *)v65[3],
                                        v61 != 0,
                                        *(unsigned __int16 *)((char *)&v176.pAllocationList[1].hDeviceSpecificAllocation
                                                            + v64
                                                            + 2));
        *(_QWORD *)((char *)v159 + (_QWORD)pAllocationList + 8) = AllocationGpuVirtualAddress;
        v59 = v131 + 1;
        v131 = v59;
        v36 = v141;
      }
      while ( v59 < v34 );
      v10 = v164;
      v7 = v165;
    }
    v176.FlipInterval = *(_DWORD *)v130;
    v176.Flags.Value = v176.Flags.Value & 0xFFFFE8FF | (*(_DWORD *)v152 >> 11) & 0x1700;
    v176.NumSrcAllocations = v34;
    v56 = v136;
    v68 = 0;
    if ( !*((_BYTE *)v136 + 3185) )
      v68 = (void *)*((_QWORD *)v36 + 23);
    v128 = ADAPTER_RENDER::DdiPresent((ADAPTER_RENDER *)v14, v68, &v176);
    v41 = (DXGADAPTER *)P;
    if ( v128 >= 0 )
    {
      if ( P != v182 && P )
        ExFreePoolWithTag(P, 0);
      P = 0;
      v183 = 0;
      goto LABEL_83;
    }
    if ( P != v182 && P )
      ExFreePoolWithTag(P, 0);
  }
  P = 0;
  v183 = 0;
LABEL_84:
  v57 = v128;
  if ( v128 < 0 )
  {
    v113 = 0;
    v114 = v126;
    if ( v126 )
    {
      v115 = v141;
      v116 = v156;
      do
      {
        if ( v115 )
          v117 = *(_DWORD *)(*(_QWORD *)(8LL * v113 + v116) + 388LL);
        else
          LOBYTE(v117) = 0;
        VIDMM_EXPORT::VidMmUnreferencePrimaryAllocation(
          v14[95],
          v14[96],
          1 << v117,
          *(struct VIDMM_ALLOC **)&v144[8 * v113++],
          v123,
          v157);
      }
      while ( v113 < v114 );
    }
    v118 = *p_CompositionBindingId;
    v119 = *(_QWORD *)(*(__int64 (__fastcall **)(__int128 *, struct VIDSCH_SUBMIT_DATA_BASE *, __int64, DXGADAPTER *))(v124 + 16))(
                        &v124,
                        v40,
                        v44,
                        v42);
    v120 = (*(__int64 (__fastcall **)(__int128 *))(v124 + 64))(&v124);
    v121 = (*(__int64 (__fastcall **)(__int128 *))(v124 + 104))(&v124);
    WdLogSingleEntry5(8, v149, v121, v120, v119, v118);
    WdLogGlobalForLineNumber = 2896;
    LOBYTE(v122) = 1;
    (*(void (__fastcall **)(__int128 *, __int64))(v124 + 232))(&v124, v122);
    *(_DWORD *)v152 &= ~0x1000000u;
    v57 = 0;
  }
  PagedPoolArray<DXGALLOCATIONREFERENCE,4>::~PagedPoolArray<DXGALLOCATIONREFERENCE,4>(v179);
  if ( v167 != v168 && v167 )
    ExFreePoolWithTag(v167, 0);
  v167 = 0;
  v169 = 0;
  DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v132);
  (*(void (__fastcall **)(__int128 *, __int64))v124)(&v124, 1);
  return v57;
}

```

## disassembly

```asm
0x14037be6c  push    rbx
0x14037be6e  push    rsi
0x14037be6f  push    rdi
0x14037be70  push    r12
0x14037be72  push    r13
0x14037be74  push    r14
0x14037be76  push    r15
0x14037be78  sub     rsp, 3D0h
0x14037be7f  mov     rax, cs:__security_cookie
0x14037be86  xor     rax, rsp
0x14037be89  mov     [rsp+408h+var_48], rax
0x14037be91  mov     rbx, r9
0x14037be94  mov     [rsp+408h+var_318], rbx
0x14037be9c  mov     r13, r8
0x14037be9f  mov     [rsp+408h+var_250], r8
0x14037bea7  mov     r12, rdx
0x14037beaa  mov     [rsp+408h+var_310], rdx
0x14037beb2  mov     rdi, rcx
0x14037beb5  mov     [rsp+408h+var_2E8], rcx
0x14037bebd  mov     [rsp+408h+var_1F8], r8
0x14037bec5  mov     [rsp+408h+var_1F0], rcx
0x14037becd  mov     [rsp+408h+var_1E8], rdx
0x14037bed5  mov     r15, r8
0x14037bed8  mov     [rsp+408h+var_258], r8
0x14037bee0  mov     [rsp+408h+var_298], rbx
0x14037bee8  mov     rsi, [rsp+408h+arg_20]
0x14037bef0  mov     [rsp+408h+var_360], rsi
0x14037bef8  mov     rax, [rsp+408h+arg_28]
0x14037bf00  mov     [rsp+408h+var_2C0], rax
0x14037bf08  call    ?IsIFlipSupported@CIFlipPresentHistoryToken@@SA_NPEBU_D3DKMT_PRESENTHISTORYTOKEN@@@Z; CIFlipPresentHistoryToken::IsIFlipSupported(_D3DKMT_PRESENTHISTORYTOKEN const *)
0x14037bf0d  xor     r14d, r14d
0x14037bf10  test    al, al
0x14037bf12  jz      loc_14037C7E0
0x14037bf18  test    rbx, rbx
0x14037bf1b  jnz     loc_14037CEBB
0x14037bf21  xorps   xmm0, xmm0
0x14037bf24  movups  [rsp+408h+var_388], xmm0
0x14037bf2c  mov     eax, [rdi]
0x14037bf2e  cmp     eax, 2
0x14037bf31  jnz     loc_14037CE79
0x14037bf37  lea     rdx, [rdi+10h]; struct _D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN *
0x14037bf3b  lea     rcx, [rsp+408h+var_388]; this
0x14037bf43  call    ??0CIFlipPresentHistoryTokenRedirectedFlip@@QEAA@PEBU_D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN@@@Z; CIFlipPresentHistoryTokenRedirectedFlip::CIFlipPresentHistoryTokenRedirectedFlip(_D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN const *)
0x14037bf48  test    rbx, rbx
0x14037bf4b  jz      loc_14037D44E
0x14037bf51  mov     rcx, [rbx+10h]
0x14037bf55  mov     [rsp+408h+var_2D8], rcx
0x14037bf5d  mov     rax, [rcx+10h]
0x14037bf61  mov     rdi, [rax+10h]
0x14037bf65  mov     [rsp+408h+var_268], rdi
0x14037bf6d  mov     [rsp+408h+var_338], rdi
0x14037bf75  test    rbx, rbx
0x14037bf78  jz      loc_14037D463
0x14037bf7e  mov     [r13+18h], r14
0x14037bf82  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x14037bf87  mov     r9, rax
0x14037bf8a  mov     [rsp+408h+var_200], rax
0x14037bf92  mov     rsi, [rdi+0CB8h]
0x14037bf99  mov     [rsp+408h+var_208], rsi
0x14037bfa1  mov     rcx, [rdi+0CB0h]
0x14037bfa8  mov     rax, r14
0x14037bfab  test    rcx, rcx
0x14037bfae  cmovnz  rax, rcx
0x14037bfb2  mov     [rsp+408h+var_368], rax
0x14037bfba  mov     rcx, rbx
0x14037bfbd  neg     rcx
0x14037bfc0  sbb     rax, rax
0x14037bfc3  and     rax, r12
0x14037bfc6  mov     [rsp+408h+var_2B8], rax
0x14037bfce  test    rbx, rbx
0x14037bfd1  jz      loc_14037D475
0x14037bfd7  mov     eax, [rax+14h]
0x14037bfda  mov     [rsp+408h+var_374], eax
0x14037bfe1  mov     r8d, eax
0x14037bfe4  lea     rdx, [rsp+408h+var_350]
0x14037bfec  mov     rcx, r9
0x14037bfef  call    ?GetAllocationSafe@DXGPROCESS@@QEAA?AVDXGALLOCATIONREFERENCE@@I@Z; DXGPROCESS::GetAllocationSafe(uint)
0x14037bff4  mov     rax, [rsp+408h+var_350]
0x14037bffc  test    rax, rax
0x14037bfff  jz      loc_14037C7C6
0x14037c005  mov     rcx, [rax+8]
0x14037c009  mov     r8, [rcx+10h]
0x14037c00d  mov     rcx, [rsp+408h+var_2D8]
0x14037c015  mov     rcx, [rcx+10h]
0x14037c019  mov     rdx, [rcx+10h]
0x14037c01d  cmp     [r8+10h], rdx
0x14037c021  jnz     loc_14037C7C6
0x14037c027  mov     [rsp+408h+var_1E0], rsi
0x14037c02f  cmp     [rsp+408h+var_2C0], r14
0x14037c037  jnz     loc_14037C7F5
0x14037c03d  mov     r12d, 1
0x14037c043  test    rbx, rbx
0x14037c046  jz      loc_14037D485
0x14037c04c  mov     rcx, [rsp+408h+var_310]
0x14037c054  mov     rcx, [rcx+5D8h]
0x14037c05b  mov     [rsp+408h+var_260], rcx
0x14037c063  mov     [rsp+408h+var_2B0], rcx
0x14037c06b  mov     rcx, [rax+30h]
0x14037c06f  mov     eax, [rcx+4]
0x14037c072  shr     eax, 6
0x14037c075  and     eax, 0Fh
0x14037c078  mov     [rsp+408h+var_348], eax
0x14037c07f  mov     [rsp+408h+var_2F8], r14d
0x14037c087  mov     [rsp+408h+var_328], r14d
0x14037c08f  mov     [rsp+408h+var_2F4], r14d
0x14037c097  mov     [rsp+408h+var_2F0], r14d
0x14037c09f  mov     [rsp+408h+var_370], r14d
0x14037c0a7  mov     rax, qword ptr [rsp+408h+var_388]
0x14037c0af  mov     rax, [rax+18h]
0x14037c0b3  lea     rcx, [rsp+408h+var_388]
0x14037c0bb  call    _guard_dispatch_icall
0x14037c0c0  mov     rcx, [rax]
0x14037c0c3  mov     [rsp+408h+var_270], rcx
0x14037c0cb  mov     [rsp+408h+var_330], r14d
0x14037c0d3  xorps   xmm0, xmm0
0x14037c0d6  movups  [rsp+408h+var_128], xmm0
0x14037c0de  xorps   xmm1, xmm1
0x14037c0e1  movups  [rsp+408h+var_118], xmm1
0x14037c0e9  mov     al, [r13+164h]
0x14037c0f0  neg     al
0x14037c0f2  sbb     rcx, rcx
0x14037c0f5  and     ecx, 0F0h
0x14037c0fb  lea     rax, [r13+210h]
0x14037c102  add     rax, rcx
0x14037c105  mov     qword ptr [rsp+408h+var_320], rax
0x14037c10d  mov     rbx, [rsi+2E0h]
0x14037c114  mov     rax, [rsp+408h+var_2E8]
0x14037c11c  add     rax, 8
0x14037c120  mov     [rsp+408h+var_2A0], rax
0x14037c128  mov     rdi, [rax]
0x14037c12b  mov     rax, qword ptr [rsp+408h+var_388]
0x14037c133  mov     rax, [rax+10h]
0x14037c137  lea     rcx, [rsp+408h+var_388]
0x14037c13f  call    _guard_dispatch_icall
0x14037c144  mov     rcx, [rbx+8]
0x14037c148  mov     r10, [rcx+1B0h]
0x14037c14f  lea     rcx, [rsp+408h+var_118]
0x14037c157  mov     [rsp+408h+var_3A0], rcx
0x14037c15c  lea     rcx, [rsp+408h+var_128]
0x14037c164  mov     [rsp+408h+var_3A8], rcx
0x14037c169  lea     rcx, [rsp+408h+var_330]
0x14037c171  mov     [rsp+408h+var_3B0], rcx
0x14037c176  lea     rcx, [rsp+408h+var_2F0]
0x14037c17e  mov     [rsp+408h+var_3B8], rcx
0x14037c183  lea     rcx, [rsp+408h+var_2F4]
0x14037c18b  mov     [rsp+408h+var_3C0], rcx
0x14037c190  lea     rcx, [rsp+408h+var_270]
0x14037c198  mov     [rsp+408h+var_3C8], rcx
0x14037c19d  lea     rcx, [rsp+408h+var_370]
0x14037c1a5  mov     qword ptr [rsp+408h+var_3D0], rcx
0x14037c1aa  lea     rcx, [rsp+408h+var_328]
0x14037c1b2  mov     [rsp+408h+var_3D8], rcx
0x14037c1b7  lea     rcx, [rsp+408h+var_2F8]
0x14037c1bf  mov     [rsp+408h+var_3E0], rcx
0x14037c1c4  mov     rcx, qword ptr [rsp+408h+var_320]
0x14037c1cc  mov     [rsp+408h+var_3E8], rcx; bool
0x14037c1d1  mov     r9, rdi
0x14037c1d4  mov     r8, rax
0x14037c1d7  lea     rdx, [rsp+408h+var_348]
0x14037c1df  mov     rcx, [rsi+2E8h]
0x14037c1e6  mov     rax, r10
0x14037c1e9  call    _guard_dispatch_icall
0x14037c1ee  mov     rax, qword ptr [rsp+408h+var_388]
0x14037c1f6  mov     rax, [rax+20h]
0x14037c1fa  mov     rdx, [rsp+408h+var_270]
0x14037c202  lea     rcx, [rsp+408h+var_388]
0x14037c20a  call    _guard_dispatch_icall
0x14037c20f  mov     rax, qword ptr [rsp+408h+var_388]
0x14037c217  mov     rax, [rax+30h]
0x14037c21b  mov     edx, [rsp+408h+var_348]
0x14037c222  lea     rcx, [rsp+408h+var_388]
0x14037c22a  call    _guard_dispatch_icall
0x14037c22f  mov     eax, [rsp+408h+var_348]
0x14037c236  mov     [r13+74h], eax
0x14037c23a  mov     rax, qword ptr [rsp+408h+var_388]
0x14037c242  mov     rax, [rax+10h]
0x14037c246  lea     rcx, [rsp+408h+var_388]
0x14037c24e  call    _guard_dispatch_icall
0x14037c253  mov     rdx, rax; SourceLuid
0x14037c256  lea     rcx, [r13+9Ch]; DestinationLuid
0x14037c25d  call    cs:__imp_RtlCopyLuid
0x14037c264  nop     dword ptr [rax+rax+00h]
0x14037c269  mov     rax, [rsp+408h+var_2A0]
0x14037c271  mov     rax, [rax]
0x14037c274  mov     [r13+0A8h], rax
0x14037c27b  btr     dword ptr [r13+0], 10h
0x14037c281  mov     ecx, [r13+0]
0x14037c285  mov     rbx, [rsp+408h+var_318]
0x14037c28d  test    rbx, rbx
0x14037c290  jnz     loc_14037CF58
0x14037c296  mov     rax, qword ptr [rsp+408h+var_388]
0x14037c29e  mov     rax, [rax+0C8h]
0x14037c2a5  lea     rcx, [rsp+408h+var_388]
0x14037c2ad  call    _guard_dispatch_icall
0x14037c2b2  movzx   ecx, al
0x14037c2b5  mov     eax, [r13+0]
0x14037c2b9  shl     ecx, 3
0x14037c2bc  xor     ecx, eax
0x14037c2be  and     ecx, 8
0x14037c2c1  xor     ecx, eax
0x14037c2c3  mov     [r13+0], ecx
0x14037c2c7  mov     rax, qword ptr [rsp+408h+var_388]
0x14037c2cf  mov     rax, [rax+0D0h]
0x14037c2d6  lea     rcx, [rsp+408h+var_388]
0x14037c2de  call    _guard_dispatch_icall
0x14037c2e3  movzx   ecx, al
0x14037c2e6  mov     eax, [r13+0]
0x14037c2ea  shl     ecx, 4
0x14037c2ed  xor     ecx, eax
0x14037c2ef  and     ecx, 10h
0x14037c2f2  xor     ecx, eax
0x14037c2f4  mov     [r13+0], ecx
0x14037c2f8  mov     rax, qword ptr [rsp+408h+var_388]
0x14037c300  mov     rax, [rax+0D8h]
0x14037c307  lea     rcx, [rsp+408h+var_388]
0x14037c30f  call    _guard_dispatch_icall
0x14037c314  movzx   ecx, al
0x14037c317  mov     eax, [r13+0]
0x14037c31b  shl     ecx, 1Ch
0x14037c31e  xor     ecx, eax
0x14037c320  and     ecx, 10000000h
0x14037c326  xor     ecx, eax
0x14037c328  mov     [r13+0], ecx
0x14037c32c  mov     rax, qword ptr [rsp+408h+var_388]
0x14037c334  mov     rax, [rax+0E0h]
0x14037c33b  lea     rcx, [rsp+408h+var_388]
0x14037c343  call    _guard_dispatch_icall
0x14037c348  movzx   ecx, al
0x14037c34b  mov     eax, [r13+4]
0x14037c34f  shl     ecx, 6
0x14037c352  xor     ecx, eax
0x14037c354  and     ecx, 40h
0x14037c357  xor     ecx, eax
0x14037c359  mov     [r13+4], ecx
0x14037c35d  mov     rax, qword ptr [rsp+408h+var_388]
0x14037c365  mov     rax, [rax+140h]
0x14037c36c  lea     rcx, [rsp+408h+var_388]
0x14037c374  call    _guard_dispatch_icall
0x14037c379  movzx   ecx, al
0x14037c37c  mov     eax, [r13+4]
0x14037c380  shl     ecx, 8
0x14037c383  xor     ecx, eax
0x14037c385  and     ecx, 100h
0x14037c38b  xor     ecx, eax
0x14037c38d  mov     [r13+4], ecx
0x14037c391  mov     rax, qword ptr [rsp+408h+var_388]
0x14037c399  mov     rax, [rax+148h]
0x14037c3a0  lea     rcx, [rsp+408h+var_388]
0x14037c3a8  call    _guard_dispatch_icall
0x14037c3ad  movzx   ecx, al
0x14037c3b0  mov     eax, [r13+4]
0x14037c3b4  shl     ecx, 9
0x14037c3b7  xor     ecx, eax
0x14037c3b9  and     ecx, 200h
0x14037c3bf  xor     ecx, eax
0x14037c3c1  mov     [r13+4], ecx
0x14037c3c5  mov     rax, qword ptr [rsp+408h+var_388]
0x14037c3cd  mov     rax, [rax+38h]
0x14037c3d1  mov     rdi, [rsp+408h+var_338]
0x14037c3d9  mov     rdx, rdi
0x14037c3dc  lea     rcx, [rsp+408h+var_388]
0x14037c3e4  call    _guard_dispatch_icall
0x14037c3e9  mov     rax, qword ptr [rsp+408h+var_388]
0x14037c3f1  mov     rax, [rax+40h]
0x14037c3f5  lea     rcx, [rsp+408h+var_388]
0x14037c3fd  call    _guard_dispatch_icall
0x14037c402  mov     [r13+70h], eax
0x14037c406  mov     rax, qword ptr [rsp+408h+var_388]
0x14037c40e  mov     rax, [rax+48h]
0x14037c412  lea     rcx, [rsp+408h+var_388]
0x14037c41a  call    _guard_dispatch_icall
0x14037c41f  mov     ecx, [rax]
0x14037c421  mov     [r13+0C0h], ecx
0x14037c428  mov     rax, qword ptr [rsp+408h+var_388]
0x14037c430  mov     rax, [rax+0C0h]
0x14037c437  lea     rcx, [rsp+408h+var_388]
0x14037c43f  call    _guard_dispatch_icall
0x14037c444  movzx   ecx, al
0x14037c447  mov     eax, [r13+0]
0x14037c44b  shl     ecx, 19h
0x14037c44e  xor     ecx, eax
0x14037c450  and     ecx, 2000000h
0x14037c456  xor     ecx, eax
0x14037c458  mov     [r13+0], ecx
0x14037c45c  mov     rax, qword ptr [rsp+408h+var_388]
0x14037c464  mov     rax, [rax+50h]
0x14037c468  lea     rcx, [rsp+408h+var_388]
0x14037c470  call    _guard_dispatch_icall
0x14037c475  mov     [r13+90h], eax
0x14037c47c  mov     rax, qword ptr [rsp+408h+var_388]
0x14037c484  mov     rax, [rax+58h]
0x14037c488  lea     rcx, [rsp+408h+var_388]
0x14037c490  call    _guard_dispatch_icall
0x14037c495  mov     [r13+94h], eax
0x14037c49c  test    rbx, rbx
0x14037c49f  jz      loc_14037D48D
0x14037c4a5  mov     eax, [rbx+180h]
0x14037c4ab  mov     [r13+88h], eax
0x14037c4b2  mov     al, [r13+164h]
0x14037c4b9  test    al, al
  ... truncated ...
```
