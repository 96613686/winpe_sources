# CreateAnsiCpString

- ea: `0x180007520`
- end: `0x18000767c`
- name: `CreateAnsiCpString`
- size: `348`
- prototype: `__int64 __fastcall(LCID Locale, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000739c`

## callees

- `0x18000626c`
- `0x180007520`
- `0x18000800c`
- `0x180008074`
- `0x1800080b0`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000755a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000755a`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180007550`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x1800075cc`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180007550`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x1800075cc`
- `KERNEL32!lstrcmpW` at `0x180007573`
- `KERNEL32!lstrcmpW` at `0x1800075b4`
- `KERNEL32!lstrcmpW` at `0x180007610`
- `KERNEL32!lstrcmpW` at `0x180007573`
- `KERNEL32!lstrcmpW` at `0x1800075b4`
- `KERNEL32!lstrcmpW` at `0x180007610`

## pseudocode

```c
__int64 __fastcall CreateAnsiCpString(LCID Locale, unsigned __int16 *a2)
{
  unsigned int v4; // esi
  size_t pcchLength; // [rsp+20h] [rbp-58h] BYREF
  WCHAR LCData[24]; // [rsp+28h] [rbp-50h] BYREF

  if ( GetLocaleInfoW(Locale, 0x1004u, a2, 12) )
  {
    v4 = 0;
    if ( lstrcmpW(a2, L"950") )
    {
      if ( lstrcmpW(a2, L"0") )
      {
        if ( Locale == 1281 || Locale == 1534 || Locale == 2559 )
          StringCchCatW(a2, 0xCu, L".QPS");
      }
      else if ( GetLocaleInfoW(Locale, 0x6Cu, LCData, 24) )
      {
        pcchLength = 0;
        if ( !StringCchLengthW(LCData, 0x18u, &pcchLength) && pcchLength >= 4 )
        {
          LCData[4] = 0;
          if ( lstrcmpW(LCData, L"Latn") )
            StringCchPrintfW(a2, 0xCu, L"0.%s", LCData);
        }
      }
    }
    else if ( (Locale & 0xFC00) == 0xC00 )
    {
      StringCchCopyW(a2, 0xCu, (size_t *)L"950.HK");
    }
  }
  else
  {
    return GetLastError();
  }
  return v4;
}

```

## disassembly

```asm
0x180007520  mov     [rsp+arg_10], rbx
0x180007525  push    rbp
0x180007526  push    rsi
0x180007527  push    rdi
0x180007528  sub     rsp, 60h
0x18000752c  mov     rax, cs:__security_cookie
0x180007533  xor     rax, rsp
0x180007536  mov     [rsp+78h+var_20], rax
0x18000753b  mov     rdi, rdx
0x18000753e  mov     r8, rdx; lpLCData
0x180007541  mov     ebp, 0Ch
0x180007546  mov     edx, 1004h; LCType
0x18000754b  mov     r9d, ebp; cchData
0x18000754e  mov     ebx, ecx
0x180007550  call    cs:__imp_GetLocaleInfoW
0x180007556  test    eax, eax
0x180007558  jnz     short loc_180007567
0x18000755a  call    cs:__imp_GetLastError
0x180007560  mov     esi, eax
0x180007562  jmp     loc_18000765D
0x180007567  lea     rdx, String2; "950"
0x18000756e  mov     rcx, rdi; lpString1
0x180007571  xor     esi, esi
0x180007573  call    cs:__imp_lstrcmpW
0x180007579  test    eax, eax
0x18000757b  jnz     short loc_1800075AA
0x18000757d  mov     eax, 0FC00h
0x180007582  and     bx, ax
0x180007585  mov     eax, 0C00h
0x18000758a  cmp     ax, bx
0x18000758d  jnz     loc_18000765D
0x180007593  lea     r8, a950Hk; "950.HK"
0x18000759a  mov     rdx, rbp; unsigned __int64
0x18000759d  mov     rcx, rdi; unsigned __int16 *
0x1800075a0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800075a5  jmp     loc_18000765D
0x1800075aa  lea     rdx, a0; "0"
0x1800075b1  mov     rcx, rdi; lpString1
0x1800075b4  call    cs:__imp_lstrcmpW
0x1800075ba  test    eax, eax
0x1800075bc  jnz     short loc_180007633
0x1800075be  lea     r9d, [rax+18h]; cchData
0x1800075c2  mov     ecx, ebx; Locale
0x1800075c4  lea     r8, [rsp+78h+LCData]; lpLCData
0x1800075c9  lea     edx, [rax+6Ch]; LCType
0x1800075cc  call    cs:__imp_GetLocaleInfoW
0x1800075d2  test    eax, eax
0x1800075d4  jz      loc_18000765D
0x1800075da  lea     r8, [rsp+78h+pcchLength]; pcchLength
0x1800075df  mov     [rsp+78h+pcchLength], rsi
0x1800075e4  mov     edx, 18h; cchMax
0x1800075e9  lea     rcx, [rsp+78h+LCData]; psz
0x1800075ee  call    StringCchLengthW
0x1800075f3  test    eax, eax
0x1800075f5  jnz     short loc_18000765D
0x1800075f7  cmp     [rsp+78h+pcchLength], 4
0x1800075fd  jb      short loc_18000765D
0x1800075ff  lea     rdx, aLatn; "Latn"
0x180007606  mov     [rsp+78h+var_48], ax
0x18000760b  lea     rcx, [rsp+78h+LCData]; lpString1
0x180007610  call    cs:__imp_lstrcmpW
0x180007616  test    eax, eax
0x180007618  jz      short loc_18000765D
0x18000761a  lea     r9, [rsp+78h+LCData]
0x18000761f  mov     rdx, rbp; cchDest
0x180007622  lea     r8, a0S; "0.%s"
0x180007629  mov     rcx, rdi; pszDest
0x18000762c  call    StringCchPrintfW
0x180007631  jmp     short loc_18000765D
0x180007633  cmp     ebx, 501h
0x180007639  jz      short loc_18000764B
0x18000763b  cmp     ebx, 5FEh
0x180007641  jz      short loc_18000764B
0x180007643  cmp     ebx, 9FFh
0x180007649  jnz     short loc_18000765D
0x18000764b  lea     r8, aQps; ".QPS"
0x180007652  mov     rdx, rbp; cchDest
0x180007655  mov     rcx, rdi; pszDest
0x180007658  call    StringCchCatW
0x18000765d  mov     eax, esi
0x18000765f  mov     rcx, [rsp+78h+var_20]
0x180007664  xor     rcx, rsp; StackCookie
0x180007667  call    __security_check_cookie
0x18000766c  mov     rbx, [rsp+78h+arg_10]
0x180007674  add     rsp, 60h
0x180007678  pop     rdi
0x180007679  pop     rsi
0x18000767a  pop     rbp
0x18000767b  retn
```
