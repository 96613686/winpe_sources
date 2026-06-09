# CmsRangeAndCountMap::AddEntry(CmsTransactionCore *,_RANGE const *,unsigned __int64 *,uchar *)

- ea: `0x140073080`
- end: `0x140074885`
- name: `?AddEntry@CmsRangeAndCountMap@@QEAAXPEAVCmsTransactionCore@@PEBU_RANGE@@PEA_KPEAE@Z`
- size: `6149`
- prototype: `void(CmsRangeAndCountMap *__hidden this, struct CmsTransactionCore *, const struct _RANGE *, unsigned __int64 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x1400b1320`

## callees

- `0x14002b110`
- `0x140071890`
- `0x140072870`
- `0x140072970`
- `0x140073080`
- `0x140074ee0`
- `0x140075200`
- `0x140075eb0`
- `0x14007aea0`
- `0x14007b060`
- `0x14007b360`
- `0x140085f10`
- `0x1400ace40`
- `0x1400c67ac`
- `0x1400c8574`
- `0x14015fcac`
- `0x140172644`
- `0x1401e9ce0`
- `0x1401e9dc0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400741c0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400741c0`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400746fb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140074737`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140074773`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400747af`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400746fb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140074737`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140074773`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400747af`
- `ntoskrnl!ExAllocatePool2` at `0x1400735d7`
- `ntoskrnl!ExAllocatePool2` at `0x1400736e6`
- `ntoskrnl!ExAllocatePool2` at `0x140073759`
- `ntoskrnl!ExAllocatePool2` at `0x14007383a`
- `ntoskrnl!ExAllocatePool2` at `0x14007388e`
- `ntoskrnl!ExAllocatePool2` at `0x140073901`
- `ntoskrnl!ExAllocatePool2` at `0x1400735d7`
- `ntoskrnl!ExAllocatePool2` at `0x1400736e6`
- `ntoskrnl!ExAllocatePool2` at `0x140073759`
- `ntoskrnl!ExAllocatePool2` at `0x14007383a`
- `ntoskrnl!ExAllocatePool2` at `0x14007388e`
- `ntoskrnl!ExAllocatePool2` at `0x140073901`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140073598`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400736b7`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400737fb`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14007385f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140073598`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400736b7`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400737fb`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14007385f`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f6d60`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f6d72`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f6d91`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f6da3`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f6d60`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f6d72`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f6d91`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f6da3`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14007416f`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14007416f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f6e96`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f6e96`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140074718`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140074754`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140074790`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400747cc`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140074718`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140074754`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140074790`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400747cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073f28`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400740dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007484b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073f28`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400740dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007484b`

## string_xrefs

