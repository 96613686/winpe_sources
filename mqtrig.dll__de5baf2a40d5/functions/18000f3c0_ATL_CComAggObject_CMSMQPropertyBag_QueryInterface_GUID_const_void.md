# ATL::CComAggObject<CMSMQPropertyBag>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000f3c0`
- end: `0x18000f418`
- name: `?QueryInterface@?$CComAggObject@VCMSMQPropertyBag@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `88`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000ed70`
- `0x18000f3c0`
- `0x180022010`

## import_xrefs

- `ATL!__imp_AtlInternalQueryInterface` at `0x18000f408`
- `ATL!__imp_AtlInternalQueryInterface` at `0x18000f408`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMSMQPropertyBag>::QueryInterface(__int64 a1, const struct _GUID *a2)
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
    return (unsigned int)AtlInternalQueryInterface(v4 + 16, &`CMSMQPropertyBag::_GetEntries'::`2'::_entries, v2, v3);
  }
  return v6;
}

```

## disassembly

```asm
0x18000f3c0  push    rbx
0x18000f3c2  sub     rsp, 20h
0x18000f3c6  mov     r9, rcx
0x18000f3c9  mov     rcx, rdx; struct _GUID *
0x18000f3cc  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x18000f3d1  test    eax, eax
0x18000f3d3  jz      short loc_18000F3F7
0x18000f3d5  test    r8, r8
0x18000f3d8  jnz     short loc_18000F3E1
0x18000f3da  mov     eax, 80004003h
0x18000f3df  jmp     short loc_18000F412
0x18000f3e1  mov     [r8], r9
0x18000f3e4  xor     ebx, ebx
0x18000f3e6  mov     rax, [r9]
0x18000f3e9  mov     rcx, r9
0x18000f3ec  mov     rax, [rax+8]
0x18000f3f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3f5  jmp     short loc_18000F410
0x18000f3f7  lea     rcx, [r9+10h]
0x18000f3fb  mov     r9, r8
0x18000f3fe  mov     r8, rdx
0x18000f401  lea     rdx, ?_entries@?1??_GetEntries@CMSMQPropertyBag@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CMSMQPropertyBag::_GetEntries(void)'::`2'::_entries
0x18000f408  call    cs:__imp_AtlInternalQueryInterface
0x18000f40e  mov     ebx, eax
0x18000f410  mov     eax, ebx
0x18000f412  add     rsp, 20h
0x18000f416  pop     rbx
0x18000f417  retn
```
