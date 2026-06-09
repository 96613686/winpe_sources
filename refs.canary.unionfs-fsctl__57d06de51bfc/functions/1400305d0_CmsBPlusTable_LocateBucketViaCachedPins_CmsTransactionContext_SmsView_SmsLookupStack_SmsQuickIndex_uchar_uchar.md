# CmsBPlusTable::LocateBucketViaCachedPins(CmsTransactionContext *,SmsView *,SmsLookupStack *,_SmsQuickIndex *,uchar,uchar,long *,uchar *,CmsKeyRange *,SmsPage * *,_LCN_TUPLE *)

- ea: `0x1400305d0`
- end: `0x140031ad4`
- name: `?LocateBucketViaCachedPins@CmsBPlusTable@@AEAAJPEAVCmsTransactionContext@@PEAUSmsView@@PEAUSmsLookupStack@@PEAU_SmsQuickIndex@@EEPEAJPEAEPEAVCmsKeyRange@@PEAPEAUSmsPage@@PEAT_LCN_TUPLE@@@Z`
- size: `5380`
- prototype: `__int64 __fastcall(CmsBPlusTable *__hidden this, struct CmsTransactionContext *, struct SmsView *, struct SmsLookupStack *, struct _SmsQuickIndex *, char, char, int *, unsigned __int8 *, struct CmsKeyRange *, struct SmsPage **, union _LCN_TUPLE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x14002e400`

## callees

