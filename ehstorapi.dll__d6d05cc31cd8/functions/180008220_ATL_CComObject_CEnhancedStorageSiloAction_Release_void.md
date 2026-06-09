# ATL::CComObject<CEnhancedStorageSiloAction>::Release(void)

- ea: `0x180008220`
- end: `0x18000827d`
- name: `?Release@?$CComObject@VCEnhancedStorageSiloAction@@@ATL@@UEAAKXZ`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000209c`
- `0x180003894`
- `0x180008220`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEnhancedStorageSiloAction>::Release(volatile int *a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = ATL::SafeDecrementReferenceMultiThread(a1 + 2);
  if ( !v2 )
  {
    ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v4);
    if ( a1 )
      (*(void (__fastcall **)(volatile int *, _QWORD))(*(_QWORD *)a1 + 48LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x180008220  mov     [rsp+arg_8], rbx
0x180008225  push    rdi
0x180008226  sub     rsp, 20h
0x18000822a  mov     rbx, rcx
0x18000822d  add     rcx, 8; volatile int *
0x180008231  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180008236  mov     edi, eax
0x180008238  test    eax, eax
0x18000823a  jnz     short loc_180008270
0x18000823c  lea     rcx, [rsp+28h+arg_0]; this
0x180008241  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x180008246  test    rbx, rbx
0x180008249  jz      short loc_18000825D
0x18000824b  mov     rdx, [rbx]
0x18000824e  mov     rcx, rbx
0x180008251  mov     rax, [rdx+30h]
0x180008255  lea     edx, [rdi+1]
0x180008258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000825d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008264  mov     rax, [rcx]
0x180008267  mov     rax, [rax+10h]
0x18000826b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008270  mov     rbx, [rsp+28h+arg_8]
0x180008275  mov     eax, edi
0x180008277  add     rsp, 20h
0x18000827b  pop     rdi
0x18000827c  retn
```
