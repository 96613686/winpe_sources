# PrepareIndependentFlipToken(_D3DKMT_PRESENTHISTORYTOKEN *,DXGK_PRESENT_PARAMS *,VIDSCH_SUBMIT_DATA_BASE *,DXGCONTEXT *,_PRESENT_REDIRECTED_PARAMS *,CRefCountedBuffer *)

- ea: `0x14037be6c`
- end: `0x14037e3bf`
- name: `?PrepareIndependentFlipToken@@YAJPEAU_D3DKMT_PRESENTHISTORYTOKEN@@PEAUDXGK_PRESENT_PARAMS@@PEAUVIDSCH_SUBMIT_DATA_BASE@@PEAVDXGCONTEXT@@PEAU_PRESENT_REDIRECTED_PARAMS@@PEAVCRefCountedBuffer@@@Z`
- size: `9555`
- prototype: `__int64 __fastcall(struct _D3DKMT_PRESENTHISTORYTOKEN *, __int64, struct VIDSCH_SUBMIT_DATA_BASE *, struct DXGCONTEXT *, struct _PRESENT_REDIRECTED_PARAMS *, struct CRefCountedBuffer *)`
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
        __int64 a2,
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
  unsigned int v34; // edi
  unsigned __int8 IsDxgmms2; // al
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
  unsigned int v59; // r9d
  __int64 v60; // r15
  char v61; // r13
  __int64 v62; // r8
  __int16 v63; // r10
  __int64 v64; // rdx
  _QWORD *v65; // r10
  DXGK_ALLOCATIONLIST *pAllocationList; // rbx
  unsigned __int64 AllocationGpuVirtualAddress; // rax
  void *v68; // rdx
  __int64 v69; // r8
  int v70; // eax
  int v71; // ecx
  int v72; // edx
  int v73; // eax
  __int64 v74; // rbx
  __int64 v75; // rax
  __int64 v76; // r8
  __int64 v77; // rax
  __int128 v78; // xmm1
  _QWORD *v79; // r9
  _QWORD *v80; // rax
  __int64 *v81; // rax
  __int64 **v82; // rdx
  __int64 v83; // r11
  VIDSCH_EXPORT *v84; // rdi
  unsigned __int64 v85; // rbx
  const struct _LUID *v86; // rax
  VIDSCH_EXPORT *v87; // rdi
  unsigned __int64 v88; // rbx
  const struct _LUID *v89; // rax
  __int64 v90; // rdx
  _DWORD *v91; // rbx
  int v92; // ebx
  VIDSCH_EXPORT *v93; // rdi
  unsigned __int64 v94; // rbx
  const struct _LUID *v95; // rax
  __int64 v96; // rdx
  unsigned __int8 PostCompositionStretching; // al
  bool v98; // r9
  __int64 *v99; // rax
  __int64 *v100; // rdi
  VIDSCH_EXPORT *v101; // rdi
  unsigned __int64 v102; // rbx
  const struct _LUID *v103; // rax
  __int64 v104; // rdx
  unsigned int v105; // eax
  unsigned int v106; // eax
  __int64 v107; // rax
  _OWORD *v108; // rax
  __int64 AllocationSafe; // rax
  __int64 v110; // r9
  __int64 v111; // rdx
  _DWORD *v112; // rax
  _DWORD *v113; // rbx
  unsigned int v114; // edi
  enum _D3DDDI_HDR_METADATA_TYPE v115; // r15d
  struct DXGCONTEXT *v116; // rbx
  __int64 v117; // r13
  int v118; // ecx
  UINT64 v119; // rsi
  __int64 v120; // rdi
  unsigned int v121; // ebx
  __int64 v122; // rax
  __int64 v123; // rdx
  bool v124; // [rsp+20h] [rbp-3E8h]
  __int128 v125; // [rsp+80h] [rbp-388h] BYREF
  char v126; // [rsp+90h] [rbp-378h]
  enum _D3DDDI_HDR_METADATA_TYPE v127; // [rsp+94h] [rbp-374h] BYREF
  unsigned int v128; // [rsp+98h] [rbp-370h] BYREF
  int v129; // [rsp+9Ch] [rbp-36Ch]
  struct ADAPTER_DISPLAY *v130; // [rsp+A0h] [rbp-368h]
  struct CRefCountedBuffer *v131; // [rsp+A8h] [rbp-360h] BYREF
  int v132; // [rsp+B0h] [rbp-358h]
  _QWORD *v133; // [rsp+B8h] [rbp-350h] BYREF
  unsigned int v134; // [rsp+C0h] [rbp-348h] BYREF
  int v135; // [rsp+C4h] [rbp-344h]
  __int64 *v136; // [rsp+C8h] [rbp-340h]
  DXGADAPTER *v137; // [rsp+D0h] [rbp-338h]
  int v138; // [rsp+D8h] [rbp-330h]
  unsigned int v139; // [rsp+DCh] [rbp-32Ch] BYREF
  int v140; // [rsp+E0h] [rbp-328h]
  bool v141[8]; // [rsp+E8h] [rbp-320h]
  struct DXGCONTEXT *v142; // [rsp+F0h] [rbp-318h]
  __int64 v143; // [rsp+F8h] [rbp-310h]
  __int64 v144; // [rsp+100h] [rbp-308h]
  _BYTE *v145; // [rsp+108h] [rbp-300h]
  int v146; // [rsp+110h] [rbp-2F8h]
  int v147; // [rsp+114h] [rbp-2F4h]
  int v148; // [rsp+118h] [rbp-2F0h]
  int v149; // [rsp+11Ch] [rbp-2ECh]
  struct _D3DKMT_PRESENTHISTORYTOKEN *v150; // [rsp+120h] [rbp-2E8h]
  _QWORD *v151; // [rsp+128h] [rbp-2E0h]
  _QWORD *v152; // [rsp+130h] [rbp-2D8h]
  struct VIDSCH_SUBMIT_DATA_BASE *v153; // [rsp+138h] [rbp-2D0h]
  int v154; // [rsp+140h] [rbp-2C8h] BYREF
  struct CRefCountedBuffer *v155; // [rsp+148h] [rbp-2C0h]
  __int64 v156; // [rsp+150h] [rbp-2B8h]
  __int64 v157; // [rsp+158h] [rbp-2B0h]
  unsigned int *v158; // [rsp+160h] [rbp-2A8h]
  UINT64 *p_CompositionBindingId; // [rsp+168h] [rbp-2A0h]
  struct DXGCONTEXT *v160; // [rsp+170h] [rbp-298h]
  struct _D3DDDI_HDR_METADATA_HDR10 v161; // [rsp+178h] [rbp-290h] BYREF
  __int64 v162; // [rsp+198h] [rbp-270h]
  __int64 v163; // [rsp+1A0h] [rbp-268h]
  __int64 v164; // [rsp+1A8h] [rbp-260h]
  struct VIDSCH_SUBMIT_DATA_BASE *v165; // [rsp+1B0h] [rbp-258h]
  struct VIDSCH_SUBMIT_DATA_BASE *v166; // [rsp+1B8h] [rbp-250h]
  struct tagRECT v167; // [rsp+1C0h] [rbp-248h] BYREF
  PVOID v168; // [rsp+1D0h] [rbp-238h]
  _BYTE v169[32]; // [rsp+1D8h] [rbp-230h] BYREF
  unsigned int v170; // [rsp+1F8h] [rbp-210h]
  DXGADAPTER **v171; // [rsp+200h] [rbp-208h]
  struct DXGPROCESS *v172; // [rsp+208h] [rbp-200h]
  struct VIDSCH_SUBMIT_DATA_BASE *v173; // [rsp+210h] [rbp-1F8h]
  struct _D3DKMT_PRESENTHISTORYTOKEN *v174; // [rsp+218h] [rbp-1F0h]
  __int64 v175; // [rsp+220h] [rbp-1E8h]
  DXGADAPTER **v176; // [rsp+228h] [rbp-1E0h]
  _DXGKARG_PRESENT v177; // [rsp+230h] [rbp-1D8h] BYREF
  __int128 v178; // [rsp+2E0h] [rbp-128h] BYREF
  struct tagRECT v179; // [rsp+2F0h] [rbp-118h] BYREF
  _QWORD v180[5]; // [rsp+300h] [rbp-108h] BYREF
  int v181; // [rsp+328h] [rbp-E0h]
  PVOID P; // [rsp+330h] [rbp-D8h] BYREF
  _BYTE v183[128]; // [rsp+338h] [rbp-D0h] BYREF
  int v184; // [rsp+3B8h] [rbp-50h]

  v142 = a4;
  v7 = a3;
  v166 = a3;
  v143 = a2;
  v150 = a1;
  v173 = a3;
  v174 = a1;
  v175 = a2;
  v10 = a3;
  v165 = a3;
  v160 = a4;
  v131 = a5;
  v155 = a6;
  v11 = 0;
  if ( !CIFlipPresentHistoryToken::IsIFlipSupported(a1) || a4 && !a2 )
    return 0;
  v125 = 0;
  if ( a1->Model == D3DKMT_PM_REDIRECTED_FLIP )
  {
    CIFlipPresentHistoryTokenRedirectedFlip::CIFlipPresentHistoryTokenRedirectedFlip(
      (CIFlipPresentHistoryTokenRedirectedFlip *)&v125,
      &a1->Token.Flip);
  }
  else if ( a1->Model == D3DKMT_PM_FLIPMANAGER )
  {
    CIFlipPresentHistoryTokenFlipManager::CIFlipPresentHistoryTokenFlipManager(
      (CIFlipPresentHistoryTokenFlipManager *)&v125,
      (const struct _D3DKMT_FLIPMANAGER_PRESENTHISTORYTOKEN *)&a1->Token);
  }
  if ( a4 )
  {
    v152 = (_QWORD *)*((_QWORD *)a4 + 2);
    v12 = *(_QWORD *)(v152[2] + 16LL);
  }
  else
  {
    v12 = *((_QWORD *)a5 + 3);
    v152 = (_QWORD *)*((_QWORD *)a5 + 4);
  }
  v163 = v12;
  v137 = (DXGADAPTER *)v12;
  if ( !a4 && !*(_BYTE *)(v12 + 3185) )
    goto LABEL_51;
  *((_QWORD *)v7 + 3) = 0;
  Current = DXGPROCESS::GetCurrent();
  v172 = Current;
  v14 = *(DXGADAPTER ***)(v12 + 3256);
  v171 = v14;
  v15 = 0;
  if ( *(_QWORD *)(v12 + 3248) )
    v15 = *(struct ADAPTER_DISPLAY **)(v12 + 3248);
  v130 = v15;
  v156 = a2 & -(__int64)(a4 != 0);
  if ( a4 )
    v16 = *(_DWORD *)((a2 & -(__int64)(a4 != 0)) + 0x14);
  else
    v16 = *((_DWORD *)v131 + 1);
  v127 = v16;
  DXGPROCESS::GetAllocationSafe(Current, &v133, (unsigned int)v16);
  v17 = v133;
  if ( !v133 || *(_QWORD *)(*(_QWORD *)(v133[1] + 16LL) + 16LL) != *(_QWORD *)(v152[2] + 16LL) )
  {
LABEL_50:
    DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v133);
