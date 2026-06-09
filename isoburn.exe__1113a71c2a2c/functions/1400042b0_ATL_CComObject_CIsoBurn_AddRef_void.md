# ATL::CComObject<CIsoBurn>::AddRef(void)

- ea: `0x1400042b0`
- end: `0x1400042d9`
- name: `?AddRef@?$CComObject@VCIsoBurn@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400042e0`
- `0x1400042f0`

## callees

- `0x1400042b0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIsoBurn>::AddRef(__int64 a1)
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
0x1400042b0  mov     r9d, 7FFFFFFFh
0x1400042b6  jmp     short loc_1400042C6
0x1400042b8  lea     edx, [r8+1]
0x1400042bc  mov     eax, r8d
0x1400042bf  lock cmpxchg [rcx+40h], edx
0x1400042c4  jz      short loc_1400042D1
0x1400042c6  mov     r8d, [rcx+40h]
0x1400042ca  cmp     r8d, r9d
0x1400042cd  jnz     short loc_1400042B8
0x1400042cf  jmp     short loc_1400042D5
0x1400042d1  lea     r9d, [r8+1]
0x1400042d5  mov     eax, r9d
0x1400042d8  retn
```
