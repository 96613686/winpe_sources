# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x18000bb30`
- end: `0x18000bb7a`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `74`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000bb30`
- `0x180011010`

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
0x18000bb30  push    rbx
0x18000bb32  sub     rsp, 20h
0x18000bb36  mov     ebx, 7FFFFFFFh
0x18000bb3b  jmp     short loc_18000BB4B
0x18000bb3d  lea     edx, [r8+1]
0x18000bb41  mov     eax, r8d
0x18000bb44  lock cmpxchg [rcx+8], edx
0x18000bb49  jz      short loc_18000BB56
0x18000bb4b  mov     r8d, [rcx+8]
0x18000bb4f  cmp     r8d, ebx
0x18000bb52  jnz     short loc_18000BB3D
0x18000bb54  jmp     short loc_18000BB72
0x18000bb56  lea     ebx, [r8+1]
0x18000bb5a  cmp     ebx, 2
0x18000bb5d  jnz     short loc_18000BB72
0x18000bb5f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000bb66  mov     rax, [rcx]
0x18000bb69  mov     rax, [rax+8]
0x18000bb6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb72  mov     eax, ebx
0x18000bb74  add     rsp, 20h
0x18000bb78  pop     rbx
0x18000bb79  retn
```
