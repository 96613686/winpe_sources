# LdapParseCrackedScopeAndFilter

- ea: `0x180012fe4`
- end: `0x1800130bd`
- name: `LdapParseCrackedScopeAndFilter`
- size: `217`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, PWSTR pszUrl, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012b4c`

## callees

- `0x180012390`
- `0x180012fe4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800130a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800130a8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013021`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013052`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013080`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013021`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013052`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013080`

## pseudocode

```c
__int64 __fastcall LdapParseCrackedScopeAndFilter(PCNZWCH lpString1, PWSTR pszUrl, __int64 a3)
{
  int v6; // ebx
  __int64 v7; // rax

  v6 = 2;
  if ( CompareStringW(0x409u, 1u, lpString1, -1, L"base", -1) == 2 )
  {
    v6 = 0;
  }
  else if ( CompareStringW(0x409u, 1u, lpString1, -1, L"one", -1) == 2 )
  {
    v6 = 1;
  }
  else if ( CompareStringW(0x409u, 1u, lpString1, -1, L"sub", -1) != 2 )
  {
    SetLastError(0x80070057);
    return 0;
  }
  v7 = LdapUrlUnescape(pszUrl);
  *(_QWORD *)(a3 + 48) = v7;
  if ( v7 )
  {
    *(_DWORD *)(a3 + 40) = v6;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180012fe4  push    rbx
0x180012fe6  push    rbp
0x180012fe7  push    rsi
0x180012fe8  push    rdi
0x180012fe9  push    r14
0x180012feb  push    r15
0x180012fed  sub     rsp, 38h
0x180012ff1  or      r15d, 0FFFFFFFFh
0x180012ff5  lea     rax, aBase; "base"
0x180012ffc  mov     rdi, r8
0x180012fff  mov     [rsp+68h+cchCount2], r15d; cchCount2
0x180013004  mov     rbp, rdx
0x180013007  mov     [rsp+68h+lpString2], rax; lpString2
0x18001300c  mov     rsi, rcx
0x18001300f  mov     r8, rcx; lpString1
0x180013012  lea     r14d, [r15+2]
0x180013016  mov     r9d, r15d; cchCount1
0x180013019  mov     edx, r14d; dwCmpFlags
0x18001301c  mov     ecx, 409h; Locale
0x180013021  call    cs:__imp_CompareStringW
0x180013027  lea     ebx, [r15+3]
0x18001302b  cmp     eax, ebx
0x18001302d  jnz     short loc_180013033
0x18001302f  xor     ebx, ebx
0x180013031  jmp     short loc_18001308A
0x180013033  lea     rax, aOne; "one"
0x18001303a  mov     [rsp+68h+cchCount2], r15d; cchCount2
0x18001303f  mov     r9d, r15d; cchCount1
0x180013042  mov     [rsp+68h+lpString2], rax; lpString2
0x180013047  mov     r8, rsi; lpString1
0x18001304a  mov     edx, r14d; dwCmpFlags
0x18001304d  mov     ecx, 409h; Locale
0x180013052  call    cs:__imp_CompareStringW
0x180013058  cmp     eax, ebx
0x18001305a  jnz     short loc_180013061
0x18001305c  mov     ebx, r14d
0x18001305f  jmp     short loc_18001308A
0x180013061  lea     rax, aSub; "sub"
0x180013068  mov     [rsp+68h+cchCount2], r15d; cchCount2
0x18001306d  mov     r9d, r15d; cchCount1
0x180013070  mov     [rsp+68h+lpString2], rax; lpString2
0x180013075  mov     r8, rsi; lpString1
0x180013078  mov     edx, r14d; dwCmpFlags
0x18001307b  mov     ecx, 409h; Locale
0x180013080  call    cs:__imp_CompareStringW
0x180013086  cmp     eax, ebx
0x180013088  jnz     short loc_1800130A3
0x18001308a  mov     rcx, rbp; pszUrl
0x18001308d  call    LdapUrlUnescape
0x180013092  mov     [rdi+30h], rax
0x180013096  test    rax, rax
0x180013099  jz      short loc_1800130AE
0x18001309b  mov     [rdi+28h], ebx
0x18001309e  mov     eax, r14d
0x1800130a1  jmp     short loc_1800130B0
0x1800130a3  mov     ecx, 80070057h; dwErrCode
0x1800130a8  call    cs:__imp_SetLastError
0x1800130ae  xor     eax, eax
0x1800130b0  add     rsp, 38h
0x1800130b4  pop     r15
0x1800130b6  pop     r14
0x1800130b8  pop     rdi
0x1800130b9  pop     rsi
0x1800130ba  pop     rbp
0x1800130bb  pop     rbx
0x1800130bc  retn
```
