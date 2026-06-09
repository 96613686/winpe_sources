# FltpEnumerateFileSystemVolumes

- ea: `0x180068900`
- end: `0x180068e20`
- name: `FltpEnumerateFileSystemVolumes`
- size: `1312`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject)`
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callers

- `0x1800674b0`

## callees

- `0x180002740`
- `0x180009f20`
- `0x18004dcc0`
- `0x1800552c0`
- `0x18005c5a0`
- `0x180067030`
- `0x180067a50`
- `0x180067b00`
- `0x180067be0`
- `0x1800682b0`
- `0x180068420`
- `0x1800688d0`
- `0x180068900`
- `0x180069170`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x180068bdf`
- `ntoskrnl!ExReleaseFastMutex` at `0x180068d40`
- `ntoskrnl!ExReleaseFastMutex` at `0x180068bdf`
- `ntoskrnl!ExReleaseFastMutex` at `0x180068d40`
- `ntoskrnl!ExAcquireFastMutex` at `0x180068ba0`
- `ntoskrnl!ExAcquireFastMutex` at `0x180068ba0`
- `ntoskrnl!ExFreePoolWithTag` at `0x180068de9`
- `ntoskrnl!ExFreePoolWithTag` at `0x180068de9`
- `ntoskrnl!ExAllocatePool2` at `0x1800689d7`
- `ntoskrnl!ExAllocatePool2` at `0x1800689d7`
- `ntoskrnl!ObfDereferenceObject` at `0x1800689ee`
- `ntoskrnl!ObfDereferenceObject` at `0x180068d66`
- `ntoskrnl!ObfDereferenceObject` at `0x180068d76`
- `ntoskrnl!ObfDereferenceObject` at `0x180068db2`
- `ntoskrnl!ObfDereferenceObject` at `0x1800689ee`
- `ntoskrnl!ObfDereferenceObject` at `0x180068d66`
- `ntoskrnl!ObfDereferenceObject` at `0x180068d76`
- `ntoskrnl!ObfDereferenceObject` at `0x180068db2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18006892e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18006892e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180068a0c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180068dd0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180068a0c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180068dd0`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x180068988`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x180068988`
- `ntoskrnl!IoGetStackLimits` at `0x180068c5e`
- `ntoskrnl!IoGetStackLimits` at `0x180068cc6`
- `ntoskrnl!IoGetStackLimits` at `0x180068c5e`
- `ntoskrnl!IoGetStackLimits` at `0x180068cc6`
- `ntoskrnl!IoEnumerateDeviceObjectList` at `0x1800689a4`
- `ntoskrnl!IoEnumerateDeviceObjectList` at `0x180068a39`
- `ntoskrnl!IoEnumerateDeviceObjectList` at `0x1800689a4`
- `ntoskrnl!IoEnumerateDeviceObjectList` at `0x180068a39`
- `ntoskrnl!IoGetDiskDeviceObject` at `0x180068ace`
- `ntoskrnl!IoGetDiskDeviceObject` at `0x180068ace`

## pseudocode

