# CmsBPlusTable::DiscardPagesWorker(void *)

- ea: `0x140055af0`
- end: `0x140056670`
- name: `?DiscardPagesWorker@CmsBPlusTable@@SAXPEAX@Z`
- size: `2944`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14002b110`
- `0x1400340e0`
- `0x140036dd0`
- `0x140053024`
- `0x140055af0`
- `0x140056890`
- `0x140056ae8`
- `0x1400596e0`
- `0x140059920`
- `0x1400b26e0`
- `0x1400c8574`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14005643a`
- `ntoskrnl!KeSetEvent` at `0x14005643a`
- `ntoskrnl!KdDebuggerEnabled` at `0x14005645b`
- `ntoskrnl!KdDebuggerEnabled` at `0x14005658e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140056413`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140056413`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400565b2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400565b2`
- `ntoskrnl!ExAllocatePool2` at `0x140055b56`
- `ntoskrnl!ExAllocatePool2` at `0x140055b56`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140055b15`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140055b15`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f4812`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f4812`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400562d7`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400562d7`
- `ntoskrnl!MmSetAddressRangeModified` at `0x140056046`
- `ntoskrnl!MmSetAddressRangeModified` at `0x140056046`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f4851`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f4851`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400565d0`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400565d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400561dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056600`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056623`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005665f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400561dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056600`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056623`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005665f`

## string_xrefs

- `0x140055b6d`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
void __fastcall CmsBPlusTable::DiscardPagesWorker(_QWORD *a1)
{
  __int64 v1; // rsi
  _QWORD *v2; // r14
  __int64 v3; // rdi
  __int64 v4; // rdx
  __int64 Pool2; // rax
  PSLIST_ENTRY v6; // rbx
  int v7; // ecx
  _QWORD *i; // rdx
  _QWORD *v9; // rbx
  _QWORD *v10; // r8
  _QWORD *v11; // r11
  _QWORD *v12; // r10
  _QWORD *v13; // r9
  bool v14; // zf
  _QWORD *j; // rax
  PSLIST_ENTRY v16; // r14
  int v17; // r11d
  _QWORD *v18; // r10
  struct SmsPage *v19; // rsi
  _QWORD *v20; // r15
  __int64 v21; // r10
  struct _FILE_OBJECT *v22; // r11
  unsigned int v23; // r13d
  unsigned int v24; // edi
  int v25; // eax
  volatile signed __int32 *v26; // r14
  unsigned __int64 *v27; // rbx
  __int64 v28; // rdx
  unsigned __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rcx
  __int64 v32; // r12
  __int64 v33; // r9
  __int64 v34; // rdx
  int v35; // r8d
  int v36; // ecx
  unsigned int v37; // eax
  signed __int64 v38; // rdx
  signed __int64 v39; // rcx
  int v40; // eax
  unsigned int v41; // r12d
  unsigned int v42; // eax
  __int64 v43; // rcx
  __int64 v44; // rdx
  int v45; // r9d
  unsigned int v46; // r11d
  int v47; // ecx
  unsigned int v48; // eax
  struct _FILE_OBJECT *v49; // r10
  signed __int64 v50; // rdx
  unsigned int v51; // eax
  struct _FILE_OBJECT *v52; // r12
  struct _FILE_OBJECT *v53; // rcx
  PSLIST_ENTRY v54; // r12
  unsigned __int64 v55; // rcx
  unsigned int n; // r9d
  __int64 v57; // rcx
  unsigned int m; // r9d
  unsigned int v59; // r13d
  __int64 v60; // rax
  __int64 v61; // r14
  int v62; // r15d
  __int64 v63; // rcx
  __int64 v64; // rbx
  __int64 v65; // r13
  int v66; // ecx
  struct _FILE_OBJECT *v67; // r8
  unsigned int v68; // eax
  struct _FILE_OBJECT *v69; // r14
  __int64 v70; // rbx
  int v71; // ecx
  __int64 v72; // rsi
  __int64 v73; // rbx
  unsigned __int8 ii; // dl
  __int64 v75; // rax
  struct _SLIST_ENTRY *Next; // rcx
  struct _SLIST_ENTRY *v77; // rcx
  struct _SLIST_ENTRY *v78; // rcx
  struct _SLIST_ENTRY *v79; // rbx
  struct _PAGED_LOOKASIDE_LIST *v80; // rcx
  struct _SLIST_ENTRY *v81; // rdx
  _QWORD *v82; // rdi
  _QWORD *v83; // rcx
  _QWORD *v84; // rax
  __int64 v85; // rbx
  struct SmsPage *v86; // rdx
  _QWORD *v87; // r10
  _QWORD *v88; // r8
  _QWORD *v89; // rdx
  struct _NPAGED_LOOKASIDE_LIST *v90; // rcx
  struct _SLIST_ENTRY *v91; // rax
  __int64 v92; // rcx
  PSLIST_ENTRY v93; // [rsp+30h] [rbp-69h]
  PSLIST_ENTRY v94; // [rsp+38h] [rbp-61h]
  __int64 v95; // [rsp+40h] [rbp-59h]
  _QWORD *v96; // [rsp+48h] [rbp-51h]
  unsigned __int64 v97; // [rsp+50h] [rbp-49h]
  __int64 v98; // [rsp+50h] [rbp-49h]
  _QWORD *v99; // [rsp+58h] [rbp-41h]
  CmsBlockCache *v100; // [rsp+68h] [rbp-31h]
  union _LARGE_INTEGER v101; // [rsp+70h] [rbp-29h] BYREF
  struct _FILE_OBJECT *v102[2]; // [rsp+78h] [rbp-21h] BYREF
  struct _FILE_OBJECT *v103; // [rsp+88h] [rbp-11h]
  struct _FILE_OBJECT *v104[2]; // [rsp+90h] [rbp-9h] BYREF
  struct _FILE_OBJECT *v105[2]; // [rsp+A0h] [rbp+7h] BYREF
  int k; // [rsp+108h] [rbp+6Fh]
  struct SmsPage *v108; // [rsp+110h] [rbp+77h] BYREF
  int v109; // [rsp+118h] [rbp+7Fh]

  v1 = *a1;
  v2 = a1;
  v3 = qword_140262408 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  if ( *(_DWORD *)v3 < 0xD50u )
  {
    v3 = 0;
    v4 = 3424;
    goto LABEL_3;
  }
  if ( *(_BYTE *)(v3 + 8) )
  {
    v90 = (struct _NPAGED_LOOKASIDE_LIST *)(v3 + 64);
    if ( *(_BYTE *)(v3 + 9) )
      v91 = (struct _SLIST_ENTRY *)ExAllocateFromNPagedLookasideList(v90);
    else
      v91 = (struct _SLIST_ENTRY *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v90);
    v6 = v91;
    CmsTransactionContext::InitializeTransactionMemoryBuffer(&v91->Next + 1);
LABEL_150:
    if ( v6 )
      goto LABEL_151;
    goto LABEL_9;
  }
  if ( (int)*(_QWORD *)(v3 + 88) > (int)HIDWORD(*(_QWORD *)(v3 + 88)) )
  {
    v7 = _InterlockedDecrement((volatile signed __int32 *)(v3 + 88));
    if ( v7 >= *(_DWORD *)(v3 + 92) && v7 >= 0 )
    {
      v6 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v3 + 64));
      goto LABEL_150;
    }
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 88));
  }
