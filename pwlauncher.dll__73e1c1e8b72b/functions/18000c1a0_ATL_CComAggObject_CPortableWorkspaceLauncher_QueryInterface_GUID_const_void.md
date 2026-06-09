# ATL::CComAggObject<CPortableWorkspaceLauncher>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000c1a0`
- end: `0x18000c203`
- name: `?QueryInterface@?$CComAggObject@VCPortableWorkspaceLauncher@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: `__int64 __fastcall(char *, __int64, char **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000c048`
- `0x18000c1a0`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CPortableWorkspaceLauncher>::QueryInterface(char *a1, __int64 a2, char **a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( *(_DWORD *)a2 || *(_DWORD *)(a2 + 4) || *(_DWORD *)(a2 + 8) != 192 || *(_DWORD *)(a2 + 12) != 1174405120 )
  {
    return (unsigned int)ATL::CComObjectRootBase::InternalQueryInterface(
                           a1 + 16,
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CPortableWorkspaceLauncher::_GetEntries'::`2'::_entries,
                           (const struct _GUID *)a2,
                           a3);
  }
  else
  {
    *a3 = a1;
    (*(void (__fastcall **)(char *))(*(_QWORD *)a1 + 8LL))(a1);
  }
  return v3;
}

```

## disassembly

```asm
0x18000c1a0  push    rbx
0x18000c1a2  sub     rsp, 20h
0x18000c1a6  xor     ebx, ebx
0x18000c1a8  test    r8, r8
0x18000c1ab  jnz     short loc_18000C1B4
0x18000c1ad  mov     eax, 80004003h
0x18000c1b2  jmp     short loc_18000C1FD
0x18000c1b4  mov     [r8], rbx
0x18000c1b7  cmp     [rdx], ebx
0x18000c1b9  jnz     short loc_18000C1E3
0x18000c1bb  cmp     [rdx+4], ebx
0x18000c1be  jnz     short loc_18000C1E3
0x18000c1c0  cmp     dword ptr [rdx+8], 0C0h
0x18000c1c7  jnz     short loc_18000C1E3
0x18000c1c9  cmp     dword ptr [rdx+0Ch], 46000000h
0x18000c1d0  jnz     short loc_18000C1E3
0x18000c1d2  mov     [r8], rcx
0x18000c1d5  mov     rax, [rcx]
0x18000c1d8  mov     rax, [rax+8]
0x18000c1dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1e1  jmp     short loc_18000C1FB
0x18000c1e3  mov     r9, r8; void **
0x18000c1e6  add     rcx, 10h; void *
0x18000c1ea  mov     r8, rdx; struct _GUID *
0x18000c1ed  lea     rdx, ?_entries@?1??_GetEntries@CPortableWorkspaceLauncher@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000c1f4  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x18000c1f9  mov     ebx, eax
0x18000c1fb  mov     eax, ebx
0x18000c1fd  add     rsp, 20h
0x18000c201  pop     rbx
0x18000c202  retn
```
