# ATL::CComAggObject<CAccClientDocMgr>::QueryInterface(_GUID const &,void * *)

- ea: `0x180010600`
- end: `0x180010660`
- name: `?QueryInterface@?$CComAggObject@VCAccClientDocMgr@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800093d0`
- `0x180010600`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CAccClientDocMgr>::QueryInterface(char *a1, __int64 a2, char **a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( *(_DWORD *)a2 || *(_DWORD *)(a2 + 4) || *(_DWORD *)(a2 + 8) != 192 || *(_DWORD *)(a2 + 12) != 1174405120 )
  {
    return (unsigned int)ATL::CComObjectRootBase::InternalQueryInterface(
                           a1 + 16,
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CAccClientDocMgr::_GetEntries'::`2'::_entries,
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
0x180010600  push    rbx
0x180010602  sub     rsp, 20h
0x180010606  xor     ebx, ebx
0x180010608  cmp     [rdx], ebx
0x18001060a  jnz     short loc_180010640
0x18001060c  cmp     [rdx+4], ebx
0x18001060f  jnz     short loc_180010640
0x180010611  cmp     dword ptr [rdx+8], 0C0h
0x180010618  jnz     short loc_180010640
0x18001061a  cmp     dword ptr [rdx+0Ch], 46000000h
0x180010621  jnz     short loc_180010640
0x180010623  test    r8, r8
0x180010626  jnz     short loc_18001062F
0x180010628  mov     eax, 80004003h
0x18001062d  jmp     short loc_18001065A
0x18001062f  mov     [r8], rcx
0x180010632  mov     rax, [rcx]
0x180010635  mov     rax, [rax+8]
0x180010639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001063e  jmp     short loc_180010658
0x180010640  mov     r9, r8; void **
0x180010643  add     rcx, 10h; void *
0x180010647  mov     r8, rdx; struct _GUID *
0x18001064a  lea     rdx, ?_entries@?1??_GetEntries@CAccClientDocMgr@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180010651  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180010656  mov     ebx, eax
0x180010658  mov     eax, ebx
0x18001065a  add     rsp, 20h
0x18001065e  pop     rbx
0x18001065f  retn
```