- `0x14002f3e0`
- `0x1400305d0`
- `0x140031ae0`
- `0x14008fa30`
- `0x1400c8574`
- `0x1400cc588`
- `0x1401e9dc0`
- `0x1401e9e40`
- `0x1401ea140`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400313ab`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140031526`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400317cd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400313ab`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140031526`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400317cd`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140031941`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140031990`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140031a4f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140031941`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140031990`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140031a4f`
- `ntoskrnl!ExAllocatePool2` at `0x140031094`
- `ntoskrnl!ExAllocatePool2` at `0x1400311b4`
- `ntoskrnl!ExAllocatePool2` at `0x14003121e`
- `ntoskrnl!ExAllocatePool2` at `0x140031094`
- `ntoskrnl!ExAllocatePool2` at `0x1400311b4`
- `ntoskrnl!ExAllocatePool2` at `0x14003121e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140031052`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140031171`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400311db`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140031052`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140031171`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400311db`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f1944`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f1956`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f19a8`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f1944`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f1956`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f19a8`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400314dc`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003162b`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003171a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400314dc`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003162b`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003171a`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x14003093a`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x14003093a`
- `ntoskrnl!ExTryAcquireAutoExpandPushLockShared` at `0x1400308ef`
- `ntoskrnl!ExTryAcquireAutoExpandPushLockShared` at `0x1400308ef`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f196f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f198d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f19ce`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f196f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f198d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f19ce`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14003195e`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400319ad`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140031a6c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14003195e`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400319ad`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140031a6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400319e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031a1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031aa7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400319e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031a1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031aa7`

## string_xrefs

- `0x1401f19ba`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsBPlusTable::LocateBucketViaCachedPins(
        CmsBPlusTable *this,
        struct CmsTransactionContext *a2,
        struct SmsView *a3,
        struct SmsLookupStack *a4,
        struct _SmsQuickIndex *a5,
        unsigned __int8 a6,
        char a7,
        int *a8,
        unsigned __int8 *a9,
        struct CmsKeyRange *a10,
        struct SmsPage **a11,
        union _LCN_TUPLE *a12)
{
  __int64 v12; // r14
  CmsBPlusTable *v15; // rbx
  __int64 v16; // rax
  unsigned __int64 v17; // r9
  _DWORD *v18; // rdx
  _DWORD *v19; // rcx
  __int64 v20; // r13
  char *v21; // r13
  __int64 v22; // rdx
  _QWORD *v23; // rax
  _QWORD *p_Flink; // rdi
  struct _LIST_ENTRY *v25; // rdx
  struct _LIST_ENTRY *v26; // rax
  unsigned int v27; // ecx
  unsigned int v28; // ebx
  __int64 v29; // rbx
  bool v30; // zf
  char *v31; // rsi
  unsigned int v32; // r8d
  __int64 v33; // r13
  __int64 v34; // rcx
  char *v35; // rcx
  __int64 v36; // rdx
  int v38; // esi
  _OWORD *v39; // rax
  int v40; // ecx
  __int64 v41; // rcx
  __int64 v42; // rax
  struct _LIST_ENTRY *Flink; // r10
  struct _LIST_ENTRY *v44; // r13
  int Blink; // r8d
  struct _LIST_ENTRY *v46; // r11
  struct _LIST_ENTRY *v47; // rcx
  __int64 v48; // rcx
  struct CmsTransactionContext *v49; // rdx
  char *v50; // rdx
  int v51; // eax
  struct _LIST_ENTRY *v52; // rdx
  struct _LIST_ENTRY *v53; // rax
  struct _LIST_ENTRY *v54; // rcx
  char *v55; // rax
  struct _LIST_ENTRY *v56; // rcx
  __int64 v57; // rdx
  __int64 v58; // r10
  unsigned __int8 v59; // r11
  char *v60; // rcx
  char *v61; // r13
  char *v62; // r8
  unsigned __int16 v63; // cx
  unsigned int v64; // eax
  int v65; // edx
  __int64 *v66; // r14
  __int64 v67; // rcx
  __int64 v68; // rcx
  char *v69; // r9
  int v70; // eax
  char *v71; // rax
  struct _LIST_ENTRY *v72; // rcx
  struct _LIST_ENTRY *v73; // rdx
  struct _LIST_ENTRY *v74; // r8
  struct _LIST_ENTRY *v75; // rdx
  __int64 v76; // r14
  _QWORD *v77; // r13
  _DWORD *v78; // rax
  const void *v79; // rcx
  _QWORD *v80; // r14
  __int64 v81; // rsi
  __int64 v82; // rdx
  __int64 Pool2; // rax
  _QWORD *v84; // rdi
  __int64 v85; // rcx
  char *v86; // rax
  char *v87; // rax
  __int64 v88; // rax
  unsigned __int64 v89; // r8
  __int64 v90; // rdx
  unsigned __int64 *v91; // rax
  __int64 v92; // rdx
  __int64 v93; // rdx
  __int64 v94; // rax
  __int64 v95; // rdx
  __int64 v96; // rdx
  __int64 v97; // rax
  __int64 v98; // rcx
  char *v99; // rax
  char *v100; // rax
  __int64 v101; // rax
  unsigned __int64 v102; // r8
  __int64 v103; // rdx
  unsigned __int64 *v104; // rax
  const void *v105; // rdx
  __int64 v106; // rcx
  unsigned int v107; // eax
  struct _SLIST_ENTRY *v108; // r8
  __int64 v109; // rcx
  __int64 v110; // rcx
  unsigned int v111; // eax
  int v112; // r13d
  __int64 v113; // rax
  __int64 v114; // rsi
  struct _SLIST_ENTRY *v115; // r8
  struct _NPAGED_LOOKASIDE_LIST *v116; // rcx
  void *v117; // rdx
  struct _SLIST_ENTRY *v118; // r8
  __int64 v119; // rcx
  __int64 v120; // rcx
  int v121; // ecx
  int v122; // ecx
  int v123; // ecx
  struct _LIST_ENTRY *v124; // rax
  struct _LIST_ENTRY *v125; // rax
  _DWORD *v126; // rax
  struct _LIST_ENTRY *v127; // rax
  int v128; // eax
  __int64 v129; // rbx
  __int64 v130; // r14
  __int64 v131; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v132; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v133; // rcx
  _QWORD *v134; // rax
  __int64 v135; // rcx
  __int64 v136; // rdx
  struct _NPAGED_LOOKASIDE_LIST *v137; // rcx
  _QWORD *v138; // rax
  __int64 v139; // rdx
  struct _LIST_ENTRY *v140; // [rsp+20h] [rbp-89h]
  int v141; // [rsp+20h] [rbp-89h]
  _QWORD *v142; // [rsp+20h] [rbp-89h]
  unsigned int v143; // [rsp+28h] [rbp-81h]
  struct _LIST_ENTRY *v144; // [rsp+28h] [rbp-81h]
  __int64 v145; // [rsp+28h] [rbp-81h]
  char *v146; // [rsp+30h] [rbp-79h]
  int v147; // [rsp+30h] [rbp-79h]
  struct _LIST_ENTRY v148; // [rsp+38h] [rbp-71h] BYREF
  struct _LIST_ENTRY *v149; // [rsp+48h] [rbp-61h]
  void *Src; // [rsp+50h] [rbp-59h] BYREF
  struct _LIST_ENTRY *v151; // [rsp+58h] [rbp-51h]
  _DWORD *v152; // [rsp+60h] [rbp-49h]
  _DWORD *v153; // [rsp+68h] [rbp-41h]
  int v154; // [rsp+70h] [rbp-39h] BYREF
  __int16 Flink_high; // [rsp+74h] [rbp-35h]
  __int64 v156; // [rsp+78h] [rbp-31h]
  __int128 v157; // [rsp+80h] [rbp-29h]
  __int128 v158; // [rsp+90h] [rbp-19h]
  unsigned int v160; // [rsp+F0h] [rbp+47h]
  unsigned int v161; // [rsp+F0h] [rbp+47h]
  int v162; // [rsp+F0h] [rbp+47h]
  size_t v163; // [rsp+F0h] [rbp+47h]
  unsigned int i; // [rsp+F8h] [rbp+4Fh]
  unsigned int v165; // [rsp+F8h] [rbp+4Fh]
  int v166; // [rsp+F8h] [rbp+4Fh]
  _QWORD *v167; // [rsp+F8h] [rbp+4Fh]
  __int64 v168; // [rsp+F8h] [rbp+4Fh]
  __int64 v169; // [rsp+F8h] [rbp+4Fh]
  unsigned int Size; // [rsp+100h] [rbp+57h]
  unsigned int Sizea; // [rsp+100h] [rbp+57h]
  size_t Sizeb; // [rsp+100h] [rbp+57h]
  size_t Sizec; // [rsp+100h] [rbp+57h]
  size_t Sized; // [rsp+100h] [rbp+57h]

  v12 = *(_QWORD *)a3;
  v148 = 0;
  v15 = this;
  if ( *(_BYTE *)(v12 + 212) || *(_BYTE *)(*(_QWORD *)(v12 + 112) + 11LL) == 1 )
  {
    v16 = *((_QWORD *)this + 4);
    v17 = (unsigned __int64)a2 + 824;
    v18 = (_DWORD *)((char *)a2 + 860);
    v19 = (_DWORD *)(v17 + 32);
    v153 = v18;
    v152 = (_DWORD *)(v17 + 32);
    v20 = *(_QWORD *)(v16 + 40);
    LODWORD(v16) = *(_DWORD *)(v20 + 120);
    v21 = (char *)(v20 + 88);
    v146 = v21;
    if ( *((_DWORD *)v21 + 9) + (_DWORD)v16 || *v18 + *v19 )
    {
      v148.Blink = &v148;
      v148.Flink = &v148;
      if ( !(*v19 + *v18) )
        goto LABEL_41;
      v22 = *(_QWORD *)(v17 + 40);
      if ( !v22 )
        goto LABEL_5;
      v84 = (_QWORD *)(v17 + 48);
      v167 = (_QWORD *)(v17 + 48);
      if ( v12 != *(_QWORD *)(v17 + 48) || a6 )
        goto LABEL_5;
      v85 = *((unsigned __int8 *)a2 + 96);
      *(_QWORD *)&v157 = 0;
      v86 = (char *)a2 + 40 * v85;
      if ( (unsigned __int8)v85 <= 2u )
        v87 = v86 - 24;
      else
        v87 = v86 + 784;
      v88 = *(_QWORD *)v87;
      if ( *(_DWORD *)v88 == 16 )
      {
        v157 = *(_OWORD *)*(_QWORD *)(v88 + 8);
        v89 = v157;
      }
      else
      {
        if ( *(_DWORD *)v88 != 12 )
          goto LABEL_164;
        v89 = **(_QWORD **)(v88 + 8);
        *(_QWORD *)&v157 = v89;
      }
      v90 = *(_QWORD *)(v22 + 16);
      if ( v90 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            v91 = (unsigned __int64 *)(v90 + *(unsigned __int8 *)(v90 + 26));
            if ( v89 >= *v91 )
              break;
            v90 = *(_QWORD *)(v90 + 8);
            if ( !v90 )
            {
              v23 = (_QWORD *)(v17 + 48);
              goto LABEL_6;
            }
          }
          if ( v89 < v91[1] + *v91 )
            break;
          v90 = *(_QWORD *)(v90 + 16);
          if ( !v90 )
          {
            v23 = (_QWORD *)(v17 + 48);
            goto LABEL_6;
          }
        }
        p_Flink = (_QWORD *)(v90 + *(unsigned __int8 *)(v90 + 26));
        if ( p_Flink )
        {
          if ( (p_Flink[9] & 4) == 0 && *((_DWORD *)p_Flink + 22) == *(_DWORD *)(p_Flink[4] + 368LL) )
          {
            v120 = p_Flink[5];
            if ( *((_DWORD *)p_Flink + 23) == *(_DWORD *)(v120 + 184) )
            {
              if ( v120 == v12 && !*((_BYTE *)p_Flink + 144) )
                goto LABEL_15;
LABEL_5:
              v23 = (_QWORD *)(v17 + 48);
              goto LABEL_6;
            }
          }
          CmsPinCache::DoomCachedPin(
            (CmsPinCache *)v17,
            (struct CmsCachedPin *)p_Flink,
            &v148,
            (struct _LIST_ENTRY **)v17);
          v23 = v167;
          v17 = (unsigned __int64)a2 + 824;
          goto LABEL_6;
        }
        v84 = (_QWORD *)(v17 + 48);
      }
LABEL_164:
      v23 = v84;
LABEL_6:
      p_Flink = 0;
      if ( *v23 == v12 )
      {
        if ( *(_BYTE *)(v12 + 212) < 2u )
          goto LABEL_41;
        v25 = *(struct _LIST_ENTRY **)(v17 + 16);
        v26 = (struct _LIST_ENTRY *)(v17 + 16);
        v27 = (unsigned __int16)dword_140262170;
      }
      else if ( a6 )
      {
        v25 = *(struct _LIST_ENTRY **)(v17 + 16);
        v26 = (struct _LIST_ENTRY *)(v17 + 16);
        v27 = (unsigned __int8)byte_140262179;
      }
      else
      {
        v25 = *(struct _LIST_ENTRY **)v17;
        v26 = (struct _LIST_ENTRY *)v17;
        v27 = HIBYTE(word_140262177);
      }
      for ( i = v27; ; v27 = i )
      {
        v140 = v26;
        v28 = 0;
        while ( 1 )
        {
          while ( 1 )
          {
            while ( 1 )
            {
              while ( 1 )
              {
                if ( v25 == v26 || v28 >= v27 )
                  goto LABEL_12;
                Flink = v25->Flink;
                v44 = v25 - 1;
                Blink = (int)v25[3].Blink;
                ++v28;
                v149 = v25;
                v46 = v25;
                Sizea = v28;
                v25 = Flink;
                v144 = Flink;
                if ( (Blink & 4) == 0 && LODWORD(v44[5].Blink) == LODWORD(v44[2].Flink[23].Flink) )
                {
                  v47 = v44[2].Blink;
                  if ( HIDWORD(v44[5].Blink) == LODWORD(v47[11].Blink) )
                    break;
                }
                if ( Flink->Blink != v46 )
                  goto LABEL_35;
                v124 = v46->Blink;
                if ( v124->Flink != v46 )
                  goto LABEL_35;
                v124->Flink = Flink;
                Flink->Blink = v124;
                v125 = v148.Flink;
                if ( v148.Flink->Blink != &v148 )
                  goto LABEL_35;
                v46->Flink = v148.Flink;
                v46->Blink = &v148;
                v125->Blink = v46;
                v148.Flink = v46;
                if ( LOBYTE(v44[9].Flink) )
                  v126 = v153;
                else
                  v126 = v152;
                --*v126;
                v127 = v44[2].Flink;
                if ( v127[41].Blink == v44 )
                  v127[41].Blink = 0;
                v128 = (int)v44[6].Blink;
                if ( (v128 & 4) != 0 )
                {
                  v129 = *(_QWORD *)(v17 + 40);
                  LOBYTE(v17) = 1;
                  MsDeleteElementGenericTableAvlEx<MST_AVL_DO_NOT_FREE_PROTOTYPE>(v129, Flink, v44[8].Flink, v17);
                  ++*(_DWORD *)(v129 + 40);
                  v17 = (unsigned __int64)a2 + 824;
                  LODWORD(v44[6].Blink) &= ~4u;
                  v128 = (int)v44[6].Blink;
                  v25 = v144;
                  v28 = Sizea;
                }
                if ( (v128 & 0x10) != 0 )
                  _InterlockedDecrement((volatile signed __int32 *)&v44[2].Flink[6].Flink[6].Blink + 1);
                LODWORD(v44[6].Blink) |= 0x20u;
                v26 = v140;
                v27 = i;
              }
              v26 = v140;
              v30 = v47 == (struct _LIST_ENTRY *)v12;
              v27 = i;
              if ( v30 )
              {
                v26 = v140;
                if ( a6 <= LOBYTE(v44[9].Flink) )
                  break;
              }
            }
            v48 = *((unsigned __int8 *)a2 + 96);
            v49 = (unsigned __int8)v48 <= 2u
                ? (struct CmsTransactionContext *)((char *)a2 - 24)
                : (struct CmsTransactionContext *)((char *)a2 + 784);
            v50 = (char *)v49 + 40 * v48;
            Sizeb = (size_t)v50;
            if ( (Blink & 2) != 0 )
              break;
            v151 = v44[3].Flink;
            LODWORD(Src) = HIDWORD(v44[3].Blink);
            WORD2(Src) = WORD2(v44[4].Flink);
            v51 = (*(__int64 (__fastcall **)(_QWORD, char *, void **))(**((_QWORD **)v50 + 2) + 8LL))(
                    *((_QWORD *)v50 + 2),
                    v50,
                    &Src);
            v25 = v144;
            v17 = (unsigned __int64)a2 + 824;
            v27 = i;
            v30 = v51 == 1;
            v26 = v140;
            if ( v30 )
            {
              v50 = (char *)Sizeb;
              break;
            }
          }
          if ( ((__int64)v44[4].Blink & 1) != 0 )
            break;
          v156 = (__int64)v44[3].Flink + ((HIDWORD(v44[3].Blink) + 7) & 0xFFFFFFF8);
          v154 = (int)v44[4].Flink;
          Flink_high = HIWORD(v44[4].Flink);
          if ( (*(unsigned int (__fastcall **)(_QWORD, char *, int *, unsigned __int64))(**((_QWORD **)v50 + 2) + 8LL))(
                 *((_QWORD *)v50 + 2),
                 v50,
                 &v154,
                 v17) != 1 )
            break;
          v25 = v144;
          v17 = (unsigned __int64)a2 + 824;
          v26 = v140;
          v27 = i;
        }
        p_Flink = &v44->Flink;
        if ( v44 )
        {
          if ( v28 > 3 )
          {
            v52 = v149;
            v53 = v149->Flink;
            if ( v149->Flink->Blink != v149 )
              goto LABEL_35;
            v54 = v149->Blink;
            if ( v54->Flink != v149 )
              goto LABEL_35;
            v54->Flink = v53;
            v53->Blink = v54;
            v55 = (char *)a2 + 824;
            if ( LOBYTE(v44[9].Flink) )
              v55 = (char *)a2 + 840;
            v56 = *(struct _LIST_ENTRY **)v55;
            if ( *(char **)(*(_QWORD *)v55 + 8LL) != v55 )
              goto LABEL_35;
            v52->Flink = v56;
            v52->Blink = (struct _LIST_ENTRY *)v55;
            v56->Blink = v52;
            *(_QWORD *)v55 = v52;
          }
          goto LABEL_14;
        }
        v26 = v140;
        v17 = (unsigned __int64)a2 + 824;
LABEL_12:
        if ( v26 != (struct _LIST_ENTRY *)v17 || *(_BYTE *)(v12 + 212) < 2u )
        {
LABEL_14:
          if ( p_Flink )
          {
LABEL_15:
            v29 = 0;
            goto LABEL_16;
          }
          v15 = this;
          v21 = v146;
LABEL_41:
          v29 = ExTryAcquireAutoExpandPushLockShared(*(_QWORD *)(*((_QWORD *)v15 + 4) + 40LL), 2);
          if ( !v29 )
          {
            _InterlockedIncrement(&dword_140261EF8);
            v38 = -1073741823;
            CmsPinCache::DeleteDoomedCachedPins(a2, &v148);
            goto LABEL_62;
          }
          _InterlockedIncrement(&dword_140261EF4);
          if ( !(*((_DWORD *)v21 + 8) + *((_DWORD *)v21 + 9)) )
            goto LABEL_43;
          v57 = *((_QWORD *)v21 + 5);
          v58 = *(_QWORD *)a3;
          v59 = a6;
          v145 = *(_QWORD *)a3;
          if ( !v57 || (v17 = (unsigned __int64)(v21 + 48), v58 != *((_QWORD *)v21 + 6)) || a6 )
          {
            v17 = (unsigned __int64)(v21 + 48);
            goto LABEL_86;
          }
          v98 = *((unsigned __int8 *)a2 + 96);
          *(_QWORD *)&v158 = 0;
          v99 = (char *)a2 + 40 * v98;
          if ( (unsigned __int8)v98 <= 2u )
            v100 = v99 - 24;
          else
            v100 = v99 + 784;
          v101 = *(_QWORD *)v100;
          if ( *(_DWORD *)v101 == 16 )
          {
            v158 = *(_OWORD *)*(_QWORD *)(v101 + 8);
            v102 = v158;
          }
          else
          {
            if ( *(_DWORD *)v101 != 12 )
              goto LABEL_86;
            v102 = **(_QWORD **)(v101 + 8);
            *(_QWORD *)&v158 = v102;
          }
          v103 = *(_QWORD *)(v57 + 16);
          if ( !v103 )
            goto LABEL_86;
          while ( 1 )
          {
            v104 = (unsigned __int64 *)(v103 + *(unsigned __int8 *)(v103 + 26));
            if ( v102 < *v104 )
            {
              v103 = *(_QWORD *)(v103 + 8);
            }
            else
            {
              if ( v102 < v104[1] + *v104 )
              {
                p_Flink = (_QWORD *)(v103 + *(unsigned __int8 *)(v103 + 26));
                if ( p_Flink )
                {
                  if ( (p_Flink[9] & 4) == 0 && *((_DWORD *)p_Flink + 22) == *(_DWORD *)(p_Flink[4] + 368LL) )
                  {
                    v131 = p_Flink[5];
                    if ( *((_DWORD *)p_Flink + 23) == *(_DWORD *)(v131 + 184)
                      && v131 == v58
                      && !*((_BYTE *)p_Flink + 144) )
                    {
                      goto LABEL_44;
                    }
                  }
                }
LABEL_86:
                p_Flink = 0;
                if ( *(_QWORD *)v17 != v58 )
                {
                  v60 = (char *)a2 + 824;
                  if ( a6 )
                  {
                    v62 = v21 + 16;
                    v61 = (char *)*((_QWORD *)v21 + 2);
                    Sizec = (size_t)v62;
                    if ( v146 == v60 )
                      v17 = (unsigned __int8)byte_140262179;
                    else
LABEL_98:
                      v17 = (unsigned __int16)dword_140262170;
                  }
                  else
                  {
                    v61 = *(char **)v21;
                    v62 = v146;
                    Sizec = (size_t)v146;
                    if ( v146 == v60 )
                    {
                      v17 = HIBYTE(word_140262177);
                    }
                    else
                    {
                      v63 = dword_14026216C;
                      if ( *(_BYTE *)(v58 + 212) > 2u )
                        v63 = HIWORD(dword_14026216C);
                      v17 = v63;
                    }
                  }
LABEL_92:
                  v160 = v17;
LABEL_93:
                  v64 = 0;
                  while ( 1 )
                  {
                    while ( 1 )
                    {
LABEL_94:
                      if ( v61 == v62 || v64 >= (unsigned int)v17 )
                      {
                        if ( v62 != v146 || *(_BYTE *)(v58 + 212) < 2u )
                          goto LABEL_44;
                        v61 = (char *)*((_QWORD *)v146 + 2);
                        v62 = v146 + 16;
                        Sizec = (size_t)(v146 + 16);
                        if ( v146 == (char *)a2 + 824 )
                          goto LABEL_93;
                        goto LABEL_98;
                      }
                      v65 = *((_DWORD *)v61 + 14);
                      v66 = (__int64 *)(v61 - 16);
                      ++v64;
                      v149 = (struct _LIST_ENTRY *)v61;
                      v61 = *(char **)v61;
                      v165 = v64;
                      if ( (v65 & 4) == 0 && *((_DWORD *)v66 + 22) == *(_DWORD *)(v66[4] + 368) )
                      {
                        v67 = v66[5];
                        if ( *((_DWORD *)v66 + 23) == *(_DWORD *)(v67 + 184)
                          && v67 == v58
                          && v59 <= *((_BYTE *)v66 + 144) )
                        {
                          break;
                        }
                      }
                    }
                    v68 = *((unsigned __int8 *)a2 + 96);
                    if ( (unsigned __int8)v68 <= 2u )
                      v69 = (char *)a2 - 24;
                    else
                      v69 = (char *)a2 + 784;
                    v17 = (unsigned __int64)&v69[40 * v68];
                    v142 = (_QWORD *)v17;
                    if ( (v65 & 2) == 0 )
                    {
                      v156 = v66[6];
                      v154 = *((_DWORD *)v66 + 15);
                      Flink_high = *((_WORD *)v66 + 34);
                      v70 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64, int *))(**(_QWORD **)(v17 + 16) + 8LL))(
                              *(_QWORD *)(v17 + 16),
                              v17,
                              &v154);
                      v62 = (char *)Sizec;
                      v30 = v70 == 1;
                      v64 = v165;
                      v17 = v160;
                      v58 = v145;
                      v59 = a6;
                      if ( !v30 )
                        goto LABEL_94;
                      v17 = (unsigned __int64)v142;
                    }
                    if ( (v66[9] & 1) != 0
                      || (v151 = (struct _LIST_ENTRY *)(v66[6] + ((*((_DWORD *)v66 + 15) + 7) & 0xFFFFFFF8)),
                          LODWORD(Src) = *((_DWORD *)v66 + 16),
                          WORD2(Src) = *((_WORD *)v66 + 35),
                          (*(unsigned int (__fastcall **)(_QWORD, unsigned __int64, void **))(**(_QWORD **)(v17 + 16)
                                                                                            + 8LL))(
                            *(_QWORD *)(v17 + 16),
                            v17,
                            &Src) != 1) )
                    {
                      v71 = v146;
                      p_Flink = v66;
                      if ( v146 == (char *)a2 + 824 && v165 > 3 )
                      {
                        v72 = v149;
                        v73 = v149->Flink;
                        if ( v149->Flink->Blink == v149 )
                        {
                          v74 = v149->Blink;
                          if ( v74->Flink == v149 )
                          {
                            v74->Flink = v73;
                            v73->Blink = v74;
                            if ( *((_BYTE *)v66 + 144) )
                              v71 = v146 + 16;
                            v75 = *(struct _LIST_ENTRY **)v71;
                            if ( *(char **)(*(_QWORD *)v71 + 8LL) == v71 )
                            {
                              v72->Flink = v75;
                              v72->Blink = (struct _LIST_ENTRY *)v71;
                              v75->Blink = v72;
                              *(_QWORD *)v71 = v72;
                              goto LABEL_44;
                            }
                          }
                        }
LABEL_35:
                        __fastfail(3u);
                      }
LABEL_44:
                      if ( !p_Flink )
                      {
LABEL_45:
                        v38 = -1073741823;
                        goto LABEL_46;
                      }
LABEL_16:
                      if ( a7 && *(_QWORD *)(p_Flink[4] + 336LL) != *((_QWORD *)a3 + 2) )
                      {
                        if ( !v29 )
                          CmsPinCache::DoomCachedPin(
                            (struct CmsTransactionContext *)((char *)a2 + 824),
                            (struct CmsCachedPin *)p_Flink,
                            &v148,
                            (struct _LIST_ENTRY **)v17);
                        goto LABEL_45;
                      }
                      if ( *((_QWORD *)a3 + 2) == *(_QWORD *)(*(_QWORD *)a3 + 168LL)
                        && *(_QWORD *)(*(_QWORD *)a3 + 160LL) != *(_QWORD *)(*(_QWORD *)a3 + 168LL)
                        && p_Flink[12] > *((_QWORD *)a3 + 2)
                        || *((_DWORD *)p_Flink + 23) != *(_DWORD *)(*(_QWORD *)a3 + 184LL) )
                      {
                        goto LABEL_45;
                      }
                      v141 = 96;
                      v147 = 8;
                      if ( !v29 )
                      {
                        _InterlockedIncrement(&dword_140261F08);
                        goto LABEL_51;
                      }
                      _InterlockedIncrement(&dword_140261F04);
                      if ( (*(_QWORD *)a2 & 0x1000000000000LL) != 0 || (*(_QWORD *)a2 & 2) != 0 )
                        goto LABEL_51;
                      v30 = *((_BYTE *)p_Flink + 144) == 0;
                      if ( !*((_BYTE *)p_Flink + 144) )
                      {
                        if ( !*((_BYTE *)a2 + 135) )
                        {
                          v31 = (char *)a2 + 2656;
                          if ( a2 == (struct CmsTransactionContext *)-2656LL )
                          {
                            v31 = 0;
                          }
                          else
                          {
                            *(_QWORD *)v31 = 0;
                            *((_QWORD *)a2 + 333) = 0;
                            *((_DWORD *)a2 + 682) |= 3u;
                            *((_QWORD *)a2 + 338) = 0;
                            *((_QWORD *)a2 + 339) = 0;
                            *((_QWORD *)a2 + 340) = 0;
                            *((_DWORD *)a2 + 690) = 0;
                            *((_QWORD *)a2 + 349) = 0;
                            *((_QWORD *)a2 + 335) = (char *)a2 + 2672;
                            *((_QWORD *)a2 + 334) = (char *)a2 + 2672;
                            *((_QWORD *)a2 + 333) = 0;
                            *(_QWORD *)v31 = 0;
                            *(_QWORD *)((char *)a2 + 2804) = 0;
                          }
                          *((_DWORD *)v31 + 26) |= 8u;
                          *((_BYTE *)a2 + 135) = 1;
                          *((_QWORD *)v31 + 17) = a2;
                          goto LABEL_28;
                        }
                        v81 = qword_140262438 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
                        if ( *(_DWORD *)v81 < 0xC0u )
                        {
                          v81 = 0;
                          v82 = 208;
                          goto LABEL_147;
                        }
                        if ( !*(_BYTE *)(v81 + 8) )
                        {
                          if ( (int)*(_QWORD *)(v81 + 88) > (int)HIDWORD(*(_QWORD *)(v81 + 88)) )
                          {
                            v122 = _InterlockedDecrement((volatile signed __int32 *)(v81 + 88));
                            if ( v122 >= *(_DWORD *)(v81 + 92) && v122 >= 0 )
                            {
                              Pool2 = (__int64)ExpInterlockedPopEntrySList((PSLIST_HEADER)(v81 + 64));
                              goto LABEL_283;
                            }
                            _InterlockedIncrement((volatile signed __int32 *)(v81 + 88));
                          }
LABEL_249:
                          v82 = *(unsigned int *)(v81 + 4);
LABEL_147:
                          Pool2 = ExAllocatePool2(66, v82, 1766871885);
                          if ( (Pool2 & 0xF) == 0 )
                          {
                            if ( Pool2 )
                              goto LABEL_284;
                            goto LABEL_51;
                          }
LABEL_332:
                          MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
                        }
                        v132 = (struct _NPAGED_LOOKASIDE_LIST *)(v81 + 64);
                        if ( *(_BYTE *)(v81 + 9) )
                          Pool2 = (__int64)ExAllocateFromNPagedLookasideList(v132);
                        else
                          Pool2 = (__int64)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v132);
LABEL_283:
                        if ( !Pool2 )
                          goto LABEL_249;
LABEL_284:
                        v130 = Pool2 + 16;
                        *(_QWORD *)Pool2 = v81;
                        if ( Pool2 != -16 )
                        {
                          memset((void *)(Pool2 + 16), 0, 0xC0u);
                          v31 = (char *)(v130 + 32);
                          *(_BYTE *)(v130 + 26) = 32;
                          if ( v130 == -32 )
                          {
                            v31 = 0;
                          }
                          else
                          {
                            *(_DWORD *)(v130 + 104) |= 3u;
                            *(_QWORD *)(v130 + 56) = v130 + 48;
                            *(_QWORD *)(v130 + 48) = v130 + 48;
                            *(_QWORD *)(v130 + 180) = 0;
                          }
                          *((_QWORD *)v31 + 16) = v130;
LABEL_28:
                          if ( v31 )
                          {
                            v32 = *((_DWORD *)v31 + 26);
                            v143 = v32;
                            if ( *((_QWORD *)v31 + 6) )
                            {
                              CmsKeyRange::FreeKeysBuffer((CmsKeyRange *)(v31 + 48));
                              v32 = v143;
                            }
                            *((_OWORD *)v31 + 3) = 0;
                            *((_OWORD *)v31 + 4) = 0;
                            *((_DWORD *)v31 + 18) |= 3u;
                            v33 = *((unsigned int *)p_Flink + 14);
                            Size = v33;
                            if ( !(_DWORD)v33 )
                              goto LABEL_32;
                            Src = (void *)p_Flink[6];
                            if ( !*((_BYTE *)a2 + 129) && (unsigned int)v33 <= 0x60 )
                            {
                              *((_BYTE *)a2 + 129) = 1;
                              v77 = (_QWORD *)((char *)a2 + 2560);
                              v166 = 96;
                              v162 = 8;
                              goto LABEL_193;
                            }
                            v92 = qword_140262420 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
                            v163 = v92;
                            if ( (unsigned int)v33 > *(_DWORD *)v92 )
                            {
                              v163 = 0;
                              v93 = v33 + 16;
                              goto LABEL_167;
                            }
                            if ( *(_BYTE *)(v92 + 8) )
                            {
                              v133 = (struct _NPAGED_LOOKASIDE_LIST *)(v92 + 64);
                              if ( *(_BYTE *)(v92 + 9) )
                                v134 = ExAllocateFromNPagedLookasideList(v133);
                              else
                                v134 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v133);
LABEL_190:
                              v77 = v134;
                              if ( !v134 )
                              {
                                v92 = v163;
                                goto LABEL_244;
                              }
LABEL_191:
                              *v77 = v163;
                              v77 += 2;
                            }
                            else
                            {
                              if ( (int)*(_QWORD *)(v92 + 88) > (int)HIDWORD(*(_QWORD *)(v92 + 88)) )
                              {
                                v121 = _InterlockedDecrement((volatile signed __int32 *)(v92 + 88));
                                if ( v121 >= *(_DWORD *)(v92 + 92) && v121 >= 0 )
                                {
                                  v134 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v92 + 64));
                                  goto LABEL_190;
                                }
                                _InterlockedIncrement((volatile signed __int32 *)(v92 + 88));
                              }
LABEL_244:
                              v93 = *(unsigned int *)(v92 + 4);
LABEL_167:
                              v94 = ExAllocatePool2(66, v93, 1766871885);
                              v77 = (_QWORD *)v94;
                              if ( (v94 & 0xF) != 0 )
                                goto LABEL_332;
                              if ( v94 )
                                goto LABEL_191;
                            }
                            v166 = Size;
                            v162 = 0;
LABEL_193:
                            if ( v77 )
                            {
                              v105 = (const void *)*((_QWORD *)v31 + 6);
                              if ( v105 )
                              {
                                memmove(v77, v105, *((unsigned int *)v31 + 14));
                                v106 = *((_QWORD *)v31 + 6);
                                if ( (*((_DWORD *)v31 + 18) & 8) != 0 )
                                {
                                  *(_BYTE *)(v106 - 2431) = 0;
                                  *((_DWORD *)v31 + 18) &= ~8u;
                                }
                                else if ( v106 )
                                {
                                  v108 = (struct _SLIST_ENTRY *)(v106 - 16);
                                  v109 = *(_QWORD *)(v106 - 16);
                                  v149 = (struct _LIST_ENTRY *)v109;
                                  if ( !v109 )
                                    goto LABEL_317;
                                  if ( *(_BYTE *)(v109 + 8) )
                                  {
                                    if ( *(_BYTE *)(v109 + 9) )
                                      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v109 + 64), v108);
                                    else
                                      ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)(v109 + 64), v108);
                                    goto LABEL_197;
                                  }
                                  v136 = *(_QWORD *)(v109 + 88);
                                  if ( (int)v136 < *(_DWORD *)(v109 + 80) || SHIDWORD(v136) >= (int)v136 )
                                  {
                                    ExpInterlockedPushEntrySList((PSLIST_HEADER)(v109 + 64), v108);
                                    _InterlockedIncrement((volatile signed __int32 *)&v149[5].Blink);
                                  }
                                  else
                                  {
LABEL_317:
                                    ExFreePoolWithTag(v108, 0);
                                  }
                                }
                              }
LABEL_197:
                              v107 = *((_DWORD *)v31 + 18) & 0xFFFFFFF7;
                              *((_QWORD *)v31 + 6) = v77;
                              *((_DWORD *)v31 + 18) = v162 | v107;
                              *((_DWORD *)v31 + 14) = v166;
                              if ( Src )
                                memmove(v77, Src, Size);
                              v32 = v143;
LABEL_32:
                              *((_DWORD *)v31 + 15) = *((_DWORD *)p_Flink + 15);
                              *((_DWORD *)v31 + 16) = *((_DWORD *)p_Flink + 16);
                              *((_WORD *)v31 + 34) = *((_WORD *)p_Flink + 34);
                              *((_WORD *)v31 + 35) = *((_WORD *)p_Flink + 35);
                              *((_DWORD *)v31 + 18) = *((_DWORD *)p_Flink + 18)
                                                    ^ (*((_DWORD *)v31 + 18)
                                                     ^ *((_DWORD *)p_Flink + 18))
                                                    & 8;
                              v34 = p_Flink[4];
                              *((_QWORD *)v31 + 4) = v34;
                              *((_QWORD *)v31 + 5) = p_Flink[5];
                              *((_QWORD *)v31 + 10) = p_Flink[10];
                              *((_DWORD *)v31 + 22) = *((_DWORD *)p_Flink + 22);
                              *((_DWORD *)v31 + 23) = *((_DWORD *)p_Flink + 23);
                              *((_QWORD *)v31 + 12) = p_Flink[12];
                              *((_QWORD *)v31 + 14) = p_Flink[14];
                              *((_QWORD *)v31 + 15) = p_Flink[15];
                              v31[144] = *((_BYTE *)p_Flink + 144);
                              _InterlockedIncrement((volatile signed __int32 *)(v34 + 380));
                              v35 = (char *)a2 + 824;
                              if ( *((_BYTE *)p_Flink + 144) )
                                v35 = (char *)a2 + 840;
                              v36 = *(_QWORD *)v35;
                              if ( *(char **)(*(_QWORD *)v35 + 8LL) != v35 )
                                goto LABEL_35;
                              *((_QWORD *)v31 + 2) = v36;
                              *((_QWORD *)v31 + 3) = v35;
                              *(_QWORD *)(v36 + 8) = v31 + 16;
                              *(_QWORD *)v35 = v31 + 16;
                              if ( *((_BYTE *)p_Flink + 144) )
                                v78 = v153;
                              else
                                v78 = v152;
                              ++*v78;
                              *((_DWORD *)v31 + 26) = (p_Flink[13] & 0xFFFFFFE9 | 2)
                                                    ^ ((p_Flink[13] & 0xE9 | 2)
                                                     ^ (unsigned __int8)(8 * (v32 >> 3)))
                                                    & 8;
                              goto LABEL_51;
                            }
                            if ( (*((_DWORD *)v31 + 26) & 8) != 0 )
                              *(_BYTE *)(*((_QWORD *)v31 + 17) + 135LL) = 0;
                            v112 = *((_DWORD *)v31 + 26) & 8;
                            if ( (*((_DWORD *)v31 + 26) & 0x10) != 0 )
                              _InterlockedAdd64(&CmsCachedPin::GlobalCachedPinPageCount, -*((_DWORD *)v31 + 38));
                            if ( *((_QWORD *)v31 + 6) )
                              CmsKeyRange::FreeKeysBuffer((CmsKeyRange *)(v31 + 48));
                            if ( !v112 )
                            {
                              v113 = *((_QWORD *)v31 + 16);
                              if ( v113 )
                              {
                                v114 = *(_QWORD *)(v113 - 16);
                                v115 = (struct _SLIST_ENTRY *)(v113 - 16);
                                if ( v114 )
                                {
                                  if ( *(_BYTE *)(v114 + 8) )
                                  {
                                    v116 = (struct _NPAGED_LOOKASIDE_LIST *)(v114 + 64);
                                    v117 = (void *)(v113 - 16);
                                    if ( *(_BYTE *)(v114 + 9) )
                                      ExFreeToNPagedLookasideList(v116, v117);
                                    else
                                      ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v116, v117);
                                    goto LABEL_51;
                                  }
                                  v135 = *(_QWORD *)(v114 + 88);
                                  if ( (int)v135 < *(_DWORD *)(v114 + 80) || SHIDWORD(v135) >= (int)v135 )
                                  {
                                    ExpInterlockedPushEntrySList((PSLIST_HEADER)(v114 + 64), v115);
                                    _InterlockedIncrement((volatile signed __int32 *)(v114 + 88));
                                    goto LABEL_51;
                                  }
                                }
                                ExFreePoolWithTag(v115, 0);
                              }
                            }
                          }
                        }
LABEL_51:
                        v30 = *((_BYTE *)p_Flink + 144) == 0;
                      }
                      if ( v30 )
                      {
                        _InterlockedIncrement(&dword_140261EFC);
                        *((_DWORD *)a10 + 6) |= 4u;
LABEL_54:
                        v39 = (_OWORD *)p_Flink[4];
                        *(_OWORD *)a12 = *v39;
                        *((_OWORD *)a12 + 1) = v39[1];
                        *((_QWORD *)a4 + 4) = p_Flink[14];
                        v40 = *((_DWORD *)p_Flink + 22);
                        *a9 = *((_BYTE *)p_Flink + 144);
                        *a8 = v40;
                        if ( (*(_DWORD *)a2 & 0x800LL) == 0 )
                        {
                          v41 = *(_QWORD *)(p_Flink[5] + 160LL);
                          if ( p_Flink[12] != v41 )
                            p_Flink[12] = v41;
                        }
                        _InterlockedIncrement((volatile signed __int32 *)(p_Flink[4] + 380LL));
                        v38 = 0;
                        *a11 = (struct SmsPage *)p_Flink[4];
                        if ( a5 )
                        {
                          if ( *a9 )
                            v42 = 0;
                          else
                            v42 = p_Flink[10];
                          *((_QWORD *)a5 + 2) = v42;
                          *((_BYTE *)a5 + 8) = (p_Flink[13] & 0x10) != 0;
                        }
LABEL_46:
                        if ( v29 )
                          ExReleaseAutoExpandPushLockShared(v29, 2);
                        CmsPinCache::DeleteDoomedCachedPins(a2, &v148);
                        if ( v38 >= 0 )
                          return (unsigned int)v38;
LABEL_62:
                        if ( a5 )
                          *(_QWORD *)a5 = 0;
                        return (unsigned int)v38;
                      }
                      _InterlockedIncrement(&dword_140261F00);
                      if ( *(_QWORD *)a10 )
                        CmsKeyRange::FreeKeysBuffer(a10);
                      *(_OWORD *)a10 = 0;
                      *((_OWORD *)a10 + 1) = 0;
                      *((_DWORD *)a10 + 6) = 3;
                      v76 = *((unsigned int *)p_Flink + 14);
                      v161 = v76;
                      if ( !(_DWORD)v76 )
                      {
LABEL_122:
                        *((_DWORD *)a10 + 3) = *((_DWORD *)p_Flink + 15);
                        *((_DWORD *)a10 + 4) = *((_DWORD *)p_Flink + 16);
                        *((_WORD *)a10 + 10) = *((_WORD *)p_Flink + 34);
                        *((_WORD *)a10 + 11) = *((_WORD *)p_Flink + 35);
                        *((_DWORD *)a10 + 6) = *((_DWORD *)p_Flink + 18)
                                             ^ (*((_DWORD *)a10 + 6)
                                              ^ *((_DWORD *)p_Flink + 18))
                                             & 8;
                        goto LABEL_54;
                      }
                      v79 = (const void *)p_Flink[6];
                      Sized = (size_t)v79;
                      if ( a2 && !*((_BYTE *)a2 + 129) && (unsigned int)v76 <= 0x60 )
                      {
                        *((_BYTE *)a2 + 129) = 1;
                        v80 = (_QWORD *)((char *)a2 + 2560);
                        goto LABEL_208;
                      }
                      v95 = qword_140262420 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
                      v168 = v95;
                      if ( (unsigned int)v76 > *(_DWORD *)v95 )
                      {
                        v168 = 0;
                        v96 = v76 + 16;
                        goto LABEL_172;
                      }
                      if ( *(_BYTE *)(v95 + 8) )
                      {
                        v137 = (struct _NPAGED_LOOKASIDE_LIST *)(v95 + 64);
                        if ( *(_BYTE *)(v95 + 9) )
                          v138 = ExAllocateFromNPagedLookasideList(v137);
                        else
                          v138 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v137);
LABEL_205:
                        v80 = v138;
                        if ( !v138 )
                        {
                          v95 = v168;
                          goto LABEL_256;
                        }
LABEL_206:
                        *v80 = v168;
                        v80 += 2;
                      }
                      else
                      {
                        if ( (int)*(_QWORD *)(v95 + 88) > (int)HIDWORD(*(_QWORD *)(v95 + 88)) )
                        {
                          v123 = _InterlockedDecrement((volatile signed __int32 *)(v95 + 88));
                          if ( v123 >= *(_DWORD *)(v95 + 92) && v123 >= 0 )
                          {
                            v138 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v95 + 64));
                            goto LABEL_205;
                          }
                          _InterlockedIncrement((volatile signed __int32 *)(v95 + 88));
                        }
LABEL_256:
                        v96 = *(unsigned int *)(v95 + 4);
LABEL_172:
                        v97 = ExAllocatePool2(66, v96, 1766871885);
                        v80 = (_QWORD *)v97;
                        if ( (v97 & 0xF) != 0 )
                          goto LABEL_332;
                        if ( v97 )
                          goto LABEL_206;
                      }
                      v79 = (const void *)Sized;
                      v141 = v161;
                      v147 = 0;
LABEL_208:
                      if ( !v80 )
                      {
                        v38 = -1073741670;
                        goto LABEL_46;
                      }
                      if ( *(_QWORD *)a10 )
                      {
                        memmove(v80, *(const void **)a10, *((unsigned int *)a10 + 2));
                        v110 = *(_QWORD *)a10;
                        if ( (*((_DWORD *)a10 + 6) & 8) != 0 )
                        {
                          *(_BYTE *)(v110 - 2431) = 0;
                          *((_DWORD *)a10 + 6) &= ~8u;
                          goto LABEL_212;
                        }
                        if ( v110 )
                        {
                          v118 = (struct _SLIST_ENTRY *)(v110 - 16);
                          v119 = *(_QWORD *)(v110 - 16);
                          v169 = v119;
                          if ( v119 )
                          {
                            if ( *(_BYTE *)(v119 + 8) )
                            {
                              if ( *(_BYTE *)(v119 + 9) )
                                ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v119 + 64), v118);
                              else
                                ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)(v119 + 64), v118);
                              goto LABEL_212;
                            }
                            v139 = *(_QWORD *)(v119 + 88);
                            if ( (int)v139 < *(_DWORD *)(v119 + 80) || SHIDWORD(v139) >= (int)v139 )
                            {
                              ExpInterlockedPushEntrySList((PSLIST_HEADER)(v119 + 64), v118);
                              _InterlockedIncrement((volatile signed __int32 *)(v169 + 88));
                              goto LABEL_212;
                            }
                          }
                          ExFreePoolWithTag(v118, 0);
                        }
LABEL_212:
                        v79 = (const void *)Sized;
                        *((_DWORD *)a10 + 2) = 0;
                      }
                      v111 = *((_DWORD *)a10 + 6) & 0xFFFFFFF7;
                      *(_QWORD *)a10 = v80;
                      *((_DWORD *)a10 + 6) = v147 | v111;
                      *((_DWORD *)a10 + 2) = v141;
                      if ( v79 )
                        memmove(v80, v79, v161);
                      goto LABEL_122;
                    }
                    v64 = v165;
                    v62 = (char *)Sizec;
                    v17 = v160;
                    v58 = v145;
                    v59 = a6;
                  }
                }
                if ( *(_BYTE *)(v58 + 212) >= 2u )
                {
                  v17 = (unsigned __int16)dword_140262170;
                  v62 = v21 + 16;
                  v61 = (char *)*((_QWORD *)v21 + 2);
                  Sizec = (size_t)v62;
                  goto LABEL_92;
                }
LABEL_43:
                p_Flink = 0;
                goto LABEL_44;
              }
              v103 = *(_QWORD *)(v103 + 16);
            }
            if ( !v103 )
              goto LABEL_86;
          }
        }
        v25 = *(struct _LIST_ENTRY **)(v17 + 16);
        v26 = (struct _LIST_ENTRY *)(v17 + 16);
      }
    }
  }
  if ( a5 )
    *(_QWORD *)a5 = 0;
  return 3221225473LL;
}

```

