# RefsCommonVolumeOpen

- ea: `0x1c0179bd4`
- end: `0x1c017a641`
- name: `RefsCommonVolumeOpen`
- size: `2669`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `23`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c0008060`
- `0x1c015d870`

## callees

- `0x1c0003c18`
- `0x1c0003fb0`
- `0x1c00045c4`
- `0x1c0005450`
- `0x1c00057a8`
- `0x1c0005818`
- `0x1c000f770`
- `0x1c0013f90`
- `0x1c003f4d4`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c00b37c0`
- `0x1c0152814`
- `0x1c015527c`
- `0x1c015c914`
- `0x1c015d78c`
- `0x1c016154c`
- `0x1c0161bfc`
- `0x1c01632d4`
- `0x1c016d3c4`
- `0x1c0179bd4`
- `0x1c017a648`
- `0x1c01cd240`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0179d8c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0179d8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c017a42b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c017a42b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c017a232`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c017a25f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c017a5cf`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0180b6f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c017a232`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c017a25f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c017a5cf`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0180b6f`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c017a038`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c017a038`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1c017a04c`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1c0180bc5`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1c018b089`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1c017a04c`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1c0180bc5`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1c018b089`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1c017a21f`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1c017a21f`
- `ntoskrnl!FsRtlAreVolumeStartupApplicationsComplete` at `0x1c017a0ea`
- `ntoskrnl!FsRtlAreVolumeStartupApplicationsComplete` at `0x1c017a0ea`
- `ntoskrnl!CcWaitForCurrentLazyWriterActivity` at `0x1c017a273`
- `ntoskrnl!CcWaitForCurrentLazyWriterActivity` at `0x1c017a273`
- `ntoskrnl!ObGetObjectSecurity` at `0x1c017a4a3`
- `ntoskrnl!ObGetObjectSecurity` at `0x1c017a4a3`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x1c017a503`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x1c017a503`

## string_xrefs

- `0x1c0179f93`: `Create.c`
- `0x1c017a58a`: `Create.c`
- `0x1c017a605`: `Create.c`
- `0x1c018b0a5`: `Create.c`

## pseudocode

```c
__int64 __fastcall RefsCommonVolumeOpen(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  NTSTATUS v4; // ebx
  __int64 v6; // rdi
  __int64 v7; // r15
  __int64 v8; // r12
  __int64 v9; // r13
  __int16 v10; // ax
  __int64 v11; // rsi
  __int64 v12; // rcx
  void *v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // r8
  int v16; // edx
  int v17; // r8d
  bool v18; // cl
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  int v23; // edx
  int v24; // r8d
  __int64 v25; // r8
  __int64 v26; // rcx
  void (__stdcall *PostIrpRoutine)(PVOID, PIRP); // [rsp+28h] [rbp-D0h]
  char v29; // [rsp+81h] [rbp-77h]
  char v30; // [rsp+82h] [rbp-76h]
  char v31; // [rsp+83h] [rbp-75h]
  unsigned int Status; // [rsp+84h] [rbp-74h]
  __int64 v33; // [rsp+88h] [rbp-70h]
  __int64 v34; // [rsp+90h] [rbp-68h]
  __int64 v35; // [rsp+A0h] [rbp-58h] BYREF
  BOOL v36; // [rsp+A8h] [rbp-50h]
  int v37; // [rsp+ACh] [rbp-4Ch] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor[9]; // [rsp+B0h] [rbp-48h] BYREF
  unsigned __int8 MemoryAllocated; // [rsp+110h] [rbp+18h] BYREF
  char v41; // [rsp+118h] [rbp+20h]

  v6 = 0;
  v34 = 0;
  v33 = 0;
  v35 = 0;
  v30 = 0;
  v29 = 0;
  v41 = 0;
  v31 = 0;
  LOBYTE(v4) = 0;
  v36 = v4;
  MemoryAllocated = 0;
  v7 = *(_QWORD *)(a2 + 184);
  v8 = *(_QWORD *)(v7 + 48);
  SecurityDescriptor[1] = (PSECURITY_DESCRIPTOR)v8;
  v9 = 1;
  if ( ((*(_BYTE *)(v7 + 19) - 1) & 0xFD) != 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
    {
      v4 = -1073741790;
    }
    else
    {
      v4 = -1073741790;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 3221225506LL);
    }
    if ( !RefsStatusDebugEnabled )
      goto LABEL_34;
    goto LABEL_33;
  }
  if ( (*(_DWORD *)(v7 + 16) & 1) != 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
    {
      v4 = -1073741811;
    }
    else
    {
      v4 = -1073741811;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 3221225485LL);
    }
    if ( !RefsStatusDebugEnabled )
      goto LABEL_34;
    goto LABEL_33;
  }
  v10 = *(_WORD *)(v7 + 26);
  if ( (v10 & 6) == 0 )
  {
    KeWaitForSingleObject((PVOID)(*(_QWORD *)(a1 + 64) + 3440LL), Executive, 0, 0, 0);
    FsRtlNotifyVolumeEvent((PFILE_OBJECT)v8, 3u);
    v31 = 1;
    v10 = *(_WORD *)(v7 + 26);
  }
  v11 = *(_QWORD *)(a1 + 64);
  v34 = v11;
  LOBYTE(a3) = 1;
  if ( (v10 & 6) != 0 )
    RefsAcquireSharedVcb(a1, v11, a3, a4);
  else
    RefsAcquireExclusiveVcb(a1, v11, a3, a4);
  v30 = 1;
  if ( (*(_DWORD *)(v11 + 4) & 0x802) != 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
    {
      v4 = -1073741790;
    }
    else
    {
      v4 = -1073741790;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 55, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 3221225506LL);
    }
    if ( !RefsStatusDebugEnabled )
      goto LABEL_34;
    goto LABEL_33;
  }
  if ( (unsigned __int8)RefsPingVolume(a1, v11, 0) && (*(_DWORD *)(v11 + 4) & 1) != 0 )
  {
    v9 = *(_QWORD *)(*(_QWORD *)(v11 + 72) + 120LL);
    v33 = v9;
    RefsAcquireExclusiveFcb(a1, v9, 0, 1);
    RefsAccessCheck(a1, 0, v9, 0, a2, *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 184) + 8LL) + 16LL), 0, 0, 0);
    RefsReleaseFcb(a1, v9);
    v29 = 0;
    RefsCheckpointCurrentTransaction(a1);
    v12 = *(_QWORD *)(*(_QWORD *)(v7 + 8) + 8LL);
    if ( (*(_BYTE *)(v7 + 26) & 6) != 0 )
    {
      v36 = (*(_BYTE *)(v12 + 20) & 7) != 0 && (*(_DWORD *)(v11 + 4) & 0x2000000) == 0;
LABEL_12:
      v13 = *(void **)(v8 + 96);
      *(_QWORD *)(v8 + 96) = ExAllocatePoolWithTag((POOL_TYPE)17, 0x10u, 0x43466552u);
      if ( v13 )
        ExFreePoolWithTag(v13, 0);
      *(_OWORD *)*(_QWORD *)(v8 + 96) = *(_OWORD *)L"\\$Volume";
      *(_DWORD *)(v8 + 88) = 1048592;
      *(_DWORD *)(v8 + 80) &= ~0x40u;
      *(_DWORD *)(v8 + 80) |= 8u;
      RefsAcquireExclusiveFcb(a1, v9, 0, 1);
      v29 = 1;
      LODWORD(PostIrpRoutine) = 2;
      v4 = RefsOpenAttribute(
             a1,
             v7,
             v11,
             0,
             v9,
             PostIrpRoutine,
             (__int64)&RefsEmptyString,
             128,
             *(_DWORD *)(v9 + 24) == 0 ? 2 : 0,
             4,
             0,
             2,
             0,
             v11 + 72,
             (__int64)&v35);
      Status = v4;
      if ( v4 >= 0 )
      {
        v14 = *(_QWORD *)(*(_QWORD *)(v7 + 8) + 8LL);
        if ( (*(_BYTE *)(v14 + 20) & 3) == 3 )
        {
          *(_WORD *)(v35 + 88) |= 0x200u;
        }
        else if ( (unsigned __int8)RefsCanAdministerVolume(*(_DWORD *)(v14 + 20) & 3, a2, v9, 0, 0)
               || (LOBYTE(v25) = RefsEffectiveMode(a2, v7, v15),
                   (unsigned __int8)RefsPrivilegeCheck(28, *(_QWORD *)(*(_QWORD *)(v7 + 8) + 8LL) + 32LL, v25)) )
        {
          *(_WORD *)(v35 + 88) |= 0x200u;
        }
        else
        {
          MemoryAllocated = 0;
          SecurityDescriptor[0] = 0;
          v37 = 3;
          if ( !ObGetObjectSecurity(*(PVOID *)(*(_QWORD *)(v11 + 208) + 16LL), SecurityDescriptor, &MemoryAllocated)
            && SecurityDescriptor[0] )
          {
            if ( (unsigned __int8)RefsCanAdministerVolume(v26, a2, v9, SecurityDescriptor[0], &v37) )
              *(_WORD *)(v35 + 88) |= 0x200u;
            ObReleaseObjectSecurity(SecurityDescriptor[0], MemoryAllocated);
          }
        }
        if ( v36 )
          *(_DWORD *)(v35 + 4) |= 0x200u;
        if ( v41 )
        {
          *(_DWORD *)(v11 + 4) |= 2u;
          *(_QWORD *)(v11 + 832) = v8;
          v31 = 0;
        }
        v7 = a2;
        *(_QWORD *)(a2 + 56) = 1;
        goto LABEL_23;
      }
LABEL_35:
      v7 = a2;
LABEL_23:
      RefsCleanupTransaction(a1, (unsigned int)v4, 0);
      if ( !v4 )
      {
        *(_QWORD *)(v8 + 96) = 0;
        *(_DWORD *)(v8 + 88) = 0;
        *(_DWORD *)(v35 + 4) |= 0x4000u;
      }
      goto LABEL_117;
    }
    if ( (*(_DWORD *)(v12 + 20) & 6) != 0 )
    {
      MemoryAllocated = 1;
      if ( FsRtlAreVolumeStartupApplicationsComplete() )
        *(_WORD *)(v7 + 26) &= ~1u;
    }
    if ( (*(_BYTE *)(v7 + 26) & 1) == 0 && *(_DWORD *)(v11 + 216) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
      {
        v4 = -1073741757;
      }
      else
      {
        v4 = -1073741757;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            57,
            WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
            3221225539LL);
      }
      if ( !RefsStatusDebugEnabled )
        goto LABEL_34;
      goto LABEL_33;
    }
    v4 = RefsFlushVolume(a1, v11, 15);
    if ( v4 == -1073741797 )
      v4 = 0;
    Status = v4;
    v16 = *(_DWORD *)(v11 + 220);
    v17 = *(_DWORD *)(v11 + 228);
    if ( (*(_BYTE *)(v7 + 26) & 1) != 0 )
      v18 = *(_DWORD *)(v11 + 224) != v16 - v17;
    else
      v18 = v16 != v17;
    if ( !v18 )
      goto LABEL_100;
    if ( v4 >= 0 )
    {
      RefsCheckpointCurrentTransaction(a1);
      v19 = *(_DWORD *)(a1 + 4);
      if ( (v19 & 0x2000) != 0 )
      {
        *(_DWORD *)(a1 + 4) = v19 & 0xFFFFCFFF;
        RtlCaptureStackBackTrace(0, 9u, (PVOID *)(v11 + 1352), 0);
        ExReleaseResourceLite((PERESOURCE)(v11 + 1176));
      }
      while ( 1 )
      {
        v20 = *(_QWORD *)(a1 + 112);
        if ( v20 == a1 + 112 )
          break;
        RefsReleaseFcbWithPaging(a1, v20 - 72);
      }
      ExReleaseResourceLite((PERESOURCE)(v11 + 1424));
      CcWaitForCurrentLazyWriterActivity();
      LOBYTE(v21) = 1;
      RefsAcquireExclusiveVcb(a1, v11, v21, v22);
      v30 = 1;
      if ( (*(_DWORD *)(v11 + 4) & 0x802) != 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
        {
          v4 = -1073741790;
        }
        else
        {
          v4 = -1073741790;
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_D(
              WPP_GLOBAL_Control->AttachedDevice,
              58,
              WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
              3221225506LL);
        }
        if ( !RefsStatusDebugEnabled )
          goto LABEL_34;
        goto LABEL_33;
      }
      v4 = RefsFlushVolume(a1, v11, 15);
      if ( v4 == -1073741797 )
        v4 = 0;
      Status = v4;
      v18 = 0;
      v23 = *(_DWORD *)(v11 + 220);
      v24 = *(_DWORD *)(v11 + 228);
      if ( (*(_BYTE *)(v7 + 26) & 1) != 0 )
      {
        if ( *(_DWORD *)(v11 + 224) != v23 - v24 )
        {
          v18 = 1;
          if ( RefsTrackVolumeOpenSharingViolation )
LABEL_90:
            __int2c();
        }
      }
      else if ( v23 != v24 )
      {
        v18 = 1;
        if ( RefsTrackVolumeOpenSharingViolation )
          goto LABEL_90;
      }
    }
    if ( v18 )
    {
      if ( v4 < 0 )
        goto LABEL_35;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
      {
        v4 = -1073741757;
      }
      else
      {
        v4 = -1073741757;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            59,
            WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
            3221225539LL);
      }
      if ( !RefsStatusDebugEnabled )
        goto LABEL_34;
