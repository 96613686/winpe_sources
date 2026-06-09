# StringCchCopyExW

- ea: `0x180003b40`
- end: `0x180003cf1`
- name: `StringCchCopyExW`
- size: `433`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc, STRSAFE_LPWSTR *ppszDestEnd, size_t *pcchRemaining, DWORD dwFlags)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180003cf8`
- `0x1800086bc`
- `0x1800087c4`
- `0x18000892c`
- `0x180008bc0`

## callees

- `0x180003b40`
- `0x18000a16e`

## pseudocode

```c
HRESULT __stdcall StringCchCopyExW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        STRSAFE_LPCWSTR pszSrc,
        STRSAFE_LPWSTR *ppszDestEnd,
        size_t *pcchRemaining,
        DWORD dwFlags)
{
  __int64 v7; // rcx
  HRESULT v8; // edi
  size_t v9; // r14
  size_t v10; // r9
  STRSAFE_LPWSTR v11; // rax
  __int64 v12; // r11
  STRSAFE_LPWSTR v13; // rcx
  __int64 v14; // r10
  size_t v15; // rdx
  bool v16; // cf
  bool v17; // zf

  v7 = 2147483646;
  if ( (dwFlags & 0x100) == 0 )
  {
    if ( cchDest - 1 <= 0x7FFFFFFE )
      goto LABEL_8;
LABEL_36:
    v8 = -2147024809;
    v17 = cchDest == 0;
LABEL_37:
    if ( !v17 )
      *pszDest = 0;
    return v8;
  }
  if ( !pszDest && cchDest || cchDest > 0x7FFFFFFF )
    goto LABEL_36;
  if ( !pszSrc )
    pszSrc = (STRSAFE_LPCWSTR)&dword_18000D4AC;
LABEL_8:
  if ( (dwFlags & 0xFFFFE000) != 0 )
  {
    v8 = -2147024809;
    if ( cchDest )
      *pszDest = 0;
    goto LABEL_11;
  }
  if ( !cchDest )
  {
    v8 = 0;
    if ( !*pszSrc )
      return v8;
    v8 = pszDest != 0 ? -2147024774 : -2147024809;
    goto LABEL_11;
  }
  v10 = cchDest;
  v11 = pszDest;
  v12 = 0;
  do
  {
    if ( !v7 )
      break;
    if ( !*pszSrc )
      break;
    *v11++ = *pszSrc++;
    --v7;
    ++v12;
    --v10;
  }
  while ( v10 );
  v13 = v11 - 1;
  v14 = v12 - 1;
  if ( v10 )
  {
    v13 = v11;
    v14 = v12;
  }
  *v13 = 0;
  v8 = v10 == 0 ? 0x8007007A : 0;
  if ( !v10 )
  {
LABEL_11:
    if ( (dwFlags & 0x1C00) == 0 || !cchDest )
      return v8;
    v9 = (2 * cchDest) >> 1;
    if ( v9 && (dwFlags & 0x1000) != 0 )
      *pszDest = 0;
    if ( (dwFlags & 0x400) != 0 && (memset_0(pszDest, (unsigned __int8)dwFlags, 2 * cchDest), (_BYTE)dwFlags) )
    {
      if ( !v9 )
        return v8;
      pszDest[v9 - 1] = 0;
    }
    else if ( !v9 )
    {
      return v8;
    }
    v17 = (dwFlags & 0x800) == 0;
    goto LABEL_37;
  }
  if ( (dwFlags & 0x200) != 0 )
  {
    v16 = cchDest == v14;
    v15 = cchDest - v14;
    if ( !v16 && v15 != 1 && 2 * v15 > 2 )
      memset_0(&pszDest[v14 + 1], (unsigned __int8)dwFlags, 2 * v15 - 2);
  }
  return v8;
}

