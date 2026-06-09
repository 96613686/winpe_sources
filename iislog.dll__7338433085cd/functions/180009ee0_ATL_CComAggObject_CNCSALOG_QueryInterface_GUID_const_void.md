# ATL::CComAggObject<CNCSALOG>::QueryInterface(_GUID const &,void * *)

- ea: `0x180009ee0`
- end: `0x180009f41`
- name: `?QueryInterface@?$CComAggObject@VCNCSALOG@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009ee0`
- `0x180010010`

## import_xrefs

- `ATL!__imp_AtlInternalQueryInterface` at `0x180009f31`
- `ATL!__imp_AtlInternalQueryInterface` at `0x180009f31`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CNCSALOG>::QueryInterface(__int64 a1, _DWORD *a2, _QWORD *a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( *a2 || a2[1] || a2[2] != 192 || a2[3] != 1174405120 )
  {
    return (unsigned int)AtlInternalQueryInterface(a1 + 24, &`CNCSALOG::_GetEntries'::`2'::_entries, a2, a3);
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
0x180009ee0  push    rbx
0x180009ee2  sub     rsp, 20h
0x180009ee6  xor     ebx, ebx
0x180009ee8  cmp     [rdx], ebx
0x180009eea  jnz     short loc_180009F20
0x180009eec  cmp     [rdx+4], ebx
0x180009eef  jnz     short loc_180009F20
0x180009ef1  cmp     dword ptr [rdx+8], 0C0h
0x180009ef8  jnz     short loc_180009F20
0x180009efa  cmp     dword ptr [rdx+0Ch], 46000000h
0x180009f01  jnz     short loc_180009F20
0x180009f03  test    r8, r8
0x180009f06  jnz     short loc_180009F0F
0x180009f08  mov     eax, 80004003h
0x180009f0d  jmp     short loc_180009F3B
0x180009f0f  mov     [r8], rcx
0x180009f12  mov     rax, [rcx]
0x180009f15  mov     rax, [rax+8]
0x180009f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f1e  jmp     short loc_180009F39
0x180009f20  mov     r9, r8
0x180009f23  add     rcx, 18h
0x180009f27  mov     r8, rdx
0x180009f2a  lea     rdx, ?_entries@?1??_GetEntries@CNCSALOG@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CNCSALOG::_GetEntries(void)'::`2'::_entries
0x180009f31  call    cs:__imp_AtlInternalQueryInterface
0x180009f37  mov     ebx, eax
0x180009f39  mov     eax, ebx
0x180009f3b  add     rsp, 20h
0x180009f3f  pop     rbx
0x180009f40  retn
```
