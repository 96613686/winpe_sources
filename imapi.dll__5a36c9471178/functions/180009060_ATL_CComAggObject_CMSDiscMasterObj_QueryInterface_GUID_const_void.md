# ATL::CComAggObject<CMSDiscMasterObj>::QueryInterface(_GUID const &,void * *)

- ea: `0x180009060`
- end: `0x1800090c3`
- name: `?QueryInterface@?$CComAggObject@VCMSDiscMasterObj@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002f84`
- `0x180009060`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMSDiscMasterObj>::QueryInterface(char *a1, __int64 a2, char **a3)
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
                           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CMSDiscMasterObj::_GetEntries'::`2'::_entries,
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
0x180009060  push    rbx
0x180009062  sub     rsp, 20h
0x180009066  xor     ebx, ebx
0x180009068  test    r8, r8
0x18000906b  jnz     short loc_180009074
0x18000906d  mov     eax, 80004003h
0x180009072  jmp     short loc_1800090BD
0x180009074  mov     [r8], rbx
0x180009077  cmp     [rdx], ebx
0x180009079  jnz     short loc_1800090A3
0x18000907b  cmp     [rdx+4], ebx
0x18000907e  jnz     short loc_1800090A3
0x180009080  cmp     dword ptr [rdx+8], 0C0h
0x180009087  jnz     short loc_1800090A3
0x180009089  cmp     dword ptr [rdx+0Ch], 46000000h
0x180009090  jnz     short loc_1800090A3
0x180009092  mov     [r8], rcx
0x180009095  mov     rax, [rcx]
0x180009098  mov     rax, [rax+8]
0x18000909c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090a1  jmp     short loc_1800090BB
0x1800090a3  mov     r9, r8; void **
0x1800090a6  add     rcx, 18h; void *
0x1800090aa  mov     r8, rdx; struct _GUID *
0x1800090ad  lea     rdx, ?_entries@?1??_GetEntries@CMSDiscMasterObj@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800090b4  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x1800090b9  mov     ebx, eax
0x1800090bb  mov     eax, ebx
0x1800090bd  add     rsp, 20h
0x1800090c1  pop     rbx
0x1800090c2  retn
```
