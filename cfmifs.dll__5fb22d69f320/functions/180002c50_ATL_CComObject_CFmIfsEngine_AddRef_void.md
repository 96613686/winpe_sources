# ATL::CComObject<CFmIfsEngine>::AddRef(void)

- ea: `0x180002c50`
- end: `0x180002c79`
- name: `?AddRef@?$CComObject@VCFmIfsEngine@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002c50`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CFmIfsEngine>::AddRef(__int64 a1)
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
0x180002c50  mov     r9d, 7FFFFFFFh
0x180002c56  jmp     short loc_180002C66
0x180002c58  lea     edx, [r8+1]
0x180002c5c  mov     eax, r8d
0x180002c5f  lock cmpxchg [rcx+8], edx
0x180002c64  jz      short loc_180002C71
0x180002c66  mov     r8d, [rcx+8]
0x180002c6a  cmp     r8d, r9d
0x180002c6d  jnz     short loc_180002C58
0x180002c6f  jmp     short loc_180002C75
0x180002c71  lea     r9d, [r8+1]
0x180002c75  mov     eax, r9d
0x180002c78  retn
```
