# FveDequeueAndDispatchToSelf

- ea: `0x1400290d8`
- end: `0x1400291f5`
- name: `FveDequeueAndDispatchToSelf`
- size: `285`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140023a64`
- `0x1400241b4`
- `0x14006e26c`
- `0x14008f08c`
- `0x1400a4d08`
- `0x1400a4e6c`
- `0x1400a54ec`

## callees

- `0x1400290d8`
- `0x1400291fc`
- `0x1400292a0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140029181`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400291bb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140029181`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400291bb`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x140029115`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x140029129`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400291de`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x140029115`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x140029129`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400291de`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400290fe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002919b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400290fe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002919b`

## pseudocode

```c
void __fastcall FveDequeueAndDispatchToSelf(__int64 a1, _QWORD **a2, KSPIN_LOCK *a3)
{
  struct _KTHREAD *CurrentThread; // rbp
  KIRQL v7; // r14
  unsigned int v8; // r12d
  __int64 v9; // rdx
  _QWORD *v10; // rcx
  _QWORD *v11; // rax
  _QWORD *v12; // r15
  unsigned int PriorityFromIrp; // eax
  unsigned int v14; // edi

  CurrentThread = KeGetCurrentThread();
  v7 = KeAcquireSpinLockRaiseToDpc(a3);
  v8 = KeSetActualBasePriorityThread(CurrentThread, 12);
  v9 = v8;
LABEL_2:
  KeSetActualBasePriorityThread(CurrentThread, v9);
  while ( 1 )
  {
    v10 = *a2;
    if ( *a2 == a2 )
      break;
    if ( (_QWORD **)v10[1] != a2 || (v11 = (_QWORD *)*v10, *(_QWORD **)(*v10 + 8LL) != v10) )
      __fastfail(3u);
    *a2 = v11;
    v12 = v10 - 21;
    v11[1] = a2;
    PriorityFromIrp = GetPriorityFromIrpEx(*(_QWORD *)(a1 + 64), v10 - 21, 12);
    if ( (int)PriorityFromIrp > (int)v8 )
      v14 = KeSetActualBasePriorityThread(CurrentThread, PriorityFromIrp);
    else
      v14 = 0;
    KeReleaseSpinLock(a3, v7);
    FveDispatchToSelf(a1, v12);
    v7 = KeAcquireSpinLockRaiseToDpc(a3);
    if ( v14 )
    {
      v9 = v14;
      goto LABEL_2;
    }
  }
  KeReleaseSpinLock(a3, v7);
}

```

## disassembly

```asm
0x1400290d8  push    rbx
0x1400290da  push    rbp
0x1400290db  push    rsi
0x1400290dc  push    rdi
0x1400290dd  push    r12
0x1400290df  push    r13
0x1400290e1  push    r14
0x1400290e3  push    r15
0x1400290e5  sub     rsp, 28h
0x1400290e9  mov     rbp, gs:188h
0x1400290f2  mov     r13, rcx
0x1400290f5  mov     rcx, r8; SpinLock
0x1400290f8  mov     rsi, r8
0x1400290fb  mov     rbx, rdx
0x1400290fe  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140029105  nop     dword ptr [rax+rax+00h]
0x14002910a  mov     edx, 0Ch
0x14002910f  mov     rcx, rbp
0x140029112  mov     r14b, al
0x140029115  call    cs:__imp_KeSetActualBasePriorityThread
0x14002911c  nop     dword ptr [rax+rax+00h]
0x140029121  mov     r12d, eax
0x140029124  mov     edx, eax
0x140029126  mov     rcx, rbp
0x140029129  call    cs:__imp_KeSetActualBasePriorityThread
0x140029130  nop     dword ptr [rax+rax+00h]
0x140029135  mov     rcx, [rbx]
0x140029138  cmp     rcx, rbx
0x14002913b  jz      short loc_1400291B5
0x14002913d  cmp     [rcx+8], rbx
0x140029141  jnz     loc_1400291EE
0x140029147  mov     rax, [rcx]
0x14002914a  cmp     [rax+8], rcx
0x14002914e  jnz     loc_1400291EE
0x140029154  mov     [rbx], rax
0x140029157  lea     r15, [rcx-0A8h]
0x14002915e  mov     [rax+8], rbx
0x140029162  mov     rdx, r15
0x140029165  mov     rcx, [r13+40h]
0x140029169  mov     r8d, 0Ch
0x14002916f  call    GetPriorityFromIrpEx
0x140029174  cmp     eax, r12d
0x140029177  jg      short loc_1400291D9
0x140029179  xor     edi, edi
0x14002917b  mov     dl, r14b; NewIrql
0x14002917e  mov     rcx, rsi; SpinLock
0x140029181  call    cs:__imp_KeReleaseSpinLock
0x140029188  nop     dword ptr [rax+rax+00h]
0x14002918d  mov     rdx, r15
0x140029190  mov     rcx, r13
0x140029193  call    FveDispatchToSelf
0x140029198  mov     rcx, rsi; SpinLock
0x14002919b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400291a2  nop     dword ptr [rax+rax+00h]
0x1400291a7  mov     r14b, al
0x1400291aa  test    edi, edi
0x1400291ac  jz      short loc_140029135
0x1400291ae  mov     edx, edi
0x1400291b0  jmp     loc_140029126
0x1400291b5  mov     dl, r14b; NewIrql
0x1400291b8  mov     rcx, rsi; SpinLock
0x1400291bb  call    cs:__imp_KeReleaseSpinLock
0x1400291c2  nop     dword ptr [rax+rax+00h]
0x1400291c7  add     rsp, 28h
0x1400291cb  pop     r15
0x1400291cd  pop     r14
0x1400291cf  pop     r13
0x1400291d1  pop     r12
0x1400291d3  pop     rdi
0x1400291d4  pop     rsi
0x1400291d5  pop     rbp
0x1400291d6  pop     rbx
0x1400291d7  retn
0x1400291d9  mov     edx, eax
0x1400291db  mov     rcx, rbp
0x1400291de  call    cs:__imp_KeSetActualBasePriorityThread
0x1400291e5  nop     dword ptr [rax+rax+00h]
0x1400291ea  mov     edi, eax
0x1400291ec  jmp     short loc_14002917B
0x1400291ee  mov     ecx, 3
0x1400291f3  int     29h; Win8: RtlFailFast(ecx)
```
