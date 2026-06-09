# NtfsTeardownFromLcb

- ea: `0x14012a0f0`
- end: `0x14012b213`
- name: `NtfsTeardownFromLcb`
- size: `4387`
- prototype: `void __fastcall(__int64, __int64, __int64, __int64, char, _BYTE *, _BYTE *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140128d50`

## callees

- `0x140007ea0`
- `0x140008278`
- `0x14000d1e0`
- `0x14000ea70`
- `0x140012e70`
- `0x14001e810`
- `0x1400331f8`
- `0x14003380c`
- `0x14004a43c`
- `0x140129500`
- `0x14012a0f0`
- `0x14012b220`
- `0x14012ba70`
- `0x14012c090`
- `0x140140380`
- `0x1401419ec`
- `0x140148f30`
- `0x14015e3f4`
- `0x1401c00e0`
- `0x1401e3230`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14012a2e2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14012a33c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14012af83`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14012aff9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14012a2e2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14012a33c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14012af83`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14012aff9`
- `ntoskrnl!ObfDereferenceObject` at `0x14012aa0f`
- `ntoskrnl!ObfDereferenceObject` at `0x14012adf5`
- `ntoskrnl!ObfDereferenceObject` at `0x14012aa0f`
- `ntoskrnl!ObfDereferenceObject` at `0x14012adf5`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14012a9d5`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14012adb6`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14012a9d5`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14012adb6`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14012a6cf`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14012a7dc`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14012aafe`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14012ab22`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14012a6cf`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14012a7dc`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14012aafe`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14012ab22`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14012a595`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14012a7bb`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14012aada`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14012a595`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14012a7bb`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14012aada`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14012a284`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14012a284`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14012a938`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14012ad21`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14012a938`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14012ad21`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402a5d1e`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402a5d1e`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012a4c7`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012a54e`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012a564`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012a9aa`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012ad8f`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012b1ec`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402a5d65`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012a4c7`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012a54e`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012a564`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012a9aa`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012ad8f`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012b1ec`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402a5d65`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14012a867`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14012a867`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012a675`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012a79f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012a675`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012a79f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14012ae99`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14012ae99`
- `ntoskrnl!ExReleaseResourceLite` at `0x14012a9fe`
- `ntoskrnl!ExReleaseResourceLite` at `0x14012ade6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14012af19`
- `ntoskrnl!ExReleaseResourceLite` at `0x14012a9fe`
- `ntoskrnl!ExReleaseResourceLite` at `0x14012ade6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14012af19`
- `ntoskrnl!ExAcquireFastMutex` at `0x14012a5e2`
- `ntoskrnl!ExAcquireFastMutex` at `0x14012a5e2`
- `ntoskrnl!ExReleaseFastMutex` at `0x14012a654`
- `ntoskrnl!ExReleaseFastMutex` at `0x14012a654`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14012a916`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14012acfe`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14012aef0`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14012a916`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14012acfe`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14012aef0`

## pseudocode

```c
void __fastcall NtfsTeardownFromLcb(__int64 a1, __int64 a2, __int64 a3, __int64 a4, char a5, _BYTE *a6, _BYTE *a7)
{
  int v7; // ebx
  __int64 v8; // rdi
  __int64 v9; // r15
  __int64 v10; // r13
  char v11; // r12
  int v12; // r10d
  struct _FILE_OBJECT *v13; // rcx
  int v14; // edx
  bool v15; // al
  __int64 v16; // rbx
  __int64 v17; // rbx
  struct _FILE_OBJECT *v18; // r9
  int v19; // eax
  int v20; // r14d
  __int64 v21; // rdx
  unsigned __int64 v22; // rax
  __int64 v23; // r14
  _QWORD **v24; // r14
  _QWORD *v25; // rcx
  __int64 v26; // r12
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rax
  LIST_ENTRY *p_WaitListHead; // r14
  __int64 v31; // rcx
  _QWORD *v32; // rcx
  __int64 v33; // rdx
  _QWORD *v34; // rcx
  __int64 v35; // rdx
  _QWORD *v36; // rcx
  void *v37; // rcx
  __int64 v38; // rcx
  PFILE_OBJECT v39; // rbx
  __int64 v40; // rdi
  __int64 v41; // rdi
  _DWORD *v42; // rbx
  __int64 v43; // rbx
  void *v44; // r8
  unsigned __int64 v45; // rdx
  __int64 v46; // rcx
  unsigned __int8 v47; // r14
  PFILE_OBJECT v48; // rcx
  _DWORD *FsContext; // rax
  bool v50; // zf
  __int64 *v51; // r14
  union _LARGE_INTEGER *v52; // rdx
  KSPIN_LOCK IrpListLock; // rdx
  char v54; // al
  PFILE_OBJECT v55; // rdx
  __int64 *v56; // r12
  __int64 v57; // rax
  __int64 **v58; // rdx
  __int64 **v59; // rax
  __int64 v60; // rdi
  bool v61; // r14
  unsigned __int8 v62; // bl
  __int64 v63; // rdi
  __int64 v64; // rax
  union _LARGE_INTEGER *v65; // rdx
  __int64 v66; // rcx
  _QWORD *v67; // rdx
  _QWORD *v68; // r8
  _QWORD *v69; // r9
  BOOLEAN v70; // dl
  PFILE_OBJECT v71; // r8
  ULONG *p_Waiters; // rcx
  BOOLEAN IsResourceAcquiredExclusiveLite; // al
  unsigned int *MatchingLcbPair; // rax
  int v75; // r10d
  __int64 v76; // rax
  char v77; // [rsp+40h] [rbp-D8h]
  char v78; // [rsp+41h] [rbp-D7h] BYREF
  BOOLEAN v79; // [rsp+42h] [rbp-D6h]
  bool v80; // [rsp+43h] [rbp-D5h]
  char v81; // [rsp+44h] [rbp-D4h]
  char v82; // [rsp+45h] [rbp-D3h]
  struct _FILE_OBJECT *v83; // [rsp+48h] [rbp-D0h]
  int v84; // [rsp+50h] [rbp-C8h]
  char v85; // [rsp+54h] [rbp-C4h]
  char v86; // [rsp+55h] [rbp-C3h]
  char v87; // [rsp+56h] [rbp-C2h]
  int v88; // [rsp+58h] [rbp-C0h]
  PFILE_OBJECT FileObject; // [rsp+60h] [rbp-B8h]
  __int64 v90; // [rsp+68h] [rbp-B0h]
  int v91; // [rsp+70h] [rbp-A8h]
  unsigned int v92; // [rsp+74h] [rbp-A4h]
  int v93; // [rsp+78h] [rbp-A0h]
  __int64 v94; // [rsp+80h] [rbp-98h] BYREF
  PFILE_OBJECT v95; // [rsp+88h] [rbp-90h]
  __int64 v96; // [rsp+90h] [rbp-88h]
  ULONG *v97; // [rsp+98h] [rbp-80h]
  _QWORD *v98; // [rsp+A0h] [rbp-78h]
  _QWORD *v99; // [rsp+A8h] [rbp-70h]
  __int64 v100; // [rsp+B0h] [rbp-68h]
  __int64 v101; // [rsp+B8h] [rbp-60h] BYREF
  __int64 v102; // [rsp+C0h] [rbp-58h]
  __int64 v103; // [rsp+C8h] [rbp-50h]
  __int64 v104; // [rsp+D0h] [rbp-48h] BYREF
  __int64 v105; // [rsp+D8h] [rbp-40h]
  __int64 v108; // [rsp+130h] [rbp+18h]
  __int64 v109; // [rsp+138h] [rbp+20h]

  v109 = a4;
  v108 = a3;
  v8 = a3;
  v9 = a1;
  v105 = a1;
  v95 = 0;
  v10 = a3;
  v94 = a3;
  v11 = 0;
  v77 = 0;
  v78 = 0;
  LOBYTE(v7) = 0;
  v93 = v7;
  v81 = 0;
  v12 = 1;
  if ( (*(_DWORD *)(a2 + 4) & 0x8000823) == 1 )
  {
    LOBYTE(v7) = *(_DWORD *)(*(_QWORD *)(a1 + 144) + 24LL) == 0;
    v93 = (unsigned __int8)v7;
    v81 = v7;
  }
LABEL_3:
  v13 = 0;
  v83 = 0;
  v95 = 0;
  v14 = 0;
  v88 = 0;
  LOBYTE(a3) = 0;
  v84 = a3;
  v85 = 0;
  v15 = (_BYTE)v7 && (*(_DWORD *)(v10 + 4) & 0x101) == 0;
  v80 = v15;
  while ( 1 )
  {
    v16 = *(_QWORD *)(v10 + 48);
    if ( v16 == v10 + 48 )
      goto LABEL_76;
    if ( v10 == v8 )
      v17 = a4;
    else
      v17 = v16 - 56;
    if ( *(_DWORD *)(v17 + 188) )
      goto LABEL_211;
    if ( (*(_DWORD *)(v17 + 4) & 3) == 1 )
    {
      MatchingLcbPair = (unsigned int *)NtfsFindMatchingLcbPair((_QWORD *)v17);
      if ( MatchingLcbPair )
      {
        SetFlagInterlocked(MatchingLcbPair + 1, 1u);
        ClearFlagInterlocked((unsigned int *)(v17 + 4), v75);
      }
      else
      {
        v76 = *(_QWORD *)(v17 + 24);
        if ( v76 )
        {
          v13 = v83;
          if ( *(int *)(*(_QWORD *)(v76 + 184) + 176LL) < 0 && *(_DWORD *)(*(_QWORD *)(v17 + 48) + 20LL) )
            goto LABEL_211;
          v12 = 1;
          goto LABEL_206;
        }
        v12 = 1;
      }
      v13 = v83;
LABEL_206:
      LOBYTE(a3) = v84;
      v14 = v88;
    }
    v18 = *(struct _FILE_OBJECT **)(v17 + 24);
    FileObject = v18;
    if ( !v18 )
      break;
    v19 = *(_DWORD *)(v17 + 4);
    v88 = v19 | v14;
    if ( v13 )
    {
      LODWORD(a3) = (unsigned __int8)a3;
      if ( v13 != v18 )
        LODWORD(a3) = v12;
      v84 = a3;
      v85 = a3;
    }
    if ( !*(_DWORD *)(v17 + 176) && (v19 & 0x20) != 0 )
    {
      v20 = *(_DWORD *)(v17 + 184);
      v91 = v20;
      v21 = *(_QWORD *)(*(_QWORD *)(v17 + 48) + 96LL) + 4968LL;
      v90 = v21;
      v98 = 0;
      v92 = 0;
      if ( (!v9 || (*(_DWORD *)(v9 + 16) & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x80000000LL) != 0 )
      {
        McTemplateU0pdpw_EtwWriteTransfer(
          *(unsigned __int16 *)(v17 + 72) >> 1,
          v21,
          v21,
          v20,
          v17,
          *(_WORD *)(v17 + 72) >> 1,
          *(_QWORD *)(v17 + 80));
        v21 = v90;
      }
      v97 = (ULONG *)(v21 + 16);
      ExAcquirePushLockSharedEx(v21 + 16, 0);
      v22 = v20 & (unsigned int)(*(_DWORD *)v90 - 1);
      if ( (unsigned int)v22 < *(_DWORD *)(v90 + 4) )
        v22 = v20 & (unsigned int)(2 * *(_DWORD *)v90 - 1);
      v23 = 16 * (v22 & 0x3FF);
      v102 = v23;
      v99 = (_QWORD *)(v90 + 8 * ((v22 >> 10) + 3));
      ExAcquirePushLockExclusiveEx(v23 + *v99 + 8LL, 0);
      v24 = (_QWORD **)(*v99 + v23);
      v98 = v24;
      while ( 1 )
      {
        v25 = *v24;
        if ( !*v24 )
          break;
        if ( *((_DWORD *)v25 + 4) == v91 && v25[1] == v17 )
        {
          *v24 = (_QWORD *)*v25;
          ExFreePoolWithTag(v25, 0);
        }
        else
        {
          v24 = (_QWORD **)*v24;
          v98 = v25;
          ++v92;
        }
      }
      if ( v92 > 5 && !*(_DWORD *)(v90 + 8) && *(_DWORD *)v90 < 0x8000u )
        *(_DWORD *)(v90 + 8) = 1;
      ExReleasePushLockEx(v102 + 8 + *v99, 0);
      ExReleasePushLockEx(v97, 0);
      *(_DWORD *)(v17 + 184) = 0;
      v18 = FileObject;
      if ( (*(_DWORD *)(v17 + 4) & 0x20) != 0 )
        _InterlockedAnd((volatile signed __int32 *)(v17 + 4), 0xFFFFFFDF);
    }
    p_WaitListHead = &v18->Event.Header.WaitListHead;
    FsRtlAcquireHeaderMutex(&v18->LastLock, &v18->Event.Header.WaitListHead);
    if ( *(_DWORD *)(v17 + 176) )
    {
      FsRtlReleaseHeaderMutex(&FileObject->LastLock, p_WaitListHead);
      v13 = v83;
      goto LABEL_211;
    }
    if ( v17 == v109 )
      *a6 = 1;
    if ( (*(_DWORD *)(v17 + 4) & 0x20) != 0 )
    {
      NtfsRemoveHashEntry(v9, *(_QWORD *)(*(_QWORD *)(v17 + 48) + 96LL) + 4968LL, *(unsigned int *)(v17 + 184), v17);
      *(_DWORD *)(v17 + 184) = 0;
      ClearFlagInterlocked((unsigned int *)(v17 + 4), 32);
    }
    NtfsRemovePrefix(v31, v17);
    ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(v17 + 48) + 104LL) + 8LL));
    v32 = *(_QWORD **)(v17 + 120);
    while ( v32 != (_QWORD *)(v17 + 120) )
    {
      v67 = v32;
      v68 = (_QWORD *)*v32;
      v32 = (_QWORD *)*v32;
      if ( v67[2] )
      {
        if ( (_QWORD *)v68[1] != v67 )
          goto LABEL_133;
        v69 = (_QWORD *)v67[1];
        if ( (_QWORD *)*v69 != v67 )
          goto LABEL_133;
        *v69 = v68;
        v68[1] = v69;
        v67[2] = 0;
      }
    }
    v33 = *(_QWORD *)(v17 + 8);
    if ( *(_QWORD *)(v33 + 8) != v17 + 8
      || (v34 = *(_QWORD **)(v17 + 16), *v34 != v17 + 8)
      || (*v34 = v33, *(_QWORD *)(v33 + 8) = v34, v35 = *(_QWORD *)(v17 + 56), *(_QWORD *)(v35 + 8) != v17 + 56)
      || (v36 = *(_QWORD **)(v17 + 64), *v36 != v17 + 56) )
    {
LABEL_133:
      __fastfail(3u);
    }
    *v36 = v35;
    *(_QWORD *)(v35 + 8) = v36;
    ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(v17 + 48) + 104LL) + 8LL));
    v37 = *(void **)(v17 + 192);
    if ( v37 != (void *)(v17 + 144) )
    {
      ExFreePoolWithTag(v37, 0);
      *(_QWORD *)(v17 + 192) = 0;
    }
    if ( *(_DWORD *)(v17 + 184) )
      MicrosoftTelemetryAssertTriggeredMsgKM((__int64)"(*Lcb)->HashValue == 0");
    *(_WORD *)v17 = 0;
    v38 = *(_QWORD *)(v17 + 48);
    if ( v17 != v38 + 1144 && v17 != v38 + 1352 )
    {
      v44 = (void *)v17;
      v103 = v17;
      v45 = 53;
      v100 = 53;
      if ( (v17 & 4) != 0 )
      {
        *(_DWORD *)v17 = -1163005939;
        v45 = 52;
        v100 = 52;
        v44 = (void *)(v17 + 4);
        v103 = v17 + 4;
      }
      memset64(v44, 0xBAADF00DBAADF00DuLL, v45 >> 1);
      if ( (v45 & 1) != 0 )
        *((_DWORD *)v44 + v45 - 1) = -1163005939;
      ExFreeToLookasideListEx(&NtfsLcbLookasideList, (PVOID)v17);
      v8 = v108;
    }
    v39 = FileObject;
    if ( !(_BYTE)v84 && FileObject[2].FileObjectExtension == &FileObject[2].FileObjectExtension )
    {
      IrpListLock = FileObject->IrpListLock;
      if ( *(int *)(IrpListLock + 176) >= 0 )
      {
        v54 = NtfsAcquireExclusiveFcb(v9, IrpListLock, (__int64)FileObject, 3);
        v55 = v83;
        if ( v54 )
          v55 = v39;
        v83 = v55;
        v95 = v55;
      }
    }
    FsRtlReleaseHeaderMutex(&v39->LastLock, p_WaitListHead);
    if ( v10 == v8 )
    {
      v13 = v83;
LABEL_76:
      if ( *(_QWORD *)(v10 + 48) != v10 + 48 )
        goto LABEL_31;
      if ( v80 && ((*(_DWORD *)(v10 + 184) & 0x20000000) != 0 || (*(_DWORD *)(v10 + 4) & 0x10) != 0) )
      {
        NtfsUpdateStandardInformation(v9, v10);
        NtfsCheckpointCurrentTransaction(v9);
      }
      v40 = *(_QWORD *)(v10 + 64);
      if ( v40 == v10 + 64 )
        goto LABEL_86;
      v41 = v40 - 168;
      v104 = v41;
      if ( (*(_DWORD *)(v41 + 512) & 0x100000) != 0 || *(_DWORD *)(v41 + 208) )
        goto LABEL_86;
      if ( (unsigned __int16)(*(_WORD *)v41 - 1797) > 1u )
      {
        FsRtlAcquireHeaderMutex(v41 + 120, v41 + 160);
        v43 = *(_QWORD *)(v41 + 640);
        FsRtlReleaseHeaderMutex(v41 + 120, v41 + 160);
        if ( v43 != v41 + 640 )
          goto LABEL_86;
        v9 = a1;
      }
      v42 = (_DWORD *)(v41 + 212);
      if ( !*(_DWORD *)(v41 + 212) )
      {
LABEL_85:
        NtfsDeleteScb(v9, &v104);
        goto LABEL_86;
      }
      if ( !*(_QWORD *)(v41 + 280) )
        goto LABEL_86;
      if ( (*(_DWORD *)(v41 + 200) & 0x400) != 0 )
        goto LABEL_86;
      v46 = *(_QWORD *)(v41 + 184);
      if ( (*(_DWORD *)(v46 + 4) & 0x20100) != 0 )
        goto LABEL_86;
      v91 = *(_WORD *)(*(_QWORD *)(v41 + 184) + 188LL) == 0;
      v84 = v91;
      v47 = 0;
      v86 = 0;
      if ( !*(_QWORD *)(v41 + 280) || (*(_DWORD *)(v41 + 200) & 0x400) != 0 )
        goto LABEL_121;
      if ( !*(_QWORD *)(v41 + 16) )
      {
LABEL_105:
        v90 = v41 + 184;
        if ( !ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(v41 + 184) + 104LL) + 64LL))
          || !ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(v41 + 192) + 2160LL))
          && (*(_DWORD *)(v9 + 16) & 0x40000000) == 0 )
        {
          ExAcquirePushLockExclusiveEx(*(_QWORD *)v90 + 200LL, 0);
          v47 = 1;
          v86 = 1;
        }
        NtfsUnlockSystemFilePages(v9, v41, v47, 1);
        FileObject = *(PFILE_OBJECT *)(v41 + 280);
        v48 = FileObject;
        *(_QWORD *)(v41 + 280) = 0;
        FsContext = v48->FsContext;
        if ( FsContext && (FsContext[50] & 0x4000) == 0 )
        {
          *(_DWORD *)&v48->FileName.Length = 0;
          v48->FileName.Buffer = 0;
        }
        v50 = v47 == 0;
        v51 = (__int64 *)v90;
        if ( !v50 )
        {
          ExReleasePushLockEx(*(_QWORD *)v90 + 200LL, 0);
          v48 = FileObject;
        }
        if ( v48->PrivateCacheMap )
        {
          v52 = &NtfsLarge0;
          if ( !(_BYTE)v91 )
            v52 = 0;
          CcUninitializeCacheMap(v48, v52, 0);
          v48 = FileObject;
        }
        if ( *(_QWORD *)(v41 + 16) )
        {
          if ( *(_WORD *)v41 != 1794 )
            v41 = *v51;
          ExReleaseResourceLite(*(PERESOURCE *)(v41 + 112));
          v48 = FileObject;
        }
        ObfDereferenceObject(v48);
        goto LABEL_121;
      }
      v70 = 0;
      v79 = 0;
      if ( *(_WORD *)v41 == 1794 )
        v71 = (PFILE_OBJECT)v41;
      else
        v71 = (PFILE_OBJECT)v46;
      FileObject = v71;
      p_Waiters = &v71->Waiters;
      v97 = &v71->Waiters;
      v90 = (__int64)&v71->Waiters;
      while ( 2 )
      {
        if ( ((__int64)v71->Vpb & 0x200) == 0 )
          goto LABEL_176;
        if ( v9 )
        {
          if ( (*(_DWORD *)(v9 + 16) & 0x40000000) != 0 )
            goto LABEL_176;
          v90 = (__int64)p_Waiters;
          if ( (*(_DWORD *)(*(_QWORD *)(v9 + 144) + 16LL) & 0x40000000) != 0 )
            goto LABEL_176;
        }
        IsResourceAcquiredExclusiveLite = ExIsResourceAcquiredExclusiveLite((PERESOURCE)(v71->FileName.Buffer + 1080));
        v70 = v79;
        if ( IsResourceAcquiredExclusiveLite )
        {
          v71 = FileObject;
LABEL_176:
          if ( v70 )
            goto LABEL_105;
          v90 = (__int64)&v71->Waiters;
          v70 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)&v71->Waiters, 0);
          v79 = v70;
          if ( !v70 )
            goto LABEL_121;
          v71 = FileObject;
          p_Waiters = v97;
          continue;
        }
        break;
      }
      if ( v79 )
      {
        ExReleaseResourceLite(*(PERESOURCE *)v90);
        v79 = 0;
      }
