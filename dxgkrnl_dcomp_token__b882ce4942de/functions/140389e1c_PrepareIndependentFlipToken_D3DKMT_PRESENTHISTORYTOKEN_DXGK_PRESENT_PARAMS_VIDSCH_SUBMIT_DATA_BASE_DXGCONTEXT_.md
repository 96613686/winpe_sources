# PrepareIndependentFlipToken(_D3DKMT_PRESENTHISTORYTOKEN *,DXGK_PRESENT_PARAMS *,VIDSCH_SUBMIT_DATA_BASE *,DXGCONTEXT *,_PRESENT_REDIRECTED_PARAMS *,CRefCountedBuffer *)

- ea: `0x140389e1c`
- end: `0x14038c359`
- name: `?PrepareIndependentFlipToken@@YAJPEAU_D3DKMT_PRESENTHISTORYTOKEN@@PEAUDXGK_PRESENT_PARAMS@@PEAUVIDSCH_SUBMIT_DATA_BASE@@PEAVDXGCONTEXT@@PEAU_PRESENT_REDIRECTED_PARAMS@@PEAVCRefCountedBuffer@@@Z`
- size: `9533`
- prototype: `__int64 __fastcall(struct _D3DKMT_PRESENTHISTORYTOKEN *, struct DXGK_PRESENT_PARAMS *, struct VIDSCH_SUBMIT_DATA_BASE *, struct DXGCONTEXT *, struct _PRESENT_REDIRECTED_PARAMS *, struct CRefCountedBuffer *)`
- caller_count: `2`
- callee_count: `37`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140390a24`
- `0x1403a2cec`

## callees

- `0x14000e568`
- `0x1400144ec`
- `0x1400150d0`
- `0x1400160e4`
- `0x14001b890`
- `0x14001c320`
- `0x14002fdc0`
- `0x140037028`
- `0x1400391ac`
- `0x14003c1cc`
- `0x14003cab0`
- `0x140040f34`
- `0x14004a498`
- `0x14004e500`
- `0x1400670a4`
- `0x1400758d4`
- `0x140079a1c`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0540`
- `0x1401f4090`
- `0x140244d64`
- `0x140312d4c`
- `0x140323854`
- `0x140327b90`
- `0x140327c10`
- `0x14032803c`
- `0x14033a7e0`
- `0x14034051c`
- `0x140340c40`
- `0x140340d50`
- `0x140389d90`
- `0x140389e1c`
- `0x14038c360`
- `0x14038c388`
- `0x14038c518`
- `0x1403c029c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14038adc9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14038b0c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14038b25c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14038b3d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14038adc9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14038b0c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14038b25c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14038b3d5`
- `ntoskrnl!ExAllocatePool2` at `0x14038b09e`
- `ntoskrnl!ExAllocatePool2` at `0x14038b09e`
- `ntoskrnl!RtlCopyLuid` at `0x14038a20d`
- `ntoskrnl!RtlCopyLuid` at `0x14038a20d`
- `watchdog!WdLogSingleEntry4` at `0x14038b049`
- `watchdog!WdLogSingleEntry4` at `0x14038b7a3`
- `watchdog!WdLogSingleEntry4` at `0x14038b049`
- `watchdog!WdLogSingleEntry4` at `0x14038b7a3`
- `watchdog!WdLogSingleEntry2` at `0x14038bdb9`
- `watchdog!WdLogSingleEntry2` at `0x14038c06e`
- `watchdog!WdLogSingleEntry2` at `0x14038bdb9`
- `watchdog!WdLogSingleEntry2` at `0x14038c06e`
- `watchdog!WdLogSingleEntry3` at `0x14038be50`
- `watchdog!WdLogSingleEntry3` at `0x14038be50`
- `watchdog!WdLogSingleEntry0` at `0x14038b5e4`
- `watchdog!WdLogSingleEntry0` at `0x14038bab5`
- `watchdog!WdLogSingleEntry0` at `0x14038bba2`
- `watchdog!WdLogSingleEntry0` at `0x14038c14d`
- `watchdog!WdLogSingleEntry0` at `0x14038b5e4`
- `watchdog!WdLogSingleEntry0` at `0x14038bab5`
- `watchdog!WdLogSingleEntry0` at `0x14038bba2`
- `watchdog!WdLogSingleEntry0` at `0x14038c14d`
- `watchdog!WdLogSingleEntry5` at `0x14038aaa9`
- `watchdog!WdLogSingleEntry5` at `0x14038c2ed`
- `watchdog!WdLogSingleEntry5` at `0x14038aaa9`
- `watchdog!WdLogSingleEntry5` at `0x14038c2ed`
- `watchdog!WdLogSingleEntry1` at `0x14038afa1`
- `watchdog!WdLogSingleEntry1` at `0x14038b9d7`
- `watchdog!WdLogSingleEntry1` at `0x14038bef0`
- `watchdog!WdLogSingleEntry1` at `0x14038afa1`
- `watchdog!WdLogSingleEntry1` at `0x14038b9d7`
- `watchdog!WdLogSingleEntry1` at `0x14038bef0`

## string_xrefs

