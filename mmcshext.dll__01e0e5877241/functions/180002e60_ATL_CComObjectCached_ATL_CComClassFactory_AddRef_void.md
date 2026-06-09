# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180002e60`
- end: `0x180002e96`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002e60`

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
        _InterlockedIncrement(&dword_180012EE8);
      return v1;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180002e60  mov     r8d, 7FFFFFFFh
0x180002e66  jmp     short loc_180002E76
0x180002e68  lea     edx, [r9+1]
0x180002e6c  mov     eax, r9d
0x180002e6f  lock cmpxchg [rcx+8], edx
0x180002e74  jz      short loc_180002E81
0x180002e76  mov     r9d, [rcx+8]
0x180002e7a  cmp     r9d, r8d
0x180002e7d  jnz     short loc_180002E68
0x180002e7f  jmp     short loc_180002E92
0x180002e81  lea     r8d, [r9+1]
0x180002e85  cmp     r8d, 2
0x180002e89  jnz     short loc_180002E92
0x180002e8b  lock inc cs:dword_180012EE8
0x180002e92  mov     eax, r8d
0x180002e95  retn
```
