# CmsBPlusTable::AddToIndex(CmsTransactionContext *,_CmsRow *,ulong,ulong,_SmsQuickIndex *,_SmsPreAllocatedRow *,unsigned __int64 *,ulong)

- ea: `0x1c001b000`
- end: `0x1c001bc77`
- name: `?AddToIndex@CmsBPlusTable@@MEAAJPEAVCmsTransactionContext@@PEAU_CmsRow@@KKPEAU_SmsQuickIndex@@PEAU_SmsPreAllocatedRow@@PEA_KK@Z`
- size: `3191`
- prototype: `__int64 __usercall@<rax>(CmsBPlusTable *__hidden this@<rcx>, struct CmsTransactionContext *@<rdx>, struct _CmsRow *@<r8>, unsigned int@<r9d>, unsigned int, struct _SmsQuickIndex *, struct _SmsPreAllocatedRow *, unsigned __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `29`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1c00ca930`

## callees

- `0x1c0002b40`
- `0x1c00059f4`
- `0x1c00151a0`
- `0x1c0019730`
- `0x1c0019d00`
- `0x1c001afd4`
- `0x1c001b000`
- `0x1c001bc80`
- `0x1c001bcb0`
- `0x1c001cb20`
- `0x1c001d280`
- `0x1c002313c`
- `0x1c00238ac`
- `0x1c0023b78`
- `0x1c0023e9c`
- `0x1c0023eb8`
- `0x1c0024e28`
- `0x1c0026c04`
- `0x1c002981c`
- `0x1c0029acc`
- `0x1c0031f20`
- `0x1c0047d84`
- `0x1c004987c`
- `0x1c0067b48`
- `0x1c0068960`
- `0x1c0069ae4`
- `0x1c006ac80`
- `0x1c006acc0`
- `0x1c006af80`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c001b8ca`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c001b8ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c001bc21`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c001bc44`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c001bc21`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c001bc44`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c001b9e0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c001b9e0`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c001b88b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c001b88b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c001b812`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c001b812`

## pseudocode

