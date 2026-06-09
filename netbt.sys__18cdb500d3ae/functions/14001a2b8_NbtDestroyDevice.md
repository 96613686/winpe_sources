# NbtDestroyDevice

- ea: `0x14001a2b8`
- end: `0x14001a77a`
- name: `NbtDestroyDevice`
- size: `1218`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject)`
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x14002ca6c`
- `0x14002cbc4`
- `0x14002cda0`
- `0x1400471c0`

## callees

- `0x140005fb0`
- `0x140006900`
- `0x14000dc40`
- `0x140015340`
- `0x14001a2b8`
- `0x14001a7c8`
- `0x140030f80`
- `0x140040294`
- `0x140041c38`
- `0x140042bf8`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x14001a54f`
- `ntoskrnl!KeCancelTimer` at `0x14001a54f`
- `ntoskrnl!IoDeleteDevice` at `0x14001a485`
- `ntoskrnl!IoDeleteDevice` at `0x14001a485`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a404`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a428`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a404`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a428`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a2de`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a5a1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a6b1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a2de`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a5a1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a6b1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a3be`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a513`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a575`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a64b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a764`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a3be`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a513`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a575`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a64b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a764`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a476`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a476`

## pseudocode

```c
__int64 __fastcall NbtDestroyDevice(PDEVICE_OBJECT DeviceObject, char a2)
{
  KIRQL v4; // al
  __int64 v5; // r8
  char *p_DriverObject; // rsi
  struct _DRIVER_OBJECT *DriverObject; // rax
  struct _DEVICE_OBJECT *NextDevice; // rcx
  char v9; // di
  bool v10; // zf
  __int64 v11; // r8
  KIRQL v12; // bp
  struct _KTIMER *i; // rdi
  int v14; // edx
  int v15; // ecx
  int v16; // r8d
  __int64 v17; // rcx
  struct _DEVICE_OBJECT *v18; // rax
  PKDEFERRED_ROUTINE DeferredRoutine; // rcx
  struct _DEVICE_OBJECT *v21; // rax
  char Blink_high; // al
  struct _LIST_ENTRY *Flink; // r14
  __int64 v24; // r15
  struct _LIST_ENTRY *v25; // rax
  PDEVICE_OBJECT v26; // rdi
  __int64 v27; // rcx
  struct _LIST_ENTRY *Blink; // rax
  __int64 v29; // rdx
  struct _KDPC *Dpc; // rcx
  KIRQL NewIrql; // [rsp+60h] [rbp+8h] BYREF

  v4 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  NewIrql = v4;
  if ( DeviceObject && LODWORD(DeviceObject[1].AttachedDevice) == 1131832644 )
  {
    p_DriverObject = (char *)&DeviceObject[1].DriverObject;
    DriverObject = DeviceObject[1].DriverObject;
    if ( DriverObject->DeviceObject == (PDEVICE_OBJECT)&DeviceObject[1].DriverObject )
    {
      NextDevice = DeviceObject[1].NextDevice;
      if ( *(char **)&NextDevice->Type == p_DriverObject )
      {
        *(_QWORD *)&NextDevice->Type = DriverObject;
        v9 = 0;
        DriverObject->DeviceObject = NextDevice;
        if ( DeviceObject[1].ReferenceCount != 1 && HIDWORD(DeviceObject[2].AttachedDevice) != -1 )
        {
          DeferredRoutine = DeviceObject[1].Dpc.DeferredRoutine;
          if ( ((unsigned __int64)DeferredRoutine & qword_140039740) != 0 )
          {
            v9 = 1;
            qword_140039740 &= ~(unsigned __int64)DeferredRoutine;
          }
          qword_140039748 &= ~(__int64)DeviceObject[1].Dpc.DeferredRoutine;
        }
        v10 = DeviceObject[1].ReferenceCount == 1;
        LODWORD(DeviceObject[1].AttachedDevice) = 846619972;
        if ( !v10 )
          qword_1400395C8 &= ~(__int64)DeviceObject[1].Dpc.DeferredRoutine;
        LOBYTE(v5) = 1;
        TimeoutLmHRequests(0, DeviceObject, v5, &NewIrql);
        if ( v9
          && pNbtSmbDevice
          && !gbDestroyingSmbDevice
          && (LOBYTE(v11) = 1, (unsigned __int8)NBT_REFERENCE_DEVICE(pNbtSmbDevice, 15, v11)) )
        {
          v26 = pNbtSmbDevice;
          KeReleaseSpinLock(&SpinLock, NewIrql);
          if ( v26[1].DeviceLock.Header.WaitListHead.Flink )
            NbtSetTcpInfo(*(PFILE_OBJECT *)&v26[1].SectorSize);
          v27 = *(_QWORD *)&v26[1].DeviceLock.Header.Lock;
          if ( v27 && *(_QWORD *)(v27 + 32) )
            NbtSetTcpInfo(*(PFILE_OBJECT *)(v27 + 48));
          v12 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
          NBT_DEREFERENCE_DEVICE(v26, 15);
        }
        else
        {
          v12 = NewIrql;
        }
LABEL_10:
        for ( i = (struct _KTIMER *)TimerQ; i != (struct _KTIMER *)&TimerQ; i = *(struct _KTIMER **)&i->Header.Lock )
        {
          if ( (PDEVICE_OBJECT)i->TimerListEntry.Flink == DeviceObject )
          {
            Blink_high = HIBYTE(i->Header.WaitListHead.Blink);
            if ( Blink_high == 1 )
            {
              v10 = (i[4].Header.Type & 8) == 0;
              Flink = i[1].Header.WaitListHead.Flink;
              v24 = *(_QWORD *)&i[1].Header.Lock;
              i[1].Header.WaitListHead.Flink = 0;
              if ( v10 && !KeCancelTimer(i + 3) )
              {
                Blink = i->TimerListEntry.Blink;
                if ( Blink )
                {
                  v29 = *(_QWORD *)&i->Processor;
                  Dpc = i->Dpc;
                  i->TimerListEntry.Blink = 0;
                  ((void (__fastcall *)(struct _KDPC *, __int64, _QWORD))Blink)(Dpc, v29, 0);
                }
                HIBYTE(i->Header.WaitListHead.Blink) = 2;
              }
              else
              {
                CleanupCTETimer(i);
              }
            }
            else
            {
              v24 = 0;
              Flink = 0;
              if ( Blink_high == 2 )
              {
                v25 = i[1].Header.WaitListHead.Flink;
                if ( v25 )
                {
                  v24 = *(_QWORD *)&i[1].Header.Lock;
                  i[1].Header.WaitListHead.Flink = 0;
                  Flink = v25;
                }
                HIBYTE(i->Header.WaitListHead.Blink) = 3;
              }
            }
            KeReleaseSpinLock(&SpinLock, v12);
            if ( Flink )
              ((void (__fastcall *)(__int64, __int64))Flink)(v24, 258);
            if ( (xmmword_140038420 & 8) != 0 )
              WPP_SF_(1027, 27, WPP_6fbf3721221234eecc9a3cdb64421ce5_Traceguids);
            v12 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
            goto LABEL_10;
          }
        }
        NBT_DEREFERENCE_DEVICE(DeviceObject, 14);
        if ( a2 )
        {
          DeviceObject[1].NextDevice = (PDEVICE_OBJECT)((char *)DeviceObject + 344);
          *(_QWORD *)p_DriverObject = p_DriverObject;
          KeReleaseSpinLock(&SpinLock, v12);
          if ( (BYTE3(xmmword_140038420) & 1) != 0 )
            WPP_SF_qZ(v15, v14, v16, (_DWORD)DeviceObject, (__int64)&DeviceObject[1].Queue.Wcb.CurrentIrp);
          qword_140038770 = (__int64)DeviceObject[1].DeviceLock.Header.WaitListHead.Blink;
          KeWaitForSingleObject(&DeviceObject[2], Executive, 0, 0, 0);
          KeWaitForSingleObject(&DeviceObject[3].Flags, Executive, 0, 0, 0);
          if ( (BYTE3(xmmword_140038420) & 1) != 0 )
            WPP_SF_Z(1048, 29, WPP_6fbf3721221234eecc9a3cdb64421ce5_Traceguids, &DeviceObject[1].Queue.Wcb.CurrentIrp);
          qword_140038770 = 0;
          v17 = *(_QWORD *)p_DriverObject;
          if ( *(char **)(*(_QWORD *)p_DriverObject + 8LL) == p_DriverObject )
          {
            v18 = DeviceObject[1].NextDevice;
            if ( *(char **)&v18->Type == p_DriverObject )
            {
              *(_QWORD *)&v18->Type = v17;
              *(_QWORD *)(v17 + 8) = v18;
              ExFreePoolWithTag(DeviceObject[1].Queue.Wcb.BufferChainingDpc, 0);
              IoDeleteDevice(DeviceObject);
              return 0;
            }
          }
        }
        else
        {
          v21 = (struct _DEVICE_OBJECT *)qword_140039458;
          if ( *(__int64 **)qword_140039458 == &qword_140039450 )
          {
            *(_QWORD *)p_DriverObject = &qword_140039450;
            DeviceObject[1].NextDevice = v21;
            *(_QWORD *)&v21->Type = p_DriverObject;
            qword_140039458 = (__int64)&DeviceObject[1].DriverObject;
            KeReleaseSpinLock(&SpinLock, v12);
            return 0;
          }
        }
      }
    }
    __fastfail(3u);
  }
  KeReleaseSpinLock(&SpinLock, v4);
  return 3221225488LL;
}

