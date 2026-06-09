# VIDMM_PAGE_DIRECTORY::CommitVirtualAddressRange(VIDMM_PAGING_EXECUTION_CONTEXT *,CVirtualAddressAllocator *,COMMIT_VA_STATE const *,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,bool,VIDMM_ALLOC * *)

- ea: `0x140099e9c`
- end: `0x14009ae97`
- name: `?CommitVirtualAddressRange@VIDMM_PAGE_DIRECTORY@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAVCVirtualAddressAllocator@@PEBUCOMMIT_VA_STATE@@_K333_NPEAPEAUVIDMM_ALLOC@@@Z`
- size: `4091`
- prototype: `__int64 __fastcall(VIDMM_PAGE_DIRECTORY *__hidden this, struct VIDMM_PAGING_EXECUTION_CONTEXT *, struct CVirtualAddressAllocator *, const struct COMMIT_VA_STATE *, unsigned __int64, unsigned __int64, unsigned __int64, unsigned int, bool, struct VIDMM_ALLOC **)`
- caller_count: `4`
- callee_count: `27`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140099b98`
- `0x140099e9c`
- `0x14009d74c`
- `0x1400aa76c`

## callees

- `0x140004268`
- `0x14002d7c0`
- `0x14002eebc`
- `0x14002f580`
- `0x14002fe1c`
- `0x140042ad0`
- `0x1400994b0`
- `0x140099e9c`
- `0x14009b008`
- `0x14009b674`
- `0x14009b8e4`
- `0x14009ba58`
- `0x14009d31c`
- `0x14009e5b0`
- `0x14009ffa0`
- `0x1400a58a4`
- `0x1400aa76c`
- `0x1400abc68`
- `0x1400c5e5c`
- `0x1400c610c`
- `0x1400f1dcc`
- `0x14010bdd8`
- `0x14010d61c`
- `0x14010f14c`
- `0x14010fc60`
- `0x140112580`
- `0x140118ed4`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14009a3da`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14009a3da`
- `watchdog!WdLogSingleEntry2` at `0x140099f7c`
- `watchdog!WdLogSingleEntry2` at `0x14009ade5`
- `watchdog!WdLogSingleEntry2` at `0x140099f7c`
- `watchdog!WdLogSingleEntry2` at `0x14009ade5`
- `watchdog!WdLogSingleEntry0` at `0x14009aaec`
- `watchdog!WdLogSingleEntry0` at `0x14009ab37`
- `watchdog!WdLogSingleEntry0` at `0x14009aaec`
- `watchdog!WdLogSingleEntry0` at `0x14009ab37`
- `watchdog!WdLogSingleEntry1` at `0x14009a3a7`
- `watchdog!WdLogSingleEntry1` at `0x14009a3a7`

## string_xrefs

- `0x14009aafa`: `Failed to create page table or page directory`

## pseudocode

```c
__int64 __fastcall VIDMM_PAGE_DIRECTORY::CommitVirtualAddressRange(
        VIDMM_PAGE_DIRECTORY *this,
        struct VIDMM_PAGING_EXECUTION_CONTEXT *a2,
        struct CVirtualAddressAllocator *a3,
        const struct COMMIT_VA_STATE *a4,
        unsigned __int64 a5,
        unsigned __int64 a6,
        unsigned __int64 a7,
        unsigned __int64 a8,
        bool a9,
        struct VIDMM_ALLOC **a10)
{
  struct VIDMM_PROCESS *v10; // rbx
  unsigned __int64 *v11; // rdi
  unsigned int v12; // r10d
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v14; // r14
  D3DGPU_VIRTUAL_ADDRESS v17; // rdx
  __int64 v18; // r11
  unsigned int v19; // r9d
  int v20; // r12d
  __int64 v21; // r12
  unsigned __int64 v22; // rdi
  unsigned __int64 v23; // r14
  int v24; // ecx
  int v25; // r8d
  struct VIDMM_PAGE_TABLE_LEVEL_DESC *v26; // r12
  __int64 v27; // rdi
  __int64 v28; // r14
  __int64 v29; // r9
  __int64 v30; // r11
  unsigned __int64 v31; // r9
  bool v32; // dl
  unsigned int v33; // r10d
  unsigned __int64 v34; // r9
  unsigned int v35; // ecx
  unsigned int v36; // eax
  int v37; // eax
  int v38; // ebx
  unsigned int v39; // r11d
  unsigned int v40; // edx
  __int64 v41; // rax
  __int64 v42; // rcx
  unsigned __int64 v43; // r14
  unsigned __int64 v44; // r8
  unsigned __int64 v45; // rdx
  unsigned int v46; // edi
  unsigned int v47; // r10d
  unsigned __int64 v48; // r11
  __int64 v49; // rdx
  unsigned __int64 v50; // r11
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rax
  unsigned int v54; // r9d
  __int64 v55; // r8
  bool v56; // r9
  __int64 v57; // rcx
  __int64 v58; // r14
  unsigned int v59; // ecx
  int v60; // eax
  int v61; // edi
  __int64 v62; // rdi
  char v63; // cl
  unsigned int v64; // eax
  char v65; // r8
  _DWORD *v66; // rax
  __int64 v67; // r12
  __int64 v68; // r14
  bool v69; // di
  struct VIDMM_PAGE_DIRECTORY *PageTable; // rax
  __int64 v71; // r8
  bool v72; // dl
  __int64 v73; // rcx
  __int64 v74; // r9
  struct VIDMM_PAGE_TABLE_LEVEL_DESC *v75; // rdi
  int v76; // eax
  int v77; // r8d
  __int64 v78; // r9
  __int64 v79; // rax
  char v80; // di
  unsigned __int64 v81; // rdx
  int v82; // eax
  int v83; // edi
  VIDMM_PAGE_TABLE *v84; // rcx
  unsigned int v85; // r8d
  _DWORD *v86; // rax
  unsigned __int64 v87; // r10
  __int64 v88; // rax
  __int64 v89; // rax
  int v90; // eax
  bool v91; // cl
  __int64 v92; // rdx
  __int64 v93; // rax
  bool v94; // zf
  __int64 v95; // rcx
  char v96; // di
  unsigned __int64 v97; // r8
  bool v98; // al
  char v99; // cl
  unsigned __int64 v100; // r11
  int v101; // r8d
  unsigned __int64 v102; // rdi
  enum _DXGK_PAGETABLEUPDATEMODE v103; // ecx
  struct _DXGK_PAGETABLEUPDATEADDRESS v104; // xmm6
  unsigned int v105; // r14d
  const struct _DXGK_PTE *v106; // rdx
  struct VIDMM_PAGE_TABLE_LEVEL_DESC *v107; // rbx
  unsigned int v108; // r9d
  int v109; // ecx
  int v110; // r8d
  unsigned __int64 *v111; // rax
  unsigned __int64 *v112; // rbx
  unsigned __int64 *v113; // rbx
  struct VIDMM_ALLOC **v115; // [rsp+40h] [rbp-D8h]
  bool v116; // [rsp+48h] [rbp-D0h]
  struct VIDMM_ALLOC **v117; // [rsp+50h] [rbp-C8h]
  char v118; // [rsp+98h] [rbp-80h]
  int v119; // [rsp+9Ch] [rbp-7Ch]
  unsigned int v120; // [rsp+A0h] [rbp-78h]
  char v121; // [rsp+A4h] [rbp-74h]
  char v122; // [rsp+A5h] [rbp-73h]
  bool v123; // [rsp+A8h] [rbp-70h]
  char v124; // [rsp+A8h] [rbp-70h]
  unsigned int NumPde; // [rsp+ACh] [rbp-6Ch]
  struct VIDMM_PAGE_TABLE_LEVEL_DESC *v126; // [rsp+B0h] [rbp-68h]
  unsigned int v127; // [rsp+B8h] [rbp-60h]
  unsigned int v128; // [rsp+BCh] [rbp-5Ch]
  unsigned __int64 v129; // [rsp+C0h] [rbp-58h]
  unsigned int v130; // [rsp+C8h] [rbp-50h]
  unsigned __int64 v131; // [rsp+D0h] [rbp-48h]
  unsigned int v132; // [rsp+D8h] [rbp-40h]
  __int64 v133; // [rsp+E0h] [rbp-38h]
  struct VIDMM_PAGE_TABLE *v134; // [rsp+E8h] [rbp-30h] BYREF
  unsigned __int64 v135; // [rsp+F0h] [rbp-28h]
  VIDMM_GLOBAL *v136; // [rsp+F8h] [rbp-20h]
  VIDMM_PAGE_TABLE *v137; // [rsp+100h] [rbp-18h]
  unsigned __int64 v138; // [rsp+108h] [rbp-10h]
  unsigned __int64 v139; // [rsp+110h] [rbp-8h]
  struct VIDMM_PAGE_DIRECTORY *v140[2]; // [rsp+118h] [rbp+0h] BYREF
  struct _DXGK_PAGETABLEUPDATEADDRESS v141; // [rsp+128h] [rbp+10h] BYREF
  unsigned __int64 v142; // [rsp+138h] [rbp+20h]
  unsigned __int64 v143; // [rsp+140h] [rbp+28h]
  unsigned __int64 v144; // [rsp+148h] [rbp+30h]
  struct VIDMM_GLOBAL_ALLOC *VidMmGlobalAllocFromOwner; // [rsp+150h] [rbp+38h]
  struct VIDMM_ALLOC *VidMmAllocFromOwner; // [rsp+158h] [rbp+40h]
  unsigned __int64 v147; // [rsp+160h] [rbp+48h]
  __int128 v148; // [rsp+168h] [rbp+50h] BYREF
  char v149; // [rsp+178h] [rbp+60h]
  bool v150; // [rsp+1E8h] [rbp+D0h] BYREF
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v151; // [rsp+1F0h] [rbp+D8h]
  char v152; // [rsp+1F8h] [rbp+E0h]
  char v153; // [rsp+200h] [rbp+E8h]

