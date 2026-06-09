# ATL::CComObject<CPnpxPairingHandler>::AddRef(void)

- ea: `0x1800059a0`
- end: `0x1800059c9`
- name: `?AddRef@?$CComObject@VCPnpxPairingHandler@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800059d0`
- `0x1800059e0`

## callees

- `0x1800059a0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CPnpxPairingHandler>::AddRef(__int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 24);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 24), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x1800059a0  mov     r9d, 7FFFFFFFh
0x1800059a6  jmp     short loc_1800059B6
0x1800059a8  lea     edx, [r8+1]
0x1800059ac  mov     eax, r8d
0x1800059af  lock cmpxchg [rcx+18h], edx
0x1800059b4  jz      short loc_1800059C1
0x1800059b6  mov     r8d, [rcx+18h]
0x1800059ba  cmp     r8d, r9d
0x1800059bd  jnz     short loc_1800059A8
0x1800059bf  jmp     short loc_1800059C5
0x1800059c1  lea     r9d, [r8+1]
0x1800059c5  mov     eax, r9d
0x1800059c8  retn
```
