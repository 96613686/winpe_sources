# I8xFinishResetRequest

- ea: `0x14000b5f4`
- end: `0x14000b723`
- name: `I8xFinishResetRequest`
- size: `303`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400063a0`
- `0x14000ba98`
- `0x14001be20`

## callees

- `0x14000b5f4`
- `0x14000c0a4`

## import_xrefs

- `ntoskrnl!IoFreeController` at `0x14000b6b9`
- `ntoskrnl!IoFreeController` at `0x14000b6b9`
- `ntoskrnl!KeCancelTimer` at `0x14000b620`
- `ntoskrnl!KeCancelTimer` at `0x14000b620`
- `ntoskrnl!IoFreeIrp` at `0x14000b6f2`
- `ntoskrnl!IoFreeIrp` at `0x14000b6f2`
- `ntoskrnl!KeLowerIrql` at `0x14000b6de`
- `ntoskrnl!KeLowerIrql` at `0x14000b6de`
- `ntoskrnl!KfRaiseIrql` at `0x14000b66e`
- `ntoskrnl!KfRaiseIrql` at `0x14000b66e`
- `ntoskrnl!IoStartNextPacket` at `0x14000b6ca`
- `ntoskrnl!IoStartNextPacket` at `0x14000b6ca`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000b70b`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000b70b`
- `ntoskrnl!KeInsertQueueDpc` at `0x14000b69b`
- `ntoskrnl!KeInsertQueueDpc` at `0x14000b69b`

## pseudocode

```c
void __fastcall I8xFinishResetRequest(__int64 a1, char a2, char a3, char a4)
{
  KIRQL v4; // si
  IRP *v8; // rdi

  v4 = 0;
  v8 = (IRP *)_InterlockedExchange64((volatile __int64 *)(a1 + 600), 0);
  if ( a4 )
    KeCancelTimer((PKTIMER)(a1 + 864));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      12,
      88,
      (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
      (char)v8);
  if ( a3 )
    v4 = KfRaiseIrql(2u);
  if ( a2 && HIBYTE(WPP_MAIN_CB.Dpc.DeferredRoutine) )
    KeInsertQueueDpc((PRKDPC)(a1 + 232), 0, (PVOID)0xFFFFFFFF80050012LL);
  *(_BYTE *)(a1 + 1104) = 0;
  IoFreeController(*(PCONTROLLER_OBJECT *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 8LL));
  IoStartNextPacket(*(PDEVICE_OBJECT *)a1, 0);
  if ( a3 )
    KeLowerIrql(v4);
  if ( v8 )
  {
    IoFreeIrp(v8);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 40), v8, 0x20u);
  }
}

```

## disassembly

```asm
0x14000b5f4  push    rbx
0x14000b5f6  push    rbp
0x14000b5f7  push    rsi
0x14000b5f8  push    rdi
0x14000b5f9  push    r14
0x14000b5fb  sub     rsp, 30h
0x14000b5ff  xor     edi, edi
0x14000b601  xor     sil, sil
0x14000b604  mov     bpl, r8b
0x14000b607  mov     r14b, dl
0x14000b60a  mov     rbx, rcx
0x14000b60d  xchg    rdi, [rcx+258h]
0x14000b614  test    r9b, r9b
0x14000b617  jz      short loc_14000B62C
0x14000b619  add     rcx, 360h; PKTIMER
0x14000b620  call    cs:__imp_KeCancelTimer
0x14000b627  nop     dword ptr [rax+rax+00h]
0x14000b62c  lea     rax, WPP_RECORDER_INITIALIZED
0x14000b633  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000b63a  jz      short loc_14000B667
0x14000b63c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b643  lea     rax, WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids
0x14000b64a  mov     r9d, 58h ; 'X'
0x14000b650  mov     [rsp+58h+var_30], rdi
0x14000b655  mov     [rsp+58h+var_38], rax
0x14000b65a  mov     rcx, [rcx+40h]
0x14000b65e  lea     r8d, [r9-4Ch]
0x14000b662  call    WPP_RECORDER_SF_q
0x14000b667  test    bpl, bpl
0x14000b66a  jz      short loc_14000B67D
0x14000b66c  mov     cl, 2; NewIrql
0x14000b66e  call    cs:__imp_KfRaiseIrql
0x14000b675  nop     dword ptr [rax+rax+00h]
0x14000b67a  mov     sil, al
0x14000b67d  test    r14b, r14b
0x14000b680  jz      short loc_14000B6A7
0x14000b682  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+7, 0
0x14000b689  jz      short loc_14000B6A7
0x14000b68b  lea     rcx, [rbx+0E8h]; Dpc
0x14000b692  xor     edx, edx; SystemArgument1
0x14000b694  mov     r8, 0FFFFFFFF80050012h; SystemArgument2
0x14000b69b  call    cs:__imp_KeInsertQueueDpc
0x14000b6a2  nop     dword ptr [rax+rax+00h]
0x14000b6a7  mov     byte ptr [rbx+450h], 0
0x14000b6ae  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14000b6b5  mov     rcx, [rcx+8]; ControllerObject
0x14000b6b9  call    cs:__imp_IoFreeController
0x14000b6c0  nop     dword ptr [rax+rax+00h]
0x14000b6c5  mov     rcx, [rbx]; DeviceObject
0x14000b6c8  xor     edx, edx; Cancelable
0x14000b6ca  call    cs:__imp_IoStartNextPacket
0x14000b6d1  nop     dword ptr [rax+rax+00h]
0x14000b6d6  test    bpl, bpl
0x14000b6d9  jz      short loc_14000B6EA
0x14000b6db  mov     cl, sil; NewIrql
0x14000b6de  call    cs:__imp_KeLowerIrql
0x14000b6e5  nop     dword ptr [rax+rax+00h]
0x14000b6ea  test    rdi, rdi
0x14000b6ed  jz      short loc_14000B717
0x14000b6ef  mov     rcx, rdi; Irp
0x14000b6f2  call    cs:__imp_IoFreeIrp
0x14000b6f9  nop     dword ptr [rax+rax+00h]
0x14000b6fe  lea     rcx, [rbx+28h]; RemoveLock
0x14000b702  mov     r8d, 20h ; ' '; RemlockSize
0x14000b708  mov     rdx, rdi; Tag
0x14000b70b  call    cs:__imp_IoReleaseRemoveLockEx
0x14000b712  nop     dword ptr [rax+rax+00h]
0x14000b717  add     rsp, 30h
0x14000b71b  pop     r14
0x14000b71d  pop     rdi
0x14000b71e  pop     rsi
0x14000b71f  pop     rbp
0x14000b720  pop     rbx
0x14000b721  retn
```