```c
__int64 __fastcall FltpEnumerateFileSystemVolumes(PDEVICE_OBJECT DeviceObject)
{
  _QWORD *DeviceExtension; // rsi
  _WORD *v3; // rax
  _WORD *v4; // rdi
  PDEVICE_OBJECT *v6; // r15
  PDEVICE_OBJECT DeviceAttachmentBaseRef; // r13
  unsigned int v8; // ebx
  PDEVICE_OBJECT *Pool2; // rax
  ULONG v10; // ebx
  PVOID *v11; // r12
  struct _DEVICE_OBJECT *v12; // rdx
  NTSTATUS v13; // eax
  int ObjectName; // ebx
  unsigned __int16 *v15; // r9
  PDEVICE_OBJECT v16; // rbx
  int v17; // r14d
  __int64 v18; // r8
  __int64 v19; // rbx
  int UniqueIdentifierForObject; // eax
  __int64 v21; // r8
  unsigned __int64 HighLimit; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int64 LowLimit; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int64 v24[3]; // [rsp+50h] [rbp-30h] BYREF
  ULONG ActualNumberDeviceObjects; // [rsp+B0h] [rbp+30h] BYREF
  ULONG v26; // [rsp+B8h] [rbp+38h]
  PDEVICE_OBJECT DiskDeviceObject; // [rsp+C0h] [rbp+40h] BYREF
  PDEVICE_OBJECT SourceDevice; // [rsp+C8h] [rbp+48h] BYREF

  DeviceExtension = DeviceObject->DeviceExtension;
  SourceDevice = 0;
  DiskDeviceObject = 0;
  ActualNumberDeviceObjects = 0;
  v3 = ExAllocateFromNPagedLookasideList(&stru_18003EDC0);
  v4 = v3;
  if ( !v3 )
    return 3221225626LL;
  *((_DWORD *)v3 + 4) = 0;
  *((_DWORD *)v3 + 6) = 0;
  *((_DWORD *)v3 + 5) = 254;
  *(_OWORD *)v3 = 0;
  v3[1] = 254;
  v6 = 0;
  *((_QWORD *)v3 + 1) = v3 + 14;
  DeviceAttachmentBaseRef = IoGetDeviceAttachmentBaseRef(DeviceObject);
  v8 = IoEnumerateDeviceObjectList(DeviceAttachmentBaseRef->DriverObject, 0, 0, &ActualNumberDeviceObjects);
  if ( v8 != -1073741789 )
  {
LABEL_44:
    FltpDbgStatus(v8);
    goto LABEL_45;
  }
  ActualNumberDeviceObjects += 8;
  Pool2 = (PDEVICE_OBJECT *)ExAllocatePool2(64, 8LL * ActualNumberDeviceObjects, 1818512710);
  v6 = Pool2;
  if ( !Pool2 )
  {
    ObfDereferenceObject(DeviceAttachmentBaseRef);
    FltpCleanupNameControl((__int64)v4);
    ExFreeToNPagedLookasideList(&stru_18003EDC0, v4);
    return 3221225626LL;
  }
  v8 = IoEnumerateDeviceObjectList(
         DeviceAttachmentBaseRef->DriverObject,
         Pool2,
         8 * ActualNumberDeviceObjects,
         &ActualNumberDeviceObjects);
  if ( (int)FltpDbgStatus(v8) >= 0 )
  {
    v10 = 0;
    v26 = 0;
    if ( ActualNumberDeviceObjects )
    {
      while ( 1 )
      {
        v11 = (PVOID *)&v6[v10];
        DiskDeviceObject = 0;
        v12 = (struct _DEVICE_OBJECT *)*v11;
        if ( *v11 != DeviceAttachmentBaseRef && v12->DeviceType == DeviceAttachmentBaseRef->DeviceType )
          break;
LABEL_42:
        ObfDereferenceObject(*v11);
        v26 = ++v10;
        if ( v10 >= ActualNumberDeviceObjects )
          goto LABEL_43;
      }
      if ( FltpIsAttachedToDevice(DeviceExtension[2], v12)
        || (FltpGetBaseDeviceObjectName((struct _DEVICE_OBJECT *)*v11), *v4)
        || (v13 = IoGetDiskDeviceObject((PDEVICE_OBJECT)*v11, &DiskDeviceObject), (int)FltpDbgStatus(v13) < 0) )
      {
LABEL_40:
        if ( DiskDeviceObject )
          ObfDereferenceObject(DiskDeviceObject);
        goto LABEL_42;
      }
      ObjectName = FltpGetObjectName(DiskDeviceObject, (__int64)v4);
      if ( (int)FltpDbgStatus(ObjectName) < 0 )
      {
        v15 = (unsigned __int16 *)&UnknownName;
LABEL_15:
        FltpLogEventWithObjectID(&FLTMGR_VOLUME_ATTACH_FAILED, ObjectName, 0, v15, 0);
LABEL_39:
        v10 = v26;
        goto LABEL_40;
      }
      ObjectName = FltpCreateVolumeDeviceObject(
                     (__int64)*v11,
                     (__int64)DiskDeviceObject,
                     (__int64)v4,
                     (__int64)(DeviceExtension + 6),
                     (__int64)(DeviceExtension + 8),
                     DeviceExtension[2],
                     &SourceDevice);
      if ( (int)FltpDbgStatus(ObjectName) < 0 )
      {
        v15 = v4;
        goto LABEL_15;
      }
      ExAcquireFastMutex((PFAST_MUTEX)(DeviceExtension[2] + 624LL));
      if ( FltpIsAttachedToDevice(DeviceExtension[2], (struct _DEVICE_OBJECT *)*v11) )
      {
        ExReleaseFastMutex((PFAST_MUTEX)(DeviceExtension[2] + 624LL));
        FltpCleanupDeviceObject(SourceDevice, 16, v21);
        goto LABEL_39;
      }
      v16 = SourceDevice;
      v17 = FltpAttachDeviceObject((PDEVICE_OBJECT)*v11, SourceDevice);
      ExReleaseFastMutex((PFAST_MUTEX)(DeviceExtension[2] + 624LL));
      if ( (int)FltpDbgStatus(v17) < 0 )
      {
        FltpLogEventWithObjectID(&FLTMGR_VOLUME_ATTACH_FAILED, v17, 0, v4, 0);
        FltpCleanupDeviceObject(v16, 16, v18);
        goto LABEL_39;
      }
      v19 = *((_QWORD *)v16->DeviceExtension + 10);
      if ( (unsigned int)dword_18003DAA8 > 5 )
      {
        HighLimit = 0;
        LowLimit = 0;
        IoGetStackLimits(&LowLimit, &HighLimit);
        if ( (unsigned __int64)&HighLimit - LowLimit >= 0x200 )
        {
          UniqueIdentifierForObject = FltpGetUniqueIdentifierForObject((char *)v19);
          if ( (int)FltpDbgStatus(UniqueIdentifierForObject) >= 0 )
          {
LABEL_26:
            if ( (unsigned int)dword_18003DAA8 > 5 )
            {
              v24[0] = 0;
              LowLimit = 0;
              IoGetStackLimits(&LowLimit, v24);
              if ( (unsigned __int64)v24 - LowLimit >= 0x200 )
              {
                if ( *(_DWORD *)(v19 + 60) == 1 )
                  _InterlockedIncrement(&dword_18003FFB8);
                else
                  FltpTelemetryVolumeAttach(v19);
              }
              else
              {
                _InterlockedIncrement(&dword_18003FFB0);
              }
            }
            if ( (*(_DWORD *)(v19 + 56) & 2) == 0 )
              _InterlockedOr((volatile signed __int32 *)(v19 + 56), 2u);
            if ( FltpIsDaxVolume(v19) && (*(_DWORD *)(v19 + 56) & 0x800) == 0 )
              _InterlockedOr((volatile signed __int32 *)(v19 + 56), 0x800u);
            FltpDoFilterNotificationForNewVolume(v19);
            goto LABEL_39;
          }
        }
        else
        {
          _InterlockedIncrement(&dword_18003FFB0);
        }
      }
      _InterlockedIncrement(&dword_18003FFB4);
      goto LABEL_26;
    }
LABEL_43:
    v8 = 0;
    goto LABEL_44;
  }
LABEL_45:
  ObfDereferenceObject(DeviceAttachmentBaseRef);
  FltpCleanupNameControl((__int64)v4);
  ExFreeToNPagedLookasideList(&stru_18003EDC0, v4);
  if ( v6 )
    ExFreePoolWithTag(v6, 0x6C644D46u);
  return v8;
}

```

