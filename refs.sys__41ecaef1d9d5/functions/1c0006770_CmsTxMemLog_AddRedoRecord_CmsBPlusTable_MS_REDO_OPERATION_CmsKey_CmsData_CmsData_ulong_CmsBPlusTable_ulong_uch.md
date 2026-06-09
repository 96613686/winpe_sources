# CmsTxMemLog::AddRedoRecord(CmsBPlusTable *,_MS_REDO_OPERATION,_CmsKey *,_CmsData *,_CmsData *,ulong,CmsBPlusTable *,ulong,uchar,long *)

- ea: `0x1c0006770`
- end: `0x1c00071bf`
- name: `?AddRedoRecord@CmsTxMemLog@@QEAAJPEAVCmsBPlusTable@@W4_MS_REDO_OPERATION@@PEAU_CmsKey@@PEAU_CmsData@@3K0KEPEAJ@Z`
- size: `2639`
- prototype: ``
- caller_count: `4`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c00059f4`
- `0x1c0006110`
- `0x1c005c1e4`
- `0x1c00e595c`

## callees

- `0x1c0002b40`
- `0x1c0006770`
- `0x1c0037038`
- `0x1c0038698`
- `0x1c004e92c`
- `0x1c0062ed8`
- `0x1c0068960`
- `0x1c006ac80`
- `0x1c006acc0`
- `0x1c006af80`
- `0x1c00dfe1c`
- `0x1c00dff44`
- `0x1c00e03b4`
- `0x1c00e0574`
- `0x1c00e0800`
- `0x1c00e5bcc`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0006902`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c006ef61`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0006902`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c006ef61`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006ef7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006ef7b`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c006f04a`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c006f04a`
- `ntoskrnl!KeSetEvent` at `0x1c006f0a2`
- `ntoskrnl!KeSetEvent` at `0x1c006f0a2`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00069b8`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c006ef31`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00069b8`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c006ef31`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0006d62`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0006d62`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0006dea`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0006dea`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c000694b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c000694b`

## pseudocode

```c
__int64 __fastcall CmsTxMemLog::AddRedoRecord(
        __int64 a1,
        __int64 a2,
        int a3,
        _DWORD *a4,
        unsigned int *a5,
        int *a6,
        unsigned int a7,
        struct CmsBPlusTable *a8,
        __int64 a9,
        char a10,
        volatile signed __int32 *a11)
{
  int v12; // esi
  unsigned int *v13; // r11
  __int64 *v14; // rdi
  unsigned int v15; // r15d
  struct CmsBPlusTable *v16; // rdx
  __int64 v17; // rax
  unsigned int v18; // ebx
  __int64 v19; // rax
  void (__fastcall *v20)(__int64 *, _QWORD, __int128 *, int *); // rax
  unsigned int v21; // r10d
  unsigned int v22; // ebx
  __int64 v23; // r13
  __int64 v24; // r14
  CmsDurableLog *v25; // r12
  unsigned int v26; // ebx
  struct _SmsRedoBlock *v27; // r15
  unsigned int v28; // ebx
  struct _SmsRedoBlock *PoolWithTag; // rax
  unsigned int v30; // esi
  ULONG CurrentProcessorNumber; // eax
  unsigned int v32; // ecx
  unsigned int *v33; // rbx
  struct _PAGED_LOOKASIDE_LIST *v34; // rcx
  _QWORD *v35; // rax
  _QWORD *v36; // rax
  _QWORD *v37; // rax
  __int64 v38; // rbx
  int v39; // r9d
  int v40; // eax
  unsigned int v41; // r10d
  __int64 v42; // rcx
  __int64 v43; // r12
  unsigned __int8 *v44; // rdi
  __int64 v45; // r12
  __int64 v46; // rax
  unsigned __int8 *v47; // r8
  __int64 v48; // rax
  __int64 v49; // rcx
  __int64 i; // rcx
  __int64 v51; // xmm0_8
  __int64 v52; // rax
  __int64 v53; // rcx
  __int64 j; // rcx
  __int64 v55; // rcx
  int v56; // edx
  _OWORD *v57; // rcx
  unsigned int v58; // eax
  _DWORD *v59; // rsi
  unsigned int v60; // r14d
  __int64 v61; // r15
  int v62; // r12d
  unsigned __int8 *v63; // r13
  void (__fastcall *v64)(__int64, _QWORD, size_t *, __int64 *); // rax
  __int64 v65; // xmm0_8
  unsigned int v66; // ecx
  const void *v67; // rdx
  int v68; // eax
  unsigned int v69; // edi
  unsigned int v70; // ecx
  const void *v71; // rdx
  unsigned int v72; // esi
  __int64 v73; // rcx
  __int64 v74; // r13
  __int64 v75; // rax
  volatile signed __int32 *v76; // rcx
  char v77; // cl
  CmsDurableLog *v78; // rdx
  unsigned int v79; // r12d
  __int64 v80; // rsi
  KIRQL v81; // al
  __int64 v82; // rdx
  KIRQL v83; // r10
  __int64 v84; // r9
  __int64 v85; // r8
  __int64 v86; // r14
  __int64 v87; // rdi
  __int64 v88; // rdi
  __int64 v89; // rax
  unsigned __int64 v90; // r14
  unsigned __int64 v91; // rax
  unsigned __int64 v92; // rax
  bool v93; // zf
  __int64 v94; // rax
  __int64 v95; // rdx
  int *v97; // rcx
  __int64 v98; // rdx
  int v99; // eax
  unsigned int *v100; // r13
  _DWORD *v101; // rdx
  unsigned int v102; // ecx
  const void *v103; // r9
  unsigned int v104; // esi
  __m128i si128; // xmm6
  __m128i v106; // xmm5
  __m128i v107; // xmm7
  __m128i v108; // xmm4
  unsigned int v109; // r14d
  __int64 v110; // r9
  __m128i v111; // xmm3
  __m128i v112; // xmm0
  __int64 v113; // r9
  __int64 v114; // rdx
  __int64 v115; // rcx
  __m128i v116; // xmm3
  __m128i v117; // xmm4
  __m128i v118; // xmm4
  __int64 v119; // rcx
  unsigned int v120; // eax
  struct _SmsRedoBlock *PreallocatedRedo; // rax
  int v122; // eax
  SIZE_T v123; // r12
  CmsDurableLog *v124; // r12
  __int64 v125; // r14
  __int64 v126; // rsi
  __int64 v127; // rdi
  char LogFullPercentage; // bl
  int ActivityIdThread; // eax
  char v130; // [rsp+40h] [rbp-C0h]
  char v131; // [rsp+41h] [rbp-BFh]
  int v133; // [rsp+44h] [rbp-BCh]
  struct _SmsRedoBlock *v134; // [rsp+48h] [rbp-B8h]
  unsigned __int32 v135; // [rsp+48h] [rbp-B8h]
  unsigned __int8 *v136; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v137; // [rsp+58h] [rbp-A8h]
  struct CmsBPlusTable *v138; // [rsp+60h] [rbp-A0h]
  unsigned int *v139; // [rsp+68h] [rbp-98h]
  CmsDurableLog *v140; // [rsp+70h] [rbp-90h]
  _DWORD *v141; // [rsp+78h] [rbp-88h]
  __int64 v142; // [rsp+80h] [rbp-80h]
  int v143; // [rsp+88h] [rbp-78h] BYREF
  __int64 v144; // [rsp+90h] [rbp-70h]
  __int64 v145; // [rsp+98h] [rbp-68h]
  struct _SmsRedoBlock **v146; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int *v147; // [rsp+A8h] [rbp-58h]
  volatile signed __int32 *v148; // [rsp+B0h] [rbp-50h]
  __int64 v149; // [rsp+B8h] [rbp-48h]
  __int64 v150; // [rsp+C0h] [rbp-40h]
  size_t Size[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v152; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v153; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v154; // [rsp+F0h] [rbp-10h]
  char v155[8]; // [rsp+F8h] [rbp-8h] BYREF
  char v156[8]; // [rsp+100h] [rbp+0h] BYREF
  char v157[8]; // [rsp+108h] [rbp+8h] BYREF
  __int128 v158; // [rsp+110h] [rbp+10h] BYREF
  __int64 v159; // [rsp+120h] [rbp+20h] BYREF
  __int64 v160; // [rsp+128h] [rbp+28h]

  ++DbgRedoCreatedCount;
  v12 = 0;
  v13 = a5;
  v147 = (unsigned int *)a6;
  v14 = *(__int64 **)(a2 + 96);
  v15 = 56;
  v148 = a11;
  v142 = a2;
  v16 = a8;
  v150 = v14[3];
  v144 = a1;
  v141 = a4;
  v17 = *(_QWORD *)(a1 + 48);
  v139 = a5;
  v138 = a8;
  v140 = (CmsDurableLog *)(v150 + 2608);
  v131 = 0;
  v130 = 0;
  v145 = v17;
  if ( a2 != v17 )
  {
    v12 = 40;
    v18 = 1;
    if ( *((_WORD *)v14 + 6) )
    {
      do
      {
        v19 = *v14;
        v143 = 0;
        v20 = *(void (__fastcall **)(__int64 *, _QWORD, __int128 *, int *))(v19 + 104);
        v152 = 0;
        v20(v14, v18++, &v152, &v143);
        v12 += ((v152 + 23) & 0xFFFFFFF8) + 8;
      }
      while ( v18 <= *((unsigned __int16 *)v14 + 6) );
      v13 = v139;
      a4 = v141;
      v16 = v138;
    }
  }
  if ( a4 )
    v15 = ((*a4 + 7) & 0xFFFFFFF8) + 64;
  if ( v13 )
    v15 += ((*v13 + 7) & 0xFFFFFFF8) + 8;
  v21 = 0;
  if ( v147 )
    v21 = a7;
  v22 = 0;
  if ( v21 )
  {
    if ( v21 >= 8 )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v106 = 0;
      v107 = _mm_load_si128((const __m128i *)&_xmm_fffffff8fffffff8fffffff8fffffff8);
      v108 = 0;
      v109 = 2;
      do
      {
        v110 = 2LL * v22;
        v22 += 8;
        v111 = _mm_unpacklo_epi32(_mm_cvtsi32_si128(v147[2 * v110]), _mm_cvtsi32_si128(v147[4 * v109]));
        v112 = _mm_cvtsi32_si128(v147[4 * v109 + 16]);
        v113 = 2LL * (v109 + 5);
        v114 = 2LL * (v109 + 3);
        v115 = 2LL * (v109 + 2);
        v116 = _mm_add_epi32(
                 _mm_unpacklo_epi32(
                   v111,
                   _mm_unpacklo_epi32(_mm_cvtsi32_si128(v147[4 * v109 - 4]), _mm_cvtsi32_si128(v147[4 * v109 + 4]))),
                 si128);
        v109 += 8;
        v106 = _mm_add_epi32(_mm_add_epi32(_mm_and_si128(v116, v107), v106), (__m128i)_xmm);
        v108 = _mm_add_epi32(
                 _mm_add_epi32(
                   _mm_and_si128(
                     _mm_add_epi32(
                       _mm_unpacklo_epi32(
                         _mm_unpacklo_epi32(_mm_cvtsi32_si128(v147[2 * v115]), v112),
                         _mm_unpacklo_epi32(_mm_cvtsi32_si128(v147[2 * v114]), _mm_cvtsi32_si128(v147[2 * v113]))),
                       si128),
                     v107),
                   v108),
                 (__m128i)_xmm);
      }
      while ( v22 < (v21 & 0xFFFFFFF8) );
      v117 = _mm_add_epi32(v108, v106);
      v118 = _mm_add_epi32(v117, _mm_srli_si128(v117, 8));
      v15 += _mm_cvtsi128_si32(_mm_add_epi32(v118, _mm_srli_si128(v118, 4)));
    }
    if ( v22 < v21 )
    {
      v97 = (int *)&v147[4 * v22];
      v98 = v21 - v22;
      do
      {
        v99 = *v97;
        v97 += 4;
        v15 += ((v99 + 7) & 0xFFFFFFF8) + 8;
        --v98;
      }
      while ( v98 );
    }
    v16 = v138;
  }
  v23 = v144;
  v24 = v142;
  v25 = v140;
  if ( v16 )
  {
    v120 = CanonicalKeyLength(*((struct CmsCompositeBase **)v16 + 12), (unsigned int)v16);
    v13 = v139;
    v16 = v138;
    v15 += ((v120 + 15) & 0xFFFFFFF8) + 8;
  }
  v26 = v15 + 7;
  v27 = *(struct _SmsRedoBlock **)(v23 + 40);
  v134 = v27;
  v28 = (v12 + v26) & 0xFFFFFFF8;
  v137 = v28;
  if ( v27 && (v119 = *((unsigned int *)v27 + 7), *((_DWORD *)v27 + 6) - (int)v119 > v28) )
  {
    v38 = v119 + *((_QWORD *)v27 + 1);
    v130 = 1;
    *(_OWORD *)v38 = 0;
    *(_OWORD *)(v38 + 16) = 0;
    *(_OWORD *)(v38 + 32) = 0;
    *(_QWORD *)(v38 + 48) = 0;
  }
  else
  {
    if ( !a10
      || (v146 = 0,
          PreallocatedRedo = FindPreallocatedRedo((struct _SmsRedoBlock **)(v23 + 16), v28, &v146),
          v134 = PreallocatedRedo,
          (v27 = PreallocatedRedo) == 0) )
    {
LABEL_16:
      PoolWithTag = (struct _SmsRedoBlock *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x48u, 0x6950534Du);
      v134 = PoolWithTag;
      v27 = PoolWithTag;
      if ( !PoolWithTag )
        return 3221225626LL;
      memset(PoolWithTag, 0, 0x48u);
      v30 = -*(_DWORD *)(*((_QWORD *)v25 + 9) + 3664LL) & (v28 + *(_DWORD *)(*((_QWORD *)v25 + 9) + 3664LL) + 183);
      CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
      if ( NumProcessors == 56 )
        v32 = CurrentProcessorNumber % 0x38;
      else
        v32 = CurrentProcessorNumber % NumProcessors;
      v33 = (unsigned int *)(qword_1C0136F50 + 192LL * v32);
      if ( v30 > (unsigned __int64)*v33 )
      {
        v33 = 0;
        v123 = v30 + 8LL;
LABEL_124:
        v35 = ExAllocatePoolWithTag((POOL_TYPE)512, v123, 0x6950534Du);
        if ( !v35 )
          goto LABEL_125;
        goto LABEL_23;
      }
      if ( *((_BYTE *)v33 + 8) )
      {
        v34 = (struct _PAGED_LOOKASIDE_LIST *)(v33 + 16);
        if ( *((_BYTE *)v33 + 9) )
        {
          ++v33[21];
          v35 = ExpInterlockedPopEntrySList(&v34->L.ListHead);
          if ( v35 )
            goto LABEL_23;
          ++v33[22];
          v35 = (_QWORD *)(*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))v33 + 14))(v33[25], v33[27], v33[26]);
        }
        else
        {
          v35 = ExAllocateFromPagedLookasideList(v34);
        }
LABEL_110:
        if ( v35 )
        {
LABEL_23:
          *v35 = v33;
          v36 = v35 + 1;
          if ( v36 )
          {
            *(_QWORD *)v27 = v36;
            v37 = v36 + 22;
            *((_QWORD *)v27 + 1) = v37++;
            *((_QWORD *)v27 + 2) = v37;
            *(_OWORD *)v37 = 0;
            *((_OWORD *)v37 + 1) = 0;
            *((_OWORD *)v37 + 2) = 0;
            v37[6] = 0;
            *((_DWORD *)v27 + 6) = *(_DWORD *)v27 + v30 - *((_DWORD *)v27 + 2);
            *(_QWORD *)((char *)v27 + 28) = 8;
            *((_DWORD *)v27 + 9) = v30;
            v38 = *((_QWORD *)v27 + 2);
            if ( v38 )
            {
              v13 = v139;
              v16 = v138;
              goto LABEL_26;
            }
            return 3221225626LL;
          }
LABEL_125:
          ExFreePoolWithTag(v27, 0);
          return 3221225626LL;
        }
        goto LABEL_122;
      }
      if ( (int)v33[20] > (int)v33[22] )
      {
        v122 = _InterlockedDecrement((volatile signed __int32 *)v33 + 20);
        if ( v122 >= (int)v33[22] && v122 >= 0 )
        {
          v35 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v33 + 4);
          goto LABEL_110;
        }
        _InterlockedIncrement((volatile signed __int32 *)v33 + 20);
      }
