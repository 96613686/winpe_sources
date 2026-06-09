# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180001df0`
- end: `0x180001e21`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001df0`
- `0x1800024f8`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(__int64 a1)
{
  unsigned int v1; // ebx

  v1 = ATL::SafeIncrementReferenceMultiThread((volatile int *)(a1 + 8));
  if ( v1 == 2 )
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  return v1;
}

```

## disassembly

```asm
0x180001df0  push    rbx
0x180001df2  sub     rsp, 20h
0x180001df6  add     rcx, 8; volatile int *
0x180001dfa  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x180001dff  mov     ebx, eax
0x180001e01  cmp     eax, 2
0x180001e04  jnz     short loc_180001E19
0x180001e06  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180001e0d  mov     rdx, [rcx]
0x180001e10  mov     rax, [rdx+8]
0x180001e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e19  mov     eax, ebx
0x180001e1b  add     rsp, 20h
0x180001e1f  pop     rbx
0x180001e20  retn
```