LABEL_121:
      if ( !*v42 )
        goto LABEL_85;
LABEL_86:
      if ( *(_QWORD *)(v10 + 64) != v10 + 64 )
        goto LABEL_49;
      ExAcquirePushLockExclusiveEx(a2 + 656, 0);
      v78 = 1;
      if ( *(_DWORD *)(v10 + 28) )
      {
        ExReleasePushLockEx(a2 + 656, 0);
        v78 = 0;
LABEL_49:
        v11 = v77;
        v9 = a1;
        goto LABEL_30;
      }
      if ( v10 == v108 )
        *a7 = 1;
      v9 = a1;
      NtfsDeleteFcb(a1, &v94, &v78);
      v11 = 0;
      v10 = v94;
LABEL_30:
      v13 = v83;
LABEL_31:
      if ( !v13 )
        goto LABEL_211;
      if ( v11 )
      {
        NtfsReleaseFcbEx(v9, v10, 0);
        v13 = v83;
      }
      v10 = v13->IrpListLock;
      v94 = v10;
      v77 = 1;
      v83 = 0;
      v95 = 0;
      v96 = 0;
      v26 = 0;
      while ( 1 )
      {
        v27 = v10 + 64;
        v28 = *(_QWORD *)(v10 + 64);
        if ( v28 == v10 + 64 )
          break;
        v29 = *(_QWORD *)(v10 + 64);
        if ( v26 )
          v29 = *(_QWORD *)(v26 + 168);
        v26 = v29 - 168;
        if ( v29 == v27 )
          v26 = 0;
        if ( !v26 )
          goto LABEL_51;
        if ( *(_DWORD *)(v26 + 256) != 32 || (*(_DWORD *)(v26 + 512) & 0x40) != 0 || v28 == *(_QWORD *)(v10 + 72) )
        {
          v101 = v26;
          v82 = 0;
          if ( (*(_DWORD *)(v26 + 512) & 0x100000) == 0 && !*(_DWORD *)(v26 + 208) )
          {
            if ( (unsigned __int16)(*(_WORD *)v26 - 1797) <= 1u
              || (FsRtlAcquireHeaderMutex(v26 + 120, v26 + 160),
                  v60 = *(_QWORD *)(v26 + 640),
                  FsRtlReleaseHeaderMutex(v26 + 120, v26 + 160),
                  v60 == v26 + 640) )
            {
              if ( a5 && *(_DWORD *)(*(_QWORD *)(v26 + 288) + 4LL) )
              {
                LOBYTE(a4) = v105 == *(_QWORD *)(v9 + 144);
                NtfsAddScbToFspClose(v9, v26, 0, a4, 0);
              }
              else
              {
                if ( !*(_DWORD *)(v26 + 212) )
                  goto LABEL_47;
                if ( *(_QWORD *)(v26 + 280)
                  && (*(_DWORD *)(v26 + 200) & 0x400) == 0
                  && (*(_DWORD *)(*(_QWORD *)(v26 + 184) + 4LL) & 0x20100) == 0 )
                {
                  v61 = *(_WORD *)(*(_QWORD *)(v26 + 184) + 188LL) == 0;
                  v91 = v61;
                  v62 = 0;
                  v87 = 0;
                  if ( !*(_QWORD *)(v26 + 16) || (unsigned __int8)NtfsAcquirePagingResourceExclusive(v9, v26, 0) )
                  {
                    if ( !ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(v26 + 184) + 104LL)
                                                                       + 64LL))
                      || !ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(v26 + 192) + 2160LL))
                      && (*(_DWORD *)(v9 + 16) & 0x40000000) == 0 )
                    {
                      ExAcquirePushLockExclusiveEx(*(_QWORD *)(v26 + 184) + 200LL, 0);
                      v62 = 1;
                      v87 = 1;
                    }
                    NtfsUnlockSystemFilePages(v9, v26, v62, 1);
                    v63 = *(_QWORD *)(v26 + 280);
                    *(_QWORD *)(v26 + 280) = 0;
                    v64 = *(_QWORD *)(v63 + 24);
                    if ( v64 && (*(_DWORD *)(v64 + 200) & 0x4000) == 0 )
                    {
                      *(_DWORD *)(v63 + 88) = 0;
                      *(_QWORD *)(v63 + 96) = 0;
                    }
                    if ( v62 )
                      ExReleasePushLockEx(*(_QWORD *)(v26 + 184) + 200LL, 0);
                    if ( *(_QWORD *)(v63 + 48) )
                    {
                      v65 = &NtfsLarge0;
                      if ( !v61 )
                        v65 = 0;
                      CcUninitializeCacheMap((PFILE_OBJECT)v63, v65, 0);
                    }
                    if ( *(_QWORD *)(v26 + 16) )
                    {
                      if ( *(_WORD *)v26 == 1794 )
                        v66 = v26;
                      else
                        v66 = *(_QWORD *)(v26 + 184);
                      ExReleaseResourceLite(*(PERESOURCE *)(v66 + 112));
                    }
                    ObfDereferenceObject((PVOID)v63);
                  }
                  if ( !*(_DWORD *)(v26 + 212) )
                  {
LABEL_47:
                    NtfsDeleteScb(v9, &v101);
                    v82 = 1;
                    v26 = 0;
                    v96 = 0;
                    continue;
                  }
                }
              }
            }
          }
          if ( v96 )
            goto LABEL_51;
        }
        else
        {
          v56 = (__int64 *)(v26 + 168);
          v57 = *v56;
          if ( *v56 == v27 )
            goto LABEL_51;
          if ( *(__int64 **)(v57 + 8) != v56 )
            goto LABEL_133;
          v58 = (__int64 **)v56[1];
          if ( *v58 != v56 )
            goto LABEL_133;
          *v58 = (__int64 *)v57;
          *(_QWORD *)(v57 + 8) = v58;
          v59 = *(__int64 ***)(v10 + 72);
          if ( *v59 != (__int64 *)v27 )
            goto LABEL_133;
          *v56 = v27;
          v56[1] = (__int64)v59;
          *v59 = v56;
          *(_QWORD *)(v10 + 72) = v56;
          v26 = 0;
          v96 = 0;
        }
      }
      if ( *(_DWORD *)(v10 + 24) )
      {
LABEL_51:
        v11 = 1;
        v13 = v83;
        goto LABEL_211;
      }
      LOBYTE(v7) = v93;
      v11 = 1;
      v8 = v108;
      a4 = v109;
      v12 = 1;
      goto LABEL_3;
    }
    v13 = v83;
    v14 = v88;
    LODWORD(a3) = v84;
    a4 = v109;
    v12 = 1;
  }
  MicrosoftTelemetryAssertTriggeredMsgKM((__int64)"!\"NtfsTeardownFromLcb has an LCB with a NULL SCB\"");
  v13 = v83;
