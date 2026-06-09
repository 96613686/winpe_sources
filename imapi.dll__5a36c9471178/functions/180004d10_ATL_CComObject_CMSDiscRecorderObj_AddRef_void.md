# ATL::CComObject<CMSDiscRecorderObj>::AddRef(void)

- ea: `0x180004d10`
- end: `0x180004d39`
- name: `?AddRef@?$CComObject@VCMSDiscRecorderObj@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004d40`

## callees

- `0x180004d10`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMSDiscRecorderObj>::AddRef(__int64 a1)
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
0x180004d10  mov     r9d, 7FFFFFFFh
0x180004d16  jmp     short loc_180004D26
0x180004d18  lea     edx, [r8+1]
0x180004d1c  mov     eax, r8d
0x180004d1f  lock cmpxchg [rcx+10h], edx
0x180004d24  jz      short loc_180004D31
0x180004d26  mov     r8d, [rcx+10h]
0x180004d2a  cmp     r8d, r9d
0x180004d2d  jnz     short loc_180004D18
0x180004d2f  jmp     short loc_180004D35
0x180004d31  lea     r9d, [r8+1]
0x180004d35  mov     eax, r9d
0x180004d38  retn
```