- `0x14038afd0`: `Failed to read dirty rects data. Returning 0x%I64x`
- `0x14038bf33`: `Encountered exception reading source allocation handle. Returning 0x%I64x`

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
  struct _PRESENT_REDIRECTED_PARAMS *v10; // rdi
  struct VIDSCH_SUBMIT_DATA_BASE *v11; // r15
  unsigned int v12; // r14d
  __int64 v13; // rax
  __int64 v14; // rdi
  struct DXGPROCESS *Current; // r9
  DXGADAPTER **v16; // rsi
  struct ADAPTER_DISPLAY *v17; // rax
  enum _D3DDDI_HDR_METADATA_TYPE v18; // eax
  _QWORD *v19; // rax
  __int64 v20; // rcx
  DXGADAPTER *v21; // rbx
  UINT64 CompositionBindingId; // rdi
  __int64 v23; // rax
  struct _LUID *v24; // rax
  struct DXGCONTEXT *v25; // rbx
  DXGADAPTER *v26; // rdi
  int v27; // eax
  char v28; // al
  int v29; // eax
  int *v30; // rbx
  int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // rdi
  char v34; // al
  struct ADAPTER_DISPLAY *v35; // rbx
  _DWORD *v36; // r8
  UINT v37; // edi
  unsigned __int8 IsDxgmms2; // al
  struct DXGCONTEXT *v39; // rbx
  _BYTE *Pool2; // rcx
  __int64 v42; // rdx
  struct VIDSCH_SUBMIT_DATA_BASE *v43; // rcx
  int v44; // eax
  UINT v45; // r8d
  _QWORD *v46; // rcx
  DXGADAPTER *v47; // rax
  UINT v48; // r8d
  _QWORD *v49; // r10
  unsigned __int64 v50; // rdx
  __int64 v51; // rcx
  bool v52; // al
  __int64 v53; // r9
  UINT64 v54; // rsi
  __int64 v55; // rdi
  unsigned int v56; // ebx
  __int64 v57; // rax
  const struct DXGADAPTER *v58; // rcx
  DXGADAPTER *v59; // rdi
  unsigned int v60; // ebx
  int v61; // ecx
  unsigned int v62; // r9d
  struct DXGK_PRESENT_PARAMS *v63; // r15
  char v64; // r13
  __int64 v65; // r8
  __int16 v66; // r10
  __int64 v67; // rdx
  _QWORD *v68; // r10
  DXGK_ALLOCATIONLIST *pAllocationList; // rbx
  unsigned __int64 AllocationGpuVirtualAddress; // rax
  void *v71; // rdx
  unsigned __int64 v72; // r8
  int v73; // eax
  int v74; // ecx
  int v75; // edx
  int v76; // eax
  __int64 v77; // rbx
  unsigned int v78; // ebx
  __int64 v79; // rax
  __int64 v80; // r8
  __int64 v81; // rax
  __int128 v82; // xmm1
  _QWORD *v83; // rdx
  _QWORD *v84; // rax
  __int64 *v85; // rax
  __int64 **v86; // rdx
  struct DXGK_PRESENT_PARAMS *v87; // r11
  VIDSCH_EXPORT *v88; // rdi
  unsigned __int64 v89; // rbx
  const struct _LUID *v90; // rax
  VIDSCH_EXPORT *v91; // rdi
  unsigned __int64 v92; // rbx
  const struct _LUID *v93; // rax
  __int64 v94; // rdx
  _DWORD *v95; // rbx
  int v96; // ebx
  VIDSCH_EXPORT *v97; // rdi
  unsigned __int64 v98; // rbx
  const struct _LUID *v99; // rax
  __int64 v100; // rbx
  unsigned int v101; // eax
  __int64 v102; // rdx
  unsigned __int8 PostCompositionStretching; // al
  bool v104; // r9
  __int64 *v105; // rax
  __int64 *v106; // rdi
  VIDSCH_EXPORT *v107; // rdi
  unsigned __int64 v108; // rbx
  const struct _LUID *v109; // rax
  __int64 v110; // rdx
  unsigned int v111; // eax
  unsigned int v112; // eax
  __int64 v113; // rax
  _OWORD *v114; // rax
  __int64 AllocationSafe; // rax
  __int64 v116; // r9
  __int64 v117; // rdx
  _DWORD *v118; // rax
  _DWORD *v119; // rbx
  unsigned int v120; // edi
  enum _D3DDDI_HDR_METADATA_TYPE v121; // r15d
  struct DXGCONTEXT *v122; // rbx
  __int64 v123; // r13
  int v124; // ecx
  UINT64 v125; // rsi
  __int64 v126; // rdi
  unsigned int v127; // ebx
  __int64 v128; // rax
  __int64 v129; // rdx
  bool v130; // [rsp+20h] [rbp-3E8h]
  __int128 v131; // [rsp+80h] [rbp-388h] BYREF
  char v132; // [rsp+90h] [rbp-378h]
  enum _D3DDDI_HDR_METADATA_TYPE v133; // [rsp+94h] [rbp-374h] BYREF
  unsigned int v134; // [rsp+98h] [rbp-370h] BYREF
  int v135; // [rsp+9Ch] [rbp-36Ch]
  DXGADAPTER *v136; // [rsp+A0h] [rbp-368h]
  struct ADAPTER_DISPLAY *v137; // [rsp+A8h] [rbp-360h]
  struct CRefCountedBuffer *v138; // [rsp+B0h] [rbp-358h] BYREF
  _QWORD *v139; // [rsp+B8h] [rbp-350h] BYREF
  unsigned int v140; // [rsp+C0h] [rbp-348h] BYREF
  UINT v141; // [rsp+C4h] [rbp-344h]
  __int64 *v142; // [rsp+C8h] [rbp-340h]
  int v143; // [rsp+D0h] [rbp-338h]
  unsigned int v144; // [rsp+D4h] [rbp-334h] BYREF
  int v145; // [rsp+D8h] [rbp-330h]
  struct DXGCONTEXT *v146; // [rsp+E0h] [rbp-328h]
  bool v147[8]; // [rsp+E8h] [rbp-320h]
  __int64 v148; // [rsp+F0h] [rbp-318h]
  struct DXGK_PRESENT_PARAMS *v149; // [rsp+F8h] [rbp-310h]
  _BYTE *v150; // [rsp+100h] [rbp-308h]
  UINT64 *p_CompositionBindingId; // [rsp+108h] [rbp-300h]
  int v152; // [rsp+110h] [rbp-2F8h]
  int v153; // [rsp+114h] [rbp-2F4h]
  int v154; // [rsp+118h] [rbp-2F0h]
  int v155; // [rsp+11Ch] [rbp-2ECh]
  struct _D3DKMT_PRESENTHISTORYTOKEN *v156; // [rsp+120h] [rbp-2E8h]
  _QWORD *v157; // [rsp+128h] [rbp-2E0h]
  _QWORD *v158; // [rsp+130h] [rbp-2D8h]
  struct VIDSCH_SUBMIT_DATA_BASE *v159; // [rsp+138h] [rbp-2D0h]
  __int64 v160; // [rsp+140h] [rbp-2C8h]
  unsigned int *v161; // [rsp+148h] [rbp-2C0h]
  unsigned __int64 v162; // [rsp+150h] [rbp-2B8h]
  struct CRefCountedBuffer *v163; // [rsp+158h] [rbp-2B0h]
  int v164; // [rsp+160h] [rbp-2A8h] BYREF
  struct DXGCONTEXT *v165; // [rsp+168h] [rbp-2A0h]
  struct _D3DDDI_HDR_METADATA_HDR10 v166; // [rsp+170h] [rbp-298h] BYREF
  struct VIDSCH_SUBMIT_DATA_BASE *v167; // [rsp+190h] [rbp-278h]
  __int64 v168; // [rsp+198h] [rbp-270h]
  struct tagRECT v169; // [rsp+1A0h] [rbp-268h] BYREF
  __int64 v170; // [rsp+1B0h] [rbp-258h]
  struct VIDSCH_SUBMIT_DATA_BASE *v171; // [rsp+1B8h] [rbp-250h]
  PVOID v172; // [rsp+1C0h] [rbp-248h]
  _BYTE v173[32]; // [rsp+1C8h] [rbp-240h] BYREF
  UINT v174; // [rsp+1E8h] [rbp-220h]
  struct DXGPROCESS *v175; // [rsp+1F0h] [rbp-218h]
  DXGADAPTER **v176; // [rsp+1F8h] [rbp-210h]
  DXGADAPTER **v177; // [rsp+200h] [rbp-208h]
  __int64 v178; // [rsp+208h] [rbp-200h]
  struct VIDSCH_SUBMIT_DATA_BASE *v179; // [rsp+210h] [rbp-1F8h]
  struct _D3DKMT_PRESENTHISTORYTOKEN *v180; // [rsp+218h] [rbp-1F0h]
  unsigned __int64 v181; // [rsp+220h] [rbp-1E8h]
  _DXGKARG_PRESENT v182; // [rsp+230h] [rbp-1D8h] BYREF
  __int128 v183; // [rsp+2E0h] [rbp-128h] BYREF
  struct tagRECT v184; // [rsp+2F0h] [rbp-118h] BYREF
  _QWORD v185[5]; // [rsp+300h] [rbp-108h] BYREF
  int v186; // [rsp+328h] [rbp-E0h]
  PVOID P; // [rsp+330h] [rbp-D8h] BYREF
  _BYTE v188[128]; // [rsp+338h] [rbp-D0h] BYREF
  int v189; // [rsp+3B8h] [rbp-50h]

  v146 = a4;
  v7 = a3;
  v167 = a3;
  v149 = (struct DXGK_PRESENT_PARAMS *)a2;
  v156 = a1;
  v179 = a3;
  v10 = a5;
  v180 = a1;
  v181 = a2;
  v11 = a3;
  v171 = a3;
  v165 = a4;
  v163 = a6;
  v12 = 0;
  if ( !CIFlipPresentHistoryToken::IsIFlipSupported(a1) || a4 && !a2 )
    return 0;
  v131 = 0;
  if ( a1->Model == D3DKMT_PM_REDIRECTED_FLIP )
  {
    CIFlipPresentHistoryTokenRedirectedFlip::CIFlipPresentHistoryTokenRedirectedFlip(
      (CIFlipPresentHistoryTokenRedirectedFlip *)&v131,
      &a1->Token.Flip);
  }
  else if ( a1->Model == D3DKMT_PM_FLIPMANAGER )
  {
    CIFlipPresentHistoryTokenFlipManager::CIFlipPresentHistoryTokenFlipManager(
      (CIFlipPresentHistoryTokenFlipManager *)&v131,
      (const struct _D3DKMT_FLIPMANAGER_PRESENTHISTORYTOKEN *)&a1->Token);
  }
  if ( a4 )
  {
    p_CompositionBindingId = 0;
    v13 = *((_QWORD *)a4 + 2);
    v10 = *(struct _PRESENT_REDIRECTED_PARAMS **)(v13 + 16);
  }
  else
  {
    p_CompositionBindingId = *(UINT64 **)a5;
    v13 = *((_QWORD *)a5 + 3);
  }
  v157 = (_QWORD *)v13;
  v14 = *((_QWORD *)v10 + 2);
  v136 = (DXGADAPTER *)v14;
  v178 = v14;
  if ( !a4 && !*(_BYTE *)(v14 + 3169) )
    goto LABEL_51;
  *((_QWORD *)v7 + 3) = 0;
  Current = DXGPROCESS::GetCurrent();
  v175 = Current;
  v16 = *(DXGADAPTER ***)(v14 + 3240);
  v176 = v16;
  v17 = 0;
  if ( *(_QWORD *)(v14 + 3232) )
    v17 = *(struct ADAPTER_DISPLAY **)(v14 + 3232);
  v137 = v17;
  v162 = a2 & -(__int64)(a4 != 0);
  if ( a4 )
    v18 = *(_DWORD *)((a2 & -(__int64)(a4 != 0)) + 0x14);
  else
    v18 = *((_DWORD *)p_CompositionBindingId + 275);
  v133 = v18;
  DXGPROCESS::GetAllocationSafe(Current, &v139, (unsigned int)v18);
  v19 = v139;
  if ( !v139 || *(_QWORD *)(*(_QWORD *)(v139[1] + 16LL) + 16LL) != *(_QWORD *)(v157[2] + 16LL) )
  {
LABEL_50:
    DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v139);
