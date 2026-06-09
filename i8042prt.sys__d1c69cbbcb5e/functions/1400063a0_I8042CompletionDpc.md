# I8042CompletionDpc

- ea: `0x1400063a0`
- end: `0x1400066c8`
- name: `I8042CompletionDpc`
- size: `808`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004530`
- `0x1400063a0`
- `0x140006950`
- `0x140007b10`
- `0x14000b5f4`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400065c1`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400065c1`
- `ntoskrnl!IoFreeController` at `0x140006625`
- `ntoskrnl!IoFreeController` at `0x14000666d`
- `ntoskrnl!IoFreeController` at `0x140006625`
- `ntoskrnl!IoFreeController` at `0x14000666d`
- `ntoskrnl!KeCancelTimer` at `0x1400063ff`
- `ntoskrnl!KeCancelTimer` at `0x1400063ff`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000660e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000660e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400065ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400065ed`
- `ntoskrnl!IofCompleteRequest` at `0x1400065a7`
- `ntoskrnl!IofCompleteRequest` at `0x1400065a7`
- `ntoskrnl!IoStartNextPacket` at `0x140006636`
- `ntoskrnl!IoStartNextPacket` at `0x14000667e`
- `ntoskrnl!IoStartNextPacket` at `0x140006636`
- `ntoskrnl!IoStartNextPacket` at `0x14000667e`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000664f`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000664f`

## pseudocode

```c
void __fastcall I8042CompletionDpc(
        struct _KDPC *Dpc,
        struct _DEVICE_OBJECT *DeferredContext,
        _QWORD *SystemArgument1,
        PVOID SystemArgument2)
{
  char *DeviceExtension; // rdi
  int v7; // edx
  __int64 v8; // r9
  int v9; // ecx
  int v10; // ecx
  __int64 v11; // rcx
  __int16 v12; // ax
  void *v13; // rcx
  int v14; // edx

  DeviceExtension = (char *)DeferredContext->DeviceExtension;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)DeferredContext,
      7,
      17,
      (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
  KeCancelTimer((PKTIMER)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 120LL));
  if ( !SystemArgument1 )
  {
    IoFreeController(*(PCONTROLLER_OBJECT *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 8LL));
    IoStartNextPacket(DeferredContext, 0);
LABEL_25:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        7,
        25,
        (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
    return;
  }
  v9 = *(_DWORD *)(SystemArgument1[23] + 24LL);
  if ( v9 == 720900 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        6,
        21,
        (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
    v11 = SystemArgument1[3];
    *((_DWORD *)DeviceExtension + 181) = *(_DWORD *)v11;
    v12 = *(_WORD *)(v11 + 4);
    *((_WORD *)DeviceExtension + 364) = v12;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_dD(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        8,
        22,
        (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids,
        *((_WORD *)DeviceExtension + 363),
        v12);
    goto LABEL_20;
  }
  if ( v9 == 720904 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        6,
        19,
        (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
    v10 = *(_DWORD *)SystemArgument1[3];
    *(_DWORD *)(DeviceExtension + 730) = v10;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        8,
        20,
        (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids,
        SBYTE2(v10));
    goto LABEL_20;
  }
  if ( v9 != 999423 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        8,
        24,
        (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
LABEL_20:
    *((_DWORD *)SystemArgument1 + 12) = 0;
    IofCompleteRequest((PIRP)SystemArgument1, 6);
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 184LL));
    v13 = (void *)*((_QWORD *)DeviceExtension + 64);
    if ( v13 && v13 != (void *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 200LL) )
      ExFreePoolWithTag(v13, 0);
    *((_QWORD *)DeviceExtension + 64) = 0;
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 184LL));
    IoFreeController(*(PCONTROLLER_OBJECT *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 8LL));
    IoStartNextPacket(DeferredContext, 0);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 40), SystemArgument1, 0x20u);
    goto LABEL_25;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      6,
      23,
      (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
  LOBYTE(v8) = 1;
  I8xFinishResetRequest(DeviceExtension, 0, 0, v8);
}

```

## disassembly

