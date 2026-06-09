# ATL::CComObject<IASTL::IASComponentObject<NTEventLog>>::AddRef(void)

- ea: `0x18000df10`
- end: `0x18000df39`
- name: `?AddRef@?$CComObject@V?$IASComponentObject@VNTEventLog@@@IASTL@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000df40`

## callees

- `0x18000df10`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<IASTL::IASComponentObject<NTEventLog>>::AddRef(__int64 a1)
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
0x18000df10  mov     r9d, 7FFFFFFFh
0x18000df16  jmp     short loc_18000DF26
0x18000df18  lea     edx, [r8+1]
0x18000df1c  mov     eax, r8d
0x18000df1f  lock cmpxchg [rcx+8], edx
0x18000df24  jz      short loc_18000DF31
0x18000df26  mov     r8d, [rcx+8]
0x18000df2a  cmp     r8d, r9d
0x18000df2d  jnz     short loc_18000DF18
0x18000df2f  jmp     short loc_18000DF35
0x18000df31  lea     r9d, [r8+1]
0x18000df35  mov     eax, r9d
0x18000df38  retn
```
