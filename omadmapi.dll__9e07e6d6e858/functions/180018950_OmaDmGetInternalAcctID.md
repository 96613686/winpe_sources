# OmaDmGetInternalAcctID

- ea: `0x180018950`
- end: `0x180018992`
- name: `OmaDmGetInternalAcctID`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e5d4`

## callees

- `0x18000f47c`
- `0x180018950`

## import_xrefs

- `DMCmnUtils!CopyString` at `0x180018979`

## pseudocode

```c
int __fastcall OmaDmGetInternalAcctID(unsigned __int16 *a1, int a2, unsigned __int16 **a3)
{
  if ( !a1 || !a3 )
    return -2147024809;
  if ( a2 )
  {
    if ( a2 == 1 )
      return CopyString(a1, 0xFFFFFFFF, a3);
    return -2147024809;
  }
  return OmaDmGetAccountIDFromLookupID((__int16 *)a1, 0, a3);
}

```

## disassembly

```asm
0x180018950  sub     rsp, 28h
0x180018954  test    rcx, rcx
0x180018957  jnz     short loc_180018964
0x180018959  mov     eax, 80070057h
0x18001895e  add     rsp, 28h
0x180018962  retn
0x180018964  test    r8, r8
0x180018967  jz      short loc_180018959
0x180018969  test    edx, edx
0x18001896b  jz      short loc_180018985
0x18001896d  cmp     edx, 1
0x180018970  jnz     short loc_180018959
0x180018972  or      edx, 0FFFFFFFFh
0x180018975  add     rsp, 28h
0x180018979  jmp     cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180018985  xor     edx, edx
0x180018987  call    ?OmaDmGetAccountIDFromLookupID@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@PEAPEAG@Z; OmaDmGetAccountIDFromLookupID(ushort const *,tagDMACCOUNTLOOKUPTYPE,ushort * *)
0x18001898c  add     rsp, 28h
0x180018990  retn
```
