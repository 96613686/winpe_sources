# MCIWndiSetCaption

- ea: `0x180014adc`
- end: `0x180014c6f`
- name: `MCIWndiSetCaption`
- size: `403`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x180012da8`
- `0x180013edc`
- `0x1800149d4`
- `0x180014fbc`

## callees

- `0x1800014b0`
- `0x180002198`
- `0x180002280`
- `0x180003f98`
- `0x180010884`
- `0x180014adc`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharPrevW` at `0x180014b68`
- `api-ms-win-core-string-l2-1-0!CharPrevW` at `0x180014b68`
- `USER32!SendMessageW` at `0x180014bc1`
- `USER32!SendMessageW` at `0x180014bc1`
- `USER32!SetWindowTextW` at `0x180014c4e`
- `USER32!SetWindowTextW` at `0x180014c4e`

## pseudocode

```c
void __fastcall MCIWndiSetCaption(__int64 a1)
{
  unsigned __int64 v2; // rdi
  __int64 v3; // rax
  const WCHAR *i; // rcx
  unsigned __int64 v5; // rax
  __int64 v6; // rdx
  const wchar_t *v7; // r8
  wchar_t lParam[40]; // [rsp+20h] [rbp-E0h] BYREF
  wchar_t pszSrc[40]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t v10[40]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t pszDest[200]; // [rsp+110h] [rbp+10h] BYREF

  if ( (*(_BYTE *)(a1 + 32) & 0x70) != 0 )
  {
    pszDest[0] = 0;
    if ( *(_DWORD *)(a1 + 20) )
    {
      if ( (*(_BYTE *)(a1 + 32) & 0x10) != 0 )
      {
        v2 = a1 + 244;
        v3 = -1;
        do
          ++v3;
        while ( *(_WORD *)(v2 + 2 * v3) );
        for ( i = (const WCHAR *)(v2 + 2 * v3); (unsigned __int64)i > v2; i = CharPrevW((LPCWSTR)(a1 + 244), i) )
        {
          v5 = *i;
          LOWORD(v5) = v5 - 47;
          if ( (unsigned __int16)v5 <= 0x2Du )
          {
            v6 = 0x200000000801LL;
            if ( _bittest64(&v6, v5) )
              break;
          }
        }
        v7 = i + 1;
        if ( (unsigned __int64)i <= v2 )
          v7 = i;
        StringCchCopyW(pszDest, 0xC8u, v7);
      }
      if ( (*(_BYTE *)(a1 + 32) & 0x60) != 0 )
        StringCchCatW(pszDest, 0xC8u, L" (");
      if ( (*(_BYTE *)(a1 + 32) & 0x20) != 0 )
      {
        SendMessageW(*(HWND *)a1, 0x4CAu, 0x28u, (LPARAM)lParam);
        if ( (*(_BYTE *)(a1 + 32) & 0x40) != 0 )
          StringCchPrintfW(pszSrc, 0x28u, L"%s - ", lParam);
        else
          StringCchCopyW(pszSrc, 0x28u, lParam);
        StringCchCatW(pszDest, 0xC8u, pszSrc);
      }
      if ( (*(_BYTE *)(a1 + 32) & 0x40) != 0 )
      {
        MCIWndGet(a1, szStatusMode, v10, 40);
        StringCchCatW(pszDest, 0xC8u, v10);
      }
      if ( (*(_BYTE *)(a1 + 32) & 0x60) != 0 )
        StringCchCatW(pszDest, 0xC8u, L")");
      SetWindowTextW(*(HWND *)a1, pszDest);
    }
  }
}

```

## disassembly

