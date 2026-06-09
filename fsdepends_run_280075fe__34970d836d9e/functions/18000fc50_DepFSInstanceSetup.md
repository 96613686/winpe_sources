# DepFSInstanceSetup

- ea: `0x18000fc50`
- end: `0x180010bfa`
- name: `DepFSInstanceSetup`
- size: `4010`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800010fc`
- `0x180001150`
- `0x1800015a8`
- `0x180001ad0`
- `0x180001d10`
- `0x180001d68`
- `0x180002480`
- `0x18000b964`
- `0x18000f5f8`
- `0x18000f73c`
- `0x18000f91c`
- `0x18000fc50`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x180010b03`
- `ntoskrnl!KeSetEvent` at `0x180010b03`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x1800108ad`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x1800108ad`
- `ntoskrnl!ExAllocatePool2` at `0x18000fef7`
- `ntoskrnl!ExAllocatePool2` at `0x180010405`
- `ntoskrnl!ExAllocatePool2` at `0x18001051a`
- `ntoskrnl!ExAllocatePool2` at `0x18000fef7`
- `ntoskrnl!ExAllocatePool2` at `0x180010405`
- `ntoskrnl!ExAllocatePool2` at `0x18001051a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180010773`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180010818`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18001087f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180010a8a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180010773`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180010818`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18001087f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180010a8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000fecb`
- `ntoskrnl!ExFreePoolWithTag` at `0x180010754`
- `ntoskrnl!ExFreePoolWithTag` at `0x180010a9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000fecb`
- `ntoskrnl!ExFreePoolWithTag` at `0x180010754`
- `ntoskrnl!ExFreePoolWithTag` at `0x180010a9e`
- `ntoskrnl!ExReleaseResourceLite` at `0x180010767`
- `ntoskrnl!ExReleaseResourceLite` at `0x18001080c`
- `ntoskrnl!ExReleaseResourceLite` at `0x180010873`
- `ntoskrnl!ExReleaseResourceLite` at `0x180010a7e`
- `ntoskrnl!ExReleaseResourceLite` at `0x180010767`
- `ntoskrnl!ExReleaseResourceLite` at `0x18001080c`
- `ntoskrnl!ExReleaseResourceLite` at `0x180010873`
- `ntoskrnl!ExReleaseResourceLite` at `0x180010a7e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180010391`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180010a0b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180010391`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180010a0b`
- `ntoskrnl!ObfDereferenceObject` at `0x1800109c7`
- `ntoskrnl!ObfDereferenceObject` at `0x180010b19`
- `ntoskrnl!ObfDereferenceObject` at `0x1800109c7`
- `ntoskrnl!ObfDereferenceObject` at `0x180010b19`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18001037c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800109f6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18001037c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800109f6`
- `FLTMGR!FltDeviceIoControlFile` at `0x18000ff50`
- `FLTMGR!FltDeviceIoControlFile` at `0x18000ff50`
- `FLTMGR!FltQuerySecurityObject` at `0x1800104f6`
- `FLTMGR!FltQuerySecurityObject` at `0x180010554`
- `FLTMGR!FltQuerySecurityObject` at `0x1800104f6`
- `FLTMGR!FltQuerySecurityObject` at `0x180010554`
- `FLTMGR!FltGetVolumeName` at `0x1800100de`
- `FLTMGR!FltGetVolumeName` at `0x1800102e7`
- `FLTMGR!FltGetVolumeName` at `0x1800100de`
- `FLTMGR!FltGetVolumeName` at `0x1800102e7`
- `FLTMGR!FltAllocateContext` at `0x1800101a8`
- `FLTMGR!FltAllocateContext` at `0x1800101a8`
- `FLTMGR!FltObjectReference` at `0x1800100ee`
- `FLTMGR!FltObjectReference` at `0x18001010b`
- `FLTMGR!FltObjectReference` at `0x1800100ee`
- `FLTMGR!FltObjectReference` at `0x18001010b`
- `FLTMGR!FltGetDiskDeviceObject` at `0x18000fd8d`
- `FLTMGR!FltGetDiskDeviceObject` at `0x18000fd8d`
- `FLTMGR!FltObjectDereference` at `0x180010124`
- `FLTMGR!FltObjectDereference` at `0x180010207`
- `FLTMGR!FltObjectDereference` at `0x180010217`
- `FLTMGR!FltObjectDereference` at `0x180010124`
- `FLTMGR!FltObjectDereference` at `0x180010207`
- `FLTMGR!FltObjectDereference` at `0x180010217`
- `FLTMGR!FltClose` at `0x180010b2d`
- `FLTMGR!FltClose` at `0x180010b2d`
- `FLTMGR!FltOpenVolume` at `0x18000fe3d`
- `FLTMGR!FltOpenVolume` at `0x18000fe3d`
- `FLTMGR!FltSetInstanceContext` at `0x18001032f`
- `FLTMGR!FltSetInstanceContext` at `0x18001032f`

## pseudocode

```c
__int64 __fastcall DepFSInstanceSetup(__int64 a1, __int64 a2, unsigned __int64 a3, int a4)
{
  char v4; // r14
  _QWORD *v6; // r15
  _QWORD *v7; // r13
  PFLT_FILTER *v8; // rdi
  int v9; // ebx
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  NTSTATUS v13; // eax
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  PDEVICE_OBJECT RealDevice; // rax
  ULONG *p_Flags; // rax
  ULONG OutputBufferLength; // r14d
  ULONG v19; // ebx
  __int64 v20; // r15
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rdx
  NTSTATUS v24; // eax
  struct _FLT_VOLUME *v25; // rcx
  PDEVICE_OBJECT v26; // rcx
  __int64 v27; // rdx
  char v28; // cl
  _QWORD *v29; // rax
  _QWORD *v30; // rax
  _QWORD *v31; // rax
  __int64 v32; // rdx
  unsigned int v33; // ecx
  __int64 v34; // r14
  __int64 Pool2; // rax
  __int64 v36; // r8
  _QWORD *v37; // r12
  _QWORD *v38; // rdx
  _QWORD *v39; // rax
  char *v40; // rcx
  PFLT_CONTEXT *v41; // rdx
  __int64 v42; // rcx
  unsigned int v43; // eax
  void *v44; // rax
  void *v45; // r15
  __int64 v46; // rax
  unsigned int v47; // eax
  PDEVICE_OBJECT v48; // rcx
  __int64 v49; // rdx
  _QWORD *v50; // rdx
  _QWORD *v51; // rax
  ULONG Characteristics; // eax
  _DWORD *v53; // r13
  unsigned int v54; // r15d
  _WORD *v55; // r14
  ULONG InputBufferLength[2]; // [rsp+28h] [rbp-39h]
  NTSTATUS SecurityObject; // [rsp+48h] [rbp-19h]
  PFLT_CONTEXT ReturnedContext; // [rsp+50h] [rbp-11h] BYREF
  char v60; // [rsp+58h] [rbp-9h]
  ULONG DeviceType; // [rsp+5Ch] [rbp-5h]
  ULONG LengthNeeded; // [rsp+60h] [rbp-1h] BYREF
  ULONG BufferSizeNeeded; // [rsp+64h] [rbp+3h] BYREF
  ULONG v64; // [rsp+68h] [rbp+7h]
  unsigned int v65; // [rsp+6Ch] [rbp+Bh]
  PDEVICE_OBJECT DiskDeviceObject; // [rsp+70h] [rbp+Fh] BYREF
  int InputBuffer; // [rsp+78h] [rbp+17h] BYREF
  ULONG LengthReturned; // [rsp+7Ch] [rbp+1Bh] BYREF
  PVOID P; // [rsp+80h] [rbp+1Fh]
  PFILE_OBJECT VolumeFileObject; // [rsp+88h] [rbp+27h] BYREF
  void *VolumeHandle; // [rsp+90h] [rbp+2Fh] BYREF
  unsigned int v73; // [rsp+D8h] [rbp+77h]

  v73 = a3;
  v4 = 0;
  ReturnedContext = 0;
  v6 = 0;
  DiskDeviceObject = 0;
  v7 = 0;
  VolumeHandle = 0;
  v8 = (PFLT_FILTER *)a1;
  VolumeFileObject = 0;
  InputBuffer = 0;
  P = 0;
  BufferSizeNeeded = 0;
  LengthReturned = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      WPP_6b5a76be7742304abc77e760f08b1d6f_Traceguids,
      *(_QWORD *)(a1 + 16),
      *(_QWORD *)(a1 + 24));
    a3 = v73;
  }
  v9 = -1071906801;
  if ( byte_180005194 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_171;
    }
    v11 = 11;
