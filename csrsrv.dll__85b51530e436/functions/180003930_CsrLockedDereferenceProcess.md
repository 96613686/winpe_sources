# CsrLockedDereferenceProcess

- ea: `0x180003930`
- end: `0x180003965`
- name: `CsrLockedDereferenceProcess`
- size: `53`
- prototype: `NTSTATUS __fastcall(__int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002a00`
- `0x180002c90`
- `0x1800030a0`
- `0x18000a070`

## callees

- `0x180003930`
- `0x180003c20`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180003953`

## pseudocode

```c
NTSTATUS __fastcall CsrLockedDereferenceProcess(__int64 a1)
{
  NTSTATUS result; // eax

  result = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 100), 0xFFFFFFFF);
  if ( result == 1 )
  {
    CsrProcessRefcountZero(a1);
    return RtlEnterCriticalSection(&CsrProcessStructureLock);
  }
  return result;
}

```

## disassembly

```asm
0x180003930  sub     rsp, 28h
0x180003934  mov     eax, 0FFFFFFFFh
0x180003939  lock xadd [rcx+64h], eax
0x18000393e  cmp     eax, 1
0x180003941  jnz     short loc_18000395F
0x180003943  call    CsrProcessRefcountZero
0x180003948  lea     rcx, CsrProcessStructureLock
0x18000394f  add     rsp, 28h
0x180003953  jmp     cs:__imp_RtlEnterCriticalSection
0x18000395f  add     rsp, 28h
0x180003963  retn
```
