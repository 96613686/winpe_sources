# RefsCommonVolumeOpen(_IRP_CONTEXT *,_IRP *,_CREATE_CONTEXT *)

- ea: `0x140308620`
- end: `0x140309264`
- name: `?RefsCommonVolumeOpen@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAU_CREATE_CONTEXT@@@Z`
- size: `3140`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, struct _IRP *, struct _CREATE_CONTEXT *)`
- caller_count: `2`
- callee_count: `27`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400bc440`
- `0x140309ae0`

## callees

- `0x14000bcc0`
- `0x140040410`
- `0x140041b40`
- `0x14007e870`
- `0x140080680`
- `0x140081670`
- `0x14008a300`
- `0x14008c400`
- `0x14008dbd0`
- `0x14008e3c0`
- `0x140092e30`
- `0x140099960`
- `0x1400af96c`
- `0x1400ca788`
- `0x1400faea4`
- `0x140286ebc`
- `0x1402870ec`
- `0x1402fec90`
- `0x1402fed30`
- `0x1403008f0`
- `0x140304dc0`
- `0x140307140`
- `0x140308620`
- `0x140309270`
- `0x14031c8e0`
- `0x140332ea0`
- `0x140334a20`

## import_xrefs

- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1403087c3`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1403091b1`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x14033f603`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1403087c3`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1403091b1`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x14033f603`
- `ntoskrnl!FsRtlAreVolumeStartupApplicationsComplete` at `0x140308a96`
- `ntoskrnl!FsRtlAreVolumeStartupApplicationsComplete` at `0x140308a96`
- `ntoskrnl!CcWaitForCurrentLazyWriterActivity` at `0x140308bfe`
- `ntoskrnl!CcWaitForCurrentLazyWriterActivity` at `0x140308bfe`
- `ntoskrnl!ObGetObjectSecurity` at `0x140308ffd`
- `ntoskrnl!ObGetObjectSecurity` at `0x140308ffd`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x140309057`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x140309057`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403087af`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403087af`
- `ntoskrnl!ExReleaseFastResource` at `0x140308bd7`
- `ntoskrnl!ExReleaseFastResource` at `0x140308bd7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140308e39`
- `ntoskrnl!ExFreePoolWithTag` at `0x140308e39`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140308e1a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140308e1a`

## string_xrefs

- `0x14030870d`: `Create.c`
- `0x140309241`: `Create.c`

## pseudocode

```c
__int64 __fastcall RefsCommonVolumeOpen(struct _IRP_CONTEXT *a1, struct _IRP *a2, struct _CREATE_CONTEXT *a3)
{
  __int64 v5; // rsi
  __int64 v6; // r12
  char v7; // r15
  __int64 v8; // rdi
  PFILE_OBJECT v9; // r14
  NTSTATUS v10; // r14d
  unsigned int v11; // r9d
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r8
  int v16; // eax
  NTSTATUS v17; // eax
  char v18; // cl
  int v19; // edx
  NTSTATUS v20; // eax
  int v21; // edx
  int v22; // ecx
  __int64 v23; // rdx
  char v24; // al
  struct _IRP_CONTEXT *v25; // rcx
  struct _IRP_CONTEXT *v26; // rdi
  int v27; // edx
  unsigned int v28; // r8d
  unsigned int v29; // r8d
  int v30; // edx
  PFILE_OBJECT v31; // rdi
  IRP *v32; // rdx
  char v34; // [rsp+81h] [rbp-87h]
  char v35; // [rsp+83h] [rbp-85h]
  char v36; // [rsp+84h] [rbp-84h]
  bool v37; // [rsp+90h] [rbp-78h]
  __int64 v38; // [rsp+98h] [rbp-70h] BYREF
  PFILE_OBJECT FileObject; // [rsp+A0h] [rbp-68h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v41; // [rsp+B0h] [rbp-58h]
  __int64 v42; // [rsp+B8h] [rbp-50h]
  PFILE_OBJECT v43; // [rsp+C0h] [rbp-48h]
  struct _CREATE_CONTEXT *MemoryAllocated; // [rsp+120h] [rbp+18h] BYREF
  PVOID P; // [rsp+128h] [rbp+20h] BYREF

  MemoryAllocated = a3;
  v5 = 0;
  v42 = 0;
  v6 = 0;
  v41 = 0;
  v38 = 0;
  v7 = 0;
  v34 = 0;
  v36 = 0;
  v35 = 0;
  v37 = 0;
  LOBYTE(P) = 0;
  v8 = *((_QWORD *)a3 + 20);
  v9 = *(PFILE_OBJECT *)(v8 + 48);
  FileObject = v9;
  v43 = v9;
  *((_DWORD *)a1 + 175) = 25;
  if ( ((*(_BYTE *)(v8 + 19) - 1) & 0xFD) != 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v10 = -1073741790;
    }
    else
    {
      v10 = -1073741790;
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221225506LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      v11 = 4365;
LABEL_9:
      RefsStatusDebug(v10, 0, "Create.c", v11);
      goto LABEL_133;
    }
    goto LABEL_133;
  }
  if ( (*(_DWORD *)(v8 + 16) & 1) == 0 )
  {
    if ( (*(_BYTE *)(v8 + 26) & 6) == 0 )
    {
      KeWaitForSingleObject((PVOID)(*((_QWORD *)a1 + 8) + 6128LL), Executive, 0, 0, 0);
      FsRtlNotifyVolumeEvent(v9, 3u);
      v35 = 1;
    }
    v5 = *((_QWORD *)a1 + 8);
    v42 = v5;
    v12 = *((_QWORD *)a1 + 13);
    v13 = *(_QWORD *)(v12 + 8) & 0x20000000000LL;
    if ( (*(_BYTE *)(v8 + 26) & 6) != 0 )
    {
      if ( !v13 )
      {
        MsInitializeFastResourceOwnerEntry(v12 + 160);
        *(_QWORD *)(v12 + 8) |= v15;
      }
      if ( !(unsigned __int8)MsAcquireFastResourceSharedInternal<0>(v5 + 1312, v12 + 160, *((_BYTE *)a1 + 8) & 1) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            11,
            WPP_31376ab3b8073048edfb14e725e449b5_Traceguids,
            3221225688LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741608, a1, "ResrcSup.c", 0x1EDu);
        RefsRaiseStatusInternal(a1, -1073741608, (unsigned int)a3);
        __debugbreak();
      }
    }
    else
    {
      if ( !v13 )
      {
        MsInitializeFastResourceOwnerEntry(v12 + 160);
        *(_QWORD *)(v12 + 8) |= v14;
      }
      if ( !(unsigned __int8)MsAcquireFastResourceExclusive(v5 + 1312, v12 + 160, *((_BYTE *)a1 + 8) & 1) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            10,
            WPP_31376ab3b8073048edfb14e725e449b5_Traceguids,
            3221225688LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741608, a1, "ResrcSup.c", 0x1A8u);
        RefsRaiseStatusInternal(a1, -1073741608, (unsigned int)a3);
        __debugbreak();
      }
    }
    v7 = 1;
    if ( (*(_DWORD *)(v5 + 24) & 0x802) != 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v10 = -1073741790;
      }
      else
      {
        v10 = -1073741790;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 58, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221225506LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v11 = 4417;
        goto LABEL_9;
      }
      goto LABEL_133;
    }
    if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v5 + 208) + 16LL) + 48LL) & 2) != 0 || (*(_DWORD *)(v5 + 24) & 1) == 0 )
    {
      *((_DWORD *)a1 + 1) |= 0x200000u;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221225688LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741608, a1, "Create.c", 0x1160u);
      RefsRaiseStatusInternal(a1, -1073741608, (unsigned int)a3);
      __debugbreak();
      JUMPOUT(0x140309264LL);
    }
    v6 = *(_QWORD *)(*(_QWORD *)(v5 + 72) + 136LL);
    v41 = v6;
    RefsAcquireExclusiveFcb(a1, v6, 0, 1);
    RefsAccessCheck(
      a1,
      0,
      (struct _FCB *)v6,
      0,
      a2,
      *(_DWORD *)(a2->Tail.Overlay.CurrentStackLocation->Parameters.WMI.ProviderId + 16),
      0,
      0,
      0);
    RefsReleaseFcb(a1, (struct _FCB *)v6);
    v34 = 0;
    RefsCheckpointCurrentTransaction(a1);
    v16 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v8 + 8) + 8LL) + 20LL);
    if ( (*(_BYTE *)(v8 + 26) & 6) != 0 )
    {
      if ( (v16 & 7) != 0 )
        v37 = (*(_DWORD *)(v5 + 24) & 0x2000000) == 0;
      goto LABEL_112;
    }
    if ( (v16 & 6) != 0 )
    {
      LOBYTE(P) = 1;
      if ( FsRtlAreVolumeStartupApplicationsComplete() )
        *(_WORD *)(v8 + 26) &= ~1u;
    }
    if ( (*(_BYTE *)(v8 + 26) & 1) == 0 && *(_DWORD *)(v5 + 216) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v10 = -1073741757;
      }
      else
      {
        v10 = -1073741757;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221225539LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v11 = 4530;
        goto LABEL_9;
      }
      goto LABEL_133;
    }
    if ( RefsUseFlushVolumeParallel )
      v17 = RefsFlushVolumeParallel(a1, v5, 15);
    else
      v17 = RefsFlushVolumeOriginal(a1, v5, 15);
    v10 = v17;
    if ( v17 == -1073741797 )
      v10 = 0;
    v18 = 0;
    v19 = *(_DWORD *)(v5 + 220);
    LODWORD(a3) = *(_DWORD *)(v5 + 228);
    if ( (*(_BYTE *)(v8 + 26) & 1) != 0 )
    {
      if ( *(_DWORD *)(v5 + 224) == v19 - (_DWORD)a3 )
        goto LABEL_97;
    }
    else if ( v19 == (_DWORD)a3 )
    {
      goto LABEL_97;
    }
    v18 = 1;
    if ( v10 >= 0 )
    {
      RefsCheckpointCurrentTransaction(a1);
      if ( (*((_DWORD *)a1 + 1) & 0x2000) != 0 )
      {
        *((_DWORD *)a1 + 1) &= 0xFFFFCFFF;
        ExReleaseFastResource(v5 + 1208, 0);
      }
      RefsReleaseAllExclusiveFcbsWithPaging(a1);
      RefsReleaseVcb(a1, (struct _VCB *)v5);
      CcWaitForCurrentLazyWriterActivity();
      RefsAcquireExclusiveVcb(a1, (struct _VCB *)v5, 1u);
      if ( (*(_DWORD *)(v5 + 24) & 0x802) != 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v10 = -1073741790;
        }
        else
        {
          v10 = -1073741790;
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            61,
            WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
            3221225506LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
        {
          v11 = 4609;
          goto LABEL_9;
        }
        goto LABEL_133;
      }
      if ( RefsUseFlushVolumeParallel )
        v20 = RefsFlushVolumeParallel(a1, v5, 15);
      else
        v20 = RefsFlushVolumeOriginal(a1, v5, 15);
      v10 = v20;
      if ( v20 == -1073741797 )
        v10 = 0;
      v18 = 0;
      v21 = *(_DWORD *)(v5 + 220);
      LODWORD(a3) = *(_DWORD *)(v5 + 228);
      if ( (*(_BYTE *)(v8 + 26) & 1) != 0 )
      {
        if ( *(_DWORD *)(v5 + 224) == v21 - (_DWORD)a3 )
          goto LABEL_97;
        v18 = 1;
        if ( !RefsTrackVolumeOpenSharingViolation )
          goto LABEL_97;
      }
      else
      {
        if ( v21 == (_DWORD)a3 )
          goto LABEL_97;
        v18 = 1;
        if ( !RefsTrackVolumeOpenSharingViolation )
          goto LABEL_97;
      }
      __int2c();
    }
