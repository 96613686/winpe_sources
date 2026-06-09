# FveRundownAllReadsAndWritesEx

- ea: `0x1400230e8`
- end: `0x14002322d`
- name: `FveRundownAllReadsAndWritesEx`
- size: `325`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14002e334`
- `0x1400c61d4`

## callees

- `0x1400230e8`
- `0x1400bea68`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x1400231b4`
- `ntoskrnl!KfRaiseIrql` at `0x1400231b4`
- `ntoskrnl!KeLowerIrql` at `0x140023213`
- `ntoskrnl!KeLowerIrql` at `0x140023213`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002311e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002311e`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14002316f`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1400231a0`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14002316f`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1400231a0`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14002318b`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14002318b`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400231d5`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400231f8`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400231d5`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400231f8`

## pseudocode

```c
void __fastcall FveRundownAllReadsAndWritesEx(__int64 a1, int a2, unsigned int a3)
{
  struct _KTHREAD *CurrentThread; // r14
  KIRQL CurrentIrql; // di
  __int64 v8; // r9
  _QWORD *v9; // rax
  __int64 v10; // rdx
  signed int v11; // eax

  if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 1472)) == 1 )
  {
    CurrentThread = KeGetCurrentThread();
    CurrentIrql = KeGetCurrentIrql();
    if ( (*(_DWORD *)(a1 + 808) & 0x100) != 0 )
    {
      v9 = *(_QWORD **)(a1 + 736);
      if ( v9 )
      {
        if ( *v9 )
        {
          v10 = (unsigned int)a2;
          LOBYTE(v8) = 1;
          if ( a2 <= 12 )
            v10 = 12;
          FveEowBoostConversionPriority(a1, v10, a3, v8);
        }
      }
    }
    ExWaitForRundownProtectionReleaseCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1464));
    if ( *(_BYTE *)(a1 + 1476) )
      ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)(a1 + 1448));
    else
      ExWaitForRundownProtectionReleaseCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1456));
    if ( CurrentIrql < 2u )
      CurrentIrql = KfRaiseIrql(2u);
    if ( a2 <= 12 )
      a2 = 12;
    *(_DWORD *)(a1 + 1484) = a2;
    v11 = KeSetActualBasePriorityThread(CurrentThread, (unsigned int)a2);
    if ( v11 >= *(_DWORD *)(a1 + 1484) )
    {
      if ( v11 > *(_DWORD *)(a1 + 1484) )
        KeSetActualBasePriorityThread(CurrentThread, (unsigned int)v11);
    }
    else
    {
      *(_DWORD *)(a1 + 1480) = v11;
    }
    *(_DWORD *)(a1 + 1488) = a3;
    if ( CurrentIrql < 2u )
      KeLowerIrql(CurrentIrql);
  }
}

```

## disassembly

```asm
0x1400230e8  push    rbx
0x1400230ea  push    rbp
0x1400230eb  push    rsi
0x1400230ec  push    rdi
0x1400230ed  push    r14
0x1400230ef  push    r15
0x1400230f1  sub     rsp, 28h
0x1400230f5  mov     ebp, r8d
0x1400230f8  mov     esi, edx
0x1400230fa  mov     rbx, rcx
0x1400230fd  mov     eax, 1
0x140023102  lock xadd [rcx+5C0h], eax
0x14002310a  inc     eax
0x14002310c  cmp     eax, 1
0x14002310f  jnz     loc_14002321F
0x140023115  mov     r14, gs:188h
0x14002311e  call    cs:__imp_KeGetCurrentIrql
0x140023125  nop     dword ptr [rax+rax+00h]
0x14002312a  test    dword ptr [rbx+328h], 100h
0x140023134  mov     r15d, 0Ch
0x14002313a  mov     dil, al
0x14002313d  jz      short loc_140023168
0x14002313f  mov     rax, [rbx+2E0h]
0x140023146  test    rax, rax
0x140023149  jz      short loc_140023168
0x14002314b  cmp     qword ptr [rax], 0
0x14002314f  jz      short loc_140023168
0x140023151  cmp     esi, r15d
0x140023154  mov     edx, esi
0x140023156  mov     r9b, 1
0x140023159  mov     r8d, ebp
0x14002315c  cmovle  edx, r15d
0x140023160  mov     rcx, rbx
0x140023163  call    FveEowBoostConversionPriority
0x140023168  mov     rcx, [rbx+5B8h]; RunRef
0x14002316f  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x140023176  nop     dword ptr [rax+rax+00h]
0x14002317b  cmp     byte ptr [rbx+5C4h], 0
0x140023182  jz      short loc_140023199
0x140023184  lea     rcx, [rbx+5A8h]; RunRef
0x14002318b  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140023192  nop     dword ptr [rax+rax+00h]
0x140023197  jmp     short loc_1400231AC
0x140023199  mov     rcx, [rbx+5B0h]; RunRef
0x1400231a0  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x1400231a7  nop     dword ptr [rax+rax+00h]
0x1400231ac  cmp     dil, 2
0x1400231b0  jnb     short loc_1400231C3
0x1400231b2  mov     cl, 2; NewIrql
0x1400231b4  call    cs:__imp_KfRaiseIrql
0x1400231bb  nop     dword ptr [rax+rax+00h]
0x1400231c0  mov     dil, al
0x1400231c3  cmp     esi, r15d
0x1400231c6  mov     rcx, r14
0x1400231c9  cmovle  esi, r15d
0x1400231cd  mov     edx, esi
0x1400231cf  mov     [rbx+5CCh], esi
0x1400231d5  call    cs:__imp_KeSetActualBasePriorityThread
0x1400231dc  nop     dword ptr [rax+rax+00h]
0x1400231e1  cmp     eax, [rbx+5CCh]
0x1400231e7  jge     short loc_1400231F1
0x1400231e9  mov     [rbx+5C8h], eax
0x1400231ef  jmp     short loc_140023204
0x1400231f1  jle     short loc_140023204
0x1400231f3  mov     edx, eax
0x1400231f5  mov     rcx, r14
0x1400231f8  call    cs:__imp_KeSetActualBasePriorityThread
0x1400231ff  nop     dword ptr [rax+rax+00h]
0x140023204  mov     [rbx+5D0h], ebp
0x14002320a  cmp     dil, 2
0x14002320e  jnb     short loc_14002321F
0x140023210  mov     cl, dil; NewIrql
0x140023213  call    cs:__imp_KeLowerIrql
0x14002321a  nop     dword ptr [rax+rax+00h]
0x14002321f  add     rsp, 28h
0x140023223  pop     r15
0x140023225  pop     r14
0x140023227  pop     rdi
0x140023228  pop     rsi
0x140023229  pop     rbp
0x14002322a  pop     rbx
0x14002322b  retn
```