  v151 = a2;
  v10 = (struct VIDMM_PROCESS *)*((_QWORD *)a3 + 13);
  v11 = 0;
  v12 = *(_DWORD *)this;
  v14 = a2;
  v140[0] = 0;
  v137 = 0;
  v134 = 0;
  v136 = (VIDMM_GLOBAL *)*((_QWORD *)a3 + 12);
  v17 = *(_QWORD *)(*((_QWORD *)v136 + 4560) + 8LL * ((v12 >> 8) & 0x1F));
  v141.GpuVirtual = v17;
  *a10 = 0;
  v18 = *(_QWORD *)a4;
  v19 = 1;
  if ( (v18 & 1) == 0 && (!VIDMM_PAGE_TABLE_BASE::IsResident(this) || !*((_DWORD *)this + 1)) )
    return 0;
  v21 = a8;
  if ( ((a8 | a6) & 0xFFF) != 0 )
  {
    WdLogSingleEntry2(v19, a6, a8);
    WdLogGlobalForLineNumber = 8686;
    DxgkLogInternalTriageEvent(
      v109,
      0x40000,
      v110,
      (unsigned int)L"Invalid alignment of start virtual address",
      a6,
      v21,
      0,
      0);
    v20 = -1073741811;
    goto LABEL_188;
  }
  v22 = a6 >> 12;
  v143 = a6 >> 12;
  v23 = (a6 >> 12) + a7;
  v147 = v23;
  if ( v23 <= a6 >> 12 )
  {
    WdLogSingleEntry2(1, (a6 >> 12) + a7, a6 >> 12);
    WdLogGlobalForLineNumber = 8712;
    DxgkLogInternalTriageEvent(
      v24,
      0x40000,
      v25,
      (unsigned int)L"LastPageIndex <= FirstPageIndex (%I64u < %I64u)",
      v23,
      v22,
      0,
      0);
    return (unsigned int)-1073741811;
  }
  v26 = (struct VIDMM_PAGE_TABLE_LEVEL_DESC *)(v17 + 48LL * (v12 & 7) + 1000);
  v126 = v26;
  v27 = *((_QWORD *)v26 + 2);
  v28 = *((_QWORD *)v26 + 3);
  NumPde = CVirtualAddressAllocator::GetNumPde(a3, this);
  if ( (*(_DWORD *)this & 0x10) != 0 )
  {
    v31 = v29 << 12;
    if ( v30 )
    {
      v115 = (struct VIDMM_ALLOC **)*((_QWORD *)a4 + 6);
      VIDMM_GLOBAL::RecordVaPagingHistoryCommit(v136, v10, a6, v31, *((_DWORD *)a4 + 18), a8, (char *)a4 + 32);
    }
    else
    {
      VIDMM_GLOBAL::RecordVaPagingHistoryUncommit(v136, v10, a6, v31);
    }
  }
  if ( VIDMM_PAGE_TABLE_BASE::IsResident(this) )
  {
    v32 = a9;
  }
  else
  {
    v20 = VIDMM_PAGE_DIRECTORY::CommitPageDirectory(this, v151, a3, a10);
    if ( v20 < 0 )
      return (unsigned int)v20;
    *(_DWORD *)this &= ~0x20000u;
    v32 = 1;
    v26 = v126;
  }
  v33 = 0;
  v139 = a5;
  v34 = (v27 & v143) >> v28;
  v35 = *(_DWORD *)this;
  v36 = *(_DWORD *)this;
  VidMmGlobalAllocFromOwner = 0;
  VidMmAllocFromOwner = 0;
  v130 = 0;
  v121 = 0;
  v122 = 0;
  v132 = 0;
  v135 = v34;
  v37 = v36 & 0x20000;
  if ( !v37 || v32 )
  {
    v40 = 0;
    v38 = v37 == 0 ? 2 : 0;
    if ( (_DWORD)v34 )
    {
      do
      {
        v41 = *((_QWORD *)this + 6);
        v42 = v40++;
        v42 *= 2;
        *(_QWORD *)(v41 + 8 * v42) = 0;
        *(_QWORD *)(v41 + 8 * v42 + 8) = 0;
      }
      while ( v40 < (unsigned int)v34 );
      v35 = *(_DWORD *)this;
    }
    v39 = NumPde;
    v128 = NumPde;
    v118 = 1;
  }
  else
  {
    v128 = 0;
    v38 = 0;
    v118 = 0;
    v39 = NumPde;
  }
  v43 = v143;
  v44 = v143 & ~*((_QWORD *)v26 + 4);
  v129 = v143;
  v45 = v44 + *((_QWORD *)v26 + 5);
  v142 = v44;
  v144 = v45;
  v138 = v45;
  if ( (v35 & 0x20) != 0 && *((_BYTE *)a4 + 78) )
  {
    if ( *((_BYTE *)a4 + 76) )
      v33 = v39;
    v132 = v33;
  }
  v119 = 0;
  while ( 1 )
  {
    if ( (unsigned int)v34 >= v39 )
      goto LABEL_166;
    v46 = v34 + v33;
    v47 = v46;
    v123 = 0;
    v150 = 0;
    v152 = 0;
    v127 = v46;
    v120 = v46;
    if ( *((_BYTE *)a4 + 79) && (*(_DWORD *)this & 0x20) != 0 )
    {
      v47 = v46 + v39;
      if ( v46 != (_DWORD)v34 )
        v47 = v34;
      v120 = v47;
      v152 = 1;
    }
    if ( v45 >= v147 )
    {
      v45 = v147;
      v138 = v147;
      v121 = 1;
    }
    v48 = v45;
    v49 = *(_QWORD *)a4;
    v50 = v48 - v43;
    v131 = v50;
    if ( (*(_QWORD *)a4 & 1) != 0 )
      break;
    v51 = *((_QWORD *)this + 6);
    if ( (*(_BYTE *)(v51 + 16LL * v46) & 1) != 0 || (*(_BYTE *)(v51 + 16LL * v47) & 1) != 0 )
      break;
LABEL_162:
    v43 = v138;
    v129 = v138;
    if ( v121 )
      goto LABEL_166;
    v33 = v132;
    v34 = (unsigned int)(v34 + 1);
    v100 = v50 << 12;
    v44 = v138;
    a8 += v100;
    v142 = v138;
    v45 = *((_QWORD *)v26 + 5) + v138;
    v139 += v100;
    v39 = NumPde;
    v135 = v34;
    v138 = v45;
    v144 = v45;
  }
  if ( (v49 & 2) != 0 )
  {
    v52 = *((_QWORD *)this + 6);
    if ( (*(_BYTE *)(v52 + 16LL * v46) & 2) != 0 )
    {
      v53 = v46;
    }
    else
    {
      if ( !v152 || (*(_BYTE *)(v52 + 16LL * v47) & 2) == 0 )
        goto LABEL_48;
      v53 = v47;
    }
    if ( (_DWORD)v53 != -1 && ((*(_BYTE *)(16 * v53 + v52) ^ (unsigned __int8)v49) & 8) == 0 )
      goto LABEL_162;
  }
LABEL_48:
  if ( *((_QWORD *)v26 + 5) <= v50 && (*((_DWORD *)a3 + 38) & 4) == 0 )
  {
    if ( VIDMM_PAGE_DIRECTORY::HandleFullPageTableCoverage(
           this,
           a3,
           *(const struct _DXGK_GPUMMUCAPS **)(v141.GpuVirtual + 1352),
           a4,
           v26,
           v46,
           v47,
           (unsigned int)v115,
           a8,
           &v150,
           (bool *)a4 + 84) )
    {
      if ( (*(_DWORD *)(*((_QWORD *)this + 6) + 16LL * v46) & 0x400LL) != 0 )
      {
        VidMmGlobalAllocFromOwner = (struct VIDMM_GLOBAL_ALLOC *)GetVidMmGlobalAllocFromOwner(
                                                                   *((unsigned int *)a4 + 14),
                                                                   *((_QWORD *)a4 + 6));
        VidMmAllocFromOwner = (struct VIDMM_ALLOC *)GetVidMmAllocFromOwner(v54, v55);
      }
      v56 = v150;
      v122 = 1;
      goto LABEL_143;
    }
    v44 = v142;
    v50 = v131;
    v123 = v150;
  }
  v57 = *((_QWORD *)this + 6);
  v58 = v46;
  if ( (*(_DWORD *)(v57 + 16LL * v46) & 0x400LL) != 0 )
  {
    v59 = v46;
  }
  else
  {
    v153 = 0;
    if ( !v152 || (*(_DWORD *)(v57 + 16LL * v120) & 0x400LL) == 0 )
      goto LABEL_65;
    v59 = v120;
  }
  if ( *((_QWORD *)v26 + 5) <= v50 )
  {
    v62 = v59;
    ExFreeToPagedLookasideList(
      (PPAGED_LOOKASIDE_LIST)(*((_QWORD *)a3 + 12) + 36544LL),
      *(PVOID *)(*((_QWORD *)this + 7) + 8LL * v59));
    *(_QWORD *)(*((_QWORD *)this + 7) + 8 * v62) = 0;
    v62 *= 16;
    *(_QWORD *)(v62 + *((_QWORD *)this + 6)) &= ~0x400uLL;
    *(_QWORD *)(v62 + *((_QWORD *)this + 6)) &= ~1uLL;
    --*((_DWORD *)this + 1);
  }
  else
  {
    v60 = VIDMM_PAGE_DIRECTORY::ExpandLargePagePte(this, v151, a3, v26, a4, v44 << 12, v59, a10);
    v61 = v60;
    v119 = v60;
    if ( v60 < 0 )
    {
      WdLogSingleEntry1(3, v60);
      WdLogGlobalForLineNumber = 8973;
      v20 = v61;
      goto LABEL_167;
    }
  }
  v46 = v127;
  v153 = 1;
LABEL_65:
  v63 = *((_BYTE *)a4 + 76);
  v64 = *(_DWORD *)this;
  v65 = v63 != 0;
  v150 = v63 != 0;
  if ( (v64 & 0x20) == 0 || *((_DWORD *)a4 + 18) || !v63 )
  {
    v150 = v63 != 0;
    goto LABEL_84;
  }
  if ( !*((_BYTE *)a4 + 78)
    && !*((_BYTE *)a4 + 77)
    && (v66 = *(_DWORD **)(*((_QWORD *)this + 7) + 8 * v58)) != 0
    && v66[1]
    && (*v66 & 0x40) == 0
    || (v131 & 0xF) != 0 )
  {
    v150 = 0;
LABEL_81:
    v46 = v135;
    v127 = v135;
    if ( v152 )
      v120 = NumPde + v135;
    goto LABEL_84;
  }
  if ( *((_QWORD *)a4 + 11) )
  {
    v150 = v63 != 0;
  }
  else if ( !*((_BYTE *)a4 + 77) || g_Feature_Largify64KBPrototype )
  {
    v65 = CheckContiguous64KB((char *)a4 + 32, (unsigned int)v131, a8 >> 12);
    v150 = v65;
  }
  if ( !v65 )
    goto LABEL_81;
LABEL_84:
  v67 = 16LL * v46;
  v68 = v46;
  v133 = v46;
  if ( ((*(_BYTE *)a4 & 1) != 0 || (*(_BYTE *)(v67 + *((_QWORD *)this + 6)) & 2) != 0)
    && !*(_QWORD *)(*((_QWORD *)this + 7) + 8LL * v46) )
  {
    v69 = 0;
    if ( (*((_DWORD *)a3 + 38) & 4) != 0 )
      v69 = a6 < *((_QWORD *)v136 + 4660);
    if ( (*(_DWORD *)this & 0x20) != 0 )
      PageTable = (struct VIDMM_PAGE_DIRECTORY *)CreatePageTable(a3);
    else
      PageTable = CreatePageDirectory(a3, (*(_DWORD *)this >> 8) & 0x1F, (*(_DWORD *)this & 7u) - 1);
    *(_QWORD *)(*((_QWORD *)this + 7) + 8 * v68) = PageTable;
    if ( v69 )
      **(_DWORD **)(*((_QWORD *)this + 7) + 8 * v68) |= 0x100000u;
    if ( !*(_QWORD *)(*((_QWORD *)this + 7) + 8 * v68) )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 9123;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        v101,
        (unsigned int)L"Failed to create page table or page directory",
        9123,
        0,
        0,
        0);
      v20 = -1073741801;
      goto LABEL_167;
    }
  }
  v71 = *((_QWORD *)this + 6);
  v72 = (*(_QWORD *)(v67 + v71) & 1) == 0;
  v73 = *(_QWORD *)(v67 + v71) & 2LL;
  if ( (*(_QWORD *)(v67 + v71) & 2) != 0 )
  {
    v74 = v120;
  }
  else if ( v152 == (_BYTE)v73 || (v74 = v120, (*(_BYTE *)(v71 + 16LL * v120) & 2) == 0) )
  {
LABEL_109:
    if ( (*(_DWORD *)this & 0x20) == 0 )
    {
      ++*((_DWORD *)this + 1);
      v90 = VIDMM_PAGE_DIRECTORY::CommitVirtualAddressRange(
              *(VIDMM_PAGE_DIRECTORY **)(*((_QWORD *)this + 7) + 8 * v68),
              v151,
              a3,
              a4,
              v139,
              v129 << 12,
              v131,
              a8,
              v72,
              a10);
      --*((_DWORD *)this + 1);
      v83 = v90;
      v119 = v90;
      goto LABEL_126;
    }
    if ( (*(_BYTE *)a4 & 1) != 0 )
    {
      v80 = *((_BYTE *)a4 + 76);
      v117 = a10;
      v116 = v72;
      v81 = a8;
      *((_BYTE *)a4 + 76) = v150;
      ++*((_DWORD *)this + 1);
      v82 = VIDMM_PAGE_TABLE::CommitVirtualAddressRange(
              *(VIDMM_PAGE_TABLE **)(*((_QWORD *)this + 7) + 8 * v68),
              v151,
              a3,
              a4,
              v139,
              v129 << 12,
              v131,
              v81,
              v116,
              v117);
      *((_BYTE *)a4 + 76) = v80;
      --*((_DWORD *)this + 1);
    }
    else
    {
      v84 = *(VIDMM_PAGE_TABLE **)(*((_QWORD *)this + 7) + 8 * v68);
      if ( !v84 || !*((_DWORD *)v84 + 1) )
      {
        v83 = v119;
LABEL_117:
        if ( *((_BYTE *)a4 + 79) )
        {
          if ( v83 < 0 )
            goto LABEL_165;
          v85 = v120;
          if ( (*(_BYTE *)(*((_QWORD *)this + 6) + 16LL * v120) & 1) == 0 )
          {
            v68 = v133;
            goto LABEL_128;
          }
          v119 = VIDMM_PAGE_TABLE::UncommitVirtualAddressRange(
                   *(VIDMM_PAGE_TABLE **)(*((_QWORD *)this + 7) + 8LL * v120),
                   v151,
                   a3,
                   a4,
                   v129 << 12,
                   v131);
          if ( v119 < 0 )
            goto LABEL_165;
          v86 = *(_DWORD **)(*((_QWORD *)this + 7) + 8LL * v120);
          if ( !v86[1] && (*v86 & 0x100000) == 0 )
          {
            v87 = v129;
            v85 = v120;
            if ( !*((_BYTE *)a4 + 82) )
            {
              --*((_DWORD *)this + 1);
              v56 = 1;
              v88 = *((_QWORD *)this + 6);
              *(_QWORD *)(v88 + 16LL * v120) = 0;
              *(_QWORD *)(v88 + 16LL * v120 + 8) = 0;
              v68 = v133;
              *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 7) + 8LL * v120) + 56LL) = v137;
              *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 7) + 8LL * v120) + 16LL) = v129 & ~*((_QWORD *)v126 + 4);
              v89 = *((_QWORD *)this + 7);
              v137 = *(VIDMM_PAGE_TABLE **)(v89 + 8LL * v120);
              v134 = v137;
              *(_QWORD *)(v89 + 8LL * v120) = 0;
              goto LABEL_130;
            }
            v68 = v133;