LABEL_211:
  if ( v78 )
  {
    ExReleasePushLockEx(a2 + 656, 0);
    v13 = v83;
  }
  if ( v11 )
  {
    NtfsReleaseFcbEx(v9, v10, 0);
    v13 = v83;
  }
  if ( v13 )
    NtfsReleaseFcbEx(v9, v13->IrpListLock, 0);
}

```

## disassembly

```asm
0x14012a0f0  mov     [rsp+arg_18], r9
0x14012a0f5  mov     [rsp+arg_10], r8
0x14012a0fa  mov     [rsp+arg_8], rdx
0x14012a0ff  mov     qword ptr [rsp+arg_0], rcx
0x14012a104  push    rbx
0x14012a105  push    rsi
0x14012a106  push    rdi
0x14012a107  push    r12
0x14012a109  push    r13
0x14012a10b  push    r14
0x14012a10d  push    r15
0x14012a10f  sub     rsp, 0E0h
0x14012a116  mov     rdi, r8
0x14012a119  mov     r15, rcx
0x14012a11c  mov     [rsp+118h+var_40], rcx
0x14012a124  xor     esi, esi
0x14012a126  mov     [rsp+118h+var_90], rsi
0x14012a12e  mov     r13, r8
0x14012a131  mov     [rsp+118h+var_98], r8
0x14012a139  xor     r12b, r12b
0x14012a13c  mov     [rsp+118h+var_D8], r12b
0x14012a141  mov     [rsp+118h+var_D7], sil
0x14012a146  xor     bl, bl
0x14012a148  mov     [rsp+118h+var_A0], ebx
0x14012a14c  mov     [rsp+118h+var_D4], bl
0x14012a150  mov     eax, [rdx+4]
0x14012a153  and     eax, 8000823h
0x14012a158  mov     r10d, 1
0x14012a15e  cmp     eax, r10d
0x14012a161  jnz     short loc_14012A17C
0x14012a163  mov     rax, [rcx+90h]
0x14012a16a  movzx   ebx, bl
0x14012a16d  cmp     [rax+18h], esi
0x14012a170  cmovz   ebx, r10d
0x14012a174  mov     [rsp+118h+var_A0], ebx
0x14012a178  mov     [rsp+118h+var_D4], bl
0x14012a17c  mov     rcx, rsi
0x14012a17f  mov     [rsp+118h+var_D0], rcx
0x14012a184  mov     [rsp+118h+var_90], rcx
0x14012a18c  mov     edx, esi
0x14012a18e  mov     [rsp+118h+var_C0], edx
0x14012a192  xor     r8b, r8b
0x14012a195  mov     [rsp+118h+var_C8], r8d
0x14012a19a  mov     [rsp+118h+var_C4], r8b
0x14012a19f  test    bl, bl
0x14012a1a1  jz      loc_14012A880
0x14012a1a7  test    dword ptr [r13+4], 101h
0x14012a1af  jnz     loc_14012A880
0x14012a1b5  mov     al, 1
0x14012a1b7  mov     [rsp+118h+var_D5], al
0x14012a1bb  lea     rax, [r13+30h]
0x14012a1bf  mov     rbx, [rax]
0x14012a1c2  cmp     rbx, rax
0x14012a1c5  jz      loc_14012A6E9
0x14012a1cb  cmp     r13, rdi
0x14012a1ce  jnz     loc_14012AAC4
0x14012a1d4  mov     rbx, r9
0x14012a1d7  cmp     dword ptr [rbx+0BCh], 0
0x14012a1de  jnz     loc_14012B1A3
0x14012a1e4  mov     eax, [rbx+4]
0x14012a1e7  and     al, 3
0x14012a1e9  cmp     al, 1
0x14012a1eb  jz      loc_14012B077
0x14012a1f1  mov     r9, [rbx+18h]
0x14012a1f5  mov     [rsp+118h+FileObject], r9
0x14012a1fa  test    r9, r9
0x14012a1fd  jz      loc_14012B061
0x14012a203  mov     eax, [rbx+4]
0x14012a206  or      edx, eax
0x14012a208  mov     [rsp+118h+var_C0], edx
0x14012a20c  test    rcx, rcx
0x14012a20f  jnz     loc_14012B0F1
0x14012a215  cmp     dword ptr [rbx+0B0h], 0
0x14012a21c  jnz     loc_14012A587
0x14012a222  test    al, 20h
0x14012a224  jz      loc_14012A587
0x14012a22a  mov     r14d, [rbx+0B8h]
0x14012a231  mov     [rsp+118h+var_A8], r14d
0x14012a236  mov     rax, [rbx+30h]
0x14012a23a  mov     rdx, [rax+60h]
0x14012a23e  add     rdx, 1368h
0x14012a245  mov     [rsp+118h+var_B0], rdx
0x14012a24a  mov     [rsp+118h+var_78], rsi
0x14012a252  mov     [rsp+118h+var_A4], esi
0x14012a256  test    r15, r15
0x14012a259  jz      short loc_14012A266
0x14012a25b  mov     eax, [r15+10h]
0x14012a25f  bt      rax, 14h
0x14012a264  jb      short loc_14012A273
0x14012a266  cmp     byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, 0
0x14012a26d  jl      loc_14012B10B
0x14012a273  lea     rax, [rdx+10h]
0x14012a277  mov     [rsp+118h+var_80], rax
0x14012a27f  xor     edx, edx
0x14012a281  mov     rcx, rax
0x14012a284  call    cs:__imp_ExAcquirePushLockSharedEx
0x14012a28b  nop     dword ptr [rax+rax+00h]
0x14012a290  mov     rdx, [rsp+118h+var_B0]
0x14012a295  mov     ecx, [rdx]
0x14012a297  lea     eax, [rcx-1]
0x14012a29a  and     eax, r14d
0x14012a29d  cmp     eax, [rdx+4]
0x14012a2a0  jnb     short loc_14012A2AC
0x14012a2a2  lea     eax, ds:0FFFFFFFFFFFFFFFFh[rcx*2]
0x14012a2a9  and     eax, r14d
0x14012a2ac  mov     r14d, eax
0x14012a2af  and     r14d, 3FFh
0x14012a2b6  shl     r14, 4
0x14012a2ba  mov     [rsp+118h+var_58], r14
0x14012a2c2  shr     rax, 0Ah
0x14012a2c6  add     rax, 3
0x14012a2ca  lea     rax, [rdx+rax*8]
0x14012a2ce  mov     [rsp+118h+var_70], rax
0x14012a2d6  mov     rcx, [rax]
0x14012a2d9  add     rcx, 8
0x14012a2dd  add     rcx, r14
0x14012a2e0  xor     edx, edx
0x14012a2e2  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14012a2e9  nop     dword ptr [rax+rax+00h]
0x14012a2ee  mov     rdx, [rsp+118h+var_70]
0x14012a2f6  add     r14, [rdx]
0x14012a2f9  mov     [rsp+118h+var_78], r14
0x14012a301  mov     rcx, [r14]; P
0x14012a304  test    rcx, rcx
0x14012a307  jz      loc_14012A527
0x14012a30d  mov     eax, [rsp+118h+var_A8]
0x14012a311  cmp     [rcx+10h], eax
0x14012a314  jz      loc_14012A78D
0x14012a31a  mov     r14, rcx
0x14012a31d  mov     [rsp+118h+var_78], rcx
0x14012a325  inc     [rsp+118h+var_A4]
0x14012a329  jmp     short loc_14012A301
0x14012a32b  mov     rdi, [rsp+118h+arg_8]
0x14012a333  xor     edx, edx
0x14012a335  lea     rcx, [rdi+290h]
0x14012a33c  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14012a343  nop     dword ptr [rax+rax+00h]
0x14012a348  mov     [rsp+118h+var_D7], 1
0x14012a34d  cmp     dword ptr [r13+1Ch], 0
0x14012a352  jnz     loc_14012A4BE
0x14012a358  cmp     r13, [rsp+118h+arg_10]
0x14012a360  jnz     short loc_14012A36D
0x14012a362  mov     rax, [rsp+118h+arg_30]
0x14012a36a  mov     byte ptr [rax], 1
0x14012a36d  lea     r8, [rsp+118h+var_D7]
0x14012a372  lea     rdx, [rsp+118h+var_98]
0x14012a37a  mov     r15, qword ptr [rsp+118h+arg_0]
0x14012a382  mov     rcx, r15
0x14012a385  call    NtfsDeleteFcb
0x14012a38a  xor     r12b, r12b
0x14012a38d  mov     [rsp+118h+var_D8], r12b
0x14012a392  mov     r13, [rsp+118h+var_98]
0x14012a39a  xor     esi, esi
0x14012a39c  mov     rcx, [rsp+118h+var_D0]
0x14012a3a1  test    rcx, rcx
0x14012a3a4  jz      loc_14012B1A3
0x14012a3aa  test    r12b, r12b
0x14012a3ad  jnz     loc_14012B033
0x14012a3b3  mov     r13, [rcx+0B8h]
0x14012a3ba  mov     [rsp+118h+var_98], r13
0x14012a3c2  mov     [rsp+118h+var_D8], 1
0x14012a3c7  mov     rdx, rsi
0x14012a3ca  mov     [rsp+118h+var_D0], rdx
0x14012a3cf  mov     [rsp+118h+var_90], rdx
0x14012a3d7  mov     rax, rsi
0x14012a3da  mov     [rsp+118h+var_88], rax
0x14012a3e2  mov     r12, rsi
0x14012a3e5  lea     rcx, [r13+40h]
0x14012a3e9  mov     rdx, [rcx]
0x14012a3ec  cmp     rdx, rcx
0x14012a3ef  jz      loc_14012A4EB
0x14012a3f5  test    rax, rax
0x14012a3f8  jnz     loc_14012AB5F
0x14012a3fe  test    r12, r12
0x14012a401  mov     rax, rdx
0x14012a404  jz      short loc_14012A40E
0x14012a406  mov     rax, [r12+0A8h]
0x14012a40e  lea     r12, [rax-0A8h]
0x14012a415  cmp     rax, rcx
0x14012a418  cmovz   r12, rsi
0x14012a41c  test    r12, r12
0x14012a41f  jz      loc_14012A4F2
0x14012a425  cmp     dword ptr [r12+100h], 20h ; ' '
0x14012a42e  jz      loc_14012AA6B
0x14012a434  mov     [rsp+118h+var_60], r12
0x14012a43c  mov     [rsp+118h+var_D3], 0
0x14012a441  test    dword ptr [r12+200h], 100000h
0x14012a44d  jnz     loc_14012AB47
0x14012a453  cmp     dword ptr [r12+0D0h], 0
0x14012a45c  jnz     loc_14012AB47
0x14012a462  movzx   eax, word ptr [r12]
0x14012a467  mov     ecx, 705h
0x14012a46c  sub     ax, cx
0x14012a46f  cmp     ax, 1
0x14012a473  ja      loc_14012AACD
0x14012a479  cmp     [rsp+118h+arg_20], 0
0x14012a481  jnz     loc_14012AF9C
0x14012a487  cmp     dword ptr [r12+0D4h], 0
0x14012a490  jnz     loc_14012AB38
0x14012a496  lea     rdx, [rsp+118h+var_60]
0x14012a49e  mov     rcx, r15
0x14012a4a1  call    NtfsDeleteScb
0x14012a4a6  mov     [rsp+118h+var_D3], 1
0x14012a4ab  mov     r12, rsi
0x14012a4ae  mov     rax, rsi
0x14012a4b1  mov     [rsp+118h+var_88], rax
0x14012a4b9  jmp     loc_14012A3E5
0x14012a4be  xor     edx, edx
0x14012a4c0  lea     rcx, [rdi+290h]
0x14012a4c7  call    cs:__imp_ExReleasePushLockEx
0x14012a4ce  nop     dword ptr [rax+rax+00h]
0x14012a4d3  mov     [rsp+118h+var_D7], 0
0x14012a4d8  movzx   r12d, [rsp+118h+var_D8]
0x14012a4de  mov     r15, qword ptr [rsp+118h+arg_0]
0x14012a4e6  jmp     loc_14012A39A
0x14012a4eb  cmp     dword ptr [r13+18h], 0
0x14012a4f0  jz      short loc_14012A502
0x14012a4f2  movzx   r12d, [rsp+118h+var_D8]
0x14012a4f8  mov     rcx, [rsp+118h+var_D0]
0x14012a4fd  jmp     loc_14012B1A3
0x14012a502  mov     ebx, [rsp+118h+var_A0]
0x14012a506  movzx   r12d, [rsp+118h+var_D8]
0x14012a50c  mov     rdi, [rsp+118h+arg_10]
0x14012a514  mov     r9, [rsp+118h+arg_18]
0x14012a51c  mov     r10d, 1
0x14012a522  jmp     loc_14012A17C
0x14012a527  cmp     [rsp+118h+var_A4], 5
0x14012a52c  ja      loc_14012AC7A
0x14012a532  mov     rax, [rsp+118h+var_70]
0x14012a53a  mov     rcx, [rax]
0x14012a53d  mov     rdx, [rsp+118h+var_58]
0x14012a545  add     rdx, 8
0x14012a549  add     rcx, rdx
0x14012a54c  xor     edx, edx
0x14012a54e  call    cs:__imp_ExReleasePushLockEx
0x14012a555  nop     dword ptr [rax+rax+00h]
0x14012a55a  xor     edx, edx
0x14012a55c  mov     rcx, [rsp+118h+var_80]
0x14012a564  call    cs:__imp_ExReleasePushLockEx
0x14012a56b  nop     dword ptr [rax+rax+00h]
0x14012a570  mov     [rbx+0B8h], esi
0x14012a576  mov     eax, [rbx+4]
0x14012a579  mov     r9, [rsp+118h+FileObject]
0x14012a57e  test    al, 20h
0x14012a580  jz      short loc_14012A587
0x14012a582  lock and dword ptr [rbx+4], 0FFFFFFDFh
0x14012a587  lea     r14, [r9+0A0h]
0x14012a58e  lea     rcx, [r9+78h]
0x14012a592  mov     rdx, r14
0x14012a595  call    cs:__imp_FsRtlAcquireHeaderMutex
0x14012a59c  nop     dword ptr [rax+rax+00h]
0x14012a5a1  cmp     dword ptr [rbx+0B0h], 0
0x14012a5a8  jnz     loc_14012AB16
0x14012a5ae  cmp     rbx, [rsp+118h+arg_18]
0x14012a5b6  jnz     short loc_14012A5C3
0x14012a5b8  mov     rax, [rsp+118h+arg_28]
0x14012a5c0  mov     byte ptr [rax], 1
0x14012a5c3  mov     eax, [rbx+4]
0x14012a5c6  test    al, 20h
0x14012a5c8  jnz     loc_14012B138
0x14012a5ce  mov     rdx, rbx
0x14012a5d1  call    NtfsRemovePrefix
0x14012a5d6  mov     rax, [rbx+30h]
0x14012a5da  mov     rcx, [rax+68h]
0x14012a5de  add     rcx, 8; FastMutex
0x14012a5e2  call    cs:__imp_ExAcquireFastMutex
0x14012a5e9  nop     dword ptr [rax+rax+00h]
0x14012a5ee  lea     rax, [rbx+78h]
0x14012a5f2  mov     rcx, [rax]
0x14012a5f5  cmp     rcx, rax
0x14012a5f8  jnz     loc_14012AE15
0x14012a5fe  lea     rax, [rbx+8]
0x14012a602  mov     rdx, [rax]
0x14012a605  cmp     [rdx+8], rax
0x14012a609  jnz     loc_14012AABD
0x14012a60f  mov     rcx, [rbx+10h]
0x14012a613  cmp     [rcx], rax
0x14012a616  jnz     loc_14012AABD
0x14012a61c  mov     [rcx], rdx
0x14012a61f  mov     [rdx+8], rcx
0x14012a623  lea     rax, [rbx+38h]
0x14012a627  mov     rdx, [rax]
0x14012a62a  cmp     [rdx+8], rax
0x14012a62e  jnz     loc_14012AABD
0x14012a634  mov     rcx, [rbx+40h]
0x14012a638  cmp     [rcx], rax
0x14012a63b  jnz     loc_14012AABD
0x14012a641  mov     [rcx], rdx
0x14012a644  mov     [rdx+8], rcx
0x14012a648  mov     rax, [rbx+30h]
0x14012a64c  mov     rcx, [rax+68h]
0x14012a650  add     rcx, 8; FastMutex
0x14012a654  call    cs:__imp_ExReleaseFastMutex
0x14012a65b  nop     dword ptr [rax+rax+00h]
0x14012a660  mov     rcx, [rbx+0C0h]; P
0x14012a667  lea     rax, [rbx+90h]
0x14012a66e  cmp     rcx, rax
0x14012a671  jz      short loc_14012A688
0x14012a673  xor     edx, edx; Tag
0x14012a675  call    cs:__imp_ExFreePoolWithTag
  ... truncated ...
```
