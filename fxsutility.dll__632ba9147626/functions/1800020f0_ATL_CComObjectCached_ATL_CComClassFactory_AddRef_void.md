# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x1800020f0`
- end: `0x180002126`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800020f0`

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
        _InterlockedIncrement(&dword_18001EB58);
      return v1;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800020f0  mov     r8d, 7FFFFFFFh
0x1800020f6  jmp     short loc_180002106
0x1800020f8  lea     edx, [r9+1]
0x1800020fc  mov     eax, r9d
0x1800020ff  lock cmpxchg [rcx+8], edx
0x180002104  jz      short loc_180002111
0x180002106  mov     r9d, [rcx+8]
0x18000210a  cmp     r9d, r8d
0x18000210d  jnz     short loc_1800020F8
0x18000210f  jmp     short loc_180002122
0x180002111  lea     r8d, [r9+1]
0x180002115  cmp     r8d, 2
0x180002119  jnz     short loc_180002122
0x18000211b  lock inc cs:dword_18001EB58
0x180002122  mov     eax, r8d
0x180002125  retn
```
