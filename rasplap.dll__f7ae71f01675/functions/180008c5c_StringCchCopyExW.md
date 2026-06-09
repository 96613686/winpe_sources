# StringCchCopyExW

- ea: `0x180008c5c`
- end: `0x180008dd6`
- name: `StringCchCopyExW`
- size: `378`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc, STRSAFE_LPWSTR *ppszDestEnd, size_t *pcchRemaining, DWORD dwFlags)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180008b94`
- `0x1800090f4`
- `0x18000ae90`

## callees

- `0x180008c5c`
- `0x180008f78`
- `0x180008ff4`
- `0x180009020`
- `0x1800090c4`

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
  size_t v9; // rdx
  wchar_t *v10; // rcx
  int v11; // ebx
  const wchar_t *v12; // r8
  wchar_t *v13; // r15
  size_t v14; // rsi
  const wchar_t *v15; // rax
  HRESULT v16; // eax
  size_t v17; // rcx
  size_t *v19; // [rsp+20h] [rbp-68h]
  STRSAFE_LPWSTR ppszDestEnda; // [rsp+30h] [rbp-58h] BYREF
  size_t pcchNewDestLength[10]; // [rsp+38h] [rbp-50h] BYREF

  v11 = StringExValidateDestW(pszDest, cchDest, (const size_t)pszSrc, dwFlags);
  if ( v11 < 0 )
  {
    if ( cchDest )
      *v10 = 0;
  }
  else
  {
    ppszDestEnda = v10;
    v13 = v10;
    pcchNewDestLength[0] = v9;
    v14 = v9;
    if ( (dwFlags & 0x100) != 0 )
    {
      v15 = &Data;
      if ( v12 )
        v15 = v12;
      v12 = v15;
    }
    if ( (dwFlags & 0xFFFFE000) != 0 )
    {
      v11 = -2147024809;
      if ( cchDest )
        *v10 = 0;
    }
    else if ( cchDest )
    {
      pcchNewDestLength[0] = 0;
      v16 = StringCopyWorkerW_0(v10, v9, pcchNewDestLength, v12, (size_t)v19);
      v17 = pcchNewDestLength[0];
      v11 = v16;
      v14 -= pcchNewDestLength[0];
      pcchNewDestLength[0] = v14;
      v13 = &pszDest[v17];
      ppszDestEnda = v13;
      if ( v16 >= 0 )
      {
        if ( (dwFlags & 0x200) != 0 && v14 > 1 )
          StringExHandleFillBehindNullW(&pszDest[v17], 2 * v14, dwFlags);
        goto LABEL_14;
      }
    }
    else
    {
      v11 = 0;
      if ( !*v12 )
      {
LABEL_14:
        if ( ppszDestEnd )
          *ppszDestEnd = v13;
        if ( pcchRemaining )
          *pcchRemaining = v14;
        return v11;
      }
      v11 = pszDest != 0 ? -2147024774 : -2147024809;
    }
    if ( (dwFlags & 0x1C00) != 0 && cchDest )
    {
      StringExHandleOtherFlagsW(pszDest, 2 * cchDest, (size_t)v12, &ppszDestEnda, pcchNewDestLength, dwFlags);
      v13 = ppszDestEnda;
      v14 = pcchNewDestLength[0];
    }
    if ( (int)(v11 + 0x80000000) < 0 || v11 == -2147024774 )
      goto LABEL_14;
  }
  return v11;
}

```

## disassembly

