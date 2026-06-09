# FveWorkerWorkComplete

- ea: `0x14002b6e0`
- end: `0x14002b9a2`
- name: `FveWorkerWorkComplete`
- size: `706`
- prototype: `__int64 __fastcall(PVOID Context, ULONG_PTR BugCheckParameter2)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14002b570`
- `0x1400dfd00`

## callees

- `0x140022cd0`
- `0x14002b6e0`
- `0x14002cac0`
- `0x14002cf30`

## import_xrefs

- `ntoskrnl!KeQueryEffectivePriorityThread` at `0x14002b738`
- `ntoskrnl!KeQueryEffectivePriorityThread` at `0x14002b834`
- `ntoskrnl!KeQueryEffectivePriorityThread` at `0x14002b738`
- `ntoskrnl!KeQueryEffectivePriorityThread` at `0x14002b834`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b7a6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b8e8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b7a6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b8e8`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14002b763`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14002b8d4`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14002b763`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14002b8d4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002b6f7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002b6f7`
- `ntoskrnl!KeBugCheckEx` at `0x14002b81a`
- `ntoskrnl!KeBugCheckEx` at `0x14002b81a`

## pseudocode

```c
char __fastcall FveWorkerWorkComplete(PVOID Context, ULONG_PTR BugCheckParameter2)
{
  KIRQL v4; // al
  struct _KTHREAD *CurrentThread; // rcx
  KIRQL v6; // bp
  char v7; // r14
  int EffectivePriorityThread; // eax
  int v9; // edi
  __int64 v10; // rdx
  void (__fastcall *v11)(ULONG_PTR, _QWORD); // rax
  struct _KTHREAD *v13; // rcx
  int v14; // eax
  __int64 v15; // rax

  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(BugCheckParameter2 + 56));
  CurrentThread = *(struct _KTHREAD **)(BugCheckParameter2 + 88);
  v6 = v4;
  if ( CurrentThread != KeGetCurrentThread() )
    KeBugCheckEx(0x120u, 2u, BugCheckParameter2, *(_QWORD *)(BugCheckParameter2 + 88), (ULONG_PTR)KeGetCurrentThread());
  v7 = 0;
  if ( !CurrentThread )
    CurrentThread = KeGetCurrentThread();
  EffectivePriorityThread = KeQueryEffectivePriorityThread(CurrentThread);
  if ( EffectivePriorityThread >= 32 )
    EffectivePriorityThread = 18;
  v9 = *(_DWORD *)(BugCheckParameter2 + 108);
  if ( EffectivePriorityThread > v9 )
  {
    v13 = *(struct _KTHREAD **)(BugCheckParameter2 + 88);
    if ( !v13 )
      v13 = KeGetCurrentThread();
    v9 = KeQueryEffectivePriorityThread(v13);
    if ( v9 >= 32 )
      v9 = 18;
  }
  v10 = *(unsigned int *)(BugCheckParameter2 + 104);
  if ( v9 != (_DWORD)v10 )
    KeSetActualBasePriorityThread(*(_QWORD *)(BugCheckParameter2 + 88), v10);
  if ( *(_BYTE *)(BugCheckParameter2 + 144) )
  {
    v14 = *(_DWORD *)(BugCheckParameter2 + 100);
    *(_BYTE *)(BugCheckParameter2 + 144) = 0;
    if ( *(_DWORD *)(BugCheckParameter2 + 140) == v14 )
    {
      v7 = 1;
      if ( *(_DWORD *)(BugCheckParameter2 + 148) < v9 )
        *(_DWORD *)(BugCheckParameter2 + 148) = v9;
      else
        v9 = *(_DWORD *)(BugCheckParameter2 + 148);
      v15 = *(_QWORD *)(BugCheckParameter2 + 112);
      if ( v15 )
        *(_QWORD *)(BugCheckParameter2 + 16) = v15;
      *(_QWORD *)(BugCheckParameter2 + 24) = *(_QWORD *)(BugCheckParameter2 + 120);
      *(_QWORD *)(BugCheckParameter2 + 32) = *(_QWORD *)(BugCheckParameter2 + 128);
      *(_DWORD *)(BugCheckParameter2 + 48) = *(_DWORD *)(BugCheckParameter2 + 136);
      *(_DWORD *)(BugCheckParameter2 + 108) = v9;
      if ( v9 > *(_DWORD *)(BugCheckParameter2 + 104) )
        KeSetActualBasePriorityThread(*(_QWORD *)(BugCheckParameter2 + 88), (unsigned int)v9);
    }
    else
    {
      *(_DWORD *)(BugCheckParameter2 + 100) = 7;
      *(_QWORD *)(BugCheckParameter2 + 104) = (unsigned int)FveWorkerQueueTypeToPriority(7);
      *(_QWORD *)(BugCheckParameter2 + 88) = -1;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(BugCheckParameter2 + 56), v6);
    if ( v7 )
      return 1;
    FvepQueueWorkItem(
      Context,
      BugCheckParameter2,
      *(_DWORD *)(BugCheckParameter2 + 156),
      *(_BYTE *)(BugCheckParameter2 + 160),
      *(_QWORD *)(BugCheckParameter2 + 112),
      *(_QWORD *)(BugCheckParameter2 + 120),
      *(_QWORD *)(BugCheckParameter2 + 128),
      *(_DWORD *)(BugCheckParameter2 + 136),
      0);
  }
  else
  {
    *(_DWORD *)(BugCheckParameter2 + 100) = 7;
    *(_QWORD *)(BugCheckParameter2 + 104) = 18;
    *(_QWORD *)(BugCheckParameter2 + 88) = -1;
    KeReleaseSpinLock((PKSPIN_LOCK)(BugCheckParameter2 + 56), v6);
  }
  v11 = *(void (__fastcall **)(ULONG_PTR, _QWORD))(BugCheckParameter2 + 72);
  if ( v11 )
    v11(BugCheckParameter2, *(_QWORD *)(BugCheckParameter2 + 80));
  return 0;
}

