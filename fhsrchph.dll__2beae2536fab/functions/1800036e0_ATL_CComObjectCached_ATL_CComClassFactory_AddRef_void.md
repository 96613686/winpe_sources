# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x1800036e0`
- end: `0x18000372a`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `74`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800036e0`
- `0x18000c010`

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
0x1800036e0  push    rbx
0x1800036e2  sub     rsp, 20h
0x1800036e6  mov     ebx, 7FFFFFFFh
0x1800036eb  jmp     short loc_1800036FB
0x1800036ed  lea     edx, [r8+1]
0x1800036f1  mov     eax, r8d
0x1800036f4  lock cmpxchg [rcx+8], edx
0x1800036f9  jz      short loc_180003706
0x1800036fb  mov     r8d, [rcx+8]
0x1800036ff  cmp     r8d, ebx
0x180003702  jnz     short loc_1800036ED
0x180003704  jmp     short loc_180003722
0x180003706  lea     ebx, [r8+1]
0x18000370a  cmp     ebx, 2
0x18000370d  jnz     short loc_180003722
0x18000370f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003716  mov     rax, [rcx]
0x180003719  mov     rax, [rax+8]
0x18000371d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003722  mov     eax, ebx
0x180003724  add     rsp, 20h
0x180003728  pop     rbx
0x180003729  retn
```