```c
__int64 __fastcall CmsBPlusTable::AddToIndex(
        CmsBPlusTable *this,
        struct CmsTransactionContext *a2,
        struct _CmsRow *a3,
        unsigned int a4,
        unsigned int a5,
        struct _SmsQuickIndex *a6,
        struct _SmsPreAllocatedRow *a7,
        unsigned __int64 *a8,
        char a9)
{
  unsigned __int64 *v10; // r12
  unsigned int v13; // r15d
  char v14; // r14
  int v15; // ebx
  __int64 v17; // rax
  void (__fastcall *v18)(CmsBPlusTable *, struct CmsTransactionContext *, _QWORD); // rax
  __int64 v19; // rax
  __int128 v20; // xmm0
  __int64 v21; // rdx
  int FirstIndexEntry; // r15d
  unsigned int v23; // eax
  struct _CmsData *v24; // rdx
  _DWORD *v25; // r10
  int v26; // r11d
  unsigned int v27; // eax
  int v28; // edx
  struct _SmsQuickIndex *v29; // rax
  unsigned __int8 v30; // r14
  __int64 v31; // r10
  unsigned __int128 *v32; // r8
  unsigned __int64 v33; // rcx
  __int64 v34; // rdx
  struct _CmsKey *v35; // rbx
  int v36; // r12d
  char v37; // al
  unsigned int v38; // r13d
  struct _CmsData *v39; // rdx
  _DWORD *v40; // r11
  unsigned int v41; // edx
  CmsVolume *v42; // rcx
  unsigned __int8 v43; // cl
  struct CmsChecksum *v44; // rbx
  unsigned int v45; // eax
  unsigned int LengthPhys; // eax
  __int64 v47; // r9
  unsigned int v48; // eax
  void *v49; // rcx
  struct SmsUndoRecord *v50; // r8
  __int64 v51; // rdx
  unsigned int v52; // eax
  __int64 v53; // r9
  CmsBPlusTable *v54; // rcx
  struct _SmsIndexEntry *v55; // rax
  struct _SmsIndexHeader *v56; // rdx
  CmsBPlusTable *v57; // rcx
  unsigned int v58; // r9d
  const void *v59; // r14
  char v60; // dl
  __int64 v61; // r9
  int v62; // r12d
  __int64 v63; // rbx
  _QWORD *PoolWithTag; // rbx
  ULONG CurrentProcessorNumber; // eax
  __int64 v66; // rcx
  unsigned int *v67; // r14
  struct _NPAGED_LOOKASIDE_LIST *v68; // rcx
  _QWORD *v69; // rax
  int v70; // eax
  SIZE_T v71; // rcx
  __int64 v72; // r13
  unsigned int v73; // eax
  void *v74; // rcx
  CmsBPlusTable *v75; // rcx
  struct _SmsIndexEntry *v76; // rax
  unsigned int v77; // r9d
  struct SmsUndoRecord *v78; // r10
  _QWORD *v79; // rbx
  _QWORD *v80; // rdi
  unsigned __int64 v81; // rcx
  _QWORD *v82; // r9
  _QWORD *v83; // r8
  __int64 i; // rdx
  unsigned __int64 v85; // r10
  struct _CmsRow *v86; // [rsp+20h] [rbp-E0h]
  struct _CmsRow *v87; // [rsp+20h] [rbp-E0h]
  char v88; // [rsp+60h] [rbp-A0h]
  unsigned int v89; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v90[2]; // [rsp+68h] [rbp-98h]
  struct _SmsQuickIndex *v91; // [rsp+70h] [rbp-90h]
  struct _CmsKey *v92; // [rsp+78h] [rbp-88h]
  struct CmsChecksum *v93; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v94; // [rsp+88h] [rbp-78h]
  unsigned __int128 v95; // [rsp+90h] [rbp-70h]
  struct _CmsRow *v96; // [rsp+A0h] [rbp-60h]
  __int64 v97; // [rsp+A8h] [rbp-58h]
  unsigned int *v98; // [rsp+B0h] [rbp-50h]
  __int128 v99; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v100; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v101[32]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v102; // [rsp+100h] [rbp+0h]
  __int64 v103; // [rsp+110h] [rbp+10h]
  int v104; // [rsp+118h] [rbp+18h]
  __int128 v105; // [rsp+120h] [rbp+20h]
  __int64 v106; // [rsp+130h] [rbp+30h]
  int v107; // [rsp+150h] [rbp+50h]
  _OWORD v108[5]; // [rsp+160h] [rbp+60h] BYREF
  size_t Size[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  size_t v110; // [rsp+1C0h] [rbp+C0h]
  void *v111; // [rsp+1C8h] [rbp+C8h]
  PVOID P; // [rsp+1D0h] [rbp+D0h]
  char v113; // [rsp+1D8h] [rbp+D8h]
  int v114; // [rsp+1DCh] [rbp+DCh]
  char v115; // [rsp+1E0h] [rbp+E0h] BYREF
  char v116[8]; // [rsp+220h] [rbp+120h] BYREF
  void *v117; // [rsp+228h] [rbp+128h]
  void *v118; // [rsp+238h] [rbp+138h]
  PVOID v119; // [rsp+240h] [rbp+140h]
  char v120; // [rsp+248h] [rbp+148h]
  int v121; // [rsp+24Ch] [rbp+14Ch]
  char v122; // [rsp+250h] [rbp+150h] BYREF
  __int128 v123; // [rsp+290h] [rbp+190h] BYREF
  __int128 v124; // [rsp+2A0h] [rbp+1A0h]
  __int64 v125; // [rsp+2B0h] [rbp+1B0h]

  v10 = a8;
  v96 = a3;
  v90[0] = a4;
  v91 = a6;
  memset(v108, 0, 0x48u);
  v13 = a5;
  v14 = 0;
  v89 = 0;
  v15 = 0;
  if ( a7 )
    return 3221225485LL;
  if ( (a9 & 2) != 0 )
  {
    v15 = 5120;
  }
  else if ( (a9 & 4) != 0 )
  {
    v15 = 6144;
  }
  else
  {
    if ( (a9 & 8) == 0 )
      goto LABEL_10;
    v15 = 4608;
  }
  v14 = 1;
LABEL_10:
  v120 = 0;
  v113 = 0;
  v121 = 64;
  v119 = &v122;
  v114 = 64;
  P = &v115;
  v94 = 0;
  v125 = 0;
  v106 = 0;
  v17 = *(_QWORD *)this;
  v103 = 0;
  v104 = 0;
  v107 = 0;
  v18 = *(void (__fastcall **)(CmsBPlusTable *, struct CmsTransactionContext *, _QWORD))(v17 + 64);
  v123 = 0;
  v124 = 0;
  v102 = 0;
  v105 = 0;
  v18(this, a2, 0);
  v19 = *(_QWORD *)this;
  v88 = 0;
  v92 = a3;
  a5 = v13;
  (*(void (__fastcall **)(CmsBPlusTable *, _OWORD *))(v19 + 160))(this, v108);
  if ( (*((_DWORD *)this + 4) & 0x1000000) != 0 )
    goto LABEL_152;
  v20 = *((_OWORD *)a3 + 1);
  v97 = 4;
  v98 = &a5;
  v99 = v20;
  if ( a5 )
    LODWORD(v99) = v99 - a5;
  v21 = *(_QWORD *)(*((_QWORD *)a2 + 243) + 8LL);
  if ( !v21 )
    v21 = *((_QWORD *)a2 + 243) + 8LL;
  v94 = (_QWORD *)v21;
  v86 = (struct _CmsRow *)&v99;
  FirstIndexEntry = CmsTransactionContext::AddRedoRecord(a2, this, 1, a3);
  if ( FirstIndexEntry >= 0 )
  {
LABEL_152:
    v23 = _SmsIndexEntry::MmsKeyIsInData(a3, (struct _CmsRow *)((char *)a3 + 16));
    v26 = -8;
    if ( v23 )
    {
      v28 = 0;
    }
    else
    {
      v27 = _SmsIndexEntry::MmsKeyLengthOutsideData(a3, v24);
      v28 = v26 & (v27 + 7);
    }
    if ( (v26 & (unsigned int)(*v25 + 7)) + 16 + v28 > (unsigned __int64)*(unsigned int *)(*((_QWORD *)this + 3) + 40LL)
                                                     + 16 )
    {
      FirstIndexEntry = -1073739516;
      goto LABEL_120;
    }
    v29 = (struct _SmsQuickIndex *)((unsigned __int64)v91 & -(__int64)(v14 != 0));
    v30 = 0;
    LODWORD(v86) = v15 | 9;
    FirstIndexEntry = CmsBPlusTable::FindFirstIndexEntry(this, a2, a3, (struct SmsPage **)v108, v86, 0, &v89, v29, 0);
    if ( FirstIndexEntry >= 0 )
    {
      if ( v89 )
      {
        (*(void (__fastcall **)(CmsBPlusTable *, struct CmsTransactionContext *, _OWORD *))(*(_QWORD *)this + 168LL))(
          this,
          a2,
          v108);
        FirstIndexEntry = 0x40000000;
        goto LABEL_118;
      }
      v31 = *((_QWORD *)&v108[2] + 1);
      if ( (*(_DWORD *)(*((_QWORD *)this + 3) + 44LL) & 2) != 0 && *((_BYTE *)this + 154) )
      {
        if ( CmsTable::UseStreamIndexEntry(this, *((struct _SmsIndexHeader **)&v108[2] + 1)) )
        {
          v33 = *((unsigned int *)v32 + 2);
          v34 = *(_QWORD *)v32;
          v95 = __PAIR128__(v33, *(_QWORD *)v32);
        }
        else
        {
          v95 = *v32;
          v33 = *((_QWORD *)&v95 + 1);
          v34 = v95;
        }
        if ( DWORD2(v108[3]) == *(_DWORD *)(v31 + 20) && v34 + v33 - 1 > *(_QWORD *)&v108[4] )
        {
          (*(void (__fastcall **)(CmsBPlusTable *, struct CmsTransactionContext *, _OWORD *))(*(_QWORD *)this + 168LL))(
            this,
            a2,
            v108);
          FirstIndexEntry = -1073741698;
          *v10 = *(_QWORD *)&v108[4] + 1LL;
          goto LABEL_120;
        }
      }
      v35 = v92;
      v36 = v90[0];
      while ( 1 )
      {
        if ( *(_BYTE *)(v31 + 12) || (v37 = 1, (*(_DWORD *)(*((_QWORD *)this + 3) + 44LL) & 4) == 0) )
          v37 = 0;
        if ( v37 )
        {
          v38 = (*((_DWORD *)v35 + 4) + 7) & 0xFFFFFFF8;
        }
        else
        {
          v41 = _SmsIndexEntry::MmsKeyIsInData(v35, (struct _CmsKey *)((char *)v35 + 16))
              ? 0
              : (_SmsIndexEntry::MmsKeyLengthOutsideData(v35, v39) + 7) & 0xFFFFFFF8;
          v38 = ((*v40 + 7) & 0xFFFFFFF8) + v41 + 16;
        }
        if ( (unsigned __int64)v38 + 4 <= *(unsigned int *)(v31 + 8) )
          break;
        if ( !v88 && CmsBPlusTable::IsDelayCollapseTree(this) && (*((_DWORD *)this + 4) & 0x20000) == 0 )
        {
          CmsVolume::BeginTopLevelAction(v42, a2, (struct _SmsTopLevelAction *)v101, 0, 0);
          v31 = *((_QWORD *)&v108[2] + 1);
          v88 = 1;
        }
        if ( (*(_BYTE *)(v31 + 13) & 2) != 0 )
        {
          if ( FirstIndexEntry >= 0 )
          {
            FirstIndexEntry = CmsBPlusTable::PushIndexRoot(
                                this,
                                a2,
                                (struct _SmsIndexHeader *)v31,
                                (struct SmsPage **)v108,
                                0,
                                0);
            if ( FirstIndexEntry < 0 )
              goto LABEL_58;
          }
        }
        else
        {
          FirstIndexEntry = CmsBPlusTable::InsertWithBucketSplit(
                              this,
                              a2,
                              v35,
                              v36,
                              (struct _SmsLookupStack *)v108,
                              (struct CmsRowWithBuffer *)Size,
                              (struct SmsDirectorData *)&v123,
                              a5,
                              v91);
          if ( FirstIndexEntry < 0 )
            goto LABEL_58;
          *((_DWORD *)a2 + 638) |= 1u;
          v43 = *((_BYTE *)this + 152);
          v93 = 0;
          FirstIndexEntry = CmsChecksum::GetMetadataChecksumClass(v43, &v93);
          if ( FirstIndexEntry < 0 )
            goto LABEL_58;
          v44 = v93;
          v45 = (*(__int64 (__fastcall **)(struct CmsChecksum *, _QWORD))(*(_QWORD *)v93 + 168LL))(
                  v93,
                  *((_QWORD *)a2 + 4));
          (*(void (__fastcall **)(struct CmsChecksum *, _QWORD, _QWORD, char *))(*(_QWORD *)v44 + 24LL))(
            v44,
            *((_QWORD *)a2 + 4),
            v45,
            (char *)v111 + 32);
          v91 = 0;
          a5 = (*((_DWORD *)v111 + 9) + 7) & 0xFFFFFFF8;
          FirstIndexEntry = CmsRowWithBuffer::NewLength(
                              (CmsRowWithBuffer *)v116,
                              Size[0],
                              a5 + (unsigned int)v110,
                              0,
                              0);
          if ( FirstIndexEntry < 0 )
            goto LABEL_58;
          memmove(v117, (const void *)Size[1], LODWORD(Size[0]));
          memmove(v118, v111, (unsigned int)v110);
          v35 = (struct _CmsKey *)v116;
          ++v30;
          v92 = (struct _CmsKey *)v116;
        }
        (*(void (__fastcall **)(CmsBPlusTable *, struct CmsTransactionContext *, _OWORD *))(*(_QWORD *)this + 168LL))(
          this,
          a2,
          v108);
        (*(void (__fastcall **)(CmsBPlusTable *, _OWORD *))(*(_QWORD *)this + 160LL))(this, v108);
        LODWORD(v87) = 9;
        FirstIndexEntry = CmsBPlusTable::FindFirstIndexEntry(
                            this,
                            a2,
                            v35,
                            (struct SmsPage **)v108,
                            v87,
                            v30,
                            &v89,
                            0,
                            0);
        if ( (_QWORD)v123 )
        {
          v100 = 0;
          LengthPhys = _SmsIndexEntry::GetLengthPhys(*(_SmsIndexEntry **)&v108[3]);
          if ( !CmsBPlusTable::AllocateUndo((__int64)this, (__int64)a2, 7, v47, LengthPhys, 0) )
          {
            FirstIndexEntry = -1073741670;
            goto LABEL_58;
          }
          v48 = _SmsIndexEntry::GetLengthPhys(*(_SmsIndexEntry **)&v108[3]);
          CmsBPlusTable::FormatUndoRecord(this, a2, v50, (struct _SmsLookupStack *)v108, v49, v48, 0);
          _SmsIndexEntry::MmsDataFromIndexEntry(*(_SmsIndexEntry **)&v108[3], (struct _CmsData *)&v100);
          v51 = *((_QWORD *)&v100 + 1);
          **((_OWORD **)&v100 + 1) = v123;
          *(_OWORD *)(v51 + 16) = v124;
          v123 = 0;
          v124 = 0;
        }
        v31 = *((_QWORD *)&v108[2] + 1);
      }
      v59 = 0;
      v60 = 0;
      if ( !v88 )
      {
        if ( (v61 = *((_QWORD *)this + 2), (v61 & 0x20000) == 0)
          && (*(_DWORD *)(*((_QWORD *)this + 12) + 16LL) & 2) == 0
          || (v61 & 0x400000) != 0 )
        {
          if ( (*((_QWORD *)this + 2) & 0x20000LL) == 0 && (*(_BYTE *)(*((_QWORD *)this + 3) + 44LL) & 2) != 0 )
            v60 = 1;
        }
      }
      v62 = v60 != 0 ? 31 : 4;
      if ( (*((_DWORD *)a2 + 4) & 0x1000LL) != 0 )
      {
        v63 = 1;
LABEL_92:
        CmsBPlusTable::InsertSimple(this, a2, v92, (struct _SmsLookupStack *)v108, a5, v91);
        if ( DWORD2(v108[3]) < *(_DWORD *)(*((_QWORD *)&v108[2] + 1) + 20LL) )
          v59 = (const void *)(*((_QWORD *)&v108[2] + 1)
                             + *(unsigned __int16 *)(*((_QWORD *)&v108[2] + 1)
                                                   + *(unsigned int *)(*((_QWORD *)&v108[2] + 1) + 16LL)
                                                   + 4LL * DWORD2(v108[3])));
        if ( v63 != 1 )
        {
          *(_DWORD *)(v63 + 32) = 0;
          *(_DWORD *)(v63 + 8) = v38;
          *(_QWORD *)(v63 + 40) = this;
          *(_OWORD *)(v63 + 48) = v108[0];
          *(_OWORD *)(v63 + 64) = v108[1];
          *(_OWORD *)(v63 + 80) = v108[2];
          *(_OWORD *)(v63 + 96) = v108[3];
          *(_QWORD *)(v63 + 112) = *(_QWORD *)&v108[4];
          v72 = *(_QWORD *)&v108[0];
          _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)&v108[0] + 324LL), 1u);
          if ( (*(_QWORD *)(v72 + 408) & 0x20) == 0 )
          {
            ExAcquireResourceExclusiveLite((PERESOURCE)(v72 + 416), 0);
            if ( !CmsBPlusTable::WasUpdateDeferred(*(CmsBPlusTable **)(v72 + 120)) )
              ++*((_DWORD *)a2 + 6);
          }
          if ( *(_QWORD *)&v108[0]
            && (!*(_BYTE *)(*(_QWORD *)&v108[0] + 328LL) && *(CmsBPlusTable **)(*(_QWORD *)&v108[0] + 120LL) == this
             || !*((_BYTE *)this + 154)) )
          {
            *(_BYTE *)(v63 + 20) |= 1u;
          }
          v73 = *(_DWORD *)(v63 + 8);
          if ( v73 )
          {
            v74 = *(void **)(v63 + 24);
            if ( v59 )
            {
              if ( v59 != v74 )
                memmove(v74, v59, v73);
            }
            else
            {
              memset(v74, 0, *(unsigned int *)(v63 + 8));
            }
          }
          *(_QWORD *)v63 = *((_QWORD *)a2 + 324);
          *((_QWORD *)a2 + 324) = v63;
          if ( *(_DWORD *)(v63 + 16) == 18 )
            _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(v63 + 40) + 8LL), 1u);
        }
        goto LABEL_58;
      }
      PoolWithTag = 0;
      *(_QWORD *)v90 = v38 + 120;
      CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
      v66 = *(_QWORD *)v90;
      v67 = (unsigned int *)(qword_1C0136F20 + 192LL * (CurrentProcessorNumber % NumProcessors));
      if ( *(_QWORD *)v90 > (unsigned __int64)*v67 )
      {
        v67 = 0;
      }
      else
      {
        if ( *((_BYTE *)v67 + 8) )
        {
          v68 = (struct _NPAGED_LOOKASIDE_LIST *)(v67 + 16);
          if ( *((_BYTE *)v67 + 9) )
            v69 = ExAllocateFromNPagedLookasideList(v68);
          else
            v69 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v68);
          goto LABEL_75;
        }
        if ( (int)v67[20] <= (int)v67[22] )
          goto LABEL_84;
        v70 = _InterlockedDecrement((volatile signed __int32 *)v67 + 20);
        if ( v70 >= (int)v67[22] && v70 >= 0 )
        {
          v69 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v67 + 4);
LABEL_75:
          v66 = *(_QWORD *)v90;
          PoolWithTag = v69;
          goto LABEL_83;
        }
        _InterlockedAdd((volatile signed __int32 *)v67 + 20, 1u);
      }
LABEL_83:
      if ( PoolWithTag )
      {
LABEL_88:
        *PoolWithTag = v67;
        v63 = (__int64)(PoolWithTag + 1);
        if ( v63 )
        {
          v59 = 0;
          *(_DWORD *)(v63 + 16) = v62;
          *(_WORD *)(v63 + 20) = 0;
          *(_QWORD *)(v63 + 40) = this;
          *(_DWORD *)(v63 + 12) = v38;
          *(_DWORD *)(v63 + 8) = v38;
          *(_DWORD *)(v63 + 32) = 0;
          if ( v38 )
          {
            *(_QWORD *)(v63 + 24) = v63 + 120;
            memset((void *)(v63 + 120), 0, v38);
          }
          else
          {
            *(_QWORD *)(v63 + 24) = 0;
          }
          goto LABEL_92;
        }
LABEL_110:
        FirstIndexEntry = -1073741670;
LABEL_58:
        (*(void (__fastcall **)(CmsBPlusTable *, struct CmsTransactionContext *, _OWORD *))(*(_QWORD *)this + 168LL))(
          this,
          a2,
          v108);
        if ( v88 )
        {
          if ( FirstIndexEntry < 0 )
          {
            CmsVolume::AbortTopLevelAction(*((CmsVolume **)a2 + 4), a2, (struct _SmsTopLevelAction *)v101);
          }
          else
          {
            LODWORD(v87) = 9;
            FirstIndexEntry = CmsBPlusTable::FindFirstIndexEntry(
                                this,
                                a2,
                                v96,
                                (struct SmsPage **)v108,
                                v87,
                                0,
                                &v89,
                                0,
                                0);
            CmsVolume::CommitTopLevelAction(*((CmsVolume **)a2 + 4), a2, (struct _SmsTopLevelAction *)v101, 0);
            v52 = _SmsIndexEntry::GetLengthPhys(*(_SmsIndexEntry **)&v108[3]);
            if ( CmsBPlusTable::AllocateUndo(
                   (__int64)this,
                   (__int64)a2,
                   (*(_DWORD *)(*((_QWORD *)this + 3) + 44LL) & 2) != 0 ? 31 : 4,
                   v53,
                   v52,
                   0) )
            {
              _SmsIndexEntry::GetLengthPhys(*(_SmsIndexEntry **)&v108[3]);
              v76 = CmsBPlusTable::MmsIndexEntryByOffset(
                      v75,
                      *((struct _SmsIndexHeader **)&v108[2] + 1),
                      DWORD2(v108[3]));
              CmsBPlusTable::FormatUndoRecord(this, a2, v78, (struct _SmsLookupStack *)v108, v76, v77, 0);
            }
            else
            {
              v55 = CmsBPlusTable::MmsIndexEntryByOffset(
                      v54,
                      *((struct _SmsIndexHeader **)&v108[2] + 1),
                      DWORD2(v108[3]));
              CmsBPlusTable::MmsMarkIndexEntryDeleted(v57, v56, v55, v58);
              FirstIndexEntry = -1073741670;
            }
            (*(void (__fastcall **)(CmsBPlusTable *, struct CmsTransactionContext *, _OWORD *))(*(_QWORD *)this + 168LL))(
              this,
              a2,
              v108);
          }
        }
        if ( FirstIndexEntry < 0 )
        {
LABEL_120:
          v79 = (_QWORD *)*((_QWORD *)a2 + 243);
          if ( v94 )
          {
            v80 = 0;
            if ( v94 != v79 + 1 )
              v80 = v94;
            v81 = v80 ? v80[6] : *v79;
            if ( v81 )
            {
              if ( v80 )
                v80[6] = 0;
              *(_OWORD *)v81 = 0;
              v82 = 0;
              v83 = 0;
              *(_OWORD *)(v81 + 16) = 0;
              *(_OWORD *)(v81 + 32) = 0;
              *(_QWORD *)(v81 + 48) = 0;
              for ( i = v79[4]; i; i = *(_QWORD *)(i + 48) )
              {
                v85 = *(_QWORD *)(i + 16);
                if ( v81 >= v85 && v81 < v85 + *(unsigned int *)(i + 24) )
                {
                  v82 = (_QWORD *)i;
                  break;
                }
                v83 = (_QWORD *)i;
              }
              if ( v82[2] != v81 )
              {
                v83 = v82;
                v82 = (_QWORD *)v82[6];
                *((_DWORD *)v83 + 7) = v81 - *((_DWORD *)v83 + 2);
              }
              if ( v83 )
              {
                v79[5] = v83;
                v83[6] = 0;
              }
              else
              {
                v79[4] = 0;
                v79[5] = 0;
              }
              FreeBufferList(v82);
              v79[1] = v80;
              if ( !v80 )
                *v79 = 0;
              v79[6] = 0;
            }
          }
          goto LABEL_143;
        }
        _InterlockedAdd64((volatile signed __int64 *)this + 7, 1u);
        goto LABEL_118;
      }
LABEL_84:
      if ( v67 )
        v71 = v67[1];
      else
        v71 = v66 + 8;
      PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, v71, 0x6950534Du);
      if ( !PoolWithTag )
        goto LABEL_110;
      goto LABEL_88;
    }
  }
LABEL_118:
  if ( FirstIndexEntry < 0 || FirstIndexEntry == 0x40000000 )
    goto LABEL_120;
LABEL_143:
  if ( v113 && P )
    ExFreePoolWithTag(P, 0);
  if ( v120 )
  {
    if ( v119 )
      ExFreePoolWithTag(v119, 0);
  }
  return (unsigned int)FirstIndexEntry;
}

```