```asm
0x1400063a0  mov     [rsp+arg_8], rbx
0x1400063a5  mov     [rsp+arg_10], rbp
0x1400063aa  push    rsi
0x1400063ab  push    rdi
0x1400063ac  push    r14
0x1400063ae  sub     rsp, 40h
0x1400063b2  mov     rdi, [rdx+40h]
0x1400063b6  mov     rbx, r8
0x1400063b9  mov     rsi, rdx
0x1400063bc  lea     rbp, WPP_RECORDER_INITIALIZED
0x1400063c3  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400063ca  lea     r14, WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids
0x1400063d1  jz      short loc_1400063F4
0x1400063d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400063da  mov     r9d, 11h
0x1400063e0  mov     r8d, 7
0x1400063e6  mov     [rsp+58h+var_38], r14
0x1400063eb  mov     rcx, [rcx+40h]
0x1400063ef  call    WPP_RECORDER_SF_
0x1400063f4  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400063fb  add     rcx, 78h ; 'x'; PKTIMER
0x1400063ff  call    cs:__imp_KeCancelTimer
0x140006406  nop     dword ptr [rax+rax+00h]
0x14000640b  test    rbx, rbx
0x14000640e  jz      loc_140006662
0x140006414  mov     rax, [rbx+0B8h]
0x14000641b  mov     ecx, [rax+18h]
0x14000641e  cmp     ecx, 0B0004h
0x140006424  jz      loc_140006519
0x14000642a  cmp     ecx, 0B0008h
0x140006430  jz      short loc_1400064AC
0x140006432  cmp     ecx, 0F3FFFh
0x140006438  jz      short loc_14000646D
0x14000643a  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140006441  jz      loc_140006596
0x140006447  mov     rcx, cs:WPP_GLOBAL_Control
0x14000644e  mov     r9d, 18h
0x140006454  mov     r8d, 8
0x14000645a  mov     [rsp+58h+var_38], r14
0x14000645f  mov     rcx, [rcx+40h]
0x140006463  call    WPP_RECORDER_SF_
0x140006468  jmp     loc_140006596
0x14000646d  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140006474  jz      short loc_140006497
0x140006476  mov     rcx, cs:WPP_GLOBAL_Control
0x14000647d  mov     r9d, 17h
0x140006483  mov     r8d, 6
0x140006489  mov     [rsp+58h+var_38], r14
0x14000648e  mov     rcx, [rcx+40h]
0x140006492  call    WPP_RECORDER_SF_
0x140006497  mov     r9b, 1
0x14000649a  xor     r8d, r8d
0x14000649d  xor     edx, edx
0x14000649f  mov     rcx, rdi
0x1400064a2  call    I8xFinishResetRequest
0x1400064a7  jmp     loc_1400066B4
0x1400064ac  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400064b3  jz      short loc_1400064D6
0x1400064b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400064bc  mov     r9d, 13h
0x1400064c2  mov     r8d, 6
0x1400064c8  mov     [rsp+58h+var_38], r14
0x1400064cd  mov     rcx, [rcx+40h]
0x1400064d1  call    WPP_RECORDER_SF_
0x1400064d6  mov     rax, [rbx+18h]
0x1400064da  mov     ecx, [rax]
0x1400064dc  mov     [rdi+2DAh], ecx
0x1400064e2  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400064e9  jz      loc_140006596
0x1400064ef  shr     ecx, 10h
0x1400064f2  mov     r9d, 14h
0x1400064f8  mov     [rsp+58h+var_30], ecx
0x1400064fc  mov     r8d, 8
0x140006502  mov     rcx, cs:WPP_GLOBAL_Control
0x140006509  mov     [rsp+58h+var_38], r14
0x14000650e  mov     rcx, [rcx+40h]
0x140006512  call    WPP_RECORDER_SF_D
0x140006517  jmp     short loc_140006596
0x140006519  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140006520  jz      short loc_140006543
0x140006522  mov     rcx, cs:WPP_GLOBAL_Control
0x140006529  mov     r9d, 15h
0x14000652f  mov     r8d, 6
0x140006535  mov     [rsp+58h+var_38], r14
0x14000653a  mov     rcx, [rcx+40h]
0x14000653e  call    WPP_RECORDER_SF_
0x140006543  mov     rcx, [rbx+18h]
0x140006547  mov     eax, [rcx]
0x140006549  mov     [rdi+2D4h], eax
0x14000654f  movzx   eax, word ptr [rcx+4]
0x140006553  mov     [rdi+2D8h], ax
0x14000655a  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140006561  jz      short loc_140006596
0x140006563  movzx   ecx, word ptr [rdi+2D6h]
0x14000656a  mov     r9d, 16h
0x140006570  movzx   eax, ax
0x140006573  mov     r8d, 8
0x140006579  mov     [rsp+58h+var_28], eax
0x14000657d  mov     [rsp+58h+var_30], ecx
0x140006581  mov     rcx, cs:WPP_GLOBAL_Control
0x140006588  mov     [rsp+58h+var_38], r14
0x14000658d  mov     rcx, [rcx+40h]
0x140006591  call    WPP_RECORDER_SF_dD
0x140006596  mov     [rsp+58h+arg_0], r15
0x14000659b  mov     dl, 6; PriorityBoost
0x14000659d  xor     r15d, r15d
0x1400065a0  mov     rcx, rbx; Irp
0x1400065a3  mov     [rbx+30h], r15d
0x1400065a7  call    cs:__imp_IofCompleteRequest
0x1400065ae  nop     dword ptr [rax+rax+00h]
0x1400065b3  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400065ba  add     rcx, 0B8h; SpinLock
0x1400065c1  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400065c8  nop     dword ptr [rax+rax+00h]
0x1400065cd  mov     rcx, [rdi+200h]; P
0x1400065d4  test    rcx, rcx
0x1400065d7  jz      short loc_1400065F9
0x1400065d9  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400065e0  add     rax, 0C8h
0x1400065e6  cmp     rcx, rax
0x1400065e9  jz      short loc_1400065F9
0x1400065eb  xor     edx, edx; Tag
0x1400065ed  call    cs:__imp_ExFreePoolWithTag
0x1400065f4  nop     dword ptr [rax+rax+00h]
0x1400065f9  mov     [rdi+200h], r15
0x140006600  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140006607  add     rcx, 0B8h; SpinLock
0x14000660e  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140006615  nop     dword ptr [rax+rax+00h]
0x14000661a  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140006621  mov     rcx, [rcx+8]; ControllerObject
0x140006625  call    cs:__imp_IoFreeController
0x14000662c  nop     dword ptr [rax+rax+00h]
0x140006631  xor     edx, edx; Cancelable
0x140006633  mov     rcx, rsi; DeviceObject
0x140006636  call    cs:__imp_IoStartNextPacket
0x14000663d  nop     dword ptr [rax+rax+00h]
0x140006642  lea     rcx, [rdi+28h]; RemoveLock
0x140006646  mov     r8d, 20h ; ' '; RemlockSize
0x14000664c  mov     rdx, rbx; Tag
0x14000664f  call    cs:__imp_IoReleaseRemoveLockEx
0x140006656  nop     dword ptr [rax+rax+00h]
0x14000665b  mov     r15, [rsp+58h+arg_0]
0x140006660  jmp     short loc_14000668A
0x140006662  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140006669  mov     rcx, [rcx+8]; ControllerObject
0x14000666d  call    cs:__imp_IoFreeController
0x140006674  nop     dword ptr [rax+rax+00h]
0x140006679  xor     edx, edx; Cancelable
0x14000667b  mov     rcx, rsi; DeviceObject
0x14000667e  call    cs:__imp_IoStartNextPacket
0x140006685  nop     dword ptr [rax+rax+00h]
0x14000668a  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140006691  jz      short loc_1400066B4
0x140006693  mov     rcx, cs:WPP_GLOBAL_Control
0x14000669a  mov     r9d, 19h
0x1400066a0  mov     r8d, 7
0x1400066a6  mov     [rsp+58h+var_38], r14
0x1400066ab  mov     rcx, [rcx+40h]
0x1400066af  call    WPP_RECORDER_SF_
0x1400066b4  mov     rbx, [rsp+58h+arg_8]
0x1400066b9  mov     rbp, [rsp+58h+arg_10]
0x1400066be  add     rsp, 40h
0x1400066c2  pop     r14
0x1400066c4  pop     rdi
0x1400066c5  pop     rsi
0x1400066c6  retn
```
