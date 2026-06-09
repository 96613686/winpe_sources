# ATL::CComAggObject<CRehydrationTaskHandler>::QueryInterface(_GUID const &,void * *)

- ea: `0x180003fd0`
- end: `0x180004033`
- name: `?QueryInterface@?$CComAggObject@VCRehydrationTaskHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: `__int64 __fastcall(char *, __int64, char **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800039f4`
- `0x180003fd0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CRehydrationTaskHandler>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CRehydrationTaskHandler::_GetEntries'::`2'::_entries,
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
0x180003fd0  push    rbx
0x180003fd2  sub     rsp, 20h
0x180003fd6  xor     ebx, ebx
0x180003fd8  test    r8, r8
0x180003fdb  jnz     short loc_180003FE4
0x180003fdd  mov     eax, 80004003h
0x180003fe2  jmp     short loc_18000402D
0x180003fe4  mov     [r8], rbx
0x180003fe7  cmp     [rdx], ebx
0x180003fe9  jnz     short loc_180004013
0x180003feb  cmp     [rdx+4], ebx
0x180003fee  jnz     short loc_180004013
0x180003ff0  cmp     dword ptr [rdx+8], 0C0h
0x180003ff7  jnz     short loc_180004013
0x180003ff9  cmp     dword ptr [rdx+0Ch], 46000000h
0x180004000  jnz     short loc_180004013
0x180004002  mov     [r8], rcx
0x180004005  mov     rax, [rcx]
0x180004008  mov     rax, [rax+8]
0x18000400c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004011  jmp     short loc_18000402B
0x180004013  mov     r9, r8; void **
0x180004016  add     rcx, 18h; void *
0x18000401a  mov     r8, rdx; struct _GUID *
0x18000401d  lea     rdx, ?_entries@?1??_GetEntries@CRehydrationTaskHandler@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180004024  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180004029  mov     ebx, eax
0x18000402b  mov     eax, ebx
0x18000402d  add     rsp, 20h
0x180004031  pop     rbx
0x180004032  retn
```
