# ATL::CComAggObject<CDocWrap>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800107c0`
- end: `0x180010820`
- name: `?QueryInterface@?$CComAggObject@VCDocWrap@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800093d0`
- `0x1800107c0`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CDocWrap>::QueryInterface(char *a1, __int64 a2, char **a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( *(_DWORD *)a2 || *(_DWORD *)(a2 + 4) || *(_DWORD *)(a2 + 8) != 192 || *(_DWORD *)(a2 + 12) != 1174405120 )
  {
    return (unsigned int)ATL::CComObjectRootBase::InternalQueryInterface(
                           a1 + 16,
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CDocWrap::_GetEntries'::`2'::_entries,
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
0x1800107c0  push    rbx
0x1800107c2  sub     rsp, 20h
0x1800107c6  xor     ebx, ebx
0x1800107c8  cmp     [rdx], ebx
0x1800107ca  jnz     short loc_180010800
0x1800107cc  cmp     [rdx+4], ebx
0x1800107cf  jnz     short loc_180010800
0x1800107d1  cmp     dword ptr [rdx+8], 0C0h
0x1800107d8  jnz     short loc_180010800
0x1800107da  cmp     dword ptr [rdx+0Ch], 46000000h
0x1800107e1  jnz     short loc_180010800
0x1800107e3  test    r8, r8
0x1800107e6  jnz     short loc_1800107EF
0x1800107e8  mov     eax, 80004003h
0x1800107ed  jmp     short loc_18001081A
0x1800107ef  mov     [r8], rcx
0x1800107f2  mov     rax, [rcx]
0x1800107f5  mov     rax, [rax+8]
0x1800107f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107fe  jmp     short loc_180010818
0x180010800  mov     r9, r8; void **
0x180010803  add     rcx, 10h; void *
0x180010807  mov     r8, rdx; struct _GUID *
0x18001080a  lea     rdx, ?_entries@?1??_GetEntries@CDocWrap@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180010811  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180010816  mov     ebx, eax
0x180010818  mov     eax, ebx
0x18001081a  add     rsp, 20h
0x18001081e  pop     rbx
0x18001081f  retn
```