LABEL_122:
      v123 = v33[1];
      goto LABEL_124;
    }
    v13 = v139;
    v131 = 1;
    *v146 = (struct _SmsRedoBlock *)*((_QWORD *)PreallocatedRedo + 6);
    v38 = *((_QWORD *)PreallocatedRedo + 2);
    v16 = v138;
    *((_QWORD *)PreallocatedRedo + 6) = 0;
  }
  if ( !v38 )
  {
    v28 = v137;
    goto LABEL_16;
  }
LABEL_26:
  v39 = *((unsigned __int16 *)v14 + 6) + 1;
  *(_DWORD *)v38 = v137;
  *(_DWORD *)(v38 + 4) = a3;
  *(_DWORD *)(v38 + 8) = v39;
  *(_DWORD *)(v38 + 16) = 0;
  if ( v24 == v145 )
  {
    *(_DWORD *)(v38 + 8) = 0;
    v39 = 0;
  }
  v40 = 0;
  if ( v141 )
  {
    *(_DWORD *)(v38 + 16) = 1;
    v40 = 1;
  }
  if ( v13 )
    *(_DWORD *)(v38 + 16) = ++v40;
  v41 = v40 + a7;
  *(_DWORD *)(v38 + 16) = v40 + a7;
  if ( v16 )
    *(_DWORD *)(v38 + 16) = ++v41;
  v160 = 0;
  v42 = (unsigned int)(8 * v39);
  v43 = (unsigned int)(v42 + 56);
  v44 = (unsigned __int8 *)(v42 + v38 + 56 + 8 * v41);
  *(_DWORD *)(v38 + 20) = v43;
  v45 = v38 + v43;
  *(_DWORD *)(v38 + 12) = 56;
  v46 = *(_QWORD *)(v24 + 96);
  v47 = v44;
  v149 = v45;
  v136 = v44;
  v145 = v46;
  if ( v39 )
  {
    LODWORD(v159) = 57392;
    v48 = v24;
    v49 = *(_QWORD *)(v24 + 32);
    if ( v49 != v24 )
    {
      do
      {
        v48 = v49;
        v49 = *(_QWORD *)(v49 + 32);
      }
      while ( v49 != v48 );
    }
    for ( i = *(_QWORD *)(v48 + 72); i != v48; i = *(_QWORD *)(i + 72) )
      v48 = i;
    HIDWORD(v159) = *(_DWORD *)(*(_QWORD *)(**(_QWORD **)(v48 + 80) + 24LL) + 16LL);
    v51 = v159;
    *(_DWORD *)(v38 + 56) = (_DWORD)v44 - v38;
    *(_DWORD *)(v38 + 60) = 12;
    *(_QWORD *)v44 = v51;
    *((_DWORD *)v44 + 2) = v160;
    v52 = v24;
    v53 = *(_QWORD *)(v24 + 32);
    if ( v53 != v24 )
    {
      do
      {
        v52 = v53;
        v53 = *(_QWORD *)(v53 + 32);
      }
      while ( v53 != v52 );
    }
    for ( j = *(_QWORD *)(v52 + 72); j != v52; j = *(_QWORD *)(j + 72) )
      v52 = j;
    v55 = *(_QWORD *)(v52 + 80);
    v56 = *(_DWORD *)(v38 + 60);
    *(_DWORD *)(v38 + 60) = v56 + 16;
    v57 = (_OWORD *)(v55 + 376);
    if ( v57 )
      *(_OWORD *)(v44 + 12) = *v57;
    v58 = ((v56 + 23) & 0xFFFFFFF8) - v56;
    v59 = (_DWORD *)(v38 + 64);
    v60 = 1;
    v44 += v58 + 12;
    v136 = v44;
    if ( *(_DWORD *)(v38 + 8) > 1u )
    {
      v61 = v145;
      v62 = (int)v44;
      v63 = &v47[v58 + 12];
      do
      {
        v64 = *(void (__fastcall **)(__int64, _QWORD, size_t *, __int64 *))(*(_QWORD *)v61 + 104LL);
        *(_OWORD *)Size = 0;
        v158 = 0;
        v64(v61, v60++, Size, &v159);
        if ( v60 < *(_DWORD *)(v38 + 8) )
          (*(void (__fastcall **)(__int64, _QWORD, __int128 *, char *))(*(_QWORD *)v61 + 104LL))(
            v61,
            v60,
            &v158,
            (char *)&v159 + 4);
        else
          HIDWORD(v159) = *(_DWORD *)(*(_QWORD *)(v142 + 24) + 16LL);
        v65 = v159;
        v59[1] = 12;
        *v59 = v62 - v38;
        *(_QWORD *)v44 = v65;
        *((_DWORD *)v44 + 2) = v160;
        v66 = Size[0];
        v67 = (const void *)Size[1];
        v133 = v59[1];
        v68 = LODWORD(Size[0]) + v133;
        v59[1] = LODWORD(Size[0]) + v133;
        v69 = (v68 + 7) & 0xFFFFFFF8;
        if ( v67 )
          memmove(v63 + 12, v67, v66);
        v59 += 2;
        v44 = &v63[v69 - v133 + 12];
        v62 = (int)v44;
        v63 = v44;
      }
      while ( v60 < *(_DWORD *)(v38 + 8) );
      v27 = v134;
      v45 = v149;
      v13 = v139;
      v136 = v44;
    }
    v24 = v142;
  }
  if ( v138 )
  {
    FormatRedoRecordTableKeysAsValue((struct _SmsRedoRecord *)v38, v138, (struct _SmsValuePointer *)v45, &v136);
    v13 = v139;
    v45 += 8;
    v44 = v136;
  }
  if ( v141 )
  {
    FormatRedoRecordValue(
      (struct _SmsRedoRecord *)v38,
      *v141,
      *((void **)v141 + 1),
      1u,
      (struct _SmsValuePointer *)v45,
      &v136);
    v13 = v139;
    v45 += 8;
    v44 = v136;
  }
  if ( v13 )
  {
    v70 = *v13;
    v71 = (const void *)*((_QWORD *)v13 + 1);
    *(_DWORD *)v45 = (_DWORD)v44 - v38;
    *(_DWORD *)(v45 + 4) = v70;
    v72 = (v70 + 7) & 0xFFFFFFF8;
    if ( v70 )
      memmove(v44, v71, v70);
    v44 += v72;
    v136 = v44;
    v45 += 8;
  }
  if ( a7 )
  {
    v100 = v147;
    v101 = (_DWORD *)a7;
    v141 = (_DWORD *)a7;
    do
    {
      v102 = *v100;
      v103 = (const void *)*((_QWORD *)v100 + 1);
      *(_DWORD *)v45 = (_DWORD)v44 - v38;
      *(_DWORD *)(v45 + 4) = v102;
      v104 = (v102 + 7) & 0xFFFFFFF8;
      if ( v102 )
      {
        memmove(v44, v103, v102);
        v101 = v141;
      }
      v45 += 8;
      v44 += v104;
      v100 += 4;
      v101 = (_DWORD *)((char *)v101 - 1);
      v141 = v101;
    }
    while ( v101 );
    v136 = v44;
  }
  v73 = v150;
  v74 = v144;
  *(_DWORD *)(v38 + 44) = 0;
  *(_QWORD *)(v38 + 24) = *(_QWORD *)(v73 + 1840);
  v75 = *(_QWORD *)(v73 + 1848);
  v76 = v148;
  *(_QWORD *)(v38 + 32) = v75;
  if ( v131 )
  {
    if ( !v76 )
    {
LABEL_79:
      v77 = v130;
      goto LABEL_80;
    }
LABEL_135:
    _InterlockedExchangeAdd(v76, 0xFFFFF000);
    *(_DWORD *)(v74 + 24) += 4096;
    *((_DWORD *)v27 + 10) = 4096;
    goto LABEL_79;
  }
  if ( v76 )
    goto LABEL_135;
  v77 = v130;
  if ( v130 )
  {
LABEL_80:
    *((_DWORD *)v27 + 7) += v137;
    v93 = *(_QWORD *)v74 == 0;
    *(_QWORD *)(v74 + 48) = v24;
    if ( v93 )
      *(_QWORD *)v74 = v38;
    v94 = *(_QWORD *)(v74 + 8);
    if ( v94 )
      *(_QWORD *)(v94 + 48) = v38;
    *(_QWORD *)(v74 + 8) = v38;
    if ( !v77 )
    {
      if ( !*(_QWORD *)(v74 + 32) )
        *(_QWORD *)(v74 + 32) = v27;
      v95 = *(_QWORD *)(v74 + 40);
      if ( v95 )
      {
        **(_DWORD **)(v95 + 8) = *(_DWORD *)(v95 + 28) - 8;
        *(_DWORD *)(*(_QWORD *)(v95 + 8) + 4LL) = *(_DWORD *)(v95 + 16) - *(_DWORD *)(v95 + 8);
        *(_DWORD *)(v95 + 32) = *(_DWORD *)(v95 + 28);
        *(_QWORD *)(*(_QWORD *)(v74 + 40) + 48LL) = v27;
      }
      *(_QWORD *)(v74 + 40) = v27;
    }
    return 0;
  }
  v78 = v140;
  v79 = (*((_DWORD *)v27 + 6) + 4095) & 0xFFFFF000;
  while ( 1 )
  {
    v80 = *((_QWORD *)v78 + 9);
    v135 = *((_DWORD *)v78 + 72);
    v81 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v80 + 3776));
    v82 = *(_QWORD *)(v80 + 3704);
    v83 = v81;
    v84 = *(unsigned int *)(v80 + 24);
    v85 = *(unsigned int *)(v80 + 32);
    v86 = *(unsigned int *)(v80 + 3664);
    v87 = RefsLargeEof == v82 ? (unsigned int)v85 - v84 : v85 + (unsigned int)v82 - v84;
    v88 = v86 * v87;
    v153 = v88;
    v89 = RefsLargeEof == v82 ? v84 + *(unsigned int *)(v80 + 3696) - v85 : v84 - v85;
    v90 = v89 * v86;
    v154 = v90;
    KeReleaseSpinLock((PKSPIN_LOCK)(v80 + 3776), v83);
    if ( v135 + v79 > v90 && !DbgIgnoreLogFull )
      break;
    v78 = v140;
    if ( !*(_BYTE *)(*((_QWORD *)v140 + 10) + 2544LL) )
    {
      v91 = 100 * (v88 + v135);
      if ( v88 + v90 == 0x20000000 )
      {
        v92 = v91 >> 29;
      }
      else
      {
        v92 = v91 / (v88 + v90);
        v78 = v140;
      }
      if ( v92 >= (unsigned __int8)dword_1C0136C58 )
      {
        KeSetEvent(&LazyWriterScanEvent, 0, 0);
        v78 = v140;
      }
    }
    if ( v135 == _InterlockedCompareExchange((volatile signed __int32 *)v78 + 72, v135 + v79, v135) )
    {
      *(_DWORD *)(v74 + 24) += v79;
      v24 = v142;
      *((_DWORD *)v27 + 10) = v79;
      goto LABEL_79;
    }
  }
  if ( dword_1C012D0B4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
  {
    v124 = v140;
    v125 = *(_QWORD *)CmsDurableLog::LastWrittenLsn(v140, v155);
    v126 = *(_QWORD *)CmsDurableLog::GetOldestRecordReference(v124, v156, 0);
    v127 = *(_QWORD *)CmsDurableLog::BaseLsn(v124, v157);
    LogFullPercentage = CmsDurableLog::GetLogFullPercentage(v124);
    ActivityIdThread = IoGetActivityIdThread();
    McTemplateK0qqiii_EtwWriteTransfer(
      (unsigned int)MinstoreEventProvider_Context,
      (unsigned int)LogFullRedoLog,
      ActivityIdThread,
      v135,
      LogFullPercentage,
      v127,
      v126,
      v125);
  }
  CmsTxMemLog::FreeRedoBlock(v27);
  return 3221225864LL;
}