LABEL_33:
      RefsStatusDebug(v4);
LABEL_34:
      Status = v4;
      v11 = v34;
      v9 = v33;
      goto LABEL_35;
    }
LABEL_100:
    if ( v4 < 0 )
      goto LABEL_35;
    if ( MemoryAllocated )
      v41 = 1;
    goto LABEL_12;
  }
  *(_DWORD *)(a1 + 4) |= 0x200000u;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 3221225688LL);
  }
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(-1073741608);
  RefsRaiseStatusInternal(a1, 3221225688LL);
LABEL_117:
  if ( v29 )
    RefsReleaseFcb(a1, v9);
  if ( v30 )
    ExReleaseResourceLite((PERESOURCE)(v11 + 1424));
  if ( v31 )
  {
    if ( (unsigned __int8)RefsIsMinstoreTransactionActive(a1) )
    {
      if ( !*(_QWORD *)(a1 + 160) )
        MsTriageGetContext(*(_QWORD *)(a1 + 24));
      RefsAbortTransaction(a1);
    }
    RefsReleaseAllResources(a1);
    FsRtlNotifyVolumeEvent((PFILE_OBJECT)v8, 4u);
  }
  if ( (*(_DWORD *)(a1 + 8) & 2) != 0 )
  {
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Status);
  }
  else
  {
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Status);
    v6 = v7;
  }
  RefsExtendedCompleteRequestInternal(a1, v6, (unsigned int)v4);
  return Status;
}

