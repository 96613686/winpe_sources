# ATL::CComContainedObject<CMSMQTriggerSet>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000f5e0`
- end: `0x18000f63b`
- name: `?QueryInterface@?$CComContainedObject@VCMSMQTriggerSet@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `91`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f650`

## callees

- `0x18000f5e0`
- `0x180022010`

## import_xrefs

- `ATL!__imp_AtlInternalQueryInterface` at `0x18000f625`
- `ATL!__imp_AtlInternalQueryInterface` at `0x18000f625`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMSMQTriggerSet>::QueryInterface(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax

  result = (***(__int64 (__fastcall ****)(_QWORD))(a1 + 16))(*(_QWORD *)(a1 + 16));
  if ( (int)result < 0 && a1 + 8 != *(_QWORD *)(a1 + 16) )
    return AtlInternalQueryInterface(a1, &`CMSMQTriggerSet::_GetEntries'::`2'::_entries, a2, a3);
  return result;
}

```

## disassembly

```asm
0x18000f5e0  mov     [rsp+arg_0], rbx
0x18000f5e5  mov     [rsp+arg_8], rsi
0x18000f5ea  push    rdi
0x18000f5eb  sub     rsp, 20h
0x18000f5ef  mov     rbx, rcx
0x18000f5f2  mov     rdi, r8
0x18000f5f5  mov     rcx, [rcx+10h]
0x18000f5f9  mov     rsi, rdx
0x18000f5fc  mov     rax, [rcx]
0x18000f5ff  mov     rax, [rax]
0x18000f602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f607  test    eax, eax
0x18000f609  jns     short loc_18000F62B
0x18000f60b  lea     rcx, [rbx+8]
0x18000f60f  cmp     rcx, [rbx+10h]
0x18000f613  jz      short loc_18000F62B
0x18000f615  mov     r9, rdi
0x18000f618  lea     rdx, ?_entries@?1??_GetEntries@CMSMQTriggerSet@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CMSMQTriggerSet::_GetEntries(void)'::`2'::_entries
0x18000f61f  mov     r8, rsi
0x18000f622  mov     rcx, rbx
0x18000f625  call    cs:__imp_AtlInternalQueryInterface
0x18000f62b  mov     rbx, [rsp+28h+arg_0]
0x18000f630  mov     rsi, [rsp+28h+arg_8]
0x18000f635  add     rsp, 20h
0x18000f639  pop     rdi
0x18000f63a  retn
```
