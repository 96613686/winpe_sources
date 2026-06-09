# GetFilenameFromPath

- ea: `0x180029f14`
- end: `0x180029fbf`
- name: `GetFilenameFromPath`
- size: `171`
- prototype: `const WCHAR *__fastcall(LPCWSTR lpStringSource)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x1800071e4`
- `0x18000815c`
- `0x180008374`
- `0x180008a64`
- `0x180008cc0`
- `0x18000b070`
- `0x18001f720`
- `0x180023a78`
- `0x18002435c`
- `0x180029e64`
- `0x18003b3cc`
- `0x1800412a4`
- `0x180044ab0`
- `0x180044d90`
- `0x180045200`
- `0x180048b80`

## callees

- `0x180029f14`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180029f67`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180029f91`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180029f67`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180029f91`

## pseudocode

```c
const WCHAR *__fastcall GetFilenameFromPath(LPCWSTR lpStringSource)
{
  __int64 v1; // rdi
  const WCHAR *v2; // rsi
  int StringOrdinal; // ebx
  int v4; // eax

  v1 = -1;
  v2 = lpStringSource;
  do
    ++v1;
  while ( lpStringSource[v1] );
  if ( v1 && lpStringSource[v1 - 1] == 92 )
    LODWORD(v1) = v1 - 1;
  StringOrdinal = FindStringOrdinal(0x800000u, lpStringSource, v1, L"\\", 1, 1);
  v4 = FindStringOrdinal(0x800000u, v2, v1, L":", 1, 1);
  if ( StringOrdinal > v4 )
    v4 = StringOrdinal;
  if ( v4 != -1 )
    v2 += v4 + 1;
  return v2;
}

```

## disassembly

```asm
0x180029f14  mov     [rsp+arg_0], rbx
0x180029f19  mov     [rsp+arg_8], rsi
0x180029f1e  push    rdi
0x180029f1f  sub     rsp, 30h
0x180029f23  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180029f27  mov     rsi, rcx
0x180029f2a  xor     eax, eax
0x180029f2c  inc     rdi
0x180029f2f  cmp     [rcx+rdi*2], ax
0x180029f33  jnz     short loc_180029F2C
0x180029f35  test    rdi, rdi
0x180029f38  jz      short loc_180029F45
0x180029f3a  cmp     word ptr [rcx+rdi*2-2], 5Ch ; '\'
0x180029f40  jnz     short loc_180029F45
0x180029f42  dec     rdi
0x180029f45  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180029f4d  lea     r9, StringValue; "\\"
0x180029f54  mov     r8d, edi; cchSource
0x180029f57  mov     [rsp+38h+cchValue], 1; cchValue
0x180029f5f  mov     rdx, rsi; lpStringSource
0x180029f62  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x180029f67  call    cs:__imp_FindStringOrdinal
0x180029f6d  lea     r9, asc_18008C924; ":"
0x180029f74  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180029f7c  mov     r8d, edi; cchSource
0x180029f7f  mov     [rsp+38h+cchValue], 1; cchValue
0x180029f87  mov     rdx, rsi; lpStringSource
0x180029f8a  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x180029f8f  mov     ebx, eax
0x180029f91  call    cs:__imp_FindStringOrdinal
0x180029f97  cmp     ebx, eax
0x180029f99  cmovg   eax, ebx
0x180029f9c  cmp     eax, 0FFFFFFFFh
0x180029f9f  jz      short loc_180029FAC
0x180029fa1  movsxd  rcx, eax
0x180029fa4  lea     rsi, [rsi+rcx*2]
0x180029fa8  add     rsi, 2
0x180029fac  mov     rbx, [rsp+38h+arg_0]
0x180029fb1  mov     rax, rsi
0x180029fb4  mov     rsi, [rsp+38h+arg_8]
0x180029fb9  add     rsp, 30h
0x180029fbd  pop     rdi
0x180029fbe  retn
```
