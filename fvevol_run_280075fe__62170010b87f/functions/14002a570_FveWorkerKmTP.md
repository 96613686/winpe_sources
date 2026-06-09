# FveWorkerKmTP

- ea: `0x14002a570`
- end: `0x14002a6d3`
- name: `FveWorkerKmTP`
- size: `355`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400219a0`
- `0x14002a570`
- `0x14002a6e0`

## import_xrefs

- `ntoskrnl!KeQueryEffectivePriorityThread` at `0x14002a5d8`
- `ntoskrnl!KeQueryEffectivePriorityThread` at `0x14002a5d8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002a608`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002a608`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14002a66f`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14002a6c2`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14002a66f`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14002a6c2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a5a6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a5a6`
- `ntoskrnl!KeBugCheckEx` at `0x14002a65e`
- `ntoskrnl!KeBugCheckEx` at `0x14002a699`
- `ntoskrnl!KeBugCheckEx` at `0x14002a65e`
- `ntoskrnl!KeBugCheckEx` at `0x14002a699`

## pseudocode

```c
void __fastcall FveWorkerKmTP(PVOID IoObject, PVOID Context, PIO_WORKITEM IoWorkItem)
{
  char *v3; // rbx
  KIRQL v5; // al
  ULONG_PTR v6; // r9
  KIRQL v7; // bp
  struct _KTHREAD *CurrentThread; // rcx
  int EffectivePriorityThread; // eax
  __int64 v10; // rdx
  __int64 v11; // rdx

  v3 = (char *)IoWorkItem - 184;
  if ( IoWorkItem == (PIO_WORKITEM)184 || !*((_QWORD *)v3 + 2) )
    KeBugCheckEx(0x120u, 2u, (ULONG_PTR)IoWorkItem - 184, 0, 0);
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v3 + 7);
  v6 = *((_QWORD *)v3 + 11);
  v7 = v5;
  if ( v6 )
    KeBugCheckEx(0x120u, 2u, (ULONG_PTR)v3, v6, 0);
  CurrentThread = KeGetCurrentThread();
  *((_QWORD *)v3 + 11) = CurrentThread;
  if ( !CurrentThread )
    CurrentThread = KeGetCurrentThread();
  EffectivePriorityThread = KeQueryEffectivePriorityThread(CurrentThread);
  if ( EffectivePriorityThread >= 32 )
    EffectivePriorityThread = 18;
  v10 = *((unsigned int *)v3 + 26);
  if ( EffectivePriorityThread < (int)v10 )
    KeSetActualBasePriorityThread(*((_QWORD *)v3 + 11), v10);
  v11 = *((unsigned int *)v3 + 27);
  if ( (int)v11 > *((_DWORD *)v3 + 26) )
    KeSetActualBasePriorityThread(*((_QWORD *)v3 + 11), v11);
  KeReleaseSpinLock((PKSPIN_LOCK)v3 + 7, v7);
  do
    (*((void (__fastcall **)(PVOID, char *))v3 + 2))(Context, v3);
  while ( FveWorkerWorkComplete(Context, (ULONG_PTR)v3) );
}

```

## disassembly

```asm
0x14002a570  mov     [rsp+arg_10], rbx
0x14002a575  push    rsi
0x14002a576  sub     rsp, 30h
0x14002a57a  lea     rbx, [r8-0B8h]
0x14002a581  mov     rsi, rdx
0x14002a584  test    rbx, rbx
0x14002a587  jz      loc_14002A680
0x14002a58d  cmp     qword ptr [rbx+10h], 0
0x14002a592  jz      loc_14002A680
0x14002a598  mov     [rsp+38h+arg_0], rbp
0x14002a59d  lea     rcx, [rbx+38h]; SpinLock
0x14002a5a1  mov     [rsp+38h+arg_8], rdi
0x14002a5a6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002a5ad  nop     dword ptr [rax+rax+00h]
0x14002a5b2  mov     r9, [rbx+58h]; BugCheckParameter3
0x14002a5b6  movzx   ebp, al
0x14002a5b9  test    r9, r9
0x14002a5bc  jnz     loc_14002A648
0x14002a5c2  mov     rcx, gs:188h
0x14002a5cb  mov     [rbx+58h], rcx
0x14002a5cf  test    rcx, rcx
0x14002a5d2  jz      loc_14002A6A6
0x14002a5d8  call    cs:__imp_KeQueryEffectivePriorityThread
0x14002a5df  nop     dword ptr [rax+rax+00h]
0x14002a5e4  cmp     eax, 20h ; ' '
0x14002a5e7  jge     loc_14002A6B4
0x14002a5ed  mov     edx, [rbx+68h]
0x14002a5f0  cmp     eax, edx
0x14002a5f2  jl      short loc_14002A66B
0x14002a5f4  mov     edx, [rbx+6Ch]
0x14002a5f7  cmp     edx, [rbx+68h]
0x14002a5fa  jg      loc_14002A6BE
0x14002a600  movzx   edx, bpl; NewIrql
0x14002a604  lea     rcx, [rbx+38h]; SpinLock
0x14002a608  call    cs:__imp_KeReleaseSpinLock
0x14002a60f  nop     dword ptr [rax+rax+00h]
0x14002a614  mov     rax, [rbx+10h]
0x14002a618  mov     rdx, rbx
0x14002a61b  mov     rcx, rsi
0x14002a61e  call    _guard_dispatch_icall
0x14002a623  mov     rdx, rbx; BugCheckParameter2
0x14002a626  mov     rcx, rsi; Context
0x14002a629  call    FveWorkerWorkComplete
0x14002a62e  test    al, al
0x14002a630  jnz     short loc_14002A614
0x14002a632  mov     rbp, [rsp+38h+arg_0]
0x14002a637  mov     rdi, [rsp+38h+arg_8]
0x14002a63c  mov     rbx, [rsp+38h+arg_10]
0x14002a641  add     rsp, 30h
0x14002a645  pop     rsi
0x14002a646  retn
0x14002a648  mov     r8, rbx; BugCheckParameter2
0x14002a64b  mov     [rsp+38h+BugCheckParameter4], 0; BugCheckParameter4
0x14002a654  mov     edx, 2; BugCheckParameter1
0x14002a659  mov     ecx, 120h; BugCheckCode
0x14002a65e  call    cs:__imp_KeBugCheckEx
0x14002a66b  mov     rcx, [rbx+58h]
0x14002a66f  call    cs:__imp_KeSetActualBasePriorityThread
0x14002a676  nop     dword ptr [rax+rax+00h]
0x14002a67b  jmp     loc_14002A5F4
0x14002a680  xor     r9d, r9d; BugCheckParameter3
0x14002a683  mov     [rsp+38h+BugCheckParameter4], 0; BugCheckParameter4
0x14002a68c  mov     r8, rbx; BugCheckParameter2
0x14002a68f  mov     edx, 2; BugCheckParameter1
0x14002a694  mov     ecx, 120h; BugCheckCode
0x14002a699  call    cs:__imp_KeBugCheckEx
0x14002a6a6  mov     rcx, gs:188h
0x14002a6af  jmp     loc_14002A5D8
0x14002a6b4  mov     eax, 12h
0x14002a6b9  jmp     loc_14002A5ED
0x14002a6be  mov     rcx, [rbx+58h]
0x14002a6c2  call    cs:__imp_KeSetActualBasePriorityThread
0x14002a6c9  nop     dword ptr [rax+rax+00h]
0x14002a6ce  jmp     loc_14002A600
```
