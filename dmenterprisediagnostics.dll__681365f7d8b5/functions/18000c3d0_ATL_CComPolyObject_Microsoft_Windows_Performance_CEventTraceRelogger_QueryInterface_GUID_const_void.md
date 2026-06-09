# ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000c3d0`
- end: `0x18000c42b`
- name: `?QueryInterface@?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180009eb0`
- `0x18000afb0`
- `0x18000c3d0`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx
  const struct _GUID *v5; // rdx
  void **v6; // r8
  __int64 v7; // r9

  v3 = 0;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( (unsigned int)ATL::InlineIsEqualUnknown(a2) )
  {
    *v6 = (void *)v7;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  }
  else
  {
    return (unsigned int)ATL::AtlInternalQueryInterface(
                           (void *)(v7 + 16),
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`Microsoft::Windows::Performance::CEventTraceRelogger::_GetEntries'::`2'::_entries,
                           v5,
                           v6);
  }
  return v3;
}

```

## disassembly

```asm
0x18000c3d0  push    rbx
0x18000c3d2  sub     rsp, 20h
0x18000c3d6  xor     ebx, ebx
0x18000c3d8  mov     r9, rcx
0x18000c3db  test    r8, r8
0x18000c3de  jnz     short loc_18000C3E7
0x18000c3e0  mov     eax, 80004003h
0x18000c3e5  jmp     short loc_18000C424
0x18000c3e7  mov     rcx, rdx; struct _GUID *
0x18000c3ea  mov     [r8], rbx
0x18000c3ed  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x18000c3f2  test    eax, eax
0x18000c3f4  jz      short loc_18000C40A
0x18000c3f6  mov     [r8], r9
0x18000c3f9  mov     rcx, r9
0x18000c3fc  mov     rax, [r9]
0x18000c3ff  mov     rax, [rax+8]
0x18000c403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c408  jmp     short loc_18000C422
0x18000c40a  lea     rcx, [r9+10h]; void *
0x18000c40e  mov     r9, r8; void **
0x18000c411  mov     r8, rdx; struct _GUID *
0x18000c414  lea     rdx, ?_entries@?1??_GetEntries@CEventTraceRelogger@Performance@Windows@Microsoft@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU67@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000c41b  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x18000c420  mov     ebx, eax
0x18000c422  mov     eax, ebx
0x18000c424  add     rsp, 20h
0x18000c428  pop     rbx
0x18000c429  retn
```
