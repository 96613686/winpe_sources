# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180006070`
- end: `0x1800060bb`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006070`
- `0x180015010`

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
0x180006070  push    rbx
0x180006072  sub     rsp, 20h
0x180006076  mov     ebx, 7FFFFFFFh
0x18000607b  jmp     short loc_18000608B
0x18000607d  lea     edx, [r8+1]
0x180006081  mov     eax, r8d
0x180006084  lock cmpxchg [rcx+8], edx
0x180006089  jz      short loc_180006096
0x18000608b  mov     r8d, [rcx+8]
0x18000608f  cmp     r8d, ebx
0x180006092  jnz     short loc_18000607D
0x180006094  jmp     short loc_1800060B2
0x180006096  lea     ebx, [r8+1]
0x18000609a  cmp     ebx, 2
0x18000609d  jnz     short loc_1800060B2
0x18000609f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800060a6  mov     rax, [rcx]
0x1800060a9  mov     rax, [rax+8]
0x1800060ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060b2  mov     eax, ebx
0x1800060b4  add     rsp, 20h
0x1800060b8  pop     rbx
0x1800060b9  retn
```