- `0x1401f6d84`: `Lookaside list allocation must be double quad aligned.`
- `0x1401f6db5`: `Lookaside list allocation must be double quad aligned.`

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
  int v15; // r14d
  int v16; // r12d
  int v17; // edi
  int v18; // esi
  int v19; // r13d
  int v20; // r15d
  int v21; // ebx
  __int64 v22; // r10
  struct _RTL_AVL_ENTRY *v23; // rax
  int v24; // eax
  unsigned __int64 v25; // rcx
  unsigned __int64 v26; // rbx
  unsigned __int64 v27; // rbx
  __int64 v28; // r14
  unsigned __int64 v29; // r15
  __int64 v30; // rcx
  unsigned __int64 v31; // r14
  char *v32; // rcx
  __int64 v33; // rcx
  unsigned __int64 v34; // r10
  unsigned __int64 v35; // r9
  __int128 v36; // xmm7
  __m128i v37; // xmm6
  unsigned __int64 v38; // rdx
  __m128i v39; // xmm0
  __int64 v40; // rax
  __int16 v41; // bx
  __int64 v42; // rdi
  __int64 v43; // rdx
  __int64 v44; // rax
  unsigned int v45; // r8d
  __m256i *Pool2; // rcx
  struct _RTL_AVL_ENTRY *v47; // rcx
  _QWORD *v48; // rcx
  int v49; // edx
  __int64 v50; // rdx
  struct _RTL_AVL_ENTRY *v51; // rdx
  struct _RTL_AVL_ENTRY *v52; // r9
  __int64 v53; // rdi
  __int64 v54; // rdx
  __int64 v55; // rax
  int v56; // ecx
  __int64 i; // rdx
  __int8 *v58; // rax
  __int64 v59; // rsi
  __int64 v60; // rdx
  __int64 v61; // rax
  __int64 v62; // rcx
  __int64 v63; // rbx
  __int64 v64; // rdx
  __int64 v65; // rax
  int v66; // ecx
  __int64 v67; // xmm1_8
  CmsRangeAndCountMap *v68; // rbx
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rcx
  CmsAvlTableLite *v72; // rbx
  struct CmsTransactionCore *v73; // r10
  __int128 v74; // xmm1
  unsigned int v75; // ecx
  unsigned int v76; // eax
  __int64 v77; // rcx
  __int64 v78; // rax
  char *v79; // rcx
  char *v80; // rcx
  __int64 v81; // r14
  __int64 v82; // rcx
  __int64 v83; // rax
  __int64 v84; // rdx
  __int64 v85; // rax
  int v86; // eax
  __int64 v87; // rax
  struct _RTL_AVL_ENTRY *v88; // xmm0_8
  char *v89; // rcx
  unsigned __int64 *v90; // rdx
  unsigned __int64 v91; // rcx
  int v92; // ecx
  unsigned __int64 v93; // r9
  unsigned __int64 v94; // r10
  unsigned __int64 v95; // r8
  unsigned __int64 v96; // rdx
  unsigned __int64 v97; // rcx
  char *v98; // rcx
  struct _RTL_AVL_ENTRY *v99; // rcx
  struct _RTL_AVL_ENTRY *v100; // rdx
  struct _MS_AVL_TABLE *v101; // rcx
  int v102; // ecx
  __int64 v103; // r9
  __int64 v104; // rsi
  unsigned __int8 v105; // dl
  CmsAvlTableLite *v106; // r15
  unsigned __int8 v107; // cl
  int v108; // r12d
  __int64 v109; // rax
  __int64 v110; // r13
  int v111; // edi
  __int64 v112; // rax
  __int64 v113; // rcx
  _WORD *v114; // rcx
  __int64 v115; // rbx
  struct _SLIST_ENTRY *v116; // r8
  struct _NPAGED_LOOKASIDE_LIST *v117; // rcx
  _OWORD *v118; // rax
  __int64 v119; // rbx
  char *v120; // rcx
  char *v121; // rcx
  __int64 v122; // rcx
  CmsAvlTableLite *v123; // rsi
  __int64 v124; // rax
  __int64 v125; // rcx
  __int64 v126; // rax
  __int64 v127; // rdx
  int v128; // eax
  int v129; // eax
  __int64 v130; // r14
  unsigned __int64 v131; // r15
  __int64 v132; // rcx
  unsigned __int64 v133; // r14
  unsigned __int64 v134; // rdx
  unsigned __int64 v135; // rax
  unsigned __int64 v136; // rdx
  unsigned __int64 v137; // rax
  struct _NPAGED_LOOKASIDE_LIST *v138; // rcx
  __m256i *v139; // rax
  struct _NPAGED_LOOKASIDE_LIST *v140; // rcx
  __m256i *v141; // rax
  struct _NPAGED_LOOKASIDE_LIST *v142; // rcx
  void *v143; // rax
  struct _NPAGED_LOOKASIDE_LIST *v144; // rcx
  void *v145; // rax
  __int64 v146; // rcx
  unsigned __int8 *LeftmostNodeAvlFull; // rax
  CmsRangeAndCountMap *v148; // r10
  __int64 v149; // rdx
  __int64 v150; // rax
  unsigned __int64 *v151; // r8
  char v152; // cl
  char v153; // al
  char v154; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v155; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v156; // [rsp+60h] [rbp-A0h]
  __m128i v157; // [rsp+68h] [rbp-98h] BYREF
  __int128 v158; // [rsp+78h] [rbp-88h]
  struct CmsTransactionCore *v159; // [rsp+88h] [rbp-78h]
  unsigned __int64 v160; // [rsp+90h] [rbp-70h] BYREF
  CmsRangeAndCountMap *v161; // [rsp+98h] [rbp-68h]
  unsigned __int64 v162; // [rsp+A0h] [rbp-60h]
  __int128 v163; // [rsp+A8h] [rbp-58h]
  CmsAvlTableLite *v164; // [rsp+B8h] [rbp-48h]
  __int64 v165; // [rsp+C0h] [rbp-40h] BYREF
  struct _RTL_AVL_ENTRY *v166[2]; // [rsp+C8h] [rbp-38h] BYREF
  int v167; // [rsp+D8h] [rbp-28h]
  __int64 v168; // [rsp+E0h] [rbp-20h]
  _BYTE v169[24]; // [rsp+E8h] [rbp-18h] BYREF
  __m256i v170; // [rsp+100h] [rbp+0h] BYREF
  __int128 v171; // [rsp+120h] [rbp+20h] BYREF
  __m128i v172; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v173[24]; // [rsp+140h] [rbp+40h]
  __int64 v174; // [rsp+158h] [rbp+58h] BYREF
  __int128 v175; // [rsp+160h] [rbp+60h] BYREF
  int v176; // [rsp+170h] [rbp+70h]
  __int128 v177; // [rsp+178h] [rbp+78h]
  CmsAvlTableLite *v178; // [rsp+188h] [rbp+88h] BYREF
  __int128 v179; // [rsp+190h] [rbp+90h]
  __int128 v180; // [rsp+1B0h] [rbp+B0h]
  __m128i v181; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 v182; // [rsp+1D0h] [rbp+D0h]
  __int128 v183; // [rsp+1E0h] [rbp+E0h] BYREF
  int v184; // [rsp+1F0h] [rbp+F0h]
  int v185; // [rsp+1F4h] [rbp+F4h]
  unsigned __int64 *v186; // [rsp+1F8h] [rbp+F8h]
  PVOID P; // [rsp+200h] [rbp+100h]
  char v188; // [rsp+208h] [rbp+108h]
  int v189; // [rsp+20Ch] [rbp+10Ch]
  _BYTE v190[32]; // [rsp+210h] [rbp+110h] BYREF

  v159 = a2;
  v4 = 0;
  v5 = a2;
  v7 = a3;
  v8 = this;
  *(_QWORD *)&v171 = a3;
  v9 = 0;
  v161 = this;
  v178 = 0;
  v179 = 0;
  v155 = 0;
  v10 = *(_OWORD *)a3;
  v156 = 0;
  v180 = 0;
  v157.m128i_i64[0] = 0;
  v163 = v10;
  v174 = 0;
  v176 = 0;
  v158 = 0;
  *(_DWORD *)v173 = 0;
  v175 = 0;
  v172 = 0;
  v181 = 0;
  v182 = 0;
  v177 = 0;
  *(_OWORD *)&v173[8] = 0;
  if ( !*((_DWORD *)this + 4) || *(_DWORD *)(*((_QWORD *)this + 1) + 32LL) < *((_DWORD *)this + 4) )
    goto LABEL_2;
  v26 = *(_QWORD *)a3;
  if ( !*(_QWORD *)a3 )
    goto LABEL_14;
  v130 = *(_QWORD *)this;
  v131 = v26 - 1;
  v184 = 0;
  v186 = 0;
  P = 0;
  v188 = 0;
  v189 = 0;
  v183 = 0;
  CmsRowWithBuffer::Reset((CmsRowWithBuffer *)&v183);
  v167 = 0;
  v168 = 0;
  *(_QWORD *)&v169[16] = 0;
  *(_QWORD *)v169 = v26 - 1;
  *(_QWORD *)&v169[8] = 1;
  *(_OWORD *)v166 = 0;
  memset(&v170, 0, sizeof(v170));
  SetRangeMapEntryRowHlpr((struct _CmsRow *)v166, (struct SmsRangeMapEntry *)v169, 0);
  if ( CmsAvlTableLite::PinInIndexEx(
         (CmsAvlTableLite *)(v130 + 8),
         v5,
         (const struct SmsInternalPropertyDef *)&CmsRangeMap::PropertyDef,
         (struct _CmsRow *)v166,
         (struct _CmsRow *)&v183,
         (struct _SmsQuickIndex *)&v170) )
  {
    v133 = -1;
    if ( !(unsigned int)CmsAvlTableLite::PinNextInIndex(v132, 1, &v183, 0, &v170) )
      v133 = *v186;
    v155 = v26 - 1;
    v156 = 1;
    if ( v133 < v26 )
      v156 = v133 - v131;
    CmsRowWithBuffer::Reset((CmsRowWithBuffer *)&v183);
    v8 = v161;
LABEL_14:
    v27 = *((_QWORD *)v7 + 1) + *(_QWORD *)v7;
    if ( v27 != -1 )
    {
      v28 = *(_QWORD *)v8;
      v184 = 0;
      v183 = 0;
      v186 = 0;
      P = 0;
      v188 = 0;
      v189 = 0;
      CmsRowWithBuffer::Reset((CmsRowWithBuffer *)&v183);
      v167 = 0;
      v168 = 0;
      *(_QWORD *)&v169[16] = 0;
      *(_QWORD *)v169 = v27;
      *(_QWORD *)&v169[8] = 1;
      *(_OWORD *)v166 = 0;
      v29 = v27 + 1;
      memset(&v170, 0, sizeof(v170));
      SetRangeMapEntryRowHlpr((struct _CmsRow *)v166, (struct SmsRangeMapEntry *)v169, 0);
      if ( !CmsAvlTableLite::PinInIndexEx(
              (CmsAvlTableLite *)(v28 + 8),
              v5,
              (const struct SmsInternalPropertyDef *)&CmsRangeMap::PropertyDef,
              (struct _CmsRow *)v166,
              (struct _CmsRow *)&v183,
              (struct _SmsQuickIndex *)&v170) )
      {
        v136 = *v186 + v186[1];
        v156 = 1;
        v137 = v186[2];
        v155 = v137;
        if ( !*(_BYTE *)(v28 + 56) )
          v155 = v27 + v137 - *v186;
        if ( v29 > v136 )
          v156 = v136 - v27;
        CmsRowWithBuffer::Reset((CmsRowWithBuffer *)&v183);
        v8 = v161;
        goto LABEL_2;
      }
      v31 = -1;
      if ( !(unsigned int)CmsAvlTableLite::PinNextInIndex(v30, 1, &v183, 0, &v170) )
        v31 = *v186;
      v155 = v27;
      v156 = 1;
      if ( v31 < v29 )
        v156 = v31 - v27;
      CmsRowWithBuffer::Reset((CmsRowWithBuffer *)&v183);
    }
    LeftmostNodeAvlFull = (unsigned __int8 *)MsFindLeftmostNodeAvlFull(*((struct _MS_AVL_TABLE **)v161 + 1), v166);
    if ( !LeftmostNodeAvlFull )
      return;
    v149 = LeftmostNodeAvlFull[26];
    v155 = *(_QWORD *)&LeftmostNodeAvlFull[v149];
    v156 = *(_QWORD *)&LeftmostNodeAvlFull[v149 + 8];
    if ( v156 >= *((_QWORD *)v7 + 1) )
      return;
    v157.m128i_i64[0] = (__int64)LeftmostNodeAvlFull;
    v157.m128i_i64[1] = (__int64)LeftmostNodeAvlFull;
    LODWORD(v158) = 1;
    CmsRangeAndCountMap::DeleteEntry(v148, v5, (struct _RANGE *)&v155, 0, (struct _SmsQuickIndex *)&v157);
    goto LABEL_220;
  }
  v134 = *v186 + v186[1];
  v156 = 1;
  v135 = v186[2];
  v155 = v135;
  if ( !*(_BYTE *)(v130 + 56) )
    v155 = v131 + v135 - *v186;
  if ( v26 > v134 )
  {
    v156 = v134 - v131;
    CmsRowWithBuffer::Reset((CmsRowWithBuffer *)&v183);
    v8 = v161;
    goto LABEL_2;
  }
  CmsRowWithBuffer::Reset((CmsRowWithBuffer *)&v183);
LABEL_220:
  v8 = v161;
