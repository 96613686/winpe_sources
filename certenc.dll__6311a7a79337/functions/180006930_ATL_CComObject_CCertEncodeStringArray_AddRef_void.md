# ATL::CComObject<CCertEncodeStringArray>::AddRef(void)

- ea: `0x180006930`
- end: `0x180006959`
- name: `?AddRef@?$CComObject@VCCertEncodeStringArray@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006960`

## callees

- `0x180006930`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCertEncodeStringArray>::AddRef(__int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 16);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 16), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x180006930  mov     r9d, 7FFFFFFFh
0x180006936  jmp     short loc_180006946
0x180006938  lea     edx, [r8+1]
0x18000693c  mov     eax, r8d
0x18000693f  lock cmpxchg [rcx+10h], edx
0x180006944  jz      short loc_180006951
0x180006946  mov     r8d, [rcx+10h]
0x18000694a  cmp     r8d, r9d
0x18000694d  jnz     short loc_180006938
0x18000694f  jmp     short loc_180006955
0x180006951  lea     r9d, [r8+1]
0x180006955  mov     eax, r9d
0x180006958  retn
```
