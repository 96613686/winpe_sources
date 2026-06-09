# ATL::CComContainedObject<CMSMQRuleHandler>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000f560`
- end: `0x18000f5bb`
- name: `?QueryInterface@?$CComContainedObject@VCMSMQRuleHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `91`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f5d0`

## callees

- `0x18000f560`
- `0x180022010`

## import_xrefs

- `ATL!__imp_AtlInternalQueryInterface` at `0x18000f5a5`
- `ATL!__imp_AtlInternalQueryInterface` at `0x18000f5a5`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMSMQRuleHandler>::QueryInterface(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax

  result = (***(__int64 (__fastcall ****)(_QWORD))(a1 + 16))(*(_QWORD *)(a1 + 16));
  if ( (int)result < 0 && a1 + 8 != *(_QWORD *)(a1 + 16) )
    return AtlInternalQueryInterface(a1, &`CMSMQRuleHandler::_GetEntries'::`2'::_entries, a2, a3);
  return result;
}

```

## disassembly

```asm
0x18000f560  mov     [rsp+arg_0], rbx
0x18000f565  mov     [rsp+arg_8], rsi
0x18000f56a  push    rdi
0x18000f56b  sub     rsp, 20h
0x18000f56f  mov     rbx, rcx
0x18000f572  mov     rdi, r8
0x18000f575  mov     rcx, [rcx+10h]
0x18000f579  mov     rsi, rdx
0x18000f57c  mov     rax, [rcx]
0x18000f57f  mov     rax, [rax]
0x18000f582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f587  test    eax, eax
0x18000f589  jns     short loc_18000F5AB
0x18000f58b  lea     rcx, [rbx+8]
0x18000f58f  cmp     rcx, [rbx+10h]
0x18000f593  jz      short loc_18000F5AB
0x18000f595  mov     r9, rdi
0x18000f598  lea     rdx, ?_entries@?1??_GetEntries@CMSMQRuleHandler@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CMSMQRuleHandler::_GetEntries(void)'::`2'::_entries
0x18000f59f  mov     r8, rsi
0x18000f5a2  mov     rcx, rbx
0x18000f5a5  call    cs:__imp_AtlInternalQueryInterface
0x18000f5ab  mov     rbx, [rsp+28h+arg_0]
0x18000f5b0  mov     rsi, [rsp+28h+arg_8]
0x18000f5b5  add     rsp, 20h
0x18000f5b9  pop     rdi
0x18000f5ba  retn
```
