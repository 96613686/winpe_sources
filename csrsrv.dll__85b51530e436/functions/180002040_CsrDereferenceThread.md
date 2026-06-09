# CsrDereferenceThread

- ea: `0x180002040`
- end: `0x1800020b1`
- name: `CsrDereferenceThread`
- size: `113`
- prototype: `__int64 __fastcall(volatile signed __int32 *BaseAddress)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001200`
- `0x1800097f0`

## callees

- `0x180002040`
- `0x1800036c0`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180002070`
- `ntdll!RtlEnterCriticalSection` at `0x180002070`
- `ntdll!RtlLeaveCriticalSection` at `0x1800020a3`
- `ntdll!RtlLeaveCriticalSection` at `0x1800020a3`

## pseudocode

```c
__int64 __fastcall CsrDereferenceThread(volatile signed __int32 *BaseAddress)
{
  signed __int32 v1; // eax
  unsigned __int32 v4; // edi

  v1 = *((_DWORD *)BaseAddress + 19);
  if ( v1 > 1 && v1 == _InterlockedCompareExchange(BaseAddress + 19, v1 - 1, v1) )
    return (unsigned int)(v1 - 1);
  RtlEnterCriticalSection(&CsrProcessStructureLock);
  v4 = _InterlockedDecrement(BaseAddress + 19);
  if ( v4 )
    RtlLeaveCriticalSection(&CsrProcessStructureLock);
  else
    CsrThreadRefcountZero((PVOID)BaseAddress);
  return v4;
}

```

## disassembly

```asm
0x180002040  push    rbx
0x180002042  sub     rsp, 20h
0x180002046  mov     eax, [rcx+4Ch]
0x180002049  mov     rbx, rcx
0x18000204c  cmp     eax, 1
0x18000204f  jle     short loc_180002064
0x180002051  lea     ecx, [rax-1]
0x180002054  lock cmpxchg [rbx+4Ch], ecx
0x180002059  jnz     short loc_180002064
0x18000205b  mov     eax, ecx
0x18000205d  add     rsp, 20h
0x180002061  pop     rbx
0x180002062  retn
0x180002064  lea     rcx, CsrProcessStructureLock; CriticalSection
0x18000206b  mov     [rsp+28h+arg_0], rdi
0x180002070  call    cs:__imp_RtlEnterCriticalSection
0x180002077  nop     dword ptr [rax+rax+00h]
0x18000207c  mov     edi, 0FFFFFFFFh
0x180002081  lock xadd [rbx+4Ch], edi
0x180002086  sub     edi, 1
0x180002089  jnz     short loc_18000209C
0x18000208b  mov     rcx, rbx; BaseAddress
0x18000208e  call    CsrThreadRefcountZero
0x180002093  mov     eax, edi
0x180002095  mov     rdi, [rsp+28h+arg_0]
0x18000209a  jmp     short loc_18000205D
0x18000209c  lea     rcx, CsrProcessStructureLock; CriticalSection
0x1800020a3  call    cs:__imp_RtlLeaveCriticalSection
0x1800020aa  nop     dword ptr [rax+rax+00h]
0x1800020af  jmp     short loc_180002093
```
