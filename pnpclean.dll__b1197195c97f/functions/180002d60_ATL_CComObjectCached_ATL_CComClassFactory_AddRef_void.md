# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180002d60`
- end: `0x180002daa`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `74`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002d60`
- `0x18000a010`

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
0x180002d60  push    rbx
0x180002d62  sub     rsp, 20h
0x180002d66  mov     ebx, 7FFFFFFFh
0x180002d6b  jmp     short loc_180002D7B
0x180002d6d  lea     edx, [r8+1]
0x180002d71  mov     eax, r8d
0x180002d74  lock cmpxchg [rcx+8], edx
0x180002d79  jz      short loc_180002D86
0x180002d7b  mov     r8d, [rcx+8]
0x180002d7f  cmp     r8d, ebx
0x180002d82  jnz     short loc_180002D6D
0x180002d84  jmp     short loc_180002DA2
0x180002d86  lea     ebx, [r8+1]
0x180002d8a  cmp     ebx, 2
0x180002d8d  jnz     short loc_180002DA2
0x180002d8f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002d96  mov     rax, [rcx]
0x180002d99  mov     rax, [rax+8]
0x180002d9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002da2  mov     eax, ebx
0x180002da4  add     rsp, 20h
0x180002da8  pop     rbx
0x180002da9  retn
```