LABEL_51:
    CIFlipPresentHistoryToken::~CIFlipPresentHistoryToken((CIFlipPresentHistoryToken *)&v125);
    return 0;
  }
  v176 = v14;
  if ( v155 )
  {
    v39 = v133[5];
    if ( v39 )
    {
      if ( (*(_DWORD *)(v39 + 4) & 1) != 0 )
        *((_QWORD *)v7 + 3) = *(_QWORD *)(*(_QWORD *)(v39 + 56) + 176LL);
    }
  }
  if ( a4 )
    v18 = *(_QWORD *)(v143 + 1496);
  else
    v18 = 0;
  v164 = v18;
  v157 = v18;
  v134 = (*(_DWORD *)(v17[6] + 4LL) >> 6) & 0xF;
  v146 = 0;
  v140 = 0;
  v147 = 0;
  v148 = 0;
  v128 = 0;
  v162 = *(_QWORD *)(*(__int64 (__fastcall **)(__int128 *))(v125 + 24))(&v125);
  v138 = 0;
  v178 = 0;
  v179 = 0;
  *(_QWORD *)v141 = (char *)v7 + (*((_BYTE *)v7 + 356) != 0 ? 0xF0 : 0) + 528;
  v19 = v14[92];
  p_CompositionBindingId = &v150->CompositionBindingId;
  CompositionBindingId = v150->CompositionBindingId;
  v21 = (*(__int64 (__fastcall **)(__int128 *))(v125 + 16))(&v125);
  v124 = v141[0];
  (*(void (__fastcall **)(DXGADAPTER *, unsigned int *, __int64, UINT64))(*((_QWORD *)v19 + 1) + 432LL))(
    v14[93],
    &v134,
    v21,
    CompositionBindingId);
  (*(void (__fastcall **)(__int128 *, __int64))(v125 + 32))(&v125, v162);
  (*(void (__fastcall **)(__int128 *, _QWORD))(v125 + 48))(&v125, v134);
  *((_DWORD *)v7 + 29) = v134;
  v22 = (struct _LUID *)(*(__int64 (__fastcall **)(__int128 *))(v125 + 16))(&v125);
  RtlCopyLuid((PLUID)((char *)v7 + 156), v22);
  *((_QWORD *)v7 + 21) = *p_CompositionBindingId;
  *(_DWORD *)v7 &= ~0x10000u;
  v23 = v142;
  if ( v142 )
  {
    v69 = v156;
    v70 = *(_DWORD *)v7 ^ (*(_DWORD *)(v156 + 88) ^ *(_DWORD *)v7) & 4;
    *(_DWORD *)v7 = v70;
    v71 = v70 ^ (v70 ^ (4 * *(_DWORD *)(v69 + 88))) & 0x80000;
    *(_DWORD *)v7 = v71;
    v72 = v71 ^ (v71 ^ (4 * *(_DWORD *)(v69 + 88))) & 0x100000;
    *(_DWORD *)v7 = v72;
    *(_DWORD *)v7 = v72 ^ (v72 ^ (4 * *(_DWORD *)(v69 + 88))) & 0x200000;
  }
  *(_DWORD *)v7 ^= ((unsigned __int8)*(_DWORD *)v7
                  ^ (unsigned __int8)(8 * (*(__int64 (__fastcall **)(__int128 *))(v125 + 200))(&v125)))
                 & 8;
  *(_DWORD *)v7 ^= ((unsigned __int8)*(_DWORD *)v7
                  ^ (unsigned __int8)(16 * (*(__int64 (__fastcall **)(__int128 *))(v125 + 208))(&v125)))
                 & 0x10;
  *(_DWORD *)v7 ^= (*(_DWORD *)v7
                  ^ ((*(unsigned __int8 (__fastcall **)(__int128 *))(v125 + 216))(&v125) << 28))
                 & 0x10000000;
  *((_DWORD *)v7 + 1) ^= ((unsigned __int8)*((_DWORD *)v7 + 1)
                        ^ (unsigned __int8)((*(unsigned __int8 (__fastcall **)(__int128 *))(v125 + 224))(&v125) << 6))
                       & 0x40;
  *((_DWORD *)v7 + 1) ^= ((unsigned __int16)*((_DWORD *)v7 + 1)
                        ^ (unsigned __int16)((*(unsigned __int8 (__fastcall **)(__int128 *))(v125 + 320))(&v125) << 8))
                       & 0x100;
  *((_DWORD *)v7 + 1) ^= ((unsigned __int16)*((_DWORD *)v7 + 1)
                        ^ (unsigned __int16)((*(unsigned __int8 (__fastcall **)(__int128 *))(v125 + 328))(&v125) << 9))
                       & 0x200;
  v24 = v137;
  (*(void (__fastcall **)(__int128 *, DXGADAPTER *))(v125 + 56))(&v125, v137);
  *((_DWORD *)v7 + 28) = (*(__int64 (__fastcall **)(__int128 *))(v125 + 64))(&v125);
  *((_DWORD *)v7 + 48) = *(_DWORD *)(*(__int64 (__fastcall **)(__int128 *))(v125 + 72))(&v125);
  *(_DWORD *)v7 ^= (*(_DWORD *)v7
                  ^ ((*(unsigned __int8 (__fastcall **)(__int128 *))(v125 + 192))(&v125) << 25))
                 & 0x2000000;
  *((_DWORD *)v7 + 36) = (*(__int64 (__fastcall **)(__int128 *))(v125 + 80))(&v125);
  *((_DWORD *)v7 + 37) = (*(__int64 (__fastcall **)(__int128 *))(v125 + 88))(&v125);
  if ( v23 )
    v25 = *((_DWORD *)v23 + 96);
  else
    v25 = 1;
  *((_DWORD *)v7 + 34) = v25;
  v26 = *((_BYTE *)v7 + 356);
  if ( v26 )
    v158 = (unsigned int *)((char *)v7 + 616);
  else
    v158 = 0;
  if ( v26 )
    *((_DWORD *)v7 + 162) = -1;
  if ( bTracingEnabled )
    *((_QWORD *)v7 + 23) = VIDMM_EXPORT::VidMmETWAllocationHandle(v14[95], v14[96], v127);
  v27 = (*(__int64 (__fastcall **)(__int128 *))(v125 + 96))(&v125);
  v131 = (struct VIDSCH_SUBMIT_DATA_BASE *)((char *)v7 + 124);
  *((_DWORD *)v7 + 31) = v27;
  v28 = (int *)((char *)v7 + 124);
  v154 = 1;
  if ( !v27
    && (!(*(unsigned __int8 (__fastcall **)(__int128 *))(v125 + 216))(&v125) || (*((_DWORD *)v24 + 647) & 0x40) == 0) )
  {
    v28 = &v154;
  }
  v29 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *))(*((_QWORD *)v14[92] + 1) + 536LL))(v152[100], v134, v28);
  *((_DWORD *)v7 + 30) = v29;
  if ( v29 != 5 && *(_DWORD *)v131 )
  {
    (*(__int64 (__fastcall **)(__int128 *))(v125 + 64))(&v125);
    v75 = (*(__int64 (__fastcall **)(__int128 *))(v125 + 104))(&v125);
    WdLogSingleEntry4(8, v150, v75);
    WdLogGlobalForLineNumber = 2291;
    goto LABEL_59;
  }
  if ( !v146 )
  {
    if ( v147 )
    {
      v127 = D3DDDI_HDR_METADATA_TYPE_NONE;
      v131 = 0;
      v84 = v14[92];
      v85 = *((_QWORD *)v7 + 21);
      v86 = (const struct _LUID *)(*(__int64 (__fastcall **)(__int128 *))(v125 + 16))(&v125);
      VIDSCH_EXPORT::VidSchExitIndependentFlip(
        v84,
        v14[93],
        1 << *((_DWORD *)v7 + 29),
        v86,
        v85,
        &v128,
        0,
        0,
        (int *)&v127,
        (unsigned __int64 *)&v131);
      ADAPTER_DISPLAY::UpdateIndependentFlipState(v130, *((_DWORD *)v7 + 29), v128, 0);
    }
    else if ( !v148 )
    {
LABEL_59:
      DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v133);
      (*(void (__fastcall **)(__int128 *, __int64))v125)(&v125, 1);
      return 0;
    }
    LOBYTE(v30) = 1;
    (*(void (__fastcall **)(__int128 *, __int64))(v125 + 232))(&v125, v30);
    goto LABEL_59;
  }
  *((_QWORD *)v7 + 22) = *(_QWORD *)(*(__int64 (__fastcall **)(__int128 *))(v125 + 24))(&v125);
  if ( !(*(unsigned __int8 (__fastcall **)(__int128 *))(v125 + 240))(&v125) )
  {
    v127 = D3DDDI_HDR_METADATA_TYPE_NONE;
    v131 = 0;
    v87 = v14[92];
    v88 = *((_QWORD *)v7 + 21);
    v89 = (const struct _LUID *)(*(__int64 (__fastcall **)(__int128 *))(v125 + 16))(&v125);
    VIDSCH_EXPORT::VidSchExitIndependentFlip(
      v87,
      v14[93],
      1 << *((_DWORD *)v7 + 29),
      v89,
      v88,
      &v128,
      0,
      0,
      (int *)&v127,
      (unsigned __int64 *)&v131);
    LOBYTE(v90) = 1;
    (*(void (__fastcall **)(__int128 *, __int64))(v125 + 232))(&v125, v90);
    ADAPTER_DISPLAY::UpdateIndependentFlipState(v130, *((_DWORD *)v7 + 29), v128, 0);
    WdLogSingleEntry0(8);
    WdLogGlobalForLineNumber = 2360;
    goto LABEL_50;
  }
  if ( v140 || DXGADAPTER::SupportCheckMultiPlaneOverlaySupport3(v14[2]) )
  {
    v31 = (*(__int64 (__fastcall **)(__int128 *))(v125 + 248))(&v125);
    v32 = v130;
    if ( !v31 )
    {
      ADAPTER_DISPLAY::UpdateIndependentFlipState(v130, *((_DWORD *)v7 + 29), v128, 1u);
LABEL_34:
      *(_DWORD *)v7 = *(_DWORD *)v7 & 0x7BFFFFFF | ((v140 & 1 | (32 * v138)) << 26);
      *(_OWORD *)((char *)v7 + 436) = v178;
      *(struct tagRECT *)((char *)v7 + 452) = v179;
      goto LABEL_35;
    }
    DXGDISPLAYSTATEMUTEX::DXGDISPLAYSTATEMUTEX((DXGDISPLAYSTATEMUTEX *)&v161, v130);
    DXGAUTOMUTEX::Acquire((DXGAUTOMUTEX *)&v161);
    PostCompositionStretching = ADAPTER_DISPLAY::GetPostCompositionStretching(v32, *((_DWORD *)v7 + 29));
    v126 = PostCompositionStretching;
    if ( PostCompositionStretching )
    {
      if ( IsYUVAllocation(*(void **)(v133[6] + 16LL), (struct ADAPTER_RENDER *)v14)
        || DISPLAY_SOURCE::GetEnabledPlaneCountUnsafe((DISPLAY_SOURCE *)(*((_QWORD *)v32 + 16)
                                                                       + 4024LL * *((unsigned int *)v7 + 29))) > 1 )
      {
        PostCompositionStretching = 0;
        v126 = 0;
      }
      else
      {
        PostCompositionStretching = v126;
      }
    }
    v167 = 0;
    if ( v128 || (v98 = 1, !PostCompositionStretching) )
      v98 = 0;
    if ( CheckAndUpdateMultiPlaneOverlayFromInternalState(
           *((_DWORD *)v7 + 29),
           v128,
           (struct CIFlipPresentHistoryTokenData *)&v125,
           v98,
           (struct ADAPTER_RENDER *)v14,
           v32,
           &v167) )
    {
      v99 = (__int64 *)(*(__int64 (__fastcall **)(__int128 *))(v125 + 8))(&v125);
      v136 = v99;
      v100 = *(__int64 **)v141;
      **(_WORD **)v141 = *(_WORD *)v99;
      *((_WORD *)v100 + 2) = *((_WORD *)v99 + 2);
      *((_WORD *)v100 + 1) = *((_WORD *)v99 + 4);
      *((_WORD *)v100 + 3) = *((_WORD *)v99 + 6);
      *((_DWORD *)v100 + 6) = (*(__int64 (__fastcall **)(__int128 *))(v125 + 112))(&v125);
      if ( v126 )
      {
        v77 = *v100;
        v100[1] = *v100;
        v100[2] = v77;
        v78 = *(_OWORD *)v136;
        v178 = v78;
        v179 = v167;
        if ( (_DWORD)v78 != v167.left
          || __PAIR64__(DWORD2(v178), DWORD1(v78)) != *(_QWORD *)&v167.top
          || (v76 = 0, HIDWORD(v178) != v167.bottom) )
        {
          v76 = 1;
        }
        v138 = v76;
        if ( !(_DWORD)v76 )
        {
          v178 = 0;
          v179 = 0;
        }
        (*(void (__fastcall **)(DXGADAPTER *, _QWORD, __int64, __int128 *, struct tagRECT *))(*((_QWORD *)v14[92] + 1)
                                                                                            + 1008LL))(
          v14[93],
          *((unsigned int *)v7 + 29),
          v76,
          &v178,
          &v179);
        UpdatePostComposition(*((_DWORD *)v7 + 29), v138 != 0, DWORD2(v178) - v178, HIDWORD(v178) - DWORD1(v178), v32);
      }
      (*(void (__fastcall **)(DXGADAPTER *, _QWORD, __int64 *, _QWORD))(*((_QWORD *)v14[92] + 1) + 440LL))(
        v14[93],
        *((unsigned int *)v7 + 29),
        v100,
        v128);
      DXGAUTOMUTEX::Release((DXGAUTOMUTEX *)&v161);
      DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)&v161);
      goto LABEL_34;
    }
    DXGAUTOMUTEX::Release((DXGAUTOMUTEX *)&v161);
    v127 = D3DDDI_HDR_METADATA_TYPE_NONE;
    v131 = 0;
    v101 = v14[92];
    v102 = *((_QWORD *)v7 + 21);
    v103 = (const struct _LUID *)(*(__int64 (__fastcall **)(__int128 *))(v125 + 16))(&v125);
    VIDSCH_EXPORT::VidSchExitIndependentFlip(
      v101,
      v14[93],
      1 << *((_DWORD *)v7 + 29),
      v103,
      v102,
      &v128,
      0,
      0,
      (int *)&v127,
      (unsigned __int64 *)&v131);
    WdLogSingleEntry1(3, v128);
    WdLogGlobalForLineNumber = 2470;
    LOBYTE(v104) = 1;
    (*(void (__fastcall **)(__int128 *, __int64))(v125 + 232))(&v125, v104);
    ADAPTER_DISPLAY::UpdateIndependentFlipState(v130, *((_DWORD *)v7 + 29), v128, 0);
    DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)&v161);
    goto LABEL_50;
  }
  v91 = (_DWORD *)(*(__int64 (__fastcall **)(__int128 *))(v125 + 8))(&v125);
  *(_QWORD *)v141 = v91;
  if ( v91[2] - *v91 != (*(unsigned int (__fastcall **)(__int128 *))(v125 + 120))(&v125)
    || (v92 = v91[3] - v91[1], v92 != (*(unsigned int (__fastcall **)(__int128 *))(v125 + 128))(&v125))
    || (*(unsigned __int8 (__fastcall **)(__int128 *))(v125 + 248))(&v125) )
  {
    v127 = D3DDDI_HDR_METADATA_TYPE_NONE;
    v131 = 0;
    v93 = v14[92];
    v94 = *((_QWORD *)v7 + 21);
    v95 = (const struct _LUID *)(*(__int64 (__fastcall **)(__int128 *))(v125 + 16))(&v125);
    VIDSCH_EXPORT::VidSchExitIndependentFlip(
      v93,
      v14[93],
      1 << *((_DWORD *)v7 + 29),
      v95,
      v94,
      &v128,
      0,
      0,
      (int *)&v127,
      (unsigned __int64 *)&v131);
    (*(__int64 (__fastcall **)(__int128 *))(v125 + 128))(&v125);
    (*(void (__fastcall **)(__int128 *))(v125 + 120))(&v125);
    WdLogSingleEntry4(
      8,
      *(_DWORD *)(*(_QWORD *)v141 + 8LL) - **(_DWORD **)v141,
      *(_DWORD *)(*(_QWORD *)v141 + 12LL) - *(_DWORD *)(*(_QWORD *)v141 + 4LL));
    WdLogGlobalForLineNumber = 2523;
    LOBYTE(v96) = 1;
    (*(void (__fastcall **)(__int128 *, __int64))(v125 + 232))(&v125, v96);
    ADAPTER_DISPLAY::UpdateIndependentFlipState(v130, *((_DWORD *)v7 + 29), 0, 0);
LABEL_149:
    DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v133);
    CIFlipPresentHistoryToken::~CIFlipPresentHistoryToken((CIFlipPresentHistoryToken *)&v125);
    return v11;
  }
  v32 = v130;
  ADAPTER_DISPLAY::UpdateIndependentFlipState(v130, *((_DWORD *)v7 + 29), 0, 1u);
