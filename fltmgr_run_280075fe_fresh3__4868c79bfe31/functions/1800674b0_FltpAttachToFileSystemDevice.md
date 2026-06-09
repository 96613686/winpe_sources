# FltpAttachToFileSystemDevice

- ea: `0x1800674b0`
- end: `0x18006790b`
- name: `FltpAttachToFileSystemDevice`
- size: `1115`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT TargetDevice)`
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180078690`

## callees

- `0x180009f20`
- `0x18001f3c0`
- `0x18004f284`
- `0x1800552c0`
- `0x18005c5a0`
- `0x1800674b0`
- `0x180067920`
- `0x180067a50`
- `0x180067b00`
- `0x180067be0`
- `0x1800682b0`
- `0x180068420`
- `0x1800688d0`
- `0x180068900`
- `0x180069170`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x180067671`
- `ntoskrnl!ExReleaseFastMutex` at `0x180067820`
- `ntoskrnl!ExReleaseFastMutex` at `0x180067671`
- `ntoskrnl!ExReleaseFastMutex` at `0x180067820`
- `ntoskrnl!ExAcquireFastMutex` at `0x180067638`
- `ntoskrnl!ExAcquireFastMutex` at `0x180067638`
- `ntoskrnl!ObfDereferenceObject` at `0x180067561`
- `ntoskrnl!ObfDereferenceObject` at `0x180067561`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1800674f5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1800674f5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1800677e7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1800677e7`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x180067540`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x180067540`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006788e`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006788e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800678a5`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800678a5`
- `ntoskrnl!IoGetStackLimits` at `0x1800676e2`
- `ntoskrnl!IoGetStackLimits` at `0x180067753`
- `ntoskrnl!IoGetStackLimits` at `0x1800676e2`
- `ntoskrnl!IoGetStackLimits` at `0x180067753`

## pseudocode

```c
__int64 __fastcall FltpAttachToFileSystemDevice(PDEVICE_OBJECT TargetDevice, __int64 a2)
{
  ULONG DeviceType; // eax
  int v5; // ecx
  UNICODE_STRING *v6; // rax
  UNICODE_STRING *v7; // rbp
  PDEVICE_OBJECT DeviceAttachmentBaseRef; // rdi
  unsigned int ObjectName; // r14d
  __int64 FrameForDeviceStack; // r9
  ULONG v11; // eax
  int v12; // r12d
  unsigned int VolumeDeviceObject; // eax
  struct _DEVICE_OBJECT *v14; // rdi
  __int64 v15; // r15
  ULONG v16; // eax
  __int64 v17; // rbx
  unsigned int UniqueIdentifierForObject; // eax
  int v20; // ecx
  int v21; // [rsp+20h] [rbp-68h]
  unsigned __int64 HighLimit; // [rsp+40h] [rbp-48h] BYREF
  unsigned __int64 v23; // [rsp+48h] [rbp-40h] BYREF
  UNICODE_STRING DestinationString; // [rsp+50h] [rbp-38h] BYREF
  unsigned __int64 LowLimit; // [rsp+90h] [rbp+8h] BYREF

  DeviceType = TargetDevice->DeviceType;
  LowLimit = 0;
  DestinationString = 0;
  if ( DeviceType > 0x14 )
    return 0;
  v5 = 1184008;
  if ( !_bittest(&v5, DeviceType) )
    return 0;
  v6 = (UNICODE_STRING *)ExAllocateFromNPagedLookasideList(&stru_18003EDC0);
  v7 = v6;
  if ( !v6 )
    return 3221225626LL;
  *(_DWORD *)&v6[1].Length = 0;
  LODWORD(v6[1].Buffer) = 0;
  *(_DWORD *)(&v6[1].MaximumLength + 1) = 254;
  *v6 = 0;
  v6->MaximumLength = 254;
  v6->Buffer = (wchar_t *)&v6[1].Buffer + 2;
  DeviceAttachmentBaseRef = IoGetDeviceAttachmentBaseRef(TargetDevice);
  ObjectName = FltpGetObjectName(DeviceAttachmentBaseRef->DriverObject, (__int64)v7);
  ObfDereferenceObject(DeviceAttachmentBaseRef);
  if ( (int)FltpDbgStatus(ObjectName, "minkernel\\fs\\filtermgr\\filter\\attachdetachsup.c", 991, 0) >= 0 )
  {
    if ( ((FltGlobals[0] & 0x10) != 0
       || (RtlInitUnicodeString(&DestinationString, L"\\FileSystem\\Fs_Rec"),
           !RtlEqualUnicodeString(v7, &DestinationString, 1u)))
      && (FrameForDeviceStack = FltpFindFrameForDeviceStack(TargetDevice)) != 0 )
    {
      v11 = TargetDevice->DeviceType;
      v12 = 1183744;
      if ( v11 <= 0x14 && _bittest(&v12, v11) )
        VolumeDeviceObject = FltpCreateVolumeDeviceObject(
                               (__int64)TargetDevice,
                               0,
                               (const UNICODE_STRING *)a2,
                               (const UNICODE_STRING *)a2,
                               v7,
                               FrameForDeviceStack,
                               (PDEVICE_OBJECT *)&LowLimit);
      else
        VolumeDeviceObject = FltpCreateControlDeviceObject(
                               (__int64)TargetDevice,
                               (const UNICODE_STRING *)a2,
                               v7,
                               FrameForDeviceStack,
                               (PDEVICE_OBJECT *)&LowLimit);
      ObjectName = VolumeDeviceObject;
      if ( (int)FltpDbgStatus(VolumeDeviceObject, "minkernel\\fs\\filtermgr\\filter\\attachdetachsup.c", 1094, 0) >= 0 )
      {
        v14 = (struct _DEVICE_OBJECT *)LowLimit;
        v15 = *(_QWORD *)(LowLimit + 64);
        ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v15 + 16) + 624LL));
        if ( (unsigned __int8)FltpIsAttachedToDevice(*(_QWORD *)(v15 + 16), TargetDevice) )
        {
          ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(v15 + 16) + 624LL));
          FltpCleanupDeviceObject(v14);
          if ( (Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits & 8) != 0 )
            McTemplateU0sppws_EtwWriteTransfer(
              v20,
              (unsigned int)AttachDetachSup_c1201,
              (unsigned int)"FltpAttachToFileSystemDevice",
              (_DWORD)TargetDevice,
              v21,
              *(_WORD *)a2 >> 1,
              *(_QWORD *)(a2 + 8));
          goto LABEL_26;
        }
        ObjectName = FltpAttachDeviceObject(TargetDevice, v14);
        ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(v15 + 16) + 624LL));
        if ( (int)FltpDbgStatus(ObjectName, "minkernel\\fs\\filtermgr\\filter\\attachdetachsup.c", 1131, 0) < 0 )
          goto LABEL_25;
        v16 = TargetDevice->DeviceType;
        if ( v16 <= 0x14 && _bittest(&v12, v16) )
        {
          v17 = *((_QWORD *)v14->DeviceExtension + 10);
          if ( (unsigned int)dword_18003DAA8 > 5 )
          {
            HighLimit = 0;
            LowLimit = 0;
            IoGetStackLimits(&LowLimit, &HighLimit);
            if ( (unsigned __int64)&HighLimit - LowLimit < 0x200 )
            {
              _InterlockedIncrement(&dword_18003FFB0);
            }
            else
            {
              UniqueIdentifierForObject = FltpGetUniqueIdentifierForObject(v17);
              if ( (int)FltpDbgStatus(
                          UniqueIdentifierForObject,
                          "minkernel\\fs\\filtermgr\\filter\\attachdetachsup.c",
                          1173,
                          0) >= 0 )
              {
LABEL_18:
                if ( (unsigned int)dword_18003DAA8 > 5 )
                {
                  v23 = 0;
                  LowLimit = 0;
                  IoGetStackLimits(&LowLimit, &v23);
                  if ( (unsigned __int64)&v23 - LowLimit >= 0x200 )
                  {
                    if ( *(_DWORD *)(v17 + 60) == 1 )
                      _InterlockedIncrement(&dword_18003FFB8);
                    else
                      FltpTelemetryVolumeAttach(v17);
                  }
                  else
                  {
                    _InterlockedIncrement(&dword_18003FFB0);
                  }
                }
                if ( (*(_DWORD *)(v17 + 56) & 2) == 0 )
                  _InterlockedOr((volatile signed __int32 *)(v17 + 56), 2u);
                FltpDoFilterNotificationForNewVolume(v17);
                goto LABEL_26;
              }
            }
          }
          _InterlockedIncrement(&dword_18003FFB4);
          goto LABEL_18;
        }
        ObjectName = FltpEnumerateFileSystemVolumes(v14);
        if ( (int)FltpDbgStatus(ObjectName, "minkernel\\fs\\filtermgr\\filter\\attachdetachsup.c", 1152, 0) < 0 )
