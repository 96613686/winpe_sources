# ATL::CComAggObject<CBackupSession>::QueryInterface(_GUID const &,void * *)

- ea: `0x180005450`
- end: `0x1800054aa`
- name: `?QueryInterface@?$CComAggObject@VCBackupSession@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `90`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000420c`
- `0x180004f88`
- `0x180005450`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CBackupSession>::QueryInterface(__int64 a1, const struct _GUID *a2, _QWORD *a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CBackupSession::_GetEntries'::`2'::_entries,
                           v5,
                           v6);
  }
  return v3;
}

```

## disassembly

```asm
0x180005450  push    rbx
0x180005452  sub     rsp, 20h
0x180005456  xor     ebx, ebx
0x180005458  mov     r9, rcx
0x18000545b  test    r8, r8
0x18000545e  jnz     short loc_180005467
0x180005460  mov     eax, 80004003h
0x180005465  jmp     short loc_1800054A4
0x180005467  mov     rcx, rdx; struct _GUID *
0x18000546a  mov     [r8], rbx
0x18000546d  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x180005472  test    eax, eax
0x180005474  jz      short loc_18000548A
0x180005476  mov     [r8], r9
0x180005479  mov     rcx, r9
0x18000547c  mov     rax, [r9]
0x18000547f  mov     rax, [rax+8]
0x180005483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005488  jmp     short loc_1800054A2
0x18000548a  lea     rcx, [r9+18h]; void *
0x18000548e  mov     r9, r8; void **
0x180005491  mov     r8, rdx; struct _GUID *
0x180005494  lea     rdx, ?_entries@?1??_GetEntries@CBackupSession@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000549b  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x1800054a0  mov     ebx, eax
0x1800054a2  mov     eax, ebx
0x1800054a4  add     rsp, 20h
0x1800054a8  pop     rbx
0x1800054a9  retn
```
