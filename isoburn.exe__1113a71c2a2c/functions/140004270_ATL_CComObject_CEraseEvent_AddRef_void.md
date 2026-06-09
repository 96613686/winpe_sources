# ATL::CComObject<CEraseEvent>::AddRef(void)

- ea: `0x140004270`
- end: `0x140004299`
- name: `?AddRef@?$CComObject@VCEraseEvent@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400042a0`

## callees

- `0x140004270`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEraseEvent>::AddRef(__int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 56);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 56), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x140004270  mov     r9d, 7FFFFFFFh
0x140004276  jmp     short loc_140004286
0x140004278  lea     edx, [r8+1]
0x14000427c  mov     eax, r8d
0x14000427f  lock cmpxchg [rcx+38h], edx
0x140004284  jz      short loc_140004291
0x140004286  mov     r8d, [rcx+38h]
0x14000428a  cmp     r8d, r9d
0x14000428d  jnz     short loc_140004278
0x14000428f  jmp     short loc_140004295
0x140004291  lea     r9d, [r8+1]
0x140004295  mov     eax, r9d
0x140004298  retn
```
