# ATL::CComObject<CRestoreSession>::Release(void)

- ea: `0x1800061a0`
- end: `0x1800061fd`
- name: `?Release@?$CComObject@VCRestoreSession@@@ATL@@UEAAKXZ`
- size: `93`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002f08`
- `0x1800061a0`
- `0x180006498`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CRestoreSession>::Release(volatile int *a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = ATL::SafeDecrementReferenceMultiThread(a1 + 2);
  if ( !v2 )
  {
    ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v4);
    if ( a1 )
      (*(void (__fastcall **)(volatile int *, _QWORD))(*(_QWORD *)a1 + 56LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x1800061a0  mov     [rsp+arg_8], rbx
0x1800061a5  push    rdi
0x1800061a6  sub     rsp, 20h
0x1800061aa  mov     rbx, rcx
0x1800061ad  add     rcx, 8; volatile int *
0x1800061b1  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x1800061b6  mov     edi, eax
0x1800061b8  test    eax, eax
0x1800061ba  jnz     short loc_1800061F0
0x1800061bc  lea     rcx, [rsp+28h+arg_0]; this
0x1800061c1  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x1800061c6  test    rbx, rbx
0x1800061c9  jz      short loc_1800061DD
0x1800061cb  mov     rdx, [rbx]
0x1800061ce  mov     rcx, rbx
0x1800061d1  mov     rax, [rdx+38h]
0x1800061d5  lea     edx, [rdi+1]
0x1800061d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061dd  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800061e4  mov     rax, [rcx]
0x1800061e7  mov     rax, [rax+10h]
0x1800061eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061f0  mov     rbx, [rsp+28h+arg_8]
0x1800061f5  mov     eax, edi
0x1800061f7  add     rsp, 20h
0x1800061fb  pop     rdi
0x1800061fc  retn
```
