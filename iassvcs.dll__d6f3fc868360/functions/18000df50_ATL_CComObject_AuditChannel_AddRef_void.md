# ATL::CComObject<AuditChannel>::AddRef(void)

- ea: `0x18000df50`
- end: `0x18000df79`
- name: `?AddRef@?$CComObject@VAuditChannel@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000df80`

## callees

- `0x18000df50`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<AuditChannel>::AddRef(__int64 a1)
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
0x18000df50  mov     r9d, 7FFFFFFFh
0x18000df56  jmp     short loc_18000DF66
0x18000df58  lea     edx, [r8+1]
0x18000df5c  mov     eax, r8d
0x18000df5f  lock cmpxchg [rcx+10h], edx
0x18000df64  jz      short loc_18000DF71
0x18000df66  mov     r8d, [rcx+10h]
0x18000df6a  cmp     r8d, r9d
0x18000df6d  jnz     short loc_18000DF58
0x18000df6f  jmp     short loc_18000DF75
0x18000df71  lea     r9d, [r8+1]
0x18000df75  mov     eax, r9d
0x18000df78  retn
```