LABEL_2:
  v154 = 1;
  if ( a4 )
    ++*a4;
  v11 = *(CmsAvlTableLite **)v7;
  v12 = *((_QWORD *)v7 + 1);
  v164 = v11;
  if ( v11 )
  {
    v11 = (CmsAvlTableLite *)((char *)v11 - 1);
    v164 = v11;
    ++v12;
  }
  v13 = v12 == -1;
  v14 = v12 + 1;
  v162 = v14;
  if ( v13 )
    goto LABEL_34;
  v15 = DWORD1(v163);
  v16 = DWORD1(v163);
  v17 = DWORD1(v163);
  v18 = DWORD1(v163);
  v19 = DWORD1(v163);
  v20 = DWORD1(v163);
  v21 = DWORD1(v163);
  while ( 2 )
  {
    v22 = *(_QWORD *)v8;
    P = v190;
    *(_OWORD *)v166 = 0;
    v170.m256i_i32[4] = 24;
    LODWORD(v183) = 0;
    DWORD1(v183) = (unsigned __int16)_mm_extract_epi16((__m128i)0LL, 2);
    *(_QWORD *)&v169[16] = 0;
    v170.m256i_i64[1] = (__int64)v169;
    *((_QWORD *)&v183 + 1) = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    v170.m256i_i64[3] = (__int64)v169;
    v165 = v22;
    v189 = 32;
    v184 = 0;
    v185 = v15;
    v186 = 0;
    v188 = 0;
    v170.m256i_i64[0] = 16;
    v160 = (unsigned __int64)v11 + v14;
    *(_QWORD *)v169 = v11;
    *(_QWORD *)&v169[8] = v14;
    v157 = 0;
    v158 = 0;
    if ( v9.m128i_i64[0] )
    {
      v88 = (struct _RTL_AVL_ENTRY *)_mm_srli_si128(v9, 8).m128i_u64[0];
      v23 = v88;
      if ( v88 )
      {
        v37 = v9;
        v36 = v4;
        if ( (CmsAvlTableLite *)(*(_QWORD *)(*(unsigned __int8 *)(v9.m128i_i64[0] + 26) + v9.m128i_i64[0])
                               + *(_QWORD *)(*(unsigned __int8 *)(v9.m128i_i64[0] + 26) + v9.m128i_i64[0] + 8)) == v11 )
        {
          v157 = v9;
          v158 = v4;
          if ( (((_DWORD)v180 - 1) & 0xFFFFFFFD) == 0 )
          {
            v23 = RealSuccessor(v88);
            if ( !v23 )
            {
              v157.m128i_i64[1] = 0;
              v37 = (__m128i)v157.m128i_u64[0];
              v155 = (unsigned __int64)v11;
              v156 = v14;
              v9 = (__m128i)v157.m128i_u64[0];
              v180 = v4;
              CmsRowWithBuffer::Reset((CmsRowWithBuffer *)&v183);
              v35 = v156;
              v34 = v155;
              v11 = v164;
              v14 = v162;
              v38 = v160;
              goto LABEL_30;
            }
          }
          v34 = (unsigned __int64)v11;
          LODWORD(v183) = *((unsigned __int8 *)v23 + 27);
          v35 = v14;
          v89 = (char *)v23 + *((unsigned __int8 *)v23 + 26);
          LODWORD(v158) = 1;
          v36 = v158;
          *((_QWORD *)&v183 + 1) = v89;
          WORD2(v183) = 0;
          v4 = v158;
          v184 = *((unsigned __int16 *)v23 + 15);
          v90 = (unsigned __int64 *)((char *)v23 + *((unsigned __int8 *)v23 + 26));
          v157.m128i_i64[1] = (__int64)v23;
          v157.m128i_i64[0] = (__int64)v23;
          v37 = v157;
          v186 = v90;
          v155 = (unsigned __int64)v11;
          v156 = v14;
          v9 = v157;
          v91 = *v90;
          v180 = v158;
          if ( (CmsAvlTableLite *)v91 != v11 )
          {
            v38 = v160;
            if ( v91 < v160 )
            {
              v35 = v91 - (_QWORD)v11;
              v156 = v91 - (_QWORD)v11;
            }
            v185 = v16;
            P = v190;
            v39 = 0;
            *(_OWORD *)v166 = 0;
            DWORD1(v183) = (unsigned __int16)_mm_extract_epi16((__m128i)0LL, 2);
            v184 = 0;
            v186 = 0;
            v188 = 0;
            goto LABEL_28;
          }
        }
        else
        {
          LODWORD(v183) = *(unsigned __int8 *)(v9.m128i_i64[0] + 27);
          *((_QWORD *)&v183 + 1) = v9.m128i_i64[0] + *(unsigned __int8 *)(v9.m128i_i64[0] + 26);
          WORD2(v183) = 0;
          v184 = *(unsigned __int16 *)(v9.m128i_i64[0] + 30);
          v23 = (struct _RTL_AVL_ENTRY *)v9.m128i_i64[0];
          v90 = (unsigned __int64 *)(v9.m128i_i64[0] + *(unsigned __int8 *)(v9.m128i_i64[0] + 26));
LABEL_116:
          v186 = v90;
        }
        v93 = v90[1];
        v94 = v93 + *v90;
        v156 = v93;
        v95 = v90[2];
        v155 = v95;
        if ( !*(_BYTE *)(v165 + 56) )
        {
          v95 = *v90;
          v155 = *v90;
        }
        v9 = v37;
        v4 = v36;
        *(_OWORD *)v166 = 0;
        v180 = v36;
        if ( v160 > v94 )
        {
          v93 = v94 - *v90;
          v156 = v93;
          v185 = v19;
        }
        else
        {
          v185 = v18;
        }
        v96 = *((_QWORD *)&v163 + 1);
        P = v190;
        LODWORD(v183) = 0;
        v188 = 0;
        WORD2(v183) = _mm_extract_epi16((__m128i)0LL, 2);
        WORD3(v183) = HIWORD(v166[0]);
        v97 = v163;
        v186 = 0;
        v184 = 0;
        *((_QWORD *)&v183 + 1) = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        v189 = 32;
        if ( v95 < (unsigned __int64)v163 )
        {
          v96 = v163 - v95 + *((_QWORD *)&v163 + 1);
          v97 = v95;
          *(_QWORD *)&v163 = v95;
          *((_QWORD *)&v163 + 1) = v96;
        }
        if ( v95 + v93 > v96 + v97 )
          *((_QWORD *)&v163 + 1) = v95 + v93 - v97;
        if ( v23 )
          v98 = (char *)v23 + *((unsigned __int8 *)v23 + 26);
        else
          v98 = 0;
        v99 = (struct _RTL_AVL_ENTRY *)*((_QWORD *)v98 + 3);
        P = v190;
        v100 = v99;
        v166[0] = v99;
        v157.m128i_i64[1] = (__int64)&v155;
        v165 = *((_QWORD *)v161 + 1);
        v101 = (struct _MS_AVL_TABLE *)v165;
        v157.m128i_i64[0] = 16;
        v189 = 32;
        ++*(_DWORD *)(v165 + 36);
        v183 = 0;
        v184 = 0;
        v185 = v20;
        v186 = 0;
        v188 = 0;
        *((_QWORD *)&v158 + 1) = &v155;
        LODWORD(v158) = 16;
        DeleteNodeFromTree(v101, v100, 1u);
        --*(_DWORD *)(v165 + 32);
        CmsAvlTableLite::FreeIndexEntry(v166[0]);
        ++*(_DWORD *)(v165 + 40);
        if ( (v188 & 1) != 0 && P )
          ExFreePoolWithTag(P, 0);
        v35 = v156;
        v34 = v155;
        v11 = v164;
        v14 = v162;
        v38 = v160;
        P = v190;
        v184 = 0;
        v186 = 0;
        v188 = 0;
        v183 = 0;
        v185 = v21;
        goto LABEL_29;
      }
    }
    v23 = *(struct _RTL_AVL_ENTRY **)(v22 + 24);
    if ( !v23 )
    {
      v157.m128i_i64[0] = 0;
      LODWORD(v158) = 0;
      v24 = *(_DWORD *)(v22 + 48);
      v162 = (unsigned __int64)v11 + v14;
      v25 = -1;
      DWORD1(v158) = v24;
      goto LABEL_11;
    }
    while ( 1 )
    {
      v48 = (_QWORD *)((char *)v23 + *((unsigned __int8 *)v23 + 26));
      if ( (unsigned __int64)v11 >= *v48 )
        break;
      v47 = (struct _RTL_AVL_ENTRY *)*((_QWORD *)v23 + 1);
      if ( !v47 )
      {
        v49 = 2;
        LODWORD(v158) = 2;
        goto LABEL_49;
      }
LABEL_44:
      v23 = v47;
    }
    if ( (unsigned __int64)v11 < v48[1] + *v48 )
    {
      v157.m128i_i64[0] = (__int64)v23;
      LODWORD(v158) = 1;
      v157.m128i_i64[1] = (__int64)v23;
      v37 = v157;
      LODWORD(v183) = *((unsigned __int8 *)v23 + 27);
      *((_QWORD *)&v183 + 1) = (char *)v23 + *((unsigned __int8 *)v23 + 26);
      WORD2(v183) = 0;
      v184 = *((unsigned __int16 *)v23 + 15);
      v90 = (unsigned __int64 *)((char *)v23 + *((unsigned __int8 *)v23 + 26));
      DWORD1(v158) = *(_DWORD *)(v22 + 48);
      v36 = v158;
      goto LABEL_116;
    }
    v47 = (struct _RTL_AVL_ENTRY *)*((_QWORD *)v23 + 2);
    if ( v47 )
      goto LABEL_44;
    v49 = 3;
    LODWORD(v158) = 3;
LABEL_49:
    DWORD1(v158) = *(_DWORD *)(v22 + 48);
    v162 = v160;
    v25 = -1;
    v157.m128i_i64[1] = (__int64)v23;
    v157.m128i_i64[0] = 0;
    if ( v49 != 3 )
      goto LABEL_24;
    v50 = *((_QWORD *)v23 + 2);
    if ( v50 )
    {
      for ( ; *(_QWORD *)(v50 + 8); v50 = *(_QWORD *)(v50 + 8) )
        ;
      v23 = (struct _RTL_AVL_ENTRY *)v50;
    }
    else
    {
      v51 = *(struct _RTL_AVL_ENTRY **)v23;
      if ( *(struct _RTL_AVL_ENTRY **)(*(_QWORD *)v23 + 16LL) == v23 )
      {
        do
        {
          v52 = *(struct _RTL_AVL_ENTRY **)v51;
          v23 = v51;
          v51 = v52;
        }
        while ( *((struct _RTL_AVL_ENTRY **)v52 + 2) == v23 );
      }
      else
      {
        v52 = *(struct _RTL_AVL_ENTRY **)v23;
      }
      v23 = *((struct _RTL_AVL_ENTRY **)v52 + 1) == v23 ? v52 : 0LL;
    }
    if ( v23 )
    {
LABEL_24:
      LODWORD(v183) = *((unsigned __int8 *)v23 + 27);
      v32 = (char *)v23 + *((unsigned __int8 *)v23 + 26);
      LODWORD(v158) = 1;
      *((_QWORD *)&v183 + 1) = v32;
      WORD2(v183) = 0;
      v184 = *((unsigned __int16 *)v23 + 15);
      v33 = *((unsigned __int8 *)v23 + 26);
      v157.m128i_i64[1] = (__int64)v23;
      v186 = (unsigned __int64 *)((char *)v23 + v33);
      v157.m128i_i64[0] = (__int64)v23;
      v25 = *(_QWORD *)((char *)v23 + v33);
      goto LABEL_25;
    }
LABEL_11:
    v157.m128i_i64[1] = 0;
LABEL_25:
    v155 = (unsigned __int64)v11;
    v34 = (unsigned __int64)v11;
    v156 = v14;
    v35 = v14;
    v36 = v158;
    v37 = v157;
    v4 = v158;
    v9 = v157;
    v180 = v158;
    if ( v25 < v162 )
    {
      v35 = v25 - (_QWORD)v11;
      v156 = v25 - (_QWORD)v11;
    }
    v38 = v160;
    v39 = 0;
    P = v190;
    *(_OWORD *)v166 = 0;
    v184 = 0;
    v185 = v17;
    DWORD1(v183) = (unsigned __int16)_mm_extract_epi16((__m128i)0LL, 2);
    v186 = 0;
    v188 = 0;
LABEL_28:
    LODWORD(v183) = v39.m128i_i32[0];
    *((_QWORD *)&v183 + 1) = _mm_srli_si128(v39, 8).m128i_u64[0];
LABEL_29:
    v189 = 32;
LABEL_30:
    if ( v154 )
    {
      v181 = v37;
      v154 = 0;
      v182 = v36;
    }
    if ( v38 > v34 + v35 )
    {
      if ( (unsigned __int64)v11 <= v34 )
        v14 = v38 - (v34 + v35);
      else
        v14 += (unsigned __int64)v11 - v34 - v35;
      v162 = v14;
      v11 = (CmsAvlTableLite *)(v34 + v35);
      v164 = (CmsAvlTableLite *)(v34 + v35);
      if ( v14 )
      {
        v8 = v161;
        continue;
      }
    }
    break;
  }
  v7 = (const struct _RANGE *)v171;
  v5 = v159;