LABEL_170:
    WPP_SF_qq(v10->AttachedDevice, v11, WPP_6b5a76be7742304abc77e760f08b1d6f_Traceguids, v8[2], v8[3]);
LABEL_171:
    SecurityObject = -1071906801;
    goto LABEL_172;
  }
  if ( byte_180005195 || byte_180005196 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_171;
    }
    v11 = 12;
    goto LABEL_170;
  }
  if ( (unsigned int)(a4 - 2) <= 3 || a4 == 22 || (v60 = 0, a4 == 28) )
    v60 = 1;
  if ( (unsigned int)a3 <= 0x24 && (v12 = 0x100000018CLL, _bittest64(&v12, a3)) )
  {
    v13 = FltGetDiskDeviceObject(v8[2], &DiskDeviceObject);
    SecurityObject = v13;
    v9 = v13;
    if ( v13 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_172;
      }
      v15 = 13;
      InputBufferLength[0] = v13;
      goto LABEL_23;
    }
    LODWORD(a3) = v73;
    DeviceType = DiskDeviceObject->DeviceType;
    LengthNeeded = DiskDeviceObject->Characteristics;
  }
  else
  {
    DeviceType = 0;
    LengthNeeded = 0;
  }
  v64 = 0;
  v65 = 0;
  if ( (_DWORD)a3 == 20 || a4 == 27 )
    goto LABEL_52;
  if ( DiskDeviceObject )
    goto LABEL_36;
  SecurityObject = FltOpenVolume(v8[3], &VolumeHandle, &VolumeFileObject);
  v9 = SecurityObject;
  if ( SecurityObject < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_172;
    }
    v15 = 14;
    InputBufferLength[0] = SecurityObject;
    goto LABEL_23;
  }
  if ( DiskDeviceObject )
