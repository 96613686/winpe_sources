# CsrDereferenceProcess

- ea: `0x180003bb0`
- end: `0x180003c16`
- name: `CsrDereferenceProcess`
- size: `102`
- prototype: `NTSTATUS __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006a80`
- `0x1800097f0`

## callees

- `0x180003bb0`
- `0x180003c20`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180003bd9`
- `ntdll!RtlEnterCriticalSection` at `0x180003bd9`
- `ntdll!RtlLeaveCriticalSection` at `0x180003c08`
- `ntdll!RtlLeaveCriticalSection` at `0x180003c08`

## pseudocode

```c
NTSTATUS __fastcall CsrDereferenceProcess(__int64 a1)
{
  signed __int32 v1; // eax
  NTSTATUS result; // eax
  int v4; // ett

  v1 = *(_DWORD *)(a1 + 100);
  if ( v1 <= 1
    || (v4 = *(_DWORD *)(a1 + 100),
        result = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 100), v1 - 1, v1),
        v4 != result) )
  {
    RtlEnterCriticalSection(&CsrProcessStructureLock);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 100), 0xFFFFFFFF) == 1 )
      return CsrProcessRefcountZero(a1);
    else
      return RtlLeaveCriticalSection(&CsrProcessStructureLock);
  }
  return result;
}

```

## disassembly

```asm
0x180003bb0  push    rbx
0x180003bb2  sub     rsp, 20h
0x180003bb6  mov     eax, [rcx+64h]
0x180003bb9  mov     rbx, rcx
0x180003bbc  cmp     eax, 1
0x180003bbf  jle     short loc_180003BD2
0x180003bc1  lea     ecx, [rax-1]
0x180003bc4  lock cmpxchg [rbx+64h], ecx
0x180003bc9  jnz     short loc_180003BD2
0x180003bcb  add     rsp, 20h
0x180003bcf  pop     rbx
0x180003bd0  retn
0x180003bd2  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180003bd9  call    cs:__imp_RtlEnterCriticalSection
0x180003be0  nop     dword ptr [rax+rax+00h]
0x180003be5  mov     eax, 0FFFFFFFFh
0x180003bea  lock xadd [rbx+64h], eax
0x180003bef  cmp     eax, 1
0x180003bf2  jnz     short loc_180003C01
0x180003bf4  mov     rcx, rbx
0x180003bf7  add     rsp, 20h
0x180003bfb  pop     rbx
0x180003bfc  jmp     CsrProcessRefcountZero
0x180003c01  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180003c08  call    cs:__imp_RtlLeaveCriticalSection
0x180003c0f  nop     dword ptr [rax+rax+00h]
0x180003c14  jmp     short loc_180003BCB
```
