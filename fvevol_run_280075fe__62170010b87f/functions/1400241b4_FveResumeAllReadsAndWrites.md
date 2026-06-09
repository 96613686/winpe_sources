# FveResumeAllReadsAndWrites

- ea: `0x1400241b4`
- end: `0x1400242b8`
- name: `FveResumeAllReadsAndWrites`
- size: `260`
- prototype: ``
- caller_count: `33`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140026db8`
- `0x140029e98`
- `0x14002f430`
- `0x140070690`
- `0x14009c380`
- `0x14009c540`
- `0x14009ec2c`
- `0x1400a0dec`
- `0x1400a1554`
- `0x1400a1810`
- `0x1400a1a28`
- `0x1400a1b6c`
- `0x1400a1ed4`
- `0x1400a2008`
- `0x1400a26e0`
- `0x1400a4308`
- `0x1400a4d08`
- `0x1400a4e6c`
- `0x1400a54ec`
- `0x1400a5efc`
- `0x1400b7740`
- `0x1400b8c90`
- `0x1400bed8c`
- `0x1400c0380`
- `0x1400c433c`
- `0x1400c61d4`
- `0x1400c6748`
- `0x1400c9248`
- `0x1400d9aa8`
- `0x1400d9cc8`
- `0x1400da750`
- `0x1400e6418`
- `0x1400e6cd4`

## callees

- `0x1400241b4`
- `0x1400290d8`
- `0x14002cb80`
- `0x1400bea68`
- `0x1400df3e8`

## import_xrefs

- `ntoskrnl!ExReInitializeRundownProtection` at `0x14002421e`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x14002421e`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x140024233`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x140024246`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x140024233`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x140024246`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400241e4`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400241e4`

## pseudocode

```c
__int64 __fastcall FveResumeAllReadsAndWrites(__int64 a1)
{
  __int64 result; // rax
  __int64 v3; // rdx
  bool v4; // zf

  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 1472), 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
  {
    v3 = *(unsigned int *)(a1 + 1480);
    if ( (_DWORD)v3 )
    {
      KeSetActualBasePriorityThread(KeGetCurrentThread(), v3);
      *(_DWORD *)(a1 + 1480) = 0;
    }
    v4 = *(_BYTE *)(a1 + 1476) == 0;
    *(_DWORD *)(a1 + 1484) = 0;
    *(_DWORD *)(a1 + 1488) = 5;
    if ( v4 )
      ExReInitializeRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1456));
    else
      ExReInitializeRundownProtection((PEX_RUNDOWN_REF)(a1 + 1448));
    ExReInitializeRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1464));
    FveCheckSyncInfoHeaders(a1);
    result = FveDequeueAndDispatchToSelf(*(_QWORD *)a1, a1 + 2240, a1 + 2256);
    if ( (*(_DWORD *)(a1 + 808) & 0x100) != 0 )
    {
      result = *(_QWORD *)(a1 + 736);
      if ( result )
      {
        if ( *(_QWORD *)result )
        {
          FveEowBoostConversionPriority(a1, 0, 5, 0);
          return FveQueueAutoWorkItem(a1, FveEowTryResumeFinalSweep, a1);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400241b4  push    rbx
0x1400241b6  sub     rsp, 20h
0x1400241ba  mov     rbx, rcx
0x1400241bd  or      eax, 0FFFFFFFFh
0x1400241c0  lock xadd [rcx+5C0h], eax
0x1400241c8  cmp     eax, 1
0x1400241cb  jnz     loc_1400242B1
0x1400241d1  mov     edx, [rcx+5C8h]
0x1400241d7  test    edx, edx
0x1400241d9  jz      short loc_1400241FA
0x1400241db  mov     rcx, gs:188h
0x1400241e4  call    cs:__imp_KeSetActualBasePriorityThread
0x1400241eb  nop     dword ptr [rax+rax+00h]
0x1400241f0  mov     dword ptr [rbx+5C8h], 0
0x1400241fa  cmp     byte ptr [rbx+5C4h], 0
0x140024201  mov     dword ptr [rbx+5CCh], 0
0x14002420b  mov     dword ptr [rbx+5D0h], 5
0x140024215  jz      short loc_14002422C
0x140024217  lea     rcx, [rbx+5A8h]; RunRef
0x14002421e  call    cs:__imp_ExReInitializeRundownProtection
0x140024225  nop     dword ptr [rax+rax+00h]
0x14002422a  jmp     short loc_14002423F
0x14002422c  mov     rcx, [rbx+5B0h]; RunRefCacheAware
0x140024233  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x14002423a  nop     dword ptr [rax+rax+00h]
0x14002423f  mov     rcx, [rbx+5B8h]; RunRefCacheAware
0x140024246  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x14002424d  nop     dword ptr [rax+rax+00h]
0x140024252  mov     rcx, rbx
0x140024255  call    FveCheckSyncInfoHeaders
0x14002425a  mov     rcx, [rbx]
0x14002425d  lea     r8, [rbx+8D0h]
0x140024264  lea     rdx, [rbx+8C0h]
0x14002426b  call    FveDequeueAndDispatchToSelf
0x140024270  test    dword ptr [rbx+328h], 100h
0x14002427a  jz      short loc_1400242B1
0x14002427c  mov     rax, [rbx+2E0h]
0x140024283  test    rax, rax
0x140024286  jz      short loc_1400242B1
0x140024288  cmp     qword ptr [rax], 0
0x14002428c  jz      short loc_1400242B1
0x14002428e  xor     r9d, r9d
0x140024291  xor     edx, edx
0x140024293  mov     rcx, rbx
0x140024296  lea     r8d, [r9+5]
0x14002429a  call    FveEowBoostConversionPriority
0x14002429f  mov     r8, rbx
0x1400242a2  lea     rdx, FveEowTryResumeFinalSweep
0x1400242a9  mov     rcx, rbx
0x1400242ac  call    FveQueueAutoWorkItem
0x1400242b1  add     rsp, 20h
0x1400242b5  pop     rbx
0x1400242b6  retn
```
