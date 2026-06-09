# ATL::CComObject<CL2TPDiagHelper>::AddRef(void)

- ea: `0x1800061e0`
- end: `0x180006209`
- name: `?AddRef@?$CComObject@VCL2TPDiagHelper@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006210`

## callees

- `0x1800061e0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CL2TPDiagHelper>::AddRef(__int64 a1)
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
0x1800061e0  mov     r9d, 7FFFFFFFh
0x1800061e6  jmp     short loc_1800061F6
0x1800061e8  lea     edx, [r8+1]
0x1800061ec  mov     eax, r8d
0x1800061ef  lock cmpxchg [rcx+38h], edx
0x1800061f4  jz      short loc_180006201
0x1800061f6  mov     r8d, [rcx+38h]
0x1800061fa  cmp     r8d, r9d
0x1800061fd  jnz     short loc_1800061E8
0x1800061ff  jmp     short loc_180006205
0x180006201  lea     r9d, [r8+1]
0x180006205  mov     eax, r9d
0x180006208  retn
```
