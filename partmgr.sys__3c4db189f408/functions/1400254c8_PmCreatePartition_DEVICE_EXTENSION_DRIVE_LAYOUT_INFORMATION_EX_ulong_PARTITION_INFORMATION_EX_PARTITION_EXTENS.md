# PmCreatePartition(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,ulong,_PARTITION_INFORMATION_EX *,_PARTITION_EXTENSION * *)

- ea: `0x1400254c8`
- end: `0x14002575a`
- name: `?PmCreatePartition@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@KPEAU_PARTITION_INFORMATION_EX@@PEAPEAU_PARTITION_EXTENSION@@@Z`
- size: `658`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT *, struct _DRIVE_LAYOUT_INFORMATION_EX *, int, struct _PARTITION_INFORMATION_EX *, struct _PARTITION_EXTENSION **)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x140005d78`
- `0x140008104`

## callees

- `0x14000c328`
- `0x14000c688`
- `0x14000d048`
- `0x140020550`
- `0x1400206f0`
- `0x14002096c`
- `0x1400254c8`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140025651`
- `ntoskrnl!KeInitializeEvent` at `0x140025651`
- `ntoskrnl!KeInitializeMutex` at `0x140025623`
- `ntoskrnl!KeInitializeMutex` at `0x140025623`
- `ntoskrnl!KeInitializeSpinLock` at `0x140025672`
- `ntoskrnl!KeInitializeSpinLock` at `0x140025672`
- `ntoskrnl!IoCreateDevice` at `0x140025539`
- `ntoskrnl!IoCreateDevice` at `0x140025539`
- `ntoskrnl!ExSizeOfRundownProtectionCacheAware` at `0x140025502`
- `ntoskrnl!ExSizeOfRundownProtectionCacheAware` at `0x140025502`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14002556f`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14002556f`
- `ntoskrnl!ExInitializeRundownProtectionCacheAware` at `0x140025639`
- `ntoskrnl!ExInitializeRundownProtectionCacheAware` at `0x140025639`

## pseudocode

