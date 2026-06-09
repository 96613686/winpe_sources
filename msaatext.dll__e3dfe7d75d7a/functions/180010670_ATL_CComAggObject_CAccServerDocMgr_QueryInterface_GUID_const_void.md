# ATL::CComAggObject<CAccServerDocMgr>::QueryInterface(_GUID const &,void * *)

- ea: `0x180010670`
- end: `0x1800106d0`
- name: `?QueryInterface@?$CComAggObject@VCAccServerDocMgr@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800093d0`
- `0x180010670`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CAccServerDocMgr>::QueryInterface(char *a1, __int64 a2, char **a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( *(_DWORD *)a2 || *(_DWORD *)(a2 + 4) || *(_DWORD *)(a2 + 8) != 192 || *(_DWORD *)(a2 + 12) != 1174405120 )
  {
    return (unsigned int)ATL::CComObjectRootBase::InternalQueryInterface(
                           a1 + 16,
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CAccServerDocMgr::_GetEntries'::`2'::_entries,
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
0x180010670  push    rbx
0x180010672  sub     rsp, 20h
0x180010676  xor     ebx, ebx
0x180010678  cmp     [rdx], ebx
0x18001067a  jnz     short loc_1800106B0
0x18001067c  cmp     [rdx+4], ebx
0x18001067f  jnz     short loc_1800106B0
0x180010681  cmp     dword ptr [rdx+8], 0C0h
0x180010688  jnz     short loc_1800106B0
0x18001068a  cmp     dword ptr [rdx+0Ch], 46000000h
0x180010691  jnz     short loc_1800106B0
0x180010693  test    r8, r8
0x180010696  jnz     short loc_18001069F
0x180010698  mov     eax, 80004003h
0x18001069d  jmp     short loc_1800106CA
0x18001069f  mov     [r8], rcx
0x1800106a2  mov     rax, [rcx]
0x1800106a5  mov     rax, [rax+8]
0x1800106a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106ae  jmp     short loc_1800106C8
0x1800106b0  mov     r9, r8; void **
0x1800106b3  add     rcx, 10h; void *
0x1800106b7  mov     r8, rdx; struct _GUID *
0x1800106ba  lea     rdx, ?_entries@?1??_GetEntries@CAccServerDocMgr@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800106c1  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x1800106c6  mov     ebx, eax
0x1800106c8  mov     eax, ebx
0x1800106ca  add     rsp, 20h
0x1800106ce  pop     rbx
0x1800106cf  retn
```