LABEL_25:
          FltpCleanupDeviceObject(v14);
      }
    }
    else
    {
      ObjectName = 0;
    }
  }
LABEL_26:
  FltpCleanupNameControl(v7);
  ExFreeToNPagedLookasideList(&stru_18003EDC0, v7);
  return ObjectName;
}

```

## disassembly

```asm
0x1800674b0  mov     r11, rsp
0x1800674b3  push    rbx
0x1800674b4  push    rsi
0x1800674b5  push    r13
0x1800674b7  sub     rsp, 70h
0x1800674bb  mov     eax, [rcx+48h]
0x1800674be  xor     r13d, r13d
0x1800674c1  mov     [r11+8], r13
0x1800674c5  xorps   xmm0, xmm0
0x1800674c8  mov     rsi, rdx
0x1800674cb  mov     rbx, rcx
0x1800674ce  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x1800674d3  cmp     eax, 14h
0x1800674d6  ja      loc_18006786F
0x1800674dc  mov     ecx, 121108h
0x1800674e1  bt      ecx, eax
0x1800674e4  jnb     loc_18006786F
0x1800674ea  lea     rcx, stru_18003EDC0; Lookaside
0x1800674f1  mov     [r11+10h], rbp
0x1800674f5  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1800674fc  nop     dword ptr [rax+rax+00h]
0x180067501  mov     rbp, rax
0x180067504  test    rax, rax
0x180067507  jz      loc_18006787B
0x18006750d  mov     [rax+10h], r13d
0x180067511  xorps   xmm0, xmm0
0x180067514  mov     [rax+18h], r13d
0x180067518  mov     rcx, rbx; DeviceObject
0x18006751b  mov     eax, 0FEh
0x180067520  mov     [rsp+88h+arg_10], rdi
0x180067528  mov     [rbp+14h], eax
0x18006752b  movups  xmmword ptr [rbp+0], xmm0
0x18006752f  mov     [rbp+2], ax
0x180067533  lea     rax, [rbp+1Ch]
0x180067537  mov     [rbp+8], rax
0x18006753b  mov     [rsp+88h+var_20], r14
0x180067540  call    cs:__imp_IoGetDeviceAttachmentBaseRef
0x180067547  nop     dword ptr [rax+rax+00h]
0x18006754c  mov     rdx, rbp
0x18006754f  mov     rdi, rax
0x180067552  mov     rcx, [rax+8]; Object
0x180067556  call    FltpGetObjectName
0x18006755b  mov     rcx, rdi; Object
0x18006755e  mov     r14d, eax
0x180067561  call    cs:__imp_ObfDereferenceObject
0x180067568  nop     dword ptr [rax+rax+00h]
0x18006756d  mov     r8d, 3DFh
0x180067573  lea     rdx, aMinkernelFsFil_21; "minkernel\\fs\\filtermgr\\filter\\attac"...
0x18006757a  xor     r9d, r9d
0x18006757d  mov     ecx, r14d
0x180067580  call    FltpDbgStatus
0x180067585  test    eax, eax
0x180067587  js      loc_1800677D5
0x18006758d  mov     eax, cs:FltGlobals
0x180067593  test    al, 10h
0x180067595  jz      loc_180067882
0x18006759b  mov     rcx, rbx; DeviceObject
0x18006759e  call    FltpFindFrameForDeviceStack
0x1800675a3  mov     r9, rax
0x1800675a6  test    rax, rax
0x1800675a9  jz      loc_1800678B9
0x1800675af  mov     eax, [rbx+48h]
0x1800675b2  mov     [rsp+88h+arg_18], r12
0x1800675ba  mov     r12d, 121000h
0x1800675c0  cmp     eax, 14h
0x1800675c3  ja      loc_1800678C1
0x1800675c9  bt      r12d, eax
0x1800675cd  jnb     loc_1800678C1
0x1800675d3  lea     rax, [rsp+88h+LowLimit]
0x1800675db  mov     r8, rsi
0x1800675de  mov     [rsp+88h+var_58], rax
0x1800675e3  xor     edx, edx
0x1800675e5  mov     [rsp+88h+var_60], r9
0x1800675ea  mov     rcx, rbx
0x1800675ed  mov     r9, rsi
0x1800675f0  mov     [rsp+88h+var_68], rbp
0x1800675f5  call    FltpCreateVolumeDeviceObject
0x1800675fa  mov     r8d, 446h
0x180067600  lea     rdx, aMinkernelFsFil_21; "minkernel\\fs\\filtermgr\\filter\\attac"...
0x180067607  xor     r9d, r9d
0x18006760a  mov     ecx, eax
0x18006760c  mov     r14d, eax
0x18006760f  call    FltpDbgStatus
0x180067614  test    eax, eax
0x180067616  js      loc_1800677CD
0x18006761c  mov     rdi, [rsp+88h+LowLimit]
0x180067624  mov     [rsp+88h+var_28], r15
0x180067629  mov     r15, [rdi+40h]
0x18006762d  mov     rcx, [r15+10h]
0x180067631  add     rcx, 270h; FastMutex
0x180067638  call    cs:__imp_ExAcquireFastMutex
0x18006763f  nop     dword ptr [rax+rax+00h]
0x180067644  mov     rcx, [r15+10h]
0x180067648  mov     rdx, rbx
0x18006764b  call    FltpIsAttachedToDevice
0x180067650  test    al, al
0x180067652  jnz     loc_180067815
0x180067658  mov     rdx, rdi; SourceDevice
0x18006765b  mov     rcx, rbx; TargetDevice
0x18006765e  call    FltpAttachDeviceObject
0x180067663  mov     rcx, [r15+10h]
0x180067667  mov     r14d, eax
0x18006766a  add     rcx, 270h; FastMutex
0x180067671  call    cs:__imp_ExReleaseFastMutex
0x180067678  nop     dword ptr [rax+rax+00h]
0x18006767d  mov     r8d, 46Bh
0x180067683  lea     rdx, aMinkernelFsFil_21; "minkernel\\fs\\filtermgr\\filter\\attac"...
0x18006768a  xor     r9d, r9d
0x18006768d  mov     ecx, r14d
0x180067690  call    FltpDbgStatus
0x180067695  test    eax, eax
0x180067697  js      loc_1800677BB
0x18006769d  mov     eax, [rbx+48h]
0x1800676a0  cmp     eax, 14h
0x1800676a3  ja      loc_180067795
0x1800676a9  bt      r12d, eax
0x1800676ad  jnb     loc_180067795
0x1800676b3  cmp     cs:dword_18003DAA8, 5
0x1800676ba  mov     rax, [rdi+40h]
0x1800676be  mov     rbx, [rax+50h]
0x1800676c2  jbe     loc_1800678E8
0x1800676c8  lea     rdx, [rsp+88h+HighLimit]; HighLimit
0x1800676cd  mov     [rsp+88h+HighLimit], r13
0x1800676d2  lea     rcx, [rsp+88h+LowLimit]; LowLimit
0x1800676da  mov     [rsp+88h+LowLimit], r13
0x1800676e2  call    cs:__imp_IoGetStackLimits
0x1800676e9  nop     dword ptr [rax+rax+00h]
0x1800676ee  lea     rax, [rsp+88h+HighLimit]
0x1800676f3  sub     rax, [rsp+88h+LowLimit]
0x1800676fb  cmp     rax, 200h
0x180067701  jb      loc_1800678E1
0x180067707  mov     rcx, rbx
0x18006770a  mov     edi, 495h
0x18006770f  call    FltpGetUniqueIdentifierForObject
0x180067714  mov     ecx, eax
0x180067716  lea     rdx, aMinkernelFsFil_21; "minkernel\\fs\\filtermgr\\filter\\attac"...
0x18006771d  xor     r9d, r9d
0x180067720  mov     r8d, edi
0x180067723  call    FltpDbgStatus
0x180067728  test    eax, eax
0x18006772a  js      loc_1800678E8
0x180067730  cmp     cs:dword_18003DAA8, 5
0x180067737  jbe     short loc_18006777F
0x180067739  lea     rdx, [rsp+88h+var_40]; HighLimit
0x18006773e  mov     [rsp+88h+var_40], r13
0x180067743  lea     rcx, [rsp+88h+LowLimit]; LowLimit
0x18006774b  mov     [rsp+88h+LowLimit], r13
0x180067753  call    cs:__imp_IoGetStackLimits
0x18006775a  nop     dword ptr [rax+rax+00h]
0x18006775f  lea     rax, [rsp+88h+var_40]
0x180067764  sub     rax, [rsp+88h+LowLimit]
0x18006776c  cmp     rax, 200h
0x180067772  jnb     loc_1800678F4
0x180067778  lock inc cs:dword_18003FFB0
0x18006777f  mov     eax, [rbx+38h]
0x180067782  test    al, 2
0x180067784  jnz     short loc_18006778B
0x180067786  lock or dword ptr [rbx+38h], 2
0x18006778b  mov     rcx, rbx
0x18006778e  call    FltpDoFilterNotificationForNewVolume
0x180067793  jmp     short loc_1800677C8
0x180067795  mov     rcx, rdi; DeviceObject
0x180067798  call    FltpEnumerateFileSystemVolumes
0x18006779d  mov     r8d, 480h
0x1800677a3  lea     rdx, aMinkernelFsFil_21; "minkernel\\fs\\filtermgr\\filter\\attac"...
0x1800677aa  xor     r9d, r9d
0x1800677ad  mov     ecx, eax
0x1800677af  mov     r14d, eax
0x1800677b2  call    FltpDbgStatus
0x1800677b7  test    eax, eax
0x1800677b9  jns     short loc_1800677C8
0x1800677bb  mov     edx, 10h
0x1800677c0  mov     rcx, rdi; DeviceObject
0x1800677c3  call    FltpCleanupDeviceObject
0x1800677c8  mov     r15, [rsp+88h+var_28]
0x1800677cd  mov     r12, [rsp+88h+arg_18]
0x1800677d5  mov     rcx, rbp
0x1800677d8  call    FltpCleanupNameControl
0x1800677dd  mov     rdx, rbp; Entry
0x1800677e0  lea     rcx, stru_18003EDC0; Lookaside
0x1800677e7  call    cs:__imp_ExFreeToNPagedLookasideList
0x1800677ee  nop     dword ptr [rax+rax+00h]
0x1800677f3  mov     rdi, [rsp+88h+arg_10]
0x1800677fb  mov     eax, r14d
0x1800677fe  mov     r14, [rsp+88h+var_20]
0x180067803  mov     rbp, [rsp+88h+arg_8]
0x18006780b  add     rsp, 70h
0x18006780f  pop     r13
0x180067811  pop     rsi
0x180067812  pop     rbx
0x180067813  retn
0x180067815  mov     rcx, [r15+10h]
0x180067819  add     rcx, 270h; FastMutex
0x180067820  call    cs:__imp_ExReleaseFastMutex
0x180067827  nop     dword ptr [rax+rax+00h]
0x18006782c  mov     edx, 10h
0x180067831  mov     rcx, rdi; DeviceObject
0x180067834  call    FltpCleanupDeviceObject
0x180067839  test    cs:Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits, 8
0x180067840  jz      short loc_1800677C8
0x180067842  movzx   edx, word ptr [rsi]
0x180067845  lea     r8, aFltpattachtofi; "FltpAttachToFileSystemDevice"
0x18006784c  mov     rax, [rsi+8]
0x180067850  mov     r9, rbx
0x180067853  shr     edx, 1
0x180067855  mov     [rsp+88h+var_58], rax
0x18006785a  mov     dword ptr [rsp+88h+var_60], edx
0x18006785e  lea     rdx, AttachDetachSup_c1201
0x180067865  call    McTemplateU0sppws_EtwWriteTransfer
0x18006786a  jmp     loc_1800677C8
0x18006786f  xor     eax, eax
0x180067871  add     rsp, 70h
0x180067875  pop     r13
0x180067877  pop     rsi
0x180067878  pop     rbx
0x180067879  retn
0x18006787b  mov     eax, 0C000009Ah
0x180067880  jmp     short loc_180067803
0x180067882  lea     rdx, aFilesystemFsRe_0; "\\FileSystem\\Fs_Rec"
0x180067889  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x18006788e  call    cs:__imp_RtlInitUnicodeString
0x180067895  nop     dword ptr [rax+rax+00h]
0x18006789a  mov     r8b, 1; CaseInSensitive
0x18006789d  lea     rdx, [rsp+88h+DestinationString]; String2
0x1800678a2  mov     rcx, rbp; String1
0x1800678a5  call    cs:__imp_RtlEqualUnicodeString
0x1800678ac  nop     dword ptr [rax+rax+00h]
0x1800678b1  test    al, al
0x1800678b3  jz      loc_18006759B
0x1800678b9  mov     r14d, r13d
0x1800678bc  jmp     loc_1800677D5
0x1800678c1  lea     rax, [rsp+88h+LowLimit]
0x1800678c9  mov     r8, rbp
0x1800678cc  mov     rdx, rsi
0x1800678cf  mov     [rsp+88h+var_68], rax
0x1800678d4  mov     rcx, rbx
0x1800678d7  call    FltpCreateControlDeviceObject
0x1800678dc  jmp     loc_1800675FA
0x1800678e1  lock inc cs:dword_18003FFB0
0x1800678e8  lock inc cs:dword_18003FFB4
0x1800678ef  jmp     loc_180067730
0x1800678f4  cmp     dword ptr [rbx+3Ch], 1
0x1800678f8  jz      loc_18007A4F4
0x1800678fe  mov     rcx, rbx
0x180067901  call    FltpTelemetryVolumeAttach
0x180067906  jmp     loc_18006777F
0x18007a4f4  lock inc cs:dword_18003FFB8
0x18007a4fb  jmp     loc_18006777F
```
