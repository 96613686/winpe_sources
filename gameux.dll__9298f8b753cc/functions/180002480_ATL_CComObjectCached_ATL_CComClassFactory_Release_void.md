# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180002480`
- end: `0x1800024c7`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001d58`
- `0x180002480`
- `0x1800024d0`
- `0x180004010`

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
0x180002480  push    rbx
0x180002482  sub     rsp, 20h
0x180002486  mov     r10, rcx
0x180002489  add     rcx, 8; volatile int *
0x18000248d  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180002492  mov     ebx, eax
0x180002494  test    eax, eax
0x180002496  jnz     short loc_1800024A7
0x180002498  test    r10, r10
0x18000249b  jz      short loc_1800024BF
0x18000249d  mov     rcx, r10; Block
0x1800024a0  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x1800024a5  jmp     short loc_1800024BF
0x1800024a7  cmp     ebx, 1
0x1800024aa  jnz     short loc_1800024BF
0x1800024ac  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800024b3  mov     rax, [rcx]
0x1800024b6  mov     rax, [rax+10h]
0x1800024ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024bf  mov     eax, ebx
0x1800024c1  add     rsp, 20h
0x1800024c5  pop     rbx
0x1800024c6  retn
```
