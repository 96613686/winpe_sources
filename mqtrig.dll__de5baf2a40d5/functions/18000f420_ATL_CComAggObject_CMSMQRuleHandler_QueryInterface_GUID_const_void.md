# ATL::CComAggObject<CMSMQRuleHandler>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000f420`
- end: `0x18000f478`
- name: `?QueryInterface@?$CComAggObject@VCMSMQRuleHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `88`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ed70`
- `0x18000f420`
- `0x180022010`

## import_xrefs

- `ATL!__imp_AtlInternalQueryInterface` at `0x18000f468`
- `ATL!__imp_AtlInternalQueryInterface` at `0x18000f468`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMSMQRuleHandler>::QueryInterface(__int64 a1, const struct _GUID *a2)
{
  __int64 v2; // rdx
  _QWORD *v3; // r8
  __int64 v4; // r9
  unsigned int v6; // ebx

  if ( (unsigned int)ATL::InlineIsEqualUnknown(a2) )
  {
    if ( !v3 )
      return 2147500035LL;
    *v3 = v4;
    v6 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
  }
  else
  {
    return (unsigned int)AtlInternalQueryInterface(v4 + 24, &`CMSMQRuleHandler::_GetEntries'::`2'::_entries, v2, v3);
  }
  return v6;
}

```

## disassembly

```asm
0x18000f420  push    rbx
0x18000f422  sub     rsp, 20h
0x18000f426  mov     r9, rcx
0x18000f429  mov     rcx, rdx; struct _GUID *
0x18000f42c  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x18000f431  test    eax, eax
0x18000f433  jz      short loc_18000F457
0x18000f435  test    r8, r8
0x18000f438  jnz     short loc_18000F441
0x18000f43a  mov     eax, 80004003h
0x18000f43f  jmp     short loc_18000F472
0x18000f441  mov     [r8], r9
0x18000f444  xor     ebx, ebx
0x18000f446  mov     rax, [r9]
0x18000f449  mov     rcx, r9
0x18000f44c  mov     rax, [rax+8]
0x18000f450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f455  jmp     short loc_18000F470
0x18000f457  lea     rcx, [r9+18h]
0x18000f45b  mov     r9, r8
0x18000f45e  mov     r8, rdx
0x18000f461  lea     rdx, ?_entries@?1??_GetEntries@CMSMQRuleHandler@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CMSMQRuleHandler::_GetEntries(void)'::`2'::_entries
0x18000f468  call    cs:__imp_AtlInternalQueryInterface
0x18000f46e  mov     ebx, eax
0x18000f470  mov     eax, ebx
0x18000f472  add     rsp, 20h
0x18000f476  pop     rbx
0x18000f477  retn
```
