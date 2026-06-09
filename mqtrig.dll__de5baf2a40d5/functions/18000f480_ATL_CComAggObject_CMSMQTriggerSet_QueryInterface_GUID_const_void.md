# ATL::CComAggObject<CMSMQTriggerSet>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000f480`
- end: `0x18000f4d8`
- name: `?QueryInterface@?$CComAggObject@VCMSMQTriggerSet@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `88`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000ed70`
- `0x18000f480`
- `0x180022010`

## import_xrefs

- `ATL!__imp_AtlInternalQueryInterface` at `0x18000f4c8`
- `ATL!__imp_AtlInternalQueryInterface` at `0x18000f4c8`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMSMQTriggerSet>::QueryInterface(__int64 a1, const struct _GUID *a2)
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
    return (unsigned int)AtlInternalQueryInterface(v4 + 24, &`CMSMQTriggerSet::_GetEntries'::`2'::_entries, v2, v3);
  }
  return v6;
}

```

## disassembly

```asm
0x18000f480  push    rbx
0x18000f482  sub     rsp, 20h
0x18000f486  mov     r9, rcx
0x18000f489  mov     rcx, rdx; struct _GUID *
0x18000f48c  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x18000f491  test    eax, eax
0x18000f493  jz      short loc_18000F4B7
0x18000f495  test    r8, r8
0x18000f498  jnz     short loc_18000F4A1
0x18000f49a  mov     eax, 80004003h
0x18000f49f  jmp     short loc_18000F4D2
0x18000f4a1  mov     [r8], r9
0x18000f4a4  xor     ebx, ebx
0x18000f4a6  mov     rax, [r9]
0x18000f4a9  mov     rcx, r9
0x18000f4ac  mov     rax, [rax+8]
0x18000f4b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4b5  jmp     short loc_18000F4D0
0x18000f4b7  lea     rcx, [r9+18h]
0x18000f4bb  mov     r9, r8
0x18000f4be  mov     r8, rdx
0x18000f4c1  lea     rdx, ?_entries@?1??_GetEntries@CMSMQTriggerSet@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CMSMQTriggerSet::_GetEntries(void)'::`2'::_entries
0x18000f4c8  call    cs:__imp_AtlInternalQueryInterface
0x18000f4ce  mov     ebx, eax
0x18000f4d0  mov     eax, ebx
0x18000f4d2  add     rsp, 20h
0x18000f4d6  pop     rbx
0x18000f4d7  retn
```
