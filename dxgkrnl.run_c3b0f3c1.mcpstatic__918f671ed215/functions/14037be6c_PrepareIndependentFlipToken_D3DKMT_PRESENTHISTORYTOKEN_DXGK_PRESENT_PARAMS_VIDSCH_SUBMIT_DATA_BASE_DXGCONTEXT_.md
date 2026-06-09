# PrepareIndependentFlipToken(_D3DKMT_PRESENTHISTORYTOKEN *,DXGK_PRESENT_PARAMS *,VIDSCH_SUBMIT_DATA_BASE *,DXGCONTEXT *,_PRESENT_REDIRECTED_PARAMS *,CRefCountedBuffer *)

- ea: `0x14037be6c`
- end: `0x14037e3bf`
- name: `?PrepareIndependentFlipToken@@YAJPEAU_D3DKMT_PRESENTHISTORYTOKEN@@PEAUDXGK_PRESENT_PARAMS@@PEAUVIDSCH_SUBMIT_DATA_BASE@@PEAVDXGCONTEXT@@PEAU_PRESENT_REDIRECTED_PARAMS@@PEAVCRefCountedBuffer@@@Z`
- size: `9555`
- prototype: `__int64 __fastcall(struct _D3DKMT_PRESENTHISTORYTOKEN *, unsigned __int64, struct VIDSCH_SUBMIT_DATA_BASE *, struct DXGCONTEXT *, struct _PRESENT_REDIRECTED_PARAMS *, struct CRefCountedBuffer *)`
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
  __int64 v31; // rdi
  char v32; // al
  struct ADAPTER_DISPLAY *v33; // rbx
  _DWORD *v34; // r8
  UINT v35; // edi
  unsigned __int8 IsDxgmms2; // al
  struct DXGCONTEXT *v37; // rbx
  _BYTE *Pool2; // rcx
  __int64 v40; // rdx
  struct VIDSCH_SUBMIT_DATA_BASE *v41; // rdx
  DXGADAPTER *v42; // rcx
  DXGADAPTER *v43; // r9
  int v44; // eax
  __int64 v45; // r8
  _QWORD *v46; // rdx
  int v47; // r8d
  _QWORD *v48; // r10
  unsigned __int64 v49; // rdx
  __int64 v50; // rcx
  bool v51; // al
  __int64 v52; // r9
  UINT64 v53; // rsi
  __int64 v54; // rdi
  unsigned int v55; // ebx
  __int64 v56; // rax
  DXGADAPTER *v57; // rdi
  unsigned int v58; // ebx
  int v59; // eax
  UINT v60; // r9d
  struct DXGK_PRESENT_PARAMS *v61; // r15
  char v62; // r13
  __int64 v63; // r8
  __int16 v64; // r10
  __int64 v65; // rdx
  _QWORD *v66; // r10
  DXGK_ALLOCATIONLIST *pAllocationList; // rbx
  unsigned __int64 AllocationGpuVirtualAddress; // rax
  void *v69; // rdx
  unsigned __int64 v70; // r8
  int v71; // eax
  int v72; // ecx
  int v73; // edx
  int v74; // eax
  __int64 v75; // rbx
  unsigned int v76; // ebx
  __int64 v77; // rax
  __int64 v78; // r8
  __int64 v79; // rax
  __int128 v80; // xmm1
  _QWORD *v81; // r9
  _QWORD *v82; // rax
  __int64 *v83; // rax
  __int64 **v84; // rdx
  struct DXGK_PRESENT_PARAMS *v85; // r11
  VIDSCH_EXPORT *v86; // rdi
  unsigned __int64 v87; // rbx
  const struct _LUID *v88; // rax
  VIDSCH_EXPORT *v89; // rdi
  unsigned __int64 v90; // rbx
  const struct _LUID *v91; // rax
  __int64 v92; // rdx
  _DWORD *v93; // rbx
  int v94; // ebx
  VIDSCH_EXPORT *v95; // rdi
  unsigned __int64 v96; // rbx
  const struct _LUID *v97; // rax
  __int64 v98; // rbx
  unsigned int v99; // eax
  __int64 v100; // rdx
  unsigned __int8 PostCompositionStretching; // al
  bool v102; // r9
  __int64 *v103; // rax
  __int64 *v104; // rdi
  VIDSCH_EXPORT *v105; // rdi
  unsigned __int64 v106; // rbx
  const struct _LUID *v107; // rax
  __int64 v108; // rdx
  unsigned int v109; // eax
  unsigned int v110; // eax
  __int64 v111; // rax
  _OWORD *v112; // rax
  __int64 AllocationSafe; // rax
  __int64 v114; // r9
  __int64 v115; // rdx
  _DWORD *v116; // rax
  _DWORD *v117; // rbx
  unsigned int v118; // edi
  enum _D3DDDI_HDR_METADATA_TYPE v119; // r15d
  struct DXGCONTEXT *v120; // rbx
  __int64 v121; // r13
  int v122; // ecx
  UINT64 v123; // rsi
  __int64 v124; // rdi
  unsigned int v125; // ebx
  __int64 v126; // rax
  __int64 v127; // rdx
  bool v128; // [rsp+20h] [rbp-3E8h]
  __int128 v129; // [rsp+80h] [rbp-388h] BYREF
  char v130; // [rsp+90h] [rbp-378h]
  enum _D3DDDI_HDR_METADATA_TYPE v131; // [rsp+94h] [rbp-374h] BYREF
  unsigned int v132; // [rsp+98h] [rbp-370h] BYREF
  int v133; // [rsp+9Ch] [rbp-36Ch]
  struct ADAPTER_DISPLAY *v134; // [rsp+A0h] [rbp-368h]
  struct CRefCountedBuffer *v135; // [rsp+A8h] [rbp-360h] BYREF
  int v136; // [rsp+B0h] [rbp-358h]
  _QWORD *v137; // [rsp+B8h] [rbp-350h] BYREF
  unsigned int v138; // [rsp+C0h] [rbp-348h] BYREF
  int v139; // [rsp+C4h] [rbp-344h]
  __int64 *v140; // [rsp+C8h] [rbp-340h]
  DXGADAPTER *v141; // [rsp+D0h] [rbp-338h]
  int v142; // [rsp+D8h] [rbp-330h]
  unsigned int v143; // [rsp+DCh] [rbp-32Ch] BYREF
  int v144; // [rsp+E0h] [rbp-328h]
  bool v145[8]; // [rsp+E8h] [rbp-320h]
  struct DXGCONTEXT *v146; // [rsp+F0h] [rbp-318h]
  struct DXGK_PRESENT_PARAMS *v147; // [rsp+F8h] [rbp-310h]
  __int64 v148; // [rsp+100h] [rbp-308h]
  _BYTE *v149; // [rsp+108h] [rbp-300h]
  int v150; // [rsp+110h] [rbp-2F8h]
  int v151; // [rsp+114h] [rbp-2F4h]
  int v152; // [rsp+118h] [rbp-2F0h]
  int v153; // [rsp+11Ch] [rbp-2ECh]
  struct _D3DKMT_PRESENTHISTORYTOKEN *v154; // [rsp+120h] [rbp-2E8h]
  _QWORD *v155; // [rsp+128h] [rbp-2E0h]
  _QWORD *v156; // [rsp+130h] [rbp-2D8h]
  struct VIDSCH_SUBMIT_DATA_BASE *v157; // [rsp+138h] [rbp-2D0h]
  int v158; // [rsp+140h] [rbp-2C8h] BYREF
  struct CRefCountedBuffer *v159; // [rsp+148h] [rbp-2C0h]
  unsigned __int64 v160; // [rsp+150h] [rbp-2B8h]
  __int64 v161; // [rsp+158h] [rbp-2B0h]
  unsigned int *v162; // [rsp+160h] [rbp-2A8h]
  UINT64 *p_CompositionBindingId; // [rsp+168h] [rbp-2A0h]
  struct DXGCONTEXT *v164; // [rsp+170h] [rbp-298h]
  struct _D3DDDI_HDR_METADATA_HDR10 v165; // [rsp+178h] [rbp-290h] BYREF
  __int64 v166; // [rsp+198h] [rbp-270h]
  __int64 v167; // [rsp+1A0h] [rbp-268h]
  __int64 v168; // [rsp+1A8h] [rbp-260h]
  struct VIDSCH_SUBMIT_DATA_BASE *v169; // [rsp+1B0h] [rbp-258h]
  struct VIDSCH_SUBMIT_DATA_BASE *v170; // [rsp+1B8h] [rbp-250h]
  struct tagRECT v171; // [rsp+1C0h] [rbp-248h] BYREF
  PVOID v172; // [rsp+1D0h] [rbp-238h]
  _BYTE v173[32]; // [rsp+1D8h] [rbp-230h] BYREF
  UINT v174; // [rsp+1F8h] [rbp-210h]
  DXGADAPTER **v175; // [rsp+200h] [rbp-208h]
  struct DXGPROCESS *v176; // [rsp+208h] [rbp-200h]
  struct VIDSCH_SUBMIT_DATA_BASE *v177; // [rsp+210h] [rbp-1F8h]
  struct _D3DKMT_PRESENTHISTORYTOKEN *v178; // [rsp+218h] [rbp-1F0h]
  unsigned __int64 v179; // [rsp+220h] [rbp-1E8h]
  DXGADAPTER **v180; // [rsp+228h] [rbp-1E0h]
  _DXGKARG_PRESENT v181; // [rsp+230h] [rbp-1D8h] BYREF
  __int128 v182; // [rsp+2E0h] [rbp-128h] BYREF
  struct tagRECT v183; // [rsp+2F0h] [rbp-118h] BYREF
  _QWORD v184[5]; // [rsp+300h] [rbp-108h] BYREF
  int v185; // [rsp+328h] [rbp-E0h]
  PVOID P; // [rsp+330h] [rbp-D8h] BYREF
  _BYTE v187[128]; // [rsp+338h] [rbp-D0h] BYREF
  int v188; // [rsp+3B8h] [rbp-50h]

  v146 = a4;
  v7 = a3;
  v170 = a3;
  v147 = (struct DXGK_PRESENT_PARAMS *)a2;
  v154 = a1;
  v177 = a3;
  v178 = a1;
  v179 = a2;
  v10 = a3;
  v169 = a3;
  v164 = a4;
  v135 = a5;
  v159 = a6;
  v11 = 0;
  if ( !CIFlipPresentHistoryToken::IsIFlipSupported(a1) || a4 && !a2 )
    return 0;
  v129 = 0;
  if ( a1->Model == D3DKMT_PM_REDIRECTED_FLIP )
  {
    CIFlipPresentHistoryTokenRedirectedFlip::CIFlipPresentHistoryTokenRedirectedFlip(
      (CIFlipPresentHistoryTokenRedirectedFlip *)&v129,
      &a1->Token.Flip);
  }
  else if ( a1->Model == D3DKMT_PM_FLIPMANAGER )
  {
    CIFlipPresentHistoryTokenFlipManager::CIFlipPresentHistoryTokenFlipManager(
      (CIFlipPresentHistoryTokenFlipManager *)&v129,
      (const struct _D3DKMT_FLIPMANAGER_PRESENTHISTORYTOKEN *)&a1->Token);
  }
  if ( a4 )
  {
    v156 = (_QWORD *)*((_QWORD *)a4 + 2);
    v12 = *(_QWORD *)(v156[2] + 16LL);
  }
  else
  {
    v12 = *((_QWORD *)a5 + 3);
    v156 = (_QWORD *)*((_QWORD *)a5 + 4);
  }
  v167 = v12;
  v141 = (DXGADAPTER *)v12;
  if ( !a4 && !*(_BYTE *)(v12 + 3185) )
    goto LABEL_51;
  *((_QWORD *)v7 + 3) = 0;
  Current = DXGPROCESS::GetCurrent();
  v176 = Current;
  v14 = *(DXGADAPTER ***)(v12 + 3256);
  v175 = v14;
  v15 = 0;
  if ( *(_QWORD *)(v12 + 3248) )
    v15 = *(struct ADAPTER_DISPLAY **)(v12 + 3248);
  v134 = v15;
  v160 = a2 & -(__int64)(a4 != 0);
  if ( a4 )
    v16 = *(_DWORD *)((a2 & -(__int64)(a4 != 0)) + 0x14);
  else
    v16 = *((_DWORD *)v135 + 1);
  v131 = v16;
  DXGPROCESS::GetAllocationSafe(Current, &v137, (unsigned int)v16);
  v17 = v137;
  if ( !v137 || *(_QWORD *)(*(_QWORD *)(v137[1] + 16LL) + 16LL) != *(_QWORD *)(v156[2] + 16LL) )
  {
LABEL_50:
    DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v137);
