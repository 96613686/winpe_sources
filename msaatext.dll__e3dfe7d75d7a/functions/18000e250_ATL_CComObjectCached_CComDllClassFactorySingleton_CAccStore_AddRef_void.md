# ATL::CComObjectCached<CComDllClassFactorySingleton<CAccStore>>::AddRef(void)

- ea: `0x18000e250`
- end: `0x18000e286`
- name: `?AddRef@?$CComObjectCached@V?$CComDllClassFactorySingleton@VCAccStore@@@@@ATL@@UEAAKXZ`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e250`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<CComDllClassFactorySingleton<CAccStore>>::AddRef(__int64 a1)
{
  unsigned int v1; // r8d
  signed __int32 v2; // r9d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 8);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8), v2 + 1, v2) )
    {
      v1 = v2 + 1;
      if ( v2 == 1 )
        _InterlockedIncrement(&dword_180024B28);
      return v1;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18000e250  mov     r8d, 7FFFFFFFh
0x18000e256  jmp     short loc_18000E266
0x18000e258  lea     edx, [r9+1]
0x18000e25c  mov     eax, r9d
0x18000e25f  lock cmpxchg [rcx+8], edx
0x18000e264  jz      short loc_18000E271
0x18000e266  mov     r9d, [rcx+8]
0x18000e26a  cmp     r9d, r8d
0x18000e26d  jnz     short loc_18000E258
0x18000e26f  jmp     short loc_18000E282
0x18000e271  lea     r8d, [r9+1]
0x18000e275  cmp     r8d, 2
0x18000e279  jnz     short loc_18000E282
0x18000e27b  lock inc cs:dword_180024B28
0x18000e282  mov     eax, r8d
0x18000e285  retn
```
