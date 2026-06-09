# ATL::CComAggObject<CGameExplorer>::QueryInterface(_GUID const &,void * *)

- ea: `0x180002280`
- end: `0x1800022da`
- name: `?QueryInterface@?$CComAggObject@VCGameExplorer@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001e28`
- `0x18000221c`
- `0x180002280`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CGameExplorer>::QueryInterface(__int64 a1, const struct _GUID *a2, _QWORD *a3)
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
                           (void *)(v7 + 24),
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CGameExplorer::_GetEntries'::`2'::_entries,
                           v5,
                           v6);
  }
  return v3;
}

```

## disassembly

```asm
0x180002280  push    rbx
0x180002282  sub     rsp, 20h
0x180002286  xor     ebx, ebx
0x180002288  mov     r9, rcx
0x18000228b  test    r8, r8
0x18000228e  jnz     short loc_180002297
0x180002290  mov     eax, 80004003h
0x180002295  jmp     short loc_1800022D4
0x180002297  mov     rcx, rdx; struct _GUID *
0x18000229a  mov     [r8], rbx
0x18000229d  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x1800022a2  test    eax, eax
0x1800022a4  jz      short loc_1800022BA
0x1800022a6  mov     [r8], r9
0x1800022a9  mov     rcx, r9
0x1800022ac  mov     rax, [r9]
0x1800022af  mov     rax, [rax+8]
0x1800022b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022b8  jmp     short loc_1800022D2
0x1800022ba  lea     rcx, [r9+18h]; void *
0x1800022be  mov     r9, r8; void **
0x1800022c1  mov     r8, rdx; struct _GUID *
0x1800022c4  lea     rdx, ?_entries@?1??_GetEntries@CGameExplorer@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800022cb  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x1800022d0  mov     ebx, eax
0x1800022d2  mov     eax, ebx
0x1800022d4  add     rsp, 20h
0x1800022d8  pop     rbx
0x1800022d9  retn
```
