# Dns_IsNameLocalW

- ea: `0x180004294`
- end: `0x18000434a`
- name: `Dns_IsNameLocalW`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004164`

## callees

- `0x180004294`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800042a8`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800042a8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800042ed`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180004320`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800042ed`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180004320`

## pseudocode

```c
__int64 __fastcall Dns_IsNameLocalW(const wchar_t *a1)
{
  wchar_t *v1; // rax
  const WCHAR *v2; // rdi
  unsigned int v3; // ebx

  v1 = wcschr(a1, 0x2Eu);
  if ( !v1 )
    return 0;
  v2 = v1 + 1;
  if ( !v1[1] )
    return 0;
  v3 = 1;
  if ( CompareStringW(0x409u, 1u, v2, -1, L"local", -1) != 2 )
    return CompareStringW(0x409u, 1u, v2, -1, L"local.", -1) == 2;
  return v3;
}

```

## disassembly

```asm
0x180004294  mov     [rsp+arg_0], rbx
0x180004299  mov     [rsp+arg_8], rsi
0x18000429e  push    rdi
0x18000429f  sub     rsp, 30h
0x1800042a3  mov     edx, 2Eh ; '.'; Ch
0x1800042a8  call    cs:__imp_wcschr
0x1800042af  nop     dword ptr [rax+rax+00h]
0x1800042b4  xor     esi, esi
0x1800042b6  test    rax, rax
0x1800042b9  jz      loc_180004346
0x1800042bf  lea     rdi, [rax+2]
0x1800042c3  cmp     [rdi], si
0x1800042c6  jz      short loc_180004346
0x1800042c8  lea     rax, String2; "local"
0x1800042cf  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800042d7  lea     ebx, [rsi+1]
0x1800042da  mov     [rsp+38h+lpString2], rax; lpString2
0x1800042df  mov     edx, ebx; dwCmpFlags
0x1800042e1  or      r9d, 0FFFFFFFFh; cchCount1
0x1800042e5  mov     r8, rdi; lpString1
0x1800042e8  mov     ecx, 409h; Locale
0x1800042ed  call    cs:__imp_CompareStringW
0x1800042f4  nop     dword ptr [rax+rax+00h]
0x1800042f9  cmp     eax, 2
0x1800042fc  jz      short loc_180004333
0x1800042fe  lea     rax, aLocal; "local."
0x180004305  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000430d  or      r9d, 0FFFFFFFFh; cchCount1
0x180004311  mov     [rsp+38h+lpString2], rax; lpString2
0x180004316  mov     r8, rdi; lpString1
0x180004319  mov     edx, ebx; dwCmpFlags
0x18000431b  mov     ecx, 409h; Locale
0x180004320  call    cs:__imp_CompareStringW
0x180004327  nop     dword ptr [rax+rax+00h]
0x18000432c  cmp     eax, 2
0x18000432f  jz      short loc_180004333
0x180004331  mov     ebx, esi
0x180004333  mov     eax, ebx
0x180004335  mov     rbx, [rsp+38h+arg_0]
0x18000433a  mov     rsi, [rsp+38h+arg_8]
0x18000433f  add     rsp, 30h
0x180004343  pop     rdi
0x180004344  retn
0x180004346  xor     eax, eax
0x180004348  jmp     short loc_180004335
```
