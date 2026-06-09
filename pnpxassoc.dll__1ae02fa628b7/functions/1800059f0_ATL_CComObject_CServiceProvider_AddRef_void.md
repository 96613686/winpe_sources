# ATL::CComObject<CServiceProvider>::AddRef(void)

- ea: `0x1800059f0`
- end: `0x180005a19`
- name: `?AddRef@?$CComObject@VCServiceProvider@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005a20`
- `0x180005a30`
- `0x180005a40`

## callees

- `0x1800059f0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CServiceProvider>::AddRef(__int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 32);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 32), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x1800059f0  mov     r9d, 7FFFFFFFh
0x1800059f6  jmp     short loc_180005A06
0x1800059f8  lea     edx, [r8+1]
0x1800059fc  mov     eax, r8d
0x1800059ff  lock cmpxchg [rcx+20h], edx
0x180005a04  jz      short loc_180005A11
0x180005a06  mov     r8d, [rcx+20h]
0x180005a0a  cmp     r8d, r9d
0x180005a0d  jnz     short loc_1800059F8
0x180005a0f  jmp     short loc_180005A15
0x180005a11  lea     r9d, [r8+1]
0x180005a15  mov     eax, r9d
0x180005a18  retn
```
