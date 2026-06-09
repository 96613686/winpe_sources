# ATL::CComObject<CGameExplorer>::Release(void)

- ea: `0x180002400`
- end: `0x18000245d`
- name: `?Release@?$CComObject@VCGameExplorer@@@ATL@@UEAAKXZ`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002470`

## callees

- `0x180001bb4`
- `0x180002400`
- `0x1800024d0`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CGameExplorer>::Release(volatile int *a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = ATL::SafeDecrementReferenceMultiThread(a1 + 4);
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
0x180002400  mov     [rsp+arg_8], rbx
0x180002405  push    rdi
0x180002406  sub     rsp, 20h
0x18000240a  mov     rbx, rcx
0x18000240d  add     rcx, 10h; volatile int *
0x180002411  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180002416  mov     edi, eax
0x180002418  test    eax, eax
0x18000241a  jnz     short loc_180002450
0x18000241c  lea     rcx, [rsp+28h+arg_0]; this
0x180002421  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x180002426  test    rbx, rbx
0x180002429  jz      short loc_18000243D
0x18000242b  mov     rdx, [rbx]
0x18000242e  mov     rcx, rbx
0x180002431  mov     rax, [rdx+30h]
0x180002435  lea     edx, [rdi+1]
0x180002438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000243d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002444  mov     rax, [rcx]
0x180002447  mov     rax, [rax+10h]
0x18000244b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002450  mov     rbx, [rsp+28h+arg_8]
0x180002455  mov     eax, edi
0x180002457  add     rsp, 20h
0x18000245b  pop     rdi
0x18000245c  retn
```
