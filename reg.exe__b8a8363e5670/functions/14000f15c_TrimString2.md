# TrimString2

- ea: `0x14000f15c`
- end: `0x14000f28b`
- name: `TrimString2`
- size: `303`
- prototype: `__int64 __fastcall(LPCWSTR lpString)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x140001e90`
- `0x140002338`
- `0x14000426c`
- `0x140006e6c`
- `0x14000a0e0`
- `0x14000cf2c`
- `0x14000df14`

## callees

- `0x140001340`
- `0x14000f0c0`
- `0x14000f15c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14000f1c6`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14000f1f9`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14000f1c6`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14000f1f9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000f1a2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000f243`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000f1a2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000f243`

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
0x14000f15c  mov     [rsp+arg_8], rbx
0x14000f161  mov     [rsp+arg_10], rbp
0x14000f166  push    rsi
0x14000f167  push    rdi
0x14000f168  push    r14
0x14000f16a  sub     rsp, 30h
0x14000f16e  mov     rax, cs:__security_cookie
0x14000f175  xor     rax, rsp
0x14000f178  mov     [rsp+48h+var_20], rax
0x14000f17d  mov     eax, dword ptr cs:asc_14001226C; " \t"
0x14000f183  xor     r14d, r14d
0x14000f186  mov     dword ptr [rsp+48h+Str], eax
0x14000f18a  mov     rdi, rcx
0x14000f18d  movzx   eax, word ptr cs:asc_14001226C+4; ""
0x14000f194  mov     [rsp+48h+var_24], ax
0x14000f199  test    rcx, rcx
0x14000f19c  jz      loc_14000F263
0x14000f1a2  call    cs:__imp_lstrlenW
0x14000f1a9  nop     dword ptr [rax+rax+00h]
0x14000f1ae  test    eax, eax
0x14000f1b0  jz      loc_14000F263
0x14000f1b6  movzx   eax, word ptr [rdi]
0x14000f1b9  mov     rbx, rdi
0x14000f1bc  jmp     short loc_14000F1DE
0x14000f1be  movzx   edx, ax; Ch
0x14000f1c1  lea     rcx, [rsp+48h+Str]; Str
0x14000f1c6  call    cs:__imp_wcschr
0x14000f1cd  nop     dword ptr [rax+rax+00h]
0x14000f1d2  test    rax, rax
0x14000f1d5  jz      short loc_14000F1E3
0x14000f1d7  add     rbx, 2
0x14000f1db  movzx   eax, word ptr [rbx]
0x14000f1de  test    ax, ax
0x14000f1e1  jnz     short loc_14000F1BE
0x14000f1e3  movzx   eax, word ptr [rbx]
0x14000f1e6  mov     rbp, rbx
0x14000f1e9  test    ax, ax
0x14000f1ec  jz      short loc_14000F231
0x14000f1ee  mov     rsi, r14
0x14000f1f1  movzx   edx, ax; Ch
0x14000f1f4  lea     rcx, [rsp+48h+Str]; Str
0x14000f1f9  call    cs:__imp_wcschr
0x14000f200  nop     dword ptr [rax+rax+00h]
0x14000f205  test    rax, rax
0x14000f208  jz      short loc_14000F219
0x14000f20a  test    rsi, rsi
0x14000f20d  mov     rax, rbx
0x14000f210  cmovnz  rax, rsi
0x14000f214  mov     rsi, rax
0x14000f217  jmp     short loc_14000F21C
0x14000f219  mov     rsi, r14
0x14000f21c  add     rbx, 2
0x14000f220  movzx   eax, word ptr [rbx]
0x14000f223  test    ax, ax
0x14000f226  jnz     short loc_14000F1F1
0x14000f228  test    rsi, rsi
0x14000f22b  jz      short loc_14000F231
0x14000f22d  mov     [rsi], r14w
0x14000f231  cmp     rbp, rdi
0x14000f234  jbe     short loc_14000F25E
0x14000f236  test    rbp, rbp
0x14000f239  jnz     short loc_14000F240
0x14000f23b  mov     eax, r14d
0x14000f23e  jmp     short loc_14000F24F
0x14000f240  mov     rcx, rbp; lpString
0x14000f243  call    cs:__imp_lstrlenW
0x14000f24a  nop     dword ptr [rax+rax+00h]
0x14000f24f  lea     r8d, [rax+1]
0x14000f253  mov     rdx, rbp
0x14000f256  mov     rcx, rdi
0x14000f259  call    StringCopyW
0x14000f25e  mov     rax, rdi
0x14000f261  jmp     short loc_14000F26A
0x14000f263  lea     rax, cwszNullString
0x14000f26a  mov     rcx, [rsp+48h+var_20]
0x14000f26f  xor     rcx, rsp; StackCookie
0x14000f272  call    __security_check_cookie
0x14000f277  mov     rbx, [rsp+48h+arg_8]
0x14000f27c  mov     rbp, [rsp+48h+arg_10]
0x14000f281  add     rsp, 30h
0x14000f285  pop     r14
0x14000f287  pop     rdi
0x14000f288  pop     rsi
0x14000f289  retn
```