LABEL_34:
  v40 = *((_QWORD *)v7 + 1);
  v178 = *(CmsAvlTableLite **)v7;
  *(_QWORD *)&v179 = v40;
  *((_QWORD *)&v179 + 1) = v178;
  memset(&v170, 0, 24);
  if ( CmsAvlTableLite::SizeOfAllocationsOnLookaside2 < 0x40 )
  {
    Pool2 = (__m256i *)ExAllocatePool2(66, 64, 1766871885);
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
    v53 = qword_140262460;
    if ( *(_DWORD *)qword_140262460 < 0x40u )
    {
      v53 = 0;
      v54 = 80;
      goto LABEL_56;
    }
    if ( !*(_BYTE *)(qword_140262460 + 8) )
    {
      if ( (int)*(_QWORD *)(qword_140262460 + 88) > (int)HIDWORD(*(_QWORD *)(qword_140262460 + 88)) )
      {
        v92 = _InterlockedDecrement((volatile signed __int32 *)(qword_140262460 + 88));
        if ( v92 >= *(_DWORD *)(v53 + 92) && v92 >= 0 )
        {
          v141 = (__m256i *)ExpInterlockedPopEntrySList((PSLIST_HEADER)(v53 + 64));
          goto LABEL_213;
        }
        _InterlockedIncrement((volatile signed __int32 *)(v53 + 88));
      }
LABEL_110:
      v54 = *(unsigned int *)(v53 + 4);
LABEL_56:
      v55 = ExAllocatePool2(66, v54, 1766871885);
      Pool2 = (__m256i *)v55;
      if ( (v55 & 0xF) != 0 )
        goto LABEL_275;
      if ( !v55 )
        goto LABEL_215;
      goto LABEL_214;
    }
    v140 = (struct _NPAGED_LOOKASIDE_LIST *)(qword_140262460 + 64);
    if ( *(_BYTE *)(qword_140262460 + 9) )
      v141 = (__m256i *)ExAllocateFromNPagedLookasideList(v140);
    else
      v141 = (__m256i *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v140);
LABEL_213:
    Pool2 = v141;
    if ( v141 )
    {
LABEL_214:
      Pool2->m256i_i64[0] = v53;
      Pool2 = (__m256i *)((char *)Pool2 + 16);
LABEL_215:
      i = 0x4000;
      goto LABEL_194;
    }
    goto LABEL_110;
  }
  v42 = qword_140262458 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  if ( *(_DWORD *)v42 < 0x40u )
  {
    v42 = 0;
    v43 = 80;
    goto LABEL_38;
  }
  if ( !*(_BYTE *)(v42 + 8) )
  {
    if ( (int)*(_QWORD *)(v42 + 88) > (int)HIDWORD(*(_QWORD *)(v42 + 88)) )
    {
      v56 = _InterlockedDecrement((volatile signed __int32 *)(v42 + 88));
      if ( v56 >= *(_DWORD *)(v42 + 92) && v56 >= 0 )
      {
        v139 = (__m256i *)ExpInterlockedPopEntrySList((PSLIST_HEADER)(v42 + 64));
        goto LABEL_191;
      }
      _InterlockedIncrement((volatile signed __int32 *)(v42 + 88));
    }
LABEL_63:
    v43 = *(unsigned int *)(v42 + 4);
LABEL_38:
    v44 = ExAllocatePool2(66, v43, 1766871885);
    Pool2 = (__m256i *)v44;
    if ( (v44 & 0xF) == 0 )
    {
      if ( v44 )
        goto LABEL_192;
      goto LABEL_193;
    }
LABEL_275:
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  }
  v138 = (struct _NPAGED_LOOKASIDE_LIST *)(v42 + 64);
  if ( *(_BYTE *)(v42 + 9) )
    v139 = (__m256i *)ExAllocateFromNPagedLookasideList(v138);
  else
    v139 = (__m256i *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v138);
LABEL_191:
  Pool2 = v139;
  if ( !v139 )
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
  *(_QWORD *)v169 = 0;
  Pool2[1] = v170;
  Pool2->m256i_i16[13] = 4128;
  Pool2->m256i_i16[14] = i;
  Pool2->m256i_i16[15] = 32;
  *((_QWORD *)&v177 + 1) = Pool2;
  LODWORD(v175) = Pool2->m256i_u8[27];
  v58 = &Pool2->m256i_i8[Pool2->m256i_u8[26]];
  WORD2(v175) = 0;
  *((_QWORD *)&v175 + 1) = v58;
  v176 = Pool2->m256i_u16[15];
  *(_QWORD *)&v177 = (char *)Pool2 + Pool2->m256i_u8[26];
  *(_OWORD *)&v169[8] = 0;
  if ( CmsAvlTableLite::SizeOfAllocationsOnLookaside2 < 0x38 )
  {
    v62 = ExAllocatePool2(66, 56, 1766871885);
    if ( !v62 )
      goto LABEL_212;
    v41 = 0x8000;
    goto LABEL_85;
  }
  if ( CmsAvlTableLite::SizeOfAllocationsOnLookaside1 < 0x38 )
  {
    KeGetCurrentProcessorNumberEx(0);
    v63 = qword_140262460;
    if ( *(_DWORD *)qword_140262460 < 0x38u )
    {
      v63 = 0;
      v64 = 72;
      goto LABEL_75;
    }
    if ( !*(_BYTE *)(qword_140262460 + 8) )
    {
      if ( (int)*(_QWORD *)(qword_140262460 + 88) > (int)HIDWORD(*(_QWORD *)(qword_140262460 + 88)) )
      {
        v102 = _InterlockedDecrement((volatile signed __int32 *)(qword_140262460 + 88));
        if ( v102 >= *(_DWORD *)(v63 + 92) && v102 >= 0 )
        {
          v145 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v63 + 64));
          goto LABEL_216;
        }
        _InterlockedIncrement((volatile signed __int32 *)(v63 + 88));
      }
LABEL_137:
      v64 = *(unsigned int *)(v63 + 4);
