# ATL::CComAggObject<CHHCollectionWrapper>::QueryInterface(_GUID const &,void * *)

- ea: `0x180004a40`
- end: `0x180004aa0`
- name: `?QueryInterface@?$CComAggObject@VCHHCollectionWrapper@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000410c`
- `0x180004a40`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CHHCollectionWrapper>::QueryInterface(char *a1, __int64 a2, char **a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( *(_DWORD *)a2 || *(_DWORD *)(a2 + 4) || *(_DWORD *)(a2 + 8) != 192 || *(_DWORD *)(a2 + 12) != 1174405120 )
  {
    return (unsigned int)ATL::CComObjectRootBase::InternalQueryInterface(
                           a1 + 16,
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CHHCollectionWrapper::_GetEntries'::`2'::_entries,
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
0x180004a40  push    rbx
0x180004a42  sub     rsp, 20h
0x180004a46  xor     ebx, ebx
0x180004a48  cmp     [rdx], ebx
0x180004a4a  jnz     short loc_180004A80
0x180004a4c  cmp     [rdx+4], ebx
0x180004a4f  jnz     short loc_180004A80
0x180004a51  cmp     dword ptr [rdx+8], 0C0h
0x180004a58  jnz     short loc_180004A80
0x180004a5a  cmp     dword ptr [rdx+0Ch], 46000000h
0x180004a61  jnz     short loc_180004A80
0x180004a63  test    r8, r8
0x180004a66  jnz     short loc_180004A6F
0x180004a68  mov     eax, 80004003h
0x180004a6d  jmp     short loc_180004A9A
0x180004a6f  mov     [r8], rcx
0x180004a72  mov     rax, [rcx]
0x180004a75  mov     rax, [rax+8]
0x180004a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a7e  jmp     short loc_180004A98
0x180004a80  mov     r9, r8; void **
0x180004a83  add     rcx, 10h; void *
0x180004a87  mov     r8, rdx; struct _GUID *
0x180004a8a  lea     rdx, ?_entries@?1??_GetEntries@CHHCollectionWrapper@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180004a91  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180004a96  mov     ebx, eax
0x180004a98  mov     eax, ebx
0x180004a9a  add     rsp, 20h
0x180004a9e  pop     rbx
0x180004a9f  retn
```