```

## disassembly

```asm
0x1c0006770  mov     [rsp-8+arg_10], rbx
0x1c0006775  push    rbp
0x1c0006776  push    rsi
0x1c0006777  push    rdi
0x1c0006778  push    r12
0x1c000677a  push    r13
0x1c000677c  push    r14
0x1c000677e  push    r15
0x1c0006780  lea     rbp, [rsp-60h]
0x1c0006785  sub     rsp, 160h
0x1c000678c  mov     rax, cs:__security_cookie
0x1c0006793  xor     rax, rsp
0x1c0006796  mov     [rbp+90h+var_60], rax
0x1c000679a  mov     rax, [rbp+90h+arg_28]
0x1c00067a1  mov     r14, rdx
0x1c00067a4  inc     cs:?DbgRedoCreatedCount@@3KA; ulong DbgRedoCreatedCount
0x1c00067aa  xor     esi, esi
0x1c00067ac  mov     r11, [rbp+90h+arg_20]
0x1c00067b3  mov     [rbp+90h+var_E8], rax
0x1c00067b7  mov     rax, [rbp+90h+arg_50]
0x1c00067be  mov     rdi, [r14+60h]
0x1c00067c2  lea     r15d, [rsi+38h]
0x1c00067c6  mov     [rbp+90h+var_E0], rax
0x1c00067ca  mov     [rbp+90h+var_110], rdx
0x1c00067ce  mov     rdx, [rbp+90h+arg_38]
0x1c00067d5  mov     rax, [rdi+18h]
0x1c00067d9  mov     [rbp+90h+var_D0], rax
0x1c00067dd  mov     [rbp+90h+var_100], rcx
0x1c00067e1  mov     [rsp+190h+var_118], r9
0x1c00067e6  lea     r12, [rax+0A30h]
0x1c00067ed  mov     [rsp+190h+var_14C], r8d
0x1c00067f2  mov     rax, [rcx+30h]
0x1c00067f6  lea     ecx, [rsi+1]
0x1c00067f9  mov     [rsp+190h+var_128], r11
0x1c00067fe  mov     [rsp+190h+var_130], rdx
0x1c0006803  mov     [rsp+190h+var_120], r12
0x1c0006808  mov     [rsp+190h+var_14F], 0
0x1c000680d  mov     [rsp+190h+var_150], 0
0x1c0006812  mov     [rbp+90h+var_F8], rax
0x1c0006816  cmp     r14, rax
0x1c0006819  jz      short loc_1C0006875
0x1c000681b  lea     esi, [rcx+27h]
0x1c000681e  mov     ebx, ecx
0x1c0006820  cmp     cx, [rdi+0Ch]
0x1c0006824  ja      short loc_1C0006875
0x1c0006826  mov     rax, [rdi]
0x1c0006829  lea     r9, [rbp+90h+var_108]
0x1c000682d  xorps   xmm0, xmm0
0x1c0006830  mov     [rbp+90h+var_108], 0
0x1c0006837  lea     r8, [rbp+90h+var_B8]
0x1c000683b  mov     edx, ebx
0x1c000683d  mov     rcx, rdi
0x1c0006840  mov     rax, [rax+68h]
0x1c0006844  movups  [rbp+90h+var_B8], xmm0
0x1c0006848  call    cs:__guard_dispatch_icall_fptr
0x1c000684e  mov     eax, dword ptr [rbp+90h+var_B8]
0x1c0006851  inc     ebx
0x1c0006853  add     eax, 17h
0x1c0006856  and     eax, 0FFFFFFF8h
0x1c0006859  add     eax, 8
0x1c000685c  add     esi, eax
0x1c000685e  movzx   eax, word ptr [rdi+0Ch]
0x1c0006862  cmp     ebx, eax
0x1c0006864  jbe     short loc_1C0006826
0x1c0006866  mov     r11, [rsp+190h+var_128]
0x1c000686b  mov     r9, [rsp+190h+var_118]
0x1c0006870  mov     rdx, [rsp+190h+var_130]; unsigned int
0x1c0006875  test    r9, r9
0x1c0006878  jnz     loc_1C000714C
0x1c000687e  test    r11, r11
0x1c0006881  jz      short loc_1C0006893
0x1c0006883  mov     eax, [r11]
0x1c0006886  add     r15d, 8
0x1c000688a  add     eax, 7
0x1c000688d  and     eax, 0FFFFFFF8h
0x1c0006890  add     r15d, eax
0x1c0006893  mov     r13, [rbp+90h+var_E8]
0x1c0006897  xor     r10d, r10d
0x1c000689a  test    r13, r13
0x1c000689d  cmovnz  r10d, [rbp+90h+arg_30]
0x1c00068a5  xor     ebx, ebx
0x1c00068a7  test    r10d, r10d
0x1c00068aa  jnz     loc_1C0006EFD
0x1c00068b0  mov     r13, [rbp+90h+var_100]
0x1c00068b4  mov     r14, [rbp+90h+var_110]
0x1c00068b8  mov     r12, [rsp+190h+var_120]
0x1c00068bd  test    rdx, rdx
0x1c00068c0  jnz     loc_1C006EE84
0x1c00068c6  lea     ebx, [r15+7]
0x1c00068ca  mov     r15, [r13+28h]
0x1c00068ce  add     ebx, esi
0x1c00068d0  mov     [rsp+190h+var_148], r15
0x1c00068d5  and     ebx, 0FFFFFFF8h
0x1c00068d8  mov     [rsp+190h+var_138], ebx
0x1c00068dc  test    r15, r15
0x1c00068df  jnz     loc_1C00070CF
0x1c00068e5  cmp     [rbp+90h+arg_48], 0
0x1c00068ec  jnz     loc_1C006EEA9
0x1c00068f2  mov     edx, 48h ; 'H'; NumberOfBytes
0x1c00068f7  mov     ecx, 200h; PoolType
0x1c00068fc  mov     r8d, 6950534Dh; Tag
0x1c0006902  call    cs:__imp_ExAllocatePoolWithTag
0x1c0006909  nop     dword ptr [rax+rax+00h]
0x1c000690e  mov     [rsp+190h+var_148], rax
0x1c0006913  mov     r15, rax
0x1c0006916  test    rax, rax
0x1c0006919  jz      loc_1C006EF87
0x1c000691f  xor     edx, edx; Val
0x1c0006921  mov     rcx, rax; void *
0x1c0006924  lea     r8d, [rdx+48h]; Size
0x1c0006928  call    memset
0x1c000692d  mov     rax, [r12+48h]
0x1c0006932  mov     ecx, [rax+0E50h]
0x1c0006938  mov     eax, ecx
0x1c000693a  neg     eax
0x1c000693c  lea     esi, [rcx+0B7h]
0x1c0006942  xor     ecx, ecx; ProcNumber
0x1c0006944  add     esi, ebx
0x1c0006946  and     esi, eax
0x1c0006948  mov     r12d, esi
0x1c000694b  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1c0006952  nop     dword ptr [rax+rax+00h]
0x1c0006957  mov     r8d, cs:?NumProcessors@@3KA; ulong NumProcessors
0x1c000695e  mov     ecx, eax
0x1c0006960  cmp     r8d, 38h ; '8'
0x1c0006964  jnz     loc_1C00071A4
0x1c000696a  mov     eax, 24924925h
0x1c000696f  mul     ecx
0x1c0006971  mov     eax, ecx
0x1c0006973  sub     eax, edx
0x1c0006975  shr     eax, 1
0x1c0006977  add     eax, edx
0x1c0006979  shr     eax, 5
0x1c000697c  imul    eax, 38h ; '8'
0x1c000697f  sub     ecx, eax
0x1c0006981  mov     eax, ecx
0x1c0006983  lea     rbx, [rax+rax*2]
0x1c0006987  shl     rbx, 6
0x1c000698b  add     rbx, cs:qword_1C0136F50
0x1c0006992  mov     eax, [rbx]
0x1c0006994  cmp     r12, rax
0x1c0006997  ja      loc_1C006EF4D
0x1c000699d  cmp     byte ptr [rbx+8], 0
0x1c00069a1  jz      loc_1C006EF10
0x1c00069a7  cmp     byte ptr [rbx+9], 0
0x1c00069ab  lea     rcx, [rbx+40h]; Lookaside
0x1c00069af  jz      loc_1C006EF05
0x1c00069b5  inc     dword ptr [rbx+54h]
0x1c00069b8  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c00069bf  nop     dword ptr [rax+rax+00h]
0x1c00069c4  test    rax, rax
0x1c00069c7  jz      loc_1C0007118
0x1c00069cd  mov     [rax], rbx
0x1c00069d0  add     rax, 8
0x1c00069d4  jz      loc_1C006EF76
0x1c00069da  mov     [r15], rax
0x1c00069dd  xorps   xmm0, xmm0
0x1c00069e0  add     rax, 0B0h
0x1c00069e6  xor     ecx, ecx
0x1c00069e8  mov     [r15+8], rax
0x1c00069ec  add     rax, 8
0x1c00069f0  mov     [r15+10h], rax
0x1c00069f4  movups  xmmword ptr [rax], xmm0
0x1c00069f7  movups  xmmword ptr [rax+10h], xmm0
0x1c00069fb  movups  xmmword ptr [rax+20h], xmm0
0x1c00069ff  mov     [rax+30h], rcx
0x1c0006a03  mov     eax, esi
0x1c0006a05  sub     eax, [r15+8]
0x1c0006a09  add     eax, [r15]
0x1c0006a0c  mov     [r15+18h], eax
0x1c0006a10  mov     qword ptr [r15+1Ch], 8
0x1c0006a18  mov     [r15+24h], esi
0x1c0006a1c  mov     rbx, [r15+10h]
0x1c0006a20  test    rbx, rbx
0x1c0006a23  jz      loc_1C006EF87
0x1c0006a29  mov     r11, [rsp+190h+var_128]
0x1c0006a2e  mov     rdx, [rsp+190h+var_130]
0x1c0006a33  movzx   r9d, word ptr [rdi+0Ch]
0x1c0006a38  mov     ecx, [rsp+190h+var_138]
0x1c0006a3c  inc     r9d
0x1c0006a3f  mov     [rbx], ecx
0x1c0006a41  mov     ecx, [rsp+190h+var_14C]
0x1c0006a45  mov     [rbx+4], ecx
0x1c0006a48  mov     [rbx+8], r9d
0x1c0006a4c  mov     dword ptr [rbx+10h], 0
0x1c0006a53  cmp     r14, [rbp+90h+var_F8]
0x1c0006a57  jz      loc_1C000713D
0x1c0006a5d  xor     eax, eax
0x1c0006a5f  cmp     [rsp+190h+var_118], rax
0x1c0006a64  jnz     loc_1C0007160
0x1c0006a6a  test    r11, r11
0x1c0006a6d  jz      short loc_1C0006A74
0x1c0006a6f  inc     eax
0x1c0006a71  mov     [rbx+10h], eax
0x1c0006a74  mov     r10d, [rbp+90h+arg_30]
0x1c0006a7b  add     r10d, eax
0x1c0006a7e  mov     [rbx+10h], r10d
0x1c0006a82  test    rdx, rdx
0x1c0006a85  jnz     loc_1C006EF91
0x1c0006a8b  lea     r8, [rbx+38h]
0x1c0006a8f  mov     [rbp+90h+var_68], 0
0x1c0006a97  mov     eax, r8d
0x1c0006a9a  lea     ecx, ds:0[r9*8]
0x1c0006aa2  add     r8, rcx
0x1c0006aa5  lea     edi, ds:0[r10*8]
0x1c0006aad  sub     eax, ebx
0x1c0006aaf  mov     r12d, r8d
0x1c0006ab2  sub     r12d, ebx
0x1c0006ab5  mov     edx, eax
0x1c0006ab7  add     rdi, r8
0x1c0006aba  mov     esi, eax
0x1c0006abc  mov     [rbx+14h], r12d
0x1c0006ac0  add     rsi, rbx
0x1c0006ac3  add     r12, rbx
0x1c0006ac6  mov     [rbx+0Ch], edx
0x1c0006ac9  mov     rax, [r14+60h]
0x1c0006acd  mov     r8, rdi
0x1c0006ad0  mov     [rbp+90h+var_D8], r12
0x1c0006ad4  mov     [rsp+190h+var_140], rdi
0x1c0006ad9  mov     [rbp+90h+var_F8], rax
0x1c0006add  test    r9d, r9d
0x1c0006ae0  jz      loc_1C0006C84
0x1c0006ae6  mov     dword ptr [rbp+90h+var_70], 0E030h
0x1c0006aed  mov     rax, r14
0x1c0006af0  mov     rcx, [r14+20h]
0x1c0006af4  cmp     rcx, r14
0x1c0006af7  jz      short loc_1C0006B05
0x1c0006af9  mov     rax, rcx
0x1c0006afc  mov     rcx, [rcx+20h]
0x1c0006b00  cmp     rcx, rax
0x1c0006b03  jnz     short loc_1C0006AF9
0x1c0006b05  mov     rcx, [rax+48h]
0x1c0006b09  cmp     rcx, rax
0x1c0006b0c  jz      short loc_1C0006B1A
0x1c0006b0e  mov     rax, rcx
0x1c0006b11  mov     rcx, [rcx+48h]
0x1c0006b15  cmp     rcx, rax
0x1c0006b18  jnz     short loc_1C0006B0E
0x1c0006b1a  mov     rax, [rax+50h]
0x1c0006b1e  mov     rcx, [rax]
0x1c0006b21  mov     rax, [rcx+18h]
0x1c0006b25  mov     ecx, [rax+10h]
0x1c0006b28  mov     eax, edi
0x1c0006b2a  sub     eax, ebx
0x1c0006b2c  mov     dword ptr [rbp+90h+var_70+4], ecx
0x1c0006b2f  movsd   xmm0, [rbp+90h+var_70]
0x1c0006b34  mov     [rsi], eax
0x1c0006b36  mov     dword ptr [rsi+4], 0Ch
0x1c0006b3d  movsd   qword ptr [rdi], xmm0
0x1c0006b41  mov     eax, dword ptr [rbp+90h+var_68]
0x1c0006b44  mov     [rdi+8], eax
0x1c0006b47  mov     rax, r14
0x1c0006b4a  mov     rcx, [r14+20h]
0x1c0006b4e  cmp     rcx, r14
0x1c0006b51  jz      short loc_1C0006B5F
0x1c0006b53  mov     rax, rcx
0x1c0006b56  mov     rcx, [rcx+20h]
0x1c0006b5a  cmp     rcx, rax
0x1c0006b5d  jnz     short loc_1C0006B53
0x1c0006b5f  mov     rcx, [rax+48h]
0x1c0006b63  cmp     rcx, rax
0x1c0006b66  jz      short loc_1C0006B74
0x1c0006b68  mov     rax, rcx
0x1c0006b6b  mov     rcx, [rcx+48h]
0x1c0006b6f  cmp     rcx, rax
0x1c0006b72  jnz     short loc_1C0006B68
0x1c0006b74  mov     rcx, [rax+50h]
0x1c0006b78  mov     edx, [rsi+4]
0x1c0006b7b  lea     eax, [rdx+10h]
0x1c0006b7e  mov     [rsi+4], eax
0x1c0006b81  add     eax, 7
0x1c0006b84  and     eax, 0FFFFFFF8h
0x1c0006b87  add     rcx, 178h
0x1c0006b8e  jz      short loc_1C0006B97
0x1c0006b90  movups  xmm0, xmmword ptr [rcx]
0x1c0006b93  movups  xmmword ptr [rdi+0Ch], xmm0
0x1c0006b97  sub     eax, edx
0x1c0006b99  add     rsi, 8
0x1c0006b9d  mov     edi, eax
0x1c0006b9f  mov     r14d, 1
0x1c0006ba5  add     rdi, 0Ch
0x1c0006ba9  add     rdi, r8
0x1c0006bac  mov     [rsp+190h+var_140], rdi
0x1c0006bb1  cmp     [rbx+8], r14d
0x1c0006bb5  jbe     loc_1C0006C80
0x1c0006bbb  mov     r15, [rbp+90h+var_F8]
0x1c0006bbf  mov     r12d, edi
0x1c0006bc2  mov     r13, rdi
0x1c0006bc5  mov     rax, [r15]
0x1c0006bc8  lea     r9, [rbp+90h+var_70]
0x1c0006bcc  xorps   xmm0, xmm0
0x1c0006bcf  lea     r8, [rbp+90h+Size]
0x1c0006bd3  xorps   xmm1, xmm1
0x1c0006bd6  mov     edx, r14d
0x1c0006bd9  mov     rcx, r15
0x1c0006bdc  mov     rax, [rax+68h]
0x1c0006be0  movups  xmmword ptr [rbp+90h+Size], xmm0
0x1c0006be4  movups  [rbp+90h+var_80], xmm1
0x1c0006be8  call    cs:__guard_dispatch_icall_fptr
0x1c0006bee  inc     r14d
  ... truncated ...
```
