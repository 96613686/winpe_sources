# ATL::CComAggObject<CASCLOG>::QueryInterface(_GUID const &,void * *)

- ea: `0x180009e00`
- end: `0x180009e61`
- name: `?QueryInterface@?$CComAggObject@VCASCLOG@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009e00`
- `0x180010010`

## import_xrefs

- `ATL!__imp_AtlInternalQueryInterface` at `0x180009e51`
- `ATL!__imp_AtlInternalQueryInterface` at `0x180009e51`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CASCLOG>::QueryInterface(__int64 a1, _DWORD *a2, _QWORD *a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( *a2 || a2[1] || a2[2] != 192 || a2[3] != 1174405120 )
  {
    return (unsigned int)AtlInternalQueryInterface(a1 + 24, &`CASCLOG::_GetEntries'::`2'::_entries, a2, a3);
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
0x180009e00  push    rbx
0x180009e02  sub     rsp, 20h
0x180009e06  xor     ebx, ebx
0x180009e08  cmp     [rdx], ebx
0x180009e0a  jnz     short loc_180009E40
0x180009e0c  cmp     [rdx+4], ebx
0x180009e0f  jnz     short loc_180009E40
0x180009e11  cmp     dword ptr [rdx+8], 0C0h
0x180009e18  jnz     short loc_180009E40
0x180009e1a  cmp     dword ptr [rdx+0Ch], 46000000h
0x180009e21  jnz     short loc_180009E40
0x180009e23  test    r8, r8
0x180009e26  jnz     short loc_180009E2F
0x180009e28  mov     eax, 80004003h
0x180009e2d  jmp     short loc_180009E5B
0x180009e2f  mov     [r8], rcx
0x180009e32  mov     rax, [rcx]
0x180009e35  mov     rax, [rax+8]
0x180009e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e3e  jmp     short loc_180009E59
0x180009e40  mov     r9, r8
0x180009e43  add     rcx, 18h
0x180009e47  mov     r8, rdx
0x180009e4a  lea     rdx, ?_entries@?1??_GetEntries@CASCLOG@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CASCLOG::_GetEntries(void)'::`2'::_entries
0x180009e51  call    cs:__imp_AtlInternalQueryInterface
0x180009e57  mov     ebx, eax
0x180009e59  mov     eax, ebx
0x180009e5b  add     rsp, 20h
0x180009e5f  pop     rbx
0x180009e60  retn
```