LABEL_51:
    CIFlipPresentHistoryToken::~CIFlipPresentHistoryToken((CIFlipPresentHistoryToken *)&v129);
    return 0;
  }
  v180 = v14;
  if ( v159 )
  {
    v40 = v137[5];
    if ( v40 )
    {
      if ( (*(_DWORD *)(v40 + 4) & 1) != 0 )
        *((_QWORD *)v7 + 3) = *(_QWORD *)(*(_QWORD *)(v40 + 56) + 176LL);
    }
  }
  if ( a4 )
    v18 = *((_QWORD *)v147 + 187);
  else
    v18 = 0;
  v168 = v18;
  v161 = v18;
  v138 = (*(_DWORD *)(v17[6] + 4LL) >> 6) & 0xF;
  v150 = 0;
  v144 = 0;
  v151 = 0;
  v152 = 0;
  v132 = 0;
  v166 = *(_QWORD *)(*(__int64 (__fastcall **)(__int128 *))(v129 + 24))(&v129);
  v142 = 0;
  v182 = 0;
  v183 = 0;
  *(_QWORD *)v145 = (char *)v7 + (*((_BYTE *)v7 + 356) != 0 ? 0xF0 : 0) + 528;
  v19 = v14[92];
  p_CompositionBindingId = &v154->CompositionBindingId;
  CompositionBindingId = v154->CompositionBindingId;
  v21 = (*(__int64 (__fastcall **)(__int128 *))(v129 + 16))(&v129);
  v128 = v145[0];
  (*(void (__fastcall **)(DXGADAPTER *, unsigned int *, __int64, UINT64))(*((_QWORD *)v19 + 1) + 432LL))(
    v14[93],
    &v138,
    v21,
    CompositionBindingId);
  (*(void (__fastcall **)(__int128 *, __int64))(v129 + 32))(&v129, v166);
  (*(void (__fastcall **)(__int128 *, _QWORD))(v129 + 48))(&v129, v138);
  *((_DWORD *)v7 + 29) = v138;
  v22 = (struct _LUID *)(*(__int64 (__fastcall **)(__int128 *))(v129 + 16))(&v129);
  RtlCopyLuid((PLUID)((char *)v7 + 156), v22);
  *((_QWORD *)v7 + 21) = *p_CompositionBindingId;
  *(_DWORD *)v7 &= ~0x10000u;
  v23 = v146;
  if ( v146 )
  {
    v70 = v160;
    v71 = *(_DWORD *)v7 ^ (*(_DWORD *)(v160 + 88) ^ *(_DWORD *)v7) & 4;
    *(_DWORD *)v7 = v71;
    v72 = v71 ^ (v71 ^ (4 * *(_DWORD *)(v70 + 88))) & 0x80000;
    *(_DWORD *)v7 = v72;
    v73 = v72 ^ (v72 ^ (4 * *(_DWORD *)(v70 + 88))) & 0x100000;
    *(_DWORD *)v7 = v73;
    *(_DWORD *)v7 = v73 ^ (v73 ^ (4 * *(_DWORD *)(v70 + 88))) & 0x200000;
  }
  *(_DWORD *)v7 ^= ((unsigned __int8)*(_DWORD *)v7
                  ^ (unsigned __int8)(8 * (*(__int64 (__fastcall **)(__int128 *))(v129 + 200))(&v129)))
                 & 8;
  *(_DWORD *)v7 ^= ((unsigned __int8)*(_DWORD *)v7
                  ^ (unsigned __int8)(16 * (*(__int64 (__fastcall **)(__int128 *))(v129 + 208))(&v129)))
                 & 0x10;
  *(_DWORD *)v7 ^= (*(_DWORD *)v7
                  ^ ((*(unsigned __int8 (__fastcall **)(__int128 *))(v129 + 216))(&v129) << 28))
                 & 0x10000000;
  *((_DWORD *)v7 + 1) ^= ((unsigned __int8)*((_DWORD *)v7 + 1)
                        ^ (unsigned __int8)((*(unsigned __int8 (__fastcall **)(__int128 *))(v129 + 224))(&v129) << 6))
                       & 0x40;
  *((_DWORD *)v7 + 1) ^= ((unsigned __int16)*((_DWORD *)v7 + 1)
                        ^ (unsigned __int16)((*(unsigned __int8 (__fastcall **)(__int128 *))(v129 + 320))(&v129) << 8))
                       & 0x100;
  *((_DWORD *)v7 + 1) ^= ((unsigned __int16)*((_DWORD *)v7 + 1)
                        ^ (unsigned __int16)((*(unsigned __int8 (__fastcall **)(__int128 *))(v129 + 328))(&v129) << 9))
                       & 0x200;
  v24 = v141;
  (*(void (__fastcall **)(__int128 *, DXGADAPTER *))(v129 + 56))(&v129, v141);
  *((_DWORD *)v7 + 28) = (*(__int64 (__fastcall **)(__int128 *))(v129 + 64))(&v129);
  *((_DWORD *)v7 + 48) = *(_DWORD *)(*(__int64 (__fastcall **)(__int128 *))(v129 + 72))(&v129);
  *(_DWORD *)v7 ^= (*(_DWORD *)v7
                  ^ ((*(unsigned __int8 (__fastcall **)(__int128 *))(v129 + 192))(&v129) << 25))
                 & 0x2000000;
  *((_DWORD *)v7 + 36) = (*(__int64 (__fastcall **)(__int128 *))(v129 + 80))(&v129);
  *((_DWORD *)v7 + 37) = (*(__int64 (__fastcall **)(__int128 *))(v129 + 88))(&v129);
  if ( v23 )
    v25 = *((_DWORD *)v23 + 96);
  else
    v25 = 1;
  *((_DWORD *)v7 + 34) = v25;
  v26 = *((_BYTE *)v7 + 356);
  if ( v26 )
    v162 = (unsigned int *)((char *)v7 + 616);
  else
    v162 = 0;
  if ( v26 )
    *((_DWORD *)v7 + 162) = -1;
  if ( bTracingEnabled )
    *((_QWORD *)v7 + 23) = VIDMM_EXPORT::VidMmETWAllocationHandle(v14[95], v14[96], v131);
  v27 = (*(__int64 (__fastcall **)(__int128 *))(v129 + 96))(&v129);
  v135 = (struct VIDSCH_SUBMIT_DATA_BASE *)((char *)v7 + 124);
  *((_DWORD *)v7 + 31) = v27;
  v28 = (int *)((char *)v7 + 124);
  v158 = 1;
  if ( !v27
    && (!(*(unsigned __int8 (__fastcall **)(__int128 *))(v129 + 216))(&v129) || (*((_DWORD *)v24 + 647) & 0x40) == 0) )
  {
    v28 = &v158;
  }
  v29 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *))(*((_QWORD *)v14[92] + 1) + 536LL))(v156[100], v138, v28);
  v31 = v29;
  *((_DWORD *)v7 + 30) = v29;
  if ( v29 != 5 && *(_DWORD *)v135 )
  {
    v76 = (*(__int64 (__fastcall **)(__int128 *))(v129 + 64))(&v129);
    v77 = (*(__int64 (__fastcall **)(__int128 *))(v129 + 104))(&v129);
    WdLogSingleEntry4(8, v154, v77, v76, v31);
    WdLogGlobalForLineNumber = 2291;
    goto LABEL_59;
  }
  if ( !v150 )
  {
    if ( v151 )
    {
      v131 = D3DDDI_HDR_METADATA_TYPE_NONE;
      v135 = 0;
      v86 = v14[92];
      v87 = *((_QWORD *)v7 + 21);
      v88 = (const struct _LUID *)(*(__int64 (__fastcall **)(__int128 *))(v129 + 16))(&v129);
      VIDSCH_EXPORT::VidSchExitIndependentFlip(
        v86,
        v14[93],
        1 << *((_DWORD *)v7 + 29),
        v88,
        v87,
        &v132,
        0,
        0,
        (int *)&v131,
        (unsigned __int64 *)&v135);
      ADAPTER_DISPLAY::UpdateIndependentFlipState(v134, *((_DWORD *)v7 + 29), v132, 0);
    }
    else if ( !v152 )
    {
LABEL_59:
      DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v137);
      (*(void (__fastcall **)(__int128 *, __int64))v129)(&v129, 1);
      return 0;
    }
    LOBYTE(v30) = 1;
    (*(void (__fastcall **)(__int128 *, __int64))(v129 + 232))(&v129, v30);
    goto LABEL_59;
  }
  *((_QWORD *)v7 + 22) = *(_QWORD *)(*(__int64 (__fastcall **)(__int128 *))(v129 + 24))(&v129);
  if ( !(*(unsigned __int8 (__fastcall **)(__int128 *))(v129 + 240))(&v129) )
  {
    v131 = D3DDDI_HDR_METADATA_TYPE_NONE;
    v135 = 0;
    v89 = v14[92];
    v90 = *((_QWORD *)v7 + 21);
    v91 = (const struct _LUID *)(*(__int64 (__fastcall **)(__int128 *))(v129 + 16))(&v129);
    VIDSCH_EXPORT::VidSchExitIndependentFlip(
      v89,
      v14[93],
      1 << *((_DWORD *)v7 + 29),
      v91,
      v90,
      &v132,
      0,
      0,
      (int *)&v131,
      (unsigned __int64 *)&v135);
    LOBYTE(v92) = 1;
    (*(void (__fastcall **)(__int128 *, __int64))(v129 + 232))(&v129, v92);
    ADAPTER_DISPLAY::UpdateIndependentFlipState(v134, *((_DWORD *)v7 + 29), v132, 0);
    WdLogSingleEntry0(8);
    WdLogGlobalForLineNumber = 2360;
    goto LABEL_50;
  }
  if ( v144 || DXGADAPTER::SupportCheckMultiPlaneOverlaySupport3(v14[2]) )
  {
    v32 = (*(__int64 (__fastcall **)(__int128 *))(v129 + 248))(&v129);
    v33 = v134;
    if ( !v32 )
    {
      ADAPTER_DISPLAY::UpdateIndependentFlipState(v134, *((_DWORD *)v7 + 29), v132, 1u);
LABEL_34:
      *(_DWORD *)v7 = *(_DWORD *)v7 & 0x7BFFFFFF | ((v144 & 1 | (32 * v142)) << 26);
      *(_OWORD *)((char *)v7 + 436) = v182;
      *(struct tagRECT *)((char *)v7 + 452) = v183;
      goto LABEL_35;
    }
    DXGDISPLAYSTATEMUTEX::DXGDISPLAYSTATEMUTEX((DXGDISPLAYSTATEMUTEX *)&v165, v134);
    DXGAUTOMUTEX::Acquire((DXGAUTOMUTEX *)&v165);
    PostCompositionStretching = ADAPTER_DISPLAY::GetPostCompositionStretching(v33, *((_DWORD *)v7 + 29));
    v130 = PostCompositionStretching;
    if ( PostCompositionStretching )
    {
      if ( IsYUVAllocation(*(void **)(v137[6] + 16LL), (struct ADAPTER_RENDER *)v14)
        || DISPLAY_SOURCE::GetEnabledPlaneCountUnsafe((DISPLAY_SOURCE *)(*((_QWORD *)v33 + 16)
                                                                       + 4024LL * *((unsigned int *)v7 + 29))) > 1 )
      {
        PostCompositionStretching = 0;
        v130 = 0;
      }
      else
      {
        PostCompositionStretching = v130;
      }
    }
    v171 = 0;
    if ( v132 || (v102 = 1, !PostCompositionStretching) )
      v102 = 0;
    if ( CheckAndUpdateMultiPlaneOverlayFromInternalState(
           *((_DWORD *)v7 + 29),
           v132,
           (struct CIFlipPresentHistoryTokenData *)&v129,
           v102,
           (struct ADAPTER_RENDER *)v14,
           v33,
           &v171) )
    {
      v103 = (__int64 *)(*(__int64 (__fastcall **)(__int128 *))(v129 + 8))(&v129);
      v140 = v103;
      v104 = *(__int64 **)v145;
      **(_WORD **)v145 = *(_WORD *)v103;
      *((_WORD *)v104 + 2) = *((_WORD *)v103 + 2);
      *((_WORD *)v104 + 1) = *((_WORD *)v103 + 4);
      *((_WORD *)v104 + 3) = *((_WORD *)v103 + 6);
      *((_DWORD *)v104 + 6) = (*(__int64 (__fastcall **)(__int128 *))(v129 + 112))(&v129);
      if ( v130 )
      {
        v79 = *v104;
        v104[1] = *v104;
        v104[2] = v79;
        v80 = *(_OWORD *)v140;
        v182 = v80;
        v183 = v171;
        if ( (_DWORD)v80 != v171.left
          || __PAIR64__(DWORD2(v182), DWORD1(v80)) != *(_QWORD *)&v171.top
          || (v78 = 0, HIDWORD(v182) != v171.bottom) )
        {
          v78 = 1;
        }
        v142 = v78;
        if ( !(_DWORD)v78 )
        {
          v182 = 0;
          v183 = 0;
        }
        (*(void (__fastcall **)(DXGADAPTER *, _QWORD, __int64, __int128 *, struct tagRECT *))(*((_QWORD *)v14[92] + 1)
                                                                                            + 1008LL))(
          v14[93],
          *((unsigned int *)v7 + 29),
          v78,
          &v182,
          &v183);
        UpdatePostComposition(*((_DWORD *)v7 + 29), v142 != 0, DWORD2(v182) - v182, HIDWORD(v182) - DWORD1(v182), v33);
      }
      (*(void (__fastcall **)(DXGADAPTER *, _QWORD, __int64 *, _QWORD))(*((_QWORD *)v14[92] + 1) + 440LL))(
        v14[93],
        *((unsigned int *)v7 + 29),
        v104,
        v132);
      DXGAUTOMUTEX::Release((DXGAUTOMUTEX *)&v165);
      DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)&v165);
      goto LABEL_34;
    }
    DXGAUTOMUTEX::Release((DXGAUTOMUTEX *)&v165);
    v131 = D3DDDI_HDR_METADATA_TYPE_NONE;
    v135 = 0;
    v105 = v14[92];
    v106 = *((_QWORD *)v7 + 21);
    v107 = (const struct _LUID *)(*(__int64 (__fastcall **)(__int128 *))(v129 + 16))(&v129);
    VIDSCH_EXPORT::VidSchExitIndependentFlip(
      v105,
      v14[93],
      1 << *((_DWORD *)v7 + 29),
      v107,
      v106,
      &v132,
      0,
      0,
      (int *)&v131,
      (unsigned __int64 *)&v135);
    WdLogSingleEntry1(3, v132);
    WdLogGlobalForLineNumber = 2470;
    LOBYTE(v108) = 1;
    (*(void (__fastcall **)(__int128 *, __int64))(v129 + 232))(&v129, v108);
    ADAPTER_DISPLAY::UpdateIndependentFlipState(v134, *((_DWORD *)v7 + 29), v132, 0);
    DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)&v165);
    goto LABEL_50;
  }
  v93 = (_DWORD *)(*(__int64 (__fastcall **)(__int128 *))(v129 + 8))(&v129);
  *(_QWORD *)v145 = v93;
  if ( v93[2] - *v93 != (*(unsigned int (__fastcall **)(__int128 *))(v129 + 120))(&v129)
    || (v94 = v93[3] - v93[1], v94 != (*(unsigned int (__fastcall **)(__int128 *))(v129 + 128))(&v129))
    || (*(unsigned __int8 (__fastcall **)(__int128 *))(v129 + 248))(&v129) )
  {
    v131 = D3DDDI_HDR_METADATA_TYPE_NONE;
    v135 = 0;
    v95 = v14[92];
    v96 = *((_QWORD *)v7 + 21);
    v97 = (const struct _LUID *)(*(__int64 (__fastcall **)(__int128 *))(v129 + 16))(&v129);
    VIDSCH_EXPORT::VidSchExitIndependentFlip(
      v95,
      v14[93],
      1 << *((_DWORD *)v7 + 29),
      v97,
      v96,
      &v132,
      0,
      0,
      (int *)&v131,
      (unsigned __int64 *)&v135);
    v98 = (*(unsigned int (__fastcall **)(__int128 *))(v129 + 128))(&v129);
    v99 = (*(__int64 (__fastcall **)(__int128 *))(v129 + 120))(&v129);
    WdLogSingleEntry4(
      8,
      *(_DWORD *)(*(_QWORD *)v145 + 8LL) - **(_DWORD **)v145,
      *(_DWORD *)(*(_QWORD *)v145 + 12LL) - *(_DWORD *)(*(_QWORD *)v145 + 4LL),
      v99,
      v98);
    WdLogGlobalForLineNumber = 2523;
    LOBYTE(v100) = 1;
    (*(void (__fastcall **)(__int128 *, __int64))(v129 + 232))(&v129, v100);
    ADAPTER_DISPLAY::UpdateIndependentFlipState(v134, *((_DWORD *)v7 + 29), 0, 0);
LABEL_149:
    DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v137);
    CIFlipPresentHistoryToken::~CIFlipPresentHistoryToken((CIFlipPresentHistoryToken *)&v129);
    return v11;
  }
  v33 = v134;
  ADAPTER_DISPLAY::UpdateIndependentFlipState(v134, *((_DWORD *)v7 + 29), 0, 1u);
