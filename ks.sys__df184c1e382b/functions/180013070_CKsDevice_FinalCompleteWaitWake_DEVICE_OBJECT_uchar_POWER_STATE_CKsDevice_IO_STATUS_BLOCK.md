# CKsDevice::FinalCompleteWaitWake(_DEVICE_OBJECT *,uchar,_POWER_STATE,CKsDevice *,_IO_STATUS_BLOCK *)

- ea: `0x180013070`
- end: `0x18001349b`
- name: `?FinalCompleteWaitWake@CKsDevice@@CAXPEAU_DEVICE_OBJECT@@ET_POWER_STATE@@PEAV1@PEAU_IO_STATUS_BLOCK@@@Z`
- size: `1067`
- prototype: `void __fastcall(PDEVICE_OBJECT DeviceObject, UCHAR MinorFunction, POWER_STATE PowerState, char *Context, PIO_STATUS_BLOCK IoStatus)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b7bc`
- `0x18000c630`
- `0x180013070`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x1800133c7`
- `ntoskrnl!ExQueueWorkItem` at `0x1800133c7`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x18001310d`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1800133a3`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x18001310d`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1800133a3`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18001321a`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18001347d`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18001321a`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18001347d`
- `ntoskrnl!PoRequestPowerIrp` at `0x18001319a`
- `ntoskrnl!PoRequestPowerIrp` at `0x18001319a`

## pseudocode

```c
void __fastcall CKsDevice::FinalCompleteWaitWake(
        PDEVICE_OBJECT DeviceObject,
        UCHAR MinorFunction,
        POWER_STATE PowerState,
        char *Context,
        PIO_STATUS_BLOCK IoStatus)
{
  NTSTATUS Status; // esi
  struct _IO_REMOVE_LOCK *v7; // r14
  NTSTATUS v8; // eax
  signed __int32 v9; // edx
  NTSTATUS v10; // eax
  int v11; // edx
  signed __int32 v12; // eax
  PDEVICE_OBJECT v13; // rcx
  int v14; // r9d
  void (__fastcall *v15)(CKsDevice *); // rdi
  PDEVICE_OBJECT v16; // rcx
  int v17; // r9d

  Status = IoStatus->Status;
  v7 = (struct _IO_REMOVE_LOCK *)(*(_QWORD *)(*((_QWORD *)Context + 28) + 64LL) - 32LL);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      142,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
      IoStatus->Status);
  if ( Status < 0 )
  {
    v15 = CKsDevice::DisarmDeviceStack;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        1,
        151,
        (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
        Status);
    goto LABEL_42;
  }
  v8 = IoAcquireRemoveLockEx(v7, CKsDevice::FinalCompleteDevicePowerIrp, File, 1u, 0x20u);
  if ( v8 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_54;
    v16 = WPP_GLOBAL_Control;
    if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
      goto LABEL_51;
    v17 = 148;
    goto LABEL_50;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v9) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        1,
        143,
        (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v9) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        1,
        144,
        (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
    }
  }
  v10 = PoRequestPowerIrp(
          *((PDEVICE_OBJECT *)Context + 29),
          2u,
          (POWER_STATE)1,
          (PREQUEST_POWER_COMPLETE)CKsDevice::FinalCompleteDevicePowerIrp,
          Context,
          0);
  if ( v10 >= 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v11) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        1,
        147,
        (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          5,
          1,
          145,
          (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
          v10);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v11) = 5;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          1,
          146,
          (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
      }
    }
    IoReleaseRemoveLockEx(v7, CKsDevice::FinalCompleteDevicePowerIrp, 0x20u);
  }
  v12 = _InterlockedCompareExchange((volatile signed __int32 *)Context + 245, 4, 3);
  v9 = v12 - 2;
  if ( v12 != 2 && v12 != 3 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_54;
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v9) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        1,
        150,
        (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
    }
    goto LABEL_30;
  }
  if ( v12 != 2 || _InterlockedCompareExchange((volatile signed __int32 *)Context + 245, 4, 2) == 2 )
  {
    v15 = CKsDevice::RearmDeviceStack;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v9) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        1,
        149,
        (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
    }