## disassembly

```asm
0x1400305d0  mov     [rsp-8+arg_18], r9
0x1400305d5  mov     [rsp-8+arg_0], rcx
0x1400305da  push    rbp
0x1400305db  push    rbx
0x1400305dc  push    rsi
0x1400305dd  push    r12
0x1400305df  push    r13
0x1400305e1  push    r14
0x1400305e3  push    r15
0x1400305e5  lea     rbp, [rsp-7]
0x1400305ea  sub     rsp, 0B0h
0x1400305f1  mov     r14, [r8]
0x1400305f4  xorps   xmm0, xmm0
0x1400305f7  movups  xmmword ptr [rbp+37h+var_A8.Flink], xmm0
0x1400305fb  mov     rsi, r8
0x1400305fe  mov     r15, rdx
0x140030601  mov     rbx, rcx
0x140030604  cmp     byte ptr [r14+0D4h], 0
0x14003060c  jz      loc_1400308B3
0x140030612  mov     rax, [rcx+20h]
0x140030616  lea     r9, [rdx+338h]; struct _LIST_ENTRY **
0x14003061d  lea     rdx, [r9+24h]
0x140030621  lea     rcx, [r9+20h]
0x140030625  mov     [rbp+37h+var_78], rdx
0x140030629  mov     [rbp+37h+var_80], rcx
0x14003062d  mov     r13, [rax+28h]
0x140030631  mov     eax, [r13+78h]
0x140030635  add     r13, 58h ; 'X'
0x140030639  mov     [rbp+37h+var_B0], r13
0x14003063d  add     eax, [r13+24h]
0x140030641  jz      loc_140031005
0x140030647  lea     rax, [rbp+37h+var_A8]
0x14003064b  mov     [rsp+0E0h+var_38], rdi
0x140030653  mov     [rbp+37h+var_A8.Blink], rax
0x140030657  xor     r12d, r12d
0x14003065a  lea     rax, [rbp+37h+var_A8]
0x14003065e  mov     [rbp+37h+var_A8.Flink], rax
0x140030662  mov     eax, [rdx]
0x140030664  add     eax, [rcx]
0x140030666  jz      loc_1400308E2
0x14003066c  mov     rdx, [r9+28h]
0x140030670  test    rdx, rdx
0x140030673  jnz     loc_1400310B6
0x140030679  lea     rax, [r9+30h]
0x14003067d  mov     rdi, r12
0x140030680  cmp     [rax], r14
0x140030683  jz      loc_140031784
0x140030689  cmp     [rbp+37h+arg_28], r12b
0x14003068d  jnz     loc_140030EAE
0x140030693  mov     rdx, [r9]
0x140030696  mov     rax, r9
0x140030699  movzx   ecx, byte ptr cs:word_140262177+1
0x1400306a0  mov     dword ptr [rbp+37h+arg_8], ecx
0x1400306a3  mov     [rsp+0E0h+var_C0], rax
0x1400306a8  nop     dword ptr [rax+rax+00000000h]
0x1400306b0  mov     ebx, r12d
0x1400306b3  cmp     rdx, rax
0x1400306b6  jnz     loc_140030A66
0x1400306bc  cmp     rax, r9
0x1400306bf  jnz     short loc_1400306CF
0x1400306c1  cmp     byte ptr [r14+0D4h], 2
0x1400306c9  jnb     loc_140031911
0x1400306cf  test    rdi, rdi
0x1400306d2  jz      loc_1400308DA
0x1400306d8  mov     rbx, r12
0x1400306db  cmp     [rbp+37h+arg_30], r12b
0x1400306df  jnz     loc_140030F46
0x1400306e5  mov     rax, [rsi]
0x1400306e8  mov     rcx, [rax+0A8h]
0x1400306ef  cmp     [rsi+10h], rcx
0x1400306f3  jnz     short loc_14003070F
0x1400306f5  mov     rax, [rsi]
0x1400306f8  mov     rcx, [rax+0A8h]
0x1400306ff  mov     rax, [rsi]
0x140030702  cmp     [rax+0A0h], rcx
0x140030709  jnz     loc_140031243
0x14003070f  mov     rax, [rsi]
0x140030712  mov     ecx, [rax+0B8h]
0x140030718  cmp     [rdi+5Ch], ecx
0x14003071b  jnz     loc_140030928
0x140030721  mov     dword ptr [rsp+0E0h+var_C0], 60h ; '`'
0x140030729  mov     dword ptr [rbp+37h+var_B0], 8
0x140030730  test    rbx, rbx
0x140030733  jz      loc_14003096A
0x140030739  lock inc cs:dword_140261F04
0x140030740  mov     rax, [r15]
0x140030743  bt      rax, 30h ; '0'
0x140030748  jb      loc_140030971
0x14003074e  test    al, 2
0x140030750  jnz     loc_140030971
0x140030756  cmp     [rdi+90h], r12b
0x14003075d  jnz     loc_140030978
0x140030763  cmp     [r15+87h], r12b
0x14003076a  jnz     loc_140031050
0x140030770  lea     rsi, [r15+0A60h]
0x140030777  test    rsi, rsi
0x14003077a  jz      loc_1400317DE
0x140030780  mov     [rsi], r12
0x140030783  lea     rax, [rsi+10h]
0x140030787  mov     [rsi+8], r12
0x14003078b  or      dword ptr [rsi+48h], 3
0x14003078f  mov     [rsi+30h], r12
0x140030793  mov     [rsi+38h], r12
0x140030797  mov     [rsi+40h], r12
0x14003079b  mov     [rsi+68h], r12d
0x14003079f  mov     [rsi+88h], r12
0x1400307a6  mov     [rax+8], rax
0x1400307aa  mov     [rax], rax
0x1400307ad  mov     [rsi+8], r12
0x1400307b1  mov     [rsi], r12
0x1400307b4  mov     [rsi+94h], r12
0x1400307bb  or      dword ptr [rsi+68h], 8
0x1400307bf  mov     byte ptr [r15+87h], 1
0x1400307c7  mov     [rsi+88h], r15
0x1400307ce  test    rsi, rsi
0x1400307d1  jz      loc_140030971
0x1400307d7  mov     r8d, [rsi+68h]
0x1400307db  mov     dword ptr [rsp+0E0h+var_B8], r8d
0x1400307e0  cmp     [rsi+30h], r12
0x1400307e4  jnz     loc_14003196F
0x1400307ea  xorps   xmm0, xmm0
0x1400307ed  movups  xmmword ptr [rsi+30h], xmm0
0x1400307f1  movups  xmmword ptr [rsi+40h], xmm0
0x1400307f5  or      dword ptr [rsi+48h], 3
0x1400307f9  mov     r13d, [rdi+38h]
0x1400307fd  mov     dword ptr [rbp+37h+Size], r13d
0x140030801  test    r13d, r13d
0x140030804  jnz     loc_140030F7C
0x14003080a  mov     eax, [rdi+3Ch]
0x14003080d  mov     [rsi+3Ch], eax
0x140030810  mov     eax, [rdi+40h]
0x140030813  mov     [rsi+40h], eax
0x140030816  movzx   eax, word ptr [rdi+44h]
0x14003081a  mov     [rsi+44h], ax
0x14003081e  movzx   eax, word ptr [rdi+46h]
0x140030822  mov     [rsi+46h], ax
0x140030826  mov     eax, [rdi+48h]
0x140030829  mov     ecx, eax
0x14003082b  xor     ecx, [rsi+48h]
0x14003082e  and     ecx, 8
0x140030831  xor     ecx, eax
0x140030833  mov     [rsi+48h], ecx
0x140030836  mov     rcx, [rdi+20h]
0x14003083a  mov     [rsi+20h], rcx
0x14003083e  mov     rax, [rdi+28h]
0x140030842  mov     [rsi+28h], rax
0x140030846  mov     rax, [rdi+50h]
0x14003084a  mov     [rsi+50h], rax
0x14003084e  mov     eax, [rdi+58h]
0x140030851  mov     [rsi+58h], eax
0x140030854  mov     eax, [rdi+5Ch]
0x140030857  mov     [rsi+5Ch], eax
0x14003085a  mov     rax, [rdi+60h]
0x14003085e  mov     [rsi+60h], rax
0x140030862  mov     rax, [rdi+70h]
0x140030866  mov     [rsi+70h], rax
0x14003086a  mov     rax, [rdi+78h]
0x14003086e  mov     [rsi+78h], rax
0x140030872  movzx   eax, byte ptr [rdi+90h]
0x140030879  mov     [rsi+90h], al
0x14003087f  nop
0x140030880  lock inc dword ptr [rcx+17Ch]
0x140030887  nop
0x140030888  lea     rcx, [r15+338h]
0x14003088f  cmp     [rdi+90h], r12b
0x140030896  jz      short loc_14003089F
0x140030898  lea     rcx, [r15+348h]
0x14003089f  mov     rdx, [rcx]
0x1400308a2  cmp     [rdx+8], rcx
0x1400308a6  jz      loc_140030FBD
0x1400308ac  mov     ecx, 3
0x1400308b1  int     29h; Win8: RtlFailFast(ecx)
0x1400308b3  mov     rax, [r14+70h]
0x1400308b7  cmp     byte ptr [rax+0Bh], 1
0x1400308bb  jz      loc_140030612
0x1400308c1  mov     rax, [rbp+37h+arg_20]
0x1400308c5  test    rax, rax
0x1400308c8  jz      short loc_1400308D0
0x1400308ca  xor     r12d, r12d
0x1400308cd  mov     [rax], r12
0x1400308d0  mov     eax, 0C0000001h
0x1400308d5  jmp     loc_140031AC1
0x1400308da  mov     rbx, [rbp+37h+arg_0]
0x1400308de  mov     r13, [rbp+37h+var_B0]
0x1400308e2  mov     rcx, [rbx+20h]
0x1400308e6  mov     edx, 2
0x1400308eb  mov     rcx, [rcx+28h]
0x1400308ef  call    cs:__imp_ExTryAcquireAutoExpandPushLockShared
0x1400308f6  nop     dword ptr [rax+rax+00h]
0x1400308fb  mov     rbx, rax
0x1400308fe  test    rax, rax
0x140030901  jz      loc_140030A39
0x140030907  lock inc cs:dword_140261EF4
0x14003090e  mov     eax, [r13+24h]
0x140030912  add     eax, [r13+20h]
0x140030916  jnz     loc_140030BD7
0x14003091c  mov     rdi, r12
0x14003091f  test    rdi, rdi
0x140030922  jnz     loc_1400306DB
0x140030928  mov     esi, 0C0000001h
0x14003092d  test    rbx, rbx
0x140030930  jz      short loc_140030946
0x140030932  mov     edx, 2
0x140030937  mov     rcx, rbx
0x14003093a  call    cs:__imp_ExReleaseAutoExpandPushLockShared
0x140030941  nop     dword ptr [rax+rax+00h]
0x140030946  lea     rdx, [rbp+37h+var_A8]; struct _LIST_ENTRY *
0x14003094a  mov     rcx, r15; struct CmsTransactionContext *
0x14003094d  call    ?DeleteDoomedCachedPins@CmsPinCache@@SAXPEAVCmsTransactionContext@@PEAU_LIST_ENTRY@@@Z; CmsPinCache::DeleteDoomedCachedPins(CmsTransactionContext *,_LIST_ENTRY *)
0x140030952  test    esi, esi
0x140030954  js      loc_140030A51
0x14003095a  mov     rdi, [rsp+0E0h+var_38]
0x140030962  mov     eax, esi
0x140030964  jmp     loc_140031AC1
0x14003096a  lock inc cs:dword_140261F08
0x140030971  cmp     [rdi+90h], r12b
0x140030978  ja      loc_140030DE4
0x14003097e  lock inc cs:dword_140261EFC
0x140030985  mov     rax, [rbp+37h+arg_48]
0x14003098c  or      dword ptr [rax+18h], 4
0x140030990  mov     rax, [rdi+20h]
0x140030994  mov     rcx, [rbp+37h+arg_58]
0x14003099b  mov     rdx, [rbp+37h+arg_40]
0x1400309a2  movups  xmm0, xmmword ptr [rax]
0x1400309a5  movups  xmmword ptr [rcx], xmm0
0x1400309a8  movups  xmm1, xmmword ptr [rax+10h]
0x1400309ac  movups  xmmword ptr [rcx+10h], xmm1
0x1400309b0  mov     rax, [rdi+70h]
0x1400309b4  mov     rcx, [rbp+37h+arg_18]
0x1400309b8  mov     [rcx+20h], rax
0x1400309bc  movzx   eax, byte ptr [rdi+90h]
0x1400309c3  mov     ecx, [rdi+58h]
0x1400309c6  mov     [rdx], al
0x1400309c8  mov     rax, [rbp+37h+arg_38]
0x1400309cc  mov     [rax], ecx
0x1400309ce  mov     eax, [r15]
0x1400309d1  bt      rax, 0Bh
0x1400309d6  jb      short loc_1400309ED
0x1400309d8  mov     rax, [rdi+28h]
0x1400309dc  mov     rcx, [rax+0A0h]
0x1400309e3  cmp     [rdi+60h], rcx
0x1400309e7  jnz     loc_140031AB8
0x1400309ed  mov     rax, [rdi+20h]
0x1400309f1  nop
0x1400309f2  lock inc dword ptr [rax+17Ch]
0x1400309f9  mov     rax, [rbp+37h+arg_50]
0x140030a00  nop
0x140030a01  mov     rcx, [rdi+20h]
0x140030a05  mov     esi, r12d
0x140030a08  mov     [rax], rcx
0x140030a0b  mov     rcx, [rbp+37h+arg_20]
0x140030a0f  test    rcx, rcx
0x140030a12  jz      loc_14003092D
0x140030a18  cmp     [rdx], sil
0x140030a1b  jnz     loc_14003177C
0x140030a21  mov     rax, [rdi+50h]
0x140030a25  mov     [rcx+10h], rax
0x140030a29  mov     eax, [rdi+68h]
0x140030a2c  shr     eax, 4
0x140030a2f  and     al, 1
0x140030a31  mov     [rcx+8], al
0x140030a34  jmp     loc_14003092D
0x140030a39  lock inc cs:dword_140261EF8
0x140030a40  lea     rdx, [rbp+37h+var_A8]; struct _LIST_ENTRY *
0x140030a44  mov     rcx, r15; struct CmsTransactionContext *
0x140030a47  mov     esi, 0C0000001h
0x140030a4c  call    ?DeleteDoomedCachedPins@CmsPinCache@@SAXPEAVCmsTransactionContext@@PEAU_LIST_ENTRY@@@Z; CmsPinCache::DeleteDoomedCachedPins(CmsTransactionContext *,_LIST_ENTRY *)
0x140030a51  mov     rax, [rbp+37h+arg_20]
0x140030a55  test    rax, rax
0x140030a58  jz      loc_14003095A
0x140030a5e  mov     [rax], r12
0x140030a61  jmp     loc_14003095A
0x140030a66  cmp     ebx, ecx
0x140030a68  jnb     loc_1400306BC
0x140030a6e  mov     r10, [rdx]
0x140030a71  lea     r13, [rdx-10h]
0x140030a75  mov     r8d, [r13+48h]
0x140030a79  inc     ebx
0x140030a7b  mov     [rbp+37h+var_98], rdx
0x140030a7f  mov     r11, rdx
0x140030a82  mov     dword ptr [rbp+37h+Size], ebx
0x140030a85  mov     rdx, r10
0x140030a88  mov     [rsp+0E0h+var_B8], rdx
0x140030a8d  test    r8b, 4
0x140030a91  jnz     loc_14003167C
0x140030a97  mov     rax, [r13+20h]
0x140030a9b  mov     ecx, [rax+170h]
0x140030aa1  cmp     [r13+58h], ecx
0x140030aa5  jnz     loc_14003167C
0x140030aab  mov     rcx, [r13+28h]
0x140030aaf  mov     eax, [rcx+0B8h]
0x140030ab5  cmp     [r13+5Ch], eax
0x140030ab9  jnz     loc_14003167C
0x140030abf  mov     rax, [rsp+0E0h+var_C0]
0x140030ac4  cmp     rcx, r14
0x140030ac7  mov     ecx, dword ptr [rbp+37h+arg_8]
0x140030aca  jnz     loc_1400306B3
0x140030ad0  movzx   eax, [rbp+37h+arg_28]
0x140030ad4  cmp     al, [r13+90h]
0x140030adb  mov     rax, [rsp+0E0h+var_C0]
  ... truncated ...
```
