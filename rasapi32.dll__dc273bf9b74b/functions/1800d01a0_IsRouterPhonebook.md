# IsRouterPhonebook

- ea: `0x1800d01a0`
- end: `0x1800d0235`
- name: `IsRouterPhonebook`
- size: `149`
- prototype: `__int64 __fastcall(LPCWSTR lpString)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180070a40`
- `0x180070fb0`
- `0x18007a430`
- `0x1800c5760`
- `0x1800cb0f8`

## callees

- `0x1800d01a0`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800d01b3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800d01b3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800d021f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800d021f`
- `rtutils!TracePrintfExA` at `0x1800d01fd`
- `rtutils!TracePrintfExA` at `0x1800d01fd`

## pseudocode

```c
__int64 __fastcall IsRouterPhonebook(LPCWSTR lpString)
{
  unsigned int v2; // ecx
  int v3; // eax
  bool v4; // zf
  const WCHAR *v5; // rax
  const WCHAR *lpString2; // rbx

  v2 = 0;
  if ( lpString )
  {
    v3 = lstrlenW(lpString);
    v4 = 2LL * v3 == 0;
    v5 = &lpString[v3];
    if ( !v4 )
    {
      do
      {
        if ( *v5 == 92 )
          break;
        --v5;
      }
      while ( v5 != lpString );
    }
    lpString2 = v5 + 1;
    if ( *v5 != 92 )
      lpString2 = v5;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "IsRouterPhonebook: pbk=%ws", lpString2);
    return CompareStringW(0x7Fu, 1u, L"router.pbk", -1, lpString2, -1) == 2;
  }
  return v2;
}

```

## disassembly

```asm
0x1800d01a0  push    rbx
0x1800d01a2  sub     rsp, 30h
0x1800d01a6  mov     rbx, rcx
0x1800d01a9  xor     ecx, ecx
0x1800d01ab  test    rbx, rbx
0x1800d01ae  jz      short loc_1800D022D
0x1800d01b0  mov     rcx, rbx; lpString
0x1800d01b3  call    cs:__imp_lstrlenW
0x1800d01b9  movsxd  rdx, eax
0x1800d01bc  mov     ecx, 5Ch ; '\'
0x1800d01c1  add     rdx, rdx
0x1800d01c4  lea     rax, [rdx+rbx]
0x1800d01c8  jz      short loc_1800D01D8
0x1800d01ca  cmp     cx, [rax]
0x1800d01cd  jz      short loc_1800D01D8
0x1800d01cf  sub     rax, 2
0x1800d01d3  cmp     rax, rbx
0x1800d01d6  jnz     short loc_1800D01CA
0x1800d01d8  cmp     cx, [rax]
0x1800d01db  lea     rbx, [rax+2]
0x1800d01df  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800d01e5  cmovnz  rbx, rax
0x1800d01e9  cmp     ecx, 0FFFFFFFFh
0x1800d01ec  jz      short loc_1800D0203
0x1800d01ee  mov     r9, rbx
0x1800d01f1  lea     r8, aIsrouterphoneb_0; "IsRouterPhonebook: pbk=%ws"
0x1800d01f8  mov     edx, 0Ch; dwFlags
0x1800d01fd  call    cs:__imp_TracePrintfExA
0x1800d0203  or      r9d, 0FFFFFFFFh; cchCount1
0x1800d0207  lea     r8, aRouterPbk; "router.pbk"
0x1800d020e  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x1800d0213  mov     [rsp+38h+lpString2], rbx; lpString2
0x1800d0218  lea     edx, [r9+2]; dwCmpFlags
0x1800d021c  lea     ecx, [rdx+7Eh]; Locale
0x1800d021f  call    cs:__imp_CompareStringW
0x1800d0225  xor     ecx, ecx
0x1800d0227  cmp     eax, 2
0x1800d022a  setz    cl
0x1800d022d  mov     eax, ecx
0x1800d022f  add     rsp, 30h
0x1800d0233  pop     rbx
0x1800d0234  retn
```