LABEL_42:
    v8 = IoAcquireRemoveLockEx(v7, v15, File, 1u, 0x20u);
    if ( !v8 )
    {
      *((_QWORD *)Context + 125) = v15;
      *((_QWORD *)Context + 126) = Context;
      *((_QWORD *)Context + 123) = 0;
      ExQueueWorkItem((PWORK_QUEUE_ITEM)(Context + 984), DelayedWorkQueue);
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_54;
      v13 = WPP_GLOBAL_Control;
      if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        goto LABEL_51;
      v14 = 152;
      goto LABEL_46;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_54;
    v16 = WPP_GLOBAL_Control;
    if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
      goto LABEL_51;
    v17 = 153;
LABEL_50:
    WPP_RECORDER_SF_D(v16->DeviceExtension, 5, 1, v17, (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids, v8);
    goto LABEL_51;
  }
LABEL_30:
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    goto LABEL_54;
  v13 = WPP_GLOBAL_Control;
  if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
    goto LABEL_51;
  v14 = 154;
LABEL_46:
  LOBYTE(v9) = 5;
  WPP_RECORDER_SF_(v13->DeviceExtension, v9, 1, v14, (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
LABEL_51:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v9) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      1,
      155,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
  }
LABEL_54:
  IoReleaseRemoveLockEx(v7, CKsDevice::FinalCompleteWaitWake, 0x20u);
}

