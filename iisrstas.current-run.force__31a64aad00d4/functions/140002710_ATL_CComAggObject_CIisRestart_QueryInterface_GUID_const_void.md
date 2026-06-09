# ATL::CComAggObject<CIisRestart>::QueryInterface(_GUID const &,void * *)

- ea: `0x140002710`
- end: `0x140002771`
- name: `?QueryInterface@?$CComAggObject@VCIisRestart@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140002710`
- `0x140006010`

## import_xrefs

- `ATL!__imp_AtlInternalQueryInterface` at `0x140002761`
- `ATL!__imp_AtlInternalQueryInterface` at `0x140002761`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CIisRestart>::QueryInterface(__int64 a1, _DWORD *a2, _QWORD *a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( *a2 || a2[1] || a2[2] != 192 || a2[3] != 1174405120 )
  {
    return (unsigned int)AtlInternalQueryInterface(a1 + 24, &`CIisRestart::_GetEntries'::`2'::_entries, a2, a3);
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
0x140002710  push    rbx
0x140002712  sub     rsp, 20h
0x140002716  xor     ebx, ebx
0x140002718  cmp     [rdx], ebx
0x14000271a  jnz     short loc_140002750
0x14000271c  cmp     [rdx+4], ebx
0x14000271f  jnz     short loc_140002750
0x140002721  cmp     dword ptr [rdx+8], 0C0h
0x140002728  jnz     short loc_140002750
0x14000272a  cmp     dword ptr [rdx+0Ch], 46000000h
0x140002731  jnz     short loc_140002750
0x140002733  test    r8, r8
0x140002736  jnz     short loc_14000273F
0x140002738  mov     eax, 80004003h
0x14000273d  jmp     short loc_14000276B
0x14000273f  mov     [r8], rcx
0x140002742  mov     rax, [rcx]
0x140002745  mov     rax, [rax+8]
0x140002749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000274e  jmp     short loc_140002769
0x140002750  mov     r9, r8
0x140002753  add     rcx, 18h
0x140002757  mov     r8, rdx
0x14000275a  lea     rdx, ?_entries@?1??_GetEntries@CIisRestart@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CIisRestart::_GetEntries(void)'::`2'::_entries
0x140002761  call    cs:__imp_AtlInternalQueryInterface
0x140002767  mov     ebx, eax
0x140002769  mov     eax, ebx
0x14000276b  add     rsp, 20h
0x14000276f  pop     rbx
0x140002770  retn
```
