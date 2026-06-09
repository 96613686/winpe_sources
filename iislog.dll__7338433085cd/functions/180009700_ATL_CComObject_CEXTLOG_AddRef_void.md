# ATL::CComObject<CEXTLOG>::AddRef(void)

- ea: `0x180009700`
- end: `0x180009729`
- name: `?AddRef@?$CComObject@VCEXTLOG@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009770`

## callees

- `0x180009700`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEXTLOG>::AddRef(__int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 8);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x180009700  mov     r9d, 7FFFFFFFh
0x180009706  jmp     short loc_180009716
0x180009708  lea     edx, [r8+1]
0x18000970c  mov     eax, r8d
0x18000970f  lock cmpxchg [rcx+8], edx
0x180009714  jz      short loc_180009721
0x180009716  mov     r8d, [rcx+8]
0x18000971a  cmp     r8d, r9d
0x18000971d  jnz     short loc_180009708
0x18000971f  jmp     short loc_180009725
0x180009721  lea     r9d, [r8+1]
0x180009725  mov     eax, r9d
0x180009728  retn
```
