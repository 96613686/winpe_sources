# ATL::CComAggObject<CExtractIcon>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800049d0`
- end: `0x180004a30`
- name: `?QueryInterface@?$CComAggObject@VCExtractIcon@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000410c`
- `0x1800049d0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CExtractIcon>::QueryInterface(char *a1, __int64 a2, char **a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( *(_DWORD *)a2 || *(_DWORD *)(a2 + 4) || *(_DWORD *)(a2 + 8) != 192 || *(_DWORD *)(a2 + 12) != 1174405120 )
  {
    return (unsigned int)ATL::CComObjectRootBase::InternalQueryInterface(
                           a1 + 16,
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CExtractIcon::_GetEntries'::`2'::_entries,
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
0x1800049d0  push    rbx
0x1800049d2  sub     rsp, 20h
0x1800049d6  xor     ebx, ebx
0x1800049d8  cmp     [rdx], ebx
0x1800049da  jnz     short loc_180004A10
0x1800049dc  cmp     [rdx+4], ebx
0x1800049df  jnz     short loc_180004A10
0x1800049e1  cmp     dword ptr [rdx+8], 0C0h
0x1800049e8  jnz     short loc_180004A10
0x1800049ea  cmp     dword ptr [rdx+0Ch], 46000000h
0x1800049f1  jnz     short loc_180004A10
0x1800049f3  test    r8, r8
0x1800049f6  jnz     short loc_1800049FF
0x1800049f8  mov     eax, 80004003h
0x1800049fd  jmp     short loc_180004A2A
0x1800049ff  mov     [r8], rcx
0x180004a02  mov     rax, [rcx]
0x180004a05  mov     rax, [rax+8]
0x180004a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a0e  jmp     short loc_180004A28
0x180004a10  mov     r9, r8; void **
0x180004a13  add     rcx, 10h; void *
0x180004a17  mov     r8, rdx; struct _GUID *
0x180004a1a  lea     rdx, ?_entries@?1??_GetEntries@CExtractIcon@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180004a21  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180004a26  mov     ebx, eax
0x180004a28  mov     eax, ebx
0x180004a2a  add     rsp, 20h
0x180004a2e  pop     rbx
0x180004a2f  retn
```
