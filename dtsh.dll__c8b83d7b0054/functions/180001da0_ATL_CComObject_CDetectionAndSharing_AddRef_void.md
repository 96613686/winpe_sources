# ATL::CComObject<CDetectionAndSharing>::AddRef(void)

- ea: `0x180001da0`
- end: `0x180001dc9`
- name: `?AddRef@?$CComObject@VCDetectionAndSharing@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001da0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDetectionAndSharing>::AddRef(__int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 8);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x180001da0  mov     r9d, 7FFFFFFFh
0x180001da6  jmp     short loc_180001DB6
0x180001da8  lea     edx, [r8+1]
0x180001dac  mov     eax, r8d
0x180001daf  lock cmpxchg [rcx+8], edx
0x180001db4  jz      short loc_180001DC1
0x180001db6  mov     r8d, [rcx+8]
0x180001dba  cmp     r8d, r9d
0x180001dbd  jnz     short loc_180001DA8
0x180001dbf  jmp     short loc_180001DC5
0x180001dc1  lea     r9d, [r8+1]
0x180001dc5  mov     eax, r9d
0x180001dc8  retn
```
