# ATL::CComObjectCached<ATL::CComClassFactorySingleton<AuditChannel>>::AddRef(void)

- ea: `0x18000df90`
- end: `0x18000dfda`
- name: `?AddRef@?$CComObjectCached@V?$CComClassFactorySingleton@VAuditChannel@@@ATL@@@ATL@@UEAAKXZ`
- size: `74`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000df90`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactorySingleton<AuditChannel>>::AddRef(__int64 a1)
{
  unsigned int v1; // ebx
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 8);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8), v2 + 1, v2) )
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
0x18000df90  push    rbx
0x18000df92  sub     rsp, 20h
0x18000df96  mov     ebx, 7FFFFFFFh
0x18000df9b  jmp     short loc_18000DFAB
0x18000df9d  lea     edx, [r8+1]
0x18000dfa1  mov     eax, r8d
0x18000dfa4  lock cmpxchg [rcx+8], edx
0x18000dfa9  jz      short loc_18000DFB6
0x18000dfab  mov     r8d, [rcx+8]
0x18000dfaf  cmp     r8d, ebx
0x18000dfb2  jnz     short loc_18000DF9D
0x18000dfb4  jmp     short loc_18000DFD2
0x18000dfb6  lea     ebx, [r8+1]
0x18000dfba  cmp     ebx, 2
0x18000dfbd  jnz     short loc_18000DFD2
0x18000dfbf  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000dfc6  mov     rax, [rcx]
0x18000dfc9  mov     rax, [rax+8]
0x18000dfcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfd2  mov     eax, ebx
0x18000dfd4  add     rsp, 20h
0x18000dfd8  pop     rbx
0x18000dfd9  retn
```
