# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180006970`
- end: `0x1800069a6`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006970`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(__int64 a1)
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
        _InterlockedIncrement(&dword_18000F8D8);
      return v1;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180006970  mov     r8d, 7FFFFFFFh
0x180006976  jmp     short loc_180006986
0x180006978  lea     edx, [r9+1]
0x18000697c  mov     eax, r9d
0x18000697f  lock cmpxchg [rcx+8], edx
0x180006984  jz      short loc_180006991
0x180006986  mov     r9d, [rcx+8]
0x18000698a  cmp     r9d, r8d
0x18000698d  jnz     short loc_180006978
0x18000698f  jmp     short loc_1800069A2
0x180006991  lea     r8d, [r9+1]
0x180006995  cmp     r8d, 2
0x180006999  jnz     short loc_1800069A2
0x18000699b  lock inc cs:dword_18000F8D8
0x1800069a2  mov     eax, r8d
0x1800069a5  retn
```
