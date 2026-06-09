# ATL::CComObject<CEnhancedStorageSilo>::Release(void)

- ea: `0x180003800`
- end: `0x18000385d`
- name: `?Release@?$CComObject@VCEnhancedStorageSilo@@@ATL@@UEAAKXZ`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000209c`
- `0x180003800`
- `0x180003894`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEnhancedStorageSilo>::Release(volatile int *a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = ATL::SafeDecrementReferenceMultiThread(a1 + 2);
  if ( !v2 )
  {
    ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v4);
    if ( a1 )
      (*(void (__fastcall **)(volatile int *, _QWORD))(*(_QWORD *)a1 + 64LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x180003800  mov     [rsp+arg_8], rbx
0x180003805  push    rdi
0x180003806  sub     rsp, 20h
0x18000380a  mov     rbx, rcx
0x18000380d  add     rcx, 8; volatile int *
0x180003811  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180003816  mov     edi, eax
0x180003818  test    eax, eax
0x18000381a  jnz     short loc_180003850
0x18000381c  lea     rcx, [rsp+28h+arg_0]; this
0x180003821  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x180003826  test    rbx, rbx
0x180003829  jz      short loc_18000383D
0x18000382b  mov     rdx, [rbx]
0x18000382e  mov     rcx, rbx
0x180003831  mov     rax, [rdx+40h]
0x180003835  lea     edx, [rdi+1]
0x180003838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000383d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003844  mov     rax, [rcx]
0x180003847  mov     rax, [rax+10h]
0x18000384b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003850  mov     rbx, [rsp+28h+arg_8]
0x180003855  mov     eax, edi
0x180003857  add     rsp, 20h
0x18000385b  pop     rdi
0x18000385c  retn
```
