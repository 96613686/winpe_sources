# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180002390`
- end: `0x1800023da`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002390`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(__int64 a1)
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
        (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
      return v1;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180002390  push    rbx
0x180002392  sub     rsp, 20h
0x180002396  mov     ebx, 7FFFFFFFh
0x18000239b  jmp     short loc_1800023AB
0x18000239d  lea     edx, [r8+1]
0x1800023a1  mov     eax, r8d
0x1800023a4  lock cmpxchg [rcx+8], edx
0x1800023a9  jz      short loc_1800023B6
0x1800023ab  mov     r8d, [rcx+8]
0x1800023af  cmp     r8d, ebx
0x1800023b2  jnz     short loc_18000239D
0x1800023b4  jmp     short loc_1800023D2
0x1800023b6  lea     ebx, [r8+1]
0x1800023ba  cmp     ebx, 2
0x1800023bd  jnz     short loc_1800023D2
0x1800023bf  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800023c6  mov     rax, [rcx]
0x1800023c9  mov     rax, [rax+8]
0x1800023cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023d2  mov     eax, ebx
0x1800023d4  add     rsp, 20h
0x1800023d8  pop     rbx
0x1800023d9  retn
```
