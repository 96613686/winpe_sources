# ATL::CComObject<CWFPClientsHelperClass>::AddRef(void)

- ea: `0x180009ac0`
- end: `0x180009ae9`
- name: `?AddRef@?$CComObject@VCWFPClientsHelperClass@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009af0`

## callees

- `0x180009ac0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWFPClientsHelperClass>::AddRef(__int64 a1)
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
0x180009ac0  mov     r9d, 7FFFFFFFh
0x180009ac6  jmp     short loc_180009AD6
0x180009ac8  lea     edx, [r8+1]
0x180009acc  mov     eax, r8d
0x180009acf  lock cmpxchg [rcx+10h], edx
0x180009ad4  jz      short loc_180009AE1
0x180009ad6  mov     r8d, [rcx+10h]
0x180009ada  cmp     r8d, r9d
0x180009add  jnz     short loc_180009AC8
0x180009adf  jmp     short loc_180009AE5
0x180009ae1  lea     r9d, [r8+1]
0x180009ae5  mov     eax, r9d
0x180009ae8  retn
```
