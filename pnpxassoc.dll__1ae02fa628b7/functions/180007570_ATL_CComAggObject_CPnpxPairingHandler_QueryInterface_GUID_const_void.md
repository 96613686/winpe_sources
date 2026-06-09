# ATL::CComAggObject<CPnpxPairingHandler>::QueryInterface(_GUID const &,void * *)

- ea: `0x180007570`
- end: `0x1800075d3`
- name: `?QueryInterface@?$CComAggObject@VCPnpxPairingHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006f94`
- `0x180007570`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CPnpxPairingHandler>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CPnpxPairingHandler::_GetEntries'::`2'::_entries,
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
0x180007570  push    rbx
0x180007572  sub     rsp, 20h
0x180007576  xor     ebx, ebx
0x180007578  test    r8, r8
0x18000757b  jnz     short loc_180007584
0x18000757d  mov     eax, 80004003h
0x180007582  jmp     short loc_1800075CD
0x180007584  mov     [r8], rbx
0x180007587  cmp     [rdx], ebx
0x180007589  jnz     short loc_1800075B3
0x18000758b  cmp     [rdx+4], ebx
0x18000758e  jnz     short loc_1800075B3
0x180007590  cmp     dword ptr [rdx+8], 0C0h
0x180007597  jnz     short loc_1800075B3
0x180007599  cmp     dword ptr [rdx+0Ch], 46000000h
0x1800075a0  jnz     short loc_1800075B3
0x1800075a2  mov     [r8], rcx
0x1800075a5  mov     rax, [rcx]
0x1800075a8  mov     rax, [rax+8]
0x1800075ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075b1  jmp     short loc_1800075CB
0x1800075b3  mov     r9, r8; void **
0x1800075b6  add     rcx, 18h; void *
0x1800075ba  mov     r8, rdx; struct _GUID *
0x1800075bd  lea     rdx, ?_entries@?1??_GetEntries@CPnpxPairingHandler@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800075c4  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x1800075c9  mov     ebx, eax
0x1800075cb  mov     eax, ebx
0x1800075cd  add     rsp, 20h
0x1800075d1  pop     rbx
0x1800075d2  retn
```