LABEL_75:
      v65 = ExAllocatePool2(66, v64, 1766871885);
      v62 = v65;
      if ( (v65 & 0xF) != 0 )
        goto LABEL_278;
      if ( !v65 )
      {
LABEL_218:
        v41 = 0x4000;
        goto LABEL_211;
      }
LABEL_217:
      *(_QWORD *)v62 = v63;
      v62 += 16;
      goto LABEL_218;
    }
    v144 = (struct _NPAGED_LOOKASIDE_LIST *)(qword_140262460 + 64);
    if ( *(_BYTE *)(qword_140262460 + 9) )
      v145 = ExAllocateFromNPagedLookasideList(v144);
    else
      v145 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v144);
LABEL_216:
    v62 = (__int64)v145;
    if ( v145 )
      goto LABEL_217;
    goto LABEL_137;
  }
  v59 = qword_140262458 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  if ( *(_DWORD *)v59 < 0x38u )
  {
    v59 = 0;
    v60 = 72;
    goto LABEL_70;
  }
  if ( !*(_BYTE *)(v59 + 8) )
  {
    if ( (int)*(_QWORD *)(v59 + 88) > (int)HIDWORD(*(_QWORD *)(v59 + 88)) )
    {
      v66 = _InterlockedDecrement((volatile signed __int32 *)(v59 + 88));
      if ( v66 >= *(_DWORD *)(v59 + 92) && v66 >= 0 )
      {
        v143 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v59 + 64));
        goto LABEL_209;
      }
      _InterlockedIncrement((volatile signed __int32 *)(v59 + 88));
    }
LABEL_82:
    v60 = *(unsigned int *)(v59 + 4);
LABEL_70:
    v61 = ExAllocatePool2(66, v60, 1766871885);
    v62 = v61;
    if ( (v61 & 0xF) == 0 )
    {
      if ( v61 )
        goto LABEL_210;
      goto LABEL_211;
    }
LABEL_278:
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  }
  v142 = (struct _NPAGED_LOOKASIDE_LIST *)(v59 + 64);
  if ( *(_BYTE *)(v59 + 9) )
    v143 = ExAllocateFromNPagedLookasideList(v142);
  else
    v143 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v142);
LABEL_209:
  v62 = (__int64)v143;
  if ( !v143 )
    goto LABEL_82;
LABEL_210:
  *(_QWORD *)v62 = v59;
  v62 += 16;
LABEL_211:
  if ( !v62 )
  {
LABEL_212:
    v111 = -1073741670;
    goto LABEL_161;
  }
LABEL_85:
  v67 = *(_QWORD *)&v169[16];
  *(_OWORD *)(v62 + 32) = *(_OWORD *)v169;
  *(_QWORD *)(v62 + 48) = v67;
  *(_WORD *)(v62 + 26) = 4128;
  *(_WORD *)(v62 + 28) = v41;
  v68 = v161;
  *(_WORD *)(v62 + 30) = 24;
  *(_QWORD *)&v173[16] = v62;
  v172.m128i_i32[0] = *(unsigned __int8 *)(v62 + 27);
  v69 = v62 + *(unsigned __int8 *)(v62 + 26);
  v172.m128i_i16[2] = 0;
  v172.m128i_i64[1] = v69;
  *(_DWORD *)v173 = *(unsigned __int16 *)(v62 + 30);
  v70 = v62 + *(unsigned __int8 *)(v62 + 26);
  v71 = *(_QWORD *)v68;
  *(_QWORD *)&v173[8] = v70;
  (*(void (__fastcall **)(__int64, struct CmsTransactionCore *, CmsAvlTableLite **, __int128 *, _QWORD, _QWORD, __m128i *, __int64 *))(*(_QWORD *)v71 + 8LL))(
    v71,
    v5,
    &v178,
    &v175,
    0,
    0,
    &v181,
    &v174);
  v72 = (CmsAvlTableLite *)*((_QWORD *)v68 + 1);
  v73 = v159;
  P = v190;
  LODWORD(v183) = 0;
  v171 = 0;
  v189 = 32;
  DWORD1(v183) = (unsigned __int16)_mm_extract_epi16((__m128i)0LL, 2);
  v185 = DWORD1(v163);
  *((_QWORD *)&v183 + 1) = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  v184 = 0;
  v186 = 0;
  v188 = 0;
  v74 = v163;
  *(_OWORD *)v172.m128i_i64[1] = v163;
  v164 = v72;
  **(_OWORD **)&v173[8] = v74;
  v75 = *((unsigned __int8 *)v73 + 96);
  v157 = v172;
  v158 = *(_OWORD *)v173;
  v76 = 5;
  if ( (*(_DWORD *)v73 & 0x8000LL) == 0 )
    v76 = 2;
  if ( v75 < v76 )
  {
    v77 = (unsigned __int8)(v75 + 1);
    *((_BYTE *)v73 + 96) = v77;
    v78 = 5 * v77;
    if ( (unsigned __int8)v77 <= 2u )
      v79 = (char *)v73 - 24;
    else
      v79 = (char *)v73 + 784;
    v80 = &v79[8 * v78];
    *((_WORD *)v80 + 16) = 0;
    *(_QWORD *)v80 = &v157;
    *((_QWORD *)v80 + 1) = &CmsCountMap::PropertyDef;
    *((_QWORD *)v80 + 2) = &off_140200A80;
  }
  v81 = *((_QWORD *)v72 + 2);
  if ( !v81 )
  {
    v81 = 0;
    v103 = 0;
LABEL_142:
    v104 = 0;
    v105 = *((_BYTE *)v73 + 96);
    v106 = v72;
    v107 = v105 - 1;
    *((_BYTE *)v73 + 96) = v105 - 1;
    goto LABEL_180;
  }
  while ( 2 )
  {
    v82 = *((unsigned __int8 *)v73 + 96);
    v83 = 5 * v82;
    if ( (unsigned __int8)v82 <= 2u )
      v84 = v83 - 3;
    else
      v84 = v83 + 98;
    LODWORD(v171) = *(unsigned __int8 *)(v81 + 27);
    v85 = *(unsigned __int8 *)(v81 + 26);
    WORD2(v171) = 0;
    *((_QWORD *)&v171 + 1) = v81 + v85;
    v86 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int128 *))(**((_QWORD **)v73 + v84 + 2) + 8LL))(
            *((_QWORD *)v73 + v84 + 2),
            (__int64)v73 + 8 * v84,
            &v171);
    if ( !v86 )
    {
      v87 = *(_QWORD *)(v81 + 8);
      if ( !v87 )
      {
        v103 = 2;
        goto LABEL_141;
      }
LABEL_96:
      v73 = v159;
      v81 = v87;
      continue;
    }
    break;
  }
  if ( v86 == 1 )
  {
    v87 = *(_QWORD *)(v81 + 16);
    if ( !v87 )
    {
      v103 = 3;
LABEL_141:
      v73 = v159;
      goto LABEL_142;
    }
    goto LABEL_96;
  }
  v73 = v159;
  v104 = v81;
  v105 = *((_BYTE *)v159 + 96);
  v107 = v105 - 1;
  *((_BYTE *)v159 + 96) = v105 - 1;
  LODWORD(v183) = *(unsigned __int8 *)(v81 + 27);
  v150 = v81 + *(unsigned __int8 *)(v81 + 26);
  WORD2(v183) = 0;
  *((_QWORD *)&v183 + 1) = v150;
  v184 = *(unsigned __int16 *)(v81 + 30);
  v151 = (unsigned __int64 *)(v81 + *(unsigned __int8 *)(v81 + 26));
  v186 = v151;
  if ( *(_OWORD *)v151 == v163 )
  {
    CmsRowWithBuffer::Reset((CmsRowWithBuffer *)&v183);
    v111 = 0;
    goto LABEL_156;
  }
  v103 = 1;
  v106 = v72;
  if ( v151 )
  {
    memset(&v170, 0, sizeof(v170));
    v129 = CmsAvlTableLite::AddToIndexEx(
             v72,
             v73,
             (const struct SmsInternalPropertyDef *)&CmsCountMap::PropertyDef,
             (struct _CmsRow *)&v157,
             (struct _SmsQuickIndex *)&v170,
             (struct _SmsPreAllocatedRow *)&v172);
    v110 = v170.m256i_i64[0];
    v111 = v129;
  }
  else
  {
LABEL_180:
    v108 = 0;
    v110 = *(_QWORD *)&v173[16];
    v119 = 0;
    v13 = (*(_DWORD *)v73 & 0x8000LL) == 0;
    LODWORD(v160) = 0;
    v45 = 5;
    v165 = 0;
    if ( v13 )
      v45 = 2;
    *(_QWORD *)&v171 = *(_QWORD *)&v173[16];
    if ( v107 < v45 )
    {
      *((_BYTE *)v73 + 96) = v105;
      v120 = (char *)v73 + 40 * v105;
      if ( v105 <= 2u )
        v121 = v120 - 24;
      else
        v121 = v120 + 784;
      *(_QWORD *)v121 = &v172;
      *((_WORD *)v121 + 16) = 0;
      *((_QWORD *)v121 + 1) = &CmsCountMap::PropertyDef;
      *((_QWORD *)v121 + 2) = &off_140200A80;
    }
    v122 = *((unsigned __int8 *)v73 + 96);
    i = (__int64)v73 + 40 * v122;
    if ( (unsigned __int8)v122 > 2u )
      i += 808;
    *(_QWORD *)i = v110;
    if ( v81 )
    {
      if ( v104 )
      {
        v109 = MsLookupElementGenericTablePartialAvl<MST_AVL_DEFAULT_PROTOTYPE>(
                 (_DWORD)v106,
                 (_DWORD)v73,
                 v45,
                 v104,
                 (__int64)&v165,
                 (__int64)&v160);
        v108 = v160;
        v119 = v165;
        v123 = v164;
        goto LABEL_149;
      }
      v123 = v164;
      v119 = v81;
      v108 = v103;
LABEL_174:
      ++*((_DWORD *)v106 + 10);
      v111 = 0;
      if ( v108 != 1 )
      {
        v118 = (_OWORD *)((__int64 (__fastcall *)(CmsAvlTableLite *, _QWORD, struct CmsTransactionCore *))qword_140262628)(
                           v106,
                           0,
                           v73);
        if ( v118 )
        {
          *v118 = 0;
          *(_OWORD *)((char *)v118 + 10) = 0;
          ++*((_DWORD *)v106 + 8);
          if ( v108 )
          {
            if ( v108 == 2 )
              *(_QWORD *)(v119 + 8) = v118;
            else
              *(_QWORD *)(v119 + 16) = v118;
            *(_QWORD *)v118 = v119;
            *((_BYTE *)v123 + 24) = -1;
            for ( i = *(_QWORD *)v118; ; v119 = i )
            {
              v13 = *(_QWORD *)(i + 8) == (_QWORD)v118;
              v152 = -1;
              v153 = *(_BYTE *)(v119 + 24);
              if ( !v13 )
                v152 = 1;
              if ( v153 )
                break;
              i = *(_QWORD *)v119;
              v118 = (_OWORD *)v119;
              *(_BYTE *)(v119 + 24) = v152;
            }
            v110 = v171;
            if ( v153 == v152 )
              RebalanceNode((struct _RTL_AVL_ENTRY *)v119);
            else
              *(_BYTE *)(v119 + 24) = 0;
          }
          else
          {
            *((_QWORD *)v123 + 2) = v118;
            *(_QWORD *)v118 = v106;
          }
        }
      }
      --*((_BYTE *)v159 + 96);
    }
    else
    {
      v123 = v164;
      v124 = *((_QWORD *)v164 + 2);
      if ( v124 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            v125 = *((unsigned __int8 *)v73 + 96);
            v119 = v124;
            v126 = 5 * v125;
            v127 = (unsigned __int8)v125 <= 2u ? v126 - 3 : v126 + 98;
            LODWORD(v166[0]) = *(unsigned __int8 *)(v119 + 27);
            v166[1] = (struct _RTL_AVL_ENTRY *)(v119 + *(unsigned __int8 *)(v119 + 26));
            WORD2(v166[0]) = 0;
            v128 = (*(__int64 (__fastcall **)(_QWORD, __int64, struct _RTL_AVL_ENTRY **, __int64))(**((_QWORD **)v73 + v127 + 2)
                                                                                                 + 8LL))(
                     *((_QWORD *)v73 + v127 + 2),
                     (__int64)v73 + 8 * v127,
                     v166,
                     v103);
            if ( v128 )
              break;
            v124 = *(_QWORD *)(v119 + 8);
            if ( !v124 )
            {
              v108 = 2;
              goto LABEL_148;
            }
            v73 = v159;
          }
          if ( v128 != 1 )
            break;
          v124 = *(_QWORD *)(v119 + 16);
          if ( !v124 )
          {
            v108 = 3;
            goto LABEL_148;
          }
          v73 = v159;
        }
        v108 = 1;
        v109 = v119;
      }
      else
      {
LABEL_148:
        v109 = 0;
      }
