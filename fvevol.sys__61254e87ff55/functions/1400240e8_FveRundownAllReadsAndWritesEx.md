# FveRundownAllReadsAndWritesEx

- ea: `0x1400240e8`
- end: `0x14002422d`
- name: `FveRundownAllReadsAndWritesEx`
- size: `325`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14002f334`
- `0x1400c9c6c`

## callees

- `0x1400240e8`
- `0x1400c24d8`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x140024213`
- `ntoskrnl!KeLowerIrql` at `0x140024213`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002411e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002411e`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14002416f`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1400241a0`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14002416f`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1400241a0`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14002418b`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14002418b`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400241d5`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400241f8`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400241d5`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400241f8`
- `ntoskrnl!KfRaiseIrql` at `0x1400241b4`
- `ntoskrnl!KfRaiseIrql` at `0x1400241b4`

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
0x1400240e8  push    rbx
0x1400240ea  push    rbp
0x1400240eb  push    rsi
0x1400240ec  push    rdi
0x1400240ed  push    r14
0x1400240ef  push    r15
0x1400240f1  sub     rsp, 28h
0x1400240f5  mov     ebp, r8d
0x1400240f8  mov     esi, edx
0x1400240fa  mov     rbx, rcx
0x1400240fd  mov     eax, 1
0x140024102  lock xadd [rcx+5C0h], eax
0x14002410a  inc     eax
0x14002410c  cmp     eax, 1
0x14002410f  jnz     loc_14002421F
0x140024115  mov     r14, gs:188h
0x14002411e  call    cs:__imp_KeGetCurrentIrql
0x140024125  nop     dword ptr [rax+rax+00h]
0x14002412a  test    dword ptr [rbx+328h], 100h
0x140024134  mov     r15d, 0Ch
0x14002413a  mov     dil, al
0x14002413d  jz      short loc_140024168
0x14002413f  mov     rax, [rbx+2E0h]
0x140024146  test    rax, rax
0x140024149  jz      short loc_140024168
0x14002414b  cmp     qword ptr [rax], 0
0x14002414f  jz      short loc_140024168
0x140024151  cmp     esi, r15d
0x140024154  mov     edx, esi
0x140024156  mov     r9b, 1
0x140024159  mov     r8d, ebp
0x14002415c  cmovle  edx, r15d
0x140024160  mov     rcx, rbx
0x140024163  call    FveEowBoostConversionPriority
0x140024168  mov     rcx, [rbx+5B8h]; RunRef
0x14002416f  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x140024176  nop     dword ptr [rax+rax+00h]
0x14002417b  cmp     byte ptr [rbx+5C4h], 0
0x140024182  jz      short loc_140024199
0x140024184  lea     rcx, [rbx+5A8h]; RunRef
0x14002418b  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140024192  nop     dword ptr [rax+rax+00h]
0x140024197  jmp     short loc_1400241AC
0x140024199  mov     rcx, [rbx+5B0h]; RunRef
0x1400241a0  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x1400241a7  nop     dword ptr [rax+rax+00h]
0x1400241ac  cmp     dil, 2
0x1400241b0  jnb     short loc_1400241C3
0x1400241b2  mov     cl, 2; NewIrql
0x1400241b4  call    cs:__imp_KfRaiseIrql
0x1400241bb  nop     dword ptr [rax+rax+00h]
0x1400241c0  mov     dil, al
0x1400241c3  cmp     esi, r15d
0x1400241c6  mov     rcx, r14
0x1400241c9  cmovle  esi, r15d
0x1400241cd  mov     edx, esi
0x1400241cf  mov     [rbx+5CCh], esi
0x1400241d5  call    cs:__imp_KeSetActualBasePriorityThread
0x1400241dc  nop     dword ptr [rax+rax+00h]
0x1400241e1  cmp     eax, [rbx+5CCh]
0x1400241e7  jge     short loc_1400241F1
0x1400241e9  mov     [rbx+5C8h], eax
0x1400241ef  jmp     short loc_140024204
0x1400241f1  jle     short loc_140024204
0x1400241f3  mov     edx, eax
0x1400241f5  mov     rcx, r14
0x1400241f8  call    cs:__imp_KeSetActualBasePriorityThread
0x1400241ff  nop     dword ptr [rax+rax+00h]
0x140024204  mov     [rbx+5D0h], ebp
0x14002420a  cmp     dil, 2
0x14002420e  jnb     short loc_14002421F
0x140024210  mov     cl, dil; NewIrql
0x140024213  call    cs:__imp_KeLowerIrql
0x14002421a  nop     dword ptr [rax+rax+00h]
0x14002421f  add     rsp, 28h
0x140024223  pop     r15
0x140024225  pop     r14
0x140024227  pop     rdi
0x140024228  pop     rsi
0x140024229  pop     rbp
0x14002422a  pop     rbx
0x14002422b  retn
```