LABEL_129:
            v56 = v123;
LABEL_130:
            if ( (*(_BYTE *)a4 & 1) == 0 )
            {
              v26 = v126;
              v96 = v56;
              if ( v153 )
                v96 = 1;
              v94 = !VIDMM_PAGE_DIRECTORY::CheckPageTableInvalid(this, v127, v87 & ~*((_QWORD *)v126 + 4), v140, &v134);
              v56 = v96;
              if ( !v94 )
                v56 = 1;
              v124 = v56;
              if ( v120 != v127 )
              {
                v98 = VIDMM_PAGE_DIRECTORY::CheckPageTableInvalid(this, v120, v97, v140, &v134);
                v99 = v124;
                if ( v98 )
                  v99 = 1;
                v56 = v99;
              }
              v137 = v134;
              goto LABEL_143;
            }
            v91 = (*(_DWORD *)this & 0x20) != 0
               && !*((_BYTE *)a4 + 78)
               && ((**(_DWORD **)(*((_QWORD *)this + 7) + 8 * v68) >> 6) & 1) != ((*(_DWORD *)(v67
                                                                                             + *((_QWORD *)this + 6))
                                                                                 & 0x60000) == 0x20000);
            v92 = *((_QWORD *)this + 6);
            v93 = *(_QWORD *)(v92 + v67);
            if ( (v93 & 1) != 0 )
            {
              if ( !v91 && !v153 )
              {
LABEL_142:
                v26 = v126;
LABEL_143:
                v94 = !v56;
                LODWORD(v34) = v135;
                if ( v94 )
                {
                  v50 = v131;
                }
                else
                {
                  if ( !v118 )
                  {
                    v118 = 1;
                    v130 = v135;
                  }
                  v50 = v131;
                  if ( (unsigned int)v135 >= v128 )
                    v128 = v135 + 1;
                }
                goto LABEL_162;
              }
            }
            else
            {
              *(_QWORD *)(v92 + v67) = v93 | 1;
              ++*((_DWORD *)this + 1);
            }
            *(_QWORD *)(*((_QWORD *)this + 6) + v67) &= ~0x400uLL;
            *(_QWORD *)(*((_QWORD *)this + 6) + v67) &= ~2uLL;
            *(_QWORD *)(*((_QWORD *)this + 6) + v67) &= ~8uLL;
            if ( v152 )
            {
              v95 = 16LL * v85;
              *(_QWORD *)(*((_QWORD *)this + 6) + v95) &= ~0x400uLL;
              *(_QWORD *)(*((_QWORD *)this + 6) + v95) &= ~2uLL;
              *(_QWORD *)(*((_QWORD *)this + 6) + v95) &= ~8uLL;
            }
            VIDMM_PAGE_DIRECTORY::SetPageTableInPde(this, a3, v127);
            v56 = 1;
            goto LABEL_142;
          }
          v68 = v133;
