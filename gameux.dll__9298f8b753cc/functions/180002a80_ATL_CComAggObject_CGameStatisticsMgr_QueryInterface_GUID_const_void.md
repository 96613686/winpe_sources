# ATL::CComAggObject<CGameStatisticsMgr>::QueryInterface(_GUID const &,void * *)

- ea: `0x180002a80`
- end: `0x180002ada`
- name: `?QueryInterface@?$CComAggObject@VCGameStatisticsMgr@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001e28`
- `0x18000221c`
- `0x180002a80`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CGameStatisticsMgr>::QueryInterface(
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CGameStatisticsMgr::_GetEntries'::`2'::_entries,
                           v5,
                           v6);
  }
  return v3;
}

```

## disassembly

```asm
0x180002a80  push    rbx
0x180002a82  sub     rsp, 20h
0x180002a86  xor     ebx, ebx
0x180002a88  mov     r9, rcx
0x180002a8b  test    r8, r8
0x180002a8e  jnz     short loc_180002A97
0x180002a90  mov     eax, 80004003h
0x180002a95  jmp     short loc_180002AD4
0x180002a97  mov     rcx, rdx; struct _GUID *
0x180002a9a  mov     [r8], rbx
0x180002a9d  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x180002aa2  test    eax, eax
0x180002aa4  jz      short loc_180002ABA
0x180002aa6  mov     [r8], r9
0x180002aa9  mov     rcx, r9
0x180002aac  mov     rax, [r9]
0x180002aaf  mov     rax, [rax+8]
0x180002ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ab8  jmp     short loc_180002AD2
0x180002aba  lea     rcx, [r9+10h]; void *
0x180002abe  mov     r9, r8; void **
0x180002ac1  mov     r8, rdx; struct _GUID *
0x180002ac4  lea     rdx, ?_entries@?1??_GetEntries@CGameStatisticsMgr@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180002acb  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180002ad0  mov     ebx, eax
0x180002ad2  mov     eax, ebx
0x180002ad4  add     rsp, 20h
0x180002ad8  pop     rbx
0x180002ad9  retn
```
