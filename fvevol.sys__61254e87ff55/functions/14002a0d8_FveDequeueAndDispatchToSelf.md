# FveDequeueAndDispatchToSelf

- ea: `0x14002a0d8`
- end: `0x14002a1f5`
- name: `FveDequeueAndDispatchToSelf`
- size: `285`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140024a64`
- `0x1400251b4`
- `0x1400702fc`
- `0x14009113c`
- `0x1400a5c60`
- `0x1400a5dc4`
- `0x1400a6444`

## callees

- `0x14002a0d8`
- `0x14002a1fc`
- `0x14002a2a0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14002a181`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002a1bb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002a181`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002a1bb`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14002a115`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14002a129`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14002a1de`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14002a115`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14002a129`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14002a1de`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a0fe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a19b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a0fe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a19b`

## pseudocode

```c
void __fastcall FveDequeueAndDispatchToSelf(__int64 a1, _QWORD **a2, KSPIN_LOCK *a3)
{
  struct _KTHREAD *CurrentThread; // rbp
  KIRQL v7; // r14
  unsigned int v8; // r12d
  __int64 v9; // rdx
  __int64 v10; // r9
  _QWORD *v11; // rcx
  _QWORD *v12; // rax
  _QWORD *v13; // r15
  unsigned int PriorityFromIrp; // eax
  unsigned int v15; // edi

  CurrentThread = KeGetCurrentThread();
  v7 = KeAcquireSpinLockRaiseToDpc(a3);
  v8 = KeSetActualBasePriorityThread(CurrentThread, 12);
  v9 = v8;
LABEL_2:
  KeSetActualBasePriorityThread(CurrentThread, v9);
  while ( 1 )
  {
    v11 = *a2;
    if ( *a2 == a2 )
      break;
    if ( (_QWORD **)v11[1] != a2 || (v12 = (_QWORD *)*v11, *(_QWORD **)(*v11 + 8LL) != v11) )
      __fastfail(3u);
    *a2 = v12;
    v13 = v11 - 21;
    v12[1] = a2;
    PriorityFromIrp = GetPriorityFromIrpEx(*(_QWORD *)(a1 + 64), v11 - 21, 12, v10);
    if ( (int)PriorityFromIrp > (int)v8 )
      v15 = KeSetActualBasePriorityThread(CurrentThread, PriorityFromIrp);
    else
      v15 = 0;
    KeReleaseSpinLock(a3, v7);
    FveDispatchToSelf(a1, v13);
    v7 = KeAcquireSpinLockRaiseToDpc(a3);
    if ( v15 )
    {
      v9 = v15;
      goto LABEL_2;
    }
  }
  KeReleaseSpinLock(a3, v7);
}

```

## disassembly

```asm
0x14002a0d8  push    rbx
0x14002a0da  push    rbp
0x14002a0db  push    rsi
0x14002a0dc  push    rdi
0x14002a0dd  push    r12
0x14002a0df  push    r13
0x14002a0e1  push    r14
0x14002a0e3  push    r15
0x14002a0e5  sub     rsp, 28h
0x14002a0e9  mov     rbp, gs:188h
0x14002a0f2  mov     r13, rcx
0x14002a0f5  mov     rcx, r8; SpinLock
0x14002a0f8  mov     rsi, r8
0x14002a0fb  mov     rbx, rdx
0x14002a0fe  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002a105  nop     dword ptr [rax+rax+00h]
0x14002a10a  mov     edx, 0Ch
0x14002a10f  mov     rcx, rbp
0x14002a112  mov     r14b, al
0x14002a115  call    cs:__imp_KeSetActualBasePriorityThread
0x14002a11c  nop     dword ptr [rax+rax+00h]
0x14002a121  mov     r12d, eax
0x14002a124  mov     edx, eax
0x14002a126  mov     rcx, rbp
0x14002a129  call    cs:__imp_KeSetActualBasePriorityThread
0x14002a130  nop     dword ptr [rax+rax+00h]
0x14002a135  mov     rcx, [rbx]
0x14002a138  cmp     rcx, rbx
0x14002a13b  jz      short loc_14002A1B5
0x14002a13d  cmp     [rcx+8], rbx
0x14002a141  jnz     loc_14002A1EE
0x14002a147  mov     rax, [rcx]
0x14002a14a  cmp     [rax+8], rcx
0x14002a14e  jnz     loc_14002A1EE
0x14002a154  mov     [rbx], rax
0x14002a157  lea     r15, [rcx-0A8h]
0x14002a15e  mov     [rax+8], rbx
0x14002a162  mov     rdx, r15
0x14002a165  mov     rcx, [r13+40h]
0x14002a169  mov     r8d, 0Ch
0x14002a16f  call    GetPriorityFromIrpEx
0x14002a174  cmp     eax, r12d
0x14002a177  jg      short loc_14002A1D9
0x14002a179  xor     edi, edi
0x14002a17b  mov     dl, r14b; NewIrql
0x14002a17e  mov     rcx, rsi; SpinLock
0x14002a181  call    cs:__imp_KeReleaseSpinLock
0x14002a188  nop     dword ptr [rax+rax+00h]
0x14002a18d  mov     rdx, r15
0x14002a190  mov     rcx, r13
0x14002a193  call    FveDispatchToSelf
0x14002a198  mov     rcx, rsi; SpinLock
0x14002a19b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002a1a2  nop     dword ptr [rax+rax+00h]
0x14002a1a7  mov     r14b, al
0x14002a1aa  test    edi, edi
0x14002a1ac  jz      short loc_14002A135
0x14002a1ae  mov     edx, edi
0x14002a1b0  jmp     loc_14002A126
0x14002a1b5  mov     dl, r14b; NewIrql
0x14002a1b8  mov     rcx, rsi; SpinLock
0x14002a1bb  call    cs:__imp_KeReleaseSpinLock
0x14002a1c2  nop     dword ptr [rax+rax+00h]
0x14002a1c7  add     rsp, 28h
0x14002a1cb  pop     r15
0x14002a1cd  pop     r14
0x14002a1cf  pop     r13
0x14002a1d1  pop     r12
0x14002a1d3  pop     rdi
0x14002a1d4  pop     rsi
0x14002a1d5  pop     rbp
0x14002a1d6  pop     rbx
0x14002a1d7  retn
0x14002a1d9  mov     edx, eax
0x14002a1db  mov     rcx, rbp
0x14002a1de  call    cs:__imp_KeSetActualBasePriorityThread
0x14002a1e5  nop     dword ptr [rax+rax+00h]
0x14002a1ea  mov     edi, eax
0x14002a1ec  jmp     short loc_14002A17B
0x14002a1ee  mov     ecx, 3
0x14002a1f3  int     29h; Win8: RtlFailFast(ecx)
```
