# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180006280`
- end: `0x1800062c7`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `71`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800036c8`
- `0x180006280`
- `0x180006498`
- `0x180034010`

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
0x180006280  push    rbx
0x180006282  sub     rsp, 20h
0x180006286  mov     r10, rcx
0x180006289  add     rcx, 8; volatile int *
0x18000628d  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180006292  mov     ebx, eax
0x180006294  test    eax, eax
0x180006296  jnz     short loc_1800062A7
0x180006298  test    r10, r10
0x18000629b  jz      short loc_1800062BF
0x18000629d  mov     rcx, r10
0x1800062a0  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x1800062a5  jmp     short loc_1800062BF
0x1800062a7  cmp     ebx, 1
0x1800062aa  jnz     short loc_1800062BF
0x1800062ac  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800062b3  mov     rax, [rcx]
0x1800062b6  mov     rax, [rax+10h]
0x1800062ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062bf  mov     eax, ebx
0x1800062c1  add     rsp, 20h
0x1800062c5  pop     rbx
0x1800062c6  retn
```
