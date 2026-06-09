# PcpDereferenceFlow

- ea: `0x140009100`
- end: `0x140009131`
- name: `PcpDereferenceFlow`
- size: `49`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `17`
- callee_count: `3`
- tags: ``

## callers

- `0x140002e80`
- `0x140005c10`
- `0x140007f90`
- `0x140008440`
- `0x1400085c0`
- `0x140009050`
- `0x14000a830`
- `0x14000cce0`
- `0x14000d284`
- `0x14000ff70`
- `0x140010340`
- `0x140010b68`
- `0x14001d47c`
- `0x14001d5bc`
- `0x14001f2a0`
- `0x140020d30`
- `0x140020ec4`

## callees

- `0x140005578`
- `0x140009100`
- `0x14000aca4`

## pseudocode

```c
__int64 __fastcall PcpDereferenceFlow(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 32), 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
  {
    if ( (*(_DWORD *)(a1 + 616) & 8) != 0 )
      return PcpCleanupFlow((PVOID)a1);
    else
      return PcpDeleteFlow((char *)a1, a2);
  }
  return result;
}

```

## disassembly

```asm
0x140009100  sub     rsp, 28h
0x140009104  mov     eax, 0FFFFFFFFh
0x140009109  lock xadd [rcx+20h], eax
0x14000910e  cmp     eax, 1
0x140009111  jz      short loc_140009119
0x140009113  add     rsp, 28h
0x140009117  retn
0x140009119  mov     eax, [rcx+268h]
0x14000911f  test    al, 8
0x140009121  jz      short loc_14000912A
0x140009123  call    PcpCleanupFlow
0x140009128  jmp     short loc_140009113
0x14000912a  call    PcpDeleteFlow
0x14000912f  jmp     short loc_140009113
```