LABEL_36:
    RealDevice = DiskDeviceObject;
  else
    RealDevice = VolumeFileObject->Vpb->RealDevice;
  p_Flags = &RealDevice->Flags;
  OutputBufferLength = 72;
  v19 = *p_Flags >> 8;
  LOBYTE(v19) = BYTE1(*p_Flags) & 1;
  v64 = v19;
  do
  {
    if ( v6 )
    {
      v20 = v6[1];
      ExFreePoolWithTag(P, 0x72517044u);
      OutputBufferLength = v20;
      P = 0;
      if ( v20 != (unsigned int)v20 )
      {
        v9 = -1073741670;
        SecurityObject = -1073741670;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qi(WPP_GLOBAL_Control->AttachedDevice, v21, v22, v8[2], v20);
        }
        goto LABEL_172;
      }
    }
    P = (PVOID)ExAllocatePool2(256, OutputBufferLength, 1917939780);
    v6 = P;
    if ( !P )
    {
      v9 = -1073741670;
      SecurityObject = -1073741670;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_172;
      }
      v15 = 16;
      InputBufferLength[0] = OutputBufferLength;
LABEL_23:
      WPP_SF_qD(
        v14->AttachedDevice,
        v15,
        WPP_6b5a76be7742304abc77e760f08b1d6f_Traceguids,
        v8[2],
        *(_QWORD *)InputBufferLength);
      goto LABEL_172;
    }
    InputBuffer = 3;
    if ( DiskDeviceObject )
    {
      InputBufferLength[1] = HIDWORD(P);
      v24 = DepFSSendIoctl(DiskDeviceObject, v23, &InputBuffer);
    }
    else
    {
      v24 = FltDeviceIoControlFile(
              v8[3],
              VolumeFileObject,
              0x2D118Cu,
              &InputBuffer,
              4u,
              P,
              OutputBufferLength,
              &LengthReturned);
    }
  }
  while ( v24 == -2147483643 );
  if ( v24 >= 0 )
  {
    v65 = *((_DWORD *)v6 + 1);
    v64 = v19;
  }
  else
  {
    *((_DWORD *)v6 + 1) = 0;
    if ( v24 != -1073741808
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      InputBufferLength[0] = v24;
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        17,
        WPP_6b5a76be7742304abc77e760f08b1d6f_Traceguids,
        v8[2],
        *(_QWORD *)InputBufferLength);
    }
  }
  v4 = v64;
