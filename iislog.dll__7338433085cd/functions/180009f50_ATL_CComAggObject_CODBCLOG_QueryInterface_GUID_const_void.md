# ATL::CComAggObject<CODBCLOG>::QueryInterface(_GUID const &,void * *)

- ea: `0x180009f50`
- end: `0x180009fb1`
- name: `?QueryInterface@?$CComAggObject@VCODBCLOG@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009f50`
- `0x180010010`

## import_xrefs

- `ATL!__imp_AtlInternalQueryInterface` at `0x180009fa1`
- `ATL!__imp_AtlInternalQueryInterface` at `0x180009fa1`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CODBCLOG>::QueryInterface(__int64 a1, _DWORD *a2, _QWORD *a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( *a2 || a2[1] || a2[2] != 192 || a2[3] != 1174405120 )
  {
    return (unsigned int)AtlInternalQueryInterface(a1 + 24, &`CODBCLOG::_GetEntries'::`2'::_entries, a2, a3);
  }
  else
  {
    if ( !a3 )
      return 2147500035LL;
    *a3 = a1;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  }
  return v3;
}

```

## disassembly

```asm
0x180009f50  push    rbx
0x180009f52  sub     rsp, 20h
0x180009f56  xor     ebx, ebx
0x180009f58  cmp     [rdx], ebx
0x180009f5a  jnz     short loc_180009F90
0x180009f5c  cmp     [rdx+4], ebx
0x180009f5f  jnz     short loc_180009F90
0x180009f61  cmp     dword ptr [rdx+8], 0C0h
0x180009f68  jnz     short loc_180009F90
0x180009f6a  cmp     dword ptr [rdx+0Ch], 46000000h
0x180009f71  jnz     short loc_180009F90
0x180009f73  test    r8, r8
0x180009f76  jnz     short loc_180009F7F
0x180009f78  mov     eax, 80004003h
0x180009f7d  jmp     short loc_180009FAB
0x180009f7f  mov     [r8], rcx
0x180009f82  mov     rax, [rcx]
0x180009f85  mov     rax, [rax+8]
0x180009f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f8e  jmp     short loc_180009FA9
0x180009f90  mov     r9, r8
0x180009f93  add     rcx, 18h
0x180009f97  mov     r8, rdx
0x180009f9a  lea     rdx, ?_entries@?1??_GetEntries@CODBCLOG@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CODBCLOG::_GetEntries(void)'::`2'::_entries
0x180009fa1  call    cs:__imp_AtlInternalQueryInterface
0x180009fa7  mov     ebx, eax
0x180009fa9  mov     eax, ebx
0x180009fab  add     rsp, 20h
0x180009faf  pop     rbx
0x180009fb0  retn
```
