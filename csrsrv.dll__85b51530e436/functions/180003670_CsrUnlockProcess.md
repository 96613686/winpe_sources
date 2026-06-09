# CsrUnlockProcess

- ea: `0x180003670`
- end: `0x1800036b6`
- name: `CsrUnlockProcess`
- size: `70`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800097f0`
- `0x18000a070`

## callees

- `0x180003670`
- `0x180003c20`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x18000368f`
- `ntdll!RtlEnterCriticalSection` at `0x18000368f`
- `ntdll!RtlLeaveCriticalSection` at `0x1800036a2`
- `ntdll!RtlLeaveCriticalSection` at `0x1800036a2`

## pseudocode

```c
__int64 __fastcall CsrUnlockProcess(__int64 a1)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 100), 0xFFFFFFFF) == 1 )
  {
    CsrProcessRefcountZero();
    RtlEnterCriticalSection(&CsrProcessStructureLock);
  }
  RtlLeaveCriticalSection(&CsrProcessStructureLock);
  return 0;
}

```

## disassembly

```asm
0x180003670  sub     rsp, 28h
0x180003674  mov     eax, 0FFFFFFFFh
0x180003679  lock xadd [rcx+64h], eax
0x18000367e  cmp     eax, 1
0x180003681  jnz     short loc_18000369B
0x180003683  call    CsrProcessRefcountZero
0x180003688  lea     rcx, CsrProcessStructureLock; CriticalSection
0x18000368f  call    cs:__imp_RtlEnterCriticalSection
0x180003696  nop     dword ptr [rax+rax+00h]
0x18000369b  lea     rcx, CsrProcessStructureLock; CriticalSection
0x1800036a2  call    cs:__imp_RtlLeaveCriticalSection
0x1800036a9  nop     dword ptr [rax+rax+00h]
0x1800036ae  xor     eax, eax
0x1800036b0  add     rsp, 28h
0x1800036b4  retn
```