LABEL_97:
    if ( v18 )
    {
      if ( v10 >= 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v10 = -1073741757;
        }
        else
        {
          v10 = -1073741757;
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            62,
            WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
            3221225539LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
        {
          v11 = 4667;
          goto LABEL_9;
        }
      }
      goto LABEL_133;
    }
    if ( v10 < 0 && v10 != -1073741797 )
      goto LABEL_133;
    v9 = FileObject;
    if ( (_BYTE)P )
      v36 = 1;
LABEL_112:
    P = v9->FileName.Buffer;
    v9->FileName.Buffer = (PWSTR)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), 0x10u, 0x43466552u);
    if ( P )
      ExFreePoolWithTag(P, 0);
    *(_OWORD *)v9->FileName.Buffer = *(_OWORD *)L"\\$Volume";
    *(_DWORD *)&v9->FileName.Length = 1048592;
    v9->Flags &= ~0x40u;
    v9->Flags |= 8u;
    v9->PrivateCacheMap = 0;
    RefsAcquireExclusiveFcb(a1, v6, 0, 1);
    v34 = 1;
    v22 = 2;
    if ( *(_DWORD *)(v6 + 16) )
      v22 = 0;
    v10 = RefsOpenAttribute(
            (struct _IRP **)a1,
            v8,
            v5,
            0,
            (__int64)MemoryAllocated,
            (struct _FCB *)v6,
            2,
            (__int64)&RefsEmptyString,
            0x80u,
            v22,
            4,
            0,
            2,
            0,
            (struct _SCB **)(v5 + 72),
            &v38);
    if ( v10 >= 0 )
    {
      v23 = *(_QWORD *)(*(_QWORD *)(v8 + 8) + 8LL);
      if ( (*(_BYTE *)(v23 + 20) & 3) == 3 )
      {
        *(_WORD *)(v38 + 88) |= 0x200u;
      }
      else if ( RefsCanAdministerVolume((struct _IRP_CONTEXT *)(*(_DWORD *)(v23 + 20) & 3), a2, (struct _FCB *)v6, 0, 0) )
      {
        *(_WORD *)(v38 + 88) |= 0x200u;
      }
      else
      {
        v24 = RefsEffectiveMode(a2, (struct _IO_STACK_LOCATION *)v8);
        if ( RefsPrivilegeCheck(
               0x1Cu,
               (struct _SECURITY_SUBJECT_CONTEXT *)(*(_QWORD *)(*(_QWORD *)(v8 + 8) + 8LL) + 32LL),
               v24) )
        {
          *(_WORD *)(v38 + 88) |= 0x200u;
        }
        else
        {
          LOBYTE(MemoryAllocated) = 0;
          SecurityDescriptor = 0;
          LODWORD(P) = 3;
          if ( !ObGetObjectSecurity(
                  *(PVOID *)(*(_QWORD *)(v5 + 208) + 16LL),
                  &SecurityDescriptor,
                  (PBOOLEAN)&MemoryAllocated)
            && SecurityDescriptor )
          {
            if ( RefsCanAdministerVolume(v25, a2, (struct _FCB *)v6, SecurityDescriptor, (unsigned int *)&P) )
              *(_WORD *)(v38 + 88) |= 0x200u;
            ObReleaseObjectSecurity(SecurityDescriptor, (BOOLEAN)MemoryAllocated);
          }
        }
      }
      if ( v37 )
        *(_DWORD *)(v38 + 4) |= 0x200u;
      if ( v36 )
      {
        *(_DWORD *)(v5 + 24) |= 2u;
        *(_QWORD *)(v5 + 872) = FileObject;
        v35 = 0;
      }
      a2->IoStatus.Information = 1;
    }
    goto LABEL_133;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
  {
    v10 = -1073741811;
  }
  else
  {
    v10 = -1073741811;
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 57, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221225485LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
  {
    v11 = 4375;
    goto LABEL_9;
  }
LABEL_133:
  v26 = (struct _IRP_CONTEXT *)*((_QWORD *)a1 + 13);
  if ( a1 != v26 && *((_BYTE *)a1 + 40) == 3 )
    v26 = a1;
  v27 = *((_DWORD *)v26 + 4);
  if ( v27 < 0 )
  {
    RefsRaiseStatusInternal(a1, v27, (unsigned int)a3);
    __debugbreak();
  }
  if ( v10 < 0 && RefsIsTransactionActive(v26) )
  {
    RefsRaiseStatusInternal(a1, v10, v28);
    __debugbreak();
  }
  if ( *((_DWORD *)a1 + 154) || *((_DWORD *)a1 + 155) )
  {
    RefsWriteUsnJournalChanges(a1);
    RefsCommitCurrentTransaction(a1, 0);
    v30 = *((_DWORD *)v26 + 4);
    if ( v30 < 0 )
    {
      RefsRaiseStatusInternal(a1, v30, v29);
      __debugbreak();
    }
  }
  v31 = FileObject;
  if ( !v10 )
  {
    FileObject->FileName.Buffer = 0;
    *(_DWORD *)&v31->FileName.Length = 0;
    *(_DWORD *)(v38 + 4) |= 0x4000u;
  }
  if ( v34 )
    RefsReleaseFcb(a1, (struct _FCB *)v6);
  if ( v7 )
    RefsReleaseVcb(a1, (struct _VCB *)v5);
  if ( v35 )
  {
    if ( RefsIsTransactionActive(a1) )
    {
      if ( !*((_QWORD *)a1 + 43) )
        MsTriageGetContext(*((_QWORD *)a1 + 3), (char *)a1 + 344);
      RefsAbortTransaction(a1);
    }
    RefsReleaseAllResources(a1);
    FsRtlNotifyVolumeEvent(v31, 4u);
  }
  v32 = 0;
  if ( (*((_BYTE *)a1 + 8) & 2) == 0 )
    v32 = a2;
  RefsCompleteRequest(a1, v32, v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140308620  mov     r11, rsp
0x140308623  mov     [r11+18h], r8
0x140308627  mov     [r11+8], rcx
0x14030862b  push    rbx
0x14030862c  push    rsi
0x14030862d  push    rdi
0x14030862e  push    r12
0x140308630  push    r13
0x140308632  push    r14
0x140308634  push    r15
0x140308636  sub     rsp, 0D0h
0x14030863d  mov     rax, r8
0x140308640  mov     r13, rdx
0x140308643  mov     rbx, rcx
0x140308646  xor     esi, esi
0x140308648  mov     [r11-50h], rsi
0x14030864c  xor     r12d, r12d
0x14030864f  mov     [r11-58h], r12
0x140308653  mov     [r11-70h], rsi
0x140308657  xor     r15b, r15b
0x14030865a  mov     [r11-86h], r15b
0x140308661  mov     [rsp+108h+var_87], sil
0x140308669  mov     [rsp+108h+var_84], sil
0x140308671  mov     [rsp+108h+var_85], sil
0x140308679  mov     [rsp+108h+var_78], sil
0x140308681  mov     [r11+20h], sil
0x140308685  mov     rdi, [r8+0A0h]
0x14030868c  mov     r14, [rdi+30h]
0x140308690  mov     [rsp+108h+FileObject], r14
0x140308698  mov     [rsp+108h+var_48], r14
0x1403086a0  mov     dword ptr [rcx+2BCh], 19h
0x1403086aa  movzx   eax, byte ptr [rdi+13h]
0x1403086ae  dec     al
0x1403086b0  test    al, 0FDh
0x1403086b2  jz      short loc_14030872B
0x1403086b4  lea     rax, WPP_GLOBAL_Control
0x1403086bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1403086c2  cmp     rcx, rax
0x1403086c5  jz      short loc_1403086F6
0x1403086c7  mov     eax, [rcx+2Ch]
0x1403086ca  bt      eax, 8
0x1403086ce  jnb     short loc_1403086F6
0x1403086d0  cmp     byte ptr [rcx+29h], 4
0x1403086d4  jb      short loc_1403086F6
0x1403086d6  mov     edx, 38h ; '8'
0x1403086db  mov     r14d, 0C0000022h
0x1403086e1  mov     r9d, r14d
0x1403086e4  lea     r8, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids
0x1403086eb  mov     rcx, [rcx+18h]
0x1403086ef  call    WPP_SF_d
0x1403086f4  jmp     short loc_1403086FC
0x1403086f6  mov     r14d, 0C0000022h
0x1403086fc  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140308703  test    al, al
0x140308705  jz      short loc_14030871E
0x140308707  mov     r9d, 110Dh; unsigned int
0x14030870d  lea     r8, aCreateC; "Create.c"
0x140308714  xor     edx, edx; struct _IRP_CONTEXT *
0x140308716  mov     ecx, r14d; Status
0x140308719  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14030871e  mov     [rsp+108h+var_80], r14d
0x140308726  jmp     loc_1403090AC
0x14030872b  mov     eax, [rdi+10h]
0x14030872e  test    al, 1
0x140308730  jz      short loc_14030878D
0x140308732  lea     rax, WPP_GLOBAL_Control
0x140308739  mov     rcx, cs:WPP_GLOBAL_Control
0x140308740  cmp     rcx, rax
0x140308743  jz      short loc_140308774
0x140308745  mov     eax, [rcx+2Ch]
0x140308748  bt      eax, 8
0x14030874c  jnb     short loc_140308774
0x14030874e  cmp     byte ptr [rcx+29h], 4
0x140308752  jb      short loc_140308774
0x140308754  mov     edx, 39h ; '9'
0x140308759  mov     r14d, 0C000000Dh
0x14030875f  mov     r9d, r14d
0x140308762  lea     r8, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids
0x140308769  mov     rcx, [rcx+18h]
0x14030876d  call    WPP_SF_d
0x140308772  jmp     short loc_14030877A
0x140308774  mov     r14d, 0C000000Dh
0x14030877a  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140308781  test    al, al
0x140308783  jz      short loc_14030871E
0x140308785  mov     r9d, 1117h
0x14030878b  jmp     short loc_14030870D
0x14030878d  test    byte ptr [rdi+1Ah], 6
0x140308791  jnz     short loc_1403087D7
0x140308793  mov     rcx, [rcx+40h]
0x140308797  add     rcx, 17F0h; Object
0x14030879e  mov     [rsp+108h+Timeout], 0; Timeout
0x1403087a7  xor     r9d, r9d; Alertable
0x1403087aa  xor     r8d, r8d; WaitMode
0x1403087ad  xor     edx, edx; WaitReason
0x1403087af  call    cs:__imp_KeWaitForSingleObject
0x1403087b6  nop     dword ptr [rax+rax+00h]
0x1403087bb  mov     edx, 3; EventCode
0x1403087c0  mov     rcx, r14; FileObject
0x1403087c3  call    cs:__imp_FsRtlNotifyVolumeEvent
0x1403087ca  nop     dword ptr [rax+rax+00h]
0x1403087cf  mov     [rsp+108h+var_85], 1
0x1403087d7  mov     rsi, [rbx+40h]
0x1403087db  mov     [rsp+108h+var_50], rsi
0x1403087e3  mov     rdx, [rbx+68h]
0x1403087e7  mov     r8, 20000000000h
0x1403087f1  mov     rcx, [rdx+8]
0x1403087f5  and     rcx, r8
0x1403087f8  test    byte ptr [rdi+1Ah], 6
0x1403087fc  jnz     loc_1403088AB
0x140308802  test    rcx, rcx
0x140308805  jnz     short loc_140308817
0x140308807  lea     rcx, [rdx+0A0h]
0x14030880e  call    MsInitializeFastResourceOwnerEntry
0x140308813  or      [rdx+8], r8
0x140308817  movzx   r8d, byte ptr [rbx+8]
0x14030881c  and     r8b, 1
0x140308820  lea     rcx, [rsi+520h]
0x140308827  add     rdx, 0A0h
0x14030882e  call    MsAcquireFastResourceExclusive
0x140308833  test    al, al
0x140308835  jnz     loc_140308950
0x14030883b  lea     rax, WPP_GLOBAL_Control
0x140308842  mov     rcx, cs:WPP_GLOBAL_Control
0x140308849  cmp     rcx, rax
0x14030884c  jz      short loc_140308878
0x14030884e  test    dword ptr [rcx+2Ch], 100h
0x140308855  jz      short loc_140308878
0x140308857  cmp     byte ptr [rcx+29h], 4
0x14030885b  jb      short loc_140308878
0x14030885d  mov     edx, 0Ah
0x140308862  mov     r9d, 0C00000D8h
0x140308868  lea     r8, WPP_31376ab3b8073048edfb14e725e449b5_Traceguids
0x14030886f  mov     rcx, [rcx+18h]
0x140308873  call    WPP_SF_d
0x140308878  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14030887f  test    al, al
0x140308881  jz      short loc_14030889D
0x140308883  mov     r9d, 1A8h; unsigned int
0x140308889  lea     r8, aResrcsupC; "ResrcSup.c"
0x140308890  mov     rdx, rbx; struct _IRP_CONTEXT *
0x140308893  mov     ecx, 0C00000D8h; Status
0x140308898  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14030889d  mov     edx, 0C00000D8h; int
0x1403088a2  mov     rcx, rbx; struct _IRP_CONTEXT *
0x1403088a5  call    ?RefsRaiseStatusInternal@@YAXPEAU_IRP_CONTEXT@@JK@Z; RefsRaiseStatusInternal(_IRP_CONTEXT *,long,ulong)
0x1403088aa  int     3; Trap to Debugger
0x1403088ab  test    rcx, rcx
0x1403088ae  jnz     short loc_1403088C0
0x1403088b0  lea     rcx, [rdx+0A0h]
0x1403088b7  call    MsInitializeFastResourceOwnerEntry
0x1403088bc  or      [rdx+8], r8
0x1403088c0  movzx   r8d, byte ptr [rbx+8]
0x1403088c5  and     r8b, 1
0x1403088c9  lea     rcx, [rsi+520h]
0x1403088d0  add     rdx, 0A0h
0x1403088d7  call    ??$MsAcquireFastResourceSharedInternal@$0A@@@YAEPEAU_MS_FAST_RESOURCE@@PEAU_MS_FAST_RESOURCE_OWNER_ENTRY@@E@Z; MsAcquireFastResourceSharedInternal<0>(_MS_FAST_RESOURCE *,_MS_FAST_RESOURCE_OWNER_ENTRY *,uchar)
0x1403088dc  test    al, al
0x1403088de  jnz     short loc_140308950
0x1403088e0  lea     rax, WPP_GLOBAL_Control
0x1403088e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1403088ee  cmp     rcx, rax
0x1403088f1  jz      short loc_14030891D
0x1403088f3  test    dword ptr [rcx+2Ch], 100h
0x1403088fa  jz      short loc_14030891D
0x1403088fc  cmp     byte ptr [rcx+29h], 4
0x140308900  jb      short loc_14030891D
0x140308902  mov     edx, 0Bh
0x140308907  mov     r9d, 0C00000D8h
0x14030890d  lea     r8, WPP_31376ab3b8073048edfb14e725e449b5_Traceguids
0x140308914  mov     rcx, [rcx+18h]
0x140308918  call    WPP_SF_d
0x14030891d  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140308924  test    al, al
0x140308926  jz      short loc_140308942
0x140308928  mov     r9d, 1EDh; unsigned int
0x14030892e  lea     r8, aResrcsupC; "ResrcSup.c"
0x140308935  mov     rdx, rbx; struct _IRP_CONTEXT *
0x140308938  mov     ecx, 0C00000D8h; Status
0x14030893d  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x140308942  mov     edx, 0C00000D8h; int
0x140308947  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14030894a  call    ?RefsRaiseStatusInternal@@YAXPEAU_IRP_CONTEXT@@JK@Z; RefsRaiseStatusInternal(_IRP_CONTEXT *,long,ulong)
0x14030894f  int     3; Trap to Debugger
0x140308950  mov     r15b, 1
0x140308953  mov     [rsp+108h+var_86], r15b
0x14030895b  test    dword ptr [rsi+18h], 802h
0x140308962  jz      short loc_1403089C6
0x140308964  lea     rax, WPP_GLOBAL_Control
0x14030896b  mov     rcx, cs:WPP_GLOBAL_Control
0x140308972  cmp     rcx, rax
0x140308975  jz      short loc_1403089A6
0x140308977  mov     eax, [rcx+2Ch]
0x14030897a  bt      eax, 8
0x14030897e  jnb     short loc_1403089A6
0x140308980  cmp     byte ptr [rcx+29h], 4
0x140308984  jb      short loc_1403089A6
0x140308986  mov     edx, 3Ah ; ':'
0x14030898b  mov     r14d, 0C0000022h
0x140308991  mov     r9d, r14d
0x140308994  lea     r8, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids
0x14030899b  mov     rcx, [rcx+18h]
0x14030899f  call    WPP_SF_d
0x1403089a4  jmp     short loc_1403089AC
0x1403089a6  mov     r14d, 0C0000022h
0x1403089ac  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1403089b3  test    al, al
0x1403089b5  jz      loc_14030871E
0x1403089bb  mov     r9d, 1141h
0x1403089c1  jmp     loc_14030870D
0x1403089c6  mov     eax, [rsi+18h]
0x1403089c9  mov     rax, [rsi+0D0h]
0x1403089d0  mov     rcx, [rax+10h]
0x1403089d4  mov     eax, [rcx+30h]
0x1403089d7  test    al, 2
0x1403089d9  jnz     loc_1403091EC
0x1403089df  mov     eax, [rsi+18h]
0x1403089e2  test    r15b, al
0x1403089e5  jz      loc_1403091EC
0x1403089eb  mov     rax, [rsi+48h]
0x1403089ef  mov     r12, [rax+88h]
0x1403089f6  mov     [rsp+108h+var_58], r12
0x1403089fe  mov     r9d, 1
0x140308a04  xor     r8d, r8d
0x140308a07  mov     rdx, r12
0x140308a0a  mov     rcx, rbx
0x140308a0d  call    ?RefsAcquireExclusiveFcb@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireExclusiveFcb(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x140308a12  mov     [rsp+108h+var_87], r15b
0x140308a1a  mov     rax, [r13+0B8h]
0x140308a21  mov     rax, [rax+8]
0x140308a25  mov     [rsp+108h+var_C8], 0; unsigned __int8
0x140308a2a  mov     [rsp+108h+var_D0], 0; unsigned __int8
0x140308a2f  mov     [rsp+108h+var_D8], 0; unsigned __int8
0x140308a34  mov     eax, [rax+10h]
0x140308a37  mov     [rsp+108h+var_E0], eax; unsigned int
0x140308a3b  mov     [rsp+108h+Timeout], r13; struct _IRP *
0x140308a40  xor     r9d, r9d; struct _FCB *
0x140308a43  mov     r8, r12; struct _FCB *
0x140308a46  xor     edx, edx; struct _CREATE_CONTEXT *
0x140308a48  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140308a4b  call    ?RefsAccessCheck@@YAXPEAU_IRP_CONTEXT@@PEAU_CREATE_CONTEXT@@PEAU_FCB@@2PEAU_IRP@@KEEE@Z; RefsAccessCheck(_IRP_CONTEXT *,_CREATE_CONTEXT *,_FCB *,_FCB *,_IRP *,ulong,uchar,uchar,uchar)
0x140308a50  mov     rdx, r12; struct _FCB *
0x140308a53  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140308a56  call    ?RefsReleaseFcb@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsReleaseFcb(_IRP_CONTEXT *,_FCB *)
0x140308a5b  mov     [rsp+108h+var_87], 0
0x140308a63  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140308a66  call    ?RefsCheckpointCurrentTransaction@@YAXPEAU_IRP_CONTEXT@@@Z; RefsCheckpointCurrentTransaction(_IRP_CONTEXT *)
0x140308a6b  mov     rax, [rdi+8]
0x140308a6f  mov     rcx, [rax+8]
0x140308a73  mov     eax, [rcx+14h]
0x140308a76  test    byte ptr [rdi+1Ah], 6
0x140308a7a  jnz     loc_140308DD6
0x140308a80  test    al, 6
0x140308a82  jz      short loc_140308AAF
0x140308a84  movzx   eax, r15b
0x140308a88  mov     byte ptr [rsp+108h+P], al
0x140308a8f  mov     [rsp+108h+var_7C], al
0x140308a96  call    cs:__imp_FsRtlAreVolumeStartupApplicationsComplete
0x140308a9d  nop     dword ptr [rax+rax+00h]
0x140308aa2  test    al, al
0x140308aa4  jz      short loc_140308AAF
0x140308aa6  mov     eax, 0FFFEh
0x140308aab  and     [rdi+1Ah], ax
0x140308aaf  test    [rdi+1Ah], r15b
0x140308ab3  jnz     short loc_140308B20
0x140308ab5  cmp     dword ptr [rsi+0D8h], 0
0x140308abc  jz      short loc_140308B20
0x140308abe  lea     rax, WPP_GLOBAL_Control
0x140308ac5  mov     rcx, cs:WPP_GLOBAL_Control
0x140308acc  cmp     rcx, rax
0x140308acf  jz      short loc_140308B00
0x140308ad1  mov     eax, [rcx+2Ch]
0x140308ad4  bt      eax, 8
0x140308ad8  jnb     short loc_140308B00
0x140308ada  cmp     byte ptr [rcx+29h], 4
0x140308ade  jb      short loc_140308B00
0x140308ae0  mov     edx, 3Ch ; '<'
0x140308ae5  mov     r14d, 0C0000043h
0x140308aeb  mov     r9d, r14d
0x140308aee  lea     r8, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids
0x140308af5  mov     rcx, [rcx+18h]
0x140308af9  call    WPP_SF_d
0x140308afe  jmp     short loc_140308B06
0x140308b00  mov     r14d, 0C0000043h
0x140308b06  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140308b0d  test    al, al
0x140308b0f  jz      loc_14030871E
0x140308b15  mov     r9d, 11B2h
0x140308b1b  jmp     loc_14030870D
0x140308b20  movzx   eax, cs:?RefsUseFlushVolumeParallel@@3EC; uchar volatile RefsUseFlushVolumeParallel
0x140308b27  mov     r8d, 0Fh
0x140308b2d  mov     rdx, rsi
0x140308b30  mov     rcx, rbx
0x140308b33  test    al, al
0x140308b35  jz      short loc_140308B3E
0x140308b37  call    ?RefsFlushVolumeParallel@@YAJPEAU_IRP_CONTEXT@@PEAU_VCB@@W4REFS_FLUSH_VOLUME_FLAGS@@@Z; RefsFlushVolumeParallel(_IRP_CONTEXT *,_VCB *,REFS_FLUSH_VOLUME_FLAGS)
0x140308b3c  jmp     short loc_140308B43
0x140308b3e  call    ?RefsFlushVolumeOriginal@@YAJPEAU_IRP_CONTEXT@@PEAU_VCB@@W4REFS_FLUSH_VOLUME_FLAGS@@@Z; RefsFlushVolumeOriginal(_IRP_CONTEXT *,_VCB *,REFS_FLUSH_VOLUME_FLAGS)
0x140308b43  mov     r14d, eax
0x140308b46  mov     [rsp+108h+var_80], eax
  ... truncated ...
```
