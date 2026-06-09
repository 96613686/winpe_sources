# LKRhash::CTypedHashTable<SnapinCLSIDTable,SnapinRecord,CStr const *,LKRhash::CLKRLinearHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)

- ea: `0x18000e4e0`
- end: `0x18000e51b`
- name: `?_EqualKeys@?$CTypedHashTable@VSnapinCLSIDTable@@VSnapinRecord@@PEBVCStr@@VCLKRLinearHashTable@LKRhash@@@LKRhash@@CA_N_K0@Z`
- size: `59`
- prototype: `bool(unsigned __int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000e4e0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000e4fe`
- `msvcrt!_wcsicmp` at `0x18000e4fe`

## pseudocode

```c
bool __fastcall LKRhash::CTypedHashTable<SnapinCLSIDTable,SnapinRecord,CStr const *,LKRhash::CLKRLinearHashTable>::_EqualKeys(
        __int64 a1,
        __int64 a2)
{
  if ( a1 )
  {
    if ( a2 && *(_DWORD *)(a1 + 16) == *(_DWORD *)(a2 + 16) )
      return _wcsicmp(*(const wchar_t **)(a1 + 8), *(const wchar_t **)(a2 + 8)) == 0;
  }
  else if ( !a2 )
  {
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18000e4e0  sub     rsp, 28h
0x18000e4e4  test    rcx, rcx
0x18000e4e7  jz      short loc_18000E50B
0x18000e4e9  test    rdx, rdx
0x18000e4ec  jz      short loc_18000E514
0x18000e4ee  mov     eax, [rdx+10h]
0x18000e4f1  cmp     [rcx+10h], eax
0x18000e4f4  jnz     short loc_18000E514
0x18000e4f6  mov     rdx, [rdx+8]; String2
0x18000e4fa  mov     rcx, [rcx+8]; String1
0x18000e4fe  call    cs:__imp__wcsicmp
0x18000e504  test    eax, eax
0x18000e506  setz    al
0x18000e509  jmp     short loc_18000E516
0x18000e50b  cmp     rcx, rdx
0x18000e50e  jnz     short loc_18000E514
0x18000e510  mov     al, 1
0x18000e512  jmp     short loc_18000E516
0x18000e514  xor     al, al
0x18000e516  add     rsp, 28h
0x18000e51a  retn
```
