# ATL::CComContainedObject<CMSMQPropertyBag>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000f4e0`
- end: `0x18000f53b`
- name: `?QueryInterface@?$CComContainedObject@VCMSMQPropertyBag@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `91`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f550`

## callees

- `0x18000f4e0`
- `0x180022010`

## import_xrefs

- `ATL!__imp_AtlInternalQueryInterface` at `0x18000f525`
- `ATL!__imp_AtlInternalQueryInterface` at `0x18000f525`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMSMQPropertyBag>::QueryInterface(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax

  result = (***(__int64 (__fastcall ****)(_QWORD))(a1 + 16))(*(_QWORD *)(a1 + 16));
  if ( (int)result < 0 && a1 + 8 != *(_QWORD *)(a1 + 16) )
    return AtlInternalQueryInterface(a1, &`CMSMQPropertyBag::_GetEntries'::`2'::_entries, a2, a3);
  return result;
}

```

## disassembly

```asm
0x18000f4e0  mov     [rsp+arg_0], rbx
0x18000f4e5  mov     [rsp+arg_8], rsi
0x18000f4ea  push    rdi
0x18000f4eb  sub     rsp, 20h
0x18000f4ef  mov     rbx, rcx
0x18000f4f2  mov     rdi, r8
0x18000f4f5  mov     rcx, [rcx+10h]
0x18000f4f9  mov     rsi, rdx
0x18000f4fc  mov     rax, [rcx]
0x18000f4ff  mov     rax, [rax]
0x18000f502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f507  test    eax, eax
0x18000f509  jns     short loc_18000F52B
0x18000f50b  lea     rcx, [rbx+8]
0x18000f50f  cmp     rcx, [rbx+10h]
0x18000f513  jz      short loc_18000F52B
0x18000f515  mov     r9, rdi
0x18000f518  lea     rdx, ?_entries@?1??_GetEntries@CMSMQPropertyBag@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CMSMQPropertyBag::_GetEntries(void)'::`2'::_entries
0x18000f51f  mov     r8, rsi
0x18000f522  mov     rcx, rbx
0x18000f525  call    cs:__imp_AtlInternalQueryInterface
0x18000f52b  mov     rbx, [rsp+28h+arg_0]
0x18000f530  mov     rsi, [rsp+28h+arg_8]
0x18000f535  add     rsp, 20h
0x18000f539  pop     rdi
0x18000f53a  retn
```
