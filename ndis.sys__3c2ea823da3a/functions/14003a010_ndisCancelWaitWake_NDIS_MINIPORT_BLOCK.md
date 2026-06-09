# ndisCancelWaitWake(_NDIS_MINIPORT_BLOCK *)

- ea: `0x14003a010`
- end: `0x14003a1a9`
- name: `?ndisCancelWaitWake@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z`
- size: `409`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *)`
- caller_count: `9`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14003a1b0`
- `0x1400517e0`
- `0x14006fe60`
- `0x140080990`
- `0x1400a60c4`
- `0x140163ee0`
- `0x140177920`
- `0x140179c80`
- `0x14017be80`

## callees

- `0x140012a70`
- `0x14001cf50`
- `0x14003a010`

## import_xrefs

- `ntoskrnl!IoCancelIrp` at `0x14003a0ac`
- `ntoskrnl!IoCancelIrp` at `0x14003a0ac`
- `ntoskrnl!IofCompleteRequest` at `0x14003a153`
- `ntoskrnl!IofCompleteRequest` at `0x14003a153`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003a04c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003a099`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003a130`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003a04c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003a099`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003a130`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003a026`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003a108`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003a026`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003a108`

## pseudocode

```c
void __fastcall ndisCancelWaitWake(struct _NDIS_MINIPORT_BLOCK *a1)
{
  KIRQL v2; // al
  int v3; // edx
  __int64 v4; // rcx
  KIRQL v5; // al
  bool WaitWakeIoCompletionRoutineRan; // di

  v2 = KeAcquireSpinLockRaiseToDpc(&a1->Lock);
  if ( !a1->WaitWakeIrp || a1->WaitWakeIoCompletionRoutineRan || a1->WaitWakeCancelAttempted )
  {
    a1->MiniportThread = 0;
    KeReleaseSpinLock(&a1->Lock, v2);
  }
  else
  {
    a1->MiniportThread = 0;
    *(_WORD *)&a1->WaitWakeCancelInProgress = 257;
    KeReleaseSpinLock(&a1->Lock, v2);
    if ( IoCancelIrp(a1->WaitWakeIrp) )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v3) = 4;
        WPP_RECORDER_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v3,
          14,
          147,
          (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
          (char)a1);
      }
      if ( (byte_14011B001 & 8) != 0 )
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD))McTemplateK0jqxd_EtwWriteTransfer)(
          v4,
          CancelledWakeIrp,
          &a1->InterfaceGuid,
          &a1->InterfaceGuid,
          a1->IfIndex,
          (_NET_LUID_LH)a1->NetLuid.Value,
          65537);
    }
    v5 = KeAcquireSpinLockRaiseToDpc(&a1->Lock);
    WaitWakeIoCompletionRoutineRan = a1->WaitWakeIoCompletionRoutineRan;
    a1->WaitWakeCancelInProgress = 0;
    a1->MiniportThread = 0;
    KeReleaseSpinLock(&a1->Lock, v5);
    if ( WaitWakeIoCompletionRoutineRan )
      IofCompleteRequest(a1->WaitWakeIrp, 0);
  }
}

```

## disassembly

