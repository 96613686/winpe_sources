# ndisCancelWaitWake(_NDIS_MINIPORT_BLOCK *)

- ea: `0x140044e80`
- end: `0x140045019`
- name: `?ndisCancelWaitWake@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z`
- size: `409`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *)`
- caller_count: `9`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140044a80`
- `0x140052790`
- `0x140056ae0`
- `0x140075ac0`
- `0x1400ab504`
- `0x14016ae70`
- `0x14017d8f0`
- `0x14017fc50`
- `0x140181e50`

## callees

- `0x1400110b0`
- `0x14003d6e0`
- `0x140044e80`

## import_xrefs

- `ntoskrnl!IoCancelIrp` at `0x140044f1c`
- `ntoskrnl!IoCancelIrp` at `0x140044f1c`
- `ntoskrnl!IofCompleteRequest` at `0x140044fc3`
- `ntoskrnl!IofCompleteRequest` at `0x140044fc3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140044ebc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140044f09`
- `ntoskrnl!KeReleaseSpinLock` at `0x140044fa0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140044ebc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140044f09`
- `ntoskrnl!KeReleaseSpinLock` at `0x140044fa0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140044e96`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140044f78`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140044e96`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140044f78`

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
      if ( (byte_140121001 & 8) != 0 )
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
0x140044e80  mov     [rsp+arg_8], rbx
0x140044e85  mov     [rsp+arg_10], rbp
0x140044e8a  push    rsi
0x140044e8b  sub     rsp, 40h
0x140044e8f  mov     rbx, rcx
0x140044e92  add     rcx, 60h ; '`'; SpinLock
0x140044e96  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140044e9d  nop     dword ptr [rax+rax+00h]
0x140044ea2  cmp     qword ptr [rbx+510h], 0
0x140044eaa  jnz     short loc_140044ED9
0x140044eac  xor     ebp, ebp
0x140044eae  lea     rcx, [rbx+60h]; SpinLock
0x140044eb2  movzx   edx, al; NewIrql
0x140044eb5  mov     [rbx+208h], rbp
0x140044ebc  call    cs:__imp_KeReleaseSpinLock
0x140044ec3  nop     dword ptr [rax+rax+00h]
0x140044ec8  mov     rbx, [rsp+48h+arg_8]
0x140044ecd  mov     rbp, [rsp+48h+arg_10]
0x140044ed2  add     rsp, 40h
0x140044ed6  pop     rsi
0x140044ed7  retn
0x140044ed9  cmp     byte ptr [rbx+530h], 0
0x140044ee0  jnz     short loc_140044EAC
0x140044ee2  cmp     byte ptr [rbx+532h], 0
0x140044ee9  jnz     short loc_140044EAC
0x140044eeb  xor     ebp, ebp
0x140044eed  mov     [rsp+48h+arg_0], rdi
0x140044ef2  movzx   edx, al; NewIrql
0x140044ef5  mov     [rbx+208h], rbp
0x140044efc  lea     rcx, [rbx+60h]; SpinLock
0x140044f00  mov     word ptr [rbx+531h], 101h
0x140044f09  call    cs:__imp_KeReleaseSpinLock
0x140044f10  nop     dword ptr [rax+rax+00h]
0x140044f15  mov     rcx, [rbx+510h]; Irp
0x140044f1c  call    cs:__imp_IoCancelIrp
0x140044f23  nop     dword ptr [rax+rax+00h]
0x140044f28  test    al, al
0x140044f2a  jz      short loc_140044F74
0x140044f2c  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140044f33  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140044f3a  jz      short loc_140044F6B
0x140044f3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140044f43  lea     rax, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x140044f4a  mov     r9d, 93h; int
0x140044f50  mov     qword ptr [rsp+48h+var_20], rbx; char
0x140044f55  mov     r8d, 0Eh; int
0x140044f5b  mov     [rsp+48h+var_28], rax; struct _GUID *
0x140044f60  mov     dl, 4; int
0x140044f62  mov     rcx, [rcx+40h]; int
0x140044f66  call    WPP_RECORDER_SF_q
0x140044f6b  test    cs:byte_140121001, 8
0x140044f72  jnz     short loc_140044FE0
0x140044f74  lea     rcx, [rbx+60h]; SpinLock
0x140044f78  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140044f7f  nop     dword ptr [rax+rax+00h]
0x140044f84  movzx   edi, byte ptr [rbx+530h]
0x140044f8b  lea     rcx, [rbx+60h]; SpinLock
0x140044f8f  movzx   edx, al; NewIrql
0x140044f92  mov     [rbx+531h], bpl
0x140044f99  mov     [rbx+208h], rbp
0x140044fa0  call    cs:__imp_KeReleaseSpinLock
0x140044fa7  nop     dword ptr [rax+rax+00h]
0x140044fac  test    dil, dil
0x140044faf  mov     rdi, [rsp+48h+arg_0]
0x140044fb4  jz      loc_140044EC8
0x140044fba  mov     rcx, [rbx+510h]; Irp
0x140044fc1  xor     edx, edx; PriorityBoost
0x140044fc3  call    cs:__imp_IofCompleteRequest
0x140044fca  nop     dword ptr [rax+rax+00h]
0x140044fcf  mov     rbx, [rsp+48h+arg_8]
0x140044fd4  mov     rbp, [rsp+48h+arg_10]
0x140044fd9  add     rsp, 40h
0x140044fdd  pop     rsi
0x140044fde  retn
0x140044fe0  mov     rax, [rbx+0FB8h]
0x140044fe7  lea     r8, [rbx+0FA8h]
0x140044fee  mov     [rsp+48h+var_18], 10001h
0x140044ff6  lea     rdx, CancelledWakeIrp
0x140044ffd  mov     qword ptr [rsp+48h+var_20], rax
0x140045002  mov     r9, r8
0x140045005  mov     eax, [rbx+0FD8h]
0x14004500b  mov     dword ptr [rsp+48h+var_28], eax
0x14004500f  call    McTemplateK0jqxd_EtwWriteTransfer
0x140045014  jmp     loc_140044F74
```
