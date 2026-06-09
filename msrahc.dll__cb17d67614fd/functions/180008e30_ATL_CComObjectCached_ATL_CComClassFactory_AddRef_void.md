# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180008e30`
- end: `0x180008e61`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `49`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180008e30`
- `0x18000bb8c`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(__int64 a1)
{
  unsigned int v1; // ebx

  v1 = ATL::SafeIncrementReferenceMultiThread((volatile int *)(a1 + 8));
  if ( v1 == 2 )
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  return v1;
}

```

## disassembly

```asm
0x180008e30  push    rbx
0x180008e32  sub     rsp, 20h
0x180008e36  add     rcx, 8; volatile int *
0x180008e3a  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x180008e3f  mov     ebx, eax
0x180008e41  cmp     eax, 2
0x180008e44  jnz     short loc_180008E59
0x180008e46  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008e4d  mov     rdx, [rcx]
0x180008e50  mov     rax, [rdx+8]
0x180008e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e59  mov     eax, ebx
0x180008e5b  add     rsp, 20h
0x180008e5f  pop     rbx
0x180008e60  retn
```
