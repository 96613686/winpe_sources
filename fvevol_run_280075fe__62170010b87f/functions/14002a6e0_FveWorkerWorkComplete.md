# FveWorkerWorkComplete

- ea: `0x14002a6e0`
- end: `0x14002a9a2`
- name: `FveWorkerWorkComplete`
- size: `706`
- prototype: `__int64 __fastcall(PVOID Context, ULONG_PTR BugCheckParameter2)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14002a570`
- `0x1400dce00`

## callees

- `0x1400219a0`
- `0x14002a6e0`
- `0x14002bac0`
- `0x14002bf30`

## import_xrefs

- `ntoskrnl!KeQueryEffectivePriorityThread` at `0x14002a738`
- `ntoskrnl!KeQueryEffectivePriorityThread` at `0x14002a834`
- `ntoskrnl!KeQueryEffectivePriorityThread` at `0x14002a738`
- `ntoskrnl!KeQueryEffectivePriorityThread` at `0x14002a834`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002a7a6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002a8e8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002a7a6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002a8e8`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14002a763`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14002a8d4`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14002a763`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14002a8d4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a6f7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a6f7`
- `ntoskrnl!KeBugCheckEx` at `0x14002a81a`
- `ntoskrnl!KeBugCheckEx` at `0x14002a81a`

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
0x14002a6e0  mov     [rsp+arg_18], rbx
0x14002a6e5  push    rbp
0x14002a6e6  push    rsi
0x14002a6e7  push    r15
0x14002a6e9  sub     rsp, 60h
0x14002a6ed  mov     r15, rcx
0x14002a6f0  mov     rbx, rdx
0x14002a6f3  lea     rcx, [rdx+38h]; SpinLock
0x14002a6f7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002a6fe  nop     dword ptr [rax+rax+00h]
0x14002a703  mov     rcx, [rbx+58h]
0x14002a707  movzx   ebp, al
0x14002a70a  mov     rdx, gs:188h
0x14002a713  cmp     rcx, rdx
0x14002a716  jnz     loc_14002A7FC
0x14002a71c  mov     [rsp+78h+arg_0], rdi
0x14002a724  mov     [rsp+78h+arg_10], r14
0x14002a72c  xor     r14b, r14b
0x14002a72f  test    rcx, rcx
0x14002a732  jz      loc_14002A961
0x14002a738  call    cs:__imp_KeQueryEffectivePriorityThread
0x14002a73f  nop     dword ptr [rax+rax+00h]
0x14002a744  cmp     eax, 20h ; ' '
0x14002a747  jge     loc_14002A96F
0x14002a74d  mov     edi, [rbx+6Ch]
0x14002a750  cmp     eax, edi
0x14002a752  jg      loc_14002A827
0x14002a758  mov     edx, [rbx+68h]
0x14002a75b  cmp     edi, edx
0x14002a75d  jz      short loc_14002A76F
0x14002a75f  mov     rcx, [rbx+58h]
0x14002a763  call    cs:__imp_KeSetActualBasePriorityThread
0x14002a76a  nop     dword ptr [rax+rax+00h]
0x14002a76f  mov     [rsp+78h+arg_8], r12
0x14002a777  cmp     [rbx+90h], r14b
0x14002a77e  jnz     loc_14002A855
0x14002a784  xor     dil, dil
0x14002a787  mov     dword ptr [rbx+64h], 7
0x14002a78e  movzx   edx, bpl; NewIrql
0x14002a792  mov     qword ptr [rbx+68h], 12h
0x14002a79a  lea     rcx, [rbx+38h]; SpinLock
0x14002a79e  mov     qword ptr [rbx+58h], 0FFFFFFFFFFFFFFFFh
0x14002a7a6  call    cs:__imp_KeReleaseSpinLock
0x14002a7ad  nop     dword ptr [rax+rax+00h]
0x14002a7b2  mov     rax, [rbx+48h]
0x14002a7b6  test    rax, rax
0x14002a7b9  jz      short loc_14002A7C7
0x14002a7bb  mov     rdx, [rbx+50h]
0x14002a7bf  mov     rcx, rbx
0x14002a7c2  call    _guard_dispatch_icall
0x14002a7c7  test    dil, dil
0x14002a7ca  jnz     loc_14002A992
0x14002a7d0  xor     al, al
0x14002a7d2  mov     r14, [rsp+78h+arg_10]
0x14002a7da  mov     r12, [rsp+78h+arg_8]
0x14002a7e2  mov     rdi, [rsp+78h+arg_0]
0x14002a7ea  mov     rbx, [rsp+78h+arg_18]
0x14002a7f2  add     rsp, 60h
0x14002a7f6  pop     r15
0x14002a7f8  pop     rsi
0x14002a7f9  pop     rbp
0x14002a7fa  retn
0x14002a7fc  mov     rax, gs:188h
0x14002a805  mov     r9, rcx; BugCheckParameter3
0x14002a808  mov     ecx, 120h; BugCheckCode
0x14002a80d  mov     [rsp+78h+BugCheckParameter4], rax; BugCheckParameter4
0x14002a812  mov     r8, rbx; BugCheckParameter2
0x14002a815  mov     edx, 2; BugCheckParameter1
0x14002a81a  call    cs:__imp_KeBugCheckEx
0x14002a827  mov     rcx, [rbx+58h]
0x14002a82b  test    rcx, rcx
0x14002a82e  jz      loc_14002A979
0x14002a834  call    cs:__imp_KeQueryEffectivePriorityThread
0x14002a83b  nop     dword ptr [rax+rax+00h]
0x14002a840  mov     edi, eax
0x14002a842  cmp     eax, 20h ; ' '
0x14002a845  jl      loc_14002A758
0x14002a84b  mov     edi, 12h
0x14002a850  jmp     loc_14002A758
0x14002a855  mov     eax, [rbx+64h]
0x14002a858  mov     [rbx+90h], r14b
0x14002a85f  cmp     [rbx+8Ch], eax
0x14002a865  jz      short loc_14002A88A
0x14002a867  mov     ecx, 7
0x14002a86c  mov     dword ptr [rbx+64h], 7
0x14002a873  call    FveWorkerQueueTypeToPriority
0x14002a878  mov     [rbx+68h], eax
0x14002a87b  xor     eax, eax
0x14002a87d  mov     [rbx+6Ch], eax
0x14002a880  mov     qword ptr [rbx+58h], 0FFFFFFFFFFFFFFFFh
0x14002a888  jmp     short loc_14002A8E0
0x14002a88a  mov     eax, [rbx+94h]
0x14002a890  mov     r14b, 1
0x14002a893  cmp     eax, edi
0x14002a895  jl      loc_14002A987
0x14002a89b  mov     edi, eax
0x14002a89d  mov     rax, [rbx+70h]
0x14002a8a1  test    rax, rax
0x14002a8a4  jz      short loc_14002A8AA
0x14002a8a6  mov     [rbx+10h], rax
0x14002a8aa  mov     rax, [rbx+78h]
0x14002a8ae  mov     [rbx+18h], rax
0x14002a8b2  mov     rax, [rbx+80h]
0x14002a8b9  mov     [rbx+20h], rax
0x14002a8bd  mov     eax, [rbx+88h]
0x14002a8c3  mov     [rbx+30h], eax
0x14002a8c6  mov     [rbx+6Ch], edi
0x14002a8c9  cmp     edi, [rbx+68h]
0x14002a8cc  jle     short loc_14002A8E0
0x14002a8ce  mov     rcx, [rbx+58h]
0x14002a8d2  mov     edx, edi
0x14002a8d4  call    cs:__imp_KeSetActualBasePriorityThread
0x14002a8db  nop     dword ptr [rax+rax+00h]
0x14002a8e0  movzx   edx, bpl; NewIrql
0x14002a8e4  lea     rcx, [rbx+38h]; SpinLock
0x14002a8e8  call    cs:__imp_KeReleaseSpinLock
0x14002a8ef  nop     dword ptr [rax+rax+00h]
0x14002a8f4  test    r14b, r14b
0x14002a8f7  jnz     loc_14002A99B
0x14002a8fd  mov     eax, [rbx+88h]
0x14002a903  mov     rdx, rbx; BugCheckParameter2
0x14002a906  mov     r9d, [rbx+94h]
0x14002a90d  mov     rcx, r15; Context
0x14002a910  movzx   r8d, byte ptr [rbx+98h]
0x14002a918  mov     [rsp+78h+var_28], r14b; char
0x14002a91d  mov     [rsp+78h+var_30], eax; int
0x14002a921  mov     rax, [rbx+80h]
0x14002a928  mov     [rsp+78h+var_38], rax; __int64
0x14002a92d  mov     rax, [rbx+78h]
0x14002a931  mov     [rsp+78h+var_40], rax; __int64
0x14002a936  mov     rax, [rbx+70h]
0x14002a93a  mov     [rsp+78h+var_48], rax; __int64
0x14002a93f  movzx   eax, byte ptr [rbx+0A0h]
0x14002a946  mov     [rsp+78h+var_50], al; char
0x14002a94a  mov     eax, [rbx+9Ch]
0x14002a950  mov     dword ptr [rsp+78h+BugCheckParameter4], eax; int
0x14002a954  call    FvepQueueWorkItem
0x14002a959  mov     dil, 1
0x14002a95c  jmp     loc_14002A7B2
0x14002a961  mov     rcx, gs:188h
0x14002a96a  jmp     loc_14002A738
0x14002a96f  mov     eax, 12h
0x14002a974  jmp     loc_14002A74D
0x14002a979  mov     rcx, gs:188h
0x14002a982  jmp     loc_14002A834
0x14002a987  mov     [rbx+94h], edi
0x14002a98d  jmp     loc_14002A89D
0x14002a992  test    r14b, r14b
0x14002a995  jz      loc_14002A7D0
0x14002a99b  mov     al, 1
0x14002a99d  jmp     loc_14002A7D2
```
