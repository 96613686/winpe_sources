# ATL::CComAggObject<CServicingSession>::QueryInterface(_GUID const &,void * *)

- ea: `0x180005510`
- end: `0x18000556a`
- name: `?QueryInterface@?$CComAggObject@VCServicingSession@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `90`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000420c`
- `0x180004f88`
- `0x180005510`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CServicingSession>::QueryInterface(
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
                           (void *)(v7 + 24),
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CServicingSession::_GetEntries'::`2'::_entries,
                           v5,
                           v6);
  }
  return v3;
}

```

## disassembly

```asm
0x180005510  push    rbx
0x180005512  sub     rsp, 20h
0x180005516  xor     ebx, ebx
0x180005518  mov     r9, rcx
0x18000551b  test    r8, r8
0x18000551e  jnz     short loc_180005527
0x180005520  mov     eax, 80004003h
0x180005525  jmp     short loc_180005564
0x180005527  mov     rcx, rdx; struct _GUID *
0x18000552a  mov     [r8], rbx
0x18000552d  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x180005532  test    eax, eax
0x180005534  jz      short loc_18000554A
0x180005536  mov     [r8], r9
0x180005539  mov     rcx, r9
0x18000553c  mov     rax, [r9]
0x18000553f  mov     rax, [rax+8]
0x180005543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005548  jmp     short loc_180005562
0x18000554a  lea     rcx, [r9+18h]; void *
0x18000554e  mov     r9, r8; void **
0x180005551  mov     r8, rdx; struct _GUID *
0x180005554  lea     rdx, ?_entries@?1??_GetEntries@CServicingSession@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000555b  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180005560  mov     ebx, eax
0x180005562  mov     eax, ebx
0x180005564  add     rsp, 20h
0x180005568  pop     rbx
0x180005569  retn
```
