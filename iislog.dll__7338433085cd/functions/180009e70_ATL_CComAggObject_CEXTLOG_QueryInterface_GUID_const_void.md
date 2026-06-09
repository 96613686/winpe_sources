# ATL::CComAggObject<CEXTLOG>::QueryInterface(_GUID const &,void * *)

- ea: `0x180009e70`
- end: `0x180009ed1`
- name: `?QueryInterface@?$CComAggObject@VCEXTLOG@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009e70`
- `0x180010010`

## import_xrefs

- `ATL!__imp_AtlInternalQueryInterface` at `0x180009ec1`
- `ATL!__imp_AtlInternalQueryInterface` at `0x180009ec1`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CEXTLOG>::QueryInterface(__int64 a1, _DWORD *a2, _QWORD *a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( *a2 || a2[1] || a2[2] != 192 || a2[3] != 1174405120 )
  {
    return (unsigned int)AtlInternalQueryInterface(a1 + 24, &`CEXTLOG::_GetEntries'::`2'::_entries, a2, a3);
  }
  else
  {
    if ( !a3 )
      return 2147500035LL;
    *a3 = a1;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  }
  return v3;
}

```

## disassembly

```asm
0x180009e70  push    rbx
0x180009e72  sub     rsp, 20h
0x180009e76  xor     ebx, ebx
0x180009e78  cmp     [rdx], ebx
0x180009e7a  jnz     short loc_180009EB0
0x180009e7c  cmp     [rdx+4], ebx
0x180009e7f  jnz     short loc_180009EB0
0x180009e81  cmp     dword ptr [rdx+8], 0C0h
0x180009e88  jnz     short loc_180009EB0
0x180009e8a  cmp     dword ptr [rdx+0Ch], 46000000h
0x180009e91  jnz     short loc_180009EB0
0x180009e93  test    r8, r8
0x180009e96  jnz     short loc_180009E9F
0x180009e98  mov     eax, 80004003h
0x180009e9d  jmp     short loc_180009ECB
0x180009e9f  mov     [r8], rcx
0x180009ea2  mov     rax, [rcx]
0x180009ea5  mov     rax, [rax+8]
0x180009ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009eae  jmp     short loc_180009EC9
0x180009eb0  mov     r9, r8
0x180009eb3  add     rcx, 18h
0x180009eb7  mov     r8, rdx
0x180009eba  lea     rdx, ?_entries@?1??_GetEntries@CEXTLOG@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CEXTLOG::_GetEntries(void)'::`2'::_entries
0x180009ec1  call    cs:__imp_AtlInternalQueryInterface
0x180009ec7  mov     ebx, eax
0x180009ec9  mov     eax, ebx
0x180009ecb  add     rsp, 20h
0x180009ecf  pop     rbx
0x180009ed0  retn
```