LABEL_35:
  if ( v32 && (*((_DWORD *)v32 + 6) & 0x10) != 0 )
  {
    if ( !ADAPTER_DISPLAY::IsHdrEnabled(v32, v134) )
    {
      *((_DWORD *)v7 + 90) = 0;
LABEL_39:
      *(_DWORD *)v7 |= 0x40000000u;
      goto LABEL_40;
    }
    *(_DWORD *)v7 ^= (*(_DWORD *)v7
                    ^ ((*(unsigned __int8 (__fastcall **)(__int128 *))(v125 + 256))(&v125) << 30))
                   & 0x40000000;
    v105 = (*(__int64 (__fastcall **)(__int128 *))(v125 + 136))(&v125);
    *((_DWORD *)v7 + 90) = v105;
    if ( (*(_DWORD *)v7 & 0x40000000) != 0 )
    {
      if ( v105 )
      {
        v106 = v105 - 1;
        if ( v106 )
        {
          if ( v106 == 1 )
          {
            v107 = (*(__int64 (__fastcall **)(__int128 *))(v125 + 152))(&v125);
            *(_OWORD *)((char *)v7 + 364) = *(_OWORD *)v107;
            *(_OWORD *)((char *)v7 + 380) = *(_OWORD *)(v107 + 16);
            *(_OWORD *)((char *)v7 + 396) = *(_OWORD *)(v107 + 32);
            *(_OWORD *)((char *)v7 + 412) = *(_OWORD *)(v107 + 48);
            *(_QWORD *)((char *)v7 + 428) = *(_QWORD *)(v107 + 64);
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
          v108 = (_OWORD *)(*(__int64 (__fastcall **)(__int128 *))(v125 + 144))(&v125);
          *(_OWORD *)((char *)v7 + 364) = *v108;
          *(_OWORD *)((char *)v7 + 376) = *(_OWORD *)((char *)v108 + 12);
        }
      }
    }
    else
    {
      if ( v105 > 2 )
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
      v127 = D3DDDI_HDR_METADATA_TYPE_NONE;
      memset(&v161, 0, sizeof(v161));
      if ( !(unsigned int)PopulateHDRMetadataFromDisplay(*((_DWORD *)v7 + 29), v32, &v161, &v127) )
      {
        *(_OWORD *)((char *)v7 + 364) = *(_OWORD *)v161.RedPrimary;
        *(_OWORD *)((char *)v7 + 376) = *(_OWORD *)v161.WhitePoint;
        *((_DWORD *)v7 + 90) = v127;
        goto LABEL_39;
      }
    }
  }
LABEL_40:
  (*(void (__fastcall **)(__int128 *, _QWORD))(v125 + 160))(&v125, v128);
  v33 = (_DWORD *)((char *)v7 + 600);
  if ( !*((_BYTE *)v7 + 356) )
    v33 = (_DWORD *)((char *)v7 + 496);
  *v33 ^= ((unsigned __int16)*v33 ^ (unsigned __int16)(1 << v128)) & 0x3FF;
  v34 = 1;
  v132 = 1;
  IsDxgmms2 = DXGADAPTER::IsDxgmms2(v137);
  v36 = v142;
  if ( IsDxgmms2 && v142 )
  {
    v34 = *(_DWORD *)(v156 + 92) + 1;
    v132 = v34;
  }
  Pool2 = 0;
  v145 = 0;
  v168 = 0;
  v170 = 0;
  if ( v34 <= 4 )
  {
    Pool2 = v169;
    v145 = v169;
    v168 = v169;
    if ( !v34 )
    {
LABEL_47:
      v170 = v34;
      goto LABEL_48;
    }
    memset(v169, 0, 8LL * v34);
    Pool2 = v168;
LABEL_46:
    v145 = Pool2;
    goto LABEL_47;
  }
  if ( 0xFFFFFFFFFFFFFFFFuLL / v34 >= 8 )
  {
    Pool2 = (_BYTE *)ExAllocatePool2(256, 8LL * v34, 1265072196);
    v168 = Pool2;
    goto LABEL_46;
  }
LABEL_48:
  *(_QWORD *)v161.RedPrimary = Pool2;
  if ( !Pool2 )
  {
    v168 = 0;
    v170 = 0;
    DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v133);
    (*(void (__fastcall **)(__int128 *, __int64))v125)(&v125, 1);
    return 3221225495LL;
  }
  v180[0] = 0;
  v181 = 0;
  PagedPoolArray<DXGALLOCATIONREFERENCE,4>::AllocateElements(v180, v34);
  *(_QWORD *)v141 = v180[0];
  if ( !v180[0] )
  {
    PagedPoolArray<DXGALLOCATIONREFERENCE,4>::~PagedPoolArray<DXGALLOCATIONREFERENCE,4>(v180);
    if ( v168 != v169 && v168 )
      ExFreePoolWithTag(v168, 0);
    v168 = 0;
    v170 = 0;
    v11 = -1073741801;
    goto LABEL_149;
  }
  v40 = v7;
  v153 = v7;
  v41 = v137;
  v42 = v137;
  v130 = v137;
  v43 = 0;
  v129 = 0;
  v127 = D3DDDI_HDR_METADATA_TYPE_NONE;
  v44 = 0;
  while ( 1 )
  {
    v135 = v44;
    if ( (unsigned int)v44 >= v34 )
      break;
    if ( (_DWORD)v44 )
    {
      v144 = (unsigned int)v44;
      v129 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v143 + 1496) + 8LL * (unsigned int)v44) + 388LL);
      v139 = 0;
      RtlCopyFromUser(&v139, (void *)(*(_QWORD *)(v156 + 1456) + 4LL * (unsigned int)(v44 - 1)), 4u);
      v136 = (__int64 *)(*(_QWORD *)v141 + 8 * v144);
      AllocationSafe = DXGPROCESS::GetAllocationSafe(v172, &v167, v139);
      DXGALLOCATIONREFERENCE::MoveAssign(v136, AllocationSafe);
      DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v167);
      v47 = (_QWORD *)*v136;
      v151 = v47;
      if ( !v47 )
      {
        WdLogSingleEntry2(2, v139, -1073741811);
        WdLogGlobalForLineNumber = 2686;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Invalid allocation handle in present: 0x%I64x. Returning 0x%I64x",
          v139,
          -1073741811,
          0,
          0,
          0);
        v43 = -1073741811;
        v129 = -1073741811;
        v149 = -1073741811;
        v42 = v130;
        break;
      }
      v83 = v143;
      v110 = 8 * v144;
      if ( *(_QWORD *)(*(_QWORD *)(v47[1] + 16LL) + 16LL) != *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v143 + 1496) + 8 * v144)
                                                                                               + 16LL)
                                                                                   + 16LL)
                                                                       + 16LL) )
      {
        _mm_lfence();
        WdLogSingleEntry3(2, *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v143 + 1496) + 8 * v144) + 16LL), v47, -1073741811);
        WdLogGlobalForLineNumber = 2695;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Device 0x%p does not match allocation 0x%p owner, returning 0x%I64x",
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v143 + 1496) + 8 * v144) + 16LL),
          *v136,
          -1073741811,
          0,
          0);
        v43 = -1073741811;
        v129 = -1073741811;
        v149 = -1073741811;
        v42 = v130;
        break;
      }
      v46 = v135;
      if ( *((_BYTE *)v7 + 356) )
        v80 = (_QWORD *)((char *)v7
                       + 64 * (unsigned __int64)(unsigned int)(v135 * *((_DWORD *)v7 + 151))
                       + (unsigned int)(8 * *((_DWORD *)v7 + 151) * (*((_DWORD *)v7 + 152) + 28))
                       + 632);
      else
        v80 = (_QWORD *)((char *)v153 + 512);
      *v80 = *(_QWORD *)(v47[6] + 16LL);
      if ( !*((_BYTE *)v137 + 3185) )
      {
        v81 = *(__int64 **)(*(_QWORD *)(v110 + *(_QWORD *)(v83 + 1496)) + 184LL);
        v136 = v81;
        if ( *((_BYTE *)v7 + 356) )
        {
          v82 = (__int64 **)((char *)v7
                           + 64 * (unsigned __int64)(unsigned int)(v46 * *((_DWORD *)v7 + 151))
                           + *((_DWORD *)v7 + 151) * ((8 * *((_DWORD *)v7 + 152) + 231) & 0xFFFFFFF8)
                           + 624);
          v83 = v143;
          v81 = v136;
        }
        else
        {
          v82 = (__int64 **)((char *)v7 + 568);
        }
        *v82 = v81;
      }
      *((_DWORD *)v7 + 34) |= 1 << v129;
      v111 = *(_QWORD *)(v110 + *(_QWORD *)(v83 + 1496));
      if ( (*(_DWORD *)(v111 + 392) & 0x10) == 0 )
        *(_QWORD *)((char *)v7 + v110 + *((unsigned int *)v7 + 138)) = *(_QWORD *)(v111 + 256);
    }
    else
    {
      v151 = v133;
      if ( *((_BYTE *)v7 + 356) )
        v45 = (_QWORD *)((char *)v7 + (unsigned int)(8 * *((_DWORD *)v7 + 151) * (*((_DWORD *)v7 + 152) + 28)) + 632);
      else
        v45 = (_QWORD *)((char *)v40 + 512);
      *v45 = *(_QWORD *)(v133[6] + 16LL);
      if ( !*((_BYTE *)v41 + 3185) )
      {
        if ( *((_BYTE *)v7 + 356) )
          v79 = (_QWORD *)((char *)v7 + (unsigned int)(8 * *((_DWORD *)v7 + 151) * (*((_DWORD *)v7 + 152) + 28)) + 624);
        else
          v79 = (_QWORD *)((char *)v7 + 568);
        *v79 = *((_QWORD *)v36 + 23);
      }
      if ( DXGADAPTER::IsDxgmms2(v41) && v36 && (*((_DWORD *)v36 + 98) & 0x10) == 0 )
        *(_QWORD *)((char *)v7 + *((unsigned int *)v7 + 138)) = *((_QWORD *)v36 + 32);
      v144 = 0;
    }
    if ( *((_BYTE *)v7 + 356) )
      v48 = (unsigned __int64)v7
          + 64 * (unsigned __int64)(unsigned int)(v46 * *((_DWORD *)v7 + 151))
          + (unsigned int)(8 * *((_DWORD *)v7 + 151) * (*((_DWORD *)v7 + 152) + 28))
          + 656;
    else
      v48 = (unsigned __int64)v7 + 504;
    v136 = (__int64 *)v48;
    v129 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64, DXGADAPTER *, unsigned int *))(*((_QWORD *)v14[95] + 1) + 400LL))(
             v152[99],
             v47[3],
             v48,
             v14[96],
             v158);
    if ( v129 < 0 )
    {
      WdLogSingleEntry2(2, v151, -1073741811);
      WdLogGlobalForLineNumber = 2744;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Failed to reference allocation for submission (0x%I64x). Returning 0x%I64x",
        (__int64)v151,
        -1073741811,
        0,
        0,
        0);
      v43 = v129;
      v42 = v130;
      break;
    }
    *(_QWORD *)&v145[8 * v144] = *v136;
    ++v127;
    v49 = v151[5];
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
                + 64 * v135 * *((_DWORD *)v7 + 151)
                + *((_DWORD *)v7 + 151) * ((8 * *((_DWORD *)v7 + 152) + 231) & 0xFFFFFFF8)
                + 664) = v51;
    else
      *((_QWORD *)v7 + 72) = v51;
    *(_DWORD *)v7 |= 0x1000000u;
    v52 = *p_CompositionBindingId;
    v53 = *(_QWORD *)(*(__int64 (__fastcall **)(__int128 *))(v125 + 16))(&v125);
    v54 = (*(__int64 (__fastcall **)(__int128 *))(v125 + 64))(&v125);
    v55 = (*(__int64 (__fastcall **)(__int128 *))(v125 + 104))(&v125);
    WdLogSingleEntry5(8, v150, v55, v54, v53, v52);
    WdLogGlobalForLineNumber = 2767;
    if ( (*(unsigned __int8 (__fastcall **)(__int128 *))(v125 + 344))(&v125)
      && (*((_DWORD *)v7 + 1) |= 2u,
          *((_QWORD *)v7 + 60) = (*(__int64 (__fastcall **)(__int128 *))(v125 + 352))(&v125),
          v112 = (_DWORD *)(*(__int64 (__fastcall **)(__int128 *))(v125 + 360))(&v125),
          v113 = v112,
          (*((_QWORD *)v7 + 61) = v112) != 0)
      && !v112[1] )
    {
      if ( *v112 != 64 )
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
      v113[8] = *((_DWORD *)v7 + 29);
      v42 = v130;
      *((_QWORD *)v113 + 3) = *(_QWORD *)((char *)v130 + 412);
    }
    else
    {
      v42 = v130;
    }
    v44 = (unsigned int)(v135 + 1);
    v14 = v171;
    v34 = v132;
    v36 = v142;
    v43 = v129;
    v41 = v137;
    v40 = v153;
  }
  *((_DWORD *)v10 + 35) = v34;
  if ( v43 < 0 || (*((_DWORD *)v42 + 647) & 0x20) == 0 )
  {
    v56 = v137;
LABEL_83:
    if ( v140 && (*(_DWORD *)v7 & 0x1000000) != 0 )
    {
      v131 = 0;
      if ( *((int *)v56 + 783) < 2500
        || (v73 = ReadPresentDirtyRectsData(v41, v128, (const struct CIFlipPresentHistoryTokenData *)&v125, &v131),
            v73 >= 0) )
      {
        *((_QWORD *)v10 + 4) = v131;
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
  memset(&v177, 0, sizeof(v177));
  v177.Flags.Value = 0x2000;
  if ( v155 )
  {
    v177.PrivateDriverDataSize = *((_DWORD *)v155 + 2);
    v177.pPrivateDriverData = (char *)v155 + 16;
  }
  P = 0;
  v184 = 0;
  PagedPoolZeroedArray<_DXGK_PRESENTALLOCATIONINFO,4>::AllocateElements((__int64 *)&P, v34);
  v177.pAllocationList = (DXGK_ALLOCATIONLIST *)P;
  if ( P )
  {
    v58 = *((_DWORD *)v130 + 649);
    if ( (v58 & 0x80u) == 0 || (v126 = 1, (v58 & 0x40) != 0) )
      v126 = 0;
    v59 = 0;
    v132 = 0;
    if ( v34 )
    {
      v60 = v143;
      v61 = v126;
      do
      {
        v62 = 8LL * v59;
        if ( v36 )
          v63 = *(_WORD *)(*(_QWORD *)(v62 + *(_QWORD *)(v60 + 1496)) + 388LL);
        else
          v63 = 0;
        v64 = 32LL * v59;
        v160 = (struct DXGCONTEXT *)v64;
        *(_WORD *)((char *)&v177.pAllocationList[1].hDeviceSpecificAllocation + v64 + 2) = v63;
        if ( v59 )
          v65 = *(_QWORD **)(v62 + *(_QWORD *)v141);
        else
          v65 = v133;
        if ( v36 )
          v61 = *(_BYTE *)(*(_QWORD *)(v62 + *(_QWORD *)(v60 + 1496)) + 431LL);
        *((_QWORD *)&v177.pAllocationList->hDeviceSpecificAllocation + 4 * v59) = v65[4];
        pAllocationList = v177.pAllocationList;
        AllocationGpuVirtualAddress = VIDMM_EXPORT::VidMmGetAllocationGpuVirtualAddress(
                                        v14[95],
                                        (const struct VIDMM_MULTI_ALLOC *)v65[3],
                                        v61 != 0,
                                        *(unsigned __int16 *)((char *)&v177.pAllocationList[1].hDeviceSpecificAllocation
                                                            + v64
                                                            + 2));
        *(_QWORD *)((char *)v160 + (_QWORD)pAllocationList + 8) = AllocationGpuVirtualAddress;
        v59 = v132 + 1;
        v132 = v59;
        v36 = v142;
      }
      while ( v59 < v34 );
      v10 = v165;
      v7 = v166;
    }
    v177.FlipInterval = *(_DWORD *)v131;
    v177.Flags.Value = v177.Flags.Value & 0xFFFFE8FF | (*(_DWORD *)v153 >> 11) & 0x1700;
    v177.NumSrcAllocations = v34;
    v56 = v137;
    v68 = 0;
    if ( !*((_BYTE *)v137 + 3185) )
      v68 = (void *)*((_QWORD *)v36 + 23);
    v129 = ADAPTER_RENDER::DdiPresent((ADAPTER_RENDER *)v14, v68, &v177);
    v41 = (DXGADAPTER *)P;
    if ( v129 >= 0 )
    {
      if ( P != v183 && P )
        ExFreePoolWithTag(P, 0);
      P = 0;
      v184 = 0;
      goto LABEL_83;
    }
    if ( P != v183 && P )
      ExFreePoolWithTag(P, 0);
  }
  P = 0;
  v184 = 0;
LABEL_84:
  v57 = v129;
  if ( v129 < 0 )
  {
    v114 = 0;
    v115 = v127;
    if ( v127 )
    {
      v116 = v142;
      v117 = v157;
      do
      {
        if ( v116 )
          v118 = *(_DWORD *)(*(_QWORD *)(8LL * v114 + v117) + 388LL);
        else
          LOBYTE(v118) = 0;
        VIDMM_EXPORT::VidMmUnreferencePrimaryAllocation(
          v14[95],
          v14[96],
          1 << v118,
          *(struct VIDMM_ALLOC **)&v145[8 * v114++],
          v124,
          v158);
      }
      while ( v114 < v115 );
    }
    v119 = *p_CompositionBindingId;
    v120 = *(_QWORD *)(*(__int64 (__fastcall **)(__int128 *, struct VIDSCH_SUBMIT_DATA_BASE *, __int64, DXGADAPTER *))(v125 + 16))(
                        &v125,
                        v40,
                        v44,
                        v42);
    v121 = (*(__int64 (__fastcall **)(__int128 *))(v125 + 64))(&v125);
    v122 = (*(__int64 (__fastcall **)(__int128 *))(v125 + 104))(&v125);
    WdLogSingleEntry5(8, v150, v122, v121, v120, v119);
    WdLogGlobalForLineNumber = 2896;
    LOBYTE(v123) = 1;
    (*(void (__fastcall **)(__int128 *, __int64))(v125 + 232))(&v125, v123);
    *(_DWORD *)v153 &= ~0x1000000u;
    v57 = 0;
  }
  PagedPoolArray<DXGALLOCATIONREFERENCE,4>::~PagedPoolArray<DXGALLOCATIONREFERENCE,4>(v180);
  if ( v168 != v169 && v168 )
    ExFreePoolWithTag(v168, 0);
  v168 = 0;
  v170 = 0;
  DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v133);
  (*(void (__fastcall **)(__int128 *, __int64))v125)(&v125, 1);
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