LABEL_35:
  if ( v33 && (*((_DWORD *)v33 + 6) & 0x10) != 0 )
  {
    if ( !ADAPTER_DISPLAY::IsHdrEnabled(v33, v138) )
    {
      *((_DWORD *)v7 + 90) = 0;
LABEL_39:
      *(_DWORD *)v7 |= 0x40000000u;
      goto LABEL_40;
    }
    *(_DWORD *)v7 ^= (*(_DWORD *)v7
                    ^ ((*(unsigned __int8 (__fastcall **)(__int128 *))(v129 + 256))(&v129) << 30))
                   & 0x40000000;
    v109 = (*(__int64 (__fastcall **)(__int128 *))(v129 + 136))(&v129);
    *((_DWORD *)v7 + 90) = v109;
    if ( (*(_DWORD *)v7 & 0x40000000) != 0 )
    {
      if ( v109 )
      {
        v110 = v109 - 1;
        if ( v110 )
        {
          if ( v110 == 1 )
          {
            v111 = (*(__int64 (__fastcall **)(__int128 *))(v129 + 152))(&v129);
            *(_OWORD *)((char *)v7 + 364) = *(_OWORD *)v111;
            *(_OWORD *)((char *)v7 + 380) = *(_OWORD *)(v111 + 16);
            *(_OWORD *)((char *)v7 + 396) = *(_OWORD *)(v111 + 32);
            *(_OWORD *)((char *)v7 + 412) = *(_OWORD *)(v111 + 48);
            *(_QWORD *)((char *)v7 + 428) = *(_QWORD *)(v111 + 64);
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
          v112 = (_OWORD *)(*(__int64 (__fastcall **)(__int128 *))(v129 + 144))(&v129);
          *(_OWORD *)((char *)v7 + 364) = *v112;
          *(_OWORD *)((char *)v7 + 376) = *(_OWORD *)((char *)v112 + 12);
        }
      }
    }
    else
    {
      if ( v109 > 2 )
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
      v131 = D3DDDI_HDR_METADATA_TYPE_NONE;
      memset(&v165, 0, sizeof(v165));
      if ( !(unsigned int)PopulateHDRMetadataFromDisplay(*((_DWORD *)v7 + 29), v33, &v165, &v131) )
      {
        *(_OWORD *)((char *)v7 + 364) = *(_OWORD *)v165.RedPrimary;
        *(_OWORD *)((char *)v7 + 376) = *(_OWORD *)v165.WhitePoint;
        *((_DWORD *)v7 + 90) = v131;
        goto LABEL_39;
      }
    }
  }
LABEL_40:
  (*(void (__fastcall **)(__int128 *, _QWORD))(v129 + 160))(&v129, v132);
  v34 = (_DWORD *)((char *)v7 + 600);
  if ( !*((_BYTE *)v7 + 356) )
    v34 = (_DWORD *)((char *)v7 + 496);
  *v34 ^= ((unsigned __int16)*v34 ^ (unsigned __int16)(1 << v132)) & 0x3FF;
  v35 = 1;
  v136 = 1;
  IsDxgmms2 = DXGADAPTER::IsDxgmms2(v141);
  v37 = v146;
  if ( IsDxgmms2 && v146 )
  {
    v35 = *(_DWORD *)(v160 + 92) + 1;
    v136 = v35;
  }
  Pool2 = 0;
  v149 = 0;
  v172 = 0;
  v174 = 0;
  if ( v35 <= 4 )
  {
    Pool2 = v173;
    v149 = v173;
    v172 = v173;
    if ( !v35 )
    {
LABEL_47:
      v174 = v35;
      goto LABEL_48;
    }
    memset(v173, 0, 8LL * v35);
    Pool2 = v172;
LABEL_46:
    v149 = Pool2;
    goto LABEL_47;
  }
  if ( 0xFFFFFFFFFFFFFFFFuLL / v35 >= 8 )
  {
    Pool2 = (_BYTE *)ExAllocatePool2(256, 8LL * v35, 1265072196);
    v172 = Pool2;
    goto LABEL_46;
  }
LABEL_48:
  *(_QWORD *)v165.RedPrimary = Pool2;
  if ( !Pool2 )
  {
    v172 = 0;
    v174 = 0;
    DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v137);
    (*(void (__fastcall **)(__int128 *, __int64))v129)(&v129, 1);
    return 3221225495LL;
  }
  v184[0] = 0;
  v185 = 0;
  PagedPoolArray<DXGALLOCATIONREFERENCE,4>::AllocateElements(v184, v35);
  *(_QWORD *)v145 = v184[0];
  if ( !v184[0] )
  {
    PagedPoolArray<DXGALLOCATIONREFERENCE,4>::~PagedPoolArray<DXGALLOCATIONREFERENCE,4>(v184);
    if ( v172 != v173 && v172 )
      ExFreePoolWithTag(v172, 0);
    v172 = 0;
    v174 = 0;
    v11 = -1073741801;
    goto LABEL_149;
  }
  v41 = v7;
  v157 = v7;
  v42 = v141;
  v43 = v141;
  v134 = v141;
  v44 = 0;
  v133 = 0;
  v131 = D3DDDI_HDR_METADATA_TYPE_NONE;
  v45 = 0;
  while ( 1 )
  {
    v139 = v45;
    if ( (unsigned int)v45 >= v35 )
      break;
    if ( (_DWORD)v45 )
    {
      v148 = (unsigned int)v45;
      v133 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v147 + 187) + 8LL * (unsigned int)v45) + 388LL);
      v143 = 0;
      RtlCopyFromUser(&v143, (void *)(*(_QWORD *)(v160 + 1456) + 4LL * (unsigned int)(v45 - 1)), 4u);
      v140 = (__int64 *)(*(_QWORD *)v145 + 8 * v148);
      AllocationSafe = DXGPROCESS::GetAllocationSafe(v176, &v171, v143);
      DXGALLOCATIONREFERENCE::MoveAssign(v140, AllocationSafe);
      DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v171);
      v48 = (_QWORD *)*v140;
      v155 = v48;
      if ( !v48 )
      {
        WdLogSingleEntry2(2, v143, -1073741811);
        WdLogGlobalForLineNumber = 2686;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Invalid allocation handle in present: 0x%I64x. Returning 0x%I64x",
          v143,
          -1073741811,
          0,
          0,
          0);
        v44 = -1073741811;
        v133 = -1073741811;
        v153 = -1073741811;
        v43 = v134;
        break;
      }
      v85 = v147;
      v114 = 8 * v148;
      if ( *(_QWORD *)(*(_QWORD *)(v48[1] + 16LL) + 16LL) != *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v147 + 187) + 8 * v148)
                                                                                               + 16LL)
                                                                                   + 16LL)
                                                                       + 16LL) )
      {
        _mm_lfence();
        WdLogSingleEntry3(2, *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v147 + 187) + 8 * v148) + 16LL), v48, -1073741811);
        WdLogGlobalForLineNumber = 2695;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Device 0x%p does not match allocation 0x%p owner, returning 0x%I64x",
          *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v147 + 187) + 8 * v148) + 16LL),
          *v140,
          -1073741811,
          0,
          0);
        v44 = -1073741811;
        v133 = -1073741811;
        v153 = -1073741811;
        v43 = v134;
        break;
      }
      v47 = v139;
      if ( *((_BYTE *)v7 + 356) )
        v82 = (_QWORD *)((char *)v7
                       + 64 * (unsigned __int64)(unsigned int)(v139 * *((_DWORD *)v7 + 151))
                       + (unsigned int)(8 * *((_DWORD *)v7 + 151) * (*((_DWORD *)v7 + 152) + 28))
                       + 632);
      else
        v82 = (_QWORD *)((char *)v157 + 512);
      *v82 = *(_QWORD *)(v48[6] + 16LL);
      if ( !*((_BYTE *)v141 + 3185) )
      {
        v83 = *(__int64 **)(*(_QWORD *)(v114 + *((_QWORD *)v85 + 187)) + 184LL);
        v140 = v83;
        if ( *((_BYTE *)v7 + 356) )
        {
          v84 = (__int64 **)((char *)v7
                           + 64 * (unsigned __int64)(unsigned int)(v47 * *((_DWORD *)v7 + 151))
                           + *((_DWORD *)v7 + 151) * ((8 * *((_DWORD *)v7 + 152) + 231) & 0xFFFFFFF8)
                           + 624);
          v85 = v147;
          v83 = v140;
        }
        else
        {
          v84 = (__int64 **)((char *)v7 + 568);
        }
        *v84 = v83;
      }
      *((_DWORD *)v7 + 34) |= 1 << v133;
      v115 = *(_QWORD *)(v114 + *((_QWORD *)v85 + 187));
      if ( (*(_DWORD *)(v115 + 392) & 0x10) == 0 )
        *(_QWORD *)((char *)v7 + v114 + *((unsigned int *)v7 + 138)) = *(_QWORD *)(v115 + 256);
    }
    else
    {
      v155 = v137;
      if ( *((_BYTE *)v7 + 356) )
        v46 = (_QWORD *)((char *)v7 + (unsigned int)(8 * *((_DWORD *)v7 + 151) * (*((_DWORD *)v7 + 152) + 28)) + 632);
      else
        v46 = (_QWORD *)((char *)v41 + 512);
      *v46 = *(_QWORD *)(v137[6] + 16LL);
      if ( !*((_BYTE *)v42 + 3185) )
      {
        if ( *((_BYTE *)v7 + 356) )
          v81 = (_QWORD *)((char *)v7 + (unsigned int)(8 * *((_DWORD *)v7 + 151) * (*((_DWORD *)v7 + 152) + 28)) + 624);
        else
          v81 = (_QWORD *)((char *)v7 + 568);
        *v81 = *((_QWORD *)v37 + 23);
      }
      if ( DXGADAPTER::IsDxgmms2(v42) && v37 && (*((_DWORD *)v37 + 98) & 0x10) == 0 )
        *(_QWORD *)((char *)v7 + *((unsigned int *)v7 + 138)) = *((_QWORD *)v37 + 32);
      v148 = 0;
    }
    if ( *((_BYTE *)v7 + 356) )
      v49 = (unsigned __int64)v7
          + 64 * (unsigned __int64)(unsigned int)(v47 * *((_DWORD *)v7 + 151))
          + (unsigned int)(8 * *((_DWORD *)v7 + 151) * (*((_DWORD *)v7 + 152) + 28))
          + 656;
    else
      v49 = (unsigned __int64)v7 + 504;
    v140 = (__int64 *)v49;
    v133 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64, DXGADAPTER *, unsigned int *))(*((_QWORD *)v14[95] + 1) + 400LL))(
             v156[99],
             v48[3],
             v49,
             v14[96],
             v162);
    if ( v133 < 0 )
    {
      WdLogSingleEntry2(2, v155, -1073741811);
      WdLogGlobalForLineNumber = 2744;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Failed to reference allocation for submission (0x%I64x). Returning 0x%I64x",
        (__int64)v155,
        -1073741811,
        0,
        0,
        0);
      v44 = v133;
      v43 = v134;
      break;
    }
    *(_QWORD *)&v149[8 * v148] = *v140;
    ++v131;
    v50 = v155[5];
    if ( v50 )
      v51 = (*(_DWORD *)(v50 + 4) & 8) != 0;
    else
      v51 = 0;
    if ( v51 )
      v52 = *(_QWORD *)(*(_QWORD *)(v50 + 56) + 184LL);
    else
      v52 = 0;
    if ( *((_BYTE *)v7 + 356) )
      *(_QWORD *)((char *)v7
                + 64 * v139 * *((_DWORD *)v7 + 151)
                + *((_DWORD *)v7 + 151) * ((8 * *((_DWORD *)v7 + 152) + 231) & 0xFFFFFFF8)
                + 664) = v52;
    else
      *((_QWORD *)v7 + 72) = v52;
    *(_DWORD *)v7 |= 0x1000000u;
    v53 = *p_CompositionBindingId;
    v54 = *(_QWORD *)(*(__int64 (__fastcall **)(__int128 *))(v129 + 16))(&v129);
    v55 = (*(__int64 (__fastcall **)(__int128 *))(v129 + 64))(&v129);
    v56 = (*(__int64 (__fastcall **)(__int128 *))(v129 + 104))(&v129);
    WdLogSingleEntry5(8, v154, v56, v55, v54, v53);
    WdLogGlobalForLineNumber = 2767;
    if ( (*(unsigned __int8 (__fastcall **)(__int128 *))(v129 + 344))(&v129)
      && (*((_DWORD *)v7 + 1) |= 2u,
          *((_QWORD *)v7 + 60) = (*(__int64 (__fastcall **)(__int128 *))(v129 + 352))(&v129),
          v116 = (_DWORD *)(*(__int64 (__fastcall **)(__int128 *))(v129 + 360))(&v129),
          v117 = v116,
          (*((_QWORD *)v7 + 61) = v116) != 0)
      && !v116[1] )
    {
      if ( *v116 != 64 )
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
      v117[8] = *((_DWORD *)v7 + 29);
      v43 = v134;
      *((_QWORD *)v117 + 3) = *(_QWORD *)((char *)v134 + 412);
    }
    else
    {
      v43 = v134;
    }
    v45 = (unsigned int)(v139 + 1);
    v14 = v175;
    v35 = v136;
    v37 = v146;
    v44 = v133;
    v42 = v141;
    v41 = v157;
  }
  *((_DWORD *)v10 + 35) = v35;
  if ( v44 < 0 || (*((_DWORD *)v43 + 647) & 0x20) == 0 )
  {
    v57 = v141;
LABEL_83:
    if ( v144 && (*(_DWORD *)v7 & 0x1000000) != 0 )
    {
      v135 = 0;
      if ( *((int *)v57 + 783) < 2500
        || (v74 = ReadPresentDirtyRectsData(v42, v132, (const struct CIFlipPresentHistoryTokenData *)&v129, &v135),
            v74 >= 0) )
      {
        *((_QWORD *)v10 + 4) = v135;
      }
      else
      {
        v75 = v74;
        WdLogSingleEntry1(2, v74);
        WdLogGlobalForLineNumber = 2868;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Failed to read dirty rects data. Returning 0x%I64x",
          v75,
          0,
          0,
          0,
          0);
      }
    }
    goto LABEL_84;
  }
  memset(&v181, 0, sizeof(v181));
  v181.Flags.Value = 0x2000;
  if ( v159 )
  {
    v181.PrivateDriverDataSize = *((_DWORD *)v159 + 2);
    v181.pPrivateDriverData = (char *)v159 + 16;
  }
  P = 0;
  v188 = 0;
  PagedPoolZeroedArray<_DXGK_PRESENTALLOCATIONINFO,4>::AllocateElements(&P, v35);
  v181.pAllocationList = (DXGK_ALLOCATIONLIST *)P;
  if ( P )
  {
    v59 = *((_DWORD *)v134 + 649);
    if ( (v59 & 0x80u) == 0 || (v130 = 1, (v59 & 0x40) != 0) )
      v130 = 0;
    v60 = 0;
    v136 = 0;
    if ( v35 )
    {
      v61 = v147;
      v62 = v130;
      do
      {
        v63 = 8LL * v60;
        if ( v37 )
          v64 = *(_WORD *)(*(_QWORD *)(v63 + *((_QWORD *)v61 + 187)) + 388LL);
        else
          v64 = 0;
        v65 = 32LL * v60;
        v164 = (struct DXGCONTEXT *)v65;
        *(_WORD *)((char *)&v181.pAllocationList[1].hDeviceSpecificAllocation + v65 + 2) = v64;
        if ( v60 )
          v66 = *(_QWORD **)(v63 + *(_QWORD *)v145);
        else
          v66 = v137;
        if ( v37 )
          v62 = *(_BYTE *)(*(_QWORD *)(v63 + *((_QWORD *)v61 + 187)) + 431LL);
        *((_QWORD *)&v181.pAllocationList->hDeviceSpecificAllocation + 4 * v60) = v66[4];
        pAllocationList = v181.pAllocationList;
        AllocationGpuVirtualAddress = VIDMM_EXPORT::VidMmGetAllocationGpuVirtualAddress(
                                        v14[95],
                                        (const struct VIDMM_MULTI_ALLOC *)v66[3],
                                        v62 != 0,
                                        *(unsigned __int16 *)((char *)&v181.pAllocationList[1].hDeviceSpecificAllocation
                                                            + v65
                                                            + 2));
        *(_QWORD *)((char *)v164 + (_QWORD)pAllocationList + 8) = AllocationGpuVirtualAddress;
        v60 = v136 + 1;
        v136 = v60;
        v37 = v146;
      }
      while ( v60 < v35 );
      v10 = v169;
      v7 = v170;
    }
    v181.FlipInterval = *(_DWORD *)v135;
    v181.Flags.Value = v181.Flags.Value & 0xFFFFE8FF | (*(_DWORD *)v157 >> 11) & 0x1700;
    v181.NumSrcAllocations = v35;
    v57 = v141;
    v69 = 0;
    if ( !*((_BYTE *)v141 + 3185) )
      v69 = (void *)*((_QWORD *)v37 + 23);
    v133 = ADAPTER_RENDER::DdiPresent((ADAPTER_RENDER *)v14, v69, &v181);
    v42 = (DXGADAPTER *)P;
    if ( v133 >= 0 )
    {
      if ( P != v187 && P )
        ExFreePoolWithTag(P, 0);
      P = 0;
      v188 = 0;
      goto LABEL_83;
    }
    if ( P != v187 && P )
      ExFreePoolWithTag(P, 0);
  }
  P = 0;
  v188 = 0;
