# CmsRangeAndCountMap::AddEntry(CmsTransactionCore *,_RANGE const *,unsigned __int64 *,uchar *)

- ea: `0x140049760`
- end: `0x14004af65`
- name: `?AddEntry@CmsRangeAndCountMap@@QEAAXPEAVCmsTransactionCore@@PEBU_RANGE@@PEA_KPEAE@Z`
- size: `6149`
- prototype: `void(CmsRangeAndCountMap *__hidden this, struct CmsTransactionCore *, const struct _RANGE *, unsigned __int64 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x1400ad300`

## callees

- `0x14003bf40`
- `0x14004802c`
- `0x140048f50`
- `0x140049050`
- `0x140049760`
- `0x14004b5b0`
- `0x14004b8d0`
- `0x14004c580`
- `0x140072520`
- `0x140072820`
- `0x140072880`
- `0x14007ab30`
- `0x1400a8210`
- `0x1400cd694`
- `0x1400ceda0`
- `0x140169b0c`
- `0x14017c950`
- `0x1401f3fb0`
- `0x1401f4090`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004a8a0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004a8a0`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004addb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004ae17`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004ae53`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004ae8f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004addb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004ae17`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004ae53`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004ae8f`
- `ntoskrnl!ExAllocatePool2` at `0x140049cb7`
- `ntoskrnl!ExAllocatePool2` at `0x140049dc6`
- `ntoskrnl!ExAllocatePool2` at `0x140049e39`
- `ntoskrnl!ExAllocatePool2` at `0x140049f1a`
- `ntoskrnl!ExAllocatePool2` at `0x140049f6e`
- `ntoskrnl!ExAllocatePool2` at `0x140049fe1`
- `ntoskrnl!ExAllocatePool2` at `0x140049cb7`
- `ntoskrnl!ExAllocatePool2` at `0x140049dc6`
- `ntoskrnl!ExAllocatePool2` at `0x140049e39`
- `ntoskrnl!ExAllocatePool2` at `0x140049f1a`
- `ntoskrnl!ExAllocatePool2` at `0x140049f6e`
- `ntoskrnl!ExAllocatePool2` at `0x140049fe1`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140049c78`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140049d97`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140049edb`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140049f3f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140049c78`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140049d97`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140049edb`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140049f3f`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fd08c`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fd09e`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fd0bd`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fd0cf`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fd08c`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fd09e`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fd0bd`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fd0cf`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14004a84f`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14004a84f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fd1c2`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fd1c2`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14004adf8`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14004ae34`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14004ae70`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14004aeac`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14004adf8`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14004ae34`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14004ae70`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14004aeac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a608`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a7bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004af2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a608`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a7bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004af2b`

## string_xrefs