LABEL_51:
    CIFlipPresentHistoryToken::~CIFlipPresentHistoryToken((CIFlipPresentHistoryToken *)&v131);
    return 0;
  }
  v177 = v16;
  if ( v163 )
  {
    v42 = v139[5];
    if ( v42 )
    {
      if ( (*(_DWORD *)(v42 + 4) & 1) != 0 )
        *((_QWORD *)v7 + 3) = *(_QWORD *)(*(_QWORD *)(v42 + 56) + 176LL);
    }
  }
  if ( a4 )
    v20 = *((_QWORD *)v149 + 187);
  else
    v20 = 0;
  v170 = v20;
  v160 = v20;
  v140 = (*(_DWORD *)(v19[6] + 4LL) >> 6) & 0xF;
  v152 = 0;
  v145 = 0;
  v153 = 0;
  v154 = 0;
  v134 = 0;
  v168 = *(_QWORD *)(*(__int64 (__fastcall **)(__int128 *))(v131 + 24))(&v131);
  v143 = 0;
  v183 = 0;
  v184 = 0;
  *(_QWORD *)v147 = (char *)v7 + (*((_BYTE *)v7 + 356) != 0 ? 0xF0 : 0) + 528;
  v21 = v16[92];
  p_CompositionBindingId = &v156->CompositionBindingId;
  CompositionBindingId = v156->CompositionBindingId;
  v23 = (*(__int64 (__fastcall **)(__int128 *))(v131 + 16))(&v131);
  v130 = v147[0];
  (*(void (__fastcall **)(DXGADAPTER *, unsigned int *, __int64, UINT64))(*((_QWORD *)v21 + 1) + 432LL))(
    v16[93],
    &v140,
    v23,
    CompositionBindingId);
  (*(void (__fastcall **)(__int128 *, __int64))(v131 + 32))(&v131, v168);
  (*(void (__fastcall **)(__int128 *, _QWORD))(v131 + 48))(&v131, v140);
  *((_DWORD *)v7 + 29) = v140;
  v24 = (struct _LUID *)(*(__int64 (__fastcall **)(__int128 *))(v131 + 16))(&v131);
  RtlCopyLuid((PLUID)((char *)v7 + 156), v24);
  *((_QWORD *)v7 + 21) = *p_CompositionBindingId;
  *(_DWORD *)v7 &= ~0x10000u;
  v25 = v146;
  if ( v146 )
  {
    v72 = v162;
    v73 = *(_DWORD *)v7 ^ (*(_DWORD *)(v162 + 88) ^ *(_DWORD *)v7) & 4;
    *(_DWORD *)v7 = v73;
    v74 = v73 ^ (v73 ^ (4 * *(_DWORD *)(v72 + 88))) & 0x80000;
    *(_DWORD *)v7 = v74;
    v75 = v74 ^ (v74 ^ (4 * *(_DWORD *)(v72 + 88))) & 0x100000;
    *(_DWORD *)v7 = v75;
    *(_DWORD *)v7 = v75 ^ (v75 ^ (4 * *(_DWORD *)(v72 + 88))) & 0x200000;
  }
  *(_DWORD *)v7 ^= ((unsigned __int8)*(_DWORD *)v7
                  ^ (unsigned __int8)(8 * (*(__int64 (__fastcall **)(__int128 *))(v131 + 200))(&v131)))
                 & 8;
  *(_DWORD *)v7 ^= ((unsigned __int8)*(_DWORD *)v7
                  ^ (unsigned __int8)(16 * (*(__int64 (__fastcall **)(__int128 *))(v131 + 208))(&v131)))
                 & 0x10;
  *(_DWORD *)v7 ^= (*(_DWORD *)v7
                  ^ ((*(unsigned __int8 (__fastcall **)(__int128 *))(v131 + 216))(&v131) << 28))
                 & 0x10000000;
  *((_DWORD *)v7 + 1) ^= ((unsigned __int8)*((_DWORD *)v7 + 1)
                        ^ (unsigned __int8)((*(unsigned __int8 (__fastcall **)(__int128 *))(v131 + 224))(&v131) << 6))
                       & 0x40;
  *((_DWORD *)v7 + 1) ^= ((unsigned __int16)*((_DWORD *)v7 + 1)
                        ^ (unsigned __int16)((*(unsigned __int8 (__fastcall **)(__int128 *))(v131 + 320))(&v131) << 8))
                       & 0x100;
  *((_DWORD *)v7 + 1) ^= ((unsigned __int16)*((_DWORD *)v7 + 1)
                        ^ (unsigned __int16)((*(unsigned __int8 (__fastcall **)(__int128 *))(v131 + 328))(&v131) << 9))
                       & 0x200;
  v26 = v136;
  (*(void (__fastcall **)(__int128 *, DXGADAPTER *))(v131 + 56))(&v131, v136);
  *((_DWORD *)v7 + 28) = (*(__int64 (__fastcall **)(__int128 *))(v131 + 64))(&v131);
  *((_DWORD *)v7 + 48) = *(_DWORD *)(*(__int64 (__fastcall **)(__int128 *))(v131 + 72))(&v131);
  *(_DWORD *)v7 ^= (*(_DWORD *)v7
                  ^ ((*(unsigned __int8 (__fastcall **)(__int128 *))(v131 + 192))(&v131) << 25))
                 & 0x2000000;
  *((_DWORD *)v7 + 36) = (*(__int64 (__fastcall **)(__int128 *))(v131 + 80))(&v131);
  *((_DWORD *)v7 + 37) = (*(__int64 (__fastcall **)(__int128 *))(v131 + 88))(&v131);
  if ( v25 )
    v27 = *((_DWORD *)v25 + 96);
  else
    v27 = 1;
  *((_DWORD *)v7 + 34) = v27;
  v28 = *((_BYTE *)v7 + 356);
  if ( v28 )
    v161 = (unsigned int *)((char *)v7 + 616);
  else
    v161 = 0;
  if ( v28 )
    *((_DWORD *)v7 + 162) = -1;
  if ( bTracingEnabled )
    *((_QWORD *)v7 + 23) = VIDMM_EXPORT::VidMmETWAllocationHandle(v16[95], v16[96], v133);
  v29 = (*(__int64 (__fastcall **)(__int128 *))(v131 + 96))(&v131);
  v138 = (struct VIDSCH_SUBMIT_DATA_BASE *)((char *)v7 + 124);
  *((_DWORD *)v7 + 31) = v29;
  v30 = (int *)((char *)v7 + 124);
  v164 = 1;
  if ( !v29
    && (!(*(unsigned __int8 (__fastcall **)(__int128 *))(v131 + 216))(&v131) || (*((_DWORD *)v26 + 643) & 0x40) == 0) )
  {
    v30 = &v164;
  }
  v31 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *))(*((_QWORD *)v16[92] + 1) + 536LL))(v157[100], v140, v30);
  v33 = v31;
  *((_DWORD *)v7 + 30) = v31;
  if ( v31 != 5 && *(_DWORD *)v138 )
  {
    v78 = (*(__int64 (__fastcall **)(__int128 *))(v131 + 64))(&v131);
    v79 = (*(__int64 (__fastcall **)(__int128 *))(v131 + 104))(&v131);
    WdLogSingleEntry4(8, v156, v79, v78, v33);
    WdLogGlobalForLineNumber = 2095;
    goto LABEL_59;
  }
  if ( !v152 )
  {
    if ( v153 )
    {
      v133 = D3DDDI_HDR_METADATA_TYPE_NONE;
      v138 = 0;
      v88 = v16[92];
      v89 = *((_QWORD *)v7 + 21);
      v90 = (const struct _LUID *)(*(__int64 (__fastcall **)(__int128 *))(v131 + 16))(&v131);
      VIDSCH_EXPORT::VidSchExitIndependentFlip(
        v88,
        v16[93],
        1 << *((_DWORD *)v7 + 29),
        v90,
        v89,
        &v134,
        0,
        0,
        (int *)&v133,
        (unsigned __int64 *)&v138);
      ADAPTER_DISPLAY::UpdateIndependentFlipState(v137, *((_DWORD *)v7 + 29), v134, 0);
    }
    else if ( !v154 )
    {
LABEL_59:
      DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v139);
      (*(void (__fastcall **)(__int128 *, __int64))v131)(&v131, 1);
      return 0;
    }
    LOBYTE(v32) = 1;
    (*(void (__fastcall **)(__int128 *, __int64))(v131 + 232))(&v131, v32);
    goto LABEL_59;
  }
  *((_QWORD *)v7 + 22) = *(_QWORD *)(*(__int64 (__fastcall **)(__int128 *))(v131 + 24))(&v131);
  if ( !(*(unsigned __int8 (__fastcall **)(__int128 *))(v131 + 240))(&v131) )
  {
    v133 = D3DDDI_HDR_METADATA_TYPE_NONE;
    v138 = 0;
    v91 = v16[92];
    v92 = *((_QWORD *)v7 + 21);
    v93 = (const struct _LUID *)(*(__int64 (__fastcall **)(__int128 *))(v131 + 16))(&v131);
    VIDSCH_EXPORT::VidSchExitIndependentFlip(
      v91,
      v16[93],
      1 << *((_DWORD *)v7 + 29),
      v93,
      v92,
      &v134,
      0,
      0,
      (int *)&v133,
      (unsigned __int64 *)&v138);
    LOBYTE(v94) = 1;
    (*(void (__fastcall **)(__int128 *, __int64))(v131 + 232))(&v131, v94);
    ADAPTER_DISPLAY::UpdateIndependentFlipState(v137, *((_DWORD *)v7 + 29), v134, 0);
    WdLogSingleEntry0(8);
    WdLogGlobalForLineNumber = 2164;
    goto LABEL_50;
  }
  if ( v145 || DXGADAPTER::SupportCheckMultiPlaneOverlaySupport3(v16[2]) )
  {
    v34 = (*(__int64 (__fastcall **)(__int128 *))(v131 + 248))(&v131);
    v35 = v137;
    if ( !v34 )
    {
      ADAPTER_DISPLAY::UpdateIndependentFlipState(v137, *((_DWORD *)v7 + 29), v134, 1u);
LABEL_34:
      *(_DWORD *)v7 = *(_DWORD *)v7 & 0x7BFFFFFF | ((v145 & 1 | (32 * v143)) << 26);
      *(_OWORD *)((char *)v7 + 436) = v183;
      *(struct tagRECT *)((char *)v7 + 452) = v184;
      goto LABEL_35;
    }
    DXGDISPLAYSTATEMUTEX::DXGDISPLAYSTATEMUTEX((DXGDISPLAYSTATEMUTEX *)&v166, v137);
    DXGAUTOMUTEX::Acquire((DXGAUTOMUTEX *)&v166);
    PostCompositionStretching = ADAPTER_DISPLAY::GetPostCompositionStretching(v35, *((_DWORD *)v7 + 29));
    v132 = PostCompositionStretching;
    if ( PostCompositionStretching )
    {
      if ( IsYUVAllocation(*(void **)(v139[6] + 16LL), (struct ADAPTER_RENDER *)v16)
        || DISPLAY_SOURCE::GetEnabledPlaneCountUnsafe((DISPLAY_SOURCE *)(*((_QWORD *)v35 + 16)
                                                                       + 4024LL * *((unsigned int *)v7 + 29))) > 1 )
      {
        PostCompositionStretching = 0;
        v132 = 0;
      }
      else
      {
        PostCompositionStretching = v132;
      }
    }
    v169 = 0;
    if ( v134 || (v104 = 1, !PostCompositionStretching) )
      v104 = 0;
    if ( CheckAndUpdateMultiPlaneOverlayFromInternalState(
           *((_DWORD *)v7 + 29),
           v134,
           (struct CIFlipPresentHistoryTokenData *)&v131,
           v104,
           (struct ADAPTER_RENDER *)v16,
           v35,
           &v169) )
    {
      v105 = (__int64 *)(*(__int64 (__fastcall **)(__int128 *))(v131 + 8))(&v131);
      v142 = v105;
      v106 = *(__int64 **)v147;
      **(_WORD **)v147 = *(_WORD *)v105;
      *((_WORD *)v106 + 2) = *((_WORD *)v105 + 2);
      *((_WORD *)v106 + 1) = *((_WORD *)v105 + 4);
      *((_WORD *)v106 + 3) = *((_WORD *)v105 + 6);
      *((_DWORD *)v106 + 6) = (*(__int64 (__fastcall **)(__int128 *))(v131 + 112))(&v131);
      if ( v132 )
      {
        v81 = *v106;
        v106[1] = *v106;
        v106[2] = v81;
        v82 = *(_OWORD *)v142;
        v183 = v82;
        v184 = v169;
        if ( (_DWORD)v82 != v169.left
          || __PAIR64__(DWORD2(v183), DWORD1(v82)) != *(_QWORD *)&v169.top
          || (v80 = 0, HIDWORD(v183) != v169.bottom) )
        {
          v80 = 1;
        }
        v143 = v80;
        if ( !(_DWORD)v80 )
        {
          v183 = 0;
          v184 = 0;
        }
        (*(void (__fastcall **)(DXGADAPTER *, _QWORD, __int64, __int128 *, struct tagRECT *))(*((_QWORD *)v16[92] + 1)
                                                                                            + 1008LL))(
          v16[93],
          *((unsigned int *)v7 + 29),
          v80,
          &v183,
          &v184);
        UpdatePostComposition(*((_DWORD *)v7 + 29), v143 != 0, DWORD2(v183) - v183, HIDWORD(v183) - DWORD1(v183), v35);
      }
      (*(void (__fastcall **)(DXGADAPTER *, _QWORD, __int64 *, _QWORD))(*((_QWORD *)v16[92] + 1) + 440LL))(
        v16[93],
        *((unsigned int *)v7 + 29),
        v106,
        v134);
      DXGAUTOMUTEX::Release((DXGAUTOMUTEX *)&v166);
      DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)&v166);
      goto LABEL_34;
    }
    DXGAUTOMUTEX::Release((DXGAUTOMUTEX *)&v166);
    v133 = D3DDDI_HDR_METADATA_TYPE_NONE;
    v138 = 0;
    v107 = v16[92];
    v108 = *((_QWORD *)v7 + 21);
    v109 = (const struct _LUID *)(*(__int64 (__fastcall **)(__int128 *))(v131 + 16))(&v131);
    VIDSCH_EXPORT::VidSchExitIndependentFlip(
      v107,
      v16[93],
      1 << *((_DWORD *)v7 + 29),
      v109,
      v108,
      &v134,
      0,
      0,
      (int *)&v133,
      (unsigned __int64 *)&v138);
    WdLogSingleEntry1(3);
    WdLogGlobalForLineNumber = 2274;
    LOBYTE(v110) = 1;
    (*(void (__fastcall **)(__int128 *, __int64))(v131 + 232))(&v131, v110);
    ADAPTER_DISPLAY::UpdateIndependentFlipState(v137, *((_DWORD *)v7 + 29), v134, 0);
    DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)&v166);
    goto LABEL_50;
  }
  v95 = (_DWORD *)(*(__int64 (__fastcall **)(__int128 *))(v131 + 8))(&v131);
  *(_QWORD *)v147 = v95;
  if ( v95[2] - *v95 != (*(unsigned int (__fastcall **)(__int128 *))(v131 + 120))(&v131)
    || (v96 = v95[3] - v95[1], v96 != (*(unsigned int (__fastcall **)(__int128 *))(v131 + 128))(&v131))
    || (*(unsigned __int8 (__fastcall **)(__int128 *))(v131 + 248))(&v131) )
  {
    v133 = D3DDDI_HDR_METADATA_TYPE_NONE;
    v138 = 0;
    v97 = v16[92];
    v98 = *((_QWORD *)v7 + 21);
    v99 = (const struct _LUID *)(*(__int64 (__fastcall **)(__int128 *))(v131 + 16))(&v131);
    VIDSCH_EXPORT::VidSchExitIndependentFlip(
      v97,
      v16[93],
      1 << *((_DWORD *)v7 + 29),
      v99,
      v98,
      &v134,
      0,
      0,
      (int *)&v133,
      (unsigned __int64 *)&v138);
    v100 = (*(unsigned int (__fastcall **)(__int128 *))(v131 + 128))(&v131);
    v101 = (*(__int64 (__fastcall **)(__int128 *))(v131 + 120))(&v131);
    WdLogSingleEntry4(
      8,
      *(_DWORD *)(*(_QWORD *)v147 + 8LL) - **(_DWORD **)v147,
      *(_DWORD *)(*(_QWORD *)v147 + 12LL) - *(_DWORD *)(*(_QWORD *)v147 + 4LL),
      v101,
      v100);
    WdLogGlobalForLineNumber = 2327;
    LOBYTE(v102) = 1;
    (*(void (__fastcall **)(__int128 *, __int64))(v131 + 232))(&v131, v102);
    ADAPTER_DISPLAY::UpdateIndependentFlipState(v137, *((_DWORD *)v7 + 29), 0, 0);
LABEL_149:
    DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v139);
    CIFlipPresentHistoryToken::~CIFlipPresentHistoryToken((CIFlipPresentHistoryToken *)&v131);
    return v12;
  }
  v35 = v137;
  ADAPTER_DISPLAY::UpdateIndependentFlipState(v137, *((_DWORD *)v7 + 29), 0, 1u);
