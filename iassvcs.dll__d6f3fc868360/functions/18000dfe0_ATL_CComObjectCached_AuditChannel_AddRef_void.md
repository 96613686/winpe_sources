# ATL::CComObjectCached<AuditChannel>::AddRef(void)

- ea: `0x18000dfe0`
- end: `0x18000e02a`
- name: `?AddRef@?$CComObjectCached@VAuditChannel@@@ATL@@UEAAKXZ`
- size: `74`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e030`

## callees

- `0x18000dfe0`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<AuditChannel>::AddRef(__int64 a1)
{
  unsigned int v1; // ebx
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 16);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 16), v2 + 1, v2) )
    {
      v1 = v2 + 1;
      if ( v2 == 1 )
        (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
      return v1;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18000dfe0  push    rbx
0x18000dfe2  sub     rsp, 20h
0x18000dfe6  mov     ebx, 7FFFFFFFh
0x18000dfeb  jmp     short loc_18000DFFB
0x18000dfed  lea     edx, [r8+1]
0x18000dff1  mov     eax, r8d
0x18000dff4  lock cmpxchg [rcx+10h], edx
0x18000dff9  jz      short loc_18000E006
0x18000dffb  mov     r8d, [rcx+10h]
0x18000dfff  cmp     r8d, ebx
0x18000e002  jnz     short loc_18000DFED
0x18000e004  jmp     short loc_18000E022
0x18000e006  lea     ebx, [r8+1]
0x18000e00a  cmp     ebx, 2
0x18000e00d  jnz     short loc_18000E022
0x18000e00f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000e016  mov     rax, [rcx]
0x18000e019  mov     rax, [rax+8]
0x18000e01d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e022  mov     eax, ebx
0x18000e024  add     rsp, 20h
0x18000e028  pop     rbx
0x18000e029  retn
```