LABEL_149:
      if ( !v109 )
      {
        v73 = v159;
        goto LABEL_174;
      }
      v110 = v109;
      v111 = -1073741771;
      --*((_BYTE *)v159 + 96);
    }
  }
  v104 = 0;
  if ( v111 >= 0 )
  {
    v104 = v110;
    *(_QWORD *)&v173[16] = 0;
  }
  if ( (v188 & 1) != 0 && P )
    ExFreePoolWithTag(P, 0);
LABEL_156:
  if ( v174 )
    v112 = v174 + *(unsigned __int8 *)(v174 + 26);
  else
    v112 = 0;
  if ( v104 )
    v113 = v104 + *(unsigned __int8 *)(v104 + 26);
  else
    v113 = 0;
  *(_QWORD *)(v112 + 24) = v104;
  *(_QWORD *)(v113 + 16) = v174;
LABEL_161:
  v114 = (_WORD *)*((_QWORD *)&v177 + 1);
  if ( *((_QWORD *)&v177 + 1) )
  {
    *((_QWORD *)&v175 + 1) = 0;
    WORD2(v175) = 0;
    v177 = 0u;
    if ( (v114[14] & 0x6000) != 0 )
    {
      v115 = *((_QWORD *)v114 - 2);
      v116 = (struct _SLIST_ENTRY *)(v114 - 8);
      if ( v115 )
      {
        if ( *(_BYTE *)(v115 + 8) )
        {
          v117 = (struct _NPAGED_LOOKASIDE_LIST *)(v115 + 64);
          if ( *(_BYTE *)(v115 + 9) )
            ExFreeToNPagedLookasideList(v117, v116);
          else
            ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v117, v116);
        }
        else
        {
          v146 = *(_QWORD *)(v115 + 88);
          if ( (int)v146 < *(_DWORD *)(v115 + 80) || SHIDWORD(v146) >= (int)v146 )
          {
            ExpInterlockedPushEntrySList((PSLIST_HEADER)(v115 + 64), v116);
            _InterlockedIncrement((volatile signed __int32 *)(v115 + 88));
          }
          else
          {
            ExFreePoolWithTag(v116, 0);
          }
        }
        goto LABEL_167;
      }
      v114 -= 8;
    }
    operator delete(v114);
  }
LABEL_167:
  if ( *(_QWORD *)&v173[16] )
    CmsAvlTableLite::CleanupPreAllocatedRow((CmsAvlTableLite *)v114, (struct _SmsPreAllocatedRow *)&v172, v45);
  if ( v111 < 0 )
    CmsRangeAndCountMap::DeleteAll(v161, (struct CmsTransactionCore *)i);
}