```

## disassembly

```asm
0x180003b40  push    rbx
0x180003b42  push    rbp
0x180003b43  push    rsi
0x180003b44  push    rdi
0x180003b45  push    r14
0x180003b47  push    r15
0x180003b49  sub     rsp, 28h
0x180003b4d  mov     ebp, [rsp+58h+dwFlags]
0x180003b54  xor     r15d, r15d
0x180003b57  mov     rsi, rcx
0x180003b5a  mov     ecx, 7FFFFFFEh
0x180003b5f  bt      ebp, 8
0x180003b63  jnb     short loc_180003B8E
0x180003b65  test    rsi, rsi
0x180003b68  jnz     short loc_180003B73
0x180003b6a  test    rdx, rdx
0x180003b6d  jnz     loc_180003CD4
0x180003b73  cmp     rdx, 7FFFFFFFh
0x180003b7a  ja      loc_180003CD4
0x180003b80  test    r8, r8
0x180003b83  jnz     short loc_180003B9B
0x180003b85  lea     r8, dword_18000D4AC
0x180003b8c  jmp     short loc_180003B9B
0x180003b8e  lea     rax, [rdx-1]
0x180003b92  cmp     rax, rcx
0x180003b95  ja      loc_180003CD4
0x180003b9b  test    ebp, 0FFFFE000h
0x180003ba1  jz      short loc_180003C0F
0x180003ba3  mov     edi, 80070057h
0x180003ba8  test    rdx, rdx
0x180003bab  jz      short loc_180003BB1
0x180003bad  mov     [rsi], r15w
0x180003bb1  test    ebp, 1C00h
0x180003bb7  jz      loc_180003CE2
0x180003bbd  test    rdx, rdx
0x180003bc0  jz      loc_180003CE2
0x180003bc6  lea     r8, [rdx+rdx]; Size
0x180003bca  mov     r14, r8
0x180003bcd  shr     r14, 1
0x180003bd0  jz      short loc_180003BDC
0x180003bd2  bt      ebp, 0Ch
0x180003bd6  jnb     short loc_180003BDC
0x180003bd8  mov     [rsi], r15w
0x180003bdc  bt      ebp, 0Ah
0x180003be0  jnb     loc_180003CC7
0x180003be6  movzx   edx, bpl; Val
0x180003bea  mov     rcx, rsi; void *
0x180003bed  call    memset_0
0x180003bf2  test    bpl, bpl
0x180003bf5  jz      loc_180003CC7
0x180003bfb  test    r14, r14
0x180003bfe  jz      loc_180003CE2
0x180003c04  mov     [rsi+r14*2-2], r15w
0x180003c0a  jmp     loc_180003CCC
0x180003c0f  test    rdx, rdx
0x180003c12  jnz     short loc_180003C38
0x180003c14  mov     edi, r15d
0x180003c17  cmp     [r8], r15w
0x180003c1b  jz      loc_180003CE2
0x180003c21  mov     rax, rsi
0x180003c24  mov     edi, 80070057h
0x180003c29  neg     rax
0x180003c2c  sbb     ecx, ecx
0x180003c2e  and     ecx, 23h
0x180003c31  add     edi, ecx
0x180003c33  jmp     loc_180003BB1
0x180003c38  mov     r9, rdx
0x180003c3b  mov     rax, rsi
0x180003c3e  mov     r11, r15
0x180003c41  test    rcx, rcx
0x180003c44  jz      short loc_180003C68
0x180003c46  movzx   r10d, word ptr [r8]
0x180003c4a  test    r10w, r10w
0x180003c4e  jz      short loc_180003C68
0x180003c50  mov     [rax], r10w
0x180003c54  add     r8, 2
0x180003c58  add     rax, 2
0x180003c5c  dec     rcx
0x180003c5f  inc     r11
0x180003c62  sub     r9, 1
0x180003c66  jnz     short loc_180003C41
0x180003c68  test    r9, r9
0x180003c6b  lea     rcx, [rax-2]
0x180003c6f  lea     r10, [r11-1]
0x180003c73  cmovnz  rcx, rax
0x180003c77  cmovnz  r10, r11
0x180003c7b  mov     rax, r9
0x180003c7e  neg     rax
0x180003c81  sbb     edi, edi
0x180003c83  mov     [rcx], r15w
0x180003c87  not     edi
0x180003c89  and     edi, 8007007Ah
0x180003c8f  test    r9, r9
0x180003c92  jz      loc_180003BB1
0x180003c98  bt      ebp, 9
0x180003c9c  jnb     short loc_180003CE2
0x180003c9e  sub     rdx, r10
0x180003ca1  cmp     rdx, 1
0x180003ca5  jbe     short loc_180003CE2
0x180003ca7  lea     r8, [rdx+rdx]
0x180003cab  cmp     r8, 2
0x180003caf  jbe     short loc_180003CE2
0x180003cb1  inc     r10
0x180003cb4  movzx   edx, bpl; Val
0x180003cb8  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180003cbc  lea     rcx, [rsi+r10*2]; void *
0x180003cc0  call    memset_0
0x180003cc5  jmp     short loc_180003CE2
0x180003cc7  test    r14, r14
0x180003cca  jz      short loc_180003CE2
0x180003ccc  test    ebp, 800h
0x180003cd2  jmp     short loc_180003CDC
0x180003cd4  mov     edi, 80070057h
0x180003cd9  test    rdx, rdx
0x180003cdc  jz      short loc_180003CE2
0x180003cde  mov     [rsi], r15w
0x180003ce2  mov     eax, edi
0x180003ce4  add     rsp, 28h
0x180003ce8  pop     r15
0x180003cea  pop     r14
0x180003cec  pop     rdi
0x180003ced  pop     rsi
0x180003cee  pop     rbp
0x180003cef  pop     rbx
0x180003cf0  retn
```