## disassembly

```asm
0x180068900  push    rbp
0x180068902  push    rbx
0x180068903  push    rsi
0x180068904  push    rdi
0x180068905  push    r14
0x180068907  mov     rbp, rsp
0x18006890a  sub     rsp, 80h
0x180068911  mov     rsi, [rcx+40h]
0x180068915  xor     r14d, r14d
0x180068918  mov     rbx, rcx
0x18006891b  mov     [rbp+SourceDevice], r14
0x18006891f  lea     rcx, stru_18003EDC0; Lookaside
0x180068926  mov     [rbp+DiskDeviceObject], r14
0x18006892a  mov     [rbp+ActualNumberDeviceObjects], r14d
0x18006892e  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x180068935  nop     dword ptr [rax+rax+00h]
0x18006893a  mov     rdi, rax
0x18006893d  test    rax, rax
0x180068940  jnz     short loc_180068956
0x180068942  mov     eax, 0C000009Ah
0x180068947  add     rsp, 80h
0x18006894e  pop     r14
0x180068950  pop     rdi
0x180068951  pop     rsi
0x180068952  pop     rbx
0x180068953  pop     rbp
0x180068954  retn
0x180068956  mov     [rax+10h], r14d
0x18006895a  xorps   xmm0, xmm0
0x18006895d  mov     [rax+18h], r14d
0x180068961  mov     rcx, rbx; DeviceObject
0x180068964  mov     eax, 0FEh
0x180068969  mov     [rsp+80h+var_10], r13
0x18006896e  mov     [rdi+14h], eax
0x180068971  movups  xmmword ptr [rdi], xmm0
0x180068974  mov     [rdi+2], ax
0x180068978  lea     rax, [rdi+1Ch]
0x18006897c  mov     [rsp+80h+var_18], r15
0x180068981  mov     r15, r14
0x180068984  mov     [rdi+8], rax
0x180068988  call    cs:__imp_IoGetDeviceAttachmentBaseRef
0x18006898f  nop     dword ptr [rax+rax+00h]
0x180068994  lea     r9, [rbp+ActualNumberDeviceObjects]; ActualNumberDeviceObjects
0x180068998  xor     r8d, r8d; DeviceObjectListSize
0x18006899b  xor     edx, edx; DeviceObjectList
0x18006899d  mov     r13, rax
0x1800689a0  mov     rcx, [rax+8]; DriverObject
0x1800689a4  call    cs:__imp_IoEnumerateDeviceObjectList
0x1800689ab  nop     dword ptr [rax+rax+00h]
0x1800689b0  mov     ebx, eax
0x1800689b2  cmp     eax, 0C0000023h
0x1800689b7  jnz     loc_180068D98
0x1800689bd  mov     ecx, [rbp+ActualNumberDeviceObjects]
0x1800689c0  mov     r8d, 6C644D46h
0x1800689c6  add     ecx, 8
0x1800689c9  mov     edx, ecx
0x1800689cb  mov     [rbp+ActualNumberDeviceObjects], ecx
0x1800689ce  mov     ecx, 40h ; '@'
0x1800689d3  shl     rdx, 3
0x1800689d7  call    cs:__imp_ExAllocatePool2
0x1800689de  nop     dword ptr [rax+rax+00h]
0x1800689e3  mov     r15, rax
0x1800689e6  test    rax, rax
0x1800689e9  jnz     short loc_180068A22
0x1800689eb  mov     rcx, r13; Object
0x1800689ee  call    cs:__imp_ObfDereferenceObject
0x1800689f5  nop     dword ptr [rax+rax+00h]
0x1800689fa  mov     rcx, rdi
0x1800689fd  call    FltpCleanupNameControl
0x180068a02  mov     rdx, rdi; Entry
0x180068a05  lea     rcx, stru_18003EDC0; Lookaside
0x180068a0c  call    cs:__imp_ExFreeToNPagedLookasideList
0x180068a13  nop     dword ptr [rax+rax+00h]
0x180068a18  mov     eax, 0C000009Ah
0x180068a1d  jmp     loc_180068DF7
0x180068a22  mov     r8d, [rbp+ActualNumberDeviceObjects]
0x180068a26  lea     r9, [rbp+ActualNumberDeviceObjects]; ActualNumberDeviceObjects
0x180068a2a  mov     rcx, [r13+8]; DriverObject
0x180068a2e  mov     rdx, r15; DeviceObjectList
0x180068a31  lea     r8d, ds:0[r8*8]; DeviceObjectListSize
0x180068a39  call    cs:__imp_IoEnumerateDeviceObjectList
0x180068a40  nop     dword ptr [rax+rax+00h]
0x180068a45  mov     r8d, 579h
0x180068a4b  lea     rdx, aMinkernelFsFil_21; "minkernel\\fs\\filtermgr\\filter\\attac"...
0x180068a52  mov     ecx, eax
0x180068a54  xor     r9d, r9d
0x180068a57  mov     ebx, eax
0x180068a59  call    FltpDbgStatus
0x180068a5e  test    eax, eax
0x180068a60  js      loc_180068DAF
0x180068a66  mov     ebx, r14d
0x180068a69  mov     [rbp+arg_8], ebx
0x180068a6c  cmp     [rbp+ActualNumberDeviceObjects], r14d
0x180068a70  jbe     loc_180068D95
0x180068a76  mov     [rsp+80h+var_8], r12
0x180068a7b  mov     eax, ebx
0x180068a7d  lea     r12, [r15+rax*8]
0x180068a81  mov     [rbp+DiskDeviceObject], r14
0x180068a85  mov     rdx, [r12]
0x180068a89  cmp     rdx, r13
0x180068a8c  jz      loc_180068D72
0x180068a92  mov     eax, [r13+48h]
0x180068a96  cmp     [rdx+48h], eax
0x180068a99  jnz     loc_180068D72
0x180068a9f  mov     rcx, [rsi+10h]
0x180068aa3  call    FltpIsAttachedToDevice
0x180068aa8  test    al, al
0x180068aaa  jnz     loc_180068D5D
0x180068ab0  mov     rcx, [r12]
0x180068ab4  mov     rdx, rdi
0x180068ab7  call    FltpGetBaseDeviceObjectName
0x180068abc  cmp     word ptr [rdi], 0
0x180068ac0  ja      loc_180068D5D
0x180068ac6  mov     rcx, [r12]; FileSystemDeviceObject
0x180068aca  lea     rdx, [rbp+DiskDeviceObject]; DiskDeviceObject
0x180068ace  call    cs:__imp_IoGetDiskDeviceObject
0x180068ad5  nop     dword ptr [rax+rax+00h]
0x180068ada  xor     r9d, r9d
0x180068add  lea     rdx, aMinkernelFsFil_21; "minkernel\\fs\\filtermgr\\filter\\attac"...
0x180068ae4  mov     ecx, eax
0x180068ae6  mov     r8d, 5ADh
0x180068aec  call    FltpDbgStatus
0x180068af1  test    eax, eax
0x180068af3  js      loc_180068D5D
0x180068af9  mov     rcx, [rbp+DiskDeviceObject]; Object
0x180068afd  mov     rdx, rdi
0x180068b00  call    FltpGetObjectName
0x180068b05  xor     r9d, r9d
0x180068b08  lea     rdx, aMinkernelFsFil_21; "minkernel\\fs\\filtermgr\\filter\\attac"...
0x180068b0f  mov     r8d, 5B9h
0x180068b15  mov     ecx, eax
0x180068b17  mov     ebx, eax
0x180068b19  call    FltpDbgStatus
0x180068b1e  test    eax, eax
0x180068b20  jns     short loc_180068B44
0x180068b22  lea     r9, UnknownName
0x180068b29  xor     r8d, r8d
0x180068b2c  mov     [rsp+80h+var_60], r14; __int64
0x180068b31  mov     edx, ebx
0x180068b33  lea     rcx, FLTMGR_VOLUME_ATTACH_FAILED; EventDescriptor
0x180068b3a  call    FltpLogEventWithObjectID
0x180068b3f  jmp     loc_180068D5A
0x180068b44  mov     rdx, [rbp+DiskDeviceObject]
0x180068b48  lea     rax, [rbp+SourceDevice]
0x180068b4c  mov     [rsp+80h+var_50], rax
0x180068b51  lea     rcx, [rsi+40h]
0x180068b55  mov     rax, [rsi+10h]
0x180068b59  lea     r9, [rsi+30h]
0x180068b5d  mov     [rsp+80h+var_58], rax
0x180068b62  mov     r8, rdi
0x180068b65  mov     [rsp+80h+var_60], rcx
0x180068b6a  mov     rcx, [r12]
0x180068b6e  call    FltpCreateVolumeDeviceObject
0x180068b73  xor     r9d, r9d
0x180068b76  lea     rdx, aMinkernelFsFil_21; "minkernel\\fs\\filtermgr\\filter\\attac"...
0x180068b7d  mov     r8d, 5CFh
0x180068b83  mov     ecx, eax
0x180068b85  mov     ebx, eax
0x180068b87  call    FltpDbgStatus
0x180068b8c  test    eax, eax
0x180068b8e  jns     short loc_180068B95
0x180068b90  mov     r9, rdi
0x180068b93  jmp     short loc_180068B29
0x180068b95  mov     rcx, [rsi+10h]
0x180068b99  add     rcx, 270h; FastMutex
0x180068ba0  call    cs:__imp_ExAcquireFastMutex
0x180068ba7  nop     dword ptr [rax+rax+00h]
0x180068bac  mov     rdx, [r12]
0x180068bb0  mov     rcx, [rsi+10h]
0x180068bb4  call    FltpIsAttachedToDevice
0x180068bb9  test    al, al
0x180068bbb  jnz     loc_180068D35
0x180068bc1  mov     rbx, [rbp+SourceDevice]
0x180068bc5  mov     rcx, [r12]; TargetDevice
0x180068bc9  mov     rdx, rbx; SourceDevice
0x180068bcc  call    FltpAttachDeviceObject
0x180068bd1  mov     rcx, [rsi+10h]
0x180068bd5  mov     r14d, eax
0x180068bd8  add     rcx, 270h; FastMutex
0x180068bdf  call    cs:__imp_ExReleaseFastMutex
0x180068be6  nop     dword ptr [rax+rax+00h]
0x180068beb  xor     r9d, r9d
0x180068bee  lea     rdx, aMinkernelFsFil_21; "minkernel\\fs\\filtermgr\\filter\\attac"...
0x180068bf5  mov     r8d, 5F6h
0x180068bfb  mov     ecx, r14d
0x180068bfe  call    FltpDbgStatus
0x180068c03  test    eax, eax
0x180068c05  jns     short loc_180068C3A
0x180068c07  mov     r9, rdi
0x180068c0a  mov     [rsp+80h+var_60], 0; __int64
0x180068c13  xor     r8d, r8d
0x180068c16  lea     rcx, FLTMGR_VOLUME_ATTACH_FAILED; EventDescriptor
0x180068c1d  mov     edx, r14d
0x180068c20  call    FltpLogEventWithObjectID
0x180068c25  mov     edx, 10h
0x180068c2a  mov     rcx, rbx; DeviceObject
0x180068c2d  call    FltpCleanupDeviceObject
0x180068c32  xor     r14d, r14d
0x180068c35  jmp     loc_180068D5A
0x180068c3a  mov     rax, [rbx+40h]
0x180068c3e  xor     r14d, r14d
0x180068c41  cmp     cs:dword_18003DAA8, 5
0x180068c48  mov     rbx, [rax+50h]
0x180068c4c  jbe     short loc_180068CA6
0x180068c4e  lea     rdx, [rbp+HighLimit]; HighLimit
0x180068c52  mov     [rbp+HighLimit], r14
0x180068c56  lea     rcx, [rbp+LowLimit]; LowLimit
0x180068c5a  mov     [rbp+LowLimit], r14
0x180068c5e  call    cs:__imp_IoGetStackLimits
0x180068c65  nop     dword ptr [rax+rax+00h]
0x180068c6a  lea     rax, [rbp+HighLimit]
0x180068c6e  sub     rax, [rbp+LowLimit]
0x180068c72  cmp     rax, 200h
0x180068c78  jnb     short loc_180068C83
0x180068c7a  lock inc cs:dword_18003FFB0
0x180068c81  jmp     short loc_180068CA6
0x180068c83  mov     rcx, rbx
0x180068c86  call    FltpGetUniqueIdentifierForObject
0x180068c8b  mov     ecx, eax
0x180068c8d  lea     rdx, aMinkernelFsFil_21; "minkernel\\fs\\filtermgr\\filter\\attac"...
0x180068c94  xor     r9d, r9d
0x180068c97  mov     r8d, 60Ch
0x180068c9d  call    FltpDbgStatus
0x180068ca2  test    eax, eax
0x180068ca4  jns     short loc_180068CAD
0x180068ca6  lock inc cs:dword_18003FFB4
0x180068cad  cmp     cs:dword_18003DAA8, 5
0x180068cb4  jbe     short loc_180068D02
0x180068cb6  lea     rdx, [rbp+var_30]; HighLimit
0x180068cba  mov     [rbp+var_30], r14
0x180068cbe  lea     rcx, [rbp+LowLimit]; LowLimit
0x180068cc2  mov     [rbp+LowLimit], r14
0x180068cc6  call    cs:__imp_IoGetStackLimits
0x180068ccd  nop     dword ptr [rax+rax+00h]
0x180068cd2  lea     rax, [rbp+var_30]
0x180068cd6  sub     rax, [rbp+LowLimit]
0x180068cda  cmp     rax, 200h
0x180068ce0  jnb     short loc_180068CEB
0x180068ce2  lock inc cs:dword_18003FFB0
0x180068ce9  jmp     short loc_180068D02
0x180068ceb  cmp     dword ptr [rbx+3Ch], 1
0x180068cef  jz      short loc_180068CFB
0x180068cf1  mov     rcx, rbx
0x180068cf4  call    FltpTelemetryVolumeAttach
0x180068cf9  jmp     short loc_180068D02
0x180068cfb  lock inc cs:dword_18003FFB8
0x180068d02  mov     eax, [rbx+38h]
0x180068d05  test    al, 2
0x180068d07  jnz     short loc_180068D0E
0x180068d09  lock or dword ptr [rbx+38h], 2
0x180068d0e  mov     rcx, rbx
0x180068d11  call    FltpIsDaxVolume
0x180068d16  test    al, al
0x180068d18  jz      short loc_180068D2B
0x180068d1a  mov     eax, [rbx+38h]
0x180068d1d  bt      eax, 0Bh
0x180068d21  jb      short loc_180068D2B
0x180068d23  lock or dword ptr [rbx+38h], 800h
0x180068d2b  mov     rcx, rbx
0x180068d2e  call    FltpDoFilterNotificationForNewVolume
0x180068d33  jmp     short loc_180068D5A
0x180068d35  mov     rcx, [rsi+10h]
0x180068d39  add     rcx, 270h; FastMutex
0x180068d40  call    cs:__imp_ExReleaseFastMutex
0x180068d47  nop     dword ptr [rax+rax+00h]
0x180068d4c  mov     rcx, [rbp+SourceDevice]; DeviceObject
0x180068d50  mov     edx, 10h
0x180068d55  call    FltpCleanupDeviceObject
0x180068d5a  mov     ebx, [rbp+arg_8]
0x180068d5d  mov     rcx, [rbp+DiskDeviceObject]; Object
0x180068d61  test    rcx, rcx
0x180068d64  jz      short loc_180068D72
0x180068d66  call    cs:__imp_ObfDereferenceObject
0x180068d6d  nop     dword ptr [rax+rax+00h]
0x180068d72  mov     rcx, [r12]; Object
0x180068d76  call    cs:__imp_ObfDereferenceObject
0x180068d7d  nop     dword ptr [rax+rax+00h]
0x180068d82  inc     ebx
0x180068d84  mov     [rbp+arg_8], ebx
0x180068d87  cmp     ebx, [rbp+ActualNumberDeviceObjects]
0x180068d8a  jb      loc_180068A7B
0x180068d90  mov     r12, [rsp+80h+var_8]
0x180068d95  mov     ebx, r14d
0x180068d98  mov     r8d, 65Bh
0x180068d9e  lea     rdx, aMinkernelFsFil_21; "minkernel\\fs\\filtermgr\\filter\\attac"...
0x180068da5  xor     r9d, r9d
0x180068da8  mov     ecx, ebx
0x180068daa  call    FltpDbgStatus
0x180068daf  mov     rcx, r13; Object
0x180068db2  call    cs:__imp_ObfDereferenceObject
0x180068db9  nop     dword ptr [rax+rax+00h]
0x180068dbe  mov     rcx, rdi
0x180068dc1  call    FltpCleanupNameControl
0x180068dc6  mov     rdx, rdi; Entry
0x180068dc9  lea     rcx, stru_18003EDC0; Lookaside
0x180068dd0  call    cs:__imp_ExFreeToNPagedLookasideList
0x180068dd7  nop     dword ptr [rax+rax+00h]
0x180068ddc  test    r15, r15
0x180068ddf  jz      short loc_180068DF5
0x180068de1  mov     edx, 6C644D46h; Tag
  ... truncated ...
```
