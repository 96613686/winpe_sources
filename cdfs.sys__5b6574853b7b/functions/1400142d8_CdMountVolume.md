# CdMountVolume

- ea: `0x1400142d8`
- end: `0x140014c32`
- name: `CdMountVolume`
- size: `2394`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140013a70`

## callees

- `0x140001160`
- `0x1400020d0`
- `0x1400024e0`
- `0x140002630`
- `0x140002df0`
- `0x140003000`
- `0x140003300`
- `0x14000fcb0`
- `0x14000fcf8`
- `0x140013c0c`
- `0x140013e2c`
- `0x1400140cc`
- `0x1400142d8`
- `0x1400181a4`
- `0x14001904c`
- `0x140019280`
- `0x140019a00`
- `0x14001b0d8`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140014abb`
- `ntoskrnl!ExReleaseResourceLite` at `0x140014b5a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140014b85`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001bc3b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001bc66`
- `ntoskrnl!ExReleaseResourceLite` at `0x140014abb`
- `ntoskrnl!ExReleaseResourceLite` at `0x140014b5a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140014b85`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001bc3b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001bc66`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014808`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014ae9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014aff`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bb92`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bbb7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014808`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014ae9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014aff`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bb92`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bbb7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400144f8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001477e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400148a1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400144f8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001477e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400148a1`
- `ntoskrnl!ObfDereferenceObject` at `0x140014aa1`
- `ntoskrnl!ObfDereferenceObject` at `0x140014bad`
- `ntoskrnl!ObfDereferenceObject` at `0x140014aa1`
- `ntoskrnl!ObfDereferenceObject` at `0x140014bad`
- `ntoskrnl!IoCreateDevice` at `0x14001459d`
- `ntoskrnl!IoCreateDevice` at `0x14001459d`
- `ntoskrnl!IoDeleteDevice` at `0x140014b72`
- `ntoskrnl!IoDeleteDevice` at `0x14001bc52`
- `ntoskrnl!IoDeleteDevice` at `0x140014b72`
- `ntoskrnl!IoDeleteDevice` at `0x14001bc52`
- `ntoskrnl!ObfReferenceObject` at `0x1400149f0`
- `ntoskrnl!ObfReferenceObject` at `0x140014a22`
- `ntoskrnl!ObfReferenceObject` at `0x1400149f0`
- `ntoskrnl!ObfReferenceObject` at `0x140014a22`
- `ntoskrnl!ExInitializeResourceLite` at `0x140014998`
- `ntoskrnl!ExInitializeResourceLite` at `0x140014998`
- `ntoskrnl!KeInitializeEvent` at `0x140014985`
- `ntoskrnl!KeInitializeEvent` at `0x140014985`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400144db`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400144db`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140014b9e`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140014b9e`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001462c`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001462c`
- `ntoskrnl!FsRtlVolumeDeviceToCorrelationId` at `0x140014717`
- `ntoskrnl!FsRtlVolumeDeviceToCorrelationId` at `0x140014717`
- `ntoskrnl!IoAllocateIrp` at `0x14001492d`
- `ntoskrnl!IoAllocateIrp` at `0x14001492d`
- `ntoskrnl!IoInitializeIrp` at `0x14001496b`
- `ntoskrnl!IoInitializeIrp` at `0x14001496b`
- `ntoskrnl!IoGetStackLimits` at `0x140014bea`
- `ntoskrnl!IoGetStackLimits` at `0x140014bea`

## pseudocode

```c
__int64 __fastcall CdMountVolume(__int64 a1, __int64 a2)
{
  __int64 v2; // r12
  __int64 v3; // rsi
  __int64 v4; // r14
  __int64 v5; // rax
  __int64 v6; // r13
  __int64 v7; // rdi
  __int64 v8; // rax
  NTSTATUS v9; // edi
  int v11; // ebx
  __int64 v12; // rcx
  int v13; // eax
  struct _IRP **p_CurrentIrp; // rbx
  struct _FILE_OBJECT *Information; // r15
  PVOID PoolWithTag; // rax
  PVOID v17; // rdi
  __int64 *v18; // rdi
  __int64 *v19; // rdx
  int v20; // ecx
  ULONG v21; // eax
  PDEVICE_OBJECT v22; // rcx
  struct _DRIVER_OBJECT **p_DriverObject; // rax
  int v24; // ecx
  __int64 v25; // rcx
  char v26; // di
  struct _IRP *v27; // rcx
  PVOID v28; // rax
  struct _IRP *v29; // rax
  struct _IRP *v30; // rdi
  __int64 i; // rdx
  IRP *Irp; // rcx
  __int64 v33; // rcx
  unsigned __int64 v34; // rdi
  int v35; // eax
  int v36; // ecx
  struct _IRP *v37; // rax
  int DeviceCharacteristics; // [rsp+20h] [rbp-138h]
  int Exclusive; // [rsp+28h] [rbp-130h]
  char PrimaryVd; // [rsp+50h] [rbp-108h]
  bool v41; // [rsp+51h] [rbp-107h]
  unsigned __int8 StackSize; // [rsp+58h] [rbp-100h]
  PDEVICE_OBJECT DeviceObject; // [rsp+60h] [rbp-F8h] BYREF
  char v44; // [rsp+68h] [rbp-F0h]
  int v45; // [rsp+6Ch] [rbp-ECh] BYREF
  unsigned int v46; // [rsp+70h] [rbp-E8h]
  int v47; // [rsp+74h] [rbp-E4h] BYREF
  int v48; // [rsp+78h] [rbp-E0h] BYREF
  int v49; // [rsp+7Ch] [rbp-DCh] BYREF
  int v50; // [rsp+80h] [rbp-D8h]
  __int64 v51; // [rsp+88h] [rbp-D0h]
  unsigned __int64 LowLimit; // [rsp+90h] [rbp-C8h] BYREF
  PVOID P; // [rsp+98h] [rbp-C0h]
  PVOID v54; // [rsp+A0h] [rbp-B8h]
  __int64 v55; // [rsp+A8h] [rbp-B0h]
  struct _IRP **v56; // [rsp+B0h] [rbp-A8h]
  struct _IRP *v57; // [rsp+B8h] [rbp-A0h]
  unsigned __int64 HighLimit; // [rsp+C0h] [rbp-98h] BYREF
  __int64 v59; // [rsp+C8h] [rbp-90h]
  __int64 v60; // [rsp+D0h] [rbp-88h]
  __int128 v61; // [rsp+D8h] [rbp-80h]
  int v62[4]; // [rsp+E8h] [rbp-70h] BYREF
  __int128 v63; // [rsp+F8h] [rbp-60h] BYREF
  __int64 v64; // [rsp+108h] [rbp-50h]
  __int128 v65; // [rsp+110h] [rbp-48h] BYREF
  __int64 v66; // [rsp+120h] [rbp-38h]

  v2 = a2;
  v3 = a1;
  v60 = a1;
  v4 = 0;
  DeviceObject = 0;
  LowLimit = 0;
  v5 = *(_QWORD *)(a2 + 184);
  v6 = *(_QWORD *)(v5 + 16);
  v7 = *(_QWORD *)(v5 + 8);
  v55 = v7;
  v65 = 0;
  v66 = 0;
  v63 = 0;
  v64 = 0;
  v61 = 0;
  v49 = 0;
  v48 = 0;
  v47 = 0;
  v45 = 0;
  *(_OWORD *)v62 = 0;
  v8 = *(_QWORD *)(v7 + 16);
  *(_QWORD *)(a1 + 40) = v8;
  v41 = (*(_BYTE *)(v8 + 48) & 2) != 0;
  if ( CdDisable )
  {
    v9 = -1073741489;
LABEL_3:
    CdCompleteRequest(a1, a2, (unsigned int)v9);
    return (unsigned int)v9;
  }
  if ( (word_14000732E & 1) == 0 )
  {
    v11 = CdPerformDevIoCtrlEx(a1, 149504, v6, 0, 0, &v45, 4);
    if ( v11 < 0 )
      goto LABEL_8;
    if ( *((_QWORD *)&v61 + 1) != 4 )
      v45 = 0;
    v13 = CdPerformDevIoCtrlEx(v12, 147532, v6, 0, 0, &v65, 24);
    v11 = -1073741670;
    if ( v13 == -1073741670 )
    {
LABEL_8:
      a2 = v2;
      a1 = v3;
      goto LABEL_6;
    }
    v59 = v7;
    p_CurrentIrp = 0;
    v56 = 0;
    PrimaryVd = 0;
    Information = 0;
    v51 = 0;
    v54 = 0;
    v46 = 1;
    if ( v13 >= 0 && (unsigned int)(HIDWORD(v66) - 1) <= 0x7FE )
      v46 = 0x800u / HIDWORD(v66);
    ExAcquireResourceExclusiveLite(&Resource, 1u);
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1041, 0x554u, 0x63746443u);
    v17 = PoolWithTag;
    P = PoolWithTag;
    if ( !ExPoolZeroingNativelySupported && PoolWithTag )
      memset(PoolWithTag, 0, 0x554u);
    v54 = v17;
    v18 = (__int64 *)qword_1400072F0;
    while ( v18 != &qword_1400072F0 )
    {
      v19 = v18 - 4;
      v18 = (__int64 *)*v18;
      v20 = *((_DWORD *)v19 + 13);
      if ( (unsigned int)(v20 - 3) <= 1 || !v20 && *((_DWORD *)v19 + 15) <= 6u )
        CdCheckForDismount(v3, v19, 0);
    }
    v9 = IoCreateDevice(DriverObject, 0x340u, 0, 3u, 0, 0, &DeviceObject);
    if ( v9 >= 0 )
    {
      v21 = *(_DWORD *)(v6 + 152);
      v22 = DeviceObject;
      if ( v21 > DeviceObject->AlignmentRequirement )
      {
        DeviceObject->AlignmentRequirement = v21;
        v22 = DeviceObject;
      }
      v22->StackSize = *(_BYTE *)(v6 + 76) + 1;
      StackSize = DeviceObject->StackSize;
      DeviceObject->Flags &= ~0x80u;
      DeviceObject[1].ReferenceCount = 0;
      p_DriverObject = &DeviceObject[1].DriverObject;
      DeviceObject[1].NextDevice = (PDEVICE_OBJECT)((char *)DeviceObject + 344);
      *p_DriverObject = (struct _DRIVER_OBJECT *)p_DriverObject;
      *(_DWORD *)&DeviceObject[1].Type = 0;
      KeInitializeSpinLock((PKSPIN_LOCK)&DeviceObject[1].AttachedDevice);
      v9 = CdProcessToc(v24, v6, (_DWORD)P, (unsigned int)&v49, (__int64)&v48, (__int64)&v47);
      if ( !v9 )
      {
        v25 = v55;
        *(_QWORD *)(v55 + 8) = DeviceObject;
        v26 = v47;
        Exclusive = v49;
        CdInitializeVcb(v25, &DeviceObject[1].CurrentIrp, v6, v25, P);
        p_CurrentIrp = &DeviceObject[1].CurrentIrp;
        v56 = p_CurrentIrp;
        DeviceObject = 0;
        v55 = 0;
        v59 = 0;
        P = 0;
        v54 = 0;
        if ( (int)FsRtlVolumeDeviceToCorrelationId(p_CurrentIrp[2], v62) >= 0 )
          *((_OWORD *)p_CurrentIrp + 49) = *(_OWORD *)v62;
        *(_QWORD *)(v3 + 16) = p_CurrentIrp;
        CdAcquireResource(v3, p_CurrentIrp + 16, 0, 0);
        ++HIDWORD(p_CurrentIrp[1]->AssociatedIrp.SystemBuffer);
        v27 = *(struct _IRP **)&p_CurrentIrp[1]->Flags;
        v27->IoStatus.Status &= ~2u;
        if ( (*((_DWORD *)p_CurrentIrp + 12) & 0x80u) != 0 )
          goto LABEL_41;
        v28 = ExAllocatePoolWithTag((POOL_TYPE)1552, 0x1000u, 0x64766443u);
        v4 = (__int64)v28;
        if ( !ExPoolZeroingNativelySupported && v28 )
          memset(v28, 0, 0x1000u);
        v51 = v4;
        LOBYTE(Exclusive) = 0;
        LOBYTE(DeviceCharacteristics) = 1;
        PrimaryVd = CdFindPrimaryVd(v3, p_CurrentIrp, v4, v46, DeviceCharacteristics);
        v44 = PrimaryVd;
        if ( PrimaryVd )
        {
LABEL_41:
          if ( PrimaryVd )
          {
            memmove((void *)(v4 + 2048), (const void *)v4, 0x800u);
            CdFindActiveVolDescriptor(v3, (__int64)p_CurrentIrp, (_BYTE *)v4, 0);
          }
          if ( (*((_DWORD *)p_CurrentIrp + 12) & 0x80u) == 0
            && HIBYTE(p_CurrentIrp[65]->Size) == LOBYTE(p_CurrentIrp[65]->Size) )
          {
            v50 = 0;
            v57 = 0;
            v29 = (struct _IRP *)ExAllocatePoolWithTag((POOL_TYPE)1041, 0x30000u, 0x73666443u);
            v30 = v29;
            if ( !ExPoolZeroingNativelySupported && v29 )
              memset(v29, 0, 0x30000u);
            p_CurrentIrp[71] = v30;
            v57 = v30;
            for ( i = 0; ; i = (unsigned int)(i + 1) )
            {
              v50 = i;
              if ( (unsigned int)i >= 4 )
                break;
              p_CurrentIrp[2 * (unsigned int)i + 73] = v30;
              LODWORD(p_CurrentIrp[2 * i + 72]) = -1;
              v30 = (struct _IRP *)((char *)v30 + 49152);
              v57 = v30;
            }
            Irp = IoAllocateIrp(StackSize, 0);
            p_CurrentIrp[81] = Irp;
            if ( !Irp )
            {
              v9 = -1073741670;
              goto LABEL_65;
            }
            IoInitializeIrp(Irp, 72 * StackSize + 208, StackSize);
            KeInitializeEvent((PRKEVENT)(p_CurrentIrp + 82), SynchronizationEvent, 0);
            ExInitializeResourceLite((PERESOURCE)(p_CurrentIrp + 85));
          }
          if ( (unsigned __int8)CdIsRemount(v27, p_CurrentIrp, &LowLimit) )
          {
            v34 = LowLimit;
            CdReMountOldVcb(v33, LowLimit, p_CurrentIrp, v6);
            v35 = *(_DWORD *)(v34 + 48);
            if ( (v35 & 0x100) != 0 )
            {
              *(_DWORD *)(v34 + 48) = v35 & 0xFFFFFEFF;
              Information = *(struct _FILE_OBJECT **)(*(_QWORD *)(v34 + 80) + 472LL);
              ObfReferenceObject(Information);
            }
          }
          else
          {
            CdUpdateVcbFromVolDescriptor(v3, (__int64)p_CurrentIrp, v4);
            v37 = p_CurrentIrp[10];
            if ( v37 )
            {
              Information = (struct _FILE_OBJECT *)v37[2].IoStatus.Information;
              ObfReferenceObject(Information);
            }
            if ( (int)CdPerformDevIoCtrl(v36, 266256, v6, (unsigned int)&v63, 24, Exclusive, 1, 0) < 0 )
            {
              *((_DWORD *)p_CurrentIrp + 137) = 27;
              *((_DWORD *)p_CurrentIrp + 138) = 16;
            }
            else
            {
              *((_DWORD *)p_CurrentIrp + 137) = DWORD1(v63) / 0x930;
              *((_DWORD *)p_CurrentIrp + 138) = DWORD2(v63);
            }
            *((_DWORD *)p_CurrentIrp + 15) -= 6;
            ObfDereferenceObject(p_CurrentIrp[2]);
            *((_DWORD *)p_CurrentIrp + 13) = 2;
            ExReleaseResourceLite((PERESOURCE)(p_CurrentIrp + 16));
            p_CurrentIrp = 0;
            v56 = 0;
          }
          v9 = 0;
          goto LABEL_65;
        }
        if ( (v26 & 1) != 0 )
        {
          v27 = p_CurrentIrp[65];
          if ( (*((_BYTE *)&v27->Size + 3) & 4) == 0 )
          {
            *((_DWORD *)p_CurrentIrp + 12) |= 0xC0u;
            if ( v4 )
            {
              ExFreePoolWithTag((PVOID)v4, 0);
              v51 = 0;
            }
            v4 = 0;
            v51 = 0;
            goto LABEL_41;
          }
        }
        v9 = -1073741489;
      }
    }
LABEL_65:
    if ( P )
      ExFreePoolWithTag(P, 0);
    if ( v4 )
      ExFreePoolWithTag((PVOID)v4, 0);
    if ( v9 && v41 )
      *(_DWORD *)(*(_QWORD *)(v3 + 40) + 48LL) |= 2u;
    if ( v55 )
      *(_QWORD *)(v55 + 8) = 0;
    if ( p_CurrentIrp )
    {
      *(_QWORD *)(v3 + 16) = 0;
      *((_DWORD *)p_CurrentIrp + 15) -= 6;
      if ( (unsigned __int8)CdDismountVcb(v3, p_CurrentIrp) )
        ExReleaseResourceLite((PERESOURCE)(p_CurrentIrp + 16));
    }
    else if ( DeviceObject )
    {
      IoDeleteDevice(DeviceObject);
    }
    ExReleaseResourceLite(&Resource);
    if ( Information )
    {
      FsRtlNotifyVolumeEvent(Information, 6u);
      ObfDereferenceObject(Information);
    }
    if ( (unsigned int)dword_140007020 > 5 )
    {
      HighLimit = 0;
      LowLimit = 0;
      IoGetStackLimits(&LowLimit, &HighLimit);
      if ( (unsigned __int64)&HighLimit - LowLimit >= 0x800 )
        CdTelemetryMount((int)v62);
      else
        _InterlockedIncrement((volatile signed __int32 *)&CdTelemetryData);
    }
    a2 = v2;
    a1 = v3;
    goto LABEL_3;
  }
  v11 = -1073741077;
