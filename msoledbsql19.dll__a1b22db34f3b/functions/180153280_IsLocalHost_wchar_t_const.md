# IsLocalHost(wchar_t const *)

- ea: `0x180153280`
- end: `0x180153307`
- name: `?IsLocalHost@@YA_NPEB_W@Z`
- size: `135`
- prototype: `bool __fastcall(PCNZWCH lpString2)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180153e00`
- `0x1801ab810`
- `0x1801ac440`

## callees

- `0x180153280`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x1801532a8`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x1801532bf`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x1801532a8`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x1801532bf`
- `KERNEL32!CompareStringW` at `0x1801532ed`
- `KERNEL32!CompareStringW` at `0x1801532ed`

## pseudocode

```c
bool __fastcall IsLocalHost(PCNZWCH lpString2)
{
  return *lpString2 == 46 && !lpString2[1]
      || !_wcsicmp_l(L"(local)", lpString2, 0)
      || !_wcsicmp_l(L"localhost", lpString2, 0)
      || CompareStringW(0x800u, 0x20001u, &gwszComputerName, -1, lpString2, -1) == 2;
}

```

## disassembly

```asm
0x180153280  push    rbx
0x180153282  sub     rsp, 30h
0x180153286  mov     eax, 2Eh ; '.'
0x18015328b  mov     rbx, rcx
0x18015328e  cmp     ax, [rcx]
0x180153291  jnz     short loc_18015329B
0x180153293  xor     eax, eax
0x180153295  cmp     ax, [rcx+2]
0x180153299  jz      short loc_1801532FF
0x18015329b  xor     r8d, r8d; Locale
0x18015329e  lea     rcx, aLocal; "(local)"
0x1801532a5  mov     rdx, rbx; String2
0x1801532a8  call    cs:__imp__wcsicmp_l
0x1801532ae  test    eax, eax
0x1801532b0  jz      short loc_1801532FF
0x1801532b2  xor     r8d, r8d; Locale
0x1801532b5  lea     rcx, aLocalhost; "localhost"
0x1801532bc  mov     rdx, rbx; String2
0x1801532bf  call    cs:__imp__wcsicmp_l
0x1801532c5  test    eax, eax
0x1801532c7  jz      short loc_1801532FF
0x1801532c9  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x1801532d1  lea     r8, ?gwszComputerName@@3PA_WA; lpString1
0x1801532d8  mov     r9d, 0FFFFFFFFh; cchCount1
0x1801532de  mov     [rsp+38h+lpString2], rbx; lpString2
0x1801532e3  mov     edx, 20001h; dwCmpFlags
0x1801532e8  mov     ecx, 800h; Locale
0x1801532ed  call    cs:__imp_CompareStringW
0x1801532f3  cmp     eax, 2
0x1801532f6  setz    al
0x1801532f9  add     rsp, 30h
0x1801532fd  pop     rbx
0x1801532fe  retn
0x1801532ff  mov     al, 1
0x180153301  add     rsp, 30h
0x180153305  pop     rbx
0x180153306  retn
```
