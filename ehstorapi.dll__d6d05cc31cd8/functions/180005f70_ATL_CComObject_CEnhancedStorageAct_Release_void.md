# ATL::CComObject<CEnhancedStorageAct>::Release(void)

- ea: `0x180005f70`
- end: `0x180005fcd`
- name: `?Release@?$CComObject@VCEnhancedStorageAct@@@ATL@@UEAAKXZ`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000209c`
- `0x180003894`
- `0x180005f70`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEnhancedStorageAct>::Release(volatile int *a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = ATL::SafeDecrementReferenceMultiThread(a1 + 2);
  if ( !v2 )
  {
    ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v4);
    if ( a1 )
      (*(void (__fastcall **)(volatile int *, _QWORD))(*(_QWORD *)a1 + 112LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x180005f70  mov     [rsp+arg_8], rbx
0x180005f75  push    rdi
0x180005f76  sub     rsp, 20h
0x180005f7a  mov     rbx, rcx
0x180005f7d  add     rcx, 8; volatile int *
0x180005f81  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180005f86  mov     edi, eax
0x180005f88  test    eax, eax
0x180005f8a  jnz     short loc_180005FC0
0x180005f8c  lea     rcx, [rsp+28h+arg_0]; this
0x180005f91  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x180005f96  test    rbx, rbx
0x180005f99  jz      short loc_180005FAD
0x180005f9b  mov     rdx, [rbx]
0x180005f9e  mov     rcx, rbx
0x180005fa1  mov     rax, [rdx+70h]
0x180005fa5  lea     edx, [rdi+1]
0x180005fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fad  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005fb4  mov     rax, [rcx]
0x180005fb7  mov     rax, [rax+10h]
0x180005fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fc0  mov     rbx, [rsp+28h+arg_8]
0x180005fc5  mov     eax, edi
0x180005fc7  add     rsp, 20h
0x180005fcb  pop     rdi
0x180005fcc  retn
```
