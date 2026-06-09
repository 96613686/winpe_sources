# ATL::CComObjectCached<MapsBackgroundTransferClassFactory>::Release(void)

- ea: `0x1800031a0`
- end: `0x1800031e7`
- name: `?Release@?$CComObjectCached@VMapsBackgroundTransferClassFactory@@@ATL@@UEAAKXZ`
- size: `71`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002b28`
- `0x1800031a0`
- `0x1800031f0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<MapsBackgroundTransferClassFactory>::Release(__int64 a1)
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
    ATL::CComObjectCached<MapsBackgroundTransferClassFactory>::`scalar deleting destructor'(v2);
  }
  return v1;
}

```

## disassembly

```asm
0x1800031a0  push    rbx
0x1800031a2  sub     rsp, 20h
0x1800031a6  mov     r10, rcx
0x1800031a9  add     rcx, 8; volatile int *
0x1800031ad  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x1800031b2  mov     ebx, eax
0x1800031b4  test    eax, eax
0x1800031b6  jnz     short loc_1800031C7
0x1800031b8  test    r10, r10
0x1800031bb  jz      short loc_1800031DF
0x1800031bd  mov     rcx, r10; Block
0x1800031c0  call    ??_G?$CComObjectCached@VMapsBackgroundTransferClassFactory@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<MapsBackgroundTransferClassFactory>::`scalar deleting destructor'(uint)
0x1800031c5  jmp     short loc_1800031DF
0x1800031c7  cmp     ebx, 1
0x1800031ca  jnz     short loc_1800031DF
0x1800031cc  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800031d3  mov     rax, [rcx]
0x1800031d6  mov     rax, [rax+10h]
0x1800031da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031df  mov     eax, ebx
0x1800031e1  add     rsp, 20h
0x1800031e5  pop     rbx
0x1800031e6  retn
```