LABEL_35:
  if ( v35 && (*((_DWORD *)v35 + 6) & 0x10) != 0 )
  {
    if ( !ADAPTER_DISPLAY::IsHdrEnabled(v35, v140) )
    {
      *((_DWORD *)v7 + 90) = 0;
LABEL_39:
      *(_DWORD *)v7 |= 0x40000000u;
      goto LABEL_40;
    }
    *(_DWORD *)v7 ^= (*(_DWORD *)v7
                    ^ ((*(unsigned __int8 (__fastcall **)(__int128 *))(v131 + 256))(&v131) << 30))
                   & 0x40000000;
    v111 = (*(__int64 (__fastcall **)(__int128 *))(v131 + 136))(&v131);
    *((_DWORD *)v7 + 90) = v111;
    if ( (*(_DWORD *)v7 & 0x40000000) != 0 )
    {
      if ( v111 )
      {
        v112 = v111 - 1;
        if ( v112 )
        {
          if ( v112 == 1 )
          {
            v113 = (*(__int64 (__fastcall **)(__int128 *))(v131 + 152))(&v131);
            *(_OWORD *)((char *)v7 + 364) = *(_OWORD *)v113;
            *(_OWORD *)((char *)v7 + 380) = *(_OWORD *)(v113 + 16);
            *(_OWORD *)((char *)v7 + 396) = *(_OWORD *)(v113 + 32);
            *(_OWORD *)((char *)v7 + 412) = *(_OWORD *)(v113 + 48);
            *(_QWORD *)((char *)v7 + 428) = *(_QWORD *)(v113 + 64);
          }
          else
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 2369;
            DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"FALSE", 2369, 0, 0, 0, 0);
            *(_DWORD *)v7 &= ~0x40000000u;
          }
        }
        else
        {
          v114 = (_OWORD *)(*(__int64 (__fastcall **)(__int128 *))(v131 + 144))(&v131);
          *(_OWORD *)((char *)v7 + 364) = *v114;
          *(_OWORD *)((char *)v7 + 376) = *(_OWORD *)((char *)v114 + 12);
        }
      }
    }
    else
    {
      if ( v111 > 2 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 2377;
        DxgkLogInternalTriageEvent(
          0,
          262146,
          -1,
          (unsigned int)L"D3DDDI_HDR_METADATA_TYPE_HDR10 == pVidSchSubmitData->HDRMetaDataType || D3DDDI_HDR_METADATA_TYPE"
                         "_HDR10PLUS == pVidSchSubmitData->HDRMetaDataType || D3DDDI_HDR_METADATA_TYPE_NONE == pVidSchSub"
                         "mitData->HDRMetaDataType",
          2377,
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
      v133 = D3DDDI_HDR_METADATA_TYPE_NONE;
      memset(&v166, 0, sizeof(v166));
      if ( !(unsigned int)PopulateHDRMetadataFromDisplay(*((_DWORD *)v7 + 29), v35, &v166, &v133) )
      {
        *(_OWORD *)((char *)v7 + 364) = *(_OWORD *)v166.RedPrimary;
        *(_OWORD *)((char *)v7 + 376) = *(_OWORD *)v166.WhitePoint;
        *((_DWORD *)v7 + 90) = v133;
        goto LABEL_39;
      }
    }
  }
LABEL_40:
  (*(void (__fastcall **)(__int128 *, _QWORD))(v131 + 160))(&v131, v134);
  v36 = (_DWORD *)((char *)v7 + 600);
  if ( !*((_BYTE *)v7 + 356) )
    v36 = (_DWORD *)((char *)v7 + 496);
  *v36 ^= ((unsigned __int16)*v36 ^ (unsigned __int16)(1 << v134)) & 0x3FF;
  v37 = 1;
  LODWORD(v137) = 1;
  IsDxgmms2 = DXGADAPTER::IsDxgmms2(v136);
  v39 = v146;
  if ( IsDxgmms2 && v146 )
  {
    v37 = *(_DWORD *)(v162 + 92) + 1;
    LODWORD(v137) = v37;
  }
  Pool2 = 0;
  v150 = 0;
  v172 = 0;
  v174 = 0;
  if ( v37 <= 4 )
  {
    Pool2 = v173;
    v150 = v173;
    v172 = v173;
    if ( !v37 )
    {
LABEL_47:
      v174 = v37;
      goto LABEL_48;
    }
    memset(v173, 0, 8LL * v37);
    Pool2 = v172;
LABEL_46:
    v150 = Pool2;
    goto LABEL_47;
  }
  if ( 0xFFFFFFFFFFFFFFFFuLL / v37 >= 8 )
  {
    Pool2 = (_BYTE *)ExAllocatePool2(256, 8LL * v37, 1265072196);
    v172 = Pool2;
    goto LABEL_46;
  }
LABEL_48:
  *(_QWORD *)v166.RedPrimary = Pool2;
  if ( !Pool2 )
  {
    v172 = 0;
    v174 = 0;
    DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v139);
    (*(void (__fastcall **)(__int128 *, __int64))v131)(&v131, 1);
    return 3221225495LL;
  }
  v185[0] = 0;
  v186 = 0;
  PagedPoolArray<DXGALLOCATIONREFERENCE,4>::AllocateElements(v185, v37);
  *(_QWORD *)v147 = v185[0];
  if ( !v185[0] )
  {
    PagedPoolArray<DXGALLOCATIONREFERENCE,4>::~PagedPoolArray<DXGALLOCATIONREFERENCE,4>(v185);
    if ( v172 != v173 && v172 )
      ExFreePoolWithTag(v172, 0);
    v172 = 0;
    v174 = 0;
    v12 = -1073741801;
    goto LABEL_149;
  }
  v43 = v7;
  v159 = v7;
  v44 = 0;
  v135 = 0;
  v133 = D3DDDI_HDR_METADATA_TYPE_NONE;
  v45 = 0;
  while ( 1 )
  {
    v141 = v45;
    if ( v45 >= v37 )
      goto LABEL_80;
    if ( !v45 )
    {
      v158 = v139;
      if ( *((_BYTE *)v7 + 356) )
        v46 = (_QWORD *)((char *)v7 + (unsigned int)(8 * *((_DWORD *)v7 + 151) * (*((_DWORD *)v7 + 152) + 28)) + 632);
      else
        v46 = (_QWORD *)((char *)v43 + 512);
      *v46 = *(_QWORD *)(v139[6] + 16LL);
      v47 = v136;
      if ( !*((_BYTE *)v136 + 3169) )
      {
        if ( *((_BYTE *)v7 + 356) )
        {
          v83 = (_QWORD *)((char *)v7 + (unsigned int)(8 * *((_DWORD *)v7 + 151) * (*((_DWORD *)v7 + 152) + 28)) + 624);
          v47 = v136;
        }
        else
        {
          v83 = (_QWORD *)((char *)v7 + 568);
        }
        *v83 = *((_QWORD *)v39 + 23);
      }
      if ( DXGADAPTER::IsDxgmms2(v47) && v39 && (*((_DWORD *)v39 + 98) & 0x10) == 0 )
        *(_QWORD *)((char *)v7 + *((unsigned int *)v7 + 138)) = *((_QWORD *)v39 + 32);
      v148 = 0;
      goto LABEL_69;
    }
    v148 = v45;
    v135 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v149 + 187) + 8LL * v45) + 388LL);
    v144 = 0;
    RtlCopyFromUser(&v144, (void *)(*(_QWORD *)(v162 + 1456) + 4LL * (v45 - 1)), 4u);
    v142 = (__int64 *)(*(_QWORD *)v147 + 8 * v148);
    AllocationSafe = DXGPROCESS::GetAllocationSafe(v175, &v169, v144);
    DXGALLOCATIONREFERENCE::MoveAssign(v142, AllocationSafe);
    DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v169);
    v49 = (_QWORD *)*v142;
    v158 = v49;
    if ( !v49 )
      break;
    v87 = v149;
    v116 = 8 * v148;
    if ( *(_QWORD *)(*(_QWORD *)(v49[1] + 16LL) + 16LL) != *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v149 + 187) + 8 * v148)
                                                                                             + 16LL)
                                                                                 + 16LL)
                                                                     + 16LL) )
    {
      _mm_lfence();
      WdLogSingleEntry3(2, *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v149 + 187) + 8 * v148) + 16LL), v49, -1073741811);
      WdLogGlobalForLineNumber = 2499;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Device 0x%p does not match allocation 0x%p owner, returning 0x%I64x",
        *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v149 + 187) + 8 * v148) + 16LL),
        *v142,
        -1073741811,
        0,
        0);
      v44 = -1073741811;
      v135 = -1073741811;
      v155 = -1073741811;
      v58 = v136;
      goto LABEL_81;
    }
    v48 = v141;
    if ( *((_BYTE *)v7 + 356) )
      v84 = (_QWORD *)((char *)v7
                     + 64 * (unsigned __int64)(v141 * *((_DWORD *)v7 + 151))
                     + (unsigned int)(8 * *((_DWORD *)v7 + 151) * (*((_DWORD *)v7 + 152) + 28))
                     + 632);
    else
      v84 = (_QWORD *)((char *)v159 + 512);
    *v84 = *(_QWORD *)(v49[6] + 16LL);
    if ( !*((_BYTE *)v136 + 3169) )
    {
      v85 = *(__int64 **)(*(_QWORD *)(v116 + *((_QWORD *)v87 + 187)) + 184LL);
      v142 = v85;
      if ( *((_BYTE *)v7 + 356) )
      {
        v86 = (__int64 **)((char *)v7
                         + 64 * (unsigned __int64)(v48 * *((_DWORD *)v7 + 151))
                         + *((_DWORD *)v7 + 151) * ((8 * *((_DWORD *)v7 + 152) + 231) & 0xFFFFFFF8)
                         + 624);
        v87 = v149;
        v85 = v142;
      }
      else
      {
        v86 = (__int64 **)((char *)v7 + 568);
      }
      *v86 = v85;
    }
    *((_DWORD *)v7 + 34) |= 1 << v135;
    v117 = *(_QWORD *)(v116 + *((_QWORD *)v87 + 187));
    if ( (*(_DWORD *)(v117 + 392) & 0x10) == 0 )
      *(_QWORD *)((char *)v7 + v116 + *((unsigned int *)v7 + 138)) = *(_QWORD *)(v117 + 256);
