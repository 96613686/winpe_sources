# ATL::CComContainedObject<CIisRestart>::QueryInterface(_GUID const &,void * *)

- ea: `0x140002780`
- end: `0x1400027d7`
- name: `?QueryInterface@?$CComContainedObject@VCIisRestart@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140002780`
- `0x140006010`

## import_xrefs

- `ATL!__imp_AtlInternalQueryInterface` at `0x1400027c1`
- `ATL!__imp_AtlInternalQueryInterface` at `0x1400027c1`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CIisRestart>::QueryInterface(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax

  result = (***(__int64 (__fastcall ****)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 8));
  if ( (int)result < 0 && a1 != *(_QWORD *)(a1 + 8) )
    return AtlInternalQueryInterface(a1, &`CIisRestart::_GetEntries'::`2'::_entries, a2, a3);
  return result;
}

```

## disassembly

```asm
0x140002780  mov     [rsp+arg_0], rbx
0x140002785  mov     [rsp+arg_8], rsi
0x14000278a  push    rdi
0x14000278b  sub     rsp, 20h
0x14000278f  mov     rbx, rcx
0x140002792  mov     rdi, r8
0x140002795  mov     rcx, [rcx+8]
0x140002799  mov     rsi, rdx
0x14000279c  mov     rax, [rcx]
0x14000279f  mov     rax, [rax]
0x1400027a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400027a7  test    eax, eax
0x1400027a9  jns     short loc_1400027C7
0x1400027ab  cmp     rbx, [rbx+8]
0x1400027af  jz      short loc_1400027C7
0x1400027b1  mov     r9, rdi
0x1400027b4  lea     rdx, ?_entries@?1??_GetEntries@CIisRestart@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CIisRestart::_GetEntries(void)'::`2'::_entries
0x1400027bb  mov     r8, rsi
0x1400027be  mov     rcx, rbx
0x1400027c1  call    cs:__imp_AtlInternalQueryInterface
0x1400027c7  mov     rbx, [rsp+28h+arg_0]
0x1400027cc  mov     rsi, [rsp+28h+arg_8]
0x1400027d1  add     rsp, 20h
0x1400027d5  pop     rdi
0x1400027d6  retn
```