```

## disassembly

```asm
0x14002b6e0  mov     [rsp+arg_18], rbx
0x14002b6e5  push    rbp
0x14002b6e6  push    rsi
0x14002b6e7  push    r15
0x14002b6e9  sub     rsp, 60h
0x14002b6ed  mov     r15, rcx
0x14002b6f0  mov     rbx, rdx
0x14002b6f3  lea     rcx, [rdx+38h]; SpinLock
0x14002b6f7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002b6fe  nop     dword ptr [rax+rax+00h]
0x14002b703  mov     rcx, [rbx+58h]
0x14002b707  movzx   ebp, al
0x14002b70a  mov     rdx, gs:188h
0x14002b713  cmp     rcx, rdx
0x14002b716  jnz     loc_14002B7FC
0x14002b71c  mov     [rsp+78h+arg_0], rdi
0x14002b724  mov     [rsp+78h+arg_10], r14
0x14002b72c  xor     r14b, r14b
0x14002b72f  test    rcx, rcx
0x14002b732  jz      loc_14002B961
0x14002b738  call    cs:__imp_KeQueryEffectivePriorityThread
0x14002b73f  nop     dword ptr [rax+rax+00h]
0x14002b744  cmp     eax, 20h ; ' '
0x14002b747  jge     loc_14002B96F
0x14002b74d  mov     edi, [rbx+6Ch]
0x14002b750  cmp     eax, edi
0x14002b752  jg      loc_14002B827
0x14002b758  mov     edx, [rbx+68h]
0x14002b75b  cmp     edi, edx
0x14002b75d  jz      short loc_14002B76F
0x14002b75f  mov     rcx, [rbx+58h]
0x14002b763  call    cs:__imp_KeSetActualBasePriorityThread
0x14002b76a  nop     dword ptr [rax+rax+00h]
0x14002b76f  mov     [rsp+78h+arg_8], r12
0x14002b777  cmp     [rbx+90h], r14b
0x14002b77e  jnz     loc_14002B855
0x14002b784  xor     dil, dil
0x14002b787  mov     dword ptr [rbx+64h], 7
0x14002b78e  movzx   edx, bpl; NewIrql
0x14002b792  mov     qword ptr [rbx+68h], 12h
0x14002b79a  lea     rcx, [rbx+38h]; SpinLock
0x14002b79e  mov     qword ptr [rbx+58h], 0FFFFFFFFFFFFFFFFh
0x14002b7a6  call    cs:__imp_KeReleaseSpinLock
0x14002b7ad  nop     dword ptr [rax+rax+00h]
0x14002b7b2  mov     rax, [rbx+48h]
0x14002b7b6  test    rax, rax
0x14002b7b9  jz      short loc_14002B7C7
0x14002b7bb  mov     rdx, [rbx+50h]
0x14002b7bf  mov     rcx, rbx
0x14002b7c2  call    _guard_dispatch_icall
0x14002b7c7  test    dil, dil
0x14002b7ca  jnz     loc_14002B992
0x14002b7d0  xor     al, al
0x14002b7d2  mov     r14, [rsp+78h+arg_10]
0x14002b7da  mov     r12, [rsp+78h+arg_8]
0x14002b7e2  mov     rdi, [rsp+78h+arg_0]
0x14002b7ea  mov     rbx, [rsp+78h+arg_18]
0x14002b7f2  add     rsp, 60h
0x14002b7f6  pop     r15
0x14002b7f8  pop     rsi
0x14002b7f9  pop     rbp
0x14002b7fa  retn
0x14002b7fc  mov     rax, gs:188h
0x14002b805  mov     r9, rcx; BugCheckParameter3
0x14002b808  mov     ecx, 120h; BugCheckCode
0x14002b80d  mov     [rsp+78h+BugCheckParameter4], rax; BugCheckParameter4
0x14002b812  mov     r8, rbx; BugCheckParameter2
0x14002b815  mov     edx, 2; BugCheckParameter1
0x14002b81a  call    cs:__imp_KeBugCheckEx
0x14002b827  mov     rcx, [rbx+58h]
0x14002b82b  test    rcx, rcx
0x14002b82e  jz      loc_14002B979
0x14002b834  call    cs:__imp_KeQueryEffectivePriorityThread
0x14002b83b  nop     dword ptr [rax+rax+00h]
0x14002b840  mov     edi, eax
0x14002b842  cmp     eax, 20h ; ' '
0x14002b845  jl      loc_14002B758
0x14002b84b  mov     edi, 12h
0x14002b850  jmp     loc_14002B758
0x14002b855  mov     eax, [rbx+64h]
0x14002b858  mov     [rbx+90h], r14b
0x14002b85f  cmp     [rbx+8Ch], eax
0x14002b865  jz      short loc_14002B88A
0x14002b867  mov     ecx, 7
0x14002b86c  mov     dword ptr [rbx+64h], 7
0x14002b873  call    FveWorkerQueueTypeToPriority
0x14002b878  mov     [rbx+68h], eax
0x14002b87b  xor     eax, eax
0x14002b87d  mov     [rbx+6Ch], eax
0x14002b880  mov     qword ptr [rbx+58h], 0FFFFFFFFFFFFFFFFh
0x14002b888  jmp     short loc_14002B8E0
0x14002b88a  mov     eax, [rbx+94h]
0x14002b890  mov     r14b, 1
0x14002b893  cmp     eax, edi
0x14002b895  jl      loc_14002B987
0x14002b89b  mov     edi, eax
0x14002b89d  mov     rax, [rbx+70h]
0x14002b8a1  test    rax, rax
0x14002b8a4  jz      short loc_14002B8AA
0x14002b8a6  mov     [rbx+10h], rax
0x14002b8aa  mov     rax, [rbx+78h]
0x14002b8ae  mov     [rbx+18h], rax
0x14002b8b2  mov     rax, [rbx+80h]
0x14002b8b9  mov     [rbx+20h], rax
0x14002b8bd  mov     eax, [rbx+88h]
0x14002b8c3  mov     [rbx+30h], eax
0x14002b8c6  mov     [rbx+6Ch], edi
0x14002b8c9  cmp     edi, [rbx+68h]
0x14002b8cc  jle     short loc_14002B8E0
0x14002b8ce  mov     rcx, [rbx+58h]
0x14002b8d2  mov     edx, edi
0x14002b8d4  call    cs:__imp_KeSetActualBasePriorityThread
0x14002b8db  nop     dword ptr [rax+rax+00h]
0x14002b8e0  movzx   edx, bpl; NewIrql
0x14002b8e4  lea     rcx, [rbx+38h]; SpinLock
0x14002b8e8  call    cs:__imp_KeReleaseSpinLock
0x14002b8ef  nop     dword ptr [rax+rax+00h]
0x14002b8f4  test    r14b, r14b
0x14002b8f7  jnz     loc_14002B99B
0x14002b8fd  mov     eax, [rbx+88h]
0x14002b903  mov     rdx, rbx; BugCheckParameter2
0x14002b906  mov     r9d, [rbx+94h]
0x14002b90d  mov     rcx, r15; Context
0x14002b910  movzx   r8d, byte ptr [rbx+98h]
0x14002b918  mov     [rsp+78h+var_28], r14b; char
0x14002b91d  mov     [rsp+78h+var_30], eax; int
0x14002b921  mov     rax, [rbx+80h]
0x14002b928  mov     [rsp+78h+var_38], rax; __int64
0x14002b92d  mov     rax, [rbx+78h]
0x14002b931  mov     [rsp+78h+var_40], rax; __int64
0x14002b936  mov     rax, [rbx+70h]
0x14002b93a  mov     [rsp+78h+var_48], rax; __int64
0x14002b93f  movzx   eax, byte ptr [rbx+0A0h]
0x14002b946  mov     [rsp+78h+var_50], al; char
0x14002b94a  mov     eax, [rbx+9Ch]
0x14002b950  mov     dword ptr [rsp+78h+BugCheckParameter4], eax; int
0x14002b954  call    FvepQueueWorkItem
0x14002b959  mov     dil, 1
0x14002b95c  jmp     loc_14002B7B2
0x14002b961  mov     rcx, gs:188h
0x14002b96a  jmp     loc_14002B738
0x14002b96f  mov     eax, 12h
0x14002b974  jmp     loc_14002B74D
0x14002b979  mov     rcx, gs:188h
0x14002b982  jmp     loc_14002B834
0x14002b987  mov     [rbx+94h], edi
0x14002b98d  jmp     loc_14002B89D
0x14002b992  test    r14b, r14b
0x14002b995  jz      loc_14002B7D0
0x14002b99b  mov     al, 1
0x14002b99d  jmp     loc_14002B7D2
```
