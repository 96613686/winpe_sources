# ATL::CComAggObject<CAccStore>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800106e0`
- end: `0x180010740`
- name: `?QueryInterface@?$CComAggObject@VCAccStore@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800093d0`
- `0x1800106e0`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CAccStore>::QueryInterface(char *a1, __int64 a2, char **a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( *(_DWORD *)a2 || *(_DWORD *)(a2 + 4) || *(_DWORD *)(a2 + 8) != 192 || *(_DWORD *)(a2 + 12) != 1174405120 )
  {
    return (unsigned int)ATL::CComObjectRootBase::InternalQueryInterface(
                           a1 + 16,
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CAccStore::_GetEntries'::`2'::_entries,
                           (const struct _GUID *)a2,
                           a3);
  }
  else
  {
    if ( !a3 )
      return 2147500035LL;
    *a3 = a1;
    (*(void (__fastcall **)(char *))(*(_QWORD *)a1 + 8LL))(a1);
  }
  return v3;
}

```

## disassembly

```asm
0x1800106e0  push    rbx
0x1800106e2  sub     rsp, 20h
0x1800106e6  xor     ebx, ebx
0x1800106e8  cmp     [rdx], ebx
0x1800106ea  jnz     short loc_180010720
0x1800106ec  cmp     [rdx+4], ebx
0x1800106ef  jnz     short loc_180010720
0x1800106f1  cmp     dword ptr [rdx+8], 0C0h
0x1800106f8  jnz     short loc_180010720
0x1800106fa  cmp     dword ptr [rdx+0Ch], 46000000h
0x180010701  jnz     short loc_180010720
0x180010703  test    r8, r8
0x180010706  jnz     short loc_18001070F
0x180010708  mov     eax, 80004003h
0x18001070d  jmp     short loc_18001073A
0x18001070f  mov     [r8], rcx
0x180010712  mov     rax, [rcx]
0x180010715  mov     rax, [rax+8]
0x180010719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001071e  jmp     short loc_180010738
0x180010720  mov     r9, r8; void **
0x180010723  add     rcx, 10h; void *
0x180010727  mov     r8, rdx; struct _GUID *
0x18001072a  lea     rdx, ?_entries@?1??_GetEntries@CAccStore@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180010731  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180010736  mov     ebx, eax
0x180010738  mov     eax, ebx
0x18001073a  add     rsp, 20h
0x18001073e  pop     rbx
0x18001073f  retn
```
