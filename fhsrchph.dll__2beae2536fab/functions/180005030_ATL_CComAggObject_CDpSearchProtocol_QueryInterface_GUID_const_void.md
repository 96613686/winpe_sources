# ATL::CComAggObject<CDpSearchProtocol>::QueryInterface(_GUID const &,void * *)

- ea: `0x180005030`
- end: `0x180005093`
- name: `?QueryInterface@?$CComAggObject@VCDpSearchProtocol@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: `__int64 __fastcall(char *, __int64, char **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004a5c`
- `0x180005030`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CDpSearchProtocol>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CDpSearchProtocol::_GetEntries'::`2'::_entries,
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
0x180005030  push    rbx
0x180005032  sub     rsp, 20h
0x180005036  xor     ebx, ebx
0x180005038  test    r8, r8
0x18000503b  jnz     short loc_180005044
0x18000503d  mov     eax, 80004003h
0x180005042  jmp     short loc_18000508D
0x180005044  mov     [r8], rbx
0x180005047  cmp     [rdx], ebx
0x180005049  jnz     short loc_180005073
0x18000504b  cmp     [rdx+4], ebx
0x18000504e  jnz     short loc_180005073
0x180005050  cmp     dword ptr [rdx+8], 0C0h
0x180005057  jnz     short loc_180005073
0x180005059  cmp     dword ptr [rdx+0Ch], 46000000h
0x180005060  jnz     short loc_180005073
0x180005062  mov     [r8], rcx
0x180005065  mov     rax, [rcx]
0x180005068  mov     rax, [rax+8]
0x18000506c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005071  jmp     short loc_18000508B
0x180005073  mov     r9, r8; void **
0x180005076  add     rcx, 18h; void *
0x18000507a  mov     r8, rdx; struct _GUID *
0x18000507d  lea     rdx, ?_entries@?1??_GetEntries@CDpSearchProtocol@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180005084  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180005089  mov     ebx, eax
0x18000508b  mov     eax, ebx
0x18000508d  add     rsp, 20h
0x180005091  pop     rbx
0x180005092  retn
```