- `0x1401fd0b0`: `Lookaside list allocation must be double quad aligned.`
- `0x1401fd0e1`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
void __fastcall CmsRangeAndCountMap::AddEntry(
        CmsRangeAndCountMap *this,
        struct CmsTransactionCore *a2,
        const struct _RANGE *a3,
        unsigned __int64 *a4)
{
  __int128 v4; // xmm8
  struct CmsTransactionCore *v5; // r12
  const struct _RANGE *v7; // rsi
  CmsRangeAndCountMap *v8; // rdx
  __m128i v9; // xmm9
  __int128 v10; // xmm0
  CmsAvlTableLite *v11; // r8
  __int64 v12; // r11
  bool v13; // zf
  unsigned __int64 v14; // r11
  __int64 v15; // r9
  int v16; // r14d
  int v17; // r12d
  int v18; // edi
  int v19; // esi
  int v20; // r13d
  int v21; // r15d
  int v22; // ebx
  __int64 v23; // r10
  struct _RTL_AVL_ENTRY *v24; // rax
  int v25; // eax
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // rbx
  unsigned __int64 v28; // rbx
  __int64 v29; // r14
  unsigned __int64 v30; // r15
  __int64 v31; // rcx
  unsigned __int64 v32; // r14
  char *v33; // rcx
  __int64 v34; // rcx
  unsigned __int64 v35; // r10
  __int128 v36; // xmm7
  __m128i v37; // xmm6
  unsigned __int64 v38; // rdx
  __m128i v39; // xmm0
  __int64 v40; // rax
  __int16 v41; // bx
  __int64 v42; // rdi
  __int64 v43; // r9
  __int64 v44; // rdx
  __int64 v45; // rax
  unsigned int v46; // r8d
  __m256i *Pool2; // rcx
  struct _RTL_AVL_ENTRY *v48; // rcx
  _QWORD *v49; // rcx
  int v50; // edx
  __int64 v51; // rdx
  struct _RTL_AVL_ENTRY *v52; // rdx
  struct _RTL_AVL_ENTRY *v53; // r9
  __int64 v54; // rdi
  __int64 v55; // rdx
  __int64 v56; // rax
  int v57; // ecx
  __int64 i; // rdx
  __int8 *v59; // rax
  __int64 v60; // rsi
  __int64 v61; // r9
  __int64 v62; // rdx
  __int64 v63; // rax
  __int64 v64; // rcx
  __int64 v65; // r9
  __int64 v66; // rbx
  __int64 v67; // rdx
  __int64 v68; // rax
  int v69; // ecx
  __int64 v70; // xmm1_8
  CmsRangeAndCountMap *v71; // rbx
  __int64 v72; // rax
  __int64 v73; // rax
  __int64 v74; // rcx
  CmsAvlTableLite *v75; // rbx
  struct CmsTransactionCore *v76; // r10
  __int128 v77; // xmm1
  unsigned int v78; // ecx
  unsigned int v79; // eax
  __int64 v80; // rcx
  __int64 v81; // rax
  char *v82; // rcx
  char *v83; // rcx
  __int64 v84; // r14
  __int64 v85; // rcx
  __int64 v86; // rax
  __int64 v87; // rdx
  __int64 v88; // rax
  int v89; // eax
  __int64 v90; // rax
  struct _RTL_AVL_ENTRY *v91; // xmm0_8
  char *v92; // rcx
  unsigned __int64 *v93; // rdx
  unsigned __int64 v94; // rcx
  int v95; // ecx
  unsigned __int64 v96; // r9
  unsigned __int64 v97; // r10
  unsigned __int64 v98; // r8
  unsigned __int64 v99; // rdx
  unsigned __int64 v100; // rcx
  char *v101; // rcx
  struct _RTL_AVL_ENTRY *v102; // rcx
  struct _RTL_AVL_ENTRY *v103; // rdx
  struct _MS_AVL_TABLE *v104; // rcx
  int v105; // ecx
  __int64 v106; // r9
  __int64 v107; // rsi
  unsigned __int8 v108; // dl
  CmsAvlTableLite *v109; // r15
  unsigned __int8 v110; // cl
  int v111; // r12d
  __int64 v112; // rax
  __int64 v113; // r13
  int v114; // edi
  __int64 v115; // rax
  __int64 v116; // rcx
  _WORD *v117; // rcx
  __int64 v118; // rbx
  struct _SLIST_ENTRY *v119; // r8
  struct _NPAGED_LOOKASIDE_LIST *v120; // rcx
  _OWORD *v121; // rax
  __int64 v122; // rbx
  char *v123; // rcx
  char *v124; // rcx
  __int64 v125; // rcx
  CmsAvlTableLite *v126; // rsi
  __int64 v127; // rax
  __int64 v128; // rcx
  __int64 v129; // rax
  __int64 v130; // rdx
  int v131; // eax
  int v132; // eax
  __int64 v133; // r14
  unsigned __int64 v134; // r15
  __int64 v135; // rcx
  unsigned __int64 v136; // r14
  unsigned __int64 v137; // rdx
  unsigned __int64 v138; // rax
  unsigned __int64 v139; // rdx
  unsigned __int64 v140; // rax
  struct _NPAGED_LOOKASIDE_LIST *v141; // rcx
  __m256i *v142; // rax
  struct _NPAGED_LOOKASIDE_LIST *v143; // rcx
  __m256i *v144; // rax
  struct _NPAGED_LOOKASIDE_LIST *v145; // rcx
  void *v146; // rax
  struct _NPAGED_LOOKASIDE_LIST *v147; // rcx
  void *v148; // rax
  __int64 v149; // rcx
  unsigned __int8 *LeftmostNodeAvlFull; // rax
  CmsRangeAndCountMap *v151; // r10
  __int64 v152; // rdx
  __int64 v153; // rax
  unsigned __int64 *v154; // r8
  char v155; // cl
  char v156; // al
  char v157; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v158; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v159; // [rsp+60h] [rbp-A0h]
  __m128i v160; // [rsp+68h] [rbp-98h] BYREF
  __int128 v161; // [rsp+78h] [rbp-88h]
  struct CmsTransactionCore *v162; // [rsp+88h] [rbp-78h]
  unsigned __int64 v163; // [rsp+90h] [rbp-70h] BYREF
  CmsRangeAndCountMap *v164; // [rsp+98h] [rbp-68h]
  unsigned __int64 v165; // [rsp+A0h] [rbp-60h]
  __int128 v166; // [rsp+A8h] [rbp-58h]
  CmsAvlTableLite *v167; // [rsp+B8h] [rbp-48h]
  __int64 v168; // [rsp+C0h] [rbp-40h] BYREF
  struct _RTL_AVL_ENTRY *v169[2]; // [rsp+C8h] [rbp-38h] BYREF
  int v170; // [rsp+D8h] [rbp-28h]
  __int64 v171; // [rsp+E0h] [rbp-20h]
  _BYTE v172[24]; // [rsp+E8h] [rbp-18h] BYREF
  __m256i v173; // [rsp+100h] [rbp+0h] BYREF
  __int128 v174; // [rsp+120h] [rbp+20h] BYREF
  __m128i v175; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v176[24]; // [rsp+140h] [rbp+40h]
  __int64 v177; // [rsp+158h] [rbp+58h] BYREF
  __int128 v178; // [rsp+160h] [rbp+60h] BYREF
  int v179; // [rsp+170h] [rbp+70h]
  __int128 v180; // [rsp+178h] [rbp+78h]
  CmsAvlTableLite *v181; // [rsp+188h] [rbp+88h] BYREF
  __int128 v182; // [rsp+190h] [rbp+90h]
  __int128 v183; // [rsp+1B0h] [rbp+B0h]
  __m128i v184; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 v185; // [rsp+1D0h] [rbp+D0h]
  __int128 v186; // [rsp+1E0h] [rbp+E0h] BYREF
  int v187; // [rsp+1F0h] [rbp+F0h]
  int v188; // [rsp+1F4h] [rbp+F4h]
  unsigned __int64 *v189; // [rsp+1F8h] [rbp+F8h]
  PVOID P; // [rsp+200h] [rbp+100h]
  char v191; // [rsp+208h] [rbp+108h]
  int v192; // [rsp+20Ch] [rbp+10Ch]
  _BYTE v193[32]; // [rsp+210h] [rbp+110h] BYREF

  v162 = a2;
  v4 = 0;
  v5 = a2;
  v7 = a3;
  v8 = this;
  *(_QWORD *)&v174 = a3;
  v9 = 0;
  v164 = this;
  v181 = 0;
  v182 = 0;
  v158 = 0;
  v10 = *(_OWORD *)a3;
  v159 = 0;
  v183 = 0;
  v160.m128i_i64[0] = 0;
  v166 = v10;
  v177 = 0;
  v179 = 0;
  v161 = 0;
  *(_DWORD *)v176 = 0;
  v178 = 0;
  v175 = 0;
  v184 = 0;
  v185 = 0;
  v180 = 0;
  *(_OWORD *)&v176[8] = 0;
  if ( !*((_DWORD *)this + 4) || *(_DWORD *)(*((_QWORD *)this + 1) + 32LL) < *((_DWORD *)this + 4) )
    goto LABEL_2;
  v27 = *(_QWORD *)a3;
  if ( !*(_QWORD *)a3 )
    goto LABEL_14;
  v133 = *(_QWORD *)this;
  v134 = v27 - 1;
  v187 = 0;
  v189 = 0;
  P = 0;
  v191 = 0;
  v192 = 0;
  v186 = 0;
  CmsRowWithBuffer::Reset((CmsRowWithBuffer *)&v186);
  v170 = 0;
  v171 = 0;
  *(_QWORD *)&v172[16] = 0;
  *(_QWORD *)v172 = v27 - 1;
  *(_QWORD *)&v172[8] = 1;
  *(_OWORD *)v169 = 0;
  memset(&v173, 0, sizeof(v173));
  SetRangeMapEntryRowHlpr((struct _CmsRow *)v169, (struct SmsRangeMapEntry *)v172, 0);
  if ( CmsAvlTableLite::PinInIndexEx(
         (CmsAvlTableLite *)(v133 + 8),
         v5,
         (const struct SmsInternalPropertyDef *)&CmsRangeMap::PropertyDef,
         (struct _CmsRow *)v169,
         (struct _CmsRow *)&v186,
         (struct _SmsQuickIndex *)&v173) )
  {
    v136 = -1;
    if ( !(unsigned int)CmsAvlTableLite::PinNextInIndex(v135, 1, &v186, 0, &v173) )
      v136 = *v189;
    v158 = v27 - 1;
    v159 = 1;
    if ( v136 < v27 )
      v159 = v136 - v134;
    CmsRowWithBuffer::Reset((CmsRowWithBuffer *)&v186);
    v8 = v164;
LABEL_14:
    v28 = *((_QWORD *)v7 + 1) + *(_QWORD *)v7;
    if ( v28 != -1 )
    {
      v29 = *(_QWORD *)v8;
      v187 = 0;
      v186 = 0;
      v189 = 0;
      P = 0;
      v191 = 0;
      v192 = 0;
      CmsRowWithBuffer::Reset((CmsRowWithBuffer *)&v186);
      v170 = 0;
      v171 = 0;
      *(_QWORD *)&v172[16] = 0;
      *(_QWORD *)v172 = v28;
      *(_QWORD *)&v172[8] = 1;
      *(_OWORD *)v169 = 0;
      v30 = v28 + 1;
      memset(&v173, 0, sizeof(v173));
      SetRangeMapEntryRowHlpr((struct _CmsRow *)v169, (struct SmsRangeMapEntry *)v172, 0);
      if ( !CmsAvlTableLite::PinInIndexEx(
              (CmsAvlTableLite *)(v29 + 8),
              v5,
              (const struct SmsInternalPropertyDef *)&CmsRangeMap::PropertyDef,
              (struct _CmsRow *)v169,
              (struct _CmsRow *)&v186,
              (struct _SmsQuickIndex *)&v173) )
      {
        v139 = *v189 + v189[1];
        v159 = 1;
        v140 = v189[2];
        v158 = v140;
        if ( !*(_BYTE *)(v29 + 56) )
          v158 = v28 + v140 - *v189;
        if ( v30 > v139 )
          v159 = v139 - v28;
        CmsRowWithBuffer::Reset((CmsRowWithBuffer *)&v186);
        v8 = v164;
        goto LABEL_2;
      }
      v32 = -1;
      if ( !(unsigned int)CmsAvlTableLite::PinNextInIndex(v31, 1, &v186, 0, &v173) )
        v32 = *v189;
      v158 = v28;
      v159 = 1;
      if ( v32 < v30 )
        v159 = v32 - v28;
      CmsRowWithBuffer::Reset((CmsRowWithBuffer *)&v186);
    }
    LeftmostNodeAvlFull = (unsigned __int8 *)MsFindLeftmostNodeAvlFull(*((struct _MS_AVL_TABLE **)v164 + 1), v169);
    if ( !LeftmostNodeAvlFull )
      return;
    v152 = LeftmostNodeAvlFull[26];
    v158 = *(_QWORD *)&LeftmostNodeAvlFull[v152];
    v159 = *(_QWORD *)&LeftmostNodeAvlFull[v152 + 8];
    if ( v159 >= *((_QWORD *)v7 + 1) )
      return;
    v160.m128i_i64[0] = (__int64)LeftmostNodeAvlFull;
    v160.m128i_i64[1] = (__int64)LeftmostNodeAvlFull;
    LODWORD(v161) = 1;
    CmsRangeAndCountMap::DeleteEntry(v151, v5, (struct _RANGE *)&v158, 0, (struct _SmsQuickIndex *)&v160);
    goto LABEL_220;
  }
  v137 = *v189 + v189[1];
  v159 = 1;
  v138 = v189[2];
  v158 = v138;
  if ( !*(_BYTE *)(v133 + 56) )
    v158 = v134 + v138 - *v189;
  if ( v27 > v137 )
  {
    v159 = v137 - v134;
    CmsRowWithBuffer::Reset((CmsRowWithBuffer *)&v186);
    v8 = v164;
    goto LABEL_2;
  }
  CmsRowWithBuffer::Reset((CmsRowWithBuffer *)&v186);
LABEL_220:
  v8 = v164;
LABEL_2:
  v157 = 1;
  if ( a4 )
    ++*a4;
  v11 = *(CmsAvlTableLite **)v7;
  v12 = *((_QWORD *)v7 + 1);
  v167 = v11;
  if ( v11 )
  {
    v11 = (CmsAvlTableLite *)((char *)v11 - 1);
    v167 = v11;
    ++v12;
  }
  v13 = v12 == -1;
  v14 = v12 + 1;
  v165 = v14;
  v15 = 24;
  if ( v13 )
    goto LABEL_34;
  v16 = DWORD1(v166);
  v17 = DWORD1(v166);
  v18 = DWORD1(v166);
  v19 = DWORD1(v166);
  v20 = DWORD1(v166);
  v21 = DWORD1(v166);
  v22 = DWORD1(v166);
  while ( 2 )
  {
    v23 = *(_QWORD *)v8;
    P = v193;
    *(_OWORD *)v169 = 0;
    v173.m256i_i32[4] = 24;
    LODWORD(v186) = 0;
    DWORD1(v186) = (unsigned __int16)_mm_extract_epi16((__m128i)0LL, 2);
    *(_QWORD *)&v172[16] = 0;
    v173.m256i_i64[1] = (__int64)v172;
    *((_QWORD *)&v186 + 1) = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    v173.m256i_i64[3] = (__int64)v172;
    v168 = v23;
    v192 = 32;
    v187 = 0;
    v188 = v16;
    v189 = 0;
    v191 = 0;
    v173.m256i_i64[0] = 16;
    v163 = (unsigned __int64)v11 + v14;
    *(_QWORD *)v172 = v11;
    *(_QWORD *)&v172[8] = v14;
    v160 = 0;
    v161 = 0;
    if ( v9.m128i_i64[0] )
    {
      v91 = (struct _RTL_AVL_ENTRY *)_mm_srli_si128(v9, 8).m128i_u64[0];
      v24 = v91;
      if ( v91 )
      {
        v37 = v9;
        v36 = v4;
        if ( (CmsAvlTableLite *)(*(_QWORD *)(*(unsigned __int8 *)(v9.m128i_i64[0] + 26) + v9.m128i_i64[0])
                               + *(_QWORD *)(*(unsigned __int8 *)(v9.m128i_i64[0] + 26) + v9.m128i_i64[0] + 8)) == v11 )
        {
          v160 = v9;
          v161 = v4;
          if ( (((_DWORD)v183 - 1) & 0xFFFFFFFD) == 0 )
          {
            v24 = RealSuccessor(v91);
            if ( !v24 )
            {
              v160.m128i_i64[1] = 0;
              v37 = (__m128i)v160.m128i_u64[0];
              v158 = (unsigned __int64)v11;
              v159 = v14;
              v9 = (__m128i)v160.m128i_u64[0];
              v183 = v4;
              CmsRowWithBuffer::Reset((CmsRowWithBuffer *)&v186);
              v15 = v159;
              v35 = v158;
              v11 = v167;
              v14 = v165;
              v38 = v163;
              goto LABEL_30;
            }
          }
          v35 = (unsigned __int64)v11;
          LODWORD(v186) = *((unsigned __int8 *)v24 + 27);
          v15 = v14;
          v92 = (char *)v24 + *((unsigned __int8 *)v24 + 26);
          LODWORD(v161) = 1;
          v36 = v161;
          *((_QWORD *)&v186 + 1) = v92;
          WORD2(v186) = 0;
          v4 = v161;
          v187 = *((unsigned __int16 *)v24 + 15);
          v93 = (unsigned __int64 *)((char *)v24 + *((unsigned __int8 *)v24 + 26));
          v160.m128i_i64[1] = (__int64)v24;
          v160.m128i_i64[0] = (__int64)v24;
          v37 = v160;
          v189 = v93;
          v158 = (unsigned __int64)v11;
          v159 = v14;
          v9 = v160;
          v94 = *v93;
          v183 = v161;
          if ( (CmsAvlTableLite *)v94 != v11 )
          {
            v38 = v163;
            if ( v94 < v163 )
            {
              v15 = v94 - (_QWORD)v11;
              v159 = v94 - (_QWORD)v11;
            }
            v188 = v17;
            P = v193;
            v39 = 0;
            *(_OWORD *)v169 = 0;
            DWORD1(v186) = (unsigned __int16)_mm_extract_epi16((__m128i)0LL, 2);
            v187 = 0;
            v189 = 0;
            v191 = 0;
            goto LABEL_28;
          }
        }
        else
        {
          LODWORD(v186) = *(unsigned __int8 *)(v9.m128i_i64[0] + 27);
          *((_QWORD *)&v186 + 1) = v9.m128i_i64[0] + *(unsigned __int8 *)(v9.m128i_i64[0] + 26);
          WORD2(v186) = 0;
          v187 = *(unsigned __int16 *)(v9.m128i_i64[0] + 30);
          v24 = (struct _RTL_AVL_ENTRY *)v9.m128i_i64[0];
          v93 = (unsigned __int64 *)(v9.m128i_i64[0] + *(unsigned __int8 *)(v9.m128i_i64[0] + 26));
LABEL_116:
          v189 = v93;
        }
        v96 = v93[1];
        v97 = v96 + *v93;
        v159 = v96;
        v98 = v93[2];
        v158 = v98;
        if ( !*(_BYTE *)(v168 + 56) )
        {
          v98 = *v93;
          v158 = *v93;
        }
        v9 = v37;
        v4 = v36;
        *(_OWORD *)v169 = 0;
        v183 = v36;
        if ( v163 > v97 )
        {
          v96 = v97 - *v93;
          v159 = v96;
          v188 = v20;
        }
        else
        {
          v188 = v19;
        }
        v99 = *((_QWORD *)&v166 + 1);
        P = v193;
        LODWORD(v186) = 0;
        v191 = 0;
        WORD2(v186) = _mm_extract_epi16((__m128i)0LL, 2);
        WORD3(v186) = HIWORD(v169[0]);
        v100 = v166;
        v189 = 0;
        v187 = 0;
        *((_QWORD *)&v186 + 1) = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        v192 = 32;
        if ( v98 < (unsigned __int64)v166 )
        {
          v99 = v166 - v98 + *((_QWORD *)&v166 + 1);
          v100 = v98;
          *(_QWORD *)&v166 = v98;
          *((_QWORD *)&v166 + 1) = v99;
        }
        if ( v98 + v96 > v99 + v100 )
          *((_QWORD *)&v166 + 1) = v98 + v96 - v100;
        if ( v24 )
          v101 = (char *)v24 + *((unsigned __int8 *)v24 + 26);
        else
          v101 = 0;
        v102 = (struct _RTL_AVL_ENTRY *)*((_QWORD *)v101 + 3);
        P = v193;
        v103 = v102;
        v169[0] = v102;
        v160.m128i_i64[1] = (__int64)&v158;
        v168 = *((_QWORD *)v164 + 1);
        v104 = (struct _MS_AVL_TABLE *)v168;
        v160.m128i_i64[0] = 16;
        v192 = 32;
        ++*(_DWORD *)(v168 + 36);
        v186 = 0;
        v187 = 0;
        v188 = v21;
        v189 = 0;
        v191 = 0;
        *((_QWORD *)&v161 + 1) = &v158;
        LODWORD(v161) = 16;
        DeleteNodeFromTree(v104, v103, 1u);
        --*(_DWORD *)(v168 + 32);
        CmsAvlTableLite::FreeIndexEntry(v169[0]);
        ++*(_DWORD *)(v168 + 40);
        if ( (v191 & 1) != 0 && P )
          ExFreePoolWithTag(P, 0);
        v15 = v159;
        v35 = v158;
        v11 = v167;
        v14 = v165;
        v38 = v163;
        P = v193;
        v187 = 0;
        v189 = 0;
        v191 = 0;
        v186 = 0;
        v188 = v22;
        goto LABEL_29;
      }
    }
    v24 = *(struct _RTL_AVL_ENTRY **)(v23 + 24);
    if ( !v24 )
    {
      v160.m128i_i64[0] = 0;
      LODWORD(v161) = 0;
      v25 = *(_DWORD *)(v23 + 48);
      v165 = (unsigned __int64)v11 + v14;
      v26 = -1;
      DWORD1(v161) = v25;
      goto LABEL_11;
    }
    while ( 1 )
    {
      v49 = (_QWORD *)((char *)v24 + *((unsigned __int8 *)v24 + 26));
      if ( (unsigned __int64)v11 >= *v49 )
        break;
      v48 = (struct _RTL_AVL_ENTRY *)*((_QWORD *)v24 + 1);
      if ( !v48 )
      {
        v50 = 2;
        LODWORD(v161) = 2;
        goto LABEL_49;
      }
LABEL_44:
      v24 = v48;
    }
    if ( (unsigned __int64)v11 < v49[1] + *v49 )
    {
      v160.m128i_i64[0] = (__int64)v24;
      LODWORD(v161) = 1;
      v160.m128i_i64[1] = (__int64)v24;
      v37 = v160;
      LODWORD(v186) = *((unsigned __int8 *)v24 + 27);
      *((_QWORD *)&v186 + 1) = (char *)v24 + *((unsigned __int8 *)v24 + 26);
      WORD2(v186) = 0;
      v187 = *((unsigned __int16 *)v24 + 15);
      v93 = (unsigned __int64 *)((char *)v24 + *((unsigned __int8 *)v24 + 26));
      DWORD1(v161) = *(_DWORD *)(v23 + 48);
      v36 = v161;
      goto LABEL_116;
    }
    v48 = (struct _RTL_AVL_ENTRY *)*((_QWORD *)v24 + 2);
    if ( v48 )
      goto LABEL_44;
    v50 = 3;
    LODWORD(v161) = 3;
LABEL_49:
    DWORD1(v161) = *(_DWORD *)(v23 + 48);
    v165 = v163;
    v26 = -1;
    v160.m128i_i64[1] = (__int64)v24;
    v160.m128i_i64[0] = 0;
    if ( v50 != 3 )
      goto LABEL_24;
    v51 = *((_QWORD *)v24 + 2);
    if ( v51 )
    {
      for ( ; *(_QWORD *)(v51 + 8); v51 = *(_QWORD *)(v51 + 8) )
        ;
      v24 = (struct _RTL_AVL_ENTRY *)v51;
    }
    else
    {
      v52 = *(struct _RTL_AVL_ENTRY **)v24;
      if ( *(struct _RTL_AVL_ENTRY **)(*(_QWORD *)v24 + 16LL) == v24 )
      {
        do
        {
          v53 = *(struct _RTL_AVL_ENTRY **)v52;
          v24 = v52;
          v52 = v53;
        }
        while ( *((struct _RTL_AVL_ENTRY **)v53 + 2) == v24 );
      }
      else
      {
        v53 = *(struct _RTL_AVL_ENTRY **)v24;
      }
      v24 = *((struct _RTL_AVL_ENTRY **)v53 + 1) == v24 ? v53 : 0LL;
    }
    if ( v24 )
    {
LABEL_24:
      LODWORD(v186) = *((unsigned __int8 *)v24 + 27);
      v33 = (char *)v24 + *((unsigned __int8 *)v24 + 26);
      LODWORD(v161) = 1;
      *((_QWORD *)&v186 + 1) = v33;
      WORD2(v186) = 0;
      v187 = *((unsigned __int16 *)v24 + 15);
      v34 = *((unsigned __int8 *)v24 + 26);
      v160.m128i_i64[1] = (__int64)v24;
      v189 = (unsigned __int64 *)((char *)v24 + v34);
      v160.m128i_i64[0] = (__int64)v24;
      v26 = *(_QWORD *)((char *)v24 + v34);
      goto LABEL_25;
    }
LABEL_11:
    v160.m128i_i64[1] = 0;
LABEL_25:
    v158 = (unsigned __int64)v11;
    v35 = (unsigned __int64)v11;
    v159 = v14;
    v15 = v14;
    v36 = v161;
    v37 = v160;
    v4 = v161;
    v9 = v160;
    v183 = v161;
    if ( v26 < v165 )
    {
      v15 = v26 - (_QWORD)v11;
      v159 = v26 - (_QWORD)v11;
    }
    v38 = v163;
    v39 = 0;
    P = v193;
    *(_OWORD *)v169 = 0;
    v187 = 0;
    v188 = v18;
    DWORD1(v186) = (unsigned __int16)_mm_extract_epi16((__m128i)0LL, 2);
    v189 = 0;
    v191 = 0;
LABEL_28:
    LODWORD(v186) = v39.m128i_i32[0];
    *((_QWORD *)&v186 + 1) = _mm_srli_si128(v39, 8).m128i_u64[0];
LABEL_29:
    v192 = 32;
LABEL_30:
    if ( v157 )
    {
      v184 = v37;
      v157 = 0;
      v185 = v36;
    }
    if ( v38 > v35 + v15 )
    {
      if ( (unsigned __int64)v11 <= v35 )
        v14 = v38 - (v35 + v15);
      else
        v14 += (unsigned __int64)v11 - v35 - v15;
      v165 = v14;
      v11 = (CmsAvlTableLite *)(v35 + v15);
      v167 = (CmsAvlTableLite *)(v35 + v15);
      v15 = 24;
      if ( v14 )
      {
        v8 = v164;
        continue;
      }
    }
    break;
  }
  v7 = (const struct _RANGE *)v174;
  v5 = v162;
LABEL_34:
  v40 = *((_QWORD *)v7 + 1);
  v181 = *(CmsAvlTableLite **)v7;
  *(_QWORD *)&v182 = v40;
  *((_QWORD *)&v182 + 1) = v181;
  memset(&v173, 0, 24);
  if ( CmsAvlTableLite::SizeOfAllocationsOnLookaside2 < 0x40 )
  {
    Pool2 = (__m256i *)ExAllocatePool2(66, 64, 1766871885, v15);
    if ( Pool2 )
    {
      v41 = 0x2000;
      LOWORD(i) = 0x8000;
      goto LABEL_66;
    }
    goto LABEL_212;
  }
  v41 = 0x2000;
  if ( CmsAvlTableLite::SizeOfAllocationsOnLookaside1 < 0x40 )
  {
    KeGetCurrentProcessorNumberEx(0);
    v54 = qword_140269460;
    if ( *(_DWORD *)qword_140269460 < 0x40u )
    {
      v54 = 0;
      v55 = 80;
      goto LABEL_56;
    }
    if ( !*(_BYTE *)(qword_140269460 + 8) )
    {
      if ( (int)*(_QWORD *)(qword_140269460 + 88) > (int)HIDWORD(*(_QWORD *)(qword_140269460 + 88)) )
      {
        v95 = _InterlockedDecrement((volatile signed __int32 *)(qword_140269460 + 88));
        if ( v95 >= *(_DWORD *)(v54 + 92) && v95 >= 0 )
        {
          v144 = (__m256i *)ExpInterlockedPopEntrySList((PSLIST_HEADER)(v54 + 64));
          goto LABEL_213;
        }
        _InterlockedIncrement((volatile signed __int32 *)(v54 + 88));
      }
LABEL_110:
      v55 = *(unsigned int *)(v54 + 4);
LABEL_56:
      v56 = ExAllocatePool2(66, v55, 1766871885, v43);
      Pool2 = (__m256i *)v56;
      if ( (v56 & 0xF) != 0 )
        goto LABEL_275;
      if ( !v56 )
        goto LABEL_215;
      goto LABEL_214;
    }
    v143 = (struct _NPAGED_LOOKASIDE_LIST *)(qword_140269460 + 64);
    if ( *(_BYTE *)(qword_140269460 + 9) )
      v144 = (__m256i *)ExAllocateFromNPagedLookasideList(v143);
    else
      v144 = (__m256i *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v143);
LABEL_213:
    Pool2 = v144;
    if ( v144 )
    {
LABEL_214:
      Pool2->m256i_i64[0] = v54;
      Pool2 = (__m256i *)((char *)Pool2 + 16);
LABEL_215:
      i = 0x4000;
      goto LABEL_194;
    }
    goto LABEL_110;
  }
  v42 = qword_140269458 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  if ( *(_DWORD *)v42 < 0x40u )
  {
    v42 = 0;
    v44 = 80;
    goto LABEL_38;
  }
  if ( !*(_BYTE *)(v42 + 8) )
  {
    if ( (int)*(_QWORD *)(v42 + 88) > (int)HIDWORD(*(_QWORD *)(v42 + 88)) )
    {
      v57 = _InterlockedDecrement((volatile signed __int32 *)(v42 + 88));
      if ( v57 >= *(_DWORD *)(v42 + 92) && v57 >= 0 )
      {
        v142 = (__m256i *)ExpInterlockedPopEntrySList((PSLIST_HEADER)(v42 + 64));
        goto LABEL_191;
      }
      _InterlockedIncrement((volatile signed __int32 *)(v42 + 88));
    }
LABEL_63:
    v44 = *(unsigned int *)(v42 + 4);
LABEL_38:
    v45 = ExAllocatePool2(66, v44, 1766871885, v43);
    Pool2 = (__m256i *)v45;
    if ( (v45 & 0xF) == 0 )
    {
      if ( v45 )
        goto LABEL_192;
      goto LABEL_193;
    }
LABEL_275:
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  }
  v141 = (struct _NPAGED_LOOKASIDE_LIST *)(v42 + 64);
  if ( *(_BYTE *)(v42 + 9) )
    v142 = (__m256i *)ExAllocateFromNPagedLookasideList(v141);
  else
    v142 = (__m256i *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v141);
LABEL_191:
  Pool2 = v142;
  if ( !v142 )
    goto LABEL_63;
LABEL_192:
  Pool2->m256i_i64[0] = v42;
  Pool2 = (__m256i *)((char *)Pool2 + 16);
LABEL_193:
  i = 0x2000;
LABEL_194:
  if ( !Pool2 )
    goto LABEL_212;
LABEL_66:
  Pool2->m256i_i16[14] = 0;
  *(_QWORD *)v172 = 0;
  Pool2[1] = v173;
  Pool2->m256i_i16[13] = 4128;
  Pool2->m256i_i16[14] = i;
  Pool2->m256i_i16[15] = 32;
  *((_QWORD *)&v180 + 1) = Pool2;
  LODWORD(v178) = Pool2->m256i_u8[27];
  v59 = &Pool2->m256i_i8[Pool2->m256i_u8[26]];
  WORD2(v178) = 0;
  *((_QWORD *)&v178 + 1) = v59;
  v179 = Pool2->m256i_u16[15];
  *(_QWORD *)&v180 = (char *)Pool2 + Pool2->m256i_u8[26];
  *(_OWORD *)&v172[8] = 0;
  if ( CmsAvlTableLite::SizeOfAllocationsOnLookaside2 < 0x38 )
  {
    v64 = ExAllocatePool2(66, 56, 1766871885, v43);
    if ( !v64 )
      goto LABEL_212;
    v41 = 0x8000;
    goto LABEL_85;
  }
  if ( CmsAvlTableLite::SizeOfAllocationsOnLookaside1 < 0x38 )
  {
    KeGetCurrentProcessorNumberEx(0);
    v66 = qword_140269460;
    if ( *(_DWORD *)qword_140269460 < 0x38u )
    {
      v66 = 0;
      v67 = 72;
      goto LABEL_75;
    }
    if ( !*(_BYTE *)(qword_140269460 + 8) )
    {
      if ( (int)*(_QWORD *)(qword_140269460 + 88) > (int)HIDWORD(*(_QWORD *)(qword_140269460 + 88)) )
      {
        v105 = _InterlockedDecrement((volatile signed __int32 *)(qword_140269460 + 88));
        if ( v105 >= *(_DWORD *)(v66 + 92) && v105 >= 0 )
        {
          v148 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v66 + 64));
          goto LABEL_216;
        }
        _InterlockedIncrement((volatile signed __int32 *)(v66 + 88));
      }
LABEL_137:
      v67 = *(unsigned int *)(v66 + 4);
LABEL_75:
      v68 = ExAllocatePool2(66, v67, 1766871885, v65);
      v64 = v68;
      if ( (v68 & 0xF) != 0 )
        goto LABEL_278;
      if ( !v68 )
      {
LABEL_218:
        v41 = 0x4000;
        goto LABEL_211;
      }
LABEL_217:
      *(_QWORD *)v64 = v66;
      v64 += 16;
      goto LABEL_218;
    }
    v147 = (struct _NPAGED_LOOKASIDE_LIST *)(qword_140269460 + 64);
    if ( *(_BYTE *)(qword_140269460 + 9) )
      v148 = ExAllocateFromNPagedLookasideList(v147);
    else
      v148 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v147);