```

## disassembly

```asm
0x180013070  push    rbx
0x180013072  push    rbp
0x180013073  push    rsi
0x180013074  push    rdi
0x180013075  push    r12
0x180013077  push    r13
0x180013079  push    r14
0x18001307b  push    r15
0x18001307d  sub     rsp, 38h
0x180013081  mov     rax, [rsp+78h+IoStatus]
0x180013089  mov     rbp, r9
0x18001308c  mov     esi, [rax]
0x18001308e  mov     rax, [r9+0E0h]
0x180013095  mov     r14, [rax+40h]
0x180013099  add     r14, 0FFFFFFFFFFFFFFE0h
0x18001309d  xor     r15d, r15d
0x1800130a0  lea     r12, WPP_RECORDER_INITIALIZED
0x1800130a7  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800130ae  lea     r13, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x1800130b5  lea     ebx, [r15+1]
0x1800130b9  jz      short loc_1800130E6
0x1800130bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800130c2  cmp     [rcx+48h], r15w
0x1800130c7  jz      short loc_1800130E6
0x1800130c9  mov     rcx, [rcx+40h]
0x1800130cd  mov     r9d, 8Eh
0x1800130d3  mov     dword ptr [rsp+78h+Irp], esi
0x1800130d7  mov     r8d, ebx
0x1800130da  mov     dl, 5
0x1800130dc  mov     qword ptr [rsp+78h+RemlockSize], r13
0x1800130e1  call    WPP_RECORDER_SF_D
0x1800130e6  test    esi, esi
0x1800130e8  js      loc_180013350
0x1800130ee  lea     rdi, ?FinalCompleteDevicePowerIrp@CKsDevice@@CAXPEAU_DEVICE_OBJECT@@ET_POWER_STATE@@PEAV1@PEAU_IO_STATUS_BLOCK@@@Z; CKsDevice::FinalCompleteDevicePowerIrp(_DEVICE_OBJECT *,uchar,_POWER_STATE,CKsDevice *,_IO_STATUS_BLOCK *)
0x1800130f5  mov     [rsp+78h+RemlockSize], 20h ; ' '; RemlockSize
0x1800130fd  mov     rdx, rdi; Tag
0x180013100  lea     r8, File; File
0x180013107  mov     r9d, ebx; Line
0x18001310a  mov     rcx, r14; RemoveLock
0x18001310d  call    cs:__imp_IoAcquireRemoveLockEx
0x180013114  nop     dword ptr [rax+rax+00h]
0x180013119  test    eax, eax
0x18001311b  jnz     loc_180013326
0x180013121  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180013128  jz      short loc_180013181
0x18001312a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013131  cmp     [rcx+48h], r15w
0x180013136  jz      short loc_180013151
0x180013138  mov     rcx, [rcx+40h]
0x18001313c  mov     r9d, 8Fh
0x180013142  mov     r8d, ebx
0x180013145  mov     qword ptr [rsp+78h+RemlockSize], r13
0x18001314a  mov     dl, 5
0x18001314c  call    WPP_RECORDER_SF_
0x180013151  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180013158  jz      short loc_180013181
0x18001315a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013161  cmp     [rcx+48h], r15w
0x180013166  jz      short loc_180013181
0x180013168  mov     rcx, [rcx+40h]
0x18001316c  mov     r9d, 90h
0x180013172  mov     r8d, ebx
0x180013175  mov     qword ptr [rsp+78h+RemlockSize], r13
0x18001317a  mov     dl, 5
0x18001317c  call    WPP_RECORDER_SF_
0x180013181  mov     rcx, [rbp+0E8h]; DeviceObject
0x180013188  mov     r9, rdi; CompletionFunction
0x18001318b  mov     [rsp+78h+Irp], r15; Irp
0x180013190  mov     r8d, ebx; PowerState
0x180013193  mov     dl, 2; MinorFunction
0x180013195  mov     qword ptr [rsp+78h+RemlockSize], rbp; Context
0x18001319a  call    cs:__imp_PoRequestPowerIrp
0x1800131a1  nop     dword ptr [rax+rax+00h]
0x1800131a6  test    eax, eax
0x1800131a8  jns     short loc_180013228
0x1800131aa  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800131b1  jz      short loc_18001320E
0x1800131b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800131ba  cmp     [rcx+48h], r15w
0x1800131bf  jz      short loc_1800131DE
0x1800131c1  mov     rcx, [rcx+40h]
0x1800131c5  mov     r9d, 91h
0x1800131cb  mov     dword ptr [rsp+78h+Irp], eax
0x1800131cf  mov     r8d, ebx
0x1800131d2  mov     dl, 5
0x1800131d4  mov     qword ptr [rsp+78h+RemlockSize], r13
0x1800131d9  call    WPP_RECORDER_SF_D
0x1800131de  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800131e5  jz      short loc_18001320E
0x1800131e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800131ee  cmp     [rcx+48h], r15w
0x1800131f3  jz      short loc_18001320E
0x1800131f5  mov     rcx, [rcx+40h]
0x1800131f9  mov     r9d, 92h
0x1800131ff  mov     r8d, ebx
0x180013202  mov     qword ptr [rsp+78h+RemlockSize], r13
0x180013207  mov     dl, 5
0x180013209  call    WPP_RECORDER_SF_
0x18001320e  mov     r8d, 20h ; ' '; RemlockSize
0x180013214  mov     rdx, rdi; Tag
0x180013217  mov     rcx, r14; RemoveLock
0x18001321a  call    cs:__imp_IoReleaseRemoveLockEx
0x180013221  nop     dword ptr [rax+rax+00h]
0x180013226  jmp     short loc_180013258
0x180013228  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18001322f  jz      short loc_180013258
0x180013231  mov     rcx, cs:WPP_GLOBAL_Control
0x180013238  cmp     [rcx+48h], r15w
0x18001323d  jz      short loc_180013258
0x18001323f  mov     rcx, [rcx+40h]
0x180013243  mov     r9d, 93h
0x180013249  mov     r8d, ebx
0x18001324c  mov     qword ptr [rsp+78h+RemlockSize], r13
0x180013251  mov     dl, 5
0x180013253  call    WPP_RECORDER_SF_
0x180013258  mov     eax, 3
0x18001325d  lea     r8d, [rax+1]
0x180013261  lock cmpxchg [rbp+3D4h], r8d
0x18001326a  mov     edx, eax
0x18001326c  sub     edx, 2
0x18001326f  jz      short loc_1800132AB
0x180013271  cmp     edx, ebx
0x180013273  jz      short loc_1800132AB
0x180013275  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18001327c  jz      loc_18001346D
0x180013282  mov     rcx, cs:WPP_GLOBAL_Control
0x180013289  cmp     [rcx+48h], r15w
0x18001328e  jz      short loc_1800132BB
0x180013290  mov     rcx, [rcx+40h]
0x180013294  mov     r9d, 96h
0x18001329a  mov     r8d, ebx
0x18001329d  mov     qword ptr [rsp+78h+RemlockSize], r13
0x1800132a2  mov     dl, 5
0x1800132a4  call    WPP_RECORDER_SF_
0x1800132a9  jmp     short loc_1800132BB
0x1800132ab  cmp     eax, 2
0x1800132ae  jnz     short loc_1800132E5
0x1800132b0  lock cmpxchg [rbp+3D4h], r8d
0x1800132b9  jz      short loc_1800132E5
0x1800132bb  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800132c2  jz      loc_18001346D
0x1800132c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800132cf  cmp     [rcx+48h], r15w
0x1800132d4  jz      loc_18001343D
0x1800132da  mov     r9d, 9Ah
0x1800132e0  jmp     loc_1800133F4
0x1800132e5  lea     rdi, ?RearmDeviceStack@CKsDevice@@CAXPEAV1@@Z; CKsDevice::RearmDeviceStack(CKsDevice *)
0x1800132ec  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800132f3  jz      loc_18001338B
0x1800132f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180013300  cmp     [rcx+48h], r15w
0x180013305  jz      loc_18001338B
0x18001330b  mov     rcx, [rcx+40h]
0x18001330f  mov     r9d, 95h
0x180013315  mov     r8d, ebx
0x180013318  mov     qword ptr [rsp+78h+RemlockSize], r13
0x18001331d  mov     dl, 5
0x18001331f  call    WPP_RECORDER_SF_
0x180013324  jmp     short loc_18001338B
0x180013326  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18001332d  jz      loc_18001346D
0x180013333  mov     rcx, cs:WPP_GLOBAL_Control
0x18001333a  cmp     [rcx+48h], r15w
0x18001333f  jz      loc_18001343D
0x180013345  mov     r9d, 94h
0x18001334b  jmp     loc_180013426
0x180013350  lea     rdi, ?DisarmDeviceStack@CKsDevice@@CAXPEAV1@@Z; CKsDevice::DisarmDeviceStack(CKsDevice *)
0x180013357  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18001335e  jz      short loc_18001338B
0x180013360  mov     rcx, cs:WPP_GLOBAL_Control
0x180013367  cmp     [rcx+48h], r15w
0x18001336c  jz      short loc_18001338B
0x18001336e  mov     rcx, [rcx+40h]
0x180013372  mov     r9d, 97h
0x180013378  mov     dword ptr [rsp+78h+Irp], esi
0x18001337c  mov     r8d, ebx
0x18001337f  mov     dl, 5
0x180013381  mov     qword ptr [rsp+78h+RemlockSize], r13
0x180013386  call    WPP_RECORDER_SF_D
0x18001338b  mov     r9d, ebx; Line
0x18001338e  mov     [rsp+78h+RemlockSize], 20h ; ' '; RemlockSize
0x180013396  lea     r8, File; File
0x18001339d  mov     rdx, rdi; Tag
0x1800133a0  mov     rcx, r14; RemoveLock
0x1800133a3  call    cs:__imp_IoAcquireRemoveLockEx
0x1800133aa  nop     dword ptr [rax+rax+00h]
0x1800133af  test    eax, eax
0x1800133b1  jnz     short loc_180013409
0x1800133b3  lea     rcx, [rbp+3D8h]; WorkItem
0x1800133ba  mov     edx, ebx; QueueType
0x1800133bc  mov     [rcx+10h], rdi
0x1800133c0  mov     [rcx+18h], rbp
0x1800133c4  mov     [rcx], r15
0x1800133c7  call    cs:__imp_ExQueueWorkItem
0x1800133ce  nop     dword ptr [rax+rax+00h]
0x1800133d3  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800133da  jz      loc_18001346D
0x1800133e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800133e7  cmp     [rcx+48h], r15w
0x1800133ec  jz      short loc_18001343D
0x1800133ee  mov     r9d, 98h
0x1800133f4  mov     rcx, [rcx+40h]
0x1800133f8  mov     r8d, ebx
0x1800133fb  mov     dl, 5
0x1800133fd  mov     qword ptr [rsp+78h+RemlockSize], r13
0x180013402  call    WPP_RECORDER_SF_
0x180013407  jmp     short loc_18001343D
0x180013409  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180013410  jz      short loc_18001346D
0x180013412  mov     rcx, cs:WPP_GLOBAL_Control
0x180013419  cmp     [rcx+48h], r15w
0x18001341e  jz      short loc_18001343D
0x180013420  mov     r9d, 99h
0x180013426  mov     rcx, [rcx+40h]
0x18001342a  mov     r8d, ebx
0x18001342d  mov     dword ptr [rsp+78h+Irp], eax
0x180013431  mov     dl, 5
0x180013433  mov     qword ptr [rsp+78h+RemlockSize], r13
0x180013438  call    WPP_RECORDER_SF_D
0x18001343d  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180013444  jz      short loc_18001346D
0x180013446  mov     rcx, cs:WPP_GLOBAL_Control
0x18001344d  cmp     [rcx+48h], r15w
0x180013452  jz      short loc_18001346D
0x180013454  mov     rcx, [rcx+40h]
0x180013458  mov     r9d, 9Bh
0x18001345e  mov     r8d, ebx
0x180013461  mov     qword ptr [rsp+78h+RemlockSize], r13
0x180013466  mov     dl, 5
0x180013468  call    WPP_RECORDER_SF_
0x18001346d  mov     r8d, 20h ; ' '; RemlockSize
0x180013473  lea     rdx, ?FinalCompleteWaitWake@CKsDevice@@CAXPEAU_DEVICE_OBJECT@@ET_POWER_STATE@@PEAV1@PEAU_IO_STATUS_BLOCK@@@Z; Tag
0x18001347a  mov     rcx, r14; RemoveLock
0x18001347d  call    cs:__imp_IoReleaseRemoveLockEx
0x180013484  nop     dword ptr [rax+rax+00h]
0x180013489  add     rsp, 38h
0x18001348d  pop     r15
0x18001348f  pop     r14
0x180013491  pop     r13
0x180013493  pop     r12
0x180013495  pop     rdi
0x180013496  pop     rsi
0x180013497  pop     rbp
0x180013498  pop     rbx
0x180013499  retn
```
