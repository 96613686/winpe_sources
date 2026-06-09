# ATL::CComAggObject<CDict>::QueryInterface(_GUID const &,void * *)

- ea: `0x180010750`
- end: `0x1800107b0`
- name: `?QueryInterface@?$CComAggObject@VCDict@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800093d0`
- `0x180010750`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CDict>::QueryInterface(char *a1, __int64 a2, char **a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( *(_DWORD *)a2 || *(_DWORD *)(a2 + 4) || *(_DWORD *)(a2 + 8) != 192 || *(_DWORD *)(a2 + 12) != 1174405120 )
  {
    return (unsigned int)ATL::CComObjectRootBase::InternalQueryInterface(
                           a1 + 16,
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CDict::_GetEntries'::`2'::_entries,
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
0x180010750  push    rbx
0x180010752  sub     rsp, 20h
0x180010756  xor     ebx, ebx
0x180010758  cmp     [rdx], ebx
0x18001075a  jnz     short loc_180010790
0x18001075c  cmp     [rdx+4], ebx
0x18001075f  jnz     short loc_180010790
0x180010761  cmp     dword ptr [rdx+8], 0C0h
0x180010768  jnz     short loc_180010790
0x18001076a  cmp     dword ptr [rdx+0Ch], 46000000h
0x180010771  jnz     short loc_180010790
0x180010773  test    r8, r8
0x180010776  jnz     short loc_18001077F
0x180010778  mov     eax, 80004003h
0x18001077d  jmp     short loc_1800107AA
0x18001077f  mov     [r8], rcx
0x180010782  mov     rax, [rcx]
0x180010785  mov     rax, [rax+8]
0x180010789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001078e  jmp     short loc_1800107A8
0x180010790  mov     r9, r8; void **
0x180010793  add     rcx, 10h; void *
0x180010797  mov     r8, rdx; struct _GUID *
0x18001079a  lea     rdx, ?_entries@?1??_GetEntries@CDict@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800107a1  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x1800107a6  mov     ebx, eax
0x1800107a8  mov     eax, ebx
0x1800107aa  add     rsp, 20h
0x1800107ae  pop     rbx
0x1800107af  retn
```