```asm
0x180008c5c  push    rbx
0x180008c5e  push    rbp
0x180008c5f  push    rsi
0x180008c60  push    rdi
0x180008c61  push    r12
0x180008c63  push    r13
0x180008c65  push    r14
0x180008c67  push    r15
0x180008c69  sub     rsp, 48h
0x180008c6d  mov     ebp, [rsp+88h+dwFlags]
0x180008c74  mov     r12, r9
0x180008c77  mov     r9d, ebp; dwFlags
0x180008c7a  mov     rdi, rdx
0x180008c7d  mov     r14, rcx
0x180008c80  call    StringExValidateDestW
0x180008c85  xor     r13d, r13d
0x180008c88  mov     ebx, eax
0x180008c8a  test    eax, eax
0x180008c8c  js      loc_180008DBA
0x180008c92  mov     [rsp+88h+ppszDestEnd], rcx
0x180008c97  mov     r15, rcx
0x180008c9a  mov     [rsp+88h+pcchNewDestLength], rdx
0x180008c9f  mov     rsi, rdx
0x180008ca2  bt      ebp, 8
0x180008ca6  jnb     short loc_180008CB9
0x180008ca8  test    r8, r8
0x180008cab  lea     rax, Data
0x180008cb2  cmovnz  rax, r8
0x180008cb6  mov     r8, rax; cchOriginalDestLength
0x180008cb9  test    ebp, 0FFFFE000h
0x180008cbf  jz      short loc_180008D3F
0x180008cc1  mov     ebx, 80070057h
0x180008cc6  test    rdi, rdi
0x180008cc9  jz      short loc_180008CCF
0x180008ccb  mov     [rcx], r13w
0x180008ccf  test    ebp, 1C00h
0x180008cd5  jz      short loc_180008D05
0x180008cd7  test    rdi, rdi
0x180008cda  jz      short loc_180008D05
0x180008cdc  lea     rax, [rsp+88h+pcchNewDestLength]
0x180008ce1  mov     [rsp+88h+var_60], ebp; dwFlags
0x180008ce5  lea     rdx, [rdi+rdi]; cbDest
0x180008ce9  mov     [rsp+88h+var_68], rax; pcchRemaining
0x180008cee  lea     r9, [rsp+88h+ppszDestEnd]; ppszDestEnd
0x180008cf3  mov     rcx, r14; pszDest
0x180008cf6  call    StringExHandleOtherFlagsW
0x180008cfb  mov     r15, [rsp+88h+ppszDestEnd]
0x180008d00  mov     rsi, [rsp+88h+pcchNewDestLength]
0x180008d05  mov     ecx, 80000000h
0x180008d0a  lea     eax, [rbx+rcx]
0x180008d0d  test    ecx, eax
0x180008d0f  jnz     short loc_180008D1D
0x180008d11  cmp     ebx, 8007007Ah
0x180008d17  jnz     loc_180008DC3
0x180008d1d  test    r12, r12
0x180008d20  jz      short loc_180008D26
0x180008d22  mov     [r12], r15
0x180008d26  mov     rax, [rsp+88h+pcchRemaining]
0x180008d2e  test    rax, rax
0x180008d31  jz      loc_180008DC3
0x180008d37  mov     [rax], rsi
0x180008d3a  jmp     loc_180008DC3
0x180008d3f  test    rdi, rdi
0x180008d42  jnz     short loc_180008D64
0x180008d44  mov     ebx, r13d
0x180008d47  cmp     [r8], r13w
0x180008d4b  jz      short loc_180008D1D
0x180008d4d  mov     rax, r14
0x180008d50  mov     ebx, 80070057h
0x180008d55  neg     rax
0x180008d58  sbb     ecx, ecx
0x180008d5a  and     ecx, 23h
0x180008d5d  add     ebx, ecx
0x180008d5f  jmp     loc_180008CCF
0x180008d64  mov     r9, r8; pszSrc
0x180008d67  mov     [rsp+88h+pcchNewDestLength], r13
0x180008d6c  lea     r8, [rsp+88h+pcchNewDestLength]; pcchNewDestLength
0x180008d71  call    StringCopyWorkerW_0
0x180008d76  mov     rcx, [rsp+88h+pcchNewDestLength]
0x180008d7b  mov     ebx, eax
0x180008d7d  sub     rsi, rcx
0x180008d80  mov     [rsp+88h+pcchNewDestLength], rsi
0x180008d85  lea     r15, [r14+rcx*2]
0x180008d89  mov     [rsp+88h+ppszDestEnd], r15
0x180008d8e  test    eax, eax
0x180008d90  js      loc_180008CCF
0x180008d96  bt      ebp, 9
0x180008d9a  jnb     short loc_180008D1D
0x180008d9c  cmp     rsi, 1
0x180008da0  jbe     loc_180008D1D
0x180008da6  lea     rdx, [rsi+rsi]; cbRemaining
0x180008daa  mov     r8d, ebp; dwFlags
0x180008dad  mov     rcx, r15; pszDestEnd
0x180008db0  call    StringExHandleFillBehindNullW
0x180008db5  jmp     loc_180008D1D
0x180008dba  test    rdi, rdi
0x180008dbd  jz      short loc_180008DC3
0x180008dbf  mov     [rcx], r13w
0x180008dc3  mov     eax, ebx
0x180008dc5  add     rsp, 48h
0x180008dc9  pop     r15
0x180008dcb  pop     r14
0x180008dcd  pop     r13
0x180008dcf  pop     r12
0x180008dd1  pop     rdi
0x180008dd2  pop     rsi
0x180008dd3  pop     rbp
0x180008dd4  pop     rbx
0x180008dd5  retn
```
