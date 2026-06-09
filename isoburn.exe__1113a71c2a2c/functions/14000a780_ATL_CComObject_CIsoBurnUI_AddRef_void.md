# ATL::CComObject<CIsoBurnUI>::AddRef(void)

- ea: `0x14000a780`
- end: `0x14000a7a9`
- name: `?AddRef@?$CComObject@VCIsoBurnUI@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000a780`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIsoBurnUI>::AddRef(__int64 a1)
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
0x14000a780  mov     r9d, 7FFFFFFFh
0x14000a786  jmp     short loc_14000A796
0x14000a788  lea     edx, [r8+1]
0x14000a78c  mov     eax, r8d
0x14000a78f  lock cmpxchg [rcx+8], edx
0x14000a794  jz      short loc_14000A7A1
0x14000a796  mov     r8d, [rcx+8]
0x14000a79a  cmp     r8d, r9d
0x14000a79d  jnz     short loc_14000A788
0x14000a79f  jmp     short loc_14000A7A5
0x14000a7a1  lea     r9d, [r8+1]
0x14000a7a5  mov     eax, r9d
0x14000a7a8  retn
```
