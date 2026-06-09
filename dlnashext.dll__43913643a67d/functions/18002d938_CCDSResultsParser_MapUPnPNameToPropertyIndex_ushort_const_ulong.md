# CCDSResultsParser::MapUPnPNameToPropertyIndex(ushort const *,ulong *)

- ea: `0x18002d938`
- end: `0x18002d9a6`
- name: `?MapUPnPNameToPropertyIndex@CCDSResultsParser@@SAJPEBGPEAK@Z`
- size: `110`
- prototype: `__int64 __fastcall(LPCWCH lpString1, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002ee8c`

## callees

- `0x18002d938`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002d983`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002d983`

## pseudocode

```c
__int64 __fastcall CCDSResultsParser::MapUPnPNameToPropertyIndex(LPCWCH lpString1, unsigned int *a2)
{
  unsigned int i; // ebx
  __int64 result; // rax

  *a2 = 0;
  for ( i = 0; ; ++i )
  {
    result = 2147500037LL;
    if ( i >= 0x31 )
      break;
    if ( CompareStringOrdinal(lpString1, -1, *((LPCWCH *)&CCDSResultsParser::c_rgCDSPropNameMap + 4 * (int)i), -1, 1) == 2 )
    {
      *a2 = i;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002d938  mov     [rsp+arg_0], rbx
0x18002d93d  mov     [rsp+arg_8], rsi
0x18002d942  push    rdi
0x18002d943  sub     rsp, 30h
0x18002d947  mov     rdi, rdx
0x18002d94a  mov     dword ptr [rdx], 0
0x18002d950  mov     rsi, rcx
0x18002d953  xor     ebx, ebx
0x18002d955  mov     eax, 80004005h
0x18002d95a  cmp     ebx, 31h ; '1'
0x18002d95d  jnb     short loc_18002D996
0x18002d95f  lea     rax, ?c_rgCDSPropNameMap@CCDSResultsParser@@2QBUCDSPROPMAPPING@1@B; CCDSResultsParser::CDSPROPMAPPING const near * const CCDSResultsParser::c_rgCDSPropNameMap
0x18002d966  movsxd  r8, ebx
0x18002d969  shl     r8, 5
0x18002d96d  or      r9d, 0FFFFFFFFh; cchCount2
0x18002d971  or      edx, r9d; cchCount1
0x18002d974  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18002d97c  mov     rcx, rsi; lpString1
0x18002d97f  mov     r8, [r8+rax]; lpString2
0x18002d983  call    cs:__imp_CompareStringOrdinal
0x18002d989  cmp     eax, 2
0x18002d98c  jz      short loc_18002D992
0x18002d98e  inc     ebx
0x18002d990  jmp     short loc_18002D955
0x18002d992  mov     [rdi], ebx
0x18002d994  xor     eax, eax
0x18002d996  mov     rbx, [rsp+38h+arg_0]
0x18002d99b  mov     rsi, [rsp+38h+arg_8]
0x18002d9a0  add     rsp, 30h
0x18002d9a4  pop     rdi
0x18002d9a5  retn
```
