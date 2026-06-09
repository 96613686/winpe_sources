# ATL::CComObject<MapsBackgroundTransferClassFactory>::Release(void)

- ea: `0x180003880`
- end: `0x1800038dd`
- name: `?Release@?$CComObject@VMapsBackgroundTransferClassFactory@@@ATL@@UEAAKXZ`
- size: `93`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002a10`
- `0x1800031f0`
- `0x180003880`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<MapsBackgroundTransferClassFactory>::Release(volatile int *a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = ATL::SafeDecrementReferenceMultiThread(a1 + 2);
  if ( !v2 )
  {
    ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v4);
    if ( a1 )
      (*(void (__fastcall **)(volatile int *, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x180003880  mov     [rsp+arg_8], rbx
0x180003885  push    rdi
0x180003886  sub     rsp, 20h
0x18000388a  mov     rbx, rcx
0x18000388d  add     rcx, 8; volatile int *
0x180003891  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180003896  mov     edi, eax
0x180003898  test    eax, eax
0x18000389a  jnz     short loc_1800038D0
0x18000389c  lea     rcx, [rsp+28h+arg_0]; this
0x1800038a1  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x1800038a6  test    rbx, rbx
0x1800038a9  jz      short loc_1800038BD
0x1800038ab  mov     rdx, [rbx]
0x1800038ae  mov     rcx, rbx
0x1800038b1  mov     rax, [rdx+28h]
0x1800038b5  lea     edx, [rdi+1]
0x1800038b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038bd  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800038c4  mov     rax, [rcx]
0x1800038c7  mov     rax, [rax+10h]
0x1800038cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038d0  mov     rbx, [rsp+28h+arg_8]
0x1800038d5  mov     eax, edi
0x1800038d7  add     rsp, 20h
0x1800038db  pop     rdi
0x1800038dc  retn
```
