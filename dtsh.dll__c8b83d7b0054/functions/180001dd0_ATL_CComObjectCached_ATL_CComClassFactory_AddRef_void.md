# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180001dd0`
- end: `0x180001e1a`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001dd0`
- `0x180005010`

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
0x180001dd0  push    rbx
0x180001dd2  sub     rsp, 20h
0x180001dd6  mov     ebx, 7FFFFFFFh
0x180001ddb  jmp     short loc_180001DEB
0x180001ddd  lea     edx, [r8+1]
0x180001de1  mov     eax, r8d
0x180001de4  lock cmpxchg [rcx+8], edx
0x180001de9  jz      short loc_180001DF6
0x180001deb  mov     r8d, [rcx+8]
0x180001def  cmp     r8d, ebx
0x180001df2  jnz     short loc_180001DDD
0x180001df4  jmp     short loc_180001E12
0x180001df6  lea     ebx, [r8+1]
0x180001dfa  cmp     ebx, 2
0x180001dfd  jnz     short loc_180001E12
0x180001dff  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180001e06  mov     rax, [rcx]
0x180001e09  mov     rax, [rax+8]
0x180001e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e12  mov     eax, ebx
0x180001e14  add     rsp, 20h
0x180001e18  pop     rbx
0x180001e19  retn
```
