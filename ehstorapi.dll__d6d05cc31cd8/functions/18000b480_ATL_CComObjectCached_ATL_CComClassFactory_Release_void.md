# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x18000b480`
- end: `0x18000b4c7`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003894`
- `0x180008db8`
- `0x18000b480`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::Release(__int64 a1)
{
  unsigned int v1; // ebx
  void *v2; // r10

  v1 = ATL::SafeDecrementReferenceMultiThread((volatile int *)(a1 + 8));
  if ( v1 )
  {
    if ( v1 == 1 )
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  else if ( v2 )
  {
    ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(v2);
  }
  return v1;
}

```

## disassembly

```asm
0x18000b480  push    rbx
0x18000b482  sub     rsp, 20h
0x18000b486  mov     r10, rcx
0x18000b489  add     rcx, 8; volatile int *
0x18000b48d  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18000b492  mov     ebx, eax
0x18000b494  test    eax, eax
0x18000b496  jnz     short loc_18000B4A7
0x18000b498  test    r10, r10
0x18000b49b  jz      short loc_18000B4BF
0x18000b49d  mov     rcx, r10; Block
0x18000b4a0  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x18000b4a5  jmp     short loc_18000B4BF
0x18000b4a7  cmp     ebx, 1
0x18000b4aa  jnz     short loc_18000B4BF
0x18000b4ac  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000b4b3  mov     rax, [rcx]
0x18000b4b6  mov     rax, [rax+10h]
0x18000b4ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4bf  mov     eax, ebx
0x18000b4c1  add     rsp, 20h
0x18000b4c5  pop     rbx
0x18000b4c6  retn
```
