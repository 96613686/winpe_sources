# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180002c80`
- end: `0x180002cca`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002c80`
- `0x180007010`

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
        (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
      return v1;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180002c80  push    rbx
0x180002c82  sub     rsp, 20h
0x180002c86  mov     ebx, 7FFFFFFFh
0x180002c8b  jmp     short loc_180002C9B
0x180002c8d  lea     edx, [r8+1]
0x180002c91  mov     eax, r8d
0x180002c94  lock cmpxchg [rcx+8], edx
0x180002c99  jz      short loc_180002CA6
0x180002c9b  mov     r8d, [rcx+8]
0x180002c9f  cmp     r8d, ebx
0x180002ca2  jnz     short loc_180002C8D
0x180002ca4  jmp     short loc_180002CC2
0x180002ca6  lea     ebx, [r8+1]
0x180002caa  cmp     ebx, 2
0x180002cad  jnz     short loc_180002CC2
0x180002caf  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002cb6  mov     rax, [rcx]
0x180002cb9  mov     rax, [rax+8]
0x180002cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cc2  mov     eax, ebx
0x180002cc4  add     rsp, 20h
0x180002cc8  pop     rbx
0x180002cc9  retn
```
