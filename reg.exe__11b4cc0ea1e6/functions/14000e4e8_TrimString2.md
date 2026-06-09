# TrimString2

- ea: `0x14000e4e8`
- end: `0x14000e5fe`
- name: `TrimString2`
- size: `278`
- prototype: `__int64 __fastcall(LPCWSTR lpString)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x140001e90`
- `0x140002290`
- `0x14000406c`
- `0x140006a5c`
- `0x140009ae4`
- `0x14000c6d0`
- `0x14000d4cc`

## callees

- `0x140001340`
- `0x14000e450`
- `0x14000e4e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14000e54c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14000e579`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14000e54c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14000e579`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000e52e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000e5bd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000e52e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000e5bd`

## pseudocode

```c
__int64 *__fastcall TrimString2(WCHAR *lpString)
{
  wchar_t v2; // ax
  wchar_t *v3; // rbx
  wchar_t v4; // ax
  WCHAR *v5; // rbp
  wchar_t *v6; // rsi
  wchar_t *v7; // rax
  int v8; // eax
  wchar_t Str[4]; // [rsp+20h] [rbp-28h] BYREF

  wcscpy(Str, L" \t");
  if ( !lpString || !lstrlenW(lpString) )
    return &cwszNullString;
  v2 = *lpString;
  v3 = lpString;
  while ( v2 && wcschr(Str, v2) )
    v2 = *++v3;
  v4 = *v3;
  v5 = v3;
  if ( *v3 )
  {
    v6 = 0;
    do
    {
      if ( wcschr(Str, v4) )
      {
        v7 = v3;
        if ( v6 )
          v7 = v6;
        v6 = v7;
      }
      else
      {
        v6 = 0;
      }
      v4 = *++v3;
    }
    while ( *v3 );
    if ( v6 )
      *v6 = 0;
  }
  if ( v5 > lpString )
  {
    if ( v5 )
      v8 = lstrlenW(v5);
    else
      v8 = 0;
    StringCopyW(lpString, v5, (unsigned int)(v8 + 1));
  }
  return (__int64 *)lpString;
}

```

## disassembly

```asm
0x14000e4e8  mov     [rsp+arg_8], rbx
0x14000e4ed  mov     [rsp+arg_10], rbp
0x14000e4f2  push    rsi
0x14000e4f3  push    rdi
0x14000e4f4  push    r14
0x14000e4f6  sub     rsp, 30h
0x14000e4fa  mov     rax, cs:__security_cookie
0x14000e501  xor     rax, rsp
0x14000e504  mov     [rsp+48h+var_20], rax
0x14000e509  mov     eax, dword ptr cs:asc_14001126C; " \t"
0x14000e50f  xor     r14d, r14d
0x14000e512  mov     dword ptr [rsp+48h+Str], eax
0x14000e516  mov     rdi, rcx
0x14000e519  movzx   eax, word ptr cs:asc_14001126C+4; ""
0x14000e520  mov     [rsp+48h+var_24], ax
0x14000e525  test    rcx, rcx
0x14000e528  jz      loc_14000E5D7
0x14000e52e  call    cs:__imp_lstrlenW
0x14000e534  test    eax, eax
0x14000e536  jz      loc_14000E5D7
0x14000e53c  movzx   eax, word ptr [rdi]
0x14000e53f  mov     rbx, rdi
0x14000e542  jmp     short loc_14000E55E
0x14000e544  movzx   edx, ax; Ch
0x14000e547  lea     rcx, [rsp+48h+Str]; Str
0x14000e54c  call    cs:__imp_wcschr
0x14000e552  test    rax, rax
0x14000e555  jz      short loc_14000E563
0x14000e557  add     rbx, 2
0x14000e55b  movzx   eax, word ptr [rbx]
0x14000e55e  test    ax, ax
0x14000e561  jnz     short loc_14000E544
0x14000e563  movzx   eax, word ptr [rbx]
0x14000e566  mov     rbp, rbx
0x14000e569  test    ax, ax
0x14000e56c  jz      short loc_14000E5AB
0x14000e56e  mov     rsi, r14
0x14000e571  movzx   edx, ax; Ch
0x14000e574  lea     rcx, [rsp+48h+Str]; Str
0x14000e579  call    cs:__imp_wcschr
0x14000e57f  test    rax, rax
0x14000e582  jz      short loc_14000E593
0x14000e584  test    rsi, rsi
0x14000e587  mov     rax, rbx
0x14000e58a  cmovnz  rax, rsi
0x14000e58e  mov     rsi, rax
0x14000e591  jmp     short loc_14000E596
0x14000e593  mov     rsi, r14
0x14000e596  add     rbx, 2
0x14000e59a  movzx   eax, word ptr [rbx]
0x14000e59d  test    ax, ax
0x14000e5a0  jnz     short loc_14000E571
0x14000e5a2  test    rsi, rsi
0x14000e5a5  jz      short loc_14000E5AB
0x14000e5a7  mov     [rsi], r14w
0x14000e5ab  cmp     rbp, rdi
0x14000e5ae  jbe     short loc_14000E5D2
0x14000e5b0  test    rbp, rbp
0x14000e5b3  jnz     short loc_14000E5BA
0x14000e5b5  mov     eax, r14d
0x14000e5b8  jmp     short loc_14000E5C3
0x14000e5ba  mov     rcx, rbp; lpString
0x14000e5bd  call    cs:__imp_lstrlenW
0x14000e5c3  lea     r8d, [rax+1]
0x14000e5c7  mov     rdx, rbp
0x14000e5ca  mov     rcx, rdi
0x14000e5cd  call    StringCopyW
0x14000e5d2  mov     rax, rdi
0x14000e5d5  jmp     short loc_14000E5DE
0x14000e5d7  lea     rax, cwszNullString
0x14000e5de  mov     rcx, [rsp+48h+var_20]
0x14000e5e3  xor     rcx, rsp; StackCookie
0x14000e5e6  call    __security_check_cookie
0x14000e5eb  mov     rbx, [rsp+48h+arg_8]
0x14000e5f0  mov     rbp, [rsp+48h+arg_10]
0x14000e5f5  add     rsp, 30h
0x14000e5f9  pop     r14
0x14000e5fb  pop     rdi
0x14000e5fc  pop     rsi
0x14000e5fd  retn
```
