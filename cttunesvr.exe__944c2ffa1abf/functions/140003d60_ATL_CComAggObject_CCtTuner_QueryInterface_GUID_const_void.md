# ATL::CComAggObject<CCtTuner>::QueryInterface(_GUID const &,void * *)

- ea: `0x140003d60`
- end: `0x140003dc3`
- name: `?QueryInterface@?$CComAggObject@VCCtTuner@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140003564`
- `0x140003d60`
- `0x140007010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CCtTuner>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CCtTuner::_GetEntries'::`2'::_entries,
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
0x140003d60  push    rbx
0x140003d62  sub     rsp, 20h
0x140003d66  xor     ebx, ebx
0x140003d68  test    r8, r8
0x140003d6b  jnz     short loc_140003D74
0x140003d6d  mov     eax, 80004003h
0x140003d72  jmp     short loc_140003DBD
0x140003d74  mov     [r8], rbx
0x140003d77  cmp     [rdx], ebx
0x140003d79  jnz     short loc_140003DA3
0x140003d7b  cmp     [rdx+4], ebx
0x140003d7e  jnz     short loc_140003DA3
0x140003d80  cmp     dword ptr [rdx+8], 0C0h
0x140003d87  jnz     short loc_140003DA3
0x140003d89  cmp     dword ptr [rdx+0Ch], 46000000h
0x140003d90  jnz     short loc_140003DA3
0x140003d92  mov     [r8], rcx
0x140003d95  mov     rax, [rcx]
0x140003d98  mov     rax, [rax+8]
0x140003d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003da1  jmp     short loc_140003DBB
0x140003da3  mov     r9, r8; void **
0x140003da6  add     rcx, 10h; void *
0x140003daa  mov     r8, rdx; struct _GUID *
0x140003dad  lea     rdx, ?_entries@?1??_GetEntries@CCtTuner@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x140003db4  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x140003db9  mov     ebx, eax
0x140003dbb  mov     eax, ebx
0x140003dbd  add     rsp, 20h
0x140003dc1  pop     rbx
0x140003dc2  retn
```