LABEL_52:
  if ( a4 == 1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_6b5a76be7742304abc77e760f08b1d6f_Traceguids, v8[2], v8[3]);
    }
    v9 = -1071906801;
    goto LABEL_58;
  }
  v25 = v8[2];
  BufferSizeNeeded = 0;
  FltGetVolumeName(v25, 0, &BufferSizeNeeded);
  SecurityObject = FltObjectReference(v8[2]);
  v9 = SecurityObject;
  if ( SecurityObject >= 0 )
  {
    SecurityObject = FltObjectReference(v8[3]);
    v9 = SecurityObject;
    if ( SecurityObject < 0 )
    {
      FltObjectDereference(v8[2]);
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v27 = 19;
        goto LABEL_74;
      }
      goto LABEL_172;
    }
    SecurityObject = FltAllocateContext(v8[1], 2u, BufferSizeNeeded + 152LL, PagedPool, &ReturnedContext);
    v9 = SecurityObject;
    if ( SecurityObject < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqD(
          WPP_GLOBAL_Control->AttachedDevice,
          21,
          WPP_6b5a76be7742304abc77e760f08b1d6f_Traceguids,
          v8[2],
          v8[3],
          SecurityObject);
      }
      FltObjectDereference(v8[3]);
      FltObjectDereference(v8[2]);
      goto LABEL_172;
    }
    memset(ReturnedContext, 0, 0x98u);
    *(_WORD *)ReturnedContext = 12320;
    *((_WORD *)ReturnedContext + 1) = 152;
    *((_QWORD *)ReturnedContext + 8) = v8[3];
    *((_QWORD *)ReturnedContext + 9) = v8[2];
    _InterlockedIncrement((volatile signed __int32 *)ReturnedContext + 29);
    v28 = v60;
    *((_DWORD *)ReturnedContext + 20) = a4;
    *((_BYTE *)ReturnedContext + 92) = v28;
    *((_DWORD *)ReturnedContext + 28) = LengthNeeded;
    *((_DWORD *)ReturnedContext + 22) = DeviceType;
    *((_DWORD *)ReturnedContext + 21) = v73;
    *((_QWORD *)ReturnedContext + 17) = (char *)ReturnedContext + 144;
    *((_WORD *)ReturnedContext + 64) = 0;
    *((_WORD *)ReturnedContext + 65) = BufferSizeNeeded;
    if ( v4 )
      *((_DWORD *)ReturnedContext + 14) |= 2u;
    FltGetVolumeName(v8[2], (PUNICODE_STRING)ReturnedContext + 8, &BufferSizeNeeded);
    v29 = (char *)ReturnedContext + 24;
    *((_QWORD *)ReturnedContext + 4) = (char *)ReturnedContext + 24;
    *v29 = v29;
    v30 = (char *)ReturnedContext + 40;
    *((_QWORD *)ReturnedContext + 6) = (char *)ReturnedContext + 40;
    *v30 = v30;
    v31 = (char *)ReturnedContext + 8;
    *((_QWORD *)ReturnedContext + 2) = (char *)ReturnedContext + 8;
    *v31 = v31;
    SecurityObject = FltSetInstanceContext(v8[3], FLT_SET_CONTEXT_KEEP_IF_EXISTS, ReturnedContext, 0);
    v9 = SecurityObject;
    if ( SecurityObject < 0 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v27 = 22;
        goto LABEL_74;
      }
      goto LABEL_172;
    }
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&Resource, 1u);
    if ( !v65 )
      goto LABEL_146;
    LODWORD(v32) = 0;
    v33 = 0;
    DeviceType = 0;
    v65 = 0;
    if ( !*((_DWORD *)v6 + 1) )
      goto LABEL_146;
    while ( 1 )
    {
      v34 = v6[6 * v33 + 6];
      if ( !v34 || *(_WORD *)v34 != 12336 || (*(_DWORD *)(v34 + 92) & 0x10) != 0 )
        break;
      Pool2 = ExAllocatePool2(256, 56, 1817210948);
      v37 = (_QWORD *)Pool2;
      if ( !Pool2 )
      {
        v9 = -1073741670;
        SecurityObject = -1073741670;
        v48 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v49 = 24;
LABEL_143:
          WPP_SF_qqD(
            v48->AttachedDevice,
            v49,
            WPP_6b5a76be7742304abc77e760f08b1d6f_Traceguids,
            v8[2],
            v8[3],
            -1073741670);
        }
LABEL_144:
        ExReleaseResourceLite(&Resource);
        KeLeaveCriticalRegion();
        goto LABEL_172;
      }
      *(_DWORD *)Pool2 = 3682384;
      *(_QWORD *)(Pool2 + 8) = v34;
      v38 = *(_QWORD **)(v34 + 32);
      if ( *v38 != v34 + 24 )
        goto LABEL_147;
      *(_QWORD *)(Pool2 + 48) = v38;
      v39 = (_QWORD *)(Pool2 + 40);
      *v39 = v34 + 24;
      *v38 = v39;
      *(_QWORD *)(v34 + 32) = v39;
      v37[2] = ReturnedContext;
      v40 = (char *)ReturnedContext + 24;
      v41 = (PFLT_CONTEXT *)*((_QWORD *)ReturnedContext + 4);
      if ( *v41 != (char *)ReturnedContext + 24 )
        goto LABEL_147;
      v37[3] = v40;
      v37[4] = v41;
      *v41 = v37 + 3;
      *((_QWORD *)v40 + 1) = v37 + 3;
      if ( *(_QWORD *)(v34 + 168) )
      {
        if ( *(_DWORD *)(v34 + 176) )
        {
          if ( !v7 )
          {
            ++*(_DWORD *)(v34 + 56);
            v7 = (_QWORD *)v34;
            *(_DWORD *)(v34 + 92) |= 0x100u;
            LengthNeeded = 0;
            if ( DiskDeviceObject )
            {
              v42 = *(_QWORD *)(v34 + 112);
              if ( v42 )
              {
                v43 = FltQuerySecurityObject(
                        *(PFLT_INSTANCE *)(v42 + 64),
                        *(PFILE_OBJECT *)(v34 + 104),
                        0x1FFu,
                        0,
                        0,
                        &LengthNeeded);
                v36 = v43;
                if ( v43 == -1073741789 )
                {
                  v44 = (void *)ExAllocatePool2(256, LengthNeeded, 1933865028);
                  v45 = v44;
                  if ( !v44 )
                  {
                    v9 = -1073741670;
                    SecurityObject = -1073741670;
                    v48 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                    {
                      v49 = 25;
                      goto LABEL_143;
                    }
                    goto LABEL_144;
                  }
                  SecurityObject = FltQuerySecurityObject(
                                     *(PFLT_INSTANCE *)(*(_QWORD *)(v34 + 112) + 64LL),
                                     *(PFILE_OBJECT *)(v34 + 104),
                                     0x1FFu,
                                     v44,
                                     LengthNeeded,
                                     0);
                  v9 = SecurityObject;
                  if ( SecurityObject < 0 )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                    {
                      WPP_SF_qqD(
                        WPP_GLOBAL_Control->AttachedDevice,
                        26,
                        WPP_6b5a76be7742304abc77e760f08b1d6f_Traceguids,
                        v8[2],
                        v8[3],
                        SecurityObject);
                    }
                    ExFreePoolWithTag(v45, 0x73447044u);
                    ExReleaseResourceLite(&Resource);
                    KeLeaveCriticalRegion();
                    goto LABEL_172;
                  }
                  *((_QWORD *)ReturnedContext + 15) = v45;
                  v6 = P;
                }
                else
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                  {
                    WPP_SF_qqD(
                      WPP_GLOBAL_Control->AttachedDevice,
                      27,
                      WPP_6b5a76be7742304abc77e760f08b1d6f_Traceguids,
                      v8[2],
                      v8[3],
                      v43);
                  }
                  v9 = 0;
                }
              }
            }
          }
        }
      }
      v32 = ++DeviceType;
      if ( (_BYTE)v64 )
      {
        *(_DWORD *)(v34 + 60) |= 0x10u;
        v46 = *(_QWORD *)(v34 + 112);
        if ( v46 )
          *(_DWORD *)(v46 + 56) |= 2u;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qqqqq(WPP_GLOBAL_Control->AttachedDevice, v32, v36, v8[2], v8[3], v37, ReturnedContext, v34);
LABEL_121:
        LODWORD(v32) = DeviceType;
      }
LABEL_122:
      v47 = *((_DWORD *)v6 + 1);
      v33 = v65 + 1;
      v65 = v33;
      if ( v33 >= v47 )
      {
        if ( !v47 || (_DWORD)v32 )
        {
          SecurityObject = v9;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_qqq(
              WPP_GLOBAL_Control->AttachedDevice,
              29,
              WPP_6b5a76be7742304abc77e760f08b1d6f_Traceguids,
              v8[2],
              v8[3],
              ReturnedContext);
          }
          SecurityObject = v9;
        }