LABEL_216:
    v64 = (__int64)v148;
    if ( v148 )
      goto LABEL_217;
    goto LABEL_137;
  }
  v60 = qword_140269458 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  if ( *(_DWORD *)v60 < 0x38u )
  {
    v60 = 0;
    v62 = 72;
    goto LABEL_70;
  }
  if ( !*(_BYTE *)(v60 + 8) )
  {
    if ( (int)*(_QWORD *)(v60 + 88) > (int)HIDWORD(*(_QWORD *)(v60 + 88)) )
    {
      v69 = _InterlockedDecrement((volatile signed __int32 *)(v60 + 88));
      if ( v69 >= *(_DWORD *)(v60 + 92) && v69 >= 0 )
      {
        v146 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v60 + 64));
        goto LABEL_209;
      }
      _InterlockedIncrement((volatile signed __int32 *)(v60 + 88));
    }
LABEL_82:
    v62 = *(unsigned int *)(v60 + 4);
LABEL_70:
    v63 = ExAllocatePool2(66, v62, 1766871885, v61);
    v64 = v63;
    if ( (v63 & 0xF) == 0 )
    {
      if ( v63 )
        goto LABEL_210;
      goto LABEL_211;
    }
LABEL_278:
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  }
  v145 = (struct _NPAGED_LOOKASIDE_LIST *)(v60 + 64);
  if ( *(_BYTE *)(v60 + 9) )
    v146 = ExAllocateFromNPagedLookasideList(v145);
  else
    v146 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v145);