LABEL_6:
  CdCompleteRequest(a1, a2, (unsigned int)v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400142d8  mov     r11, rsp
0x1400142db  mov     [r11+18h], rbx
0x1400142df  mov     [r11+20h], rsi
0x1400142e3  push    rdi
0x1400142e4  push    r12
0x1400142e6  push    r13
0x1400142e8  push    r14
0x1400142ea  push    r15
0x1400142ec  sub     rsp, 130h
0x1400142f3  mov     rax, cs:__security_cookie
0x1400142fa  xor     rax, rsp
0x1400142fd  mov     [rsp+158h+var_30], rax
0x140014305  mov     r12, rdx
0x140014308  mov     rsi, rcx
0x14001430b  mov     [rsp+158h+var_88], rcx
0x140014313  xor     r14d, r14d
0x140014316  mov     [rsp+158h+var_F8], r14
0x14001431b  mov     [r11-0C8h], r14
0x140014322  mov     rax, [rdx+0B8h]
0x140014329  mov     r13, [rax+10h]
0x14001432d  mov     rdi, [rax+8]
0x140014331  mov     [r11-0B0h], rdi
0x140014338  xorps   xmm0, xmm0
0x14001433b  xor     eax, eax
0x14001433d  movups  xmmword ptr [r11-48h], xmm0
0x140014342  mov     [r11-38h], rax
0x140014346  xorps   xmm1, xmm1
0x140014349  movups  xmmword ptr [r11-60h], xmm1
0x14001434e  mov     [r11-50h], rax
0x140014352  movups  xmmword ptr [r11-80h], xmm0
0x140014357  mov     [rsp+158h+var_DC], r14d
0x14001435c  mov     [rsp+158h+var_E0], r14d
0x140014361  mov     [rsp+158h+var_E4], r14d
0x140014366  mov     [rsp+158h+var_EC], r14d
0x14001436b  movups  xmmword ptr [r11-70h], xmm0
0x140014370  mov     rax, [rdi+10h]
0x140014374  mov     [rcx+28h], rax
0x140014378  mov     al, [rax+30h]
0x14001437b  shr     al, 1
0x14001437d  and     al, 1
0x14001437f  mov     [rsp+158h+var_107], al
0x140014383  cmp     cs:CdDisable, r14b
0x14001438a  jz      short loc_1400143C9
0x14001438c  mov     edi, 0C000014Fh
0x140014391  mov     r8d, edi
0x140014394  call    CdCompleteRequest
0x140014399  mov     eax, edi
0x14001439b  mov     rcx, [rsp+158h+var_30]
0x1400143a3  xor     rcx, rsp; StackCookie
0x1400143a6  call    __security_check_cookie
0x1400143ab  lea     r11, [rsp+158h+var_28]
0x1400143b3  mov     rbx, [r11+40h]
0x1400143b7  mov     rsi, [r11+48h]
0x1400143bb  mov     rsp, r11
0x1400143be  pop     r15
0x1400143c0  pop     r14
0x1400143c2  pop     r13
0x1400143c4  pop     r12
0x1400143c6  pop     rdi
0x1400143c7  retn
0x1400143c9  movzx   eax, cs:word_14000732E
0x1400143d0  test    al, 1
0x1400143d2  jz      short loc_1400143E5
0x1400143d4  mov     ebx, 0C00002EBh
0x1400143d9  mov     r8d, ebx
0x1400143dc  call    CdCompleteRequest
0x1400143e1  mov     eax, ebx
0x1400143e3  jmp     short loc_14001439B
0x1400143e5  lea     rax, [rsp+158h+var_80]
0x1400143ed  mov     [rsp+158h+var_110], rax
0x1400143f2  mov     byte ptr [rsp+158h+var_118], 1
0x1400143f7  mov     dword ptr [rsp+158h+DeviceObject], 4
0x1400143ff  lea     rax, [rsp+158h+var_EC]
0x140014404  mov     qword ptr [rsp+158h+Exclusive], rax
0x140014409  mov     [rsp+158h+DeviceCharacteristics], r14d
0x14001440e  xor     r9d, r9d
0x140014411  mov     r8, r13
0x140014414  mov     edx, 24800h
0x140014419  call    CdPerformDevIoCtrlEx
0x14001441e  mov     ebx, eax
0x140014420  test    eax, eax
0x140014422  jns     short loc_14001442C
0x140014424  mov     rdx, r12
0x140014427  mov     rcx, rsi
0x14001442a  jmp     short loc_1400143D9
0x14001442c  cmp     [rsp+158h+var_78], 4
0x140014435  jz      short loc_14001443C
0x140014437  mov     [rsp+158h+var_EC], r14d
0x14001443c  mov     [rsp+158h+var_110], r14
0x140014441  mov     byte ptr [rsp+158h+var_118], 1
0x140014446  mov     dword ptr [rsp+158h+DeviceObject], 18h
0x14001444e  lea     rax, [rsp+158h+var_48]
0x140014456  mov     qword ptr [rsp+158h+Exclusive], rax
0x14001445b  mov     [rsp+158h+DeviceCharacteristics], r14d
0x140014460  xor     r9d, r9d
0x140014463  mov     r8, r13
0x140014466  mov     edx, 2404Ch
0x14001446b  call    CdPerformDevIoCtrlEx
0x140014470  mov     [rsp+158h+var_104], eax
0x140014474  mov     ebx, 0C000009Ah
0x140014479  cmp     eax, ebx
0x14001447b  jz      short loc_140014424
0x14001447d  mov     [rsp+158h+var_90], rdi
0x140014485  mov     rbx, r14
0x140014488  mov     [rsp+158h+var_A8], rbx
0x140014490  mov     [rsp+158h+var_108], r14b
0x140014495  mov     r15, r14
0x140014498  mov     [rsp+158h+var_D0], r14
0x1400144a0  mov     [rsp+158h+var_B8], rbx
0x1400144a8  mov     [rsp+158h+var_E8], 1
0x1400144b0  test    eax, eax
0x1400144b2  js      short loc_1400144D2
0x1400144b4  mov     ecx, [rsp+158h+var_34]
0x1400144bb  lea     eax, [rcx-1]
0x1400144be  cmp     eax, 7FEh
0x1400144c3  ja      short loc_1400144D2
0x1400144c5  xor     edx, edx
0x1400144c7  mov     eax, 800h
0x1400144cc  div     ecx
0x1400144ce  mov     [rsp+158h+var_E8], eax
0x1400144d2  mov     dl, 1; Wait
0x1400144d4  lea     rcx, Resource; Resource
0x1400144db  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400144e2  nop     dword ptr [rax+rax+00h]
0x1400144e7  nop
0x1400144e8  mov     edx, 554h; NumberOfBytes
0x1400144ed  mov     ecx, 411h; PoolType
0x1400144f2  mov     r8d, 63746443h; Tag
0x1400144f8  call    cs:__imp_ExAllocatePoolWithTag
0x1400144ff  nop     dword ptr [rax+rax+00h]
0x140014504  mov     rdi, rax
0x140014507  mov     [rsp+158h+P], rax
0x14001450f  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140014516  jnz     short loc_14001452D
0x140014518  test    rax, rax
0x14001451b  jz      short loc_14001452D
0x14001451d  xor     edx, edx; Val
0x14001451f  mov     r8d, 554h; Size
0x140014525  mov     rcx, rax; void *
0x140014528  call    memset
0x14001452d  mov     [rsp+158h+var_B8], rdi
0x140014535  mov     rdi, cs:qword_1400072F0
0x14001453c  lea     rax, qword_1400072F0
0x140014543  cmp     rdi, rax
0x140014546  jz      short loc_140014571
0x140014548  lea     rdx, [rdi-20h]
0x14001454c  mov     rdi, [rdi]
0x14001454f  mov     ecx, [rdx+34h]
0x140014552  lea     eax, [rcx-3]
0x140014555  cmp     eax, 1
0x140014558  jbe     short loc_140014564
0x14001455a  test    ecx, ecx
0x14001455c  jnz     short loc_14001456F
0x14001455e  cmp     dword ptr [rdx+3Ch], 6
0x140014562  ja      short loc_14001456F
0x140014564  xor     r8d, r8d
0x140014567  mov     rcx, rsi
0x14001456a  call    CdCheckForDismount
0x14001456f  jmp     short loc_14001453C
0x140014571  lea     rax, [rsp+158h+var_F8]
0x140014576  mov     [rsp+158h+DeviceObject], rax; DeviceObject
0x14001457b  mov     [rsp+158h+Exclusive], 0; Exclusive
0x140014580  mov     [rsp+158h+DeviceCharacteristics], 0; DeviceCharacteristics
0x140014588  mov     r9d, 3; DeviceType
0x14001458e  xor     r8d, r8d; DeviceName
0x140014591  mov     edx, 340h; DeviceExtensionSize
0x140014596  mov     rcx, cs:DriverObject; DriverObject
0x14001459d  call    cs:__imp_IoCreateDevice
0x1400145a4  nop     dword ptr [rax+rax+00h]
0x1400145a9  mov     edi, eax
0x1400145ab  mov     [rsp+158h+var_104], eax
0x1400145af  test    eax, eax
0x1400145b1  js      loc_140014AD7
0x1400145b7  mov     eax, [r13+98h]
0x1400145be  mov     rcx, [rsp+158h+var_F8]
0x1400145c3  cmp     eax, [rcx+98h]
0x1400145c9  jbe     short loc_1400145D6
0x1400145cb  mov     [rcx+98h], eax
0x1400145d1  mov     rcx, [rsp+158h+var_F8]
0x1400145d6  mov     al, [r13+4Ch]
0x1400145da  inc     al
0x1400145dc  mov     [rcx+4Ch], al
0x1400145df  mov     rax, [rsp+158h+var_F8]
0x1400145e4  mov     cl, [rax+4Ch]
0x1400145e7  mov     [rsp+158h+var_100], cl
0x1400145eb  btr     dword ptr [rax+30h], 7
0x1400145f0  mov     rax, [rsp+158h+var_F8]
0x1400145f5  mov     dword ptr [rax+154h], 0
0x1400145ff  mov     rax, [rsp+158h+var_F8]
0x140014604  add     rax, 158h
0x14001460a  mov     [rax+8], rax
0x14001460e  mov     [rax], rax
0x140014611  mov     rax, [rsp+158h+var_F8]
0x140014616  mov     dword ptr [rax+150h], 0
0x140014620  mov     rcx, [rsp+158h+var_F8]
0x140014625  add     rcx, 168h; SpinLock
0x14001462c  call    cs:__imp_KeInitializeSpinLock
0x140014633  nop     dword ptr [rax+rax+00h]
0x140014638  lea     rax, [rsp+158h+var_E4]
0x14001463d  mov     qword ptr [rsp+158h+Exclusive], rax
0x140014642  lea     rax, [rsp+158h+var_E0]
0x140014647  mov     qword ptr [rsp+158h+DeviceCharacteristics], rax
0x14001464c  lea     r9, [rsp+158h+var_DC]
0x140014651  mov     r8, [rsp+158h+P]
0x140014659  mov     rdx, r13
0x14001465c  call    CdProcessToc
0x140014661  mov     edi, eax
0x140014663  mov     [rsp+158h+var_104], eax
0x140014667  test    eax, eax
0x140014669  jnz     loc_140014AD7
0x14001466f  mov     rax, [rsp+158h+var_F8]
0x140014674  mov     rcx, [rsp+158h+var_B0]
0x14001467c  mov     [rcx+8], rax
0x140014680  mov     rdx, [rsp+158h+var_F8]
0x140014685  add     rdx, 170h
0x14001468c  mov     eax, [rsp+158h+var_EC]
0x140014690  mov     dword ptr [rsp+158h+var_110], eax
0x140014694  mov     eax, [rsp+158h+var_E8]
0x140014698  mov     [rsp+158h+var_118], eax
0x14001469c  mov     edi, [rsp+158h+var_E4]
0x1400146a0  mov     dword ptr [rsp+158h+var_120], edi
0x1400146a4  mov     eax, [rsp+158h+var_E0]
0x1400146a8  mov     dword ptr [rsp+158h+DeviceObject], eax
0x1400146ac  mov     eax, [rsp+158h+var_DC]
0x1400146b0  mov     dword ptr [rsp+158h+Exclusive], eax
0x1400146b4  mov     rax, [rsp+158h+P]
0x1400146bc  mov     qword ptr [rsp+158h+DeviceCharacteristics], rax
0x1400146c1  mov     r9, rcx
0x1400146c4  mov     r8, r13
0x1400146c7  call    CdInitializeVcb
0x1400146cc  mov     rbx, [rsp+158h+var_F8]
0x1400146d1  add     rbx, 170h
0x1400146d8  mov     [rsp+158h+var_A8], rbx
0x1400146e0  mov     [rsp+158h+var_F8], 0
0x1400146e9  xor     eax, eax
0x1400146eb  mov     [rsp+158h+var_B0], rax
0x1400146f3  mov     [rsp+158h+var_90], rax
0x1400146fb  mov     [rsp+158h+P], rax
0x140014703  mov     [rsp+158h+var_B8], rax
0x14001470b  lea     rdx, [rsp+158h+var_70]
0x140014713  mov     rcx, [rbx+10h]
0x140014717  call    cs:__imp_FsRtlVolumeDeviceToCorrelationId
0x14001471e  nop     dword ptr [rax+rax+00h]
0x140014723  test    eax, eax
0x140014725  js      short loc_140014737
0x140014727  movups  xmm0, xmmword ptr [rsp+158h+var_70]
0x14001472f  movdqu  xmmword ptr [rbx+310h], xmm0
0x140014737  mov     [rsi+10h], rbx
0x14001473b  lea     rdx, [rbx+80h]
0x140014742  xor     r9d, r9d
0x140014745  xor     r8d, r8d
0x140014748  mov     rcx, rsi
0x14001474b  call    CdAcquireResource
0x140014750  mov     rax, [rbx+8]
0x140014754  inc     dword ptr [rax+1Ch]
0x140014757  mov     rax, [rbx+8]
0x14001475b  mov     rcx, [rax+10h]
0x14001475f  and     dword ptr [rcx+30h], 0FFFFFFFDh
0x140014763  mov     eax, [rbx+30h]
0x140014766  test    al, al
0x140014768  js      loc_14001482B
0x14001476e  mov     edx, 1000h; NumberOfBytes
0x140014773  mov     ecx, 610h; PoolType
0x140014778  mov     r8d, 64766443h; Tag
0x14001477e  call    cs:__imp_ExAllocatePoolWithTag
0x140014785  nop     dword ptr [rax+rax+00h]
0x14001478a  mov     r14, rax
0x14001478d  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140014794  jnz     short loc_1400147AB
0x140014796  test    rax, rax
0x140014799  jz      short loc_1400147AB
0x14001479b  xor     edx, edx; Val
0x14001479d  mov     r8d, 1000h; Size
0x1400147a3  mov     rcx, rax; void *
0x1400147a6  call    memset
0x1400147ab  mov     [rsp+158h+var_D0], r14
0x1400147b3  mov     [rsp+158h+Exclusive], 0
0x1400147b8  mov     byte ptr [rsp+158h+DeviceCharacteristics], 1
0x1400147bd  mov     r9d, [rsp+158h+var_E8]
0x1400147c2  mov     r8, r14
0x1400147c5  mov     rdx, rbx
0x1400147c8  mov     rcx, rsi
0x1400147cb  call    CdFindPrimaryVd
0x1400147d0  mov     [rsp+158h+var_108], al
0x1400147d4  mov     [rsp+158h+var_F0], al
0x1400147d8  test    al, al
0x1400147da  jnz     short loc_14001482B
0x1400147dc  test    dil, 1
0x1400147e0  jz      loc_140014919
0x1400147e6  mov     rcx, [rbx+208h]
0x1400147ed  test    byte ptr [rcx+5], 4
0x1400147f1  jnz     loc_140014919
0x1400147f7  or      dword ptr [rbx+30h], 0C0h
0x1400147fe  test    r14, r14
0x140014801  jz      short loc_140014820
0x140014803  xor     edx, edx; Tag
0x140014805  mov     rcx, r14; P
0x140014808  call    cs:__imp_ExFreePoolWithTag
0x14001480f  nop     dword ptr [rax+rax+00h]
0x140014814  mov     [rsp+158h+var_D0], 0
  ... truncated ...
```
