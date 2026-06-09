# ATL::CComAggObject<CAdvancedConfig>::QueryInterface(_GUID const &,void * *)

- ea: `0x180004c70`
- end: `0x180004cd3`
- name: `?QueryInterface@?$CComAggObject@VCAdvancedConfig@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004684`
- `0x180004c70`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CAdvancedConfig>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CAdvancedConfig::_GetEntries'::`2'::_entries,
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
0x180004c70  push    rbx
0x180004c72  sub     rsp, 20h
0x180004c76  xor     ebx, ebx
0x180004c78  test    r8, r8
0x180004c7b  jnz     short loc_180004C84
0x180004c7d  mov     eax, 80004003h
0x180004c82  jmp     short loc_180004CCD
0x180004c84  mov     [r8], rbx
0x180004c87  cmp     [rdx], ebx
0x180004c89  jnz     short loc_180004CB3
0x180004c8b  cmp     [rdx+4], ebx
0x180004c8e  jnz     short loc_180004CB3
0x180004c90  cmp     dword ptr [rdx+8], 0C0h
0x180004c97  jnz     short loc_180004CB3
0x180004c99  cmp     dword ptr [rdx+0Ch], 46000000h
0x180004ca0  jnz     short loc_180004CB3
0x180004ca2  mov     [r8], rcx
0x180004ca5  mov     rax, [rcx]
0x180004ca8  mov     rax, [rax+8]
0x180004cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cb1  jmp     short loc_180004CCB
0x180004cb3  mov     r9, r8; void **
0x180004cb6  add     rcx, 18h; void *
0x180004cba  mov     r8, rdx; struct _GUID *
0x180004cbd  lea     rdx, ?_entries@?1??_GetEntries@CAdvancedConfig@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180004cc4  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180004cc9  mov     ebx, eax
0x180004ccb  mov     eax, ebx
0x180004ccd  add     rsp, 20h
0x180004cd1  pop     rbx
0x180004cd2  retn
```
