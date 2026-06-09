# HIDSM_RunStateMachine

- ea: `0x1800109ac`
- end: `0x180010ae5`
- name: `HIDSM_RunStateMachine`
- size: `313`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f2f0`
- `0x180010830`

## callees

- `0x1800109ac`
- `0x180010aec`
- `0x180010f58`
- `0x1800114d4`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x180010ac5`
- `ntoskrnl!IoQueueWorkItem` at `0x180010ac5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800109ed`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800109ed`
- `ntoskrnl!KeGetCurrentIrql` at `0x180010a9a`
- `ntoskrnl!KeGetCurrentIrql` at `0x180010a9a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180010a3a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180010ad4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180010a3a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180010ad4`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x180010a7e`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x180010a7e`

## pseudocode

```c
void __fastcall HIDSM_RunStateMachine(unsigned int *Context, int a2, KIRQL *a3)
{
  __int64 v3; // r15
  unsigned int v5; // r12d
  unsigned int NextEvent; // edi
  struct _IO_REMOVE_LOCK *v9; // rcx

  v3 = *((_QWORD *)Context + 121);
  v5 = Context[244];
  while ( 1 )
  {
    if ( a2 == 1000 )
    {
      NextEvent = HIDSM_GetNextEvent(Context);
      if ( NextEvent == 1000 )
      {
        v9 = (struct _IO_REMOVE_LOCK *)(*((_QWORD *)Context + 120) + 640LL);
        *((_BYTE *)Context + 848) = 0;
        IoReleaseRemoveLockEx(v9, "State Machine Tag", 0x20u);
        return;
      }
    }
    else
    {
      NextEvent = a2;
      a2 = 1000;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)Context + 105, *a3);
    if ( !(unsigned __int8)HIDSM_FindAndSetTargetState(Context, NextEvent) )
      goto LABEL_7;
    if ( (*(_DWORD *)(*(_QWORD *)(v3 + 8LL * (Context[Context[220] + 213] - v5)) + 16LL) & 0x10) != 0
      && KeGetCurrentIrql() )
    {
      break;
    }
    a2 = HIDSM_ExecuteEntryFunctionsAndPushPopStateMachinesForCurrentState(Context);
    if ( a2 == 1002 )
      goto LABEL_12;
LABEL_7:
    *a3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 105);
  }
  IoQueueWorkItem(*((PIO_WORKITEM *)Context + 123), HIDSM_SmWorker, DelayedWorkQueue, Context);
LABEL_12:
  *a3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 105);
}

```

## disassembly

```asm
0x1800109ac  push    rbx
0x1800109ae  push    rbp
0x1800109af  push    rsi
0x1800109b0  push    rdi
0x1800109b1  push    r12
0x1800109b3  push    r14
0x1800109b5  push    r15
0x1800109b7  sub     rsp, 20h
0x1800109bb  mov     r15, [rcx+3C8h]
0x1800109c2  mov     r14, r8
0x1800109c5  mov     r12d, [rcx+3D0h]
0x1800109cc  mov     ebx, edx
0x1800109ce  mov     rsi, rcx
0x1800109d1  cmp     ebx, 3E8h
0x1800109d7  jz      short loc_180010A4B
0x1800109d9  mov     edi, ebx
0x1800109db  mov     ebx, 3E8h
0x1800109e0  mov     dl, [r14]; NewIrql
0x1800109e3  lea     rbp, [rsi+348h]
0x1800109ea  mov     rcx, rbp; SpinLock
0x1800109ed  call    cs:__imp_KeReleaseSpinLock
0x1800109f4  nop     dword ptr [rax+rax+00h]
0x1800109f9  mov     edx, edi
0x1800109fb  mov     rcx, rsi
0x1800109fe  call    HIDSM_FindAndSetTargetState
0x180010a03  test    al, al
0x180010a05  jz      short loc_180010A37
0x180010a07  mov     eax, [rsi+370h]
0x180010a0d  mov     ecx, [rsi+rax*4+354h]
0x180010a14  sub     ecx, r12d
0x180010a17  mov     rcx, [r15+rcx*8]
0x180010a1b  mov     eax, [rcx+10h]
0x180010a1e  test    al, 10h
0x180010a20  jnz     short loc_180010A9A
0x180010a22  mov     rcx, rsi; Context
0x180010a25  call    HIDSM_ExecuteEntryFunctionsAndPushPopStateMachinesForCurrentState
0x180010a2a  mov     ebx, eax
0x180010a2c  cmp     eax, 3EAh
0x180010a31  jz      loc_180010AD1
0x180010a37  mov     rcx, rbp; SpinLock
0x180010a3a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180010a41  nop     dword ptr [rax+rax+00h]
0x180010a46  mov     [r14], al
0x180010a49  jmp     short loc_1800109D1
0x180010a4b  mov     rcx, rsi
0x180010a4e  call    HIDSM_GetNextEvent
0x180010a53  mov     edi, eax
0x180010a55  cmp     eax, 3E8h
0x180010a5a  jnz     short loc_1800109E0
0x180010a5c  mov     rcx, [rsi+3C0h]
0x180010a63  lea     rdx, StateMachineTag; "State Machine Tag"
0x180010a6a  add     rcx, 280h; RemoveLock
0x180010a71  mov     byte ptr [rsi+350h], 0
0x180010a78  mov     r8d, 20h ; ' '; RemlockSize
0x180010a7e  call    cs:__imp_IoReleaseRemoveLockEx
0x180010a85  nop     dword ptr [rax+rax+00h]
0x180010a8a  add     rsp, 20h
0x180010a8e  pop     r15
0x180010a90  pop     r14
0x180010a92  pop     r12
0x180010a94  pop     rdi
0x180010a95  pop     rsi
0x180010a96  pop     rbp
0x180010a97  pop     rbx
0x180010a98  retn
0x180010a9a  call    cs:__imp_KeGetCurrentIrql
0x180010aa1  nop     dword ptr [rax+rax+00h]
0x180010aa6  test    al, al
0x180010aa8  jz      loc_180010A22
0x180010aae  mov     rcx, [rsi+3D8h]; IoWorkItem
0x180010ab5  lea     rdx, HIDSM_SmWorker; WorkerRoutine
0x180010abc  mov     r9, rsi; Context
0x180010abf  mov     r8d, 1; QueueType
0x180010ac5  call    cs:__imp_IoQueueWorkItem
0x180010acc  nop     dword ptr [rax+rax+00h]
0x180010ad1  mov     rcx, rbp; SpinLock
0x180010ad4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180010adb  nop     dword ptr [rax+rax+00h]
0x180010ae0  mov     [r14], al
0x180010ae3  jmp     short loc_180010A8A
```
