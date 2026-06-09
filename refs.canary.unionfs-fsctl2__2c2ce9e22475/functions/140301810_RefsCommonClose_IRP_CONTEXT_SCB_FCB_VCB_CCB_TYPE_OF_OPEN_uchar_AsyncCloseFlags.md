# RefsCommonClose(_IRP_CONTEXT *,_SCB *,_FCB *,_VCB *,_CCB * *,_TYPE_OF_OPEN,uchar,AsyncCloseFlags)

- ea: `0x140301810`
- end: `0x1403021d8`
- name: `?RefsCommonClose@@YAJPEAU_IRP_CONTEXT@@PEAU_SCB@@PEAU_FCB@@PEAU_VCB@@PEAPEAU_CCB@@W4_TYPE_OF_OPEN@@EW4AsyncCloseFlags@@@Z`
- size: `2504`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1403012f0`
- `0x1403391e0`

## callees

- `0x14002b110`
- `0x140038f80`
- `0x140041b40`
- `0x140052010`
- `0x140077f00`
- `0x14007b700`
- `0x14007e870`
- `0x140081670`
- `0x14008c400`
- `0x14008dbd0`
- `0x14008e3c0`
- `0x14008faf0`
- `0x1400b2d58`
- `0x1400c8644`
- `0x1400ca788`
- `0x140286ebc`
- `0x140290854`
- `0x1402fec90`
- `0x1403000b0`
- `0x1403008f0`
- `0x140301810`
- `0x1403021e0`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140301d61`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140301d61`
- `ntoskrnl!MmCanFileBeTruncated` at `0x140301c67`
- `ntoskrnl!MmCanFileBeTruncated` at `0x140301c67`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140301a36`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140301a36`
- `ntoskrnl!MmBadPointer` at `0x140301a80`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140301bcf`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140301c91`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140301bcf`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140301c91`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140301a46`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140301a46`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14033ee04`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14033ee50`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14033ee04`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14033ee50`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140301a9a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140301a9a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140301aa6`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140301aa6`
- `ntoskrnl!ExReleaseFastResource` at `0x140301f54`
- `ntoskrnl!ExReleaseFastResource` at `0x140301f54`
- `ntoskrnl!ExFreePoolWithTag` at `0x140301b93`
- `ntoskrnl!ExFreePoolWithTag` at `0x140301f76`
- `ntoskrnl!ExFreePoolWithTag` at `0x140301b93`
- `ntoskrnl!ExFreePoolWithTag` at `0x140301f76`

## pseudocode

```c
__int64 __fastcall RefsCommonClose(
        __int64 a1,
        struct _SCB *a2,
        __int64 a3,
        struct _VCB *a4,
        struct _CCB **a5,
        char a6,
        char a7,
        char a8)
{
  struct _VCB *v8; // r10
  char v11; // di
  unsigned int v12; // ebx
  unsigned int v13; // r13d
  _QWORD *v14; // r12
  __int64 v15; // rdx
  __int64 v16; // r8
  struct _SCB *v17; // r8
  struct _VCB *v18; // r9
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  struct _CCB *v22; // rbx
  __int64 v23; // rdi
  __int64 v24; // rax
  _QWORD *v25; // rcx
  union _LARGE_INTEGER v26; // rbx
  void *v27; // rcx
  bool v28; // zf
  __int64 *i; // rbx
  __int16 v30; // ax
  SECTION_OBJECT_POINTERS *v31; // rcx
  bool v32; // r8
  char v33; // dl
  _QWORD *j; // rax
  __int64 v35; // r8
  int v36; // eax
  __int64 v38; // rax
  __int64 v39; // rax
  unsigned int v40; // r9d
  int v41; // [rsp+20h] [rbp-98h]
  char v42; // [rsp+40h] [rbp-78h]
  bool v43; // [rsp+41h] [rbp-77h]
  struct _LCB *QuadPart; // [rsp+50h] [rbp-68h] BYREF
  int v45; // [rsp+58h] [rbp-60h]
  union _LARGE_INTEGER NewFileSize; // [rsp+60h] [rbp-58h] BYREF
  struct IndexSCB *v47[10]; // [rsp+68h] [rbp-50h] BYREF
  struct _SCB *v48; // [rsp+C8h] [rbp+10h]

  v48 = a2;
  v8 = a4;
  v42 = 0;
  v11 = 0;
  v12 = 1;
  v45 = 1;
  v13 = 0;
  v14 = (_QWORD *)(a1 + 8);
  v47[1] = (struct IndexSCB *)(a1 + 8);
  if ( (*(_BYTE *)(a1 + 8) & 1) == 0 )
  {
    v12 = 3;
    v45 = 3;
  }
  while ( 1 )
  {
    while ( 1 )
    {
      if ( (*v14 & 0x800000LL) == 0 )
      {
        if ( (*((_DWORD *)v8 + 6) & 0x800) == 0 && (*v14 & 0x100LL) == 0 )
        {
          v15 = *(_QWORD *)(a1 + 104);
          if ( (*(_QWORD *)(v15 + 8) & 0x20000000000LL) == 0 )
          {
            MsInitializeFastResourceOwnerEntry(v15 + 160);
            *(_QWORD *)(v15 + 8) |= v16;
          }
          if ( !(unsigned __int8)MsAcquireFastResourceSharedInternal<0>(
                                   (char *)v8 + 1312,
                                   v15 + 160,
                                   *(_BYTE *)(a1 + 8) & 1) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_4391b888391630af3073df0a7ea07d8a_Traceguids, 259);
            }
            if ( !(_BYTE)RefsStatusDebugEnabled )
              return 259;
            v40 = 1154;
LABEL_146:
            RefsStatusDebug(259, 0, "Close.c", v40);
            return 259;
          }
        }
        else
        {
          if ( !RefsAcquireExclusiveVcb((struct _IRP_CONTEXT *)a1, v8, 0) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_4391b888391630af3073df0a7ea07d8a_Traceguids, 259);
            }
            if ( !(_BYTE)RefsStatusDebugEnabled )
              return 259;
            v40 = 1147;
            goto LABEL_146;
          }
          v42 = 1;
        }
        a2 = v48;
      }
      if ( (*(_DWORD *)(a1 + 4) & 0x10000) == 0 && !*((_DWORD *)a2 + 40) )
      {
        if ( (*((_DWORD *)a2 + 38) & 0x100) != 0
          && (v38 = *((_QWORD *)a2 + 31), !*(_QWORD *)(v38 + 8))
          && !*(_QWORD *)(v38 + 24)
          || !*(_DWORD *)(a3 + 16) && *(_QWORD *)(a3 + 232) )
        {
          *(_DWORD *)(a1 + 4) |= 0x10000u;
        }
      }
      if ( !(unsigned __int8)RefsAcquireFcbWithPaging(a1, a3, 0, v12) )
      {
        if ( (*(_DWORD *)v14 & 0x800000) == 0 )
          RefsReleaseVcb((struct _IRP_CONTEXT *)a1, a4);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_4391b888391630af3073df0a7ea07d8a_Traceguids, 259);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
        {
          v40 = 1198;
          goto LABEL_146;
        }
        return 259;
      }
      v17 = v48;
      if ( (*(_DWORD *)(a1 + 4) & 0x10000) != 0 || *((_DWORD *)v48 + 40) )
        break;
      if ( (*((_DWORD *)v48 + 38) & 0x100) == 0
        || (v39 = *((_QWORD *)v48 + 31), *(_QWORD *)(v39 + 8))
        || *(_QWORD *)(v39 + 24) )
      {
        if ( *(_DWORD *)(a3 + 16) || !*(_QWORD *)(a3 + 232) )
          break;
      }
      *(_DWORD *)(a1 + 4) |= 0x10000u;
      RefsReleaseFcbWithPaging((struct _IRP_CONTEXT *)a1, (struct _FCB *)a3);
      a2 = v48;
      v8 = a4;
      if ( (*(_DWORD *)v14 & 0x800000) == 0 )
        goto LABEL_132;
    }
    v18 = a4;
    if ( v42 || (*(_DWORD *)v14 & 0x800000) != 0 || (*((_DWORD *)a4 + 6) & 0x800) == 0 )
      break;
    RefsReleaseFcbWithPaging((struct _IRP_CONTEXT *)a1, (struct _FCB *)a3);
    a2 = v48;
    if ( (*(_DWORD *)v14 & 0x800000) == 0 )
    {
LABEL_132:
      RefsReleaseVcb((struct _IRP_CONTEXT *)a1, a4);
      a2 = v48;
    }
    v8 = a4;
  }
  *v14 |= 1uLL;
  if ( (*((_DWORD *)v48 + 38) & 0x100) == 0
    || (a8 & 4) != 0
    || (v19 = *((_QWORD *)v48 + 31), *(_QWORD *)(v19 + 8))
    || *(_QWORD *)(v19 + 24)
    || (v20 = *(_QWORD *)(a3 + 8), (v20 & 1) != 0)
    || (v20 & 0x800) == 0 )
  {
LABEL_23:
    if ( !*(_DWORD *)(a3 + 16) )
    {
      v21 = *(_QWORD *)(a3 + 232);
      if ( v21 )
      {
        if ( *(_DWORD *)(v21 + 104)
          && (*((_DWORD *)v18 + 6) & 2) == 0
          && (*((_DWORD *)v17 + 75) & 0x4000) == 0
          && (*(_BYTE *)v14 & 4) == 0
          && (*(_BYTE *)(a3 + 8) & 1) == 0 )
        {
          for ( i = *(__int64 **)(a3 + 48); i != (__int64 *)(a3 + 48); i = (__int64 *)*i )
          {
            v30 = *((_WORD *)i + 48);
            if ( v30 == 128 || v30 == 176 )
            {
              v31 = (SECTION_OBJECT_POINTERS *)(i[16] + 8);
              if ( v31->DataSectionObject )
              {
                NewFileSize.QuadPart = 0;
                if ( !MmCanFileBeTruncated(v31, &NewFileSize) )
                  goto LABEL_25;
              }
            }
          }
          if ( (v45 & 2) != 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_4391b888391630af3073df0a7ea07d8a_Traceguids, 259);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(259, 0, "Close.c", 0x540u);
            v13 = 259;
            v11 = 0;
            goto LABEL_93;
          }
          RefsPostUsnChange((struct _IRP_CONTEXT *)a1, (struct _FCB *)a3, 0x80000000, 0);
          RefsWriteUsnJournalChanges((struct _IRP_CONTEXT *)a1);
          RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
          v36 = *(_DWORD *)(a1 + 4);
          if ( (v36 & 0x2000) != 0 )
          {
            *(_DWORD *)(a1 + 4) = v36 & 0xFFFFCFFF;
            ExReleaseFastResource(*(_QWORD *)(a3 + 80) + 1208LL, 0);
          }
          RefsReleaseAllExclusiveFcbs((struct _IRP_CONTEXT *)a1, (struct _FCB *)a3);
        }
      }
    }
    goto LABEL_25;
  }
  if ( *(_DWORD *)(a3 + 16) )
  {
LABEL_25:
    v43 = (*(_BYTE *)(a3 + 8) & 4) != 0 || a6 == 5 || *a5 && (*((_DWORD *)*a5 + 1) & 0x20000000) != 0;
    v22 = *a5;
    if ( *a5 )
    {
      NewFileSize = *(union _LARGE_INTEGER *)((char *)v22 + 72);
      QuadPart = (struct _LCB *)NewFileSize.QuadPart;
      if ( *(_WORD *)v22 == 2056 )
      {
        CmsRowWithBuffer::Reset((struct _CCB *)((char *)v22 + 384));
        v27 = (void *)*((_QWORD *)v22 + 59);
        if ( v27 )
        {
          ExFreePoolWithTag(v27, 0);
          *((_QWORD *)v22 + 59) = 0;
        }
        RefsCleanupIndexCursor(v22);
      }
      if ( (*((_DWORD *)v22 + 1) & 0x4000) != 0 )
        ExFreePoolWithTag(*((PVOID *)v22 + 3), 0);
      v23 = *(_QWORD *)(a3 + 88);
      KeEnterGuardedRegion();
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v23 + 8));
      v24 = *((_QWORD *)v22 + 9);
      *((_QWORD *)v22 + 9) = 0;
      if ( v24 )
      {
        ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence((char *)v22 + 56);
        v25[1] = 0;
        *v25 = 0;
      }
      ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence((char *)v22 + 40);
      *((_QWORD *)v22 + 6) = 0;
      *((_QWORD *)v22 + 5) = 0;
      *((_QWORD *)v22 + 6) = MmBadPointer;
      *((_QWORD *)v22 + 5) = MmBadPointer;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a3 + 88) + 8LL));
      KeLeaveGuardedRegion();
      if ( v22 == (struct _CCB *)(a3 + 872) || v22 == (struct _CCB *)(a3 + 800) )
      {
        *(_WORD *)v22 = 0;
      }
      else
      {
        v28 = *(_WORD *)v22 == 2056;
        *(_WORD *)v22 = 0;
        if ( v28 )
          ExFreeToLookasideListEx(&RefsCcbLookasideList, v22);
        else
          ExFreeToLookasideListEx(&RefsCcbDataLookasideList, v22);
      }
      *a5 = 0;
      v26 = NewFileSize;
    }
    else
    {
      v26.QuadPart = 0;
      QuadPart = 0;
    }
    RefsFlushForWriteThrough(a1, a3, 0);
    LOBYTE(v41) = a7;
    v11 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))RefsDecrementCloseCounts)(
            a1,
            v48,
            (union _LARGE_INTEGER)v26.QuadPart,
            v43,
            v41,
            0);
    goto LABEL_93;
  }
  if ( (*((_DWORD *)a4 + 6) & 0x8000823) != 1 )
    goto LABEL_23;
  v33 = 0;
  for ( j = *(_QWORD **)(a3 + 48); j != (_QWORD *)(a3 + 48); j = (_QWORD *)*j )
  {
    v35 = j[16];
    v32 = *(_QWORD *)(v35 + 8) || *(_QWORD *)(v35 + 24);
    v33 |= v32;
  }
  if ( v33 )
  {
LABEL_81:
    v17 = v48;
    goto LABEL_23;
  }
  if ( a1 == *(_QWORD *)(a1 + 104) && LOBYTE(IoGetTopLevelIrp()->Type) && (v12 & 2) == 0 )
  {
    v47[0] = 0;
    QuadPart = 0;
    RefsCompleteFileDeletion((struct _IRP_CONTEXT *)a1, (struct _FCB *)a3, v48, *a5, v47, &QuadPart, 0);
    v18 = a4;
    goto LABEL_81;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_4391b888391630af3073df0a7ea07d8a_Traceguids, 259);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
    RefsStatusDebug(259, 0, "Close.c", 0x4FCu);
  v13 = 259;
