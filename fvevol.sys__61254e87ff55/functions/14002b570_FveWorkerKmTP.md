# FveWorkerKmTP

- ea: `0x14002b570`
- end: `0x14002b6d3`
- name: `FveWorkerKmTP`
- size: `355`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140022cd0`
- `0x14002b570`
- `0x14002b6e0`

## import_xrefs

- `ntoskrnl!KeQueryEffectivePriorityThread` at `0x14002b5d8`
- `ntoskrnl!KeQueryEffectivePriorityThread` at `0x14002b5d8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b608`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b608`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14002b66f`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14002b6c2`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14002b66f`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14002b6c2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002b5a6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002b5a6`
- `ntoskrnl!KeBugCheckEx` at `0x14002b65e`
- `ntoskrnl!KeBugCheckEx` at `0x14002b699`
- `ntoskrnl!KeBugCheckEx` at `0x14002b65e`
- `ntoskrnl!KeBugCheckEx` at `0x14002b699`

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
0x14002b570  mov     [rsp+arg_10], rbx
0x14002b575  push    rsi
0x14002b576  sub     rsp, 30h
0x14002b57a  lea     rbx, [r8-0B8h]
0x14002b581  mov     rsi, rdx
0x14002b584  test    rbx, rbx
0x14002b587  jz      loc_14002B680
0x14002b58d  cmp     qword ptr [rbx+10h], 0
0x14002b592  jz      loc_14002B680
0x14002b598  mov     [rsp+38h+arg_0], rbp
0x14002b59d  lea     rcx, [rbx+38h]; SpinLock
0x14002b5a1  mov     [rsp+38h+arg_8], rdi
0x14002b5a6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002b5ad  nop     dword ptr [rax+rax+00h]
0x14002b5b2  mov     r9, [rbx+58h]; BugCheckParameter3
0x14002b5b6  movzx   ebp, al
0x14002b5b9  test    r9, r9
0x14002b5bc  jnz     loc_14002B648
0x14002b5c2  mov     rcx, gs:188h
0x14002b5cb  mov     [rbx+58h], rcx
0x14002b5cf  test    rcx, rcx
0x14002b5d2  jz      loc_14002B6A6
0x14002b5d8  call    cs:__imp_KeQueryEffectivePriorityThread
0x14002b5df  nop     dword ptr [rax+rax+00h]
0x14002b5e4  cmp     eax, 20h ; ' '
0x14002b5e7  jge     loc_14002B6B4
0x14002b5ed  mov     edx, [rbx+68h]
0x14002b5f0  cmp     eax, edx
0x14002b5f2  jl      short loc_14002B66B
0x14002b5f4  mov     edx, [rbx+6Ch]
0x14002b5f7  cmp     edx, [rbx+68h]
0x14002b5fa  jg      loc_14002B6BE
0x14002b600  movzx   edx, bpl; NewIrql
0x14002b604  lea     rcx, [rbx+38h]; SpinLock
0x14002b608  call    cs:__imp_KeReleaseSpinLock
0x14002b60f  nop     dword ptr [rax+rax+00h]
0x14002b614  mov     rax, [rbx+10h]
0x14002b618  mov     rdx, rbx
0x14002b61b  mov     rcx, rsi
0x14002b61e  call    _guard_dispatch_icall
0x14002b623  mov     rdx, rbx; BugCheckParameter2
0x14002b626  mov     rcx, rsi; Context
0x14002b629  call    FveWorkerWorkComplete
0x14002b62e  test    al, al
0x14002b630  jnz     short loc_14002B614
0x14002b632  mov     rbp, [rsp+38h+arg_0]
0x14002b637  mov     rdi, [rsp+38h+arg_8]
0x14002b63c  mov     rbx, [rsp+38h+arg_10]
0x14002b641  add     rsp, 30h
0x14002b645  pop     rsi
0x14002b646  retn
0x14002b648  mov     r8, rbx; BugCheckParameter2
0x14002b64b  mov     [rsp+38h+BugCheckParameter4], 0; BugCheckParameter4
0x14002b654  mov     edx, 2; BugCheckParameter1
0x14002b659  mov     ecx, 120h; BugCheckCode
0x14002b65e  call    cs:__imp_KeBugCheckEx
0x14002b66b  mov     rcx, [rbx+58h]
0x14002b66f  call    cs:__imp_KeSetActualBasePriorityThread
0x14002b676  nop     dword ptr [rax+rax+00h]
0x14002b67b  jmp     loc_14002B5F4
0x14002b680  xor     r9d, r9d; BugCheckParameter3
0x14002b683  mov     [rsp+38h+BugCheckParameter4], 0; BugCheckParameter4
0x14002b68c  mov     r8, rbx; BugCheckParameter2
0x14002b68f  mov     edx, 2; BugCheckParameter1
0x14002b694  mov     ecx, 120h; BugCheckCode
0x14002b699  call    cs:__imp_KeBugCheckEx
0x14002b6a6  mov     rcx, gs:188h
0x14002b6af  jmp     loc_14002B5D8
0x14002b6b4  mov     eax, 12h
0x14002b6b9  jmp     loc_14002B5ED
0x14002b6be  mov     rcx, [rbx+58h]
0x14002b6c2  call    cs:__imp_KeSetActualBasePriorityThread
0x14002b6c9  nop     dword ptr [rax+rax+00h]
0x14002b6ce  jmp     loc_14002B600
```
