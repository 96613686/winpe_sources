# ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)

- ea: `0x180003a20`
- end: `0x180003a51`
- name: `?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `49`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003a20`
- `0x1800064c0`
- `0x180034010`

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
0x180003a20  push    rbx
0x180003a22  sub     rsp, 20h
0x180003a26  add     rcx, 8; volatile int *
0x180003a2a  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x180003a2f  mov     ebx, eax
0x180003a31  cmp     eax, 2
0x180003a34  jnz     short loc_180003A49
0x180003a36  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003a3d  mov     rdx, [rcx]
0x180003a40  mov     rax, [rdx+8]
0x180003a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a49  mov     eax, ebx
0x180003a4b  add     rsp, 20h
0x180003a4f  pop     rbx
0x180003a50  retn
```
