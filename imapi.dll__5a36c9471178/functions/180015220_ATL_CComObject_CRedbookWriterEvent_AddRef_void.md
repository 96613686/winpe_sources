# ATL::CComObject<CRedbookWriterEvent>::AddRef(void)

- ea: `0x180015220`
- end: `0x180015249`
- name: `?AddRef@?$CComObject@VCRedbookWriterEvent@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180015250`

## callees

- `0x180015220`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CRedbookWriterEvent>::AddRef(__int64 a1)
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
0x180015220  mov     r9d, 7FFFFFFFh
0x180015226  jmp     short loc_180015236
0x180015228  lea     edx, [r8+1]
0x18001522c  mov     eax, r8d
0x18001522f  lock cmpxchg [rcx+38h], edx
0x180015234  jz      short loc_180015241
0x180015236  mov     r8d, [rcx+38h]
0x18001523a  cmp     r8d, r9d
0x18001523d  jnz     short loc_180015228
0x18001523f  jmp     short loc_180015245
0x180015241  lea     r9d, [r8+1]
0x180015245  mov     eax, r9d
0x180015248  retn
```
