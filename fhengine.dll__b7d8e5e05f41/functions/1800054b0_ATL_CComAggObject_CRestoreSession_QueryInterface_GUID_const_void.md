# ATL::CComAggObject<CRestoreSession>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800054b0`
- end: `0x18000550a`
- name: `?QueryInterface@?$CComAggObject@VCRestoreSession@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `90`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000420c`
- `0x180004f88`
- `0x1800054b0`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CRestoreSession>::QueryInterface(__int64 a1, const struct _GUID *a2, _QWORD *a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CRestoreSession::_GetEntries'::`2'::_entries,
                           v5,
                           v6);
  }
  return v3;
}

```

## disassembly

```asm
0x1800054b0  push    rbx
0x1800054b2  sub     rsp, 20h
0x1800054b6  xor     ebx, ebx
0x1800054b8  mov     r9, rcx
0x1800054bb  test    r8, r8
0x1800054be  jnz     short loc_1800054C7
0x1800054c0  mov     eax, 80004003h
0x1800054c5  jmp     short loc_180005504
0x1800054c7  mov     rcx, rdx; struct _GUID *
0x1800054ca  mov     [r8], rbx
0x1800054cd  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x1800054d2  test    eax, eax
0x1800054d4  jz      short loc_1800054EA
0x1800054d6  mov     [r8], r9
0x1800054d9  mov     rcx, r9
0x1800054dc  mov     rax, [r9]
0x1800054df  mov     rax, [rax+8]
0x1800054e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054e8  jmp     short loc_180005502
0x1800054ea  lea     rcx, [r9+18h]; void *
0x1800054ee  mov     r9, r8; void **
0x1800054f1  mov     r8, rdx; struct _GUID *
0x1800054f4  lea     rdx, ?_entries@?1??_GetEntries@CRestoreSession@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800054fb  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180005500  mov     ebx, eax
0x180005502  mov     eax, ebx
0x180005504  add     rsp, 20h
0x180005508  pop     rbx
0x180005509  retn
```