LABEL_209:
  v64 = (__int64)v146;
  if ( !v146 )
    goto LABEL_82;
LABEL_210:
  *(_QWORD *)v64 = v60;
  v64 += 16;
LABEL_211:
  if ( !v64 )
  {
LABEL_212:
    v114 = -1073741670;
    goto LABEL_161;
  }
LABEL_85:
  v70 = *(_QWORD *)&v172[16];
  *(_OWORD *)(v64 + 32) = *(_OWORD *)v172;
  *(_QWORD *)(v64 + 48) = v70;
  *(_WORD *)(v64 + 26) = 4128;
  *(_WORD *)(v64 + 28) = v41;
  v71 = v164;
  *(_WORD *)(v64 + 30) = 24;
  *(_QWORD *)&v176[16] = v64;
  v175.m128i_i32[0] = *(unsigned __int8 *)(v64 + 27);
  v72 = v64 + *(unsigned __int8 *)(v64 + 26);
  v175.m128i_i16[2] = 0;
  v175.m128i_i64[1] = v72;
  *(_DWORD *)v176 = *(unsigned __int16 *)(v64 + 30);
  v73 = v64 + *(unsigned __int8 *)(v64 + 26);
  v74 = *(_QWORD *)v71;
  *(_QWORD *)&v176[8] = v73;
  (*(void (__fastcall **)(__int64, struct CmsTransactionCore *, CmsAvlTableLite **, __int128 *, _QWORD, _QWORD, __m128i *, __int64 *))(*(_QWORD *)v74 + 8LL))(
    v74,
    v5,
    &v181,
    &v178,
    0,
    0,
    &v184,
    &v177);
  v75 = (CmsAvlTableLite *)*((_QWORD *)v71 + 1);
  v76 = v162;
  P = v193;
  LODWORD(v186) = 0;
  v174 = 0;
  v192 = 32;
  DWORD1(v186) = (unsigned __int16)_mm_extract_epi16((__m128i)0LL, 2);
  v188 = DWORD1(v166);
  *((_QWORD *)&v186 + 1) = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  v187 = 0;
  v189 = 0;
  v191 = 0;
  v77 = v166;
  *(_OWORD *)v175.m128i_i64[1] = v166;
  v167 = v75;
  **(_OWORD **)&v176[8] = v77;
  v78 = *((unsigned __int8 *)v76 + 96);
  v160 = v175;
  v161 = *(_OWORD *)v176;
  v79 = 5;
  if ( (*(_DWORD *)v76 & 0x8000LL) == 0 )
    v79 = 2;
  if ( v78 < v79 )
  {
    v80 = (unsigned __int8)(v78 + 1);
    *((_BYTE *)v76 + 96) = v80;
    v81 = 5 * v80;
    if ( (unsigned __int8)v80 <= 2u )
      v82 = (char *)v76 - 24;
    else
      v82 = (char *)v76 + 784;
    v83 = &v82[8 * v81];
    *((_WORD *)v83 + 16) = 0;
    *(_QWORD *)v83 = &v160;
    *((_QWORD *)v83 + 1) = &CmsCountMap::PropertyDef;
    *((_QWORD *)v83 + 2) = &off_140207A10;
  }
  v84 = *((_QWORD *)v75 + 2);
  if ( !v84 )
  {
    v84 = 0;
    v106 = 0;
LABEL_142:
    v107 = 0;
    v108 = *((_BYTE *)v76 + 96);
    v109 = v75;
    v110 = v108 - 1;
    *((_BYTE *)v76 + 96) = v108 - 1;
    goto LABEL_180;
  }
  while ( 2 )
  {
    v85 = *((unsigned __int8 *)v76 + 96);
    v86 = 5 * v85;
    if ( (unsigned __int8)v85 <= 2u )
      v87 = v86 - 3;
    else
      v87 = v86 + 98;
    LODWORD(v174) = *(unsigned __int8 *)(v84 + 27);
    v88 = *(unsigned __int8 *)(v84 + 26);
    WORD2(v174) = 0;
    *((_QWORD *)&v174 + 1) = v84 + v88;
    v89 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int128 *))(**((_QWORD **)v76 + v87 + 2) + 8LL))(
            *((_QWORD *)v76 + v87 + 2),
            (__int64)v76 + 8 * v87,
            &v174);
    if ( !v89 )
    {
      v90 = *(_QWORD *)(v84 + 8);
      if ( !v90 )
      {
        v106 = 2;
        goto LABEL_141;
      }
LABEL_96:
      v76 = v162;
      v84 = v90;
      continue;
    }
    break;
  }
  if ( v89 == 1 )
  {
    v90 = *(_QWORD *)(v84 + 16);
    if ( !v90 )
    {
      v106 = 3;
LABEL_141:
      v76 = v162;
      goto LABEL_142;
    }
    goto LABEL_96;
  }
  v76 = v162;
  v107 = v84;
  v108 = *((_BYTE *)v162 + 96);
  v110 = v108 - 1;
  *((_BYTE *)v162 + 96) = v108 - 1;
  LODWORD(v186) = *(unsigned __int8 *)(v84 + 27);
  v153 = v84 + *(unsigned __int8 *)(v84 + 26);
  WORD2(v186) = 0;
  *((_QWORD *)&v186 + 1) = v153;
  v187 = *(unsigned __int16 *)(v84 + 30);
  v154 = (unsigned __int64 *)(v84 + *(unsigned __int8 *)(v84 + 26));
  v189 = v154;
  if ( *(_OWORD *)v154 == v166 )
  {
    CmsRowWithBuffer::Reset((CmsRowWithBuffer *)&v186);
    v114 = 0;
    goto LABEL_156;
  }
  v106 = 1;
  v109 = v75;
  if ( v154 )
  {
    memset(&v173, 0, sizeof(v173));
    v132 = CmsAvlTableLite::AddToIndexEx(
             v75,
             v76,
             (const struct SmsInternalPropertyDef *)&CmsCountMap::PropertyDef,
             (struct _CmsRow *)&v160,
             (struct _SmsQuickIndex *)&v173,
             (struct _SmsPreAllocatedRow *)&v175);
    v113 = v173.m256i_i64[0];
    v114 = v132;
  }
  else
  {
LABEL_180:
    v111 = 0;
    v113 = *(_QWORD *)&v176[16];
    v122 = 0;
    v13 = (*(_DWORD *)v76 & 0x8000LL) == 0;
    LODWORD(v163) = 0;
    v46 = 5;
    v168 = 0;
    if ( v13 )
      v46 = 2;
    *(_QWORD *)&v174 = *(_QWORD *)&v176[16];
    if ( v110 < v46 )
    {
      *((_BYTE *)v76 + 96) = v108;
      v123 = (char *)v76 + 40 * v108;
      if ( v108 <= 2u )
        v124 = v123 - 24;
      else
        v124 = v123 + 784;
      *(_QWORD *)v124 = &v175;
      *((_WORD *)v124 + 16) = 0;
      *((_QWORD *)v124 + 1) = &CmsCountMap::PropertyDef;
      *((_QWORD *)v124 + 2) = &off_140207A10;
    }
    v125 = *((unsigned __int8 *)v76 + 96);
    i = (__int64)v76 + 40 * v125;
    if ( (unsigned __int8)v125 > 2u )
      i += 808;
    *(_QWORD *)i = v113;
    if ( v84 )
    {
      if ( v107 )
      {
        v112 = MsLookupElementGenericTablePartialAvl<MST_AVL_DEFAULT_PROTOTYPE>(
                 (_DWORD)v109,
                 (_DWORD)v76,
                 v46,
                 v107,
                 (__int64)&v168,
                 (__int64)&v163);
        v111 = v163;
        v122 = v168;
        v126 = v167;
        goto LABEL_149;
      }
      v126 = v167;
      v122 = v84;
      v111 = v106;
LABEL_174:
      ++*((_DWORD *)v109 + 10);
      v114 = 0;
      if ( v111 != 1 )
      {
        v121 = (_OWORD *)((__int64 (__fastcall *)(CmsAvlTableLite *, _QWORD, struct CmsTransactionCore *))qword_1402692F0)(
                           v109,
                           0,
                           v76);
        if ( v121 )
        {
          *v121 = 0;
          *(_OWORD *)((char *)v121 + 10) = 0;
          ++*((_DWORD *)v109 + 8);
          if ( v111 )
          {
            if ( v111 == 2 )
              *(_QWORD *)(v122 + 8) = v121;
            else
              *(_QWORD *)(v122 + 16) = v121;
            *(_QWORD *)v121 = v122;
            *((_BYTE *)v126 + 24) = -1;
            for ( i = *(_QWORD *)v121; ; v122 = i )
            {
              v13 = *(_QWORD *)(i + 8) == (_QWORD)v121;
              v155 = -1;
              v156 = *(_BYTE *)(v122 + 24);
              if ( !v13 )
                v155 = 1;
              if ( v156 )
                break;
              i = *(_QWORD *)v122;
              v121 = (_OWORD *)v122;
              *(_BYTE *)(v122 + 24) = v155;
            }
            v113 = v174;
            if ( v156 == v155 )
              RebalanceNode((struct _RTL_AVL_ENTRY *)v122);
            else
              *(_BYTE *)(v122 + 24) = 0;
          }
          else
          {
            *((_QWORD *)v126 + 2) = v121;
            *(_QWORD *)v121 = v109;
          }
        }
      }
      --*((_BYTE *)v162 + 96);
    }
    else
    {
      v126 = v167;
      v127 = *((_QWORD *)v167 + 2);
      if ( v127 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            v128 = *((unsigned __int8 *)v76 + 96);
            v122 = v127;
            v129 = 5 * v128;
            v130 = (unsigned __int8)v128 <= 2u ? v129 - 3 : v129 + 98;
            LODWORD(v169[0]) = *(unsigned __int8 *)(v122 + 27);
            v169[1] = (struct _RTL_AVL_ENTRY *)(v122 + *(unsigned __int8 *)(v122 + 26));
            WORD2(v169[0]) = 0;
            v131 = (*(__int64 (__fastcall **)(_QWORD, __int64, struct _RTL_AVL_ENTRY **, __int64))(**((_QWORD **)v76 + v130 + 2)
                                                                                                 + 8LL))(
                     *((_QWORD *)v76 + v130 + 2),
                     (__int64)v76 + 8 * v130,
                     v169,
                     v106);
            if ( v131 )
              break;
            v127 = *(_QWORD *)(v122 + 8);
            if ( !v127 )
            {
              v111 = 2;
              goto LABEL_148;
            }
            v76 = v162;
          }
          if ( v131 != 1 )
            break;
          v127 = *(_QWORD *)(v122 + 16);
          if ( !v127 )
          {
            v111 = 3;
            goto LABEL_148;
          }
          v76 = v162;
        }
        v111 = 1;
        v112 = v122;
      }
      else
      {
LABEL_148:
        v112 = 0;
      }
