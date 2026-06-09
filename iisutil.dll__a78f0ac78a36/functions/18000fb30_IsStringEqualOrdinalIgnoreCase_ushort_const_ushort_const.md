# IsStringEqualOrdinalIgnoreCase(ushort const *,ushort const *)

- ea: `0x18000fb30`
- end: `0x18000fb75`
- name: `?IsStringEqualOrdinalIgnoreCase@@YA_NPEBG0@Z`
- size: `69`
- prototype: `bool(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000fb30`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000fb52`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000fb52`

## pseudocode

```c
bool __fastcall IsStringEqualOrdinalIgnoreCase(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  if ( !a1 )
    a1 = &pServiceName;
  if ( !a2 )
    a2 = &pServiceName;
  return CompareStringOrdinal(a1, -1, a2, -1, 1) == 2;
}

```

## disassembly

```asm
0x18000fb30  sub     rsp, 38h
0x18000fb34  test    rcx, rcx
0x18000fb37  jz      short loc_18000FB63
0x18000fb39  test    rdx, rdx
0x18000fb3c  jz      short loc_18000FB6C
0x18000fb3e  mov     r9d, 0FFFFFFFFh; cchCount2
0x18000fb44  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000fb4c  mov     r8, rdx; lpString2
0x18000fb4f  mov     edx, r9d; cchCount1
0x18000fb52  call    cs:__imp_CompareStringOrdinal
0x18000fb58  cmp     eax, 2
0x18000fb5b  setz    al
0x18000fb5e  add     rsp, 38h
0x18000fb62  retn
0x18000fb63  lea     rcx, pServiceName
0x18000fb6a  jmp     short loc_18000FB39
0x18000fb6c  lea     rdx, pServiceName
0x18000fb73  jmp     short loc_18000FB3E
```
