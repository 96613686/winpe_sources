# FveWorkerWorkStart

- ea: `0x14002d600`
- end: `0x14002d6e4`
- name: `FveWorkerWorkStart`
- size: `228`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400dfd00`

## callees

- `0x14002d600`

## import_xrefs

- `ntoskrnl!KeQueryEffectivePriorityThread` at `0x14002d640`
- `ntoskrnl!KeQueryEffectivePriorityThread` at `0x14002d640`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002d668`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002d668`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14002d6ac`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14002d6d3`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14002d6ac`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14002d6d3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002d616`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002d616`
- `ntoskrnl!KeBugCheckEx` at `0x14002d69b`
- `ntoskrnl!KeBugCheckEx` at `0x14002d69b`

## pseudocode

```c
void __fastcall FveWorkerWorkStart(ULONG_PTR BugCheckParameter2)
{
  KIRQL v2; // al
  ULONG_PTR v3; // r9
  KIRQL v4; // si
  struct _KTHREAD *CurrentThread; // rcx
  int EffectivePriorityThread; // eax
  __int64 v7; // rdx
  __int64 v8; // rdx

  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(BugCheckParameter2 + 56));
  v3 = *(_QWORD *)(BugCheckParameter2 + 88);
  v4 = v2;
  if ( v3 )
    KeBugCheckEx(0x120u, 2u, BugCheckParameter2, v3, 0);
  CurrentThread = KeGetCurrentThread();
  *(_QWORD *)(BugCheckParameter2 + 88) = CurrentThread;
  if ( !CurrentThread )
    CurrentThread = KeGetCurrentThread();
  EffectivePriorityThread = KeQueryEffectivePriorityThread(CurrentThread);
  if ( EffectivePriorityThread >= 32 )
    EffectivePriorityThread = 18;
  v7 = *(unsigned int *)(BugCheckParameter2 + 104);
  if ( EffectivePriorityThread < (int)v7 )
    KeSetActualBasePriorityThread(*(_QWORD *)(BugCheckParameter2 + 88), v7);
  v8 = *(unsigned int *)(BugCheckParameter2 + 108);
  if ( (int)v8 > *(_DWORD *)(BugCheckParameter2 + 104) )
    KeSetActualBasePriorityThread(*(_QWORD *)(BugCheckParameter2 + 88), v8);
  KeReleaseSpinLock((PKSPIN_LOCK)(BugCheckParameter2 + 56), v4);
}

```

## disassembly

```asm
0x14002d600  mov     [rsp+arg_0], rbx
0x14002d605  mov     [rsp+arg_8], rsi
0x14002d60a  push    rdi
0x14002d60b  sub     rsp, 30h
0x14002d60f  mov     rbx, rcx
0x14002d612  add     rcx, 38h ; '8'; SpinLock
0x14002d616  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002d61d  nop     dword ptr [rax+rax+00h]
0x14002d622  mov     r9, [rbx+58h]; BugCheckParameter3
0x14002d626  movzx   esi, al
0x14002d629  test    r9, r9
0x14002d62c  jnz     short loc_14002D685
0x14002d62e  mov     rcx, gs:188h
0x14002d637  mov     [rbx+58h], rcx
0x14002d63b  test    rcx, rcx
0x14002d63e  jz      short loc_14002D6BA
0x14002d640  call    cs:__imp_KeQueryEffectivePriorityThread
0x14002d647  nop     dword ptr [rax+rax+00h]
0x14002d64c  cmp     eax, 20h ; ' '
0x14002d64f  jge     short loc_14002D6C8
0x14002d651  mov     edx, [rbx+68h]
0x14002d654  cmp     eax, edx
0x14002d656  jl      short loc_14002D6A8
0x14002d658  mov     edx, [rbx+6Ch]
0x14002d65b  cmp     edx, [rbx+68h]
0x14002d65e  jg      short loc_14002D6CF
0x14002d660  movzx   edx, sil; NewIrql
0x14002d664  lea     rcx, [rbx+38h]; SpinLock
0x14002d668  call    cs:__imp_KeReleaseSpinLock
0x14002d66f  nop     dword ptr [rax+rax+00h]
0x14002d674  mov     rbx, [rsp+38h+arg_0]
0x14002d679  mov     rsi, [rsp+38h+arg_8]
0x14002d67e  add     rsp, 30h
0x14002d682  pop     rdi
0x14002d683  retn
0x14002d685  mov     r8, rbx; BugCheckParameter2
0x14002d688  mov     [rsp+38h+BugCheckParameter4], 0; BugCheckParameter4
0x14002d691  mov     edx, 2; BugCheckParameter1
0x14002d696  mov     ecx, 120h; BugCheckCode
0x14002d69b  call    cs:__imp_KeBugCheckEx
0x14002d6a8  mov     rcx, [rbx+58h]
0x14002d6ac  call    cs:__imp_KeSetActualBasePriorityThread
0x14002d6b3  nop     dword ptr [rax+rax+00h]
0x14002d6b8  jmp     short loc_14002D658
0x14002d6ba  mov     rcx, gs:188h
0x14002d6c3  jmp     loc_14002D640
0x14002d6c8  mov     eax, 12h
0x14002d6cd  jmp     short loc_14002D651
0x14002d6cf  mov     rcx, [rbx+58h]
0x14002d6d3  call    cs:__imp_KeSetActualBasePriorityThread
0x14002d6da  nop     dword ptr [rax+rax+00h]
0x14002d6df  jmp     loc_14002D660
```