LABEL_146:
        v50 = (_QWORD *)qword_1800051A8;
        if ( *(__int64 **)qword_1800051A8 != &qword_1800051A0 )
LABEL_147:
          __fastfail(3u);
        v51 = (char *)ReturnedContext + 40;
        *((_QWORD *)ReturnedContext + 6) = qword_1800051A8;
        *v51 = &qword_1800051A0;
        *v50 = v51;
        ++dword_180005190;
        qword_1800051A8 = (__int64)v51;
        ExReleaseResourceLite(&Resource);
        KeLeaveCriticalRegion();
        if ( !v7 || !DiskDeviceObject )
          goto LABEL_172;
        SecurityObject = ObSetSecurityObjectByPointer(DiskDeviceObject, 20, v7[21]);
        v9 = SecurityObject;
        if ( SecurityObject >= 0 )
        {
          Characteristics = DiskDeviceObject->Characteristics;
          if ( (Characteristics & 0x100) == 0 )
            DiskDeviceObject->Characteristics = Characteristics | 0x100;
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            v27 = 30;
            goto LABEL_74;
          }
          goto LABEL_172;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqD(
            WPP_GLOBAL_Control->AttachedDevice,
            31,
            WPP_6b5a76be7742304abc77e760f08b1d6f_Traceguids,
            v8[2],
            v8[3],
            SecurityObject);
        }
        v9 = 0;
LABEL_58:
        SecurityObject = v9;
        goto LABEL_172;
      }
    }
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      goto LABEL_122;
    }
    WPP_SF_qqq(
      WPP_GLOBAL_Control->AttachedDevice,
      23,
      WPP_6b5a76be7742304abc77e760f08b1d6f_Traceguids,
      v8[2],
      v8[3],
      v34);
    goto LABEL_121;
  }
  v26 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v27 = 20;
LABEL_74:
    WPP_SF_qqD(v26->AttachedDevice, v27, WPP_6b5a76be7742304abc77e760f08b1d6f_Traceguids, v8[2], v8[3], v9);
  }
