# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180009790`
- end: `0x1800097c6`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009790`

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
        _InterlockedIncrement(&dword_180017A78);
      return v1;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180009790  mov     r8d, 7FFFFFFFh
0x180009796  jmp     short loc_1800097A6
0x180009798  lea     edx, [r9+1]
0x18000979c  mov     eax, r9d
0x18000979f  lock cmpxchg [rcx+8], edx
0x1800097a4  jz      short loc_1800097B1
0x1800097a6  mov     r9d, [rcx+8]
0x1800097aa  cmp     r9d, r8d
0x1800097ad  jnz     short loc_180009798
0x1800097af  jmp     short loc_1800097C2
0x1800097b1  lea     r8d, [r9+1]
0x1800097b5  cmp     r8d, 2
0x1800097b9  jnz     short loc_1800097C2
0x1800097bb  lock inc cs:dword_180017A78
0x1800097c2  mov     eax, r8d
0x1800097c5  retn
```
