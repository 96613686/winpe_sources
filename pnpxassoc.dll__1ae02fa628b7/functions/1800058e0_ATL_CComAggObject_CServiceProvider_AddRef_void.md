# ATL::CComAggObject<CServiceProvider>::AddRef(void)

- ea: `0x1800058e0`
- end: `0x180005909`
- name: `?AddRef@?$CComAggObject@VCServiceProvider@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800058e0`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CServiceProvider>::AddRef(__int64 a1)
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
0x1800058e0  mov     r9d, 7FFFFFFFh
0x1800058e6  jmp     short loc_1800058F6
0x1800058e8  lea     edx, [r8+1]
0x1800058ec  mov     eax, r8d
0x1800058ef  lock cmpxchg [rcx+8], edx
0x1800058f4  jz      short loc_180005901
0x1800058f6  mov     r8d, [rcx+8]
0x1800058fa  cmp     r8d, r9d
0x1800058fd  jnz     short loc_1800058E8
0x1800058ff  jmp     short loc_180005905
0x180005901  lea     r9d, [r8+1]
0x180005905  mov     eax, r9d
0x180005908  retn
```