LABEL_149:
      if ( !v112 )
      {
        v76 = v162;
        goto LABEL_174;
      }
      v113 = v112;
      v114 = -1073741771;
      --*((_BYTE *)v162 + 96);
    }
  }
  v107 = 0;
  if ( v114 >= 0 )
  {
    v107 = v113;
    *(_QWORD *)&v176[16] = 0;
  }
  if ( (v191 & 1) != 0 && P )
    ExFreePoolWithTag(P, 0);
LABEL_156:
  if ( v177 )
    v115 = v177 + *(unsigned __int8 *)(v177 + 26);
  else
    v115 = 0;
  if ( v107 )
    v116 = v107 + *(unsigned __int8 *)(v107 + 26);
  else
    v116 = 0;
  *(_QWORD *)(v115 + 24) = v107;
  *(_QWORD *)(v116 + 16) = v177;
LABEL_161:
  v117 = (_WORD *)*((_QWORD *)&v180 + 1);
  if ( *((_QWORD *)&v180 + 1) )
  {
    *((_QWORD *)&v178 + 1) = 0;
    WORD2(v178) = 0;
    v180 = 0u;
    if ( (v117[14] & 0x6000) != 0 )
    {
      v118 = *((_QWORD *)v117 - 2);
      v119 = (struct _SLIST_ENTRY *)(v117 - 8);
      if ( v118 )
      {
        if ( *(_BYTE *)(v118 + 8) )
        {
          v120 = (struct _NPAGED_LOOKASIDE_LIST *)(v118 + 64);
          if ( *(_BYTE *)(v118 + 9) )
            ExFreeToNPagedLookasideList(v120, v119);
          else
            ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v120, v119);
        }
        else
        {
          v149 = *(_QWORD *)(v118 + 88);
          if ( (int)v149 < *(_DWORD *)(v118 + 80) || SHIDWORD(v149) >= (int)v149 )
          {
            ExpInterlockedPushEntrySList((PSLIST_HEADER)(v118 + 64), v119);
            _InterlockedIncrement((volatile signed __int32 *)(v118 + 88));
          }
          else
          {
            ExFreePoolWithTag(v119, 0);
          }
        }
        goto LABEL_167;
      }
      v117 -= 8;
    }
    operator delete(v117);
  }
