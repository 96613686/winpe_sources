# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180006220`
- end: `0x18000626b`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `75`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006220`
- `0x18000f010`

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
0x180006220  push    rbx
0x180006222  sub     rsp, 20h
0x180006226  mov     ebx, 7FFFFFFFh
0x18000622b  jmp     short loc_18000623B
0x18000622d  lea     edx, [r8+1]
0x180006231  mov     eax, r8d
0x180006234  lock cmpxchg [rcx+8], edx
0x180006239  jz      short loc_180006246
0x18000623b  mov     r8d, [rcx+8]
0x18000623f  cmp     r8d, ebx
0x180006242  jnz     short loc_18000622D
0x180006244  jmp     short loc_180006262
0x180006246  lea     ebx, [r8+1]
0x18000624a  cmp     ebx, 2
0x18000624d  jnz     short loc_180006262
0x18000624f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006256  mov     rax, [rcx]
0x180006259  mov     rax, [rax+8]
0x18000625d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006262  mov     eax, ebx
0x180006264  add     rsp, 20h
0x180006268  pop     rbx
0x180006269  retn
```