```

## disassembly

```asm
0x140073080  push    rbp
0x140073082  push    rbx
0x140073083  push    rsi
0x140073084  push    rdi
0x140073085  push    r12
0x140073087  push    r13
0x140073089  push    r14
0x14007308b  push    r15
0x14007308d  lea     rbp, [rsp-188h]
0x140073095  sub     rsp, 288h
0x14007309c  movaps  [rsp+2C0h+var_70], xmm8
0x1400730a5  movaps  [rsp+2C0h+var_80], xmm9
0x1400730ae  mov     rax, cs:__security_cookie
0x1400730b5  xor     rax, rsp
0x1400730b8  mov     [rbp+1C0h+var_90], rax
0x1400730bf  xor     r15d, r15d
0x1400730c2  mov     [rbp+1C0h+var_238], rdx
0x1400730c6  xorps   xmm1, xmm1
0x1400730c9  xorps   xmm0, xmm0
0x1400730cc  xorps   xmm8, xmm8
0x1400730d0  mov     r12, rdx
0x1400730d3  mov     rdi, r9
0x1400730d6  mov     rsi, r8
0x1400730d9  mov     rdx, rcx
0x1400730dc  mov     qword ptr [rbp+1C0h+var_1A0], r8
0x1400730e0  xorps   xmm9, xmm9
0x1400730e4  mov     [rbp+1C0h+var_228], rcx
0x1400730e8  mov     r13, 0FFFFFFFFFFFFFFFFh
0x1400730ef  mov     [rbp+1C0h+var_138], r15
0x1400730f6  movdqu  [rbp+1C0h+var_130], xmm0
0x1400730fe  mov     [rsp+2C0h+var_268], r15
0x140073103  movups  xmm0, xmmword ptr [r8]
0x140073107  mov     [rsp+2C0h+var_260], r15
0x14007310c  movups  [rbp+1C0h+var_110], xmm8
0x140073114  mov     qword ptr [rsp+2C0h+var_258], r15
0x140073119  movups  [rbp+1C0h+var_218], xmm0
0x14007311d  mov     [rbp+1C0h+var_168], r15
0x140073121  xorps   xmm0, xmm0
0x140073124  mov     [rbp+1C0h+var_150], r15d
0x140073128  movdqu  [rsp+2C0h+var_248], xmm0
0x14007312e  mov     dword ptr [rbp+1C0h+var_180], r15d
0x140073132  movups  [rbp+1C0h+var_160], xmm0
0x140073136  movups  [rbp+1C0h+var_190], xmm0
0x14007313a  movups  [rbp+1C0h+var_100], xmm1
0x140073141  movups  [rbp+1C0h+var_F0], xmm1
0x140073148  movdqu  [rbp+1C0h+var_148], xmm1
0x14007314d  movdqu  [rbp+1C0h+var_178], xmm1
0x140073152  cmp     [rcx+10h], r15d
0x140073156  ja      loc_1400732C0
0x14007315c  mov     [rsp+2C0h+var_270], 1
0x140073161  test    rdi, rdi
0x140073164  jnz     loc_140074680
0x14007316a  mov     r8, [rsi]
0x14007316d  mov     r11, [rsi+8]
0x140073171  mov     [rbp+1C0h+var_208], r8
0x140073175  test    r8, r8
0x140073178  jz      short loc_140073184
0x14007317a  dec     r8
0x14007317d  mov     [rbp+1C0h+var_208], r8
0x140073181  inc     r11
0x140073184  add     r11, 1
0x140073188  mov     r14d, 20h ; ' '
0x14007318e  mov     [rbp+1C0h+var_220], r11
0x140073192  mov     r9d, 18h
0x140073198  jz      loc_14007354A
0x14007319e  mov     r14d, dword ptr [rbp+1C0h+var_218+4]
0x1400731a2  mov     r12d, dword ptr [rbp+1C0h+var_218+4]
0x1400731a6  mov     edi, dword ptr [rbp+1C0h+var_218+4]
0x1400731a9  mov     esi, dword ptr [rbp+1C0h+var_218+4]
0x1400731ac  mov     r13d, dword ptr [rbp+1C0h+var_218+4]
0x1400731b0  mov     r15d, dword ptr [rbp+1C0h+var_218+4]
0x1400731b4  mov     ebx, dword ptr [rbp+1C0h+var_218+4]
0x1400731b7  movaps  [rsp+2C0h+var_50], xmm6
0x1400731bf  movaps  [rsp+2C0h+var_60], xmm7
0x1400731c7  mov     r10, [rdx]
0x1400731ca  lea     rax, [rbp+1C0h+var_B0]
0x1400731d1  xorps   xmm0, xmm0
0x1400731d4  mov     [rbp+1C0h+P], rax
0x1400731db  pextrw  eax, xmm0, 2
0x1400731e0  movups  xmmword ptr [rbp+1C0h+var_1F8], xmm0
0x1400731e4  lea     rcx, [r11+r8]
0x1400731e8  mov     dword ptr [rbp+1C0h+var_1B0], r9d
0x1400731ec  movss   dword ptr [rbp+1C0h+var_E0], xmm0
0x1400731f4  movq    r9, xmm9
0x1400731f9  mov     word ptr [rbp+1C0h+var_E0+4], ax
0x140073200  movzx   eax, word ptr [rbp+1C0h+var_1F8+6]
0x140073204  mov     word ptr [rbp+1C0h+var_E0+6], ax
0x14007320b  xor     eax, eax
0x14007320d  mov     [rbp+1C0h+var_1C8], rax
0x140073211  lea     rax, [rbp+1C0h+var_1D8]
0x140073215  psrldq  xmm0, 8
0x14007321a  mov     qword ptr [rbp+1C0h+var_1C0+8], rax
0x14007321e  lea     rax, [rbp+1C0h+var_1D8]
0x140073222  movq    qword ptr [rbp+1C0h+var_E0+8], xmm0
0x14007322a  xorps   xmm0, xmm0
0x14007322d  mov     qword ptr [rbp+1C0h+var_1B0+8], rax
0x140073231  mov     [rbp+1C0h+var_200], r10
0x140073235  mov     [rbp+1C0h+var_B4], 20h ; ' '
0x14007323f  mov     [rbp+1C0h+var_D0], 0
0x140073249  mov     [rbp+1C0h+var_CC], r14d
0x140073250  mov     [rbp+1C0h+var_C8], 0
0x14007325b  mov     [rbp+1C0h+var_B8], 0
0x140073262  mov     qword ptr [rbp+1C0h+var_1C0], 10h
0x14007326a  mov     [rbp+1C0h+var_230], rcx
0x14007326e  mov     qword ptr [rbp+1C0h+var_1D8], r8
0x140073272  mov     qword ptr [rbp+1C0h+var_1D8+8], r11
0x140073276  movups  [rsp+2C0h+var_258], xmm0
0x14007327b  movups  [rsp+2C0h+var_248], xmm0
0x140073280  test    r9, r9
0x140073283  jnz     loc_140073B4D
0x140073289  mov     rax, [r10+18h]
0x14007328d  test    rax, rax
0x140073290  jnz     loc_140073622
0x140073296  mov     qword ptr [rsp+2C0h+var_258], rax
0x14007329b  mov     dword ptr [rsp+2C0h+var_248], eax
0x14007329f  mov     eax, [r10+30h]
0x1400732a3  mov     [rbp+1C0h+var_220], rcx
0x1400732a7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400732ae  mov     dword ptr [rsp+2C0h+var_248+4], eax
0x1400732b2  mov     qword ptr [rsp+2C0h+var_258+8], 0
0x1400732bb  jmp     loc_140073454
0x1400732c0  mov     rax, [rcx+8]
0x1400732c4  mov     ecx, [rax+20h]
0x1400732c7  cmp     ecx, [rdx+10h]
0x1400732ca  jb      loc_14007315C
0x1400732d0  mov     rbx, [r8]
0x1400732d3  test    rbx, rbx
0x1400732d6  jnz     loc_14007449A
0x1400732dc  mov     rbx, [rsi]
0x1400732df  add     rbx, [rsi+8]
0x1400732e3  cmp     rbx, r13
0x1400732e6  jnb     loc_1401F6CC6
0x1400732ec  mov     r14, [rdx]
0x1400732ef  lea     rcx, [rbp+1C0h+var_E0]; this
0x1400732f6  xorps   xmm0, xmm0
0x1400732f9  mov     [rbp+1C0h+var_D0], r15d
0x140073300  movups  [rbp+1C0h+var_E0], xmm0
0x140073307  mov     [rbp+1C0h+var_C8], r15
0x14007330e  mov     [rbp+1C0h+P], r15
0x140073315  mov     [rbp+1C0h+var_B8], 0
0x14007331c  mov     [rbp+1C0h+var_B4], r15d
0x140073323  call    ?Reset@CmsRowWithBuffer@@QEAAXXZ; CmsRowWithBuffer::Reset(void)
0x140073328  xorps   xmm0, xmm0
0x14007332b  mov     [rbp+1C0h+var_1E8], r15d
0x14007332f  xor     eax, eax
0x140073331  mov     [rbp+1C0h+var_1E0], r15
0x140073335  xor     r8d, r8d; struct _SmsPreAllocatedRow *
0x140073338  mov     [rbp+1C0h+var_1C8], rax
0x14007333c  lea     rdx, [rbp+1C0h+var_1D8]; struct SmsRangeMapEntry *
0x140073340  mov     qword ptr [rbp+1C0h+var_1D8], rbx
0x140073344  lea     rcx, [rbp+1C0h+var_1F8]; struct _CmsRow *
0x140073348  mov     qword ptr [rbp+1C0h+var_1D8+8], 1
0x140073350  movups  xmmword ptr [rbp+1C0h+var_1F8], xmm0
0x140073354  lea     r15, [rbx+1]
0x140073358  movups  [rbp+1C0h+var_1C0], xmm0
0x14007335c  movups  [rbp+1C0h+var_1B0], xmm0
0x140073360  call    ?SetRangeMapEntryRowHlpr@@YAXPEAU_CmsRow@@PEAUSmsRangeMapEntry@@PEAU_SmsPreAllocatedRow@@@Z; SetRangeMapEntryRowHlpr(_CmsRow *,SmsRangeMapEntry *,_SmsPreAllocatedRow *)
0x140073365  lea     rax, [rbp+1C0h+var_1C0]
0x140073369  mov     rdx, r12; struct CmsTransactionCore *
0x14007336c  mov     [rsp+2C0h+var_298], rax; struct _SmsQuickIndex *
0x140073371  lea     rcx, [r14+8]; this
0x140073375  lea     rax, [rbp+1C0h+var_E0]
0x14007337c  lea     r9, [rbp+1C0h+var_1F8]; struct _CmsRow *
0x140073380  mov     [rsp+2C0h+var_2A0], rax; struct _CmsRow *
0x140073385  lea     r8, ?PropertyDef@CmsRangeMap@@1USmsInternalPropertyDef@@B; struct SmsInternalPropertyDef *
0x14007338c  call    ?PinInIndexEx@CmsAvlTableLite@@QEAAJPEAVCmsTransactionCore@@PEBUSmsInternalPropertyDef@@PEAU_CmsRow@@2PEAU_SmsQuickIndex@@@Z; CmsAvlTableLite::PinInIndexEx(CmsTransactionCore *,SmsInternalPropertyDef const *,_CmsRow *,_CmsRow *,_SmsQuickIndex *)
0x140073391  test    eax, eax
0x140073393  jz      loc_1400745FE
0x140073399  lea     rax, [rbp+1C0h+var_1C0]
0x14007339d  xor     r9d, r9d
0x1400733a0  lea     r8, [rbp+1C0h+var_E0]
0x1400733a7  mov     [rsp+2C0h+var_2A0], rax
0x1400733ac  mov     edx, 1
0x1400733b1  mov     r14, r13
0x1400733b4  call    ?PinNextInIndex@CmsAvlTableLite@@QEAAJW4_EMS_CURSOR_FLAGS@@PEAU_CmsRow@@PEAUSmsLookupStack@@PEAU_SmsQuickIndex@@@Z; CmsAvlTableLite::PinNextInIndex(_EMS_CURSOR_FLAGS,_CmsRow *,SmsLookupStack *,_SmsQuickIndex *)
0x1400733b9  test    eax, eax
0x1400733bb  jnz     short loc_1400733C7
0x1400733bd  mov     rax, [rbp+1C0h+var_C8]
0x1400733c4  mov     r14, [rax]
0x1400733c7  mov     [rsp+2C0h+var_268], rbx
0x1400733cc  mov     [rsp+2C0h+var_260], 1
0x1400733d5  cmp     r14, r15
0x1400733d8  jb      loc_140074673
0x1400733de  lea     rcx, [rbp+1C0h+var_E0]; this
0x1400733e5  call    ?Reset@CmsRowWithBuffer@@QEAAXXZ; CmsRowWithBuffer::Reset(void)
0x1400733ea  nop
0x1400733eb  jmp     loc_1401F6CC6
0x1400733f0  cmp     [r9+8], rax
0x1400733f4  jnz     loc_140074041
0x1400733fa  mov     rax, r9
0x1400733fd  test    rax, rax
0x140073400  jz      loc_1400732B2
0x140073406  movzx   ecx, byte ptr [rax+1Bh]
0x14007340a  mov     dword ptr [rbp+1C0h+var_E0], ecx
0x140073410  movzx   ecx, byte ptr [rax+1Ah]
0x140073414  add     rcx, rax
0x140073417  mov     dword ptr [rsp+2C0h+var_248], 1
0x14007341f  mov     qword ptr [rbp+1C0h+var_E0+8], rcx
0x140073426  xor     ecx, ecx
0x140073428  mov     word ptr [rbp+1C0h+var_E0+4], cx
0x14007342f  movzx   ecx, word ptr [rax+1Eh]
0x140073433  mov     [rbp+1C0h+var_D0], ecx
0x140073439  movzx   ecx, byte ptr [rax+1Ah]
0x14007343d  add     rcx, rax
0x140073440  mov     qword ptr [rsp+2C0h+var_258+8], rax
0x140073445  mov     [rbp+1C0h+var_C8], rcx
0x14007344c  mov     qword ptr [rsp+2C0h+var_258], rax
0x140073451  mov     rcx, [rcx]
0x140073454  mov     rax, [rbp+1C0h+var_220]
0x140073458  mov     [rsp+2C0h+var_268], r8
0x14007345d  mov     r10, r8
0x140073460  mov     [rsp+2C0h+var_260], r11
0x140073465  mov     r9, r11
0x140073468  movups  xmm7, [rsp+2C0h+var_248]
0x14007346d  movups  xmm6, [rsp+2C0h+var_258]
0x140073472  movups  xmm8, xmm7
0x140073476  movups  xmm9, xmm6
0x14007347a  movups  [rbp+1C0h+var_110], xmm7
0x140073481  cmp     rcx, rax
0x140073484  jb      loc_1400746C6
0x14007348a  mov     rdx, [rbp+1C0h+var_230]
0x14007348e  lea     rax, [rbp+1C0h+var_B0]
0x140073495  xorps   xmm0, xmm0
0x140073498  mov     [rbp+1C0h+P], rax
0x14007349f  pextrw  eax, xmm0, 2
0x1400734a4  movups  xmmword ptr [rbp+1C0h+var_1F8], xmm0
0x1400734a8  mov     [rbp+1C0h+var_D0], 0
0x1400734b2  mov     [rbp+1C0h+var_CC], edi
0x1400734b8  mov     word ptr [rbp+1C0h+var_E0+4], ax
0x1400734bf  movzx   eax, word ptr [rbp+1C0h+var_1F8+6]
0x1400734c3  mov     word ptr [rbp+1C0h+var_E0+6], ax
0x1400734ca  mov     [rbp+1C0h+var_C8], 0
0x1400734d5  mov     [rbp+1C0h+var_B8], 0
0x1400734dc  movss   dword ptr [rbp+1C0h+var_E0], xmm0
0x1400734e4  psrldq  xmm0, 8
0x1400734e9  movq    qword ptr [rbp+1C0h+var_E0+8], xmm0
0x1400734f1  mov     [rbp+1C0h+var_B4], 20h ; ' '
0x1400734fb  cmp     [rsp+2C0h+var_270], 0
0x140073500  jz      short loc_140073515
0x140073502  movups  [rbp+1C0h+var_100], xmm6
0x140073509  mov     [rsp+2C0h+var_270], 0
0x14007350e  movups  [rbp+1C0h+var_F0], xmm7
0x140073515  lea     rax, [r10+r9]
0x140073519  cmp     rdx, rax
0x14007351c  ja      loc_1400746D6
0x140073522  mov     rsi, qword ptr [rbp+1C0h+var_1A0]
0x140073526  mov     r13, 0FFFFFFFFFFFFFFFFh
0x14007352d  mov     r12, [rbp+1C0h+var_238]
0x140073531  xor     r15d, r15d
0x140073534  movaps  xmm7, [rsp+2C0h+var_60]
0x14007353c  mov     r14d, 20h ; ' '
0x140073542  movaps  xmm6, [rsp+2C0h+var_50]
0x14007354a  cmp     cs:?SizeOfAllocationsOnLookaside2@CmsAvlTableLite@@2KA, 40h ; '@'; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside2
0x140073551  xorps   xmm0, xmm0
0x140073554  mov     rcx, [rsi]
0x140073557  mov     rax, [rsi+8]
0x14007355b  mov     [rbp+1C0h+var_138], rcx
0x140073562  mov     qword ptr [rbp+1C0h+var_130], rax
0x140073569  mov     qword ptr [rbp+1C0h+var_130+8], rcx
0x140073570  movdqu  [rbp+1C0h+var_1C0+8], xmm0
0x140073575  mov     qword ptr [rbp+1C0h+var_1C0], r15
0x140073579  jb      loc_140073749
0x14007357f  xor     ecx, ecx; ProcNumber
0x140073581  mov     esi, 4000h
0x140073586  cmp     cs:?SizeOfAllocationsOnLookaside1@CmsAvlTableLite@@2KA, 40h ; '@'; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside1
0x14007358d  mov     ebx, 2000h
0x140073592  jb      loc_1400736B7
0x140073598  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14007359f  nop     dword ptr [rax+rax+00h]
0x1400735a4  xor     edx, edx
0x1400735a6  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x1400735ac  lea     rdi, [rdx+rdx*2]
0x1400735b0  shl     rdi, 6
0x1400735b4  add     rdi, cs:qword_140262458
0x1400735bb  cmp     dword ptr [rdi], 40h ; '@'
0x1400735be  jnb     loc_14007370B
0x1400735c4  mov     rdi, r15
0x1400735c7  mov     edx, 50h ; 'P'
0x1400735cc  mov     ecx, 42h ; 'B'
0x1400735d1  mov     r8d, 6950534Dh
0x1400735d7  call    cs:__imp_ExAllocatePool2
0x1400735de  nop     dword ptr [rax+rax+00h]
0x1400735e3  mov     rcx, rax
0x1400735e6  test    al, 0Fh
0x1400735e8  jnz     loc_1401F6D84
0x1400735ee  test    rax, rax
0x1400735f1  jz      loc_140074336
0x1400735f7  jmp     loc_14007432F
0x1400735fc  mov     rdx, [rcx]
0x1400735ff  cmp     r8, rdx
0x140073602  jb      short loc_14007362B
0x140073604  add     rdx, [rcx+8]
0x140073608  cmp     r8, rdx
0x14007360b  jb      loc_140073D27
0x140073611  mov     rcx, [rax+10h]
0x140073615  test    rcx, rcx
0x140073618  jz      short loc_140073641
0x14007361a  mov     rax, rcx
0x14007361d  test    rcx, rcx
0x140073620  jz      short loc_1400735FC
  ... truncated ...
```