LABEL_172:
  if ( DiskDeviceObject )
  {
    ObfDereferenceObject(DiskDeviceObject);
    DiskDeviceObject = 0;
  }
  if ( v7 )
    DereferenceDependencyContext(v7);
  v53 = P;
  if ( P )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&Resource, 1u);
    v54 = 0;
    if ( v53[1] )
    {
      do
      {
        v55 = *(_WORD **)&v53[12 * v54 + 12];
        if ( v55 && *v55 == 12336 )
        {
          if ( v73 - 7 <= 1 || v73 == 36 )
            DepFSDecrementActiveMountCount(*(_QWORD *)&v53[12 * v54 + 12]);
          DereferenceDependencyContext(v55);
        }
        ++v54;
      }
      while ( v54 < v53[1] );
      v9 = SecurityObject;
      v8 = (PFLT_FILTER *)a1;
    }
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
    ExFreePoolWithTag(v53, 0x72517044u);
  }
  else if ( v73 - 7 <= 1 || v73 == 36 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_6b5a76be7742304abc77e760f08b1d6f_Traceguids, v8[2], v8[3]);
    }
    KeSetEvent(&Event, 0, 0);
  }
  if ( VolumeHandle )
  {
    ObfDereferenceObject(VolumeFileObject);
    VolumeFileObject = 0;
    FltClose(VolumeHandle);
    VolumeHandle = 0;
  }
  if ( ReturnedContext )
    DereferenceVolumeContext();
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_6b5a76be7742304abc77e760f08b1d6f_Traceguids, v8[2], v8[3]);
    }
    return (unsigned int)-1071906801;
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_6b5a76be7742304abc77e760f08b1d6f_Traceguids, v8[2], v8[3]);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000fc50  mov     rax, rsp
0x18000fc53  mov     [rax+10h], rbx
0x18000fc57  mov     [rax+20h], rdi
0x18000fc5b  mov     [rax+18h], r8d
0x18000fc5f  mov     [rax+8], rcx
0x18000fc63  push    rbp
0x18000fc64  push    r12
0x18000fc66  push    r13
0x18000fc68  push    r14
0x18000fc6a  push    r15
0x18000fc6c  lea     rbp, [rax-5Fh]
0x18000fc70  sub     rsp, 90h
0x18000fc77  xor     r14d, r14d
0x18000fc7a  mov     r12d, r9d
0x18000fc7d  mov     [rbp+57h+ReturnedContext], r14
0x18000fc81  mov     r15d, r14d
0x18000fc84  mov     [rbp+57h+DiskDeviceObject], r14
0x18000fc88  mov     r13d, r14d
0x18000fc8b  mov     [rbp+57h+VolumeHandle], r14
0x18000fc8f  mov     rdi, rcx
0x18000fc92  mov     [rbp+57h+VolumeFileObject], r14
0x18000fc96  mov     [rbp+57h+InputBuffer], r14d
0x18000fc9a  mov     [rbp+57h+P], r14
0x18000fc9e  mov     [rbp+57h+BufferSizeNeeded], r14d
0x18000fca2  mov     [rbp+57h+var_3C], r14d
0x18000fca6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fcad  lea     rax, WPP_GLOBAL_Control
0x18000fcb4  cmp     rcx, rax
0x18000fcb7  jz      short loc_18000FCF2
0x18000fcb9  mov     eax, [rcx+2Ch]
0x18000fcbc  test    al, 4
0x18000fcbe  jz      short loc_18000FCEB
0x18000fcc0  cmp     byte ptr [rcx+29h], 4
0x18000fcc4  jb      short loc_18000FCEB
0x18000fcc6  mov     rax, [rdi+18h]
0x18000fcca  lea     edx, [r14+0Ah]
0x18000fcce  mov     r9, [rdi+10h]
0x18000fcd2  lea     r8, WPP_6b5a76be7742304abc77e760f08b1d6f_Traceguids
0x18000fcd9  mov     rcx, [rcx+18h]
0x18000fcdd  mov     qword ptr [rsp+0B0h+InputBufferLength], rax
0x18000fce2  call    WPP_SF_qq
0x18000fce7  mov     r8d, [rbp+57h+arg_10]
0x18000fceb  lea     rax, WPP_GLOBAL_Control
0x18000fcf2  cmp     cs:byte_180005194, r14b
0x18000fcf9  mov     ebx, 0C01C000Fh
0x18000fcfe  jz      short loc_18000FD2F
0x18000fd00  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd07  cmp     rcx, rax
0x18000fd0a  jz      loc_1800109B1
0x18000fd10  mov     eax, [rcx+2Ch]
0x18000fd13  test    al, 1
0x18000fd15  jz      loc_1800109B1
0x18000fd1b  cmp     byte ptr [rcx+29h], 2
0x18000fd1f  jb      loc_1800109B1
0x18000fd25  mov     edx, 0Bh
0x18000fd2a  jmp     loc_180010994
0x18000fd2f  cmp     cs:byte_180005195, r14b
0x18000fd36  jnz     loc_180010976
0x18000fd3c  cmp     cs:byte_180005196, r14b
0x18000fd43  jnz     loc_180010976
0x18000fd49  lea     eax, [r12-2]
0x18000fd4e  cmp     eax, 3
0x18000fd51  jbe     short loc_18000FD63
0x18000fd53  cmp     r12d, 16h
0x18000fd57  jz      short loc_18000FD63
0x18000fd59  mov     [rbp+57h+var_60], r14b
0x18000fd5d  cmp     r12d, 1Ch
0x18000fd61  jnz     short loc_18000FD67
0x18000fd63  mov     [rbp+57h+var_60], 1
0x18000fd67  cmp     r8d, 24h ; '$'
0x18000fd6b  ja      loc_18000FE07
0x18000fd71  mov     rcx, 100000018Ch
0x18000fd7b  bt      rcx, r8
0x18000fd7f  jnb     loc_18000FE07
0x18000fd85  mov     rcx, [rdi+10h]; Volume
0x18000fd89  lea     rdx, [rbp+57h+DiskDeviceObject]; DiskDeviceObject
0x18000fd8d  call    cs:__imp_FltGetDiskDeviceObject
0x18000fd94  nop     dword ptr [rax+rax+00h]
0x18000fd99  mov     [rbp+57h+var_70], eax
0x18000fd9c  mov     ebx, eax
0x18000fd9e  test    eax, eax
0x18000fda0  jns     short loc_18000FDF1
0x18000fda2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fda9  lea     r15, WPP_GLOBAL_Control
0x18000fdb0  cmp     rcx, r15
0x18000fdb3  jz      loc_1800109BB
0x18000fdb9  mov     edx, [rcx+2Ch]
0x18000fdbc  test    dl, 1
0x18000fdbf  jz      loc_1800109BB
0x18000fdc5  cmp     byte ptr [rcx+29h], 2
0x18000fdc9  jb      loc_1800109BB
0x18000fdcf  mov     edx, 0Dh
0x18000fdd4  mov     [rsp+0B0h+InputBufferLength], eax
0x18000fdd8  mov     r9, [rdi+10h]
0x18000fddc  lea     r8, WPP_6b5a76be7742304abc77e760f08b1d6f_Traceguids
0x18000fde3  mov     rcx, [rcx+18h]
0x18000fde7  call    WPP_SF_qD
0x18000fdec  jmp     loc_1800109BB
0x18000fdf1  mov     rcx, [rbp+57h+DiskDeviceObject]
0x18000fdf5  mov     r8d, [rbp+57h+arg_10]
0x18000fdf9  mov     eax, [rcx+48h]
0x18000fdfc  mov     [rbp+57h+var_5C], eax
0x18000fdff  mov     eax, [rcx+34h]
0x18000fe02  mov     [rbp+57h+LengthNeeded], eax
0x18000fe05  jmp     short loc_18000FE0F
0x18000fe07  mov     [rbp+57h+var_5C], r14d
0x18000fe0b  mov     [rbp+57h+LengthNeeded], r14d
0x18000fe0f  mov     [rbp+57h+var_50], r14d
0x18000fe13  mov     [rbp+57h+var_4C], r13d
0x18000fe17  cmp     r8d, 14h
0x18000fe1b  jz      loc_18000FFD9
0x18000fe21  cmp     r12d, 1Bh
0x18000fe25  jz      loc_18000FFD9
0x18000fe2b  cmp     [rbp+57h+DiskDeviceObject], r14
0x18000fe2f  jnz     short loc_18000FEA0
0x18000fe31  mov     rcx, [rdi+18h]; Instance
0x18000fe35  lea     r8, [rbp+57h+VolumeFileObject]; VolumeFileObject
0x18000fe39  lea     rdx, [rbp+57h+VolumeHandle]; VolumeHandle
0x18000fe3d  call    cs:__imp_FltOpenVolume
0x18000fe44  nop     dword ptr [rax+rax+00h]
0x18000fe49  mov     [rbp+57h+var_70], eax
0x18000fe4c  mov     ebx, eax
0x18000fe4e  test    eax, eax
0x18000fe50  jns     short loc_18000FE8C
0x18000fe52  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe59  lea     r15, WPP_GLOBAL_Control
0x18000fe60  cmp     rcx, r15
0x18000fe63  jz      loc_1800109BB
0x18000fe69  mov     eax, [rcx+2Ch]
0x18000fe6c  test    al, 1
0x18000fe6e  jz      loc_1800109BB
0x18000fe74  cmp     byte ptr [rcx+29h], 2
0x18000fe78  jb      loc_1800109BB
0x18000fe7e  mov     edx, 0Eh
0x18000fe83  mov     [rsp+0B0h+InputBufferLength], ebx
0x18000fe87  jmp     loc_18000FDD8
0x18000fe8c  cmp     [rbp+57h+DiskDeviceObject], r14
0x18000fe90  jnz     short loc_18000FEA0
0x18000fe92  mov     rax, [rbp+57h+VolumeFileObject]
0x18000fe96  mov     rcx, [rax+10h]
0x18000fe9a  mov     rax, [rcx+10h]
0x18000fe9e  jmp     short loc_18000FEA4
0x18000fea0  mov     rax, [rbp+57h+DiskDeviceObject]
0x18000fea4  add     rax, 30h ; '0'
0x18000fea8  mov     r14d, 48h ; 'H'
0x18000feae  mov     ebx, [rax]
0x18000feb0  shr     ebx, 8
0x18000feb3  and     bl, 1
0x18000feb6  mov     [rbp+57h+var_50], ebx
0x18000feb9  test    r15, r15
0x18000febc  jz      short loc_18000FEE9
0x18000febe  mov     rcx, [rbp+57h+P]; P
0x18000fec2  mov     edx, 72517044h; Tag
0x18000fec7  mov     r15, [r15+8]
0x18000fecb  call    cs:__imp_ExFreePoolWithTag
0x18000fed2  nop     dword ptr [rax+rax+00h]
0x18000fed7  xor     ecx, ecx
0x18000fed9  mov     r14d, r15d
0x18000fedc  mov     [rbp+57h+P], rcx
0x18000fee0  cmp     r15, r14
0x18000fee3  jnz     loc_180010033
0x18000fee9  mov     edx, r14d
0x18000feec  mov     ecx, 100h
0x18000fef1  mov     r8d, 72517044h
0x18000fef7  call    cs:__imp_ExAllocatePool2
0x18000fefe  nop     dword ptr [rax+rax+00h]
0x18000ff03  mov     [rbp+57h+P], rax
0x18000ff07  mov     r15, rax
0x18000ff0a  test    rax, rax
0x18000ff0d  jz      loc_18001008D
0x18000ff13  mov     rcx, [rbp+57h+DiskDeviceObject]
0x18000ff17  lea     rax, [rbp+57h+var_3C]
0x18000ff1b  mov     [rbp+57h+InputBuffer], 3
0x18000ff22  test    rcx, rcx
0x18000ff25  jnz     short loc_18000FF5E
0x18000ff27  mov     rdx, [rbp+57h+VolumeFileObject]; FileObject
0x18000ff2b  lea     r9, [rbp+57h+InputBuffer]; InputBuffer
0x18000ff2f  mov     rcx, [rdi+18h]; Instance
0x18000ff33  mov     r8d, 2D118Ch; IoControlCode
0x18000ff39  mov     [rsp+0B0h+LengthReturned], rax; LengthReturned
0x18000ff3e  mov     [rsp+0B0h+OutputBufferLength], r14d; OutputBufferLength
0x18000ff43  mov     [rsp+0B0h+OutputBuffer], r15; OutputBuffer
0x18000ff48  mov     [rsp+0B0h+InputBufferLength], 4; InputBufferLength
0x18000ff50  call    cs:__imp_FltDeviceIoControlFile
0x18000ff57  nop     dword ptr [rax+rax+00h]
0x18000ff5c  jmp     short loc_18000FF76
0x18000ff5e  mov     qword ptr [rsp+0B0h+OutputBufferLength], rax
0x18000ff63  lea     r8, [rbp+57h+InputBuffer]
0x18000ff67  mov     dword ptr [rsp+0B0h+OutputBuffer], r14d
0x18000ff6c  mov     qword ptr [rsp+0B0h+InputBufferLength], r15
0x18000ff71  call    DepFSSendIoctl
0x18000ff76  mov     ecx, eax
0x18000ff78  cmp     eax, 80000005h
0x18000ff7d  jz      loc_18000FEB9
0x18000ff83  test    eax, eax
0x18000ff85  jns     loc_18001007E
0x18000ff8b  mov     [r15+4], r13d
0x18000ff8f  cmp     eax, 0C0000010h
0x18000ff94  jz      short loc_18000FFD5
0x18000ff96  mov     r10, cs:WPP_GLOBAL_Control
0x18000ff9d  lea     rax, WPP_GLOBAL_Control
0x18000ffa4  cmp     r10, rax
0x18000ffa7  jz      short loc_18000FFD5
0x18000ffa9  mov     eax, [r10+2Ch]
0x18000ffad  test    al, 1
0x18000ffaf  jz      short loc_18000FFD5
0x18000ffb1  cmp     byte ptr [r10+29h], 2
0x18000ffb6  jb      short loc_18000FFD5
0x18000ffb8  mov     r9, [rdi+10h]
0x18000ffbc  lea     r8, WPP_6b5a76be7742304abc77e760f08b1d6f_Traceguids
0x18000ffc3  mov     [rsp+0B0h+InputBufferLength], ecx
0x18000ffc7  mov     edx, 11h
0x18000ffcc  mov     rcx, [r10+18h]
0x18000ffd0  call    WPP_SF_qD
0x18000ffd5  mov     r14d, [rbp+57h+var_50]
0x18000ffd9  cmp     r12d, 1
0x18000ffdd  jnz     loc_1800100D0
0x18000ffe3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ffea  lea     r15, WPP_GLOBAL_Control
0x18000fff1  cmp     rcx, r15
0x18000fff4  jz      short loc_180010026
0x18000fff6  mov     eax, [rcx+2Ch]
0x18000fff9  test    r12b, al
0x18000fffc  jz      short loc_180010026
0x18000fffe  cmp     byte ptr [rcx+29h], 2
0x180010002  jb      short loc_180010026
0x180010004  mov     rax, [rdi+18h]
0x180010008  lea     edx, [r12+11h]
0x18001000d  mov     r9, [rdi+10h]
0x180010011  lea     r8, WPP_6b5a76be7742304abc77e760f08b1d6f_Traceguids
0x180010018  mov     rcx, [rcx+18h]
0x18001001c  mov     qword ptr [rsp+0B0h+InputBufferLength], rax
0x180010021  call    WPP_SF_qq
0x180010026  mov     ebx, 0C01C000Fh
0x18001002b  mov     [rbp+57h+var_70], ebx
0x18001002e  jmp     loc_1800109BB
0x180010033  mov     ebx, 0C000009Ah
0x180010038  mov     [rbp+57h+var_70], ebx
0x18001003b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010042  lea     rax, WPP_GLOBAL_Control
0x180010049  cmp     rcx, rax
0x18001004c  jz      loc_1800109B4
0x180010052  mov     eax, [rcx+2Ch]
0x180010055  test    al, 1
0x180010057  jz      loc_1800109B4
0x18001005d  cmp     byte ptr [rcx+29h], 2
0x180010061  jb      loc_1800109B4
0x180010067  mov     r9, [rdi+10h]
0x18001006b  mov     rcx, [rcx+18h]
0x18001006f  mov     qword ptr [rsp+0B0h+InputBufferLength], r15
0x180010074  call    WPP_SF_qi
0x180010079  jmp     loc_1800109B4
0x18001007e  mov     eax, [r15+4]
0x180010082  mov     [rbp+57h+var_4C], eax
0x180010085  mov     [rbp+57h+var_50], ebx
0x180010088  jmp     loc_18000FFD5
0x18001008d  mov     ebx, 0C000009Ah
0x180010092  mov     [rbp+57h+var_70], ebx
0x180010095  mov     rcx, cs:WPP_GLOBAL_Control
0x18001009c  lea     r15, WPP_GLOBAL_Control
0x1800100a3  cmp     rcx, r15
0x1800100a6  jz      loc_1800109BB
0x1800100ac  mov     eax, [rcx+2Ch]
0x1800100af  test    al, 1
0x1800100b1  jz      loc_1800109BB
0x1800100b7  cmp     byte ptr [rcx+29h], 2
0x1800100bb  jb      loc_1800109BB
0x1800100c1  mov     edx, 10h
0x1800100c6  mov     [rsp+0B0h+InputBufferLength], r14d
0x1800100cb  jmp     loc_18000FDD8
0x1800100d0  mov     rcx, [rdi+10h]; Volume
0x1800100d4  lea     r8, [rbp+57h+BufferSizeNeeded]; BufferSizeNeeded
0x1800100d8  xor     edx, edx; VolumeName
0x1800100da  mov     [rbp+57h+BufferSizeNeeded], r13d
0x1800100de  call    cs:__imp_FltGetVolumeName
0x1800100e5  nop     dword ptr [rax+rax+00h]
0x1800100ea  mov     rcx, [rdi+10h]; FltObject
0x1800100ee  call    cs:__imp_FltObjectReference
0x1800100f5  nop     dword ptr [rax+rax+00h]
0x1800100fa  mov     [rbp+57h+var_70], eax
0x1800100fd  mov     ebx, eax
0x1800100ff  test    eax, eax
0x180010101  js      loc_18001094C
0x180010107  mov     rcx, [rdi+18h]; FltObject
0x18001010b  call    cs:__imp_FltObjectReference
0x180010112  nop     dword ptr [rax+rax+00h]
0x180010117  mov     [rbp+57h+var_70], eax
0x18001011a  mov     ebx, eax
0x18001011c  test    eax, eax
0x18001011e  jns     short loc_180010187
0x180010120  mov     rcx, [rdi+10h]; FltObject
0x180010124  call    cs:__imp_FltObjectDereference
0x18001012b  nop     dword ptr [rax+rax+00h]
0x180010130  mov     rcx, cs:WPP_GLOBAL_Control
0x180010137  lea     r15, WPP_GLOBAL_Control
0x18001013e  cmp     rcx, r15
0x180010141  jz      loc_1800109BB
0x180010147  mov     eax, [rcx+2Ch]
0x18001014a  test    al, 1
0x18001014c  jz      loc_1800109BB
  ... truncated ...
```
