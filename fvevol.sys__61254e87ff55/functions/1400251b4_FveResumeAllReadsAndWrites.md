# FveResumeAllReadsAndWrites

- ea: `0x1400251b4`
- end: `0x1400252b8`
- name: `FveResumeAllReadsAndWrites`
- size: `260`
- prototype: ``
- caller_count: `33`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140027db8`
- `0x14002ae98`
- `0x140030430`
- `0x140072670`
- `0x14009e380`
- `0x14009fb70`
- `0x1400a1d38`
- `0x1400a24a0`
- `0x1400a275c`
- `0x1400a2974`
- `0x1400a2ab8`
- `0x1400a2e20`
- `0x1400a2f54`
- `0x1400a3630`
- `0x1400a5258`
- `0x1400a5c60`
- `0x1400a5dc4`
- `0x1400a6444`
- `0x1400a6e54`
- `0x1400b8a3c`
- `0x1400b9fbc`
- `0x1400ba750`
- `0x1400c27fc`
- `0x1400c3df0`
- `0x1400c7dcc`
- `0x1400c9c6c`
- `0x1400ca1d8`
- `0x1400ccd18`
- `0x1400dc318`
- `0x1400dc538`
- `0x1400dcfc0`
- `0x1400e8cc8`
- `0x1400e9584`

## callees

- `0x1400251b4`
- `0x14002a0d8`
- `0x14002db80`
- `0x1400c24d8`
- `0x1400e1b08`

## import_xrefs

- `ntoskrnl!ExReInitializeRundownProtection` at `0x14002521e`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x14002521e`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x140025233`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x140025246`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x140025233`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x140025246`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400251e4`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400251e4`

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
    result = FveDequeueAndDispatchToSelf(*(_QWORD *)a1, a1 + 2256, a1 + 2272);
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
0x1400251b4  push    rbx
0x1400251b6  sub     rsp, 20h
0x1400251ba  mov     rbx, rcx
0x1400251bd  or      eax, 0FFFFFFFFh
0x1400251c0  lock xadd [rcx+5C0h], eax
0x1400251c8  cmp     eax, 1
0x1400251cb  jnz     loc_1400252B1
0x1400251d1  mov     edx, [rcx+5C8h]
0x1400251d7  test    edx, edx
0x1400251d9  jz      short loc_1400251FA
0x1400251db  mov     rcx, gs:188h
0x1400251e4  call    cs:__imp_KeSetActualBasePriorityThread
0x1400251eb  nop     dword ptr [rax+rax+00h]
0x1400251f0  mov     dword ptr [rbx+5C8h], 0
0x1400251fa  cmp     byte ptr [rbx+5C4h], 0
0x140025201  mov     dword ptr [rbx+5CCh], 0
0x14002520b  mov     dword ptr [rbx+5D0h], 5
0x140025215  jz      short loc_14002522C
0x140025217  lea     rcx, [rbx+5A8h]; RunRef
0x14002521e  call    cs:__imp_ExReInitializeRundownProtection
0x140025225  nop     dword ptr [rax+rax+00h]
0x14002522a  jmp     short loc_14002523F
0x14002522c  mov     rcx, [rbx+5B0h]; RunRefCacheAware
0x140025233  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x14002523a  nop     dword ptr [rax+rax+00h]
0x14002523f  mov     rcx, [rbx+5B8h]; RunRefCacheAware
0x140025246  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x14002524d  nop     dword ptr [rax+rax+00h]
0x140025252  mov     rcx, rbx
0x140025255  call    FveCheckSyncInfoHeaders
0x14002525a  mov     rcx, [rbx]
0x14002525d  lea     r8, [rbx+8E0h]
0x140025264  lea     rdx, [rbx+8D0h]
0x14002526b  call    FveDequeueAndDispatchToSelf
0x140025270  test    dword ptr [rbx+328h], 100h
0x14002527a  jz      short loc_1400252B1
0x14002527c  mov     rax, [rbx+2E0h]
0x140025283  test    rax, rax
0x140025286  jz      short loc_1400252B1
0x140025288  cmp     qword ptr [rax], 0
0x14002528c  jz      short loc_1400252B1
0x14002528e  xor     r9d, r9d
0x140025291  xor     edx, edx
0x140025293  mov     rcx, rbx
0x140025296  lea     r8d, [r9+5]
0x14002529a  call    FveEowBoostConversionPriority
0x14002529f  mov     r8, rbx
0x1400252a2  lea     rdx, FveEowTryResumeFinalSweep
0x1400252a9  mov     rcx, rbx
0x1400252ac  call    FveQueueAutoWorkItem
0x1400252b1  add     rsp, 20h
0x1400252b5  pop     rbx
0x1400252b6  retn
```
