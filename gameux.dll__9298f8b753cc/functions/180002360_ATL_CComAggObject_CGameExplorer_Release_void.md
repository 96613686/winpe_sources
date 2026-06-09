# ATL::CComAggObject<CGameExplorer>::Release(void)

- ea: `0x180002360`
- end: `0x1800023bd`
- name: `?Release@?$CComAggObject@VCGameExplorer@@@ATL@@UEAAKXZ`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001bb4`
- `0x180002360`
- `0x1800024d0`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CGameExplorer>::Release(volatile int *a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = ATL::SafeDecrementReferenceMultiThread(a1 + 2);
  if ( !v2 )
  {
    ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v4);
    if ( a1 )
      (*(void (__fastcall **)(volatile int *, _QWORD))(*(_QWORD *)a1 + 24LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x180002360  mov     [rsp+arg_8], rbx
0x180002365  push    rdi
0x180002366  sub     rsp, 20h
0x18000236a  mov     rbx, rcx
0x18000236d  add     rcx, 8; volatile int *
0x180002371  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180002376  mov     edi, eax
0x180002378  test    eax, eax
0x18000237a  jnz     short loc_1800023B0
0x18000237c  lea     rcx, [rsp+28h+arg_0]; this
0x180002381  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x180002386  test    rbx, rbx
0x180002389  jz      short loc_18000239D
0x18000238b  mov     rdx, [rbx]
0x18000238e  mov     rcx, rbx
0x180002391  mov     rax, [rdx+18h]
0x180002395  lea     edx, [rdi+1]
0x180002398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000239d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800023a4  mov     rax, [rcx]
0x1800023a7  mov     rax, [rax+10h]
0x1800023ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023b0  mov     rbx, [rsp+28h+arg_8]
0x1800023b5  mov     eax, edi
0x1800023b7  add     rsp, 20h
0x1800023bb  pop     rdi
0x1800023bc  retn
```