LABEL_167:
  if ( *(_QWORD *)&v176[16] )
    CmsAvlTableLite::CleanupPreAllocatedRow((CmsAvlTableLite *)v117, (struct _SmsPreAllocatedRow *)&v175, v46);
  if ( v114 < 0 )
    CmsRangeAndCountMap::DeleteAll(v164, (struct CmsTransactionCore *)i);
}

```

## disassembly

```asm
0x140049760  push    rbp
0x140049762  push    rbx
0x140049763  push    rsi
0x140049764  push    rdi
0x140049765  push    r12
0x140049767  push    r13
0x140049769  push    r14
0x14004976b  push    r15
0x14004976d  lea     rbp, [rsp-188h]
0x140049775  sub     rsp, 288h
0x14004977c  movaps  [rsp+2C0h+var_70], xmm8
0x140049785  movaps  [rsp+2C0h+var_80], xmm9
0x14004978e  mov     rax, cs:__security_cookie
0x140049795  xor     rax, rsp
0x140049798  mov     [rbp+1C0h+var_90], rax
0x14004979f  xor     r15d, r15d
0x1400497a2  mov     [rbp+1C0h+var_238], rdx
0x1400497a6  xorps   xmm1, xmm1
0x1400497a9  xorps   xmm0, xmm0
0x1400497ac  xorps   xmm8, xmm8
0x1400497b0  mov     r12, rdx
0x1400497b3  mov     rdi, r9
0x1400497b6  mov     rsi, r8
0x1400497b9  mov     rdx, rcx
0x1400497bc  mov     qword ptr [rbp+1C0h+var_1A0], r8
0x1400497c0  xorps   xmm9, xmm9
0x1400497c4  mov     [rbp+1C0h+var_228], rcx
0x1400497c8  mov     r13, 0FFFFFFFFFFFFFFFFh
0x1400497cf  mov     [rbp+1C0h+var_138], r15
0x1400497d6  movdqu  [rbp+1C0h+var_130], xmm0
0x1400497de  mov     [rsp+2C0h+var_268], r15
0x1400497e3  movups  xmm0, xmmword ptr [r8]
0x1400497e7  mov     [rsp+2C0h+var_260], r15
0x1400497ec  movups  [rbp+1C0h+var_110], xmm8
0x1400497f4  mov     qword ptr [rsp+2C0h+var_258], r15
0x1400497f9  movups  [rbp+1C0h+var_218], xmm0
0x1400497fd  mov     [rbp+1C0h+var_168], r15
0x140049801  xorps   xmm0, xmm0
0x140049804  mov     [rbp+1C0h+var_150], r15d
0x140049808  movdqu  [rsp+2C0h+var_248], xmm0
0x14004980e  mov     dword ptr [rbp+1C0h+var_180], r15d
0x140049812  movups  [rbp+1C0h+var_160], xmm0
0x140049816  movups  [rbp+1C0h+var_190], xmm0
0x14004981a  movups  [rbp+1C0h+var_100], xmm1
0x140049821  movups  [rbp+1C0h+var_F0], xmm1
0x140049828  movdqu  [rbp+1C0h+var_148], xmm1
0x14004982d  movdqu  [rbp+1C0h+var_178], xmm1
0x140049832  cmp     [rcx+10h], r15d
0x140049836  ja      loc_1400499A0
0x14004983c  mov     [rsp+2C0h+var_270], 1
0x140049841  test    rdi, rdi
0x140049844  jnz     loc_14004AD60
0x14004984a  mov     r8, [rsi]
0x14004984d  mov     r11, [rsi+8]
0x140049851  mov     [rbp+1C0h+var_208], r8
0x140049855  test    r8, r8
0x140049858  jz      short loc_140049864
0x14004985a  dec     r8
0x14004985d  mov     [rbp+1C0h+var_208], r8
0x140049861  inc     r11
0x140049864  add     r11, 1
0x140049868  mov     r14d, 20h ; ' '
0x14004986e  mov     [rbp+1C0h+var_220], r11
0x140049872  mov     r9d, 18h
0x140049878  jz      loc_140049C2A
0x14004987e  mov     r14d, dword ptr [rbp+1C0h+var_218+4]
0x140049882  mov     r12d, dword ptr [rbp+1C0h+var_218+4]
0x140049886  mov     edi, dword ptr [rbp+1C0h+var_218+4]
0x140049889  mov     esi, dword ptr [rbp+1C0h+var_218+4]
0x14004988c  mov     r13d, dword ptr [rbp+1C0h+var_218+4]
0x140049890  mov     r15d, dword ptr [rbp+1C0h+var_218+4]
0x140049894  mov     ebx, dword ptr [rbp+1C0h+var_218+4]
0x140049897  movaps  [rsp+2C0h+var_50], xmm6
0x14004989f  movaps  [rsp+2C0h+var_60], xmm7
0x1400498a7  mov     r10, [rdx]
0x1400498aa  lea     rax, [rbp+1C0h+var_B0]
0x1400498b1  xorps   xmm0, xmm0
0x1400498b4  mov     [rbp+1C0h+P], rax
0x1400498bb  pextrw  eax, xmm0, 2
0x1400498c0  movups  xmmword ptr [rbp+1C0h+var_1F8], xmm0
0x1400498c4  lea     rcx, [r11+r8]
0x1400498c8  mov     dword ptr [rbp+1C0h+var_1B0], r9d
0x1400498cc  movss   dword ptr [rbp+1C0h+var_E0], xmm0
0x1400498d4  movq    r9, xmm9
0x1400498d9  mov     word ptr [rbp+1C0h+var_E0+4], ax
0x1400498e0  movzx   eax, word ptr [rbp+1C0h+var_1F8+6]
0x1400498e4  mov     word ptr [rbp+1C0h+var_E0+6], ax
0x1400498eb  xor     eax, eax
0x1400498ed  mov     [rbp+1C0h+var_1C8], rax
0x1400498f1  lea     rax, [rbp+1C0h+var_1D8]
0x1400498f5  psrldq  xmm0, 8
0x1400498fa  mov     qword ptr [rbp+1C0h+var_1C0+8], rax
0x1400498fe  lea     rax, [rbp+1C0h+var_1D8]
0x140049902  movq    qword ptr [rbp+1C0h+var_E0+8], xmm0
0x14004990a  xorps   xmm0, xmm0
0x14004990d  mov     qword ptr [rbp+1C0h+var_1B0+8], rax
0x140049911  mov     [rbp+1C0h+var_200], r10
0x140049915  mov     [rbp+1C0h+var_B4], 20h ; ' '
0x14004991f  mov     [rbp+1C0h+var_D0], 0
0x140049929  mov     [rbp+1C0h+var_CC], r14d
0x140049930  mov     [rbp+1C0h+var_C8], 0
0x14004993b  mov     [rbp+1C0h+var_B8], 0
0x140049942  mov     qword ptr [rbp+1C0h+var_1C0], 10h
0x14004994a  mov     [rbp+1C0h+var_230], rcx
0x14004994e  mov     qword ptr [rbp+1C0h+var_1D8], r8
0x140049952  mov     qword ptr [rbp+1C0h+var_1D8+8], r11
0x140049956  movups  [rsp+2C0h+var_258], xmm0
0x14004995b  movups  [rsp+2C0h+var_248], xmm0
0x140049960  test    r9, r9
0x140049963  jnz     loc_14004A22D
0x140049969  mov     rax, [r10+18h]
0x14004996d  test    rax, rax
0x140049970  jnz     loc_140049D02
0x140049976  mov     qword ptr [rsp+2C0h+var_258], rax
0x14004997b  mov     dword ptr [rsp+2C0h+var_248], eax
0x14004997f  mov     eax, [r10+30h]
0x140049983  mov     [rbp+1C0h+var_220], rcx
0x140049987  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14004998e  mov     dword ptr [rsp+2C0h+var_248+4], eax
0x140049992  mov     qword ptr [rsp+2C0h+var_258+8], 0
0x14004999b  jmp     loc_140049B34
0x1400499a0  mov     rax, [rcx+8]
0x1400499a4  mov     ecx, [rax+20h]
0x1400499a7  cmp     ecx, [rdx+10h]
0x1400499aa  jb      loc_14004983C
0x1400499b0  mov     rbx, [r8]
0x1400499b3  test    rbx, rbx
0x1400499b6  jnz     loc_14004AB7A
0x1400499bc  mov     rbx, [rsi]
0x1400499bf  add     rbx, [rsi+8]
0x1400499c3  cmp     rbx, r13
0x1400499c6  jnb     loc_1401FCFF2
0x1400499cc  mov     r14, [rdx]
0x1400499cf  lea     rcx, [rbp+1C0h+var_E0]; this
0x1400499d6  xorps   xmm0, xmm0
0x1400499d9  mov     [rbp+1C0h+var_D0], r15d
0x1400499e0  movups  [rbp+1C0h+var_E0], xmm0
0x1400499e7  mov     [rbp+1C0h+var_C8], r15
0x1400499ee  mov     [rbp+1C0h+P], r15
0x1400499f5  mov     [rbp+1C0h+var_B8], 0
0x1400499fc  mov     [rbp+1C0h+var_B4], r15d
0x140049a03  call    ?Reset@CmsRowWithBuffer@@QEAAXXZ; CmsRowWithBuffer::Reset(void)
0x140049a08  xorps   xmm0, xmm0
0x140049a0b  mov     [rbp+1C0h+var_1E8], r15d
0x140049a0f  xor     eax, eax
0x140049a11  mov     [rbp+1C0h+var_1E0], r15
0x140049a15  xor     r8d, r8d; struct _SmsPreAllocatedRow *
0x140049a18  mov     [rbp+1C0h+var_1C8], rax
0x140049a1c  lea     rdx, [rbp+1C0h+var_1D8]; struct SmsRangeMapEntry *
0x140049a20  mov     qword ptr [rbp+1C0h+var_1D8], rbx
0x140049a24  lea     rcx, [rbp+1C0h+var_1F8]; struct _CmsRow *
0x140049a28  mov     qword ptr [rbp+1C0h+var_1D8+8], 1
0x140049a30  movups  xmmword ptr [rbp+1C0h+var_1F8], xmm0
0x140049a34  lea     r15, [rbx+1]
0x140049a38  movups  [rbp+1C0h+var_1C0], xmm0
0x140049a3c  movups  [rbp+1C0h+var_1B0], xmm0
0x140049a40  call    ?SetRangeMapEntryRowHlpr@@YAXPEAU_CmsRow@@PEAUSmsRangeMapEntry@@PEAU_SmsPreAllocatedRow@@@Z; SetRangeMapEntryRowHlpr(_CmsRow *,SmsRangeMapEntry *,_SmsPreAllocatedRow *)
0x140049a45  lea     rax, [rbp+1C0h+var_1C0]
0x140049a49  mov     rdx, r12; struct CmsTransactionCore *
0x140049a4c  mov     [rsp+2C0h+var_298], rax; struct _SmsQuickIndex *
0x140049a51  lea     rcx, [r14+8]; this
0x140049a55  lea     rax, [rbp+1C0h+var_E0]
0x140049a5c  lea     r9, [rbp+1C0h+var_1F8]; struct _CmsRow *
0x140049a60  mov     [rsp+2C0h+var_2A0], rax; struct _CmsRow *
0x140049a65  lea     r8, ?PropertyDef@CmsRangeMap@@1USmsInternalPropertyDef@@B; struct SmsInternalPropertyDef *
0x140049a6c  call    ?PinInIndexEx@CmsAvlTableLite@@QEAAJPEAVCmsTransactionCore@@PEBUSmsInternalPropertyDef@@PEAU_CmsRow@@2PEAU_SmsQuickIndex@@@Z; CmsAvlTableLite::PinInIndexEx(CmsTransactionCore *,SmsInternalPropertyDef const *,_CmsRow *,_CmsRow *,_SmsQuickIndex *)
0x140049a71  test    eax, eax
0x140049a73  jz      loc_14004ACDE
0x140049a79  lea     rax, [rbp+1C0h+var_1C0]
0x140049a7d  xor     r9d, r9d
0x140049a80  lea     r8, [rbp+1C0h+var_E0]
0x140049a87  mov     [rsp+2C0h+var_2A0], rax
0x140049a8c  mov     edx, 1
0x140049a91  mov     r14, r13
0x140049a94  call    ?PinNextInIndex@CmsAvlTableLite@@QEAAJW4_EMS_CURSOR_FLAGS@@PEAU_CmsRow@@PEAUSmsLookupStack@@PEAU_SmsQuickIndex@@@Z; CmsAvlTableLite::PinNextInIndex(_EMS_CURSOR_FLAGS,_CmsRow *,SmsLookupStack *,_SmsQuickIndex *)
0x140049a99  test    eax, eax
0x140049a9b  jnz     short loc_140049AA7
0x140049a9d  mov     rax, [rbp+1C0h+var_C8]
0x140049aa4  mov     r14, [rax]
0x140049aa7  mov     [rsp+2C0h+var_268], rbx
0x140049aac  mov     [rsp+2C0h+var_260], 1
0x140049ab5  cmp     r14, r15
0x140049ab8  jb      loc_14004AD53
0x140049abe  lea     rcx, [rbp+1C0h+var_E0]; this
0x140049ac5  call    ?Reset@CmsRowWithBuffer@@QEAAXXZ; CmsRowWithBuffer::Reset(void)
0x140049aca  nop
0x140049acb  jmp     loc_1401FCFF2
0x140049ad0  cmp     [r9+8], rax
0x140049ad4  jnz     loc_14004A721
0x140049ada  mov     rax, r9
0x140049add  test    rax, rax
0x140049ae0  jz      loc_140049992
0x140049ae6  movzx   ecx, byte ptr [rax+1Bh]
0x140049aea  mov     dword ptr [rbp+1C0h+var_E0], ecx
0x140049af0  movzx   ecx, byte ptr [rax+1Ah]
0x140049af4  add     rcx, rax
0x140049af7  mov     dword ptr [rsp+2C0h+var_248], 1
0x140049aff  mov     qword ptr [rbp+1C0h+var_E0+8], rcx
0x140049b06  xor     ecx, ecx
0x140049b08  mov     word ptr [rbp+1C0h+var_E0+4], cx
0x140049b0f  movzx   ecx, word ptr [rax+1Eh]
0x140049b13  mov     [rbp+1C0h+var_D0], ecx
0x140049b19  movzx   ecx, byte ptr [rax+1Ah]
0x140049b1d  add     rcx, rax
0x140049b20  mov     qword ptr [rsp+2C0h+var_258+8], rax
0x140049b25  mov     [rbp+1C0h+var_C8], rcx
0x140049b2c  mov     qword ptr [rsp+2C0h+var_258], rax
0x140049b31  mov     rcx, [rcx]
0x140049b34  mov     rax, [rbp+1C0h+var_220]
0x140049b38  mov     [rsp+2C0h+var_268], r8
0x140049b3d  mov     r10, r8
0x140049b40  mov     [rsp+2C0h+var_260], r11
0x140049b45  mov     r9, r11
0x140049b48  movups  xmm7, [rsp+2C0h+var_248]
0x140049b4d  movups  xmm6, [rsp+2C0h+var_258]
0x140049b52  movups  xmm8, xmm7
0x140049b56  movups  xmm9, xmm6
0x140049b5a  movups  [rbp+1C0h+var_110], xmm7
0x140049b61  cmp     rcx, rax
0x140049b64  jb      loc_14004ADA6
0x140049b6a  mov     rdx, [rbp+1C0h+var_230]
0x140049b6e  lea     rax, [rbp+1C0h+var_B0]
0x140049b75  xorps   xmm0, xmm0
0x140049b78  mov     [rbp+1C0h+P], rax
0x140049b7f  pextrw  eax, xmm0, 2
0x140049b84  movups  xmmword ptr [rbp+1C0h+var_1F8], xmm0
0x140049b88  mov     [rbp+1C0h+var_D0], 0
0x140049b92  mov     [rbp+1C0h+var_CC], edi
0x140049b98  mov     word ptr [rbp+1C0h+var_E0+4], ax
0x140049b9f  movzx   eax, word ptr [rbp+1C0h+var_1F8+6]
0x140049ba3  mov     word ptr [rbp+1C0h+var_E0+6], ax
0x140049baa  mov     [rbp+1C0h+var_C8], 0
0x140049bb5  mov     [rbp+1C0h+var_B8], 0
0x140049bbc  movss   dword ptr [rbp+1C0h+var_E0], xmm0
0x140049bc4  psrldq  xmm0, 8
0x140049bc9  movq    qword ptr [rbp+1C0h+var_E0+8], xmm0
0x140049bd1  mov     [rbp+1C0h+var_B4], 20h ; ' '
0x140049bdb  cmp     [rsp+2C0h+var_270], 0
0x140049be0  jz      short loc_140049BF5
0x140049be2  movups  [rbp+1C0h+var_100], xmm6
0x140049be9  mov     [rsp+2C0h+var_270], 0
0x140049bee  movups  [rbp+1C0h+var_F0], xmm7
0x140049bf5  lea     rax, [r10+r9]
0x140049bf9  cmp     rdx, rax
0x140049bfc  ja      loc_14004ADB6
0x140049c02  mov     rsi, qword ptr [rbp+1C0h+var_1A0]
0x140049c06  mov     r13, 0FFFFFFFFFFFFFFFFh
0x140049c0d  mov     r12, [rbp+1C0h+var_238]
0x140049c11  xor     r15d, r15d
0x140049c14  movaps  xmm7, [rsp+2C0h+var_60]
0x140049c1c  mov     r14d, 20h ; ' '
0x140049c22  movaps  xmm6, [rsp+2C0h+var_50]
0x140049c2a  cmp     cs:?SizeOfAllocationsOnLookaside2@CmsAvlTableLite@@2KA, 40h ; '@'; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside2
0x140049c31  xorps   xmm0, xmm0
0x140049c34  mov     rcx, [rsi]
0x140049c37  mov     rax, [rsi+8]
0x140049c3b  mov     [rbp+1C0h+var_138], rcx
0x140049c42  mov     qword ptr [rbp+1C0h+var_130], rax
0x140049c49  mov     qword ptr [rbp+1C0h+var_130+8], rcx
0x140049c50  movdqu  [rbp+1C0h+var_1C0+8], xmm0
0x140049c55  mov     qword ptr [rbp+1C0h+var_1C0], r15
0x140049c59  jb      loc_140049E29
0x140049c5f  xor     ecx, ecx; ProcNumber
0x140049c61  mov     esi, 4000h
0x140049c66  cmp     cs:?SizeOfAllocationsOnLookaside1@CmsAvlTableLite@@2KA, 40h ; '@'; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside1
0x140049c6d  mov     ebx, 2000h
0x140049c72  jb      loc_140049D97
0x140049c78  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140049c7f  nop     dword ptr [rax+rax+00h]
0x140049c84  xor     edx, edx
0x140049c86  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140049c8c  lea     rdi, [rdx+rdx*2]
0x140049c90  shl     rdi, 6
0x140049c94  add     rdi, cs:qword_140269458
0x140049c9b  cmp     dword ptr [rdi], 40h ; '@'
0x140049c9e  jnb     loc_140049DEB
0x140049ca4  mov     rdi, r15
0x140049ca7  mov     edx, 50h ; 'P'
0x140049cac  mov     ecx, 42h ; 'B'
0x140049cb1  mov     r8d, 6950534Dh
0x140049cb7  call    cs:__imp_ExAllocatePool2
0x140049cbe  nop     dword ptr [rax+rax+00h]
0x140049cc3  mov     rcx, rax
0x140049cc6  test    al, 0Fh
0x140049cc8  jnz     loc_1401FD0B0
0x140049cce  test    rax, rax
0x140049cd1  jz      loc_14004AA16
0x140049cd7  jmp     loc_14004AA0F
0x140049cdc  mov     rdx, [rcx]
0x140049cdf  cmp     r8, rdx
0x140049ce2  jb      short loc_140049D0B
0x140049ce4  add     rdx, [rcx+8]
0x140049ce8  cmp     r8, rdx
0x140049ceb  jb      loc_14004A407
0x140049cf1  mov     rcx, [rax+10h]
0x140049cf5  test    rcx, rcx
0x140049cf8  jz      short loc_140049D21
0x140049cfa  mov     rax, rcx
0x140049cfd  test    rcx, rcx
0x140049d00  jz      short loc_140049CDC
  ... truncated ...
```