LABEL_84:
  v58 = v133;
  if ( v133 < 0 )
  {
    v118 = 0;
    v119 = v131;
    if ( v131 )
    {
      v120 = v146;
      v121 = v161;
      do
      {
        if ( v120 )
          v122 = *(_DWORD *)(*(_QWORD *)(8LL * v118 + v121) + 388LL);
        else
          LOBYTE(v122) = 0;
        VIDMM_EXPORT::VidMmUnreferencePrimaryAllocation(
          v14[95],
          v14[96],
          1 << v122,
          *(struct VIDMM_ALLOC **)&v149[8 * v118++],
          v128,
          v162);
      }
      while ( v118 < v119 );
    }
    v123 = *p_CompositionBindingId;
    v124 = *(_QWORD *)(*(__int64 (__fastcall **)(__int128 *, struct VIDSCH_SUBMIT_DATA_BASE *, __int64, DXGADAPTER *))(v129 + 16))(
                        &v129,
                        v41,
                        v45,
                        v43);
    v125 = (*(__int64 (__fastcall **)(__int128 *))(v129 + 64))(&v129);
    v126 = (*(__int64 (__fastcall **)(__int128 *))(v129 + 104))(&v129);
    WdLogSingleEntry5(8, v154, v126, v125, v124, v123);
    WdLogGlobalForLineNumber = 2896;
    LOBYTE(v127) = 1;
    (*(void (__fastcall **)(__int128 *, __int64))(v129 + 232))(&v129, v127);
    *(_DWORD *)v157 &= ~0x1000000u;
    v58 = 0;
  }
  PagedPoolArray<DXGALLOCATIONREFERENCE,4>::~PagedPoolArray<DXGALLOCATIONREFERENCE,4>(v184);
  if ( v172 != v173 && v172 )
    ExFreePoolWithTag(v172, 0);
  v172 = 0;
  v174 = 0;
  DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v137);
  (*(void (__fastcall **)(__int128 *, __int64))v129)(&v129, 1);
  return v58;
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