```

## disassembly

```asm
0x14001a2b8  mov     [rsp+arg_8], rbx
0x14001a2bd  mov     [rsp+arg_10], rbp
0x14001a2c2  push    rsi
0x14001a2c3  push    rdi
0x14001a2c4  push    r12
0x14001a2c6  push    r14
0x14001a2c8  push    r15
0x14001a2ca  sub     rsp, 30h
0x14001a2ce  mov     rbx, rcx
0x14001a2d1  lea     r14, SpinLock
0x14001a2d8  mov     rcx, r14; SpinLock
0x14001a2db  mov     r12b, dl
0x14001a2de  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001a2e5  nop     dword ptr [rax+rax+00h]
0x14001a2ea  mov     [rsp+58h+NewIrql], al
0x14001a2ee  test    rbx, rbx
0x14001a2f1  jz      loc_14001A75F
0x14001a2f7  cmp     dword ptr [rbx+168h], 43766544h
0x14001a301  jnz     loc_14001A75F
0x14001a307  lea     rsi, [rbx+158h]
0x14001a30e  mov     rax, [rsi]
0x14001a311  cmp     [rax+8], rsi
0x14001a315  jnz     loc_14001A5D9
0x14001a31b  mov     rcx, [rsi+8]
0x14001a31f  cmp     [rcx], rsi
0x14001a322  jnz     loc_14001A5D9
0x14001a328  mov     [rcx], rax
0x14001a32b  xor     dil, dil
0x14001a32e  mov     [rax+8], rcx
0x14001a332  cmp     dword ptr [rbx+154h], 1
0x14001a339  jnz     loc_14001A4AB
0x14001a33f  cmp     dword ptr [rbx+154h], 1
0x14001a346  mov     dword ptr [rbx+168h], 32766544h
0x14001a350  jnz     loc_14001A5F5
0x14001a356  lea     r9, [rsp+58h+NewIrql]
0x14001a35b  mov     r8b, 1
0x14001a35e  mov     rdx, rbx
0x14001a361  xor     ecx, ecx
0x14001a363  call    TimeoutLmHRequests
0x14001a368  test    dil, dil
0x14001a36b  jnz     loc_14001A60B
0x14001a371  mov     bpl, [rsp+58h+NewIrql]
0x14001a376  mov     rdi, cs:TimerQ
0x14001a37d  lea     rax, TimerQ
0x14001a384  cmp     rdi, rax
0x14001a387  jz      short loc_14001A398
0x14001a389  cmp     [rdi+20h], rbx
0x14001a38d  jz      loc_14001A524
0x14001a393  mov     rdi, [rdi]
0x14001a396  jmp     short loc_14001A384
0x14001a398  mov     r8b, 1
0x14001a39b  mov     edx, 0Eh
0x14001a3a0  mov     rcx, rbx
0x14001a3a3  call    NBT_DEREFERENCE_DEVICE
0x14001a3a8  test    r12b, r12b
0x14001a3ab  jz      loc_14001A4E5
0x14001a3b1  mov     dl, bpl; NewIrql
0x14001a3b4  mov     [rsi+8], rsi
0x14001a3b8  mov     rcx, r14; SpinLock
0x14001a3bb  mov     [rsi], rsi
0x14001a3be  call    cs:__imp_KeReleaseSpinLock
0x14001a3c5  nop     dword ptr [rax+rax+00h]
0x14001a3ca  test    byte ptr cs:xmmword_140038420+3, 1
0x14001a3d1  lea     rdi, [rbx+1D8h]
0x14001a3d8  jnz     loc_14001A72F
0x14001a3de  mov     rax, [rbx+278h]
0x14001a3e5  lea     rcx, [rbx+2A0h]; Object
0x14001a3ec  xor     r9d, r9d; Alertable
0x14001a3ef  mov     cs:qword_140038770, rax
0x14001a3f6  xor     r8d, r8d; WaitMode
0x14001a3f9  mov     [rsp+58h+Timeout], 0; Timeout
0x14001a402  xor     edx, edx; WaitReason
0x14001a404  call    cs:__imp_KeWaitForSingleObject
0x14001a40b  nop     dword ptr [rax+rax+00h]
0x14001a410  lea     rcx, [rbx+420h]; Object
0x14001a417  mov     [rsp+58h+Timeout], 0; Timeout
0x14001a420  xor     r9d, r9d; Alertable
0x14001a423  xor     r8d, r8d; WaitMode
0x14001a426  xor     edx, edx; WaitReason
0x14001a428  call    cs:__imp_KeWaitForSingleObject
0x14001a42f  nop     dword ptr [rax+rax+00h]
0x14001a434  test    byte ptr cs:xmmword_140038420+3, 1
0x14001a43b  jnz     loc_14001A741
0x14001a441  mov     cs:qword_140038770, 0
0x14001a44c  mov     rcx, [rsi]
0x14001a44f  cmp     [rcx+8], rsi
0x14001a453  jnz     loc_14001A5D9
0x14001a459  mov     rax, [rsi+8]
0x14001a45d  cmp     [rax], rsi
0x14001a460  jnz     loc_14001A5D9
0x14001a466  mov     [rax], rcx
0x14001a469  xor     edx, edx; Tag
0x14001a46b  mov     [rcx+8], rax
0x14001a46f  mov     rcx, [rbx+1E0h]; P
0x14001a476  call    cs:__imp_ExFreePoolWithTag
0x14001a47d  nop     dword ptr [rax+rax+00h]
0x14001a482  mov     rcx, rbx; DeviceObject
0x14001a485  call    cs:__imp_IoDeleteDevice
0x14001a48c  nop     dword ptr [rax+rax+00h]
0x14001a491  xor     eax, eax
0x14001a493  mov     rbx, [rsp+58h+arg_8]
0x14001a498  mov     rbp, [rsp+58h+arg_10]
0x14001a49d  add     rsp, 30h
0x14001a4a1  pop     r15
0x14001a4a3  pop     r14
0x14001a4a5  pop     r12
0x14001a4a7  pop     rdi
0x14001a4a8  pop     rsi
0x14001a4a9  retn
0x14001a4ab  cmp     dword ptr [rbx+2BCh], 0FFFFFFFFh
0x14001a4b2  jz      loc_14001A33F
0x14001a4b8  mov     rcx, [rbx+230h]
0x14001a4bf  mov     rax, cs:qword_140039740
0x14001a4c6  test    rax, rcx
0x14001a4c9  jnz     loc_14001A5E0
0x14001a4cf  mov     rax, [rbx+230h]
0x14001a4d6  not     rax
0x14001a4d9  and     cs:qword_140039748, rax
0x14001a4e0  jmp     loc_14001A33F
0x14001a4e5  mov     rax, cs:qword_140039458
0x14001a4ec  lea     rcx, qword_140039450
0x14001a4f3  cmp     [rax], rcx
0x14001a4f6  jnz     loc_14001A5D9
0x14001a4fc  mov     [rsi], rcx
0x14001a4ff  mov     dl, bpl; NewIrql
0x14001a502  mov     [rsi+8], rax
0x14001a506  mov     rcx, r14; SpinLock
0x14001a509  mov     [rax], rsi
0x14001a50c  mov     cs:qword_140039458, rsi
0x14001a513  call    cs:__imp_KeReleaseSpinLock
0x14001a51a  nop     dword ptr [rax+rax+00h]
0x14001a51f  jmp     loc_14001A491
0x14001a524  mov     al, [rdi+17h]
0x14001a527  cmp     al, 1
0x14001a529  jnz     loc_14001A5B5
0x14001a52f  test    byte ptr [rdi+100h], 8
0x14001a536  mov     r14, [rdi+48h]
0x14001a53a  mov     r15, [rdi+40h]
0x14001a53e  mov     qword ptr [rdi+48h], 0
0x14001a546  jnz     short loc_14001A563
0x14001a548  lea     rcx, [rdi+0C0h]; PKTIMER
0x14001a54f  call    cs:__imp_KeCancelTimer
0x14001a556  nop     dword ptr [rax+rax+00h]
0x14001a55b  test    al, al
0x14001a55d  jz      loc_14001A6D5
0x14001a563  mov     rcx, rdi; Entry
0x14001a566  call    CleanupCTETimer
0x14001a56b  mov     dl, bpl; NewIrql
0x14001a56e  lea     rcx, SpinLock; SpinLock
0x14001a575  call    cs:__imp_KeReleaseSpinLock
0x14001a57c  nop     dword ptr [rax+rax+00h]
0x14001a581  test    r14, r14
0x14001a584  jnz     loc_14001A6FF
0x14001a58a  test    byte ptr cs:xmmword_140038420, 8
0x14001a591  jnz     loc_14001A714
0x14001a597  lea     r14, SpinLock
0x14001a59e  mov     rcx, r14; SpinLock
0x14001a5a1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001a5a8  nop     dword ptr [rax+rax+00h]
0x14001a5ad  mov     bpl, al
0x14001a5b0  jmp     loc_14001A376
0x14001a5b5  xor     r15d, r15d
0x14001a5b8  xor     r14d, r14d
0x14001a5bb  cmp     al, 2
0x14001a5bd  jnz     short loc_14001A56B
0x14001a5bf  mov     rax, [rdi+48h]
0x14001a5c3  test    rax, rax
0x14001a5c6  jz      short loc_14001A5D3
0x14001a5c8  mov     r15, [rdi+40h]
0x14001a5cc  mov     [rdi+48h], r14
0x14001a5d0  mov     r14, rax
0x14001a5d3  mov     byte ptr [rdi+17h], 3
0x14001a5d7  jmp     short loc_14001A56B
0x14001a5d9  mov     ecx, 3
0x14001a5de  int     29h; Win8: RtlFailFast(ecx)
0x14001a5e0  not     rcx
0x14001a5e3  mov     dil, 1
0x14001a5e6  and     rax, rcx
0x14001a5e9  mov     cs:qword_140039740, rax
0x14001a5f0  jmp     loc_14001A4CF
0x14001a5f5  mov     rax, [rbx+230h]
0x14001a5fc  not     rax
0x14001a5ff  and     cs:qword_1400395C8, rax
0x14001a606  jmp     loc_14001A356
0x14001a60b  mov     rcx, cs:pNbtSmbDevice
0x14001a612  test    rcx, rcx
0x14001a615  jz      loc_14001A371
0x14001a61b  cmp     cs:gbDestroyingSmbDevice, 0
0x14001a622  jnz     loc_14001A371
0x14001a628  mov     r8b, 1
0x14001a62b  mov     edx, 0Fh
0x14001a630  call    NBT_REFERENCE_DEVICE
0x14001a635  test    al, al
0x14001a637  jz      loc_14001A371
0x14001a63d  mov     dl, [rsp+58h+NewIrql]; NewIrql
0x14001a641  mov     rcx, r14; SpinLock
0x14001a644  mov     rdi, cs:pNbtSmbDevice
0x14001a64b  call    cs:__imp_KeReleaseSpinLock
0x14001a652  nop     dword ptr [rax+rax+00h]
0x14001a657  cmp     qword ptr [rdi+270h], 0
0x14001a65f  mov     ebp, 200h
0x14001a664  mov     r15d, 1Ah
0x14001a66a  jz      short loc_14001A685
0x14001a66c  mov     r9d, [rbx+2BCh]
0x14001a673  mov     r8d, ebp
0x14001a676  mov     rcx, [rdi+280h]; FileObject
0x14001a67d  mov     edx, r15d
0x14001a680  call    NbtSetTcpInfo
0x14001a685  mov     rcx, [rdi+268h]
0x14001a68c  test    rcx, rcx
0x14001a68f  jz      short loc_14001A6AE
0x14001a691  cmp     qword ptr [rcx+20h], 0
0x14001a696  jz      short loc_14001A6AE
0x14001a698  mov     r9d, [rbx+2BCh]
0x14001a69f  mov     r8d, ebp
0x14001a6a2  mov     rcx, [rcx+30h]; FileObject
0x14001a6a6  mov     edx, r15d
0x14001a6a9  call    NbtSetTcpInfo
0x14001a6ae  mov     rcx, r14; SpinLock
0x14001a6b1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001a6b8  nop     dword ptr [rax+rax+00h]
0x14001a6bd  mov     r8b, 1
0x14001a6c0  mov     edx, 0Fh
0x14001a6c5  mov     rcx, rdi
0x14001a6c8  mov     bpl, al
0x14001a6cb  call    NBT_DEREFERENCE_DEVICE
0x14001a6d0  jmp     loc_14001A376
0x14001a6d5  mov     rax, [rdi+28h]
0x14001a6d9  test    rax, rax
0x14001a6dc  jz      short loc_14001A6F6
0x14001a6de  mov     rdx, [rdi+38h]
0x14001a6e2  xor     r8d, r8d
0x14001a6e5  mov     rcx, [rdi+30h]
0x14001a6e9  mov     qword ptr [rdi+28h], 0
0x14001a6f1  call    _guard_dispatch_icall
0x14001a6f6  mov     byte ptr [rdi+17h], 2
0x14001a6fa  jmp     loc_14001A56B
0x14001a6ff  mov     edx, 102h
0x14001a704  mov     rcx, r15
0x14001a707  mov     rax, r14
0x14001a70a  call    _guard_dispatch_icall
0x14001a70f  jmp     loc_14001A58A
0x14001a714  mov     edx, 1Bh
0x14001a719  lea     r8, WPP_6fbf3721221234eecc9a3cdb64421ce5_Traceguids
0x14001a720  mov     ecx, 403h
0x14001a725  call    WPP_SF_
0x14001a72a  jmp     loc_14001A597
0x14001a72f  mov     r9, rbx
0x14001a732  mov     [rsp+58h+Timeout], rdi
0x14001a737  call    WPP_SF_qZ
0x14001a73c  jmp     loc_14001A3DE
0x14001a741  mov     edx, 1Dh
0x14001a746  lea     r8, WPP_6fbf3721221234eecc9a3cdb64421ce5_Traceguids
0x14001a74d  mov     ecx, 418h
0x14001a752  mov     r9, rdi
0x14001a755  call    WPP_SF_Z
0x14001a75a  jmp     loc_14001A441
0x14001a75f  mov     dl, al; NewIrql
0x14001a761  mov     rcx, r14; SpinLock
0x14001a764  call    cs:__imp_KeReleaseSpinLock
0x14001a76b  nop     dword ptr [rax+rax+00h]
0x14001a770  mov     eax, 0C0000010h
0x14001a775  jmp     loc_14001A493
```
