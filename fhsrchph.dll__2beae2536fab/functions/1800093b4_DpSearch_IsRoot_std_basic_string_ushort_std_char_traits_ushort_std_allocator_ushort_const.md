# DpSearch::IsRoot(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800093b4`
- end: `0x1800094a2`
- name: `?IsRoot@DpSearch@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `238`
- prototype: `char __fastcall(__int64, const WCHAR *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004020`

## callees

- `0x1800067b4`
- `0x1800093b4`
- `0x18000a52c`
- `0x18000a62c`
- `0x18000ab60`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009467`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000947c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009467`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000947c`
- `KERNEL32!CompareStringOrdinal` at `0x180009450`
- `KERNEL32!CompareStringOrdinal` at `0x180009450`

## pseudocode

```c
char __fastcall DpSearch::IsRoot(__int64 a1, const WCHAR *a2)
{
  const WCHAR *v4; // r8
  LPCWCH lpString2[3]; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int64 v7; // [rsp+48h] [rbp-18h]

  v7 = 7;
  lpString2[2] = 0;
  LOWORD(lpString2[0]) = 0;
  std::wstring::assign(lpString2, L"DP://");
  std::wstring::append(lpString2, a1 + 32, 0, -1);
  std::wstring::append(lpString2, L"/");
  v4 = (const WCHAR *)lpString2;
  if ( v7 >= 8 )
    v4 = lpString2[0];
  if ( *((_QWORD *)a2 + 3) >= 8u )
    a2 = *(const WCHAR **)a2;
  if ( CompareStringOrdinal(a2, -1, v4, -1, 1) == 2 )
  {
    if ( v7 >= 8 )
      operator delete((void *)lpString2[0]);
    return 1;
  }
  else
  {
    if ( v7 >= 8 )
      operator delete((void *)lpString2[0]);
    return 0;
  }
}

```

## disassembly

```asm
0x1800093b4  mov     [rsp-8+arg_10], rbx
0x1800093b9  mov     [rsp-8+arg_18], rdi
0x1800093be  push    rbp
0x1800093bf  mov     rbp, rsp
0x1800093c2  sub     rsp, 60h
0x1800093c6  mov     rax, cs:__security_cookie
0x1800093cd  xor     rax, rsp
0x1800093d0  mov     [rbp+var_8], rax
0x1800093d4  mov     rdi, rdx
0x1800093d7  mov     rbx, rcx
0x1800093da  mov     [rbp+var_18], 7
0x1800093e2  xor     eax, eax
0x1800093e4  mov     [rbp+var_20], rax
0x1800093e8  mov     word ptr [rbp+lpString2], ax
0x1800093ec  lea     r8d, [rax+5]
0x1800093f0  lea     rdx, aDp; "DP://"
0x1800093f7  lea     rcx, [rbp+lpString2]; Src
0x1800093fb  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180009400  nop
0x180009401  lea     rdx, [rbx+20h]
0x180009405  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180009409  mov     r9, rbx
0x18000940c  xor     r8d, r8d
0x18000940f  lea     rcx, [rbp+lpString2]
0x180009413  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180009418  lea     rdx, asc_18000E3F4; "/"
0x18000941f  lea     rcx, [rbp+lpString2]; Src
0x180009423  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180009428  lea     r8, [rbp+lpString2]
0x18000942c  cmp     [rbp+var_18], 8
0x180009431  cmovnb  r8, [rbp+lpString2]; lpString2
0x180009436  cmp     qword ptr [rdi+18h], 8
0x18000943b  jb      short loc_180009440
0x18000943d  mov     rdi, [rdi]
0x180009440  mov     [rsp+60h+bIgnoreCase], 1; bIgnoreCase
0x180009448  mov     r9d, ebx; cchCount2
0x18000944b  mov     edx, ebx; cchCount1
0x18000944d  mov     rcx, rdi; lpString1
0x180009450  call    cs:__imp_CompareStringOrdinal
0x180009456  nop
0x180009457  cmp     eax, 2
0x18000945a  jnz     short loc_180009471
0x18000945c  cmp     [rbp+var_18], 8
0x180009461  jb      short loc_18000946D
0x180009463  mov     rcx, [rbp+lpString2]
0x180009467  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000946d  mov     al, 1
0x18000946f  jmp     short loc_180009484
0x180009471  cmp     [rbp+var_18], 8
0x180009476  jb      short loc_180009482
0x180009478  mov     rcx, [rbp+lpString2]
0x18000947c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009482  xor     al, al
0x180009484  mov     rcx, [rbp+var_8]
0x180009488  xor     rcx, rsp; StackCookie
0x18000948b  call    __security_check_cookie
0x180009490  lea     r11, [rsp+60h+var_s0]
0x180009495  mov     rbx, [r11+20h]
0x180009499  mov     rdi, [r11+28h]
0x18000949d  mov     rsp, r11
0x1800094a0  pop     rbp
0x1800094a1  retn
```
