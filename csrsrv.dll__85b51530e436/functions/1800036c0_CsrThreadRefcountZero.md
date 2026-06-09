# CsrThreadRefcountZero

- ea: `0x1800036c0`
- end: `0x180003778`
- name: `CsrThreadRefcountZero`
- size: `184`
- prototype: `NTSTATUS __fastcall(PVOID BaseAddress)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002040`

## callees

- `0x1800036c0`
- `0x180003780`
- `0x180003c20`

## import_xrefs

- `ntdll!NtClose` at `0x1800036ed`
- `ntdll!NtClose` at `0x1800036ed`
- `ntdll!RtlFreeHeap` at `0x180003705`
- `ntdll!RtlFreeHeap` at `0x180003705`
- `ntdll!RtlEnterCriticalSection` at `0x180003736`
- `ntdll!RtlEnterCriticalSection` at `0x180003736`
- `ntdll!RtlLeaveCriticalSection` at `0x1800036dd`
- `ntdll!RtlLeaveCriticalSection` at `0x18000376a`
- `ntdll!RtlLeaveCriticalSection` at `0x1800036dd`
- `ntdll!RtlLeaveCriticalSection` at `0x18000376a`

## pseudocode

```c
NTSTATUS __fastcall CsrThreadRefcountZero(PVOID BaseAddress)
{
  __int64 v1; // rbx
  signed __int32 v3; // eax
  NTSTATUS result; // eax
  int v5; // ett

  v1 = *((_QWORD *)BaseAddress + 7);
  CsrRemoveThread(BaseAddress);
  RtlLeaveCriticalSection(&CsrProcessStructureLock);
  NtClose(*((HANDLE *)BaseAddress + 8));
  RtlFreeHeap(CsrHeap, 0, BaseAddress);
  v3 = *(_DWORD *)(v1 + 100);
  if ( v3 <= 1
    || (v5 = *(_DWORD *)(v1 + 100),
        result = _InterlockedCompareExchange((volatile signed __int32 *)(v1 + 100), v3 - 1, v3),
        v5 != result) )
  {
    RtlEnterCriticalSection(&CsrProcessStructureLock);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 100), 0xFFFFFFFF) == 1 )
      return CsrProcessRefcountZero(v1);
    else
      return RtlLeaveCriticalSection(&CsrProcessStructureLock);
  }
  return result;
}

```

## disassembly

```asm
0x1800036c0  mov     [rsp+arg_8], rbx
0x1800036c5  push    rdi
0x1800036c6  sub     rsp, 20h
0x1800036ca  mov     rbx, [rcx+38h]
0x1800036ce  mov     rdi, rcx
0x1800036d1  call    CsrRemoveThread
0x1800036d6  lea     rcx, CsrProcessStructureLock; CriticalSection
0x1800036dd  call    cs:__imp_RtlLeaveCriticalSection
0x1800036e4  nop     dword ptr [rax+rax+00h]
0x1800036e9  mov     rcx, [rdi+40h]; Handle
0x1800036ed  call    cs:__imp_NtClose
0x1800036f4  nop     dword ptr [rax+rax+00h]
0x1800036f9  mov     rcx, cs:CsrHeap; HeapHandle
0x180003700  mov     r8, rdi; BaseAddress
0x180003703  xor     edx, edx; Flags
0x180003705  call    cs:__imp_RtlFreeHeap
0x18000370c  nop     dword ptr [rax+rax+00h]
0x180003711  mov     eax, [rbx+64h]
0x180003714  cmp     eax, 1
0x180003717  jle     short loc_18000372F
0x180003719  lea     ecx, [rax-1]
0x18000371c  lock cmpxchg [rbx+64h], ecx
0x180003721  jnz     short loc_18000372F
0x180003723  mov     rbx, [rsp+28h+arg_8]
0x180003728  add     rsp, 20h
0x18000372c  pop     rdi
0x18000372d  retn
0x18000372f  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180003736  call    cs:__imp_RtlEnterCriticalSection
0x18000373d  nop     dword ptr [rax+rax+00h]
0x180003742  mov     eax, 0FFFFFFFFh
0x180003747  lock xadd [rbx+64h], eax
0x18000374c  cmp     eax, 1
0x18000374f  jnz     short loc_180003763
0x180003751  mov     rcx, rbx
0x180003754  mov     rbx, [rsp+28h+arg_8]
0x180003759  add     rsp, 20h
0x18000375d  pop     rdi
0x18000375e  jmp     CsrProcessRefcountZero
0x180003763  lea     rcx, CsrProcessStructureLock; CriticalSection
0x18000376a  call    cs:__imp_RtlLeaveCriticalSection
0x180003771  nop     dword ptr [rax+rax+00h]
0x180003776  jmp     short loc_180003723
```
