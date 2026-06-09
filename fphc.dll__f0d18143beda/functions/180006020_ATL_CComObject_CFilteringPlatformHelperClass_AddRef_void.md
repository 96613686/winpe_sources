# ATL::CComObject<CFilteringPlatformHelperClass>::AddRef(void)

- ea: `0x180006020`
- end: `0x180006049`
- name: `?AddRef@?$CComObject@VCFilteringPlatformHelperClass@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006050`
- `0x180006060`

## callees

- `0x180006020`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CFilteringPlatformHelperClass>::AddRef(__int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 64);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 64), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x180006020  mov     r9d, 7FFFFFFFh
0x180006026  jmp     short loc_180006036
0x180006028  lea     edx, [r8+1]
0x18000602c  mov     eax, r8d
0x18000602f  lock cmpxchg [rcx+40h], edx
0x180006034  jz      short loc_180006041
0x180006036  mov     r8d, [rcx+40h]
0x18000603a  cmp     r8d, r9d
0x18000603d  jnz     short loc_180006028
0x18000603f  jmp     short loc_180006045
0x180006041  lea     r9d, [r8+1]
0x180006045  mov     eax, r9d
0x180006048  retn
```