LABEL_69:
    if ( *((_BYTE *)v7 + 356) )
      v50 = (unsigned __int64)v7
          + 64 * (unsigned __int64)(v48 * *((_DWORD *)v7 + 151))
          + (unsigned int)(8 * *((_DWORD *)v7 + 151) * (*((_DWORD *)v7 + 152) + 28))
          + 656;
    else
      v50 = (unsigned __int64)v7 + 504;
    v142 = (__int64 *)v50;
    v135 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64, DXGADAPTER *, unsigned int *))(*((_QWORD *)v16[95] + 1) + 400LL))(
             v157[99],
             v49[3],
             v50,
             v16[96],
             v161);
    if ( v135 < 0 )
    {
      WdLogSingleEntry2(2, v158);
      WdLogGlobalForLineNumber = 2548;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Failed to reference allocation for submission (0x%I64x). Returning 0x%I64x",
        (__int64)v158,
        -1073741811,
        0,
        0,
        0);
      v44 = v135;
LABEL_80:
      v58 = v136;
      goto LABEL_81;
    }
    *(_QWORD *)&v150[8 * v148] = *v142;
    ++v133;
    v51 = v158[5];
    if ( v51 )
      v52 = (*(_DWORD *)(v51 + 4) & 8) != 0;
    else
      v52 = 0;
    if ( v52 )
      v53 = *(_QWORD *)(*(_QWORD *)(v51 + 56) + 184LL);
    else
      v53 = 0;
    if ( *((_BYTE *)v7 + 356) )
      *(_QWORD *)((char *)v7
                + 64 * v141 * *((_DWORD *)v7 + 151)
                + *((_DWORD *)v7 + 151) * ((8 * *((_DWORD *)v7 + 152) + 231) & 0xFFFFFFF8)
                + 664) = v53;
    else
      *((_QWORD *)v7 + 72) = v53;
    *(_DWORD *)v7 |= 0x1000000u;
    v54 = *p_CompositionBindingId;
    v55 = *(_QWORD *)(*(__int64 (__fastcall **)(__int128 *))(v131 + 16))(&v131);
    v56 = (*(__int64 (__fastcall **)(__int128 *))(v131 + 64))(&v131);
    v57 = (*(__int64 (__fastcall **)(__int128 *))(v131 + 104))(&v131);
    WdLogSingleEntry5(8, v156, v57, v56, v55, v54);
    WdLogGlobalForLineNumber = 2571;
    if ( (*(unsigned __int8 (__fastcall **)(__int128 *))(v131 + 344))(&v131) )
    {
      *((_DWORD *)v7 + 1) |= 2u;
      *((_QWORD *)v7 + 60) = (*(__int64 (__fastcall **)(__int128 *))(v131 + 352))(&v131);
      v118 = (_DWORD *)(*(__int64 (__fastcall **)(__int128 *))(v131 + 360))(&v131);
      v119 = v118;
      *((_QWORD *)v7 + 61) = v118;
      if ( v118 )
      {
        if ( !v118[1] )
        {
          if ( *v118 != 64 )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 2585;
            DxgkLogInternalTriageEvent(
              0,
              262146,
              -1,
              (unsigned int)L"pAuxiliaryPresentInfo->size == sizeof(D3DKMT_FLIPMANAGER_AUXILIARYPRESENTINFO)",
              2585,
              0,
              0,
              0,
              0);
          }
          v119[8] = *((_DWORD *)v7 + 29);
          *((_QWORD *)v119 + 3) = *(_QWORD *)((char *)v136 + 412);
        }
      }
    }
    v45 = v141 + 1;
    v16 = v176;
    v37 = (unsigned int)v137;
    v39 = v146;
    v44 = v135;
    v43 = v159;
  }
  WdLogSingleEntry2(2, v144);
  WdLogGlobalForLineNumber = 2490;
  DxgkLogInternalTriageEvent(
    0,
    0x40000,
    -1,
    (unsigned int)L"Invalid allocation handle in present: 0x%I64x. Returning 0x%I64x",
    v144,
    -1073741811,
    0,
    0,
    0);
  v44 = -1073741811;
  v135 = -1073741811;
  v155 = -1073741811;
  v58 = v136;