LABEL_127:
          v85 = v120;
LABEL_128:
          v87 = v129;
          goto LABEL_129;
        }
LABEL_126:
        if ( v83 < 0 )
        {
LABEL_165:
          WdLogSingleEntry0(3);
          WdLogGlobalForLineNumber = 9276;
LABEL_166:
          v20 = v119;
LABEL_167:
          v75 = v126;
          goto LABEL_168;
        }
        goto LABEL_127;
      }
      v82 = VIDMM_PAGE_TABLE::UncommitVirtualAddressRange(v84, v151, a3, a4, v129 << 12, v131);
    }
    v83 = v82;
    v119 = v82;
    goto LABEL_117;
  }
  v75 = v126;
  if ( *((_QWORD *)v126 + 5) <= v131 )
  {
    if ( v73 )
      v74 = v127;
    v77 = 0;
    v78 = 16 * v74;
    do
    {
      v79 = (unsigned int)v77++;
      *(_QWORD *)(v78 + *((_QWORD *)this + 6)) &= v79 - 3;
    }
    while ( v77 < 2 );
    --*((_DWORD *)this + 1);
    goto LABEL_108;
  }
  v76 = VIDMM_PAGE_DIRECTORY::ExpandZeroPte(this, v151, a3, a4, v127, v74, v129, v138, v142, v144, a10);
  v119 = v76;
  if ( v76 >= 0 )
  {
    v72 = 0;
LABEL_108:
    v153 = 1;
    goto LABEL_109;
  }
  v20 = v76;
