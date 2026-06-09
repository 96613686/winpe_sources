# ATL::CComAggObject<CAdvancedConfig>::AddRef(void)

- ea: `0x180003550`
- end: `0x180003579`
- name: `?AddRef@?$CComAggObject@VCAdvancedConfig@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003550`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CAdvancedConfig>::AddRef(__int64 a1)
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
0x180003550  mov     r9d, 7FFFFFFFh
0x180003556  jmp     short loc_180003566
0x180003558  lea     edx, [r8+1]
0x18000355c  mov     eax, r8d
0x18000355f  lock cmpxchg [rcx+8], edx
0x180003564  jz      short loc_180003571
0x180003566  mov     r8d, [rcx+8]
0x18000356a  cmp     r8d, r9d
0x18000356d  jnz     short loc_180003558
0x18000356f  jmp     short loc_180003575
0x180003571  lea     r9d, [r8+1]
0x180003575  mov     eax, r9d
0x180003578  retn
```
