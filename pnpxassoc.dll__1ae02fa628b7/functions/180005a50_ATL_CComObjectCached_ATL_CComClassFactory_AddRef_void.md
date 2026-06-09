# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180005a50`
- end: `0x180005a9a`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005a50`
- `0x180014010`

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
0x180005a50  push    rbx
0x180005a52  sub     rsp, 20h
0x180005a56  mov     ebx, 7FFFFFFFh
0x180005a5b  jmp     short loc_180005A6B
0x180005a5d  lea     edx, [r8+1]
0x180005a61  mov     eax, r8d
0x180005a64  lock cmpxchg [rcx+8], edx
0x180005a69  jz      short loc_180005A76
0x180005a6b  mov     r8d, [rcx+8]
0x180005a6f  cmp     r8d, ebx
0x180005a72  jnz     short loc_180005A5D
0x180005a74  jmp     short loc_180005A92
0x180005a76  lea     ebx, [r8+1]
0x180005a7a  cmp     ebx, 2
0x180005a7d  jnz     short loc_180005A92
0x180005a7f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005a86  mov     rax, [rcx]
0x180005a89  mov     rax, [rax+8]
0x180005a8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a92  mov     eax, ebx
0x180005a94  add     rsp, 20h
0x180005a98  pop     rbx
0x180005a99  retn
```