LABEL_168:
  if ( !v118 )
  {
    v107 = v126;
LABEL_182:
    v14 = v151;
    goto LABEL_183;
  }
  v149 = 1;
  v141 = 0;
  v148 = 0;
  VIDMM_PAGE_TABLE_BASE::GetDriverUpdateAddress(this, v151, a3, &v141, (struct VIDMM_SYSTEM_ADDRESS_CONTEXT *)&v148);
  v102 = (v143 & ~(*((_QWORD *)v75 + 4) | *((_QWORD *)v75 + 2))) + *((_QWORD *)v75 + 5) * v130;
  if ( *((_BYTE *)v136 + 37229) )
    v103 = DXGK_PAGETABLEUPDATE_CPU_VIRTUAL;
  else
    v103 = (int)(*(_DWORD *)this << 15) >> 29;
  v104 = v141;
  if ( *((_BYTE *)a4 + 78) && (*(_DWORD *)this & 0x20) != 0 )
  {
    v105 = NumPde + v130;
    v106 = (const struct _DXGK_PTE *)(*((_QWORD *)this + 6) + 16LL * (NumPde + v130));
  }
  else
  {
    v106 = 0;
    v105 = NumPde + v130;
  }
  VIDMM_GLOBAL::UpdatePageTable(
    v136,
    v151,
    this,
    *((struct VIDMM_PROCESS **)a3 + 13),
    *((_QWORD *)a4 + 2),
    VidMmAllocFromOwner,
    VidMmGlobalAllocFromOwner,
    a5 + ((v102 - v143) << 12),
    v130,
    v128 - v130,
    (const struct _DXGK_PTE *)(*((_QWORD *)this + 6) + 16LL * v130),
    v106,
    (*(_DWORD *)this >> 8) & 0x1F,
    &v141,
    v103,
    v102,
    (struct _DXGK_UPDATEPAGETABLEFLAGS)v38,
    *((_QWORD *)a4 + 11));
  v141 = v104;
  VIDMM_PAGE_TABLE_BASE::FreeDriverUpdateAddress(this, v151, a3, &v141, (struct VIDMM_SYSTEM_ADDRESS_CONTEXT *)&v148);
  *(_DWORD *)this |= 0x20000u;
  v107 = v126;
  if ( !v122 )
    goto LABEL_182;
  CVirtualAddressAllocator::FlushGpuVaTlb(
    a3,
    v151,
    (*(_DWORD *)this >> 8) & 0x1F,
    v102 << 12,
    (v102 + *((_QWORD *)v126 + 5)) << 12);
  VIDMM_PAGE_DIRECTORY::DestroyDisconnectedPageTables(this, v151, a3, v130, v128, v102, *((_QWORD *)v126 + 5), *a10);
  if ( !*((_BYTE *)a4 + 78) || (*(_DWORD *)this & 0x20) == 0 )
    goto LABEL_182;
  v108 = v105;
  v14 = v151;
  VIDMM_PAGE_DIRECTORY::DestroyDisconnectedPageTables(
    this,
    v151,
    a3,
    v108,
    NumPde + v128,
    v102,
    *((_QWORD *)v126 + 5),
    *a10);
LABEL_183:
  if ( !*((_DWORD *)this + 1) && (*((_DWORD *)a3 + 38) & 4) == 0 )
    VIDMM_PAGE_DIRECTORY::EvictPageDirectory(this, v14, a3, a6 & ~*((_QWORD *)v107 + 4), 1, 1);
  v11 = (unsigned __int64 *)v140[0];
