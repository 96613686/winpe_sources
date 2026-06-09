# CompareCNRLinks(_cnrlink const *,_cnrlink const *)

- ea: `0x1800043e4`
- end: `0x1800044c6`
- name: `?CompareCNRLinks@@YA?AW4_comparisonresult@@PEBU_cnrlink@@0@Z`
- size: `226`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000535c`
- `0x1800053f0`
- `0x180005460`

## callees

- `0x1800043e4`
- `0x1800044cc`
- `0x180005750`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000443a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180004482`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000443a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180004482`

## pseudocode

```c
__int64 __fastcall CompareCNRLinks(__int64 a1, __int64 a2)
{
  const CHAR *v2; // r8
  WCHAR *v4; // rsi
  const CHAR *v5; // r8
  WCHAR *v6; // rbx
  WCHAR WideCharStr[264]; // [rsp+30h] [rbp-438h] BYREF
  WCHAR lpWideCharStr[264]; // [rsp+240h] [rbp-228h] BYREF

  v2 = (const CHAR *)(a1 + *(unsigned int *)(a1 + 8));
  if ( v2 == (const CHAR *)(a1 + 20) )
  {
    v4 = WideCharStr;
    MultiByteToWideChar(0, 0, v2, -1, WideCharStr, 260);
  }
  else
  {
    v4 = (WCHAR *)(a1 + *(unsigned int *)(a1 + 20));
  }
  v5 = (const CHAR *)(a2 + *(unsigned int *)(a2 + 8));
  if ( v5 == (const CHAR *)(a2 + 20) )
  {
    v6 = lpWideCharStr;
    MultiByteToWideChar(0, 0, v5, -1, lpWideCharStr, 260);
  }
  else
  {
    v6 = (WCHAR *)(a2 + *(unsigned int *)(a2 + 20));
  }
  return CompareNetNames(v4, v6);
}

```

## disassembly

```asm
0x1800043e4  mov     [rsp+arg_10], rbx
0x1800043e9  mov     [rsp+arg_18], rsi
0x1800043ee  push    rdi
0x1800043ef  sub     rsp, 460h
0x1800043f6  mov     rax, cs:__security_cookie
0x1800043fd  xor     rax, rsp
0x180004400  mov     [rsp+468h+var_18], rax
0x180004408  mov     r8d, [rcx+8]
0x18000440c  lea     rax, [rcx+14h]
0x180004410  add     r8, rcx; lpMultiByteStr
0x180004413  mov     rdi, rdx
0x180004416  cmp     r8, rax
0x180004419  jnz     short loc_180004448
0x18000441b  lea     rax, [rsp+468h+WideCharStr]
0x180004420  mov     [rsp+468h+cchWideChar], 104h; cchWideChar
0x180004428  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18000442c  mov     [rsp+468h+lpWideCharStr], rax; lpWideCharStr
0x180004431  xor     edx, edx; dwFlags
0x180004433  lea     rsi, [rsp+468h+WideCharStr]
0x180004438  xor     ecx, ecx; CodePage
0x18000443a  call    cs:__imp_MultiByteToWideChar
0x180004441  nop     dword ptr [rax+rax+00h]
0x180004446  jmp     short loc_18000444D
0x180004448  mov     esi, [rax]
0x18000444a  add     rsi, rcx
0x18000444d  mov     r8d, [rdi+8]
0x180004451  lea     rax, [rdi+14h]
0x180004455  add     r8, rdi; lpMultiByteStr
0x180004458  cmp     r8, rax
0x18000445b  jnz     short loc_180004490
0x18000445d  lea     rax, [rsp+468h+var_228]
0x180004465  mov     [rsp+468h+cchWideChar], 104h; cchWideChar
0x18000446d  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180004471  mov     [rsp+468h+lpWideCharStr], rax; lpWideCharStr
0x180004476  xor     edx, edx; dwFlags
0x180004478  lea     rbx, [rsp+468h+var_228]
0x180004480  xor     ecx, ecx; CodePage
0x180004482  call    cs:__imp_MultiByteToWideChar
0x180004489  nop     dword ptr [rax+rax+00h]
0x18000448e  jmp     short loc_180004495
0x180004490  mov     ebx, [rax]
0x180004492  add     rbx, rdi
0x180004495  mov     rdx, rbx
0x180004498  mov     rcx, rsi
0x18000449b  call    ?CompareNetNames@@YA?AW4_comparisonresult@@PEBG0@Z; CompareNetNames(ushort const *,ushort const *)
0x1800044a0  mov     rcx, [rsp+468h+var_18]
0x1800044a8  xor     rcx, rsp; StackCookie
0x1800044ab  call    __security_check_cookie
0x1800044b0  lea     r11, [rsp+468h+var_8]
0x1800044b8  mov     rbx, [r11+20h]
0x1800044bc  mov     rsi, [r11+28h]
0x1800044c0  mov     rsp, r11
0x1800044c3  pop     rdi
0x1800044c4  retn
```