LABEL_81:
  *((_DWORD *)v11 + 35) = v37;
  if ( v44 < 0 || (*((_DWORD *)v58 + 643) & 0x20) == 0 )
  {
    v59 = v136;
    goto LABEL_83;
  }
  memset(&v182, 0, sizeof(v182));
  v182.Flags.Value = 0x2000;
  if ( v163 )
  {
    v182.PrivateDriverDataSize = *((_DWORD *)v163 + 2);
    v182.pPrivateDriverData = (char *)v163 + 16;
  }
  P = 0;
  v189 = 0;
  PagedPoolZeroedArray<_DXGK_PRESENTALLOCATIONINFO,4>::AllocateElements(&P, v37);
  v182.pAllocationList = (DXGK_ALLOCATIONLIST *)P;
  if ( !P )
  {
LABEL_166:
    P = 0;
    v189 = 0;
    goto LABEL_84;
  }
  v61 = *((_DWORD *)v136 + 645);
  if ( (v61 & 0x80u) == 0 || (v132 = 1, (v61 & 0x40) != 0) )
    v132 = 0;
  v62 = 0;
  LODWORD(v137) = 0;
  if ( v37 )
  {
    v63 = v149;
    v64 = v132;
    do
    {
      v65 = 8LL * v62;
      if ( v39 )
        v66 = *(_WORD *)(*(_QWORD *)(v65 + *((_QWORD *)v63 + 187)) + 388LL);
      else
        v66 = 0;
      v67 = 32LL * v62;
      v165 = (struct DXGCONTEXT *)v67;
      *(_WORD *)((char *)&v182.pAllocationList[1].hDeviceSpecificAllocation + v67 + 2) = v66;
      if ( v62 )
        v68 = *(_QWORD **)(v65 + *(_QWORD *)v147);
      else
        v68 = v139;
      if ( v39 )
        v64 = *(_BYTE *)(*(_QWORD *)(v65 + *((_QWORD *)v63 + 187)) + 431LL);
      *((_QWORD *)&v182.pAllocationList->hDeviceSpecificAllocation + 4 * v62) = v68[4];
      pAllocationList = v182.pAllocationList;
      AllocationGpuVirtualAddress = VIDMM_EXPORT::VidMmGetAllocationGpuVirtualAddress(
                                      v16[95],
                                      (const struct VIDMM_MULTI_ALLOC *)v68[3],
                                      v64 != 0,
                                      *(unsigned __int16 *)((char *)&v182.pAllocationList[1].hDeviceSpecificAllocation
                                                          + v67
                                                          + 2));
      *(_QWORD *)((char *)v165 + (_QWORD)pAllocationList + 8) = AllocationGpuVirtualAddress;
      v62 = (_DWORD)v137 + 1;
      LODWORD(v137) = v62;
      v39 = v146;
    }
    while ( v62 < v37 );
    v11 = v171;
    v7 = v167;
  }
  v182.FlipInterval = *(_DWORD *)v138;
  v182.Flags.Value = v182.Flags.Value & 0xFFFFE8FF | (*(_DWORD *)v159 >> 11) & 0x1700;
  v182.NumSrcAllocations = v37;
  v59 = v136;
  v71 = 0;
  if ( !*((_BYTE *)v136 + 3169) )
    v71 = (void *)*((_QWORD *)v39 + 23);
  v135 = ADAPTER_RENDER::DdiPresent((ADAPTER_RENDER *)v16, v71, &v182);
  v58 = (const struct DXGADAPTER *)P;
  if ( v135 < 0 )
  {
    if ( P != v188 && P )
      ExFreePoolWithTag(P, 0);
    goto LABEL_166;
  }
  if ( P != v188 && P )
    ExFreePoolWithTag(P, 0);
  P = 0;
  v189 = 0;
LABEL_83:
  if ( v145 && (*(_DWORD *)v7 & 0x1000000) != 0 )
  {
    v138 = 0;
    if ( *((int *)v59 + 779) < 2500
      || (v76 = ReadPresentDirtyRectsData(v58, v134, (const struct CIFlipPresentHistoryTokenData *)&v131, &v138),
          v76 >= 0) )
    {
      *((_QWORD *)v11 + 4) = v138;
    }
    else
    {
      v77 = v76;
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 2672;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Failed to read dirty rects data. Returning 0x%I64x",
        v77,
        0,
        0,
        0,
        0);
    }
  }
LABEL_84:
  v60 = v135;
  if ( v135 < 0 )
  {
    v120 = 0;
    v121 = v133;
    if ( v133 )
    {
      v122 = v146;
      v123 = v160;
      do
      {
        if ( v122 )
          v124 = *(_DWORD *)(*(_QWORD *)(8LL * v120 + v123) + 388LL);
        else
          LOBYTE(v124) = 0;
        VIDMM_EXPORT::VidMmUnreferencePrimaryAllocation(
          v16[95],
          v16[96],
          1 << v124,
          *(struct VIDMM_ALLOC **)&v150[8 * v120++],
          v130,
          v161);
      }
      while ( v120 < v121 );
    }
    v125 = *p_CompositionBindingId;
    v126 = *(_QWORD *)(*(__int64 (__fastcall **)(__int128 *))(v131 + 16))(&v131);
    v127 = (*(__int64 (__fastcall **)(__int128 *))(v131 + 64))(&v131);
    v128 = (*(__int64 (__fastcall **)(__int128 *))(v131 + 104))(&v131);
    WdLogSingleEntry5(8, v156, v128, v127, v126, v125);
    WdLogGlobalForLineNumber = 2700;
    LOBYTE(v129) = 1;
    (*(void (__fastcall **)(__int128 *, __int64))(v131 + 232))(&v131, v129);
    *(_DWORD *)v159 &= ~0x1000000u;
    v60 = 0;
  }
  PagedPoolArray<DXGALLOCATIONREFERENCE,4>::~PagedPoolArray<DXGALLOCATIONREFERENCE,4>(v185);
  if ( v172 != v173 && v172 )
    ExFreePoolWithTag(v172, 0);
  v172 = 0;
  v174 = 0;
  DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v139);
  (*(void (__fastcall **)(__int128 *, __int64))v131)(&v131, 1);
  return v60;
}