## disassembly

```asm
0x1c001b000  push    rbp
0x1c001b002  push    rbx
0x1c001b003  push    rsi
0x1c001b004  push    rdi
0x1c001b005  push    r12
0x1c001b007  push    r13
0x1c001b009  push    r14
0x1c001b00b  push    r15
0x1c001b00d  lea     rbp, [rsp-1C8h]
0x1c001b015  sub     rsp, 2C8h
0x1c001b01c  mov     rax, cs:__security_cookie
0x1c001b023  xor     rax, rsp
0x1c001b026  mov     [rbp+200h+var_48], rax
0x1c001b02d  mov     rax, [rbp+200h+arg_28]
0x1c001b034  mov     rsi, rdx
0x1c001b037  mov     r12, [rbp+200h+arg_38]
0x1c001b03e  xor     edx, edx; Val
0x1c001b040  mov     r13, r8
0x1c001b043  mov     [rbp+200h+var_260], r8
0x1c001b047  mov     rdi, rcx
0x1c001b04a  mov     [rsp+300h+var_298], r9d
0x1c001b04f  lea     rcx, [rbp+200h+var_1A0]; void *
0x1c001b053  mov     [rsp+300h+var_290], rax
0x1c001b058  lea     r8d, [rdx+48h]; Size
0x1c001b05c  call    memset
0x1c001b061  mov     r15d, [rbp+200h+arg_20]
0x1c001b068  xor     edx, edx
0x1c001b06a  mov     r14b, dl
0x1c001b06d  mov     [rsp+300h+var_29C], edx
0x1c001b071  mov     ebx, edx
0x1c001b073  cmp     [rbp+200h+arg_30], rdx
0x1c001b07a  jz      short loc_1C001B086
0x1c001b07c  mov     eax, 0C000000Dh
0x1c001b081  jmp     loc_1C001BC53
0x1c001b086  mov     eax, [rbp+200h+arg_40]
0x1c001b08c  mov     ecx, 1
0x1c001b091  test    al, 2
0x1c001b093  jz      short loc_1C001B09C
0x1c001b095  mov     ebx, 1400h
0x1c001b09a  jmp     short loc_1C001B0B0
0x1c001b09c  test    al, 4
0x1c001b09e  jz      short loc_1C001B0A7
0x1c001b0a0  mov     ebx, 1800h
0x1c001b0a5  jmp     short loc_1C001B0B0
0x1c001b0a7  test    al, 8
0x1c001b0a9  jz      short loc_1C001B0B3
0x1c001b0ab  mov     ebx, 1200h
0x1c001b0b0  mov     r14b, cl
0x1c001b0b3  xorps   xmm0, xmm0
0x1c001b0b6  mov     [rbp+200h+var_B8], dl
0x1c001b0bc  mov     ecx, 40h ; '@'
0x1c001b0c1  mov     [rbp+200h+var_128], dl
0x1c001b0c7  lea     rax, [rbp+200h+var_B0]
0x1c001b0ce  mov     [rbp+200h+var_B4], ecx
0x1c001b0d4  mov     [rbp+200h+var_C0], rax
0x1c001b0db  xorps   xmm1, xmm1
0x1c001b0de  lea     rax, [rbp+200h+var_120]
0x1c001b0e5  mov     [rbp+200h+var_124], ecx
0x1c001b0eb  mov     [rbp+200h+P], rax
0x1c001b0f2  xor     r8d, r8d
0x1c001b0f5  xor     eax, eax
0x1c001b0f7  mov     [rbp+200h+var_278], rdx
0x1c001b0fb  mov     [rbp+200h+var_50], rax
0x1c001b102  mov     rcx, rdi
0x1c001b105  mov     [rbp+200h+var_1D0], rax
0x1c001b109  mov     rax, [rdi]
0x1c001b10c  mov     [rbp+200h+var_1F0], rdx
0x1c001b110  mov     [rbp+200h+var_1E8], edx
0x1c001b113  mov     [rbp+200h+var_1B0], edx
0x1c001b116  mov     rdx, rsi
0x1c001b119  mov     rax, [rax+40h]
0x1c001b11d  movups  [rbp+200h+var_70], xmm0
0x1c001b124  movups  [rbp+200h+var_60], xmm0
0x1c001b12b  movdqa  [rbp+200h+var_200], xmm0
0x1c001b130  movups  [rbp+200h+var_1E0], xmm1
0x1c001b134  call    cs:__guard_dispatch_icall_fptr
0x1c001b13a  mov     rax, [rdi]
0x1c001b13d  lea     rdx, [rbp+200h+var_1A0]
0x1c001b141  mov     rcx, rdi
0x1c001b144  mov     [rsp+300h+var_2A0], 0
0x1c001b149  mov     [rsp+300h+var_288], r13
0x1c001b14e  mov     [rbp+200h+arg_20], r15d
0x1c001b155  mov     rax, [rax+0A0h]
0x1c001b15c  call    cs:__guard_dispatch_icall_fptr
0x1c001b162  mov     eax, [rdi+10h]
0x1c001b165  bt      rax, 18h
0x1c001b16a  jb      loc_1C001B202
0x1c001b170  movups  xmm0, xmmword ptr [r13+10h]
0x1c001b175  mov     ecx, [rbp+200h+arg_20]
0x1c001b17b  lea     rax, [rbp+200h+arg_20]
0x1c001b182  xor     r8d, r8d
0x1c001b185  mov     [rbp+200h+var_258], 4
0x1c001b18d  mov     [rbp+200h+var_250], rax
0x1c001b191  movdqu  [rbp+200h+var_248], xmm0
0x1c001b196  test    ecx, ecx
0x1c001b198  jz      short loc_1C001B19D
0x1c001b19a  sub     dword ptr [rbp+200h+var_248], ecx
0x1c001b19d  mov     rax, [rsi+798h]
0x1c001b1a4  mov     r9, r13
0x1c001b1a7  add     rax, 8
0x1c001b1ab  mov     [rsp+300h+var_2B0], r8
0x1c001b1b0  mov     [rsp+300h+var_2B8], r8b
0x1c001b1b5  mov     [rsp+300h+var_2C8], r8
0x1c001b1ba  mov     rdx, [rax]
0x1c001b1bd  test    rdx, rdx
0x1c001b1c0  cmovz   rdx, rax
0x1c001b1c4  mov     eax, r8d
0x1c001b1c7  test    ecx, ecx
0x1c001b1c9  mov     [rbp+200h+var_278], rdx
0x1c001b1cd  mov     r8d, 1
0x1c001b1d3  mov     rdx, rdi
0x1c001b1d6  setnz   al
0x1c001b1d9  mov     rcx, rsi
0x1c001b1dc  mov     dword ptr [rsp+300h+var_2D0], eax
0x1c001b1e0  lea     rax, [rbp+200h+var_258]
0x1c001b1e4  mov     [rsp+300h+var_2D8], rax
0x1c001b1e9  lea     rax, [rbp+200h+var_248]
0x1c001b1ed  mov     [rsp+300h+var_2E0], rax
0x1c001b1f2  call    ?AddRedoRecord@CmsTransactionContext@@QEAAJPEAVCmsBPlusTable@@W4_MS_REDO_OPERATION@@PEAU_CmsKey@@PEAU_CmsData@@3K0KEPEAJ@Z; CmsTransactionContext::AddRedoRecord(CmsBPlusTable *,_MS_REDO_OPERATION,_CmsKey *,_CmsData *,_CmsData *,ulong,CmsBPlusTable *,ulong,uchar,long *)
0x1c001b1f7  mov     r15d, eax
0x1c001b1fa  test    eax, eax
0x1c001b1fc  js      loc_1C001BB2D
0x1c001b202  lea     r10, [r13+10h]
0x1c001b206  mov     rcx, r13; struct _CmsKey *
0x1c001b209  mov     rdx, r10; struct _CmsData *
0x1c001b20c  call    ?MmsKeyIsInData@_SmsIndexEntry@@SAKPEAU_CmsKey@@PEAU_CmsData@@@Z; _SmsIndexEntry::MmsKeyIsInData(_CmsKey *,_CmsData *)
0x1c001b211  mov     r11d, 0FFFFFFF8h
0x1c001b217  test    eax, eax
0x1c001b219  jnz     short loc_1C001B22B
0x1c001b21b  mov     rcx, r13; struct _CmsKey *
0x1c001b21e  call    ?MmsKeyLengthOutsideData@_SmsIndexEntry@@SAKPEAU_CmsKey@@PEAU_CmsData@@@Z; _SmsIndexEntry::MmsKeyLengthOutsideData(_CmsKey *,_CmsData *)
0x1c001b223  lea     edx, [rax+7]
0x1c001b226  and     edx, r11d
0x1c001b229  jmp     short loc_1C001B22D
0x1c001b22b  xor     edx, edx
0x1c001b22d  mov     eax, [r10]
0x1c001b230  add     eax, 7
0x1c001b233  and     eax, r11d
0x1c001b236  add     eax, 10h
0x1c001b239  add     edx, eax
0x1c001b23b  mov     rax, [rdi+18h]
0x1c001b23f  mov     ecx, [rax+28h]
0x1c001b242  add     rcx, 10h
0x1c001b246  cmp     rdx, rcx
0x1c001b249  jbe     short loc_1C001B259
0x1c001b24b  mov     r15d, 0C0000904h
0x1c001b251  xor     r13d, r13d
0x1c001b254  jmp     loc_1C001BB42
0x1c001b259  neg     r14b
0x1c001b25c  lea     r9, [rbp+200h+var_1A0]; struct _SmsLookupStack *
0x1c001b260  mov     r8, r13; struct _CmsRow *
0x1c001b263  mov     rdx, rsi; struct CmsTransactionContext *
0x1c001b266  sbb     rax, rax
0x1c001b269  mov     rcx, rdi; this
0x1c001b26c  and     rax, [rsp+300h+var_290]
0x1c001b271  xor     r14d, r14d
0x1c001b274  mov     [rsp+300h+var_2C0], r14; struct _SmsView *
0x1c001b279  or      ebx, 9
0x1c001b27c  mov     [rsp+300h+var_2C8], rax; struct _SmsQuickIndex *
0x1c001b281  lea     rax, [rsp+300h+var_29C]
0x1c001b286  mov     [rsp+300h+var_2D0], rax; unsigned int *
0x1c001b28b  mov     byte ptr [rsp+300h+var_2D8], r14b; char
0x1c001b290  mov     dword ptr [rsp+300h+var_2E0], ebx; struct _CmsRow *
0x1c001b294  call    ?FindFirstIndexEntry@CmsBPlusTable@@AEAAJPEAVCmsTransactionContext@@PEAU_CmsRow@@PEAU_SmsLookupStack@@JEPEAKPEAU_SmsQuickIndex@@PEAU_SmsView@@@Z; CmsBPlusTable::FindFirstIndexEntry(CmsTransactionContext *,_CmsRow *,_SmsLookupStack *,long,uchar,ulong *,_SmsQuickIndex *,_SmsView *)
0x1c001b299  mov     r15d, eax
0x1c001b29c  test    eax, eax
0x1c001b29e  js      loc_1C001BB2D
0x1c001b2a4  cmp     [rsp+300h+var_29C], r14d
0x1c001b2a9  jnz     loc_1C001BB0D
0x1c001b2af  mov     rax, [rdi+18h]
0x1c001b2b3  mov     r10, [rbp+200h+var_178]
0x1c001b2ba  mov     ecx, [rax+2Ch]
0x1c001b2bd  test    cl, 2
0x1c001b2c0  jz      loc_1C001B35A
0x1c001b2c6  cmp     [rdi+9Ah], r14b
0x1c001b2cd  jz      loc_1C001B35A
0x1c001b2d3  mov     r8, [r13+8]
0x1c001b2d7  mov     rdx, r10; struct _SmsIndexHeader *
0x1c001b2da  mov     rcx, rdi; this
0x1c001b2dd  call    ?UseStreamIndexEntry@CmsTable@@QEAAEPEAU_SmsIndexHeader@@@Z; CmsTable::UseStreamIndexEntry(_SmsIndexHeader *)
0x1c001b2e2  xor     r13d, r13d
0x1c001b2e5  test    al, al
0x1c001b2e7  jz      short loc_1C001B2FA
0x1c001b2e9  mov     ecx, [r8+8]
0x1c001b2ed  mov     rdx, [r8]
0x1c001b2f0  mov     qword ptr [rbp+200h+var_270+8], rcx
0x1c001b2f4  mov     qword ptr [rbp+200h+var_270], rdx
0x1c001b2f8  jmp     short loc_1C001B30B
0x1c001b2fa  movups  xmm0, xmmword ptr [r8]
0x1c001b2fe  movdqu  [rbp+200h+var_270], xmm0
0x1c001b303  mov     rcx, qword ptr [rbp+200h+var_270+8]
0x1c001b307  mov     rdx, qword ptr [rbp+200h+var_270]
0x1c001b30b  mov     eax, [r10+14h]
0x1c001b30f  cmp     dword ptr [rbp+200h+var_170+8], eax
0x1c001b315  jnz     short loc_1C001B35D
0x1c001b317  lea     rax, [rcx-1]
0x1c001b31b  add     rax, rdx
0x1c001b31e  cmp     rax, [rbp+200h+var_160]
0x1c001b325  jbe     short loc_1C001B35D
0x1c001b327  mov     rax, [rdi]
0x1c001b32a  lea     r8, [rbp+200h+var_1A0]
0x1c001b32e  mov     rdx, rsi
0x1c001b331  mov     rcx, rdi
0x1c001b334  mov     rax, [rax+0A8h]
0x1c001b33b  call    cs:__guard_dispatch_icall_fptr
0x1c001b341  mov     rax, [rbp+200h+var_160]
0x1c001b348  mov     r15d, 0C000007Eh
0x1c001b34e  inc     rax
0x1c001b351  mov     [r12], rax
0x1c001b355  jmp     loc_1C001BB42
0x1c001b35a  xor     r13d, r13d
0x1c001b35d  mov     rbx, [rsp+300h+var_288]
0x1c001b362  mov     r12d, [rsp+300h+var_298]
0x1c001b367  cmp     [r10+0Ch], r13b
0x1c001b36b  jnz     short loc_1C001B37B
0x1c001b36d  mov     rax, [rdi+18h]
0x1c001b371  mov     ecx, [rax+2Ch]
0x1c001b374  mov     al, 1
0x1c001b376  test    cl, 4
0x1c001b379  jnz     short loc_1C001B37E
0x1c001b37b  mov     al, r13b
0x1c001b37e  lea     r11, [rbx+10h]
0x1c001b382  test    al, al
0x1c001b384  jz      short loc_1C001B393
0x1c001b386  mov     r13d, [r11]
0x1c001b389  add     r13d, 7
0x1c001b38d  and     r13d, 0FFFFFFF8h
0x1c001b391  jmp     short loc_1C001B3C5
0x1c001b393  mov     rdx, r11; struct _CmsData *
0x1c001b396  mov     rcx, rbx; struct _CmsKey *
0x1c001b399  call    ?MmsKeyIsInData@_SmsIndexEntry@@SAKPEAU_CmsKey@@PEAU_CmsData@@@Z; _SmsIndexEntry::MmsKeyIsInData(_CmsKey *,_CmsData *)
0x1c001b39e  test    eax, eax
0x1c001b3a0  jnz     short loc_1C001B3B2
0x1c001b3a2  mov     rcx, rbx; struct _CmsKey *
0x1c001b3a5  call    ?MmsKeyLengthOutsideData@_SmsIndexEntry@@SAKPEAU_CmsKey@@PEAU_CmsData@@@Z; _SmsIndexEntry::MmsKeyLengthOutsideData(_CmsKey *,_CmsData *)
0x1c001b3aa  lea     edx, [rax+7]
0x1c001b3ad  and     edx, 0FFFFFFF8h
0x1c001b3b0  jmp     short loc_1C001B3B5
0x1c001b3b2  mov     edx, r13d
0x1c001b3b5  mov     eax, [r11]
0x1c001b3b8  lea     r13d, [rdx+10h]
0x1c001b3bc  add     eax, 7
0x1c001b3bf  and     eax, 0FFFFFFF8h
0x1c001b3c2  add     r13d, eax
0x1c001b3c5  mov     ecx, [r10+8]
0x1c001b3c9  mov     eax, r13d
0x1c001b3cc  add     rax, 4
0x1c001b3d0  cmp     rax, rcx
0x1c001b3d3  jbe     loc_1C001B79A
0x1c001b3d9  xor     r13d, r13d
0x1c001b3dc  cmp     [rsp+300h+var_2A0], r13b
0x1c001b3e1  jnz     short loc_1C001B419
0x1c001b3e3  mov     rcx, rdi; this
0x1c001b3e6  call    ?IsDelayCollapseTree@CmsBPlusTable@@IEAAEXZ; CmsBPlusTable::IsDelayCollapseTree(void)
0x1c001b3eb  test    al, al
0x1c001b3ed  jz      short loc_1C001B419
0x1c001b3ef  mov     eax, [rdi+10h]
0x1c001b3f2  bt      rax, 11h
0x1c001b3f7  jb      short loc_1C001B419
0x1c001b3f9  xor     r9d, r9d; unsigned __int8
0x1c001b3fc  mov     byte ptr [rsp+300h+var_2E0], r13b; char
0x1c001b401  lea     r8, [rbp+200h+var_220]; struct _SmsTopLevelAction *
0x1c001b405  mov     rdx, rsi; struct CmsTransactionContext *
0x1c001b408  call    ?BeginTopLevelAction@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAU_SmsTopLevelAction@@EE@Z; CmsVolume::BeginTopLevelAction(CmsTransactionContext *,_SmsTopLevelAction *,uchar,uchar)
0x1c001b40d  mov     r10, [rbp+200h+var_178]
0x1c001b414  mov     [rsp+300h+var_2A0], 1
0x1c001b419  test    byte ptr [r10+0Dh], 2
0x1c001b41e  jnz     loc_1C001B566
0x1c001b424  mov     rax, [rsp+300h+var_290]
0x1c001b429  mov     r9d, r12d; unsigned int
0x1c001b42c  mov     [rsp+300h+var_2C0], rax; struct _SmsQuickIndex *
0x1c001b431  mov     r8, rbx; struct _CmsRow *
0x1c001b434  mov     eax, [rbp+200h+arg_20]
0x1c001b43a  mov     rdx, rsi; struct CmsTransactionContext *
0x1c001b43d  mov     dword ptr [rsp+300h+var_2C8], eax; unsigned int
0x1c001b441  mov     rcx, rdi; this
0x1c001b444  lea     rax, [rbp+200h+var_70]
0x1c001b44b  mov     [rsp+300h+var_2D0], rax; struct SmsDirectorData *
0x1c001b450  lea     rax, [rbp+200h+Size]
0x1c001b457  mov     [rsp+300h+var_2D8], rax; struct CmsRowWithBuffer *
0x1c001b45c  lea     rax, [rbp+200h+var_1A0]
0x1c001b460  mov     [rsp+300h+var_2E0], rax; struct _SmsLookupStack *
0x1c001b465  call    ?InsertWithBucketSplit@CmsBPlusTable@@AEAAJPEAVCmsTransactionContext@@PEAU_CmsRow@@KPEAU_SmsLookupStack@@PEAVCmsRowWithBuffer@@PEAUSmsDirectorData@@KPEAU_SmsQuickIndex@@@Z; CmsBPlusTable::InsertWithBucketSplit(CmsTransactionContext *,_CmsRow *,ulong,_SmsLookupStack *,CmsRowWithBuffer *,SmsDirectorData *,ulong,_SmsQuickIndex *)
0x1c001b46a  mov     r15d, eax
0x1c001b46d  test    eax, eax
0x1c001b46f  js      loc_1C001B6B0
0x1c001b475  or      dword ptr [rsi+9F8h], 1
0x1c001b47c  lea     rdx, [rbp+200h+var_280]; struct CmsChecksum **
0x1c001b480  mov     cl, [rdi+98h]; unsigned __int8
0x1c001b486  mov     [rbp+200h+var_280], r13
0x1c001b48a  call    ?GetMetadataChecksumClass@CmsChecksum@@SAJEAEAPEAV1@@Z; CmsChecksum::GetMetadataChecksumClass(uchar,CmsChecksum * &)
0x1c001b48f  mov     r15d, eax
0x1c001b492  test    eax, eax
0x1c001b494  js      loc_1C001B6B0
0x1c001b49a  mov     rbx, [rbp+200h+var_280]
0x1c001b49e  mov     rdx, [rsi+20h]
0x1c001b4a2  mov     rcx, rbx
0x1c001b4a5  mov     rax, [rbx]
0x1c001b4a8  mov     rax, [rax+0A8h]
0x1c001b4af  call    cs:__guard_dispatch_icall_fptr
  ... truncated ...
```