```asm
0x14003a010  mov     [rsp+arg_8], rbx
0x14003a015  mov     [rsp+arg_10], rbp
0x14003a01a  push    rsi
0x14003a01b  sub     rsp, 40h
0x14003a01f  mov     rbx, rcx
0x14003a022  add     rcx, 60h ; '`'; SpinLock
0x14003a026  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003a02d  nop     dword ptr [rax+rax+00h]
0x14003a032  cmp     qword ptr [rbx+510h], 0
0x14003a03a  jnz     short loc_14003A069
0x14003a03c  xor     ebp, ebp
0x14003a03e  lea     rcx, [rbx+60h]; SpinLock
0x14003a042  movzx   edx, al; NewIrql
0x14003a045  mov     [rbx+208h], rbp
0x14003a04c  call    cs:__imp_KeReleaseSpinLock
0x14003a053  nop     dword ptr [rax+rax+00h]
0x14003a058  mov     rbx, [rsp+48h+arg_8]
0x14003a05d  mov     rbp, [rsp+48h+arg_10]
0x14003a062  add     rsp, 40h
0x14003a066  pop     rsi
0x14003a067  retn
0x14003a069  cmp     byte ptr [rbx+530h], 0
0x14003a070  jnz     short loc_14003A03C
0x14003a072  cmp     byte ptr [rbx+532h], 0
0x14003a079  jnz     short loc_14003A03C
0x14003a07b  xor     ebp, ebp
0x14003a07d  mov     [rsp+48h+arg_0], rdi
0x14003a082  movzx   edx, al; NewIrql
0x14003a085  mov     [rbx+208h], rbp
0x14003a08c  lea     rcx, [rbx+60h]; SpinLock
0x14003a090  mov     word ptr [rbx+531h], 101h
0x14003a099  call    cs:__imp_KeReleaseSpinLock
0x14003a0a0  nop     dword ptr [rax+rax+00h]
0x14003a0a5  mov     rcx, [rbx+510h]; Irp
0x14003a0ac  call    cs:__imp_IoCancelIrp
0x14003a0b3  nop     dword ptr [rax+rax+00h]
0x14003a0b8  test    al, al
0x14003a0ba  jz      short loc_14003A104
0x14003a0bc  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003a0c3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003a0ca  jz      short loc_14003A0FB
0x14003a0cc  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a0d3  lea     rax, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x14003a0da  mov     r9d, 93h; int
0x14003a0e0  mov     qword ptr [rsp+48h+var_20], rbx; char
0x14003a0e5  mov     r8d, 0Eh; int
0x14003a0eb  mov     [rsp+48h+var_28], rax; struct _GUID *
0x14003a0f0  mov     dl, 4; int
0x14003a0f2  mov     rcx, [rcx+40h]; int
0x14003a0f6  call    WPP_RECORDER_SF_q
0x14003a0fb  test    cs:byte_14011B001, 8
0x14003a102  jnz     short loc_14003A170
0x14003a104  lea     rcx, [rbx+60h]; SpinLock
0x14003a108  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003a10f  nop     dword ptr [rax+rax+00h]
0x14003a114  movzx   edi, byte ptr [rbx+530h]
0x14003a11b  lea     rcx, [rbx+60h]; SpinLock
0x14003a11f  movzx   edx, al; NewIrql
0x14003a122  mov     [rbx+531h], bpl
0x14003a129  mov     [rbx+208h], rbp
0x14003a130  call    cs:__imp_KeReleaseSpinLock
0x14003a137  nop     dword ptr [rax+rax+00h]
0x14003a13c  test    dil, dil
0x14003a13f  mov     rdi, [rsp+48h+arg_0]
0x14003a144  jz      loc_14003A058
0x14003a14a  mov     rcx, [rbx+510h]; Irp
0x14003a151  xor     edx, edx; PriorityBoost
0x14003a153  call    cs:__imp_IofCompleteRequest
0x14003a15a  nop     dword ptr [rax+rax+00h]
0x14003a15f  mov     rbx, [rsp+48h+arg_8]
0x14003a164  mov     rbp, [rsp+48h+arg_10]
0x14003a169  add     rsp, 40h
0x14003a16d  pop     rsi
0x14003a16e  retn
0x14003a170  mov     rax, [rbx+0FB8h]
0x14003a177  lea     r8, [rbx+0FA8h]
0x14003a17e  mov     [rsp+48h+var_18], 10001h
0x14003a186  lea     rdx, CancelledWakeIrp
0x14003a18d  mov     qword ptr [rsp+48h+var_20], rax
0x14003a192  mov     r9, r8
0x14003a195  mov     eax, [rbx+0FD8h]
0x14003a19b  mov     dword ptr [rsp+48h+var_28], eax
0x14003a19f  call    McTemplateK0jqxd_EtwWriteTransfer
0x14003a1a4  jmp     loc_14003A104
```