LABEL_9:
  v4 = *(unsigned int *)(v3 + 4);
LABEL_3:
  Pool2 = ExAllocatePool2(66, v4, 1766871885);
  v6 = (PSLIST_ENTRY)Pool2;
  if ( (Pool2 & 0xF) != 0 )
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  if ( Pool2 )
  {
    CmsTransactionContext::InitializeTransactionMemoryBuffer((void *)(Pool2 + 16));
LABEL_151:
    v54 = v6 + 1;
    v6->Next = (struct _SLIST_ENTRY *)v3;
    v93 = v6 + 1;
    if ( v6 == (PSLIST_ENTRY)-16LL )
      goto LABEL_133;
    v82 = v2 + 123;
    *((_QWORD *)&v6[1].Next + 1) = v1;
    v54->Next = (struct _SLIST_ENTRY *)0x8000;
    v89 = (_QWORD *)v2[123];
    v96 = v2 + 123;
    v94 = v6 + 1;
    if ( v89 == v2 + 123 || (_QWORD *)*v89 == v82 )
    {
      v93 = v6 + 1;
      v16 = v6 + 1;
    }
    else
    {
      v2[124] = v89;
      v87 = v89;
      v88 = (_QWORD *)*v89;
      if ( (_QWORD *)*v89 == v82 )
      {
        v93 = v6 + 1;
      }
      else
      {
        do
        {
          if ( (__int64)(*(v89 - 9) - *(v88 - 9)) > 0 )
          {
            v87[1] = v88;
            v87 = v88;
            *v89 = 0;
          }
          v89 = v88;
          v88 = (_QWORD *)*v88;
        }
        while ( v88 != v82 );
      }
      if ( (_QWORD *)v2[124] == v87 )
      {
        v16 = v6 + 1;
        v82[1] = v89;
      }
      else
      {
        *v89 = 0;
        v87[1] = 0;
        for ( i = (_QWORD *)v2[124]; i[1]; i = (_QWORD *)v2[124] )
        {
          v9 = v2 + 123;
          do
          {
            v10 = (_QWORD *)i[1];
            v11 = (_QWORD *)v10[1];
            if ( (__int64)(*(i - 9) - *(v10 - 9)) <= 0 )
            {
              v12 = i;
              i = (_QWORD *)*i;
            }
            else
            {
              v12 = (_QWORD *)i[1];
              v10 = (_QWORD *)*v10;
            }
            v13 = v12;
            v14 = i == 0;
            if ( i )
            {
              do
              {
                if ( !v10 )
                  break;
                if ( (__int64)(*(i - 9) - *(v10 - 9)) > 0 )
                {
                  *v13 = v10;
                  v13 = v10;
                  v10 = (_QWORD *)*v10;
                }
                else
                {
                  *v13 = i;
                  v13 = i;
                  i = (_QWORD *)*i;
                }
              }
              while ( i );
              v14 = i == 0;
            }
            if ( v14 )
              i = v10;
            *v13 = i;
            v9[1] = v12;
            v12[1] = v11;
            if ( !v11 )
              break;
            v9 = v12;
            i = v11;
          }
          while ( v11[1] );
        }
        *v82 = i;
        for ( j = v2 + 123; i; i = (_QWORD *)*i )
        {
          i[1] = j;
          j = i;
        }
        v16 = v94;
        *j = v82;
        v82[1] = j;
      }
    }
    v54->Next = (struct _SLIST_ENTRY *)((unsigned __int64)v54->Next | 0x800);
    v17 = -1;
    for ( k = -1; ; v17 = k )
    {
      v18 = (_QWORD *)*v82;
      v99 = (_QWORD *)*v82;
      if ( (_QWORD *)*v82 == v82 || !v17 )
        break;
      v19 = (struct SmsPage *)(v18 - 9);
      if ( (v18[60] & 0x10) == 0 )
        goto LABEL_120;
      v20 = (_QWORD *)*v18;
      if ( (_QWORD *)*v18 == v82 )
        goto LABEL_120;
      v21 = *((_QWORD *)&v54->Next + 1);
      v22 = (struct _FILE_OBJECT *)(&v54->Next + 1);
      v23 = *((_DWORD *)v19 + 94);
      v24 = 1;
      v25 = k;
      v95 = v21;
      for ( v102[0] = (struct _FILE_OBJECT *)(&v54->Next + 1); ; v22 = v102[0] )
      {
        v109 = v25;
        if ( !v25 )
          goto LABEL_85;
        v26 = (volatile signed __int32 *)(v20 + 60);
        if ( (v20[60] & 0x30) != 0x10 )
          goto LABEL_85;
        if ( *((_QWORD *)v19 + 14) )
          goto LABEL_85;
        v27 = v20 - 9;
        if ( v20[5] )
          goto LABEL_85;
        v28 = *((_QWORD *)v19 + 13);
        if ( !v28 )
          goto LABEL_85;
        v29 = v27[13];
        if ( !v29 )
          goto LABEL_85;
        if ( *((_QWORD *)v19 + 1) )
        {
          v57 = *(_QWORD *)v19;
          for ( m = 1; ; ++m )
          {
            ++v57;
            if ( m >= 4 )
              break;
            if ( *((_QWORD *)v19 + m) != v57 )
              goto LABEL_85;
          }
        }
        if ( v27[1] )
        {
          v55 = *v27;
          for ( n = 1; ; ++n )
          {
            ++v55;
            if ( n >= 4 )
              break;
            if ( v27[n] != v55 )
              goto LABEL_85;
          }
        }
        if ( ((*(_BYTE *)(*(_QWORD *)(*((_QWORD *)v19 + 12) + 32LL) + 16LL) & 4) != 0) != ((*(_BYTE *)(*(_QWORD *)(v27[12] + 32) + 16LL)
                                                                                          & 4) != 0)
          || v28 + (v23 << *(_DWORD *)(v21 + 64)) != v29
          || ((v29 ^ v28) & 0xFFFFFFFFFFFC0000uLL) != 0 )
        {
          goto LABEL_85;
        }
        v14 = (*(_BYTE *)(*(_QWORD *)(*((_QWORD *)v19 + 12) + 32LL) + 16LL) & 4) == 0;
        v30 = *(_QWORD *)&v22->Type;
        v31 = 400;
        v20 = (_QWORD *)*v20;
        v32 = *(_QWORD *)v19;
        LODWORD(v108) = *((_DWORD *)v27 + 94);
        v97 = *v27;
        if ( v14 )
          v31 = 296;
        v33 = v31 + v30;
        v100 = (CmsBlockCache *)v33;
        *(_OWORD *)v104 = 0;
        v14 = *(_BYTE *)(v33 + 48) == 0;
        *(_OWORD *)v105 = 0;
        if ( !v14 )
        {
          v34 = *(unsigned int *)(*(_QWORD *)(v33 + 56) + 84LL);
          v32 = -v34 & ((unsigned __int64)v32 >> 1) | (unsigned int)v32 & ((_DWORD)v34 - 1);
        }
        v35 = CmsBlockCache::PrepareInstanceForCaching((CmsBlockCache *)v33, v32, &v104[1]);
        if ( v35 < 0 )
        {
          v41 = 0;
          v103 = v104[0];
        }
        else
        {
          v36 = *((_DWORD *)v100 + 6);
          v37 = v32 >> v36;
          v103 = (struct _FILE_OBJECT *)(v32 - ((unsigned __int64)v37 << v36));
          v38 = ((unsigned __int64)(v37 + 1) << v36) - 1;
          v39 = v32 + v23;
          v40 = v38 - v32;
          v41 = v23;
          v42 = v40 + 1;
          if ( v39 > v38 )
            v41 = v42;
        }
        if ( v41 < v23 || v35 < 0 )
        {
          v53 = v104[1];
          if ( !v104[1] )
            goto LABEL_70;
          goto LABEL_69;
        }
        if ( *((_BYTE *)v100 + 48) )
        {
          v43 = *(unsigned int *)(*((_QWORD *)v100 + 7) + 84LL);
          v44 = -v43 & (v97 >> 1) | (unsigned int)v97 & ((_DWORD)v43 - 1);
        }
        else
        {
          v44 = v97;
        }
        v98 = v44;
        v45 = CmsBlockCache::PrepareInstanceForCaching(v100, v44, &v105[1]);
        if ( v45 < 0 )
        {
          v49 = v105[0];
          v46 = (unsigned int)v108;
        }
        else
        {
          v46 = (unsigned int)v108;
          v41 = (unsigned int)v108;
          v47 = *((_DWORD *)v100 + 6);
          v48 = v98 >> v47;
          v49 = (struct _FILE_OBJECT *)(v98 - ((unsigned __int64)v48 << v47));
          v50 = ((unsigned __int64)(v48 + 1) << v47) - 1;
          v51 = ((v48 + 1) << v47) - v98;
          if ( v98 + (unsigned int)v108 > v50 )
            v41 = v51;
        }
        if ( v41 < v46 || v45 < 0 )
          break;
        v52 = v104[1];
        if ( v105[1] != v104[1] || (struct _FILE_OBJECT *)((char *)v103 + v23) != v49 )
        {
          if ( v105[1] )
            MsKmeDereferenceObject(v105[1]);
          if ( !v52 )
            goto LABEL_70;
          v53 = v52;
LABEL_69:
          MsKmeDereferenceObject(v53);
LABEL_70:
          v54 = v93;
          v21 = v95;
          goto LABEL_85;
        }
        if ( v105[1] )
          MsKmeDereferenceObject(v105[1]);
        if ( v52 )
          MsKmeDereferenceObject(v52);
        v23 += *((_DWORD *)v27 + 94);
        ++v24;
        _InterlockedOr(v26, 0x20u);
        v54 = v93;
        v21 = v95;
        if ( v20 == v96 )
          goto LABEL_85;
        v25 = v109 - 1;
      }
      if ( v105[1] )
        MsKmeDereferenceObject(v105[1]);
      if ( !v104[1] )
        goto LABEL_70;
      MsKmeDereferenceObject(v104[1]);
      v21 = v95;
      v54 = v93;
LABEL_85:
      if ( v24 <= 1 )
        goto LABEL_118;
      v59 = v23 << *(_DWORD *)(v21 + 64);
      _InterlockedOr((volatile signed __int32 *)v19 + 138, 0x20u);
      v101.QuadPart = 0;
      v60 = *((_QWORD *)v19 + 12);
      v61 = v21 + 400;
      *(_OWORD *)v102 = 0;
      if ( (*(_BYTE *)(*(_QWORD *)(v60 + 32) + 16LL) & 4) == 0 )
        v61 = v21 + 296;
      v62 = *(_DWORD *)(v21 + 64);
      MmSetAddressRangeModified(*((PVOID *)v19 + 13), v59);
      if ( *(_BYTE *)(v61 + 48) )
      {
        v63 = *(unsigned int *)(*(_QWORD *)(v61 + 56) + 84LL);
        v64 = -v63 & (*(_QWORD *)v19 >> 1) | (unsigned int)*(_QWORD *)v19 & ((_DWORD)v63 - 1);
      }
      else
      {
        v64 = *(_QWORD *)v19;
      }
      if ( (int)CmsBlockCache::PrepareInstanceForCaching((CmsBlockCache *)v61, v64, &v102[1]) < 0 )
        goto LABEL_116;
      v65 = v59 >> v62;
      v66 = *(_DWORD *)(v61 + 24);
      v67 = (struct _FILE_OBJECT *)(v64 - ((unsigned __int64)(unsigned int)(v64 >> v66) << v66));
      v102[0] = v67;
      if ( v64 + v65 > (__int64)(((unsigned __int64)((unsigned int)(v64 >> v66) + 1) << v66) - 1) )
      {
        v68 = (((unsigned int)(v64 >> v66) + 1) << v66) - v64;
        if ( v68 >= (unsigned int)v65 )
          goto LABEL_93;
LABEL_116:
        if ( v102[1] )
          MsKmeDereferenceObject(v102[1]);
LABEL_118:
        v16 = v94;
        goto LABEL_119;
      }
      v68 = v65;
LABEL_93:
      v69 = v102[1];
      v70 = (__int64)v19;
      v71 = *(_DWORD *)(v95 + 64);
      v101.QuadPart = (_QWORD)v67 << v71;
      MsKmeFlushCache(v102[1], &v101, v68 << v71, 0);
      do
      {
        _InterlockedAnd((volatile signed __int32 *)(v70 + 552), 0xFFFFFFEF);
        v70 = *(_QWORD *)(v70 + 72) - 72LL;
        --v24;
      }
      while ( v24 );
      if ( v69 )
        MsKmeDereferenceObject(v69);
      v16 = v94;
      v93 = v54;
LABEL_119:
      v18 = v99;
      v82 = v96;
      v17 = k;
LABEL_120:
      v83 = (_QWORD *)*v18;
      if ( *(_QWORD **)(*v18 + 8LL) != v18 || (v84 = (_QWORD *)v18[1], (_QWORD *)*v84 != v18) )
        __fastfail(3u);
      *v84 = v83;
      v83[1] = v84;
      v18[1] = 0;
      *v18 = 0;
      v85 = *((_QWORD *)v19 + 12);
      v108 = v19;
      k = v17 - 1;
      if ( (*((_DWORD *)v19 + 138) & 0x40) != 0 )
      {
        CmsVolumeContainer::SetContainerStationaryVolatile(
          *(CmsVolumeContainer **)(*((_QWORD *)&v54->Next + 1) + 3336LL),
          (struct CmsTransactionContext *)v54,
          v19,
          0,
          0);
        _InterlockedAnd((volatile signed __int32 *)v108 + 138, 0xFFFFFFBF);
        v19 = v108;
      }
      _InterlockedExchange64((volatile __int64 *)v19 + 42, 0);
      v86 = v108;
      if ( *((_QWORD *)v108 + 43) )
      {
        _InterlockedExchange64((volatile __int64 *)v108 + 43, 1);
        v86 = v108;
      }
      _InterlockedAnd((volatile signed __int32 *)v86 + 138, 0xFFFF5FF7);
      CmsCompositeBase::Unpin(*(CmsCompositeBase **)(v85 + 112), (struct CmsTransactionCore *)v54, &v108, 0xAu);
    }
    CmsTransactionContext::Commit((CmsTransactionContext *)v54, 0, 0, 0);
    v72 = *((_QWORD *)&v54->Next + 1);
    v73 = (__int64)v54->Next & 0x10000000;
    if ( (*((_QWORD *)&v54[18].Next + 1) || LODWORD(v54[22].Next) || HIDWORD(v54[22].Next)) && (_BYTE)KdDebuggerEnabled )
      __debugbreak();
    for ( ii = 0; ii < LOBYTE(v54[8].Next); *((_DWORD *)&v16[71].Next + 22 * v75 + 1) &= ~1u )
      v75 = ii++;
    Next = v54[212].Next;
    LOBYTE(v54[8].Next) = 0;
    if ( Next )
    {
      ExFreePoolWithTag(Next, 0);
      v54[212].Next = 0;
      *((_DWORD *)&v54[212].Next + 2) = 0;
    }
    if ( (*(_BYTE *)(&v54[208].Next + 1) & 1) != 0 )
    {
      v77 = v54[208].Next;
      if ( v77 )
        ExFreePoolWithTag(v77, 0);
    }
    *((_DWORD *)&v54[208].Next + 3) = 32;
    v54[208].Next = v54 + 209;
    HIDWORD(v54[207].Next) = HIDWORD(v105[0]);
    v54[206] = 0;
    LODWORD(v54[207].Next) = 0;
    *((_QWORD *)&v54[207].Next + 1) = 0;
    *((_BYTE *)&v54[208].Next + 8) = 0;
    CmsRowWithBuffer::Reset((CmsRowWithBuffer *)&v54[201]);
    CmsRowWithBuffer::Reset((CmsRowWithBuffer *)&v54[196]);
    CmsRowWithBuffer::Reset((CmsRowWithBuffer *)&v54[191]);
    CmsRowWithBuffer::Reset((CmsRowWithBuffer *)&v54[186]);
    CmsRowWithBuffer::Reset((CmsRowWithBuffer *)&v54[181]);
    CmsRowWithBuffer::Reset((CmsRowWithBuffer *)&v54[176]);
    if ( v54[64].Next && (_BYTE)KdDebuggerEnabled )
      __debugbreak();
    v78 = v54[54].Next;
    if ( v78 )
    {
      ExFreePoolWithTag(v78, 0);
      v54[54].Next = 0;
    }
    if ( v73 )
    {
      CmsReservedPool::FreeToPool((CmsReservedPool *)(v72 + 160), v54);
      v2 = a1;
      goto LABEL_133;
    }
    v79 = v54[-1].Next;
    if ( v79 )
    {
      if ( *((_BYTE *)&v79->Next + 8) )
      {
        v80 = (struct _PAGED_LOOKASIDE_LIST *)&v79[4];
        v81 = v54 - 1;
        if ( !*((_BYTE *)&v79->Next + 9) )
        {
          ExFreeToPagedLookasideList(v80, v81);
          v2 = a1;
          goto LABEL_133;
        }
        ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v80, v81);
LABEL_132:
        v2 = a1;
        goto LABEL_133;
      }
      v92 = *((_QWORD *)&v79[5].Next + 1);
      if ( (int)v92 < SLODWORD(v79[5].Next) || SHIDWORD(v92) >= (int)v92 )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)&v79[4], v54 - 1);
        _InterlockedIncrement((volatile signed __int32 *)&v79[5].Next + 2);
        goto LABEL_132;
      }
    }
    ExFreePoolWithTag(&v54[-1], 0);
    goto LABEL_132;
  }
