# I8xSysButtonCancelRoutine

- ea: `0x14000d610`
- end: `0x14000d6ff`
- name: `I8xSysButtonCancelRoutine`
- size: `239`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004530`
- `0x14000c0a4`
- `0x14000d610`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000d6e5`
- `ntoskrnl!IofCompleteRequest` at `0x14000d6e5`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000d6c5`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000d6c5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d663`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d663`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d6b6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d6b6`

## pseudocode

```c
void __fastcall I8xSysButtonCancelRoutine(__int64 a1, IRP *a2)
{
  __int64 v2; // rdi
  int v4; // edx
  KIRQL v5; // bp
  __int64 v6; // rax

  v2 = *(_QWORD *)(a1 + 64);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      23,
      23,
      (__int64)WPP_9a74d45702a83a61696de9b252942f2f_Traceguids);
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 664));
  v6 = *(_QWORD *)(v2 + 592);
  *(_QWORD *)(v2 + 592) = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      24,
      24,
      (__int64)WPP_9a74d45702a83a61696de9b252942f2f_Traceguids,
      v6);
  KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 664), v5);
  IoReleaseCancelSpinLock(a2->CancelIrql);
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = -1073741536;
  IofCompleteRequest(a2, 0);
}

```

## disassembly

```asm
0x14000d610  push    rbx
0x14000d612  push    rbp
0x14000d613  push    rsi
0x14000d614  push    rdi
0x14000d615  push    r14
0x14000d617  push    r15
0x14000d619  sub     rsp, 38h
0x14000d61d  mov     rdi, [rcx+40h]
0x14000d621  mov     rbx, rdx
0x14000d624  lea     r14, WPP_RECORDER_INITIALIZED
0x14000d62b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000d632  lea     r15, WPP_9a74d45702a83a61696de9b252942f2f_Traceguids
0x14000d639  jz      short loc_14000D659
0x14000d63b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d642  mov     r8d, 17h
0x14000d648  mov     r9d, r8d
0x14000d64b  mov     [rsp+68h+var_48], r15
0x14000d650  mov     rcx, [rcx+40h]
0x14000d654  call    WPP_RECORDER_SF_
0x14000d659  lea     rsi, [rdi+298h]
0x14000d660  mov     rcx, rsi; SpinLock
0x14000d663  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d66a  nop     dword ptr [rax+rax+00h]
0x14000d66f  mov     bpl, al
0x14000d672  mov     rax, [rdi+250h]
0x14000d679  mov     qword ptr [rdi+250h], 0
0x14000d684  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000d68b  jz      short loc_14000D6B0
0x14000d68d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d694  mov     r8d, 18h
0x14000d69a  mov     [rsp+68h+var_40], rax
0x14000d69f  mov     r9d, r8d
0x14000d6a2  mov     [rsp+68h+var_48], r15
0x14000d6a7  mov     rcx, [rcx+40h]
0x14000d6ab  call    WPP_RECORDER_SF_q
0x14000d6b0  mov     dl, bpl; NewIrql
0x14000d6b3  mov     rcx, rsi; SpinLock
0x14000d6b6  call    cs:__imp_KeReleaseSpinLock
0x14000d6bd  nop     dword ptr [rax+rax+00h]
0x14000d6c2  mov     cl, [rbx+45h]; Irql
0x14000d6c5  call    cs:__imp_IoReleaseCancelSpinLock
0x14000d6cc  nop     dword ptr [rax+rax+00h]
0x14000d6d1  xor     edx, edx; PriorityBoost
0x14000d6d3  mov     qword ptr [rbx+38h], 0
0x14000d6db  mov     rcx, rbx; Irp
0x14000d6de  mov     dword ptr [rbx+30h], 0C0000120h
0x14000d6e5  call    cs:__imp_IofCompleteRequest
0x14000d6ec  nop     dword ptr [rax+rax+00h]
0x14000d6f1  add     rsp, 38h
0x14000d6f5  pop     r15
0x14000d6f7  pop     r14
0x14000d6f9  pop     rdi
0x14000d6fa  pop     rsi
0x14000d6fb  pop     rbp
0x14000d6fc  pop     rbx
0x14000d6fd  retn
```