LABEL_93:
  if ( !v11 )
    RefsReleaseFcbWithPaging((struct _IRP_CONTEXT *)a1, (struct _FCB *)a3);
  if ( (*(_DWORD *)v14 & 0x800000) == 0 )
  {
    if ( v42 )
      RefsReleaseVcbCheckDelete((struct _IRP_CONTEXT *)a1, a4);
    else
      RefsReleaseVcb((struct _IRP_CONTEXT *)a1, a4);
  }
  if ( v13 != 259 )
    RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)a1, 0, v13);
  return v13;
}

```

## disassembly

```asm
0x140301810  mov     [rsp+arg_18], r9
0x140301815  mov     [rsp+arg_10], r8
0x14030181a  mov     [rsp+arg_8], rdx
0x14030181f  mov     [rsp+arg_0], rcx
0x140301824  push    rbx
0x140301825  push    rsi
0x140301826  push    rdi
0x140301827  push    r12
0x140301829  push    r13
0x14030182b  push    r14
0x14030182d  push    r15
0x14030182f  sub     rsp, 80h
0x140301836  mov     r10, r9
0x140301839  mov     rsi, r8
0x14030183c  mov     r14, rcx
0x14030183f  mov     [rsp+0B8h+var_78], 0
0x140301844  xor     dil, dil
0x140301847  mov     [rsp+0B8h+var_76], dil
0x14030184c  mov     ebx, 1
0x140301851  mov     [rsp+0B8h+var_60], ebx
0x140301855  xor     r15d, r15d
0x140301858  mov     r13d, r15d
0x14030185b  mov     [rsp+0B8h+var_74], r15d
0x140301860  lea     r12, [rcx+8]
0x140301864  mov     [rsp+0B8h+var_48], r12
0x140301869  test    [r12], bl
0x14030186d  jnz     short loc_140301878
0x14030186f  mov     ebx, 3
0x140301874  mov     [rsp+0B8h+var_60], ebx
0x140301878  mov     r8, 20000000000h
0x140301882  mov     rax, [r12]
0x140301886  bt      rax, 17h
0x14030188b  jb      short loc_1403018EE
0x14030188d  test    dword ptr [r10+18h], 800h
0x140301895  setz    cl
0x140301898  bt      rax, 8
0x14030189d  setnb   al
0x1403018a0  test    al, cl
0x1403018a2  jz      loc_140302120
0x1403018a8  mov     rdx, [r14+68h]
0x1403018ac  test    [rdx+8], r8
0x1403018b0  jnz     short loc_1403018C2
0x1403018b2  lea     rcx, [rdx+0A0h]
0x1403018b9  call    MsInitializeFastResourceOwnerEntry
0x1403018be  or      [rdx+8], r8
0x1403018c2  movzx   r8d, byte ptr [r14+8]
0x1403018c7  and     r8b, 1
0x1403018cb  lea     rcx, [r10+520h]
0x1403018d2  add     rdx, 0A0h
0x1403018d9  call    ??$MsAcquireFastResourceSharedInternal@$0A@@@YAEPEAU_MS_FAST_RESOURCE@@PEAU_MS_FAST_RESOURCE_OWNER_ENTRY@@E@Z; MsAcquireFastResourceSharedInternal<0>(_MS_FAST_RESOURCE *,_MS_FAST_RESOURCE_OWNER_ENTRY *,uchar)
0x1403018de  test    al, al
0x1403018e0  jz      loc_1403020A6
0x1403018e6  mov     rdx, [rsp+0B8h+arg_8]
0x1403018ee  test    dword ptr [r14+4], 10000h
0x1403018f6  jz      loc_140301FEA
0x1403018fc  mov     r9d, ebx
0x1403018ff  xor     r8d, r8d
0x140301902  mov     rdx, rsi
0x140301905  mov     rcx, r14
0x140301908  call    ?RefsAcquireFcbWithPaging@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireFcbWithPaging(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x14030190d  test    al, al
0x14030190f  jz      loc_1403021B3
0x140301915  mov     r8, [rsp+0B8h+arg_8]
0x14030191d  test    dword ptr [r14+4], 10000h
0x140301925  jz      loc_14030202D
0x14030192b  mov     r9, [rsp+0B8h+arg_18]
0x140301933  cmp     [rsp+0B8h+var_78], dil
0x140301938  jnz     short loc_140301953
0x14030193a  mov     eax, [r12]
0x14030193e  bt      rax, 17h
0x140301943  jb      short loc_140301953
0x140301945  test    dword ptr [r9+18h], 800h
0x14030194d  jnz     loc_140302140
0x140301953  or      qword ptr [r12], 1
0x140301958  test    dword ptr [r8+98h], 100h
0x140301963  jz      short loc_1403019AD
0x140301965  mov     eax, [rsp+0B8h+arg_38]
0x14030196c  and     eax, 4
0x14030196f  jnz     short loc_1403019AD
0x140301971  mov     rax, [r8+0F8h]
0x140301978  cmp     qword ptr [rax+8], 0
0x14030197d  jnz     short loc_1403019AD
0x14030197f  cmp     qword ptr [rax+18h], 0
0x140301984  jnz     short loc_1403019AD
0x140301986  mov     rax, [rsi+8]
0x14030198a  test    al, 1
0x14030198c  jnz     short loc_1403019AD
0x14030198e  bt      rax, 0Bh
0x140301993  jnb     short loc_1403019AD
0x140301995  cmp     dword ptr [rsi+10h], 0
0x140301999  jnz     short loc_1403019C3
0x14030199b  mov     eax, [r9+18h]
0x14030199f  and     eax, 8000823h
0x1403019a4  cmp     eax, 1
0x1403019a7  jz      loc_140301D56
0x1403019ad  cmp     dword ptr [rsi+10h], 0
0x1403019b1  jnz     short loc_1403019C3
0x1403019b3  mov     rax, [rsi+0E8h]
0x1403019ba  test    rax, rax
0x1403019bd  jnz     loc_140301BED
0x1403019c3  mov     rcx, [rsp+0B8h+arg_20]
0x1403019cb  test    byte ptr [rsi+8], 4
0x1403019cf  jnz     loc_140301B6F
0x1403019d5  cmp     [rsp+0B8h+arg_28], 5
0x1403019dd  jz      loc_140301B6F
0x1403019e3  mov     rax, [rcx]
0x1403019e6  test    rax, rax
0x1403019e9  jz      short loc_1403019F8
0x1403019eb  test    dword ptr [rax+4], 20000000h
0x1403019f2  jnz     loc_140301B6F
0x1403019f8  mov     [rsp+0B8h+var_77], 0
0x1403019fd  mov     rbx, [rcx]
0x140301a00  test    rbx, rbx
0x140301a03  jz      loc_140301BE0
0x140301a09  mov     rax, [rbx+48h]
0x140301a0d  mov     qword ptr [rsp+0B8h+NewFileSize], rax
0x140301a12  mov     [rsp+0B8h+var_68], rax
0x140301a17  mov     eax, 808h
0x140301a1c  cmp     [rbx], ax
0x140301a1f  jz      loc_140301B79
0x140301a25  test    dword ptr [rbx+4], 4000h
0x140301a2c  jnz     loc_140301F70
0x140301a32  mov     rdi, [rsi+58h]
0x140301a36  call    cs:__imp_KeEnterGuardedRegion
0x140301a3d  nop     dword ptr [rax+rax+00h]
0x140301a42  lea     rcx, [rdi+8]; FastMutex
0x140301a46  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140301a4d  nop     dword ptr [rax+rax+00h]
0x140301a52  mov     rax, [rbx+48h]
0x140301a56  mov     [rbx+48h], r15
0x140301a5a  test    rax, rax
0x140301a5d  jz      short loc_140301A6F
0x140301a5f  lea     rcx, [rbx+38h]
0x140301a63  call    ?RemoveEntryListWriteNoFence@?$ListHeadBase@U_FCB@@$0EA@VListEntryLinks@@@@SAEPEAU_LIST_ENTRY@@@Z; ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(_LIST_ENTRY *)
0x140301a68  mov     [rcx+8], r15
0x140301a6c  mov     [rcx], r15
0x140301a6f  lea     rcx, [rbx+28h]
0x140301a73  call    ?RemoveEntryListWriteNoFence@?$ListHeadBase@U_FCB@@$0EA@VListEntryLinks@@@@SAEPEAU_LIST_ENTRY@@@Z; ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(_LIST_ENTRY *)
0x140301a78  mov     [rbx+30h], r15
0x140301a7c  mov     [rbx+28h], r15
0x140301a80  mov     rax, cs:MmBadPointer
0x140301a87  mov     rcx, [rax]
0x140301a8a  mov     [rbx+30h], rcx
0x140301a8e  mov     [rbx+28h], rcx
0x140301a92  mov     rcx, [rsi+58h]
0x140301a96  add     rcx, 8; FastMutex
0x140301a9a  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140301aa1  nop     dword ptr [rax+rax+00h]
0x140301aa6  call    cs:__imp_KeLeaveGuardedRegion
0x140301aad  nop     dword ptr [rax+rax+00h]
0x140301ab2  lea     rax, [rsi+368h]
0x140301ab9  cmp     rbx, rax
0x140301abc  jz      short loc_140301ACE
0x140301abe  lea     rax, [rsi+320h]
0x140301ac5  cmp     rbx, rax
0x140301ac8  jnz     loc_140301BB3
0x140301ace  mov     [rbx], r15w
0x140301ad2  mov     rax, [rsp+0B8h+arg_20]
0x140301ada  mov     [rax], r15
0x140301add  mov     rbx, qword ptr [rsp+0B8h+NewFileSize]
0x140301ae2  xor     r8d, r8d
0x140301ae5  mov     rdx, rsi
0x140301ae8  mov     rcx, r14
0x140301aeb  call    ?RefsFlushForWriteThrough@@YAXPEAU_IRP_CONTEXT@@PEAXW4REFS_FLUSH_FOR_WRITE_THROUGH_FLAGS@@@Z; RefsFlushForWriteThrough(_IRP_CONTEXT *,void *,REFS_FLUSH_FOR_WRITE_THROUGH_FLAGS)
0x140301af0  jmp     short loc_140301B39
0x140301af2  mov     r14, [rsp+0B8h+arg_0]
0x140301afa  test    r14, r14
0x140301afd  jz      short loc_140301B0F
0x140301aff  and     dword ptr [r14+4], 0FFFFFEFFh
0x140301b07  mov     dword ptr [r14+10h], 0
0x140301b0f  mov     dword ptr [r14+10h], 0
0x140301b17  and     qword ptr [r14+8], 0FFFFFFFFFFFFFBFFh
0x140301b1f  xor     r15d, r15d
0x140301b22  mov     rsi, [rsp+0B8h+arg_10]
0x140301b2a  mov     r13d, [rsp+0B8h+var_74]
0x140301b2f  mov     rbx, [rsp+0B8h+var_68]
0x140301b34  mov     r12, [rsp+0B8h+var_48]
0x140301b39  mov     dword ptr [rsp+0B8h+var_90], r15d
0x140301b3e  movzx   eax, [rsp+0B8h+arg_30]
0x140301b46  mov     byte ptr [rsp+0B8h+var_98], al
0x140301b4a  movzx   r9d, [rsp+0B8h+var_77]
0x140301b50  mov     r8, rbx
0x140301b53  mov     rdx, [rsp+0B8h+arg_8]
0x140301b5b  mov     rcx, r14
0x140301b5e  call    ?RefsDecrementCloseCounts@@YA_NPEAU_IRP_CONTEXT@@AEAU_SCB@@PEAU_LCB@@EEW4CloseCountFlags@@@Z; RefsDecrementCloseCounts(_IRP_CONTEXT *,_SCB &,_LCB *,uchar,uchar,CloseCountFlags)
0x140301b63  movzx   edi, al
0x140301b66  mov     [rsp+0B8h+var_76], al
0x140301b6a  jmp     loc_140301F87
0x140301b6f  mov     [rsp+0B8h+var_77], 1
0x140301b74  jmp     loc_1403019FD
0x140301b79  lea     rcx, [rbx+180h]; this
0x140301b80  call    ?Reset@CmsRowWithBuffer@@QEAAXXZ; CmsRowWithBuffer::Reset(void)
0x140301b85  mov     rcx, [rbx+1D8h]; P
0x140301b8c  test    rcx, rcx
0x140301b8f  jz      short loc_140301BA6
0x140301b91  xor     edx, edx; Tag
0x140301b93  call    cs:__imp_ExFreePoolWithTag
0x140301b9a  nop     dword ptr [rax+rax+00h]
0x140301b9f  mov     [rbx+1D8h], r15
0x140301ba6  mov     rcx, rbx; struct _CCB *
0x140301ba9  call    ?RefsCleanupIndexCursor@@YAXAEAU_CCB@@@Z; RefsCleanupIndexCursor(_CCB &)
0x140301bae  jmp     loc_140301A25
0x140301bb3  mov     eax, 808h
0x140301bb8  mov     rdx, rbx; Entry
0x140301bbb  cmp     [rbx], ax
0x140301bbe  mov     [rbx], r15w
0x140301bc2  jz      loc_140301C8A
0x140301bc8  lea     rcx, ?RefsCcbDataLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x140301bcf  call    cs:__imp_ExFreeToLookasideListEx
0x140301bd6  nop     dword ptr [rax+rax+00h]
0x140301bdb  jmp     loc_140301AD2
0x140301be0  mov     rbx, r15
0x140301be3  mov     [rsp+0B8h+var_68], rbx
0x140301be8  jmp     loc_140301AE2
0x140301bed  cmp     dword ptr [rax+68h], 0
0x140301bf1  jz      loc_1403019C3
0x140301bf7  mov     eax, [r9+18h]
0x140301bfb  test    al, 2
0x140301bfd  jnz     loc_1403019C3
0x140301c03  test    dword ptr [r8+12Ch], 4000h
0x140301c0e  jnz     loc_1403019C3
0x140301c14  test    byte ptr [r12], 4
0x140301c19  jnz     loc_1403019C3
0x140301c1f  test    byte ptr [rsi+8], 1
0x140301c23  jnz     loc_1403019C3
0x140301c29  lea     rdi, [rsi+30h]
0x140301c2d  mov     rbx, [rdi]
0x140301c30  mov     ecx, 80h
0x140301c35  mov     edx, 0B0h
0x140301c3a  cmp     rbx, rdi
0x140301c3d  jz      short loc_140301CA2
0x140301c3f  movzx   eax, word ptr [rbx+60h]
0x140301c43  cmp     ax, cx
0x140301c46  jnz     loc_140301E24
0x140301c4c  mov     rcx, [rbx+80h]
0x140301c53  add     rcx, 8; SectionPointer
0x140301c57  cmp     qword ptr [rcx], 0
0x140301c5b  jz      short loc_140301C80
0x140301c5d  mov     qword ptr [rsp+0B8h+NewFileSize], r15
0x140301c62  lea     rdx, [rsp+0B8h+NewFileSize]; NewFileSize
0x140301c67  call    cs:__imp_MmCanFileBeTruncated
0x140301c6e  nop     dword ptr [rax+rax+00h]
0x140301c73  test    al, al
0x140301c75  jz      loc_1403019C3
0x140301c7b  mov     edx, 0B0h
0x140301c80  mov     ecx, 80h
0x140301c85  mov     rbx, [rbx]
0x140301c88  jmp     short loc_140301C3A
0x140301c8a  lea     rcx, ?RefsCcbLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x140301c91  call    cs:__imp_ExFreeToLookasideListEx
0x140301c98  nop     dword ptr [rax+rax+00h]
0x140301c9d  jmp     loc_140301AD2
0x140301ca2  mov     eax, [rsp+0B8h+var_60]
0x140301ca6  and     eax, 2
0x140301ca9  jz      loc_140301E87
0x140301caf  lea     rax, WPP_GLOBAL_Control
0x140301cb6  mov     rcx, cs:WPP_GLOBAL_Control
0x140301cbd  cmp     rcx, rax
0x140301cc0  jnz     loc_140301E32
0x140301cc6  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140301ccd  test    al, al
0x140301ccf  jnz     loc_140301E69
0x140301cd5  mov     r13d, 103h
0x140301cdb  mov     [rsp+0B8h+var_74], r13d
0x140301ce0  xor     dil, dil
0x140301ce3  jmp     loc_140301F87
0x140301ce8  cmp     rax, rcx
0x140301ceb  jnz     short loc_140301D43
0x140301ced  test    dl, dl
0x140301cef  jnz     loc_140301DC2
0x140301cf5  cmp     r14, [r14+68h]
0x140301cf9  jz      short loc_140301D61
0x140301cfb  lea     rax, WPP_GLOBAL_Control
0x140301d02  mov     rcx, cs:WPP_GLOBAL_Control
0x140301d09  cmp     rcx, rax
0x140301d0c  jnz     loc_140301DCF
0x140301d12  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140301d19  test    al, al
0x140301d1b  jnz     loc_140301E06
0x140301d21  mov     r13d, 103h
0x140301d27  mov     [rsp+0B8h+var_74], r13d
0x140301d2c  jmp     loc_140301F87
0x140301d31  cmp     qword ptr [r8+18h], 0
0x140301d36  jnz     short loc_140301D51
0x140301d38  xor     r8b, r8b
0x140301d3b  or      dl, r8b
0x140301d3e  mov     rax, [rax]
0x140301d41  jmp     short loc_140301CE8
0x140301d43  mov     r8, [rax+80h]
0x140301d4a  cmp     qword ptr [r8+8], 0
0x140301d4f  jz      short loc_140301D31
0x140301d51  mov     r8b, 1
0x140301d54  jmp     short loc_140301D3B
0x140301d56  xor     dl, dl
0x140301d58  lea     rcx, [rsi+30h]
0x140301d5c  mov     rax, [rcx]
0x140301d5f  jmp     short loc_140301CE8
0x140301d61  call    cs:__imp_IoGetTopLevelIrp
0x140301d68  nop     dword ptr [rax+rax+00h]
0x140301d6d  cmp     byte ptr [rax], 0
  ... truncated ...
```