```c
__int64 __fastcall PmCreatePartition(
        PDEVICE_OBJECT *a1,
        struct _DRIVE_LAYOUT_INFORMATION_EX *a2,
        int a3,
        struct _PARTITION_INFORMATION_EX *a4,
        struct _PARTITION_EXTENSION **a5)
{
  PDRIVER_OBJECT *DeviceExtension; // rbx
  unsigned int v10; // r15d
  NTSTATUS v11; // edi
  char *v12; // rbx
  PDEVICE_OBJECT AttachedDeviceReference; // rax
  PDEVICE_OBJECT v14; // rax
  PDEVICE_OBJECT DeviceObject; // [rsp+40h] [rbp-58h] BYREF

  DeviceObject = 0;
  DeviceExtension = (PDRIVER_OBJECT *)PmControlObject->DeviceExtension;
  *a5 = 0;
  v10 = ExSizeOfRundownProtectionCacheAware();
  v11 = IoCreateDevice(DeviceExtension[1], v10 + 456, 0, 0x2Du, 0x100u, 0, &DeviceObject);
  if ( v11 >= 0 )
  {
    v12 = (char *)DeviceObject->DeviceExtension;
    *(_QWORD *)v12 = &PartitionDispatch;
    *((_QWORD *)v12 + 1) = DeviceObject;
    AttachedDeviceReference = IoGetAttachedDeviceReference(a1[1]);
    *((_QWORD *)v12 + 3) = a1;
    *((_QWORD *)v12 + 2) = AttachedDeviceReference;
    *((_DWORD *)v12 + 40) = a3;
    *((_QWORD *)v12 + 50) = v12 + 456;
    *(_OWORD *)(v12 + 168) = *(_OWORD *)&a4->PartitionStyle;
    *(_OWORD *)(v12 + 184) = *(_OWORD *)&a4->PartitionLength.LowPart;
    *(_OWORD *)(v12 + 200) = *(_OWORD *)&a4->Mbr.PartitionType;
    *(GUID *)(v12 + 216) = a4->Gpt.PartitionId;
    *(_OWORD *)(v12 + 232) = *(_OWORD *)&a4->Gpt.Attributes;
    *(_OWORD *)(v12 + 248) = *(_OWORD *)&a4->Gpt.Name[4];
    *(_OWORD *)(v12 + 264) = *(_OWORD *)&a4->Gpt.Name[12];
    *(_OWORD *)(v12 + 280) = *(_OWORD *)&a4->Gpt.Name[20];
    *(_OWORD *)(v12 + 296) = *(_OWORD *)&a4->Gpt.Name[28];
    *((_QWORD *)v12 + 40) = v12 + 312;
    *((_QWORD *)v12 + 39) = v12 + 312;
    *((_QWORD *)v12 + 42) = v12 + 328;
    *((_QWORD *)v12 + 41) = v12 + 328;
    KeInitializeMutex((PRKMUTEX)(v12 + 344), 0);
    ExInitializeRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)v12 + 50), v10);
    KeInitializeEvent((PRKEVENT)v12 + 17, NotificationEvent, 0);
    *((_QWORD *)v12 + 55) = v12 + 432;
    *((_QWORD *)v12 + 54) = v12 + 432;
    KeInitializeSpinLock((PKSPIN_LOCK)v12 + 56);
    if ( (a1[1]->Characteristics & 1) != 0 && a4->PartitionStyle != PARTITION_STYLE_GPT && a4->PartitionNumber == 1 )
      *((_DWORD *)v12 + 10) |= 0x200u;
    v11 = PmBuildInstanceId((struct _DEVICE_EXTENSION *)a1, (struct _PARTITION_EXTENSION *)v12);
    if ( v11 < 0
      || (v11 = PmBuildStableGuid((struct _DEVICE_EXTENSION *)a1, (struct _PARTITION_EXTENSION *)v12), v11 < 0)
      || (v11 = PmBuildUniqueId((struct _DEVICE_EXTENSION *)a1, (struct _PARTITION_EXTENSION *)v12), v11 < 0) )
    {
      if ( v12 )
        PmDeletePartition((struct _PARTITION_EXTENSION *)v12);
    }
    else
    {
      PmIsConversionInProgress((struct _DEVICE_EXTENSION *)a1, (struct _PARTITION_EXTENSION *)v12);
      PmSetPartitionFlags((struct _PARTITION_EXTENSION *)v12, a2);
      v14 = a1[1];
      *a5 = (struct _PARTITION_EXTENSION *)v12;
      DeviceObject->DeviceType = v14->DeviceType;
      DeviceObject->StackSize = *(_BYTE *)(*((_QWORD *)v12 + 2) + 76LL) + 1;
      DeviceObject->AlignmentRequirement = *(_DWORD *)(*((_QWORD *)v12 + 2) + 152LL);
      DeviceObject->SectorSize = *(_WORD *)(*((_QWORD *)v12 + 2) + 304LL);
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400254c8  push    rbx
0x1400254ca  push    rbp
0x1400254cb  push    rsi
0x1400254cc  push    rdi
0x1400254cd  push    r12
0x1400254cf  push    r13
0x1400254d1  push    r14
0x1400254d3  push    r15
0x1400254d5  sub     rsp, 58h
0x1400254d9  mov     rax, cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * PmControlObject
0x1400254e0  xor     edi, edi
0x1400254e2  mov     r14, [rsp+98h+arg_20]
0x1400254ea  mov     rbp, r9
0x1400254ed  mov     r13d, r8d
0x1400254f0  mov     [rsp+98h+var_58], rdi
0x1400254f5  mov     r12, rdx
0x1400254f8  mov     rsi, rcx
0x1400254fb  mov     rbx, [rax+40h]
0x1400254ff  mov     [r14], rdi
0x140025502  call    cs:__imp_ExSizeOfRundownProtectionCacheAware
0x140025509  nop     dword ptr [rax+rax+00h]
0x14002550e  mov     rcx, [rbx+8]; DriverObject
0x140025512  lea     r9d, [rdi+2Dh]; DeviceType
0x140025516  mov     r15, rax
0x140025519  xor     r8d, r8d; DeviceName
0x14002551c  lea     edx, [rax+1C8h]; DeviceExtensionSize
0x140025522  lea     rax, [rsp+98h+var_58]
0x140025527  mov     [rsp+98h+DeviceObject], rax; DeviceObject
0x14002552c  mov     [rsp+98h+Exclusive], dil; Exclusive
0x140025531  mov     [rsp+98h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x140025539  call    cs:__imp_IoCreateDevice
0x140025540  nop     dword ptr [rax+rax+00h]
0x140025545  mov     edi, eax
0x140025547  test    eax, eax
0x140025549  js      loc_140025746
0x14002554f  mov     rcx, [rsp+98h+var_58]
0x140025554  lea     rax, ?PartitionDispatch@@3QBQ6AJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@ZB; long (*const near * const PartitionDispatch)(_DEVICE_OBJECT *,_IRP *)
0x14002555b  mov     rbx, [rcx+40h]
0x14002555f  mov     [rbx], rax
0x140025562  mov     rax, [rsp+98h+var_58]
0x140025567  mov     [rbx+8], rax
0x14002556b  mov     rcx, [rsi+8]; DeviceObject
0x14002556f  call    cs:__imp_IoGetAttachedDeviceReference
0x140025576  nop     dword ptr [rax+rax+00h]
0x14002557b  mov     [rbx+18h], rsi
0x14002557f  lea     rcx, [rbx+158h]; Mutex
0x140025586  mov     [rbx+10h], rax
0x14002558a  xor     edx, edx; Level
0x14002558c  mov     [rbx+0A0h], r13d
0x140025593  lea     rax, [rbx+1C8h]
0x14002559a  mov     [rbx+190h], rax
0x1400255a1  lea     rax, [rbx+138h]
0x1400255a8  movups  xmm0, xmmword ptr [rbp+0]
0x1400255ac  movups  xmmword ptr [rbx+0A8h], xmm0
0x1400255b3  movups  xmm1, xmmword ptr [rbp+10h]
0x1400255b7  movups  xmmword ptr [rbx+0B8h], xmm1
0x1400255be  movups  xmm0, xmmword ptr [rbp+20h]
0x1400255c2  movups  xmmword ptr [rbx+0C8h], xmm0
0x1400255c9  movups  xmm1, xmmword ptr [rbp+30h]
0x1400255cd  movups  xmmword ptr [rbx+0D8h], xmm1
0x1400255d4  movups  xmm0, xmmword ptr [rbp+40h]
0x1400255d8  movups  xmmword ptr [rbx+0E8h], xmm0
0x1400255df  movups  xmm1, xmmword ptr [rbp+50h]
0x1400255e3  movups  xmmword ptr [rbx+0F8h], xmm1
0x1400255ea  movups  xmm0, xmmword ptr [rbp+60h]
0x1400255ee  movups  xmmword ptr [rbx+108h], xmm0
0x1400255f5  movups  xmm1, xmmword ptr [rbp+70h]
0x1400255f9  movups  xmmword ptr [rbx+118h], xmm1
0x140025600  movups  xmm0, xmmword ptr [rbp+80h]
0x140025607  movups  xmmword ptr [rbx+128h], xmm0
0x14002560e  mov     [rax+8], rax
0x140025612  mov     [rax], rax
0x140025615  lea     rax, [rbx+148h]
0x14002561c  mov     [rax+8], rax
0x140025620  mov     [rax], rax
0x140025623  call    cs:__imp_KeInitializeMutex
0x14002562a  nop     dword ptr [rax+rax+00h]
0x14002562f  mov     rcx, [rbx+190h]; RunRefCacheAware
0x140025636  mov     edx, r15d; RunRefSize
0x140025639  call    cs:__imp_ExInitializeRundownProtectionCacheAware
0x140025640  nop     dword ptr [rax+rax+00h]
0x140025645  lea     rcx, [rbx+198h]; Event
0x14002564c  xor     r8d, r8d; State
0x14002564f  xor     edx, edx; Type
0x140025651  call    cs:__imp_KeInitializeEvent
0x140025658  nop     dword ptr [rax+rax+00h]
0x14002565d  lea     rax, [rbx+1B0h]
0x140025664  lea     rcx, [rbx+1C0h]; SpinLock
0x14002566b  mov     [rax+8], rax
0x14002566f  mov     [rax], rax
0x140025672  call    cs:__imp_KeInitializeSpinLock
0x140025679  nop     dword ptr [rax+rax+00h]
0x14002567e  mov     rax, [rsi+8]
0x140025682  mov     ecx, [rax+34h]
0x140025685  test    cl, 1
0x140025688  jz      short loc_14002569B
0x14002568a  cmp     dword ptr [rbp+0], 1
0x14002568e  jz      short loc_14002569B
0x140025690  cmp     dword ptr [rbp+18h], 1
0x140025694  jnz     short loc_14002569B
0x140025696  bts     dword ptr [rbx+28h], 9
0x14002569b  mov     rdx, rbx; struct _PARTITION_EXTENSION *
0x14002569e  mov     rcx, rsi; struct _DEVICE_EXTENSION *
0x1400256a1  call    ?PmBuildInstanceId@@YAJPEAU_DEVICE_EXTENSION@@PEAU_PARTITION_EXTENSION@@@Z; PmBuildInstanceId(_DEVICE_EXTENSION *,_PARTITION_EXTENSION *)
0x1400256a6  mov     edi, eax
0x1400256a8  test    eax, eax
0x1400256aa  js      loc_140025739
0x1400256b0  mov     rdx, rbx; struct _PARTITION_EXTENSION *
0x1400256b3  mov     rcx, rsi; struct _DEVICE_EXTENSION *
0x1400256b6  call    ?PmBuildStableGuid@@YAJPEAU_DEVICE_EXTENSION@@PEAU_PARTITION_EXTENSION@@@Z; PmBuildStableGuid(_DEVICE_EXTENSION *,_PARTITION_EXTENSION *)
0x1400256bb  mov     edi, eax
0x1400256bd  test    eax, eax
0x1400256bf  js      short loc_140025739
0x1400256c1  mov     rdx, rbx; struct _PARTITION_EXTENSION *
0x1400256c4  mov     rcx, rsi; struct _DEVICE_EXTENSION *
0x1400256c7  call    ?PmBuildUniqueId@@YAJPEAU_DEVICE_EXTENSION@@PEAU_PARTITION_EXTENSION@@@Z; PmBuildUniqueId(_DEVICE_EXTENSION *,_PARTITION_EXTENSION *)
0x1400256cc  mov     edi, eax
0x1400256ce  test    eax, eax
0x1400256d0  js      short loc_140025739
0x1400256d2  mov     rdx, rbx; struct _PARTITION_EXTENSION *
0x1400256d5  mov     rcx, rsi; struct _DEVICE_EXTENSION *
0x1400256d8  call    ?PmIsConversionInProgress@@YAJPEAU_DEVICE_EXTENSION@@PEAU_PARTITION_EXTENSION@@@Z; PmIsConversionInProgress(_DEVICE_EXTENSION *,_PARTITION_EXTENSION *)
0x1400256dd  mov     rdx, r12; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x1400256e0  mov     rcx, rbx; struct _PARTITION_EXTENSION *
0x1400256e3  call    ?PmSetPartitionFlags@@YAXPEAU_PARTITION_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmSetPartitionFlags(_PARTITION_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *)
0x1400256e8  mov     rax, [rsi+8]
0x1400256ec  mov     [r14], rbx
0x1400256ef  mov     ecx, [rax+48h]
0x1400256f2  mov     rax, [rsp+98h+var_58]
0x1400256f7  mov     [rax+48h], ecx
0x1400256fa  mov     rax, [rbx+10h]
0x1400256fe  mov     cl, [rax+4Ch]
0x140025701  mov     rax, [rsp+98h+var_58]
0x140025706  inc     cl
0x140025708  mov     [rax+4Ch], cl
0x14002570b  mov     rax, [rbx+10h]
0x14002570f  mov     ecx, [rax+98h]
0x140025715  mov     rax, [rsp+98h+var_58]
0x14002571a  mov     [rax+98h], ecx
0x140025720  mov     rax, [rbx+10h]
0x140025724  movzx   ecx, word ptr [rax+130h]
0x14002572b  mov     rax, [rsp+98h+var_58]
0x140025730  mov     [rax+130h], cx
0x140025737  jmp     short loc_140025746
0x140025739  test    rbx, rbx
0x14002573c  jz      short loc_140025746
0x14002573e  mov     rcx, rbx; struct _PARTITION_EXTENSION *
0x140025741  call    ?PmDeletePartition@@YAXPEAU_PARTITION_EXTENSION@@@Z; PmDeletePartition(_PARTITION_EXTENSION *)
0x140025746  mov     eax, edi
0x140025748  add     rsp, 58h
0x14002574c  pop     r15
0x14002574e  pop     r14
0x140025750  pop     r13
0x140025752  pop     r12
0x140025754  pop     rdi
0x140025755  pop     rsi
0x140025756  pop     rbp
0x140025757  pop     rbx
0x140025758  retn
```