LABEL_133:
  KeSetEvent((PRKEVENT)v2 + 40, 0, 0);
}

```

## disassembly

```asm
0x140055af0  mov     [rsp-8+arg_0], rcx
0x140055af5  push    rbp
0x140055af6  push    rbx
0x140055af7  push    rsi
0x140055af8  push    rdi
0x140055af9  push    r12
0x140055afb  push    r13
0x140055afd  push    r14
0x140055aff  push    r15
0x140055b01  lea     rbp, [rsp-1Fh]
0x140055b06  sub     rsp, 0B8h
0x140055b0d  mov     rsi, [rcx]
0x140055b10  mov     r14, rcx
0x140055b13  xor     ecx, ecx; ProcNumber
0x140055b15  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140055b1c  nop     dword ptr [rax+rax+00h]
0x140055b21  xor     edx, edx
0x140055b23  xor     r15d, r15d
0x140055b26  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140055b2c  lea     rdi, [rdx+rdx*2]
0x140055b30  shl     rdi, 6
0x140055b34  add     rdi, cs:qword_140262408
0x140055b3b  cmp     dword ptr [rdi], 0D50h
0x140055b41  jnb     short loc_140055B7A
0x140055b43  mov     edi, r15d
0x140055b46  mov     edx, 0D60h
0x140055b4b  mov     ecx, 42h ; 'B'
0x140055b50  mov     r8d, 6950534Dh
0x140055b56  call    cs:__imp_ExAllocatePool2
0x140055b5d  nop     dword ptr [rax+rax+00h]
0x140055b62  mov     rbx, rax
0x140055b65  test    al, 0Fh
0x140055b67  jz      loc_1401F4830
0x140055b6d  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x140055b74  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x140055b7a  cmp     [rdi+8], r15b
0x140055b7e  jnz     loc_1400565A4
0x140055b84  mov     rcx, [rdi+58h]
0x140055b88  mov     rax, rcx
0x140055b8b  shr     rax, 20h
0x140055b8f  cmp     ecx, eax
0x140055b91  jle     short loc_140055BB2
0x140055b93  nop
0x140055b94  mov     ecx, 0FFFFFFFFh
0x140055b99  lock xadd [rdi+58h], ecx
0x140055b9e  nop
0x140055b9f  dec     ecx
0x140055ba1  mov     eax, [rdi+5Ch]
0x140055ba4  cmp     ecx, eax
0x140055ba6  jge     loc_1400565C4
0x140055bac  nop
0x140055bad  lock inc dword ptr [rdi+58h]
0x140055bb1  nop
0x140055bb2  mov     edx, [rdi+4]
0x140055bb5  jmp     short loc_140055B4B
0x140055bb7  mov     [rdx], r15
0x140055bba  mov     [r10+8], r15
0x140055bbe  mov     rdx, [rdi+8]
0x140055bc2  cmp     [rdx+8], r15
0x140055bc6  jz      short loc_140055C44
0x140055bc8  mov     rbx, rdi
0x140055bcb  nop     dword ptr [rax+rax+00h]
0x140055bd0  mov     r8, [rdx+8]
0x140055bd4  mov     rcx, [rdx-48h]
0x140055bd8  sub     rcx, [r8-48h]
0x140055bdc  mov     r11, [r8+8]
0x140055be0  test    rcx, rcx
0x140055be3  jle     loc_140055C77
0x140055be9  mov     r10, r8
0x140055bec  mov     r8, [r8]
0x140055bef  mov     r9, r10
0x140055bf2  test    rdx, rdx
0x140055bf5  jz      short loc_140055C1A
0x140055bf7  test    r8, r8
0x140055bfa  jz      short loc_140055C17
0x140055bfc  mov     rcx, [rdx-48h]
0x140055c00  sub     rcx, [r8-48h]
0x140055c04  test    rcx, rcx
0x140055c07  jg      short loc_140055C6C
0x140055c09  mov     [r9], rdx
0x140055c0c  mov     r9, rdx
0x140055c0f  mov     rdx, [rdx]
0x140055c12  test    rdx, rdx
0x140055c15  jnz     short loc_140055BF7
0x140055c17  test    rdx, rdx
0x140055c1a  cmovz   rdx, r8
0x140055c1e  mov     [r9], rdx
0x140055c21  mov     [rbx+8], r10
0x140055c25  mov     [r10+8], r11
0x140055c29  test    r11, r11
0x140055c2c  jz      short loc_140055C3A
0x140055c2e  mov     rbx, r10
0x140055c31  mov     rdx, r11
0x140055c34  cmp     [r11+8], r15
0x140055c38  jnz     short loc_140055BD0
0x140055c3a  mov     rdx, [rdi+8]
0x140055c3e  cmp     [rdx+8], r15
0x140055c42  jnz     short loc_140055BC8
0x140055c44  mov     [rdi], rdx
0x140055c47  mov     rax, rdi
0x140055c4a  test    rdx, rdx
0x140055c4d  jz      short loc_140055C5F
0x140055c4f  nop
0x140055c50  mov     [rdx+8], rax
0x140055c54  mov     rax, rdx
0x140055c57  mov     rdx, [rdx]
0x140055c5a  test    rdx, rdx
0x140055c5d  jnz     short loc_140055C50
0x140055c5f  mov     r14, [rbp+57h+var_B8]
0x140055c63  mov     [rax], rdi
0x140055c66  mov     [rdi+8], rax
0x140055c6a  jmp     short loc_140055C89
0x140055c6c  mov     [r9], r8
0x140055c6f  mov     r9, r8
0x140055c72  mov     r8, [r8]
0x140055c75  jmp     short loc_140055C12
0x140055c77  mov     r10, rdx
0x140055c7a  mov     rdx, [rdx]
0x140055c7d  jmp     loc_140055BEF
0x140055c82  mov     [rbp+57h+var_C0], r12
0x140055c86  mov     r14, r12
0x140055c89  or      qword ptr [r12], 800h
0x140055c91  mov     r11d, 0FFFFFFFFh
0x140055c97  mov     [rbp+57h+arg_8], r11d
0x140055c9b  nop     dword ptr [rax+rax+00h]
0x140055ca0  mov     r10, [rdi]
0x140055ca3  mov     [rbp+57h+var_98], r10
0x140055ca7  cmp     r10, rdi
0x140055caa  jz      loc_140056135
0x140055cb0  test    r11d, r11d
0x140055cb3  jz      loc_140056135
0x140055cb9  lea     rsi, [r10-48h]
0x140055cbd  mov     eax, [rsi+228h]
0x140055cc3  test    al, 10h
0x140055cc5  jz      loc_14005630D
0x140055ccb  mov     r15, [r10]
0x140055cce  cmp     r15, rdi
0x140055cd1  jz      loc_14005630A
0x140055cd7  mov     r10, [r12+8]
0x140055cdc  lea     r11, [r12+8]
0x140055ce1  mov     r13d, [rsi+178h]
0x140055ce8  mov     edi, 1
0x140055ced  mov     eax, [rbp+57h+arg_8]
0x140055cf0  mov     [rbp+57h+var_B0], r10
0x140055cf4  mov     [rbp+57h+var_78], r11
0x140055cf8  mov     [rbp+57h+arg_18], eax
0x140055cfb  test    eax, eax
0x140055cfd  jz      loc_140055FF8
0x140055d03  lea     r14, [r15+1E0h]
0x140055d0a  mov     eax, [r14]
0x140055d0d  and     al, 30h
0x140055d0f  cmp     al, 10h
0x140055d11  jnz     loc_140055FF8
0x140055d17  cmp     qword ptr [rsi+70h], 0
0x140055d1c  jnz     loc_140055FF8
0x140055d22  cmp     qword ptr [r15+28h], 0
0x140055d27  lea     rbx, [r15-48h]
0x140055d2b  jnz     loc_140055FF8
0x140055d31  mov     rdx, [rsi+68h]
0x140055d35  test    rdx, rdx
0x140055d38  jz      loc_140055FF8
0x140055d3e  mov     r8, [rbx+68h]
0x140055d42  test    r8, r8
0x140055d45  jz      loc_140055FF8
0x140055d4b  cmp     qword ptr [rsi+8], 0
0x140055d50  jnz     loc_140055F7F
0x140055d56  cmp     qword ptr [rbx+8], 0
0x140055d5b  jnz     loc_140055F5B
0x140055d61  mov     rax, [rsi+60h]
0x140055d65  mov     rcx, [rax+20h]
0x140055d69  mov     rax, [rbx+60h]
0x140055d6d  movzx   r9d, byte ptr [rcx+10h]
0x140055d72  mov     rcx, [rax+20h]
0x140055d76  shr     r9b, 2
0x140055d7a  and     r9b, 1
0x140055d7e  movzx   eax, byte ptr [rcx+10h]
0x140055d82  shr     al, 2
0x140055d85  and     al, 1
0x140055d87  cmp     r9b, al
0x140055d8a  jnz     loc_140055FF8
0x140055d90  mov     ecx, [r10+40h]
0x140055d94  mov     eax, r13d
0x140055d97  shl     eax, cl
0x140055d99  mov     ecx, eax
0x140055d9b  add     rcx, rdx
0x140055d9e  cmp     rcx, r8
0x140055da1  jnz     loc_140055FF8
0x140055da7  xor     rdx, r8
0x140055daa  test    rdx, 0FFFFFFFFFFFC0000h
0x140055db1  jnz     loc_140055FF8
0x140055db7  mov     eax, [rbx+178h]
0x140055dbd  test    r9b, r9b
0x140055dc0  mov     r9, [r11]
0x140055dc3  mov     ecx, 190h
0x140055dc8  mov     r15, [r15]
0x140055dcb  xorps   xmm0, xmm0
0x140055dce  mov     r12, [rsi]
0x140055dd1  xorps   xmm1, xmm1
0x140055dd4  mov     dword ptr [rbp+57h+arg_10], eax
0x140055dd7  mov     rax, [rbx]
0x140055dda  mov     [rbp+57h+var_A0], rax
0x140055dde  mov     eax, 128h
0x140055de3  cmovz   ecx, eax
0x140055de6  mov     [rbp+57h+var_90], 0
0x140055ded  add     r9, rcx
0x140055df0  mov     [rbp+57h+var_88], r9
0x140055df4  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x140055df9  cmp     byte ptr [r9+30h], 0
0x140055dfe  movdqu  xmmword ptr [rbp+57h+var_50], xmm1
0x140055e03  jz      short loc_140055E27
0x140055e05  mov     rax, [r9+38h]
0x140055e09  mov     edx, [rax+54h]
0x140055e0c  mov     eax, r12d
0x140055e0f  shr     r12, 1
0x140055e12  lea     ecx, [rdx-1]
0x140055e15  neg     rdx
0x140055e18  and     rcx, rax
0x140055e1b  mov     rax, r12
0x140055e1e  and     rax, rdx
0x140055e21  mov     r12, rcx
0x140055e24  or      r12, rax
0x140055e27  lea     r8, [rbp+57h+var_60+8]; struct _FILE_OBJECT **
0x140055e2b  mov     rdx, r12; __int64
0x140055e2e  mov     rcx, r9; this
0x140055e31  call    ?PrepareInstanceForCaching@CmsBlockCache@@AEAAJ_JPEAPEAU_FILE_OBJECT@@@Z; CmsBlockCache::PrepareInstanceForCaching(__int64,_FILE_OBJECT * *)
0x140055e36  mov     r9, [rbp+57h+var_88]
0x140055e3a  mov     r8d, eax
0x140055e3d  test    eax, eax
0x140055e3f  js      loc_1400563F5
0x140055e45  mov     ecx, [r9+18h]
0x140055e49  mov     rdx, r12
0x140055e4c  sar     rdx, cl
0x140055e4f  mov     r10, r12
0x140055e52  mov     eax, edx
0x140055e54  mov     edx, edx
0x140055e56  shl     rdx, cl
0x140055e59  sub     r10, rdx
0x140055e5c  lea     edx, [rax+1]
0x140055e5f  mov     [rbp+57h+var_68], r10
0x140055e63  shl     rdx, cl
0x140055e66  dec     rdx
0x140055e69  mov     ecx, r13d
0x140055e6c  add     rcx, r12
0x140055e6f  mov     eax, edx
0x140055e71  sub     eax, r12d
0x140055e74  mov     r12d, r13d
0x140055e77  inc     eax
0x140055e79  cmp     rcx, rdx
0x140055e7c  cmovg   r12d, eax
0x140055e80  cmp     r12d, r13d
0x140055e83  jb      loc_1400563E3
0x140055e89  test    r8d, r8d
0x140055e8c  js      loc_1400563E3
0x140055e92  cmp     byte ptr [r9+30h], 0
0x140055e97  jz      loc_1400564A0
0x140055e9d  mov     rax, [r9+38h]
0x140055ea1  mov     r8, [rbp+57h+var_A0]
0x140055ea5  mov     ecx, [rax+54h]
0x140055ea8  mov     eax, r8d
0x140055eab  shr     r8, 1
0x140055eae  lea     edx, [rcx-1]
0x140055eb1  neg     rcx
0x140055eb4  and     r8, rcx
0x140055eb7  and     rdx, rax
0x140055eba  or      rdx, r8; __int64
0x140055ebd  lea     r8, [rbp+57h+var_50+8]; struct _FILE_OBJECT **
0x140055ec1  mov     [rbp+57h+var_A0], rdx
0x140055ec5  mov     rcx, r9; this
0x140055ec8  call    ?PrepareInstanceForCaching@CmsBlockCache@@AEAAJ_JPEAPEAU_FILE_OBJECT@@@Z; CmsBlockCache::PrepareInstanceForCaching(__int64,_FILE_OBJECT * *)
0x140055ecd  mov     r9d, eax
0x140055ed0  test    eax, eax
0x140055ed2  js      loc_140056406
0x140055ed8  mov     r8, [rbp+57h+var_A0]
0x140055edc  mov     rcx, [rbp+57h+var_88]
0x140055ee0  mov     rdx, r8
0x140055ee3  mov     r11d, dword ptr [rbp+57h+arg_10]
0x140055ee7  mov     r10, r8
0x140055eea  mov     r12d, r11d
0x140055eed  mov     ecx, [rcx+18h]
0x140055ef0  sar     rdx, cl
0x140055ef3  mov     eax, edx
0x140055ef5  mov     edx, edx
0x140055ef7  shl     rdx, cl
0x140055efa  sub     r10, rdx
0x140055efd  lea     edx, [rax+1]
0x140055f00  shl     rdx, cl
0x140055f03  lea     rcx, [r8+r11]
0x140055f07  dec     rdx
0x140055f0a  mov     eax, edx
0x140055f0c  sub     eax, r8d
0x140055f0f  inc     eax
0x140055f11  cmp     rcx, rdx
0x140055f14  cmovg   r12d, eax
0x140055f18  cmp     r12d, r11d
0x140055f1b  jb      loc_140056561
0x140055f21  test    r9d, r9d
0x140055f24  js      loc_140056561
0x140055f2a  mov     rcx, [rbp+57h+var_50+8]; struct _FILE_OBJECT *
0x140055f2e  mov     r12, [rbp+57h+var_60+8]
0x140055f32  cmp     rcx, r12
  ... truncated ...
```