```

## disassembly

```asm
0x1c0179bd4  mov     r11, rsp
0x1c0179bd7  mov     [r11+10h], rdx
0x1c0179bdb  mov     [r11+8], rcx
0x1c0179bdf  push    rbx
0x1c0179be0  push    rsi
0x1c0179be1  push    rdi
0x1c0179be2  push    r12
0x1c0179be4  push    r13
0x1c0179be6  push    r14
0x1c0179be8  push    r15
0x1c0179bea  sub     rsp, 0C0h
0x1c0179bf1  mov     rax, rdx
0x1c0179bf4  mov     r14, rcx
0x1c0179bf7  xor     edi, edi
0x1c0179bf9  mov     [r11-68h], rdi
0x1c0179bfd  mov     [r11-70h], rdi
0x1c0179c01  mov     [r11-58h], rdi
0x1c0179c05  mov     [r11-76h], dil
0x1c0179c09  mov     [r11-77h], dil
0x1c0179c0d  mov     [r11+20h], dil
0x1c0179c11  mov     [r11-75h], dil
0x1c0179c15  mov     bl, dil
0x1c0179c18  mov     [rsp+0F8h+var_50], ebx
0x1c0179c1f  mov     [r11+18h], dil
0x1c0179c23  mov     r15, [rdx+0B8h]
0x1c0179c2a  mov     r12, [r15+30h]
0x1c0179c2e  mov     [rsp+0F8h+var_40], r12
0x1c0179c36  mov     al, [r15+13h]
0x1c0179c3a  lea     r13d, [rdi+1]
0x1c0179c3e  sub     al, r13b
0x1c0179c41  test    al, 0FDh
0x1c0179c43  jnz     loc_1C0179F35
0x1c0179c49  mov     eax, [r15+10h]
0x1c0179c4d  test    r13b, al
0x1c0179c50  jnz     loc_1C0179FC5
0x1c0179c56  movzx   eax, word ptr [r15+1Ah]
0x1c0179c5b  test    al, 6
0x1c0179c5d  jz      loc_1C017A020
0x1c0179c63  mov     rsi, [r14+40h]
0x1c0179c67  mov     [rsp+0F8h+var_68], rsi
0x1c0179c6f  mov     r8b, r13b
0x1c0179c72  mov     rdx, rsi
0x1c0179c75  mov     rcx, r14
0x1c0179c78  test    al, 6
0x1c0179c7a  jz      loc_1C017A06A
0x1c0179c80  call    RefsAcquireSharedVcb
0x1c0179c85  mov     [rsp+0F8h+var_76], r13b
0x1c0179c8d  test    dword ptr [rsi+4], 802h
0x1c0179c94  jnz     loc_1C017A074
0x1c0179c9a  xor     r8d, r8d
0x1c0179c9d  mov     rdx, rsi
0x1c0179ca0  mov     rcx, r14
0x1c0179ca3  call    RefsPingVolume
0x1c0179ca8  test    al, al
0x1c0179caa  jz      loc_1C017A537
0x1c0179cb0  mov     eax, [rsi+4]
0x1c0179cb3  test    r13b, al
0x1c0179cb6  jz      loc_1C017A537
0x1c0179cbc  mov     rax, [rsi+48h]
0x1c0179cc0  mov     r13, [rax+78h]
0x1c0179cc4  mov     [rsp+0F8h+var_70], r13
0x1c0179ccc  mov     r9d, 1
0x1c0179cd2  xor     r8d, r8d
0x1c0179cd5  mov     rdx, r13
0x1c0179cd8  mov     rcx, r14
0x1c0179cdb  call    RefsAcquireExclusiveFcb
0x1c0179ce0  mov     [rsp+0F8h+var_77], 1
0x1c0179ce8  mov     rdx, [rsp+0F8h+arg_8]
0x1c0179cf0  mov     rax, [rdx+0B8h]
0x1c0179cf7  mov     rcx, [rax+8]
0x1c0179cfb  mov     byte ptr [rsp+0F8h+var_B8], dil
0x1c0179d00  mov     byte ptr [rsp+0F8h+var_C0], dil
0x1c0179d05  mov     byte ptr [rsp+0F8h+var_C8], dil
0x1c0179d0a  mov     eax, [rcx+10h]
0x1c0179d0d  mov     dword ptr [rsp+0F8h+PostIrpRoutine], eax
0x1c0179d11  mov     [rsp+0F8h+Timeout], rdx
0x1c0179d16  xor     r9d, r9d
0x1c0179d19  mov     r8, r13
0x1c0179d1c  xor     edx, edx
0x1c0179d1e  mov     rcx, r14
0x1c0179d21  call    RefsAccessCheck
0x1c0179d26  mov     rdx, r13
0x1c0179d29  mov     rcx, r14
0x1c0179d2c  call    RefsReleaseFcb
0x1c0179d31  mov     [rsp+0F8h+var_77], dil
0x1c0179d39  mov     rcx, r14
0x1c0179d3c  call    RefsCheckpointCurrentTransaction
0x1c0179d41  mov     rax, [r15+8]
0x1c0179d45  mov     rcx, [rax+8]
0x1c0179d49  test    byte ptr [r15+1Ah], 6
0x1c0179d4e  jz      loc_1C017A0D3
0x1c0179d54  test    byte ptr [rcx+14h], 7
0x1c0179d58  setnz   cl
0x1c0179d5b  test    dword ptr [rsi+4], 2000000h
0x1c0179d62  setz    al
0x1c0179d65  test    al, cl
0x1c0179d67  movzx   ebx, bl
0x1c0179d6a  mov     eax, 1
0x1c0179d6f  cmovnz  ebx, eax
0x1c0179d72  mov     [rsp+0F8h+var_50], ebx
0x1c0179d79  mov     rbx, [r12+60h]
0x1c0179d7e  mov     edx, 10h; NumberOfBytes
0x1c0179d83  lea     ecx, [rdx+1]; PoolType
0x1c0179d86  mov     r8d, 43466552h; Tag
0x1c0179d8c  call    cs:__imp_ExAllocatePoolWithTag
0x1c0179d93  nop     dword ptr [rax+rax+00h]
0x1c0179d98  mov     [r12+60h], rax
0x1c0179d9d  test    rbx, rbx
0x1c0179da0  jnz     loc_1C017A426
0x1c0179da6  mov     rax, [r12+60h]
0x1c0179dab  movups  xmm0, xmmword ptr cs:aVolume; "\\$Volume"
0x1c0179db2  movdqu  xmmword ptr [rax], xmm0
0x1c0179db6  mov     dword ptr [r12+58h], 100010h
0x1c0179dbf  and     dword ptr [r12+50h], 0FFFFFFBFh
0x1c0179dc5  mov     eax, [r12+50h]
0x1c0179dca  or      eax, 8
0x1c0179dcd  mov     [r12+50h], eax
0x1c0179dd2  mov     ebx, 1
0x1c0179dd7  mov     r9d, ebx
0x1c0179dda  xor     r8d, r8d
0x1c0179ddd  mov     rdx, r13
0x1c0179de0  mov     rcx, r14
0x1c0179de3  call    RefsAcquireExclusiveFcb
0x1c0179de8  mov     [rsp+0F8h+var_77], bl
0x1c0179def  mov     eax, [r13+18h]
0x1c0179df3  neg     eax
0x1c0179df5  sbb     ecx, ecx
0x1c0179df7  not     ecx
0x1c0179df9  and     ecx, 2
0x1c0179dfc  lea     rax, [rsp+0F8h+var_58]
0x1c0179e04  mov     [rsp+0F8h+var_88], rax; __int64
0x1c0179e09  lea     rax, [rsi+48h]
0x1c0179e0d  mov     [rsp+0F8h+var_90], rax; __int64
0x1c0179e12  mov     [rsp+0F8h+var_98], rdi; __int64
0x1c0179e17  mov     [rsp+0F8h+var_A0], 2; int
0x1c0179e1f  mov     [rsp+0F8h+var_A8], edi; int
0x1c0179e23  mov     [rsp+0F8h+var_B0], 4; int
0x1c0179e2b  mov     [rsp+0F8h+var_B8], ecx; int
0x1c0179e2f  mov     [rsp+0F8h+var_C0], 80h; int
0x1c0179e37  lea     rax, RefsEmptyString
0x1c0179e3e  mov     [rsp+0F8h+var_C8], rax; __int64
0x1c0179e43  mov     dword ptr [rsp+0F8h+PostIrpRoutine], 2; PostIrpRoutine
0x1c0179e4b  mov     [rsp+0F8h+Timeout], r13; __int64
0x1c0179e50  xor     r9d, r9d; int
0x1c0179e53  mov     r8, rsi; int
0x1c0179e56  mov     rdx, r15; int
0x1c0179e59  mov     rcx, r14; int
0x1c0179e5c  call    RefsOpenAttribute
0x1c0179e61  mov     ebx, eax
0x1c0179e63  mov     [rsp+0F8h+Status], eax
0x1c0179e6a  test    eax, eax
0x1c0179e6c  js      loc_1C0179FB8
0x1c0179e72  mov     rcx, [r15+8]
0x1c0179e76  mov     rdx, [rcx+8]
0x1c0179e7a  mov     ecx, [rdx+14h]
0x1c0179e7d  and     ecx, 3
0x1c0179e80  cmp     cl, 3
0x1c0179e83  jz      loc_1C0179F20
0x1c0179e89  mov     [rsp+0F8h+Timeout], rdi
0x1c0179e8e  xor     r9d, r9d
0x1c0179e91  mov     r8, r13
0x1c0179e94  mov     rdx, [rsp+0F8h+arg_8]
0x1c0179e9c  call    RefsCanAdministerVolume
0x1c0179ea1  test    al, al
0x1c0179ea3  jz      loc_1C017A43C
0x1c0179ea9  mov     rax, [rsp+0F8h+var_58]
0x1c0179eb1  mov     r15d, 200h
0x1c0179eb7  or      [rax+58h], r15w
0x1c0179ebc  cmp     byte ptr [rsp+0F8h+var_50], dil
0x1c0179ec4  jnz     short loc_1C0179F12
0x1c0179ec6  cmp     [rsp+0F8h+arg_18], dil
0x1c0179ece  jnz     loc_1C017A51F
0x1c0179ed4  mov     r15, [rsp+0F8h+arg_8]
0x1c0179edc  mov     eax, 1
0x1c0179ee1  mov     [r15+38h], rax
0x1c0179ee5  xor     r8d, r8d
0x1c0179ee8  mov     edx, ebx
0x1c0179eea  mov     rcx, r14
0x1c0179eed  call    RefsCleanupTransaction
0x1c0179ef2  test    ebx, ebx
0x1c0179ef4  jnz     short loc_1C0179F0D
0x1c0179ef6  mov     [r12+60h], rdi
0x1c0179efb  mov     [r12+58h], edi
0x1c0179f00  mov     rax, [rsp+0F8h+var_58]
0x1c0179f08  bts     dword ptr [rax+4], 0Eh
0x1c0179f0d  jmp     loc_1C017A5A9
0x1c0179f12  mov     rax, [rsp+0F8h+var_58]
0x1c0179f1a  or      [rax+4], r15d
0x1c0179f1e  jmp     short loc_1C0179EC6
0x1c0179f20  mov     rcx, [rsp+0F8h+var_58]
0x1c0179f28  mov     r15d, 200h
0x1c0179f2e  or      [rcx+58h], r15w
0x1c0179f33  jmp     short loc_1C0179EBC
0x1c0179f35  lea     rax, WPP_GLOBAL_Control
0x1c0179f3c  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0179f43  cmp     rcx, rax
0x1c0179f46  jz      short loc_1C0179F76
0x1c0179f48  mov     eax, [rcx+2Ch]
0x1c0179f4b  bt      eax, 8
0x1c0179f4f  jnb     short loc_1C0179F76
0x1c0179f51  mov     ebx, 0C0000022h
0x1c0179f56  cmp     byte ptr [rcx+29h], 4
0x1c0179f5a  jb      short loc_1C0179F7B
0x1c0179f5c  mov     edx, 35h ; '5'
0x1c0179f61  mov     r9d, ebx
0x1c0179f64  lea     r8, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c0179f6b  mov     rcx, [rcx+18h]
0x1c0179f6f  call    WPP_SF_D
0x1c0179f74  jmp     short loc_1C0179F7B
0x1c0179f76  mov     ebx, 0C0000022h
0x1c0179f7b  mov     al, cs:RefsStatusDebugEnabled
0x1c0179f81  test    al, al
0x1c0179f83  jz      short loc_1C0179FA1
0x1c0179f85  mov     r8d, 1074h
0x1c0179f8b  jmp     short loc_1C0179F93
0x1c0179f8d  mov     r8d, 11B2h
0x1c0179f93  lea     rdx, aCreateC; "Create.c"
0x1c0179f9a  mov     ecx, ebx; Status
0x1c0179f9c  call    RefsStatusDebug
0x1c0179fa1  mov     [rsp+0F8h+Status], ebx
0x1c0179fa8  mov     rsi, [rsp+0F8h+var_68]
0x1c0179fb0  mov     r13, [rsp+0F8h+var_70]
0x1c0179fb8  mov     r15, [rsp+0F8h+arg_8]
0x1c0179fc0  jmp     loc_1C0179EE5
0x1c0179fc5  lea     rax, WPP_GLOBAL_Control
0x1c0179fcc  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0179fd3  cmp     rcx, rax
0x1c0179fd6  jz      short loc_1C017A006
0x1c0179fd8  mov     eax, [rcx+2Ch]
0x1c0179fdb  bt      eax, 8
0x1c0179fdf  jnb     short loc_1C017A006
0x1c0179fe1  mov     ebx, 0C000000Dh
0x1c0179fe6  cmp     byte ptr [rcx+29h], 4
0x1c0179fea  jb      short loc_1C017A00B
0x1c0179fec  mov     edx, 36h ; '6'
0x1c0179ff1  mov     r9d, ebx
0x1c0179ff4  lea     r8, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c0179ffb  mov     rcx, [rcx+18h]
0x1c0179fff  call    WPP_SF_D
0x1c017a004  jmp     short loc_1C017A00B
0x1c017a006  mov     ebx, 0C000000Dh
0x1c017a00b  mov     al, cs:RefsStatusDebugEnabled
0x1c017a011  test    al, al
0x1c017a013  jz      short loc_1C0179FA1
0x1c017a015  mov     r8d, 107Eh
0x1c017a01b  jmp     loc_1C0179F93
0x1c017a020  mov     rcx, [rcx+40h]
0x1c017a024  add     rcx, 0D70h; Object
0x1c017a02b  mov     [rsp+0F8h+Timeout], rdi; Timeout
0x1c017a030  xor     r9d, r9d; Alertable
0x1c017a033  xor     r8d, r8d; WaitMode
0x1c017a036  xor     edx, edx; WaitReason
0x1c017a038  call    cs:__imp_KeWaitForSingleObject
0x1c017a03f  nop     dword ptr [rax+rax+00h]
0x1c017a044  mov     edx, 3; EventCode
0x1c017a049  mov     rcx, r12; FileObject
0x1c017a04c  call    cs:__imp_FsRtlNotifyVolumeEvent
0x1c017a053  nop     dword ptr [rax+rax+00h]
0x1c017a058  mov     [rsp+0F8h+var_75], r13b
0x1c017a060  movzx   eax, word ptr [r15+1Ah]
0x1c017a065  jmp     loc_1C0179C63
0x1c017a06a  call    RefsAcquireExclusiveVcb
0x1c017a06f  jmp     loc_1C0179C85
0x1c017a074  lea     rax, WPP_GLOBAL_Control
0x1c017a07b  mov     rcx, cs:WPP_GLOBAL_Control
0x1c017a082  cmp     rcx, rax
0x1c017a085  jz      short loc_1C017A0B5
0x1c017a087  mov     eax, [rcx+2Ch]
0x1c017a08a  bt      eax, 8
0x1c017a08e  jnb     short loc_1C017A0B5
0x1c017a090  mov     ebx, 0C0000022h
0x1c017a095  cmp     byte ptr [rcx+29h], 4
0x1c017a099  jb      short loc_1C017A0BA
0x1c017a09b  mov     edx, 37h ; '7'
0x1c017a0a0  mov     r9d, ebx
0x1c017a0a3  lea     r8, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c017a0aa  mov     rcx, [rcx+18h]
0x1c017a0ae  call    WPP_SF_D
0x1c017a0b3  jmp     short loc_1C017A0BA
0x1c017a0b5  mov     ebx, 0C0000022h
0x1c017a0ba  mov     al, cs:RefsStatusDebugEnabled
0x1c017a0c0  test    al, al
0x1c017a0c2  jz      loc_1C0179FA1
0x1c017a0c8  mov     r8d, 10A8h
0x1c017a0ce  jmp     loc_1C0179F93
0x1c017a0d3  mov     eax, [rcx+14h]
0x1c017a0d6  test    al, 6
0x1c017a0d8  jz      short loc_1C017A104
0x1c017a0da  mov     bl, 1
0x1c017a0dc  mov     [rsp+0F8h+MemoryAllocated], bl
0x1c017a0e3  mov     [rsp+0F8h+var_60], bl
0x1c017a0ea  call    cs:__imp_FsRtlAreVolumeStartupApplicationsComplete
0x1c017a0f1  nop     dword ptr [rax+rax+00h]
0x1c017a0f6  test    al, al
0x1c017a0f8  jz      short loc_1C017A104
0x1c017a0fa  mov     eax, 0FFFEh
0x1c017a0ff  and     [r15+1Ah], ax
0x1c017a104  test    byte ptr [r15+1Ah], 1
0x1c017a109  jnz     short loc_1C017A172
0x1c017a10b  cmp     [rsi+0D8h], edi
  ... truncated ...
```
