# ATL::CComObject<CMSDiscMasterObj>::AddRef(void)

- ea: `0x180008110`
- end: `0x18000813f`
- name: `?AddRef@?$CComObject@VCMSDiscMasterObj@@@ATL@@UEAAKXZ`
- size: `47`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008150`
- `0x180008160`
- `0x180008170`
- `0x180008180`
- `0x180008190`

## callees

- `0x180008110`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMSDiscMasterObj>::AddRef(__int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 128);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 128), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x180008110  mov     r9d, 7FFFFFFFh
0x180008116  jmp     short loc_180008129
0x180008118  lea     edx, [r8+1]
0x18000811c  mov     eax, r8d
0x18000811f  lock cmpxchg [rcx+80h], edx
0x180008127  jz      short loc_180008137
0x180008129  mov     r8d, [rcx+80h]
0x180008130  cmp     r8d, r9d
0x180008133  jnz     short loc_180008118
0x180008135  jmp     short loc_18000813B
0x180008137  lea     r9d, [r8+1]
0x18000813b  mov     eax, r9d
0x18000813e  retn
```