```

## disassembly

```asm
0x140389e1c  push    rbx
0x140389e1e  push    rsi
0x140389e1f  push    rdi
0x140389e20  push    r12
0x140389e22  push    r13
0x140389e24  push    r14
0x140389e26  push    r15
0x140389e28  sub     rsp, 3D0h
0x140389e2f  mov     rax, cs:__security_cookie
0x140389e36  xor     rax, rsp
0x140389e39  mov     [rsp+408h+var_48], rax
0x140389e41  mov     rbx, r9
0x140389e44  mov     [rsp+408h+var_328], rbx
0x140389e4c  mov     r13, r8
0x140389e4f  mov     [rsp+408h+var_278], r8
0x140389e57  mov     r12, rdx
0x140389e5a  mov     [rsp+408h+var_310], rdx
0x140389e62  mov     rsi, rcx
0x140389e65  mov     [rsp+408h+var_2E8], rcx
0x140389e6d  mov     [rsp+408h+var_1F8], r8
0x140389e75  mov     rdi, [rsp+408h+arg_20]
0x140389e7d  mov     [rsp+408h+var_1F0], rcx
0x140389e85  mov     [rsp+408h+var_1E8], rdx
0x140389e8d  mov     r15, r8
0x140389e90  mov     [rsp+408h+var_250], r8
0x140389e98  mov     [rsp+408h+var_2A0], rbx
0x140389ea0  mov     rax, [rsp+408h+arg_28]
0x140389ea8  mov     [rsp+408h+var_2B0], rax
0x140389eb0  call    ?IsIFlipSupported@CIFlipPresentHistoryToken@@SA_NPEBU_D3DKMT_PRESENTHISTORYTOKEN@@@Z; CIFlipPresentHistoryToken::IsIFlipSupported(_D3DKMT_PRESENTHISTORYTOKEN const *)
0x140389eb5  xor     r14d, r14d
0x140389eb8  test    al, al
0x140389eba  jz      loc_14038A790
0x140389ec0  test    rbx, rbx
0x140389ec3  jnz     loc_14038AE5A
0x140389ec9  xorps   xmm0, xmm0
0x140389ecc  movups  [rsp+408h+var_388], xmm0
0x140389ed4  mov     eax, [rsi]
0x140389ed6  cmp     eax, 2
0x140389ed9  jnz     loc_14038AE18
0x140389edf  lea     rdx, [rsi+10h]; struct _D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN *
0x140389ee3  lea     rcx, [rsp+408h+var_388]; this
0x140389eeb  call    ??0CIFlipPresentHistoryTokenRedirectedFlip@@QEAA@PEBU_D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN@@@Z; CIFlipPresentHistoryTokenRedirectedFlip::CIFlipPresentHistoryTokenRedirectedFlip(_D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN const *)
0x140389ef0  test    rbx, rbx
0x140389ef3  jz      loc_14038B3F6
0x140389ef9  mov     [rsp+408h+var_300], r14
0x140389f01  mov     rax, [rbx+10h]
0x140389f05  mov     rdi, [rax+10h]
0x140389f09  mov     [rsp+408h+var_2E0], rax
0x140389f11  mov     rdi, [rdi+10h]
0x140389f15  mov     [rsp+408h+var_368], rdi
0x140389f1d  mov     [rsp+408h+var_200], rdi
0x140389f25  test    rbx, rbx
0x140389f28  jz      loc_14038B40A
0x140389f2e  mov     [r13+18h], r14
0x140389f32  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x140389f37  mov     r9, rax
0x140389f3a  mov     [rsp+408h+var_218], rax
0x140389f42  mov     rsi, [rdi+0CA8h]
0x140389f49  mov     [rsp+408h+var_210], rsi
0x140389f51  mov     rcx, [rdi+0CA0h]
0x140389f58  mov     rax, r14
0x140389f5b  test    rcx, rcx
0x140389f5e  cmovnz  rax, rcx
0x140389f62  mov     [rsp+408h+var_360], rax
0x140389f6a  mov     rcx, rbx
0x140389f6d  neg     rcx
0x140389f70  sbb     rax, rax
0x140389f73  and     rax, r12
0x140389f76  mov     [rsp+408h+var_2B8], rax
0x140389f7e  test    rbx, rbx
0x140389f81  jz      loc_14038B41C
0x140389f87  mov     eax, [rax+14h]
0x140389f8a  mov     [rsp+408h+var_374], eax
0x140389f91  mov     r8d, eax
0x140389f94  lea     rdx, [rsp+408h+var_350]
0x140389f9c  mov     rcx, r9
0x140389f9f  call    ?GetAllocationSafe@DXGPROCESS@@QEAA?AVDXGALLOCATIONREFERENCE@@I@Z; DXGPROCESS::GetAllocationSafe(uint)
0x140389fa4  mov     rax, [rsp+408h+var_350]
0x140389fac  test    rax, rax
0x140389faf  jz      loc_14038A776
0x140389fb5  mov     rcx, [rax+8]
0x140389fb9  mov     r8, [rcx+10h]
0x140389fbd  mov     rcx, [rsp+408h+var_2E0]
0x140389fc5  mov     rcx, [rcx+10h]
0x140389fc9  mov     rdx, [rcx+10h]
0x140389fcd  cmp     [r8+10h], rdx
0x140389fd1  jnz     loc_14038A776
0x140389fd7  mov     [rsp+408h+var_208], rsi
0x140389fdf  cmp     [rsp+408h+var_2B0], r14
0x140389fe7  jnz     loc_14038A7A5
0x140389fed  mov     r12d, 1
0x140389ff3  test    rbx, rbx
0x140389ff6  jz      loc_14038B42F
0x140389ffc  mov     rcx, [rsp+408h+var_310]
0x14038a004  mov     rcx, [rcx+5D8h]
0x14038a00b  mov     [rsp+408h+var_258], rcx
0x14038a013  mov     [rsp+408h+var_2C8], rcx
0x14038a01b  mov     rcx, [rax+30h]
0x14038a01f  mov     eax, [rcx+4]
0x14038a022  shr     eax, 6
0x14038a025  and     eax, 0Fh
0x14038a028  mov     [rsp+408h+var_348], eax
0x14038a02f  mov     [rsp+408h+var_2F8], r14d
0x14038a037  mov     [rsp+408h+var_330], r14d
0x14038a03f  mov     [rsp+408h+var_2F4], r14d
0x14038a047  mov     [rsp+408h+var_2F0], r14d
0x14038a04f  mov     [rsp+408h+var_370], r14d
0x14038a057  mov     rax, qword ptr [rsp+408h+var_388]
0x14038a05f  mov     rax, [rax+18h]
0x14038a063  lea     rcx, [rsp+408h+var_388]
0x14038a06b  call    _guard_dispatch_icall
0x14038a070  mov     rcx, [rax]
0x14038a073  mov     [rsp+408h+var_270], rcx
0x14038a07b  mov     [rsp+408h+var_338], r14d
0x14038a083  xorps   xmm0, xmm0
0x14038a086  movups  [rsp+408h+var_128], xmm0
0x14038a08e  xorps   xmm1, xmm1
0x14038a091  movups  [rsp+408h+var_118], xmm1
0x14038a099  mov     al, [r13+164h]
0x14038a0a0  neg     al
0x14038a0a2  sbb     rcx, rcx
0x14038a0a5  and     ecx, 0F0h
0x14038a0ab  lea     rax, [r13+210h]
0x14038a0b2  add     rax, rcx
0x14038a0b5  mov     qword ptr [rsp+408h+var_320], rax
0x14038a0bd  mov     rbx, [rsi+2E0h]
0x14038a0c4  mov     rax, [rsp+408h+var_2E8]
0x14038a0cc  add     rax, 8
0x14038a0d0  mov     [rsp+408h+var_300], rax
0x14038a0d8  mov     rdi, [rax]
0x14038a0db  mov     rax, qword ptr [rsp+408h+var_388]
0x14038a0e3  mov     rax, [rax+10h]
0x14038a0e7  lea     rcx, [rsp+408h+var_388]
0x14038a0ef  call    _guard_dispatch_icall
0x14038a0f4  mov     rcx, [rbx+8]
0x14038a0f8  mov     r10, [rcx+1B0h]
0x14038a0ff  lea     rcx, [rsp+408h+var_118]
0x14038a107  mov     [rsp+408h+var_3A0], rcx
0x14038a10c  lea     rcx, [rsp+408h+var_128]
0x14038a114  mov     [rsp+408h+var_3A8], rcx
0x14038a119  lea     rcx, [rsp+408h+var_338]
0x14038a121  mov     [rsp+408h+var_3B0], rcx
0x14038a126  lea     rcx, [rsp+408h+var_2F0]
0x14038a12e  mov     [rsp+408h+var_3B8], rcx
0x14038a133  lea     rcx, [rsp+408h+var_2F4]
0x14038a13b  mov     [rsp+408h+var_3C0], rcx
0x14038a140  lea     rcx, [rsp+408h+var_270]
0x14038a148  mov     [rsp+408h+var_3C8], rcx
0x14038a14d  lea     rcx, [rsp+408h+var_370]
0x14038a155  mov     qword ptr [rsp+408h+var_3D0], rcx
0x14038a15a  lea     rcx, [rsp+408h+var_330]
0x14038a162  mov     [rsp+408h+var_3D8], rcx
0x14038a167  lea     rcx, [rsp+408h+var_2F8]
0x14038a16f  mov     [rsp+408h+var_3E0], rcx
0x14038a174  mov     rcx, qword ptr [rsp+408h+var_320]
0x14038a17c  mov     [rsp+408h+var_3E8], rcx; bool
0x14038a181  mov     r9, rdi
0x14038a184  mov     r8, rax
0x14038a187  lea     rdx, [rsp+408h+var_348]
0x14038a18f  mov     rcx, [rsi+2E8h]
0x14038a196  mov     rax, r10
0x14038a199  call    _guard_dispatch_icall
0x14038a19e  mov     rax, qword ptr [rsp+408h+var_388]
0x14038a1a6  mov     rax, [rax+20h]
0x14038a1aa  mov     rdx, [rsp+408h+var_270]
0x14038a1b2  lea     rcx, [rsp+408h+var_388]
0x14038a1ba  call    _guard_dispatch_icall
0x14038a1bf  mov     rax, qword ptr [rsp+408h+var_388]
0x14038a1c7  mov     rax, [rax+30h]
0x14038a1cb  mov     edx, [rsp+408h+var_348]
0x14038a1d2  lea     rcx, [rsp+408h+var_388]
0x14038a1da  call    _guard_dispatch_icall
0x14038a1df  mov     eax, [rsp+408h+var_348]
0x14038a1e6  mov     [r13+74h], eax
0x14038a1ea  mov     rax, qword ptr [rsp+408h+var_388]
0x14038a1f2  mov     rax, [rax+10h]
0x14038a1f6  lea     rcx, [rsp+408h+var_388]
0x14038a1fe  call    _guard_dispatch_icall
0x14038a203  mov     rdx, rax; SourceLuid
0x14038a206  lea     rcx, [r13+9Ch]; DestinationLuid
0x14038a20d  call    cs:__imp_RtlCopyLuid
0x14038a214  nop     dword ptr [rax+rax+00h]
0x14038a219  mov     rax, [rsp+408h+var_300]
0x14038a221  mov     rax, [rax]
0x14038a224  mov     [r13+0A8h], rax
0x14038a22b  btr     dword ptr [r13+0], 10h
0x14038a231  mov     ecx, [r13+0]
0x14038a235  mov     rbx, [rsp+408h+var_328]
0x14038a23d  test    rbx, rbx
0x14038a240  jnz     loc_14038AEF7
0x14038a246  mov     rax, qword ptr [rsp+408h+var_388]
0x14038a24e  mov     rax, [rax+0C8h]
0x14038a255  lea     rcx, [rsp+408h+var_388]
0x14038a25d  call    _guard_dispatch_icall
0x14038a262  movzx   ecx, al
0x14038a265  mov     eax, [r13+0]
0x14038a269  shl     ecx, 3
0x14038a26c  xor     ecx, eax
0x14038a26e  and     ecx, 8
0x14038a271  xor     ecx, eax
0x14038a273  mov     [r13+0], ecx
0x14038a277  mov     rax, qword ptr [rsp+408h+var_388]
0x14038a27f  mov     rax, [rax+0D0h]
0x14038a286  lea     rcx, [rsp+408h+var_388]
0x14038a28e  call    _guard_dispatch_icall
0x14038a293  movzx   ecx, al
0x14038a296  mov     eax, [r13+0]
0x14038a29a  shl     ecx, 4
0x14038a29d  xor     ecx, eax
0x14038a29f  and     ecx, 10h
0x14038a2a2  xor     ecx, eax
0x14038a2a4  mov     [r13+0], ecx
0x14038a2a8  mov     rax, qword ptr [rsp+408h+var_388]
0x14038a2b0  mov     rax, [rax+0D8h]
0x14038a2b7  lea     rcx, [rsp+408h+var_388]
0x14038a2bf  call    _guard_dispatch_icall
0x14038a2c4  movzx   ecx, al
0x14038a2c7  mov     eax, [r13+0]
0x14038a2cb  shl     ecx, 1Ch
0x14038a2ce  xor     ecx, eax
0x14038a2d0  and     ecx, 10000000h
0x14038a2d6  xor     ecx, eax
0x14038a2d8  mov     [r13+0], ecx
0x14038a2dc  mov     rax, qword ptr [rsp+408h+var_388]
0x14038a2e4  mov     rax, [rax+0E0h]
0x14038a2eb  lea     rcx, [rsp+408h+var_388]
0x14038a2f3  call    _guard_dispatch_icall
0x14038a2f8  movzx   ecx, al
0x14038a2fb  mov     eax, [r13+4]
0x14038a2ff  shl     ecx, 6
0x14038a302  xor     ecx, eax
0x14038a304  and     ecx, 40h
0x14038a307  xor     ecx, eax
0x14038a309  mov     [r13+4], ecx
0x14038a30d  mov     rax, qword ptr [rsp+408h+var_388]
0x14038a315  mov     rax, [rax+140h]
0x14038a31c  lea     rcx, [rsp+408h+var_388]
0x14038a324  call    _guard_dispatch_icall
0x14038a329  movzx   ecx, al
0x14038a32c  mov     eax, [r13+4]
0x14038a330  shl     ecx, 8
0x14038a333  xor     ecx, eax
0x14038a335  and     ecx, 100h
0x14038a33b  xor     ecx, eax
0x14038a33d  mov     [r13+4], ecx
0x14038a341  mov     rax, qword ptr [rsp+408h+var_388]
0x14038a349  mov     rax, [rax+148h]
0x14038a350  lea     rcx, [rsp+408h+var_388]
0x14038a358  call    _guard_dispatch_icall
0x14038a35d  movzx   ecx, al
0x14038a360  mov     eax, [r13+4]
0x14038a364  shl     ecx, 9
0x14038a367  xor     ecx, eax
0x14038a369  and     ecx, 200h
0x14038a36f  xor     ecx, eax
0x14038a371  mov     [r13+4], ecx
0x14038a375  mov     rax, qword ptr [rsp+408h+var_388]
0x14038a37d  mov     rax, [rax+38h]
0x14038a381  mov     rdi, [rsp+408h+var_368]
0x14038a389  mov     rdx, rdi
0x14038a38c  lea     rcx, [rsp+408h+var_388]
0x14038a394  call    _guard_dispatch_icall
0x14038a399  mov     rax, qword ptr [rsp+408h+var_388]
0x14038a3a1  mov     rax, [rax+40h]
0x14038a3a5  lea     rcx, [rsp+408h+var_388]
0x14038a3ad  call    _guard_dispatch_icall
0x14038a3b2  mov     [r13+70h], eax
0x14038a3b6  mov     rax, qword ptr [rsp+408h+var_388]
0x14038a3be  mov     rax, [rax+48h]
0x14038a3c2  lea     rcx, [rsp+408h+var_388]
0x14038a3ca  call    _guard_dispatch_icall
0x14038a3cf  mov     ecx, [rax]
0x14038a3d1  mov     [r13+0C0h], ecx
0x14038a3d8  mov     rax, qword ptr [rsp+408h+var_388]
0x14038a3e0  mov     rax, [rax+0C0h]
0x14038a3e7  lea     rcx, [rsp+408h+var_388]
0x14038a3ef  call    _guard_dispatch_icall
0x14038a3f4  movzx   ecx, al
0x14038a3f7  mov     eax, [r13+0]
0x14038a3fb  shl     ecx, 19h
0x14038a3fe  xor     ecx, eax
0x14038a400  and     ecx, 2000000h
0x14038a406  xor     ecx, eax
0x14038a408  mov     [r13+0], ecx
0x14038a40c  mov     rax, qword ptr [rsp+408h+var_388]
0x14038a414  mov     rax, [rax+50h]
0x14038a418  lea     rcx, [rsp+408h+var_388]
0x14038a420  call    _guard_dispatch_icall
0x14038a425  mov     [r13+90h], eax
0x14038a42c  mov     rax, qword ptr [rsp+408h+var_388]
0x14038a434  mov     rax, [rax+58h]
0x14038a438  lea     rcx, [rsp+408h+var_388]
0x14038a440  call    _guard_dispatch_icall
0x14038a445  mov     [r13+94h], eax
0x14038a44c  test    rbx, rbx
0x14038a44f  jz      loc_14038B437
0x14038a455  mov     eax, [rbx+180h]
0x14038a45b  mov     [r13+88h], eax
0x14038a462  mov     al, [r13+164h]
0x14038a469  test    al, al
  ... truncated ...
```
