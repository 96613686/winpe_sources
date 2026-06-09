# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x18000bac0`
- end: `0x18000bb07`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `71`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180008aa8`
- `0x18000bac0`
- `0x18000bb64`
- `0x18001c010`

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
      (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
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
0x18000bac0  push    rbx
0x18000bac2  sub     rsp, 20h
0x18000bac6  mov     r10, rcx
0x18000bac9  add     rcx, 8; volatile int *
0x18000bacd  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18000bad2  mov     ebx, eax
0x18000bad4  test    eax, eax
0x18000bad6  jnz     short loc_18000BAE7
0x18000bad8  test    r10, r10
0x18000badb  jz      short loc_18000BAFF
0x18000badd  mov     rcx, r10
0x18000bae0  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x18000bae5  jmp     short loc_18000BAFF
0x18000bae7  cmp     ebx, 1
0x18000baea  jnz     short loc_18000BAFF
0x18000baec  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000baf3  mov     rax, [rcx]
0x18000baf6  mov     rax, [rax+10h]
0x18000bafa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000baff  mov     eax, ebx
0x18000bb01  add     rsp, 20h
0x18000bb05  pop     rbx
0x18000bb06  retn
```