LABEL_188:
  v111 = (unsigned __int64 *)v137;
  if ( v137 )
  {
    do
    {
      v112 = (unsigned __int64 *)v111[7];
      VIDMM_PAGE_TABLE::DestroyPageTable((VIDMM_PAGE_TABLE *)v111, v14, a3, v111[2]);
      v111 = v112;
    }
    while ( v112 );
  }
  if ( v11 )
  {
    do
    {
      v113 = (unsigned __int64 *)v11[5];
      VIDMM_PAGE_DIRECTORY::DestroyPageDirectory((VIDMM_PAGE_DIRECTORY *)v11, v14, a3, v11[2]);
      v11 = v113;
    }
    while ( v113 );
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x140099e9c  mov     rax, rsp
0x140099e9f  mov     [rax+10h], rdx
0x140099ea3  push    rbp
0x140099ea4  push    rbx
0x140099ea5  push    rsi
0x140099ea6  push    rdi
0x140099ea7  push    r12
0x140099ea9  push    r13
0x140099eab  push    r14
0x140099ead  push    r15
0x140099eaf  lea     rbp, [rax-0C8h]
0x140099eb6  sub     rsp, 198h
0x140099ebd  mov     rbx, [r8+68h]
0x140099ec1  xor     edi, edi
0x140099ec3  mov     r10d, [rcx]
0x140099ec6  mov     r13, r8
0x140099ec9  movaps  xmmword ptr [rax-58h], xmm6
0x140099ecd  mov     r14, rdx
0x140099ed0  xor     eax, eax
0x140099ed2  mov     [rbp+0C0h+var_C0], rdi
0x140099ed6  mov     [rbp+0C0h+var_D8], rax
0x140099eda  mov     r15, r9
0x140099edd  mov     [rbp+0C0h+var_F0], rax
0x140099ee1  mov     rsi, rcx
0x140099ee4  mov     rax, [r8+60h]
0x140099ee8  mov     r8d, r10d
0x140099eeb  shr     r8, 8
0x140099eef  mov     [rbp+0C0h+var_E0], rax
0x140099ef3  and     r8d, 1Fh
0x140099ef7  mov     rax, [rax+8E80h]
0x140099efe  mov     rdx, [rax+r8*8]
0x140099f02  mov     rax, [rbp+0C0h+arg_48]
0x140099f09  mov     qword ptr [rbp+0C0h+var_B0], rdx
0x140099f0d  mov     [rax], rdi
0x140099f10  mov     r11, [r9]
0x140099f13  lea     r9d, [rdi+1]
0x140099f17  and     r11, r9
0x140099f1a  jnz     short loc_140099F32
0x140099f1c  call    ?IsResident@VIDMM_PAGE_TABLE_BASE@@QEBA_NXZ; VIDMM_PAGE_TABLE_BASE::IsResident(void)
0x140099f21  test    al, al
0x140099f23  jz      short loc_140099F2A
0x140099f25  cmp     [rsi+4], edi
0x140099f28  jnz     short loc_140099F32
0x140099f2a  xor     r12d, r12d
0x140099f2d  jmp     loc_14009AE77
0x140099f32  mov     rcx, [rbp+0C0h+arg_28]
0x140099f39  mov     r12, [rbp+0C0h+arg_38]
0x140099f40  mov     rax, rcx
0x140099f43  or      rax, r12
0x140099f46  test    rax, 0FFFh
0x140099f4c  jnz     loc_14009ADDC
0x140099f52  mov     r9, [rbp+0C0h+arg_30]
0x140099f59  mov     rdi, rcx
0x140099f5c  shr     rdi, 0Ch
0x140099f60  mov     [rbp+0C0h+var_98], rdi
0x140099f64  lea     r14, [rdi+r9]
0x140099f68  mov     [rbp+0C0h+var_78], r14
0x140099f6c  cmp     r14, rdi
0x140099f6f  ja      short loc_140099FCA
0x140099f71  mov     r8, rdi
0x140099f74  mov     rdx, r14
0x140099f77  mov     ecx, 1
0x140099f7c  call    cs:__imp_WdLogSingleEntry2
0x140099f83  nop     dword ptr [rax+rax+00h]
0x140099f88  mov     [rsp+1D0h+var_198], 0
0x140099f91  lea     r9, aLastpageindexF; "LastPageIndex <= FirstPageIndex (%I64u "...
0x140099f98  mov     [rsp+1D0h+var_1A0], 0
0x140099fa1  mov     edx, 40000h
0x140099fa6  mov     [rsp+1D0h+var_1A8], rdi
0x140099fab  mov     [rsp+1D0h+var_1B0], r14
0x140099fb0  mov     cs:WdLogGlobalForLineNumber, 2208h
0x140099fba  call    DxgkLogInternalTriageEvent
0x140099fbf  mov     r12d, 0C000000Dh
0x140099fc5  jmp     loc_14009AE77
0x140099fca  and     r10d, 7
0x140099fce  mov     rcx, r13; this
0x140099fd1  lea     r12, [r10+r10*2]
0x140099fd5  shl     r12, 4
0x140099fd9  add     r12, 3E8h
0x140099fe0  add     r12, rdx
0x140099fe3  mov     rdx, rsi; struct VIDMM_PAGE_DIRECTORY *
0x140099fe6  mov     [rbp+0C0h+var_128], r12
0x140099fea  mov     rdi, [r12+10h]
0x140099fef  mov     r14, [r12+18h]
0x140099ff4  call    ?GetNumPde@CVirtualAddressAllocator@@QEBAIPEAVVIDMM_PAGE_DIRECTORY@@@Z; CVirtualAddressAllocator::GetNumPde(VIDMM_PAGE_DIRECTORY *)
0x140099ff9  mov     ecx, [rsi]
0x140099ffb  mov     [rbp+0C0h+var_12C], eax
0x140099ffe  test    cl, 10h
0x14009a001  jz      short loc_14009A05F
0x14009a003  shl     r9, 0Ch; unsigned __int64
0x14009a007  mov     rdx, rbx; struct VIDMM_PROCESS *
0x14009a00a  test    r11, r11
0x14009a00d  jz      short loc_14009A04F
0x14009a00f  mov     ecx, [r15+38h]
0x14009a013  lea     r8, [r15+20h]
0x14009a017  mov     rax, [rbp+0C0h+arg_38]
0x14009a01e  mov     dword ptr [rsp+1D0h+var_190], ecx
0x14009a022  mov     rcx, [r15+30h]
0x14009a026  mov     [rsp+1D0h+var_198], rcx
0x14009a02b  mov     rcx, [rbp+0C0h+var_E0]
0x14009a02f  mov     [rsp+1D0h+var_1A0], r8
0x14009a034  mov     r8, [rbp+0C0h+arg_28]
0x14009a03b  mov     [rsp+1D0h+var_1A8], rax
0x14009a040  mov     eax, [r15+48h]
0x14009a044  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x14009a048  call    ?RecordVaPagingHistoryCommit@VIDMM_GLOBAL@@QEAAXPEAVVIDMM_PROCESS@@_K1I1PEBU_DXGK_ADL@@PEAXW4VIDMM_VAD_OWNER_TYPE@@@Z; VIDMM_GLOBAL::RecordVaPagingHistoryCommit(VIDMM_PROCESS *,unsigned __int64,unsigned __int64,uint,unsigned __int64,_DXGK_ADL const *,void *,VIDMM_VAD_OWNER_TYPE)
0x14009a04d  jmp     short loc_14009A05F
0x14009a04f  mov     r8, [rbp+0C0h+arg_28]; unsigned __int64
0x14009a056  mov     rcx, [rbp+0C0h+var_E0]; this
0x14009a05a  call    ?RecordVaPagingHistoryUncommit@VIDMM_GLOBAL@@QEAAXPEAVVIDMM_PROCESS@@_K1@Z; VIDMM_GLOBAL::RecordVaPagingHistoryUncommit(VIDMM_PROCESS *,unsigned __int64,unsigned __int64)
0x14009a05f  mov     rcx, rsi; this
0x14009a062  call    ?IsResident@VIDMM_PAGE_TABLE_BASE@@QEBA_NXZ; VIDMM_PAGE_TABLE_BASE::IsResident(void)
0x14009a067  xor     r11d, r11d
0x14009a06a  test    al, al
0x14009a06c  jnz     short loc_14009A0A1
0x14009a06e  mov     r9, [rbp+0C0h+arg_48]; struct VIDMM_ALLOC **
0x14009a075  mov     r8, r13; struct CVirtualAddressAllocator *
0x14009a078  mov     rdx, [rbp+0C0h+arg_8]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x14009a07f  mov     rcx, rsi; this
0x14009a082  call    ?CommitPageDirectory@VIDMM_PAGE_DIRECTORY@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAVCVirtualAddressAllocator@@PEAPEAUVIDMM_ALLOC@@@Z; VIDMM_PAGE_DIRECTORY::CommitPageDirectory(VIDMM_PAGING_EXECUTION_CONTEXT *,CVirtualAddressAllocator *,VIDMM_ALLOC * *)
0x14009a087  xor     r11d, r11d
0x14009a08a  mov     r12d, eax
0x14009a08d  test    eax, eax
0x14009a08f  js      loc_14009AE77
0x14009a095  btr     dword ptr [rsi], 11h
0x14009a099  mov     dl, 1
0x14009a09b  mov     r12, [rbp+0C0h+var_128]
0x14009a09f  jmp     short loc_14009A0A7
0x14009a0a1  mov     dl, [rbp+0C0h+arg_40]
0x14009a0a7  mov     rax, [rbp+0C0h+arg_20]
0x14009a0ae  mov     rcx, r14
0x14009a0b1  mov     r9, [rbp+0C0h+var_98]
0x14009a0b5  mov     r10d, r11d
0x14009a0b8  and     r9, rdi
0x14009a0bb  mov     [rbp+0C0h+var_C8], rax
0x14009a0bf  shr     r9, cl
0x14009a0c2  mov     ecx, [rsi]
0x14009a0c4  mov     eax, ecx
0x14009a0c6  mov     [rbp+0C0h+var_88], r11
0x14009a0ca  mov     [rbp+0C0h+var_80], r11
0x14009a0ce  mov     [rbp+0C0h+var_110], r11d
0x14009a0d2  mov     [rbp+0C0h+var_134], r11b
0x14009a0d6  mov     [rbp+0C0h+var_133], r11b
0x14009a0da  mov     [rbp+0C0h+var_100], r11d
0x14009a0de  mov     [rbp+0C0h+var_E8], r9
0x14009a0e2  and     eax, 20000h
0x14009a0e7  jz      short loc_14009A0FE
0x14009a0e9  test    dl, dl
0x14009a0eb  jnz     short loc_14009A0FE
0x14009a0ed  mov     [rbp+0C0h+var_11C], r11d
0x14009a0f1  mov     ebx, r11d
0x14009a0f4  mov     [rbp+0C0h+var_140], r11b
0x14009a0f8  mov     r11d, [rbp+0C0h+var_12C]
0x14009a0fc  jmp     short loc_14009A136
0x14009a0fe  neg     eax
0x14009a100  mov     edx, r11d
0x14009a103  sbb     ebx, ebx
0x14009a105  not     ebx
0x14009a107  and     ebx, 2
0x14009a10a  test    r9d, r9d
0x14009a10d  jz      short loc_14009A12A
0x14009a10f  mov     rax, [rsi+30h]
0x14009a113  mov     ecx, edx
0x14009a115  inc     edx
0x14009a117  add     rcx, rcx
0x14009a11a  mov     [rax+rcx*8], r11
0x14009a11e  mov     [rax+rcx*8+8], r11
0x14009a123  cmp     edx, r9d
0x14009a126  jb      short loc_14009A10F
0x14009a128  mov     ecx, [rsi]
0x14009a12a  mov     r11d, [rbp+0C0h+var_12C]
0x14009a12e  mov     [rbp+0C0h+var_11C], r11d
0x14009a132  mov     [rbp+0C0h+var_140], 1
0x14009a136  mov     r14, [rbp+0C0h+var_98]
0x14009a13a  mov     r8, [r12+20h]
0x14009a13f  mov     rdx, [r12+28h]
0x14009a144  not     r8
0x14009a147  and     r8, r14
0x14009a14a  mov     [rbp+0C0h+var_118], r14
0x14009a14e  add     rdx, r8
0x14009a151  mov     [rbp+0C0h+var_A0], r8
0x14009a155  mov     [rbp+0C0h+var_90], rdx
0x14009a159  mov     [rbp+0C0h+var_D0], rdx
0x14009a15d  test    cl, 20h
0x14009a160  jz      short loc_14009A176
0x14009a162  cmp     byte ptr [r15+4Eh], 0
0x14009a167  jz      short loc_14009A176
0x14009a169  cmp     byte ptr [r15+4Ch], 0
0x14009a16e  cmovnz  r10d, r11d
0x14009a172  mov     [rbp+0C0h+var_100], r10d
0x14009a176  xor     eax, eax
0x14009a178  mov     [rbp+0C0h+var_13C], eax
0x14009a17b  cmp     r9d, r11d
0x14009a17e  jnb     loc_14009AB4D
0x14009a184  xor     cl, cl
0x14009a186  lea     edi, [r9+r10]
0x14009a18a  mov     r10d, edi
0x14009a18d  mov     [rbp+0C0h+var_130], ecx
0x14009a190  mov     [rbp+0C0h+arg_0], cl
0x14009a196  mov     [rbp+0C0h+arg_10], cl
0x14009a19c  mov     [rbp+0C0h+var_120], edi
0x14009a19f  mov     [rbp+0C0h+var_138], edi
0x14009a1a2  cmp     [r15+4Fh], cl
0x14009a1a6  jz      short loc_14009A1C5
0x14009a1a8  mov     eax, [rsi]
0x14009a1aa  test    al, 20h
0x14009a1ac  jz      short loc_14009A1C5
0x14009a1ae  lea     r10d, [rdi+r11]
0x14009a1b2  cmp     edi, r9d
0x14009a1b5  jz      short loc_14009A1BA
0x14009a1b7  mov     r10d, r9d
0x14009a1ba  mov     [rbp+0C0h+var_138], r10d
0x14009a1be  mov     [rbp+0C0h+arg_10], 1
0x14009a1c5  mov     rax, [rbp+0C0h+var_78]
0x14009a1c9  cmp     rdx, rax
0x14009a1cc  jb      short loc_14009A1D9
0x14009a1ce  mov     rdx, rax
0x14009a1d1  mov     [rbp+0C0h+var_D0], rax
0x14009a1d5  mov     [rbp+0C0h+var_134], 1
0x14009a1d9  mov     r11, rdx
0x14009a1dc  mov     rdx, [r15]
0x14009a1df  sub     r11, r14
0x14009a1e2  mov     [rbp+0C0h+var_108], r11
0x14009a1e6  test    dl, 1
0x14009a1e9  jnz     short loc_14009A20A
0x14009a1eb  mov     rcx, [rsi+30h]
0x14009a1ef  mov     eax, edi
0x14009a1f1  add     rax, rax
0x14009a1f4  test    byte ptr [rcx+rax*8], 1
0x14009a1f8  jnz     short loc_14009A20A
0x14009a1fa  mov     eax, r10d
0x14009a1fd  add     rax, rax
0x14009a200  test    byte ptr [rcx+rax*8], 1
0x14009a204  jz      loc_14009AA9B
0x14009a20a  test    dl, 2
0x14009a20d  jz      short loc_14009A24F
0x14009a20f  mov     rcx, [rsi+30h]
0x14009a213  mov     eax, edi
0x14009a215  add     rax, rax
0x14009a218  test    byte ptr [rcx+rax*8], 2
0x14009a21c  jz      short loc_14009A222
0x14009a21e  mov     eax, edi
0x14009a220  jmp     short loc_14009A23A
0x14009a222  cmp     [rbp+0C0h+arg_10], 0
0x14009a229  jz      short loc_14009A24F
0x14009a22b  mov     eax, r10d
0x14009a22e  add     rax, rax
0x14009a231  test    byte ptr [rcx+rax*8], 2
0x14009a235  jz      short loc_14009A24F
0x14009a237  mov     eax, r10d
0x14009a23a  cmp     eax, 0FFFFFFFFh
0x14009a23d  jz      short loc_14009A24F
0x14009a23f  shl     rax, 4
0x14009a243  xor     dl, [rax+rcx]
0x14009a246  test    dl, 8
0x14009a249  jz      loc_14009AA9B
0x14009a24f  cmp     [r12+28h], r11
0x14009a254  ja      loc_14009A315
0x14009a25a  mov     eax, [r13+98h]
0x14009a261  test    al, 4
0x14009a263  jnz     loc_14009A315
0x14009a269  lea     rax, [r15+54h]
0x14009a26d  mov     r9, r15; struct COMMIT_VA_STATE *
0x14009a270  mov     [rsp+1D0h+var_180], rax; bool *
0x14009a275  mov     rdx, r13; struct CVirtualAddressAllocator *
0x14009a278  lea     rax, [rbp+0C0h+arg_0]
0x14009a27f  mov     rcx, rsi; this
0x14009a282  mov     [rsp+1D0h+var_188], rax; bool *
0x14009a287  mov     rax, [rbp+0C0h+arg_38]
0x14009a28e  mov     qword ptr [rsp+1D0h+var_190], rax; unsigned __int64
0x14009a293  mov     rax, qword ptr [rbp+0C0h+var_B0]
0x14009a297  mov     dword ptr [rsp+1D0h+var_1A0], r10d; unsigned int
0x14009a29c  mov     dword ptr [rsp+1D0h+var_1A8], edi; unsigned int
0x14009a2a0  mov     [rsp+1D0h+var_1B0], r12; struct VIDMM_PAGE_TABLE_LEVEL_DESC *
0x14009a2a5  mov     r8, [rax+548h]; struct _DXGK_GPUMMUCAPS *
0x14009a2ac  call    ?HandleFullPageTableCoverage@VIDMM_PAGE_DIRECTORY@@QEAA_NPEAVCVirtualAddressAllocator@@PEBU_DXGK_GPUMMUCAPS@@PEBUCOMMIT_VA_STATE@@PEBUVIDMM_PAGE_TABLE_LEVEL_DESC@@III_KPEA_N5@Z; VIDMM_PAGE_DIRECTORY::HandleFullPageTableCoverage(CVirtualAddressAllocator *,_DXGK_GPUMMUCAPS const *,COMMIT_VA_STATE const *,VIDMM_PAGE_TABLE_LEVEL_DESC const *,uint,uint,uint,unsigned __int64,bool *,bool *)
0x14009a2b1  test    al, al
0x14009a2b3  jz      short loc_14009A304
0x14009a2b5  mov     rax, [rsi+30h]
0x14009a2b9  mov     ecx, edi
0x14009a2bb  add     rcx, rcx
0x14009a2be  mov     ecx, [rax+rcx*8]
0x14009a2c1  bt      rcx, 0Ah
0x14009a2c6  jnb     short loc_14009A2EE
0x14009a2c8  mov     r8, [r15+30h]
0x14009a2cc  mov     r9d, [r15+38h]
0x14009a2d0  mov     rdx, r8
0x14009a2d3  mov     ecx, r9d
0x14009a2d6  call    ?GetVidMmGlobalAllocFromOwner@@YAPEAUVIDMM_GLOBAL_ALLOC@@W4VIDMM_VAD_OWNER_TYPE@@PEAX@Z; GetVidMmGlobalAllocFromOwner(VIDMM_VAD_OWNER_TYPE,void *)
0x14009a2db  mov     rdx, r8
0x14009a2de  mov     [rbp+0C0h+var_88], rax
0x14009a2e2  mov     ecx, r9d
0x14009a2e5  call    ?GetVidMmAllocFromOwner@@YAPEAUVIDMM_ALLOC@@W4VIDMM_VAD_OWNER_TYPE@@PEAX@Z; GetVidMmAllocFromOwner(VIDMM_VAD_OWNER_TYPE,void *)
0x14009a2ea  mov     [rbp+0C0h+var_80], rax
0x14009a2ee  mov     r9b, [rbp+0C0h+arg_0]
0x14009a2f5  mov     r11d, 1
0x14009a2fb  mov     [rbp+0C0h+var_133], r11b
0x14009a2ff  jmp     loc_14009A964
0x14009a304  mov     cl, [rbp+0C0h+arg_0]
0x14009a30a  mov     r8, [rbp+0C0h+var_A0]
  ... truncated ...
```
