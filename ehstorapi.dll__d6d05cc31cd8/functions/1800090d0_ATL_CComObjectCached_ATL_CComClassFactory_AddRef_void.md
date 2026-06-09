# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x1800090d0`
- end: `0x180009101`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800038bc`
- `0x1800090d0`
- `0x18000d010`

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
0x1800090d0  push    rbx
0x1800090d2  sub     rsp, 20h
0x1800090d6  add     rcx, 8; volatile int *
0x1800090da  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x1800090df  mov     ebx, eax
0x1800090e1  cmp     eax, 2
0x1800090e4  jnz     short loc_1800090F9
0x1800090e6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800090ed  mov     rdx, [rcx]
0x1800090f0  mov     rax, [rdx+8]
0x1800090f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090f9  mov     eax, ebx
0x1800090fb  add     rsp, 20h
0x1800090ff  pop     rbx
0x180009100  retn
```
