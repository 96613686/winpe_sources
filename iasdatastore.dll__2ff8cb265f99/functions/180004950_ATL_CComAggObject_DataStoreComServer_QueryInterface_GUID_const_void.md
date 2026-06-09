# ATL::CComAggObject<DataStoreComServer>::QueryInterface(_GUID const &,void * *)

- ea: `0x180004950`
- end: `0x1800049b3`
- name: `?QueryInterface@?$CComAggObject@VDataStoreComServer@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004364`
- `0x180004950`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<DataStoreComServer>::QueryInterface(char *a1, __int64 a2, char **a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( *(_DWORD *)a2 || *(_DWORD *)(a2 + 4) || *(_DWORD *)(a2 + 8) != 192 || *(_DWORD *)(a2 + 12) != 1174405120 )
  {
    return (unsigned int)ATL::CComObjectRootBase::InternalQueryInterface(
                           a1 + 24,
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`DataStoreComServer::_GetEntries'::`2'::_entries,
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
0x180004950  push    rbx
0x180004952  sub     rsp, 20h
0x180004956  xor     ebx, ebx
0x180004958  test    r8, r8
0x18000495b  jnz     short loc_180004964
0x18000495d  mov     eax, 80004003h
0x180004962  jmp     short loc_1800049AD
0x180004964  mov     [r8], rbx
0x180004967  cmp     [rdx], ebx
0x180004969  jnz     short loc_180004993
0x18000496b  cmp     [rdx+4], ebx
0x18000496e  jnz     short loc_180004993
0x180004970  cmp     dword ptr [rdx+8], 0C0h
0x180004977  jnz     short loc_180004993
0x180004979  cmp     dword ptr [rdx+0Ch], 46000000h
0x180004980  jnz     short loc_180004993
0x180004982  mov     [r8], rcx
0x180004985  mov     rax, [rcx]
0x180004988  mov     rax, [rax+8]
0x18000498c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004991  jmp     short loc_1800049AB
0x180004993  mov     r9, r8; void **
0x180004996  add     rcx, 18h; void *
0x18000499a  mov     r8, rdx; struct _GUID *
0x18000499d  lea     rdx, ?_entries@?1??_GetEntries@DataStoreComServer@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800049a4  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x1800049a9  mov     ebx, eax
0x1800049ab  mov     eax, ebx
0x1800049ad  add     rsp, 20h
0x1800049b1  pop     rbx
0x1800049b2  retn
```