```asm
0x180014adc  push    rbp
0x180014ade  push    rbx
0x180014adf  push    rsi
0x180014ae0  push    rdi
0x180014ae1  lea     rbp, [rsp-1B8h]
0x180014ae9  sub     rsp, 2B8h
0x180014af0  mov     rax, cs:__security_cookie
0x180014af7  xor     rax, rsp
0x180014afa  mov     [rbp+1D0h+var_30], rax
0x180014b01  test    byte ptr [rcx+20h], 70h
0x180014b05  mov     rbx, rcx
0x180014b08  jz      loc_180014C54
0x180014b0e  xor     ecx, ecx
0x180014b10  mov     [rbp+1D0h+pszDest], cx
0x180014b14  cmp     [rbx+14h], ecx
0x180014b17  jz      loc_180014C54
0x180014b1d  test    byte ptr [rbx+20h], 10h
0x180014b21  mov     esi, 0C8h
0x180014b26  jz      short loc_180014B8D
0x180014b28  lea     rdi, [rbx+0F4h]
0x180014b2f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014b33  inc     rax
0x180014b36  cmp     [rdi+rax*2], cx
0x180014b3a  jnz     short loc_180014B33
0x180014b3c  lea     rcx, [rdi+rax*2]
0x180014b40  cmp     rcx, rdi
0x180014b43  jbe     short loc_180014B76
0x180014b45  movzx   eax, word ptr [rcx]
0x180014b48  sub     ax, 2Fh ; '/'
0x180014b4c  cmp     ax, 2Dh ; '-'
0x180014b50  ja      short loc_180014B62
0x180014b52  mov     rdx, 200000000801h
0x180014b5c  bt      rdx, rax
0x180014b60  jb      short loc_180014B76
0x180014b62  mov     rdx, rcx; lpszCurrent
0x180014b65  mov     rcx, rdi; lpszStart
0x180014b68  call    cs:__imp_CharPrevW
0x180014b6e  mov     rcx, rax
0x180014b71  cmp     rax, rdi
0x180014b74  ja      short loc_180014B45
0x180014b76  cmp     rcx, rdi
0x180014b79  lea     r8, [rcx+2]
0x180014b7d  mov     rdx, rsi; cchDest
0x180014b80  cmovbe  r8, rcx; pszSrc
0x180014b84  lea     rcx, [rbp+1D0h+pszDest]; pszDest
0x180014b88  call    StringCchCopyW
0x180014b8d  test    byte ptr [rbx+20h], 60h
0x180014b91  jz      short loc_180014BA6
0x180014b93  lea     r8, asc_18001933C; " ("
0x180014b9a  mov     rdx, rsi; cchDest
0x180014b9d  lea     rcx, [rbp+1D0h+pszDest]; pszDest
0x180014ba1  call    StringCchCatW
0x180014ba6  test    byte ptr [rbx+20h], 20h
0x180014baa  mov     edi, 28h ; '('
0x180014baf  jz      short loc_180014C02
0x180014bb1  mov     rcx, [rbx]; hWnd
0x180014bb4  lea     r9, [rsp+2D0h+lParam]; lParam
0x180014bb9  mov     r8d, edi; wParam
0x180014bbc  mov     edx, 4CAh; Msg
0x180014bc1  call    cs:__imp_SendMessageW
0x180014bc7  test    byte ptr [rbx+20h], 40h
0x180014bcb  lea     rcx, [rsp+2D0h+pszSrc]; pszDest
0x180014bd0  mov     edx, edi; cchDest
0x180014bd2  jz      short loc_180014BE7
0x180014bd4  lea     r9, [rsp+2D0h+lParam]
0x180014bd9  lea     r8, aS; "%s - "
0x180014be0  call    StringCchPrintfW
0x180014be5  jmp     short loc_180014BF1
0x180014be7  lea     r8, [rsp+2D0h+lParam]; pszSrc
0x180014bec  call    StringCchCopyW
0x180014bf1  lea     r8, [rsp+2D0h+pszSrc]; pszSrc
0x180014bf6  mov     rdx, rsi; cchDest
0x180014bf9  lea     rcx, [rbp+1D0h+pszDest]; pszDest
0x180014bfd  call    StringCchCatW
0x180014c02  test    byte ptr [rbx+20h], 40h
0x180014c06  jz      short loc_180014C2E
0x180014c08  mov     r9d, edi
0x180014c0b  lea     r8, [rbp+1D0h+var_210]
0x180014c0f  lea     rdx, szStatusMode; "status mode"
0x180014c16  mov     rcx, rbx
0x180014c19  call    MCIWndGet
0x180014c1e  lea     r8, [rbp+1D0h+var_210]; pszSrc
0x180014c22  mov     rdx, rsi; cchDest
0x180014c25  lea     rcx, [rbp+1D0h+pszDest]; pszDest
0x180014c29  call    StringCchCatW
0x180014c2e  test    byte ptr [rbx+20h], 60h
0x180014c32  jz      short loc_180014C47
0x180014c34  lea     r8, asc_180019354; ")"
0x180014c3b  mov     rdx, rsi; cchDest
0x180014c3e  lea     rcx, [rbp+1D0h+pszDest]; pszDest
0x180014c42  call    StringCchCatW
0x180014c47  mov     rcx, [rbx]; hWnd
0x180014c4a  lea     rdx, [rbp+1D0h+pszDest]; lpString
0x180014c4e  call    cs:__imp_SetWindowTextW
0x180014c54  mov     rcx, [rbp+1D0h+var_30]
0x180014c5b  xor     rcx, rsp; StackCookie
0x180014c5e  call    __security_check_cookie
0x180014c63  add     rsp, 2B8h
0x180014c6a  pop     rdi
0x180014c6b  pop     rsi
0x180014c6c  pop     rbx
0x180014c6d  pop     rbp
0x180014c6e  retn
```
