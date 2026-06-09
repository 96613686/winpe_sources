# StringCchPrintfExW

- ea: `0x180015a40`
- end: `0x180015bd4`
- name: `StringCchPrintfExW`
- size: `404`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPWSTR *ppszDestEnd, size_t *pcchRemaining, DWORD dwFlags, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180014978`
- `0x180019770`
- `0x180019de4`
- `0x18001d538`
- `0x18001e3ac`

## callees

- `0x180015a40`
- `0x180015bdc`
- `0x18001dc0c`
- `0x18001dc38`

## import_xrefs

- `ntdll!_vsnwprintf` at `0x180015b51`
- `ntdll!_vsnwprintf` at `0x180015b51`

## pseudocode

```c
HRESULT StringCchPrintfExW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        STRSAFE_LPWSTR *ppszDestEnd,
        size_t *pcchRemaining,
        DWORD dwFlags,
        STRSAFE_LPCWSTR pszFormat,
        ...)
{
  size_t v8; // rdx
  wchar_t *v9; // rcx
  int v10; // ebx
  size_t *v11; // r10
  const wchar_t *v12; // r8
  wchar_t *v13; // r12
  size_t v14; // r14
  unsigned __int64 v15; // rdi
  int v16; // eax
  STRSAFE_LPWSTR ppszDestEnda; // [rsp+30h] [rbp-18h] BYREF
  size_t v19[2]; // [rsp+38h] [rbp-10h] BYREF
  va_list Args; // [rsp+C0h] [rbp+78h] BYREF

  va_start(Args, pszFormat);
  v10 = StringExValidateDestW(pszDest, cchDest, (const size_t)ppszDestEnd, dwFlags);
  if ( v10 < 0 )
  {
    if ( cchDest )
      *v9 = 0;
    return v10;
  }
  v12 = pszFormat;
  v13 = v9;
  ppszDestEnda = v9;
  v14 = v8;
  v19[0] = v8;
  if ( (dwFlags & 0x100) != 0 && !pszFormat )
    v12 = (const wchar_t *)&LocaleName;
  if ( (dwFlags & 0xFFFFE000) != 0 )
  {
    v10 = -2147024809;
    if ( cchDest )
      *v9 = 0;
    goto LABEL_8;
  }
  if ( cchDest )
  {
    v19[0] = 0;
    v15 = v8 - 1;
    v16 = _vsnwprintf(v9, v8 - 1, v12, Args);
    if ( v16 < 0 || v16 > v15 )
    {
      v10 = -2147024774;
    }
    else
    {
      v10 = 0;
      if ( v16 != v15 )
      {
        v15 = v16;
        goto LABEL_26;
      }
    }
    pszDest[v15] = 0;
LABEL_26:
    v14 -= v15;
    v13 = &pszDest[v15];
    ppszDestEnda = v13;
    v19[0] = v14;
    if ( v10 >= 0 )
    {
      if ( (dwFlags & 0x200) != 0 && v14 > 1 )
        StringExHandleFillBehindNullW(&pszDest[v15], 2 * v14, dwFlags);
      goto LABEL_12;
    }
    goto LABEL_8;
  }
  v10 = 0;
  if ( !*v12 )
    goto LABEL_13;
  v10 = pszDest != 0 ? -2147024774 : -2147024809;
LABEL_8:
  if ( (dwFlags & 0x1C00) != 0 && cchDest )
  {
    StringExHandleOtherFlagsW(pszDest, 2 * cchDest, (size_t)v12, &ppszDestEnda, v19, dwFlags);
    v13 = ppszDestEnda;
    v14 = v19[0];
  }
  if ( v10 == -2147024774 )
  {
LABEL_12:
    v11 = pcchRemaining;
LABEL_13:
    if ( ppszDestEnd )
      *ppszDestEnd = v13;
    if ( v11 )
      *v11 = v14;
  }
  return v10;
}

```

## disassembly

```asm
0x180015a40  mov     [rsp-40h+arg_18], r9
0x180015a45  mov     [rsp-40h+arg_10], r8
0x180015a4a  push    rbp
0x180015a4b  push    rbx
0x180015a4c  push    rsi
0x180015a4d  push    rdi
0x180015a4e  push    r12
0x180015a50  push    r13
0x180015a52  push    r14
0x180015a54  push    r15
0x180015a56  mov     rbp, rsp
0x180015a59  sub     rsp, 48h
0x180015a5d  mov     r13d, [rbp+dwFlags]
0x180015a61  mov     r10, r9
0x180015a64  mov     r9d, r13d; dwFlags
0x180015a67  mov     r15, rdx
0x180015a6a  mov     rsi, rcx
0x180015a6d  call    StringExValidateDestW
0x180015a72  xor     edi, edi
0x180015a74  mov     ebx, eax
0x180015a76  test    eax, eax
0x180015a78  js      loc_180015BB9
0x180015a7e  mov     r8, [rbp+pszFormat]
0x180015a82  mov     r12, rcx
0x180015a85  mov     [rbp+ppszDestEnd], rcx
0x180015a89  mov     r14, rdx
0x180015a8c  mov     [rbp+var_10], rdx
0x180015a90  bt      r13d, 8
0x180015a95  jnb     short loc_180015AA7
0x180015a97  test    r8, r8
0x180015a9a  jnz     short loc_180015AA7
0x180015a9c  lea     r8, LocaleName; Format
0x180015aa3  mov     [rbp+pszFormat], r8
0x180015aa7  test    r13d, 0FFFFE000h
0x180015aae  jz      short loc_180015B1E
0x180015ab0  mov     ebx, 80070057h
0x180015ab5  test    r15, r15
0x180015ab8  jz      short loc_180015ABD
0x180015aba  mov     [rcx], di
0x180015abd  test    r13d, 1C00h
0x180015ac4  jz      short loc_180015AF1
0x180015ac6  test    r15, r15
0x180015ac9  jz      short loc_180015AF1
0x180015acb  lea     rax, [rbp+var_10]
0x180015acf  mov     [rsp+48h+var_20], r13d; dwFlags
0x180015ad4  lea     rdx, [r15+r15]; cbDest
0x180015ad8  mov     [rsp+48h+pcchRemaining], rax; pcchRemaining
0x180015add  lea     r9, [rbp+ppszDestEnd]; ppszDestEnd
0x180015ae1  mov     rcx, rsi; pszDest
0x180015ae4  call    StringExHandleOtherFlagsW
0x180015ae9  mov     r12, [rbp+ppszDestEnd]
0x180015aed  mov     r14, [rbp+var_10]
0x180015af1  cmp     ebx, 8007007Ah
0x180015af7  jnz     loc_180015BC1
0x180015afd  mov     r10, [rbp+arg_18]
0x180015b01  mov     rax, [rbp+arg_10]
0x180015b05  test    rax, rax
0x180015b08  jz      short loc_180015B0D
0x180015b0a  mov     [rax], r12
0x180015b0d  test    r10, r10
0x180015b10  jz      loc_180015BC1
0x180015b16  mov     [r10], r14
0x180015b19  jmp     loc_180015BC1
0x180015b1e  test    r15, r15
0x180015b21  jnz     short loc_180015B42
0x180015b23  mov     ebx, edi
0x180015b25  cmp     [r8], di
0x180015b29  jz      short loc_180015B01
0x180015b2b  mov     rax, rsi
0x180015b2e  mov     ebx, 80070057h
0x180015b33  neg     rax
0x180015b36  sbb     ecx, ecx
0x180015b38  and     ecx, 23h
0x180015b3b  add     ebx, ecx
0x180015b3d  jmp     loc_180015ABD
0x180015b42  mov     [rbp+var_10], rdi
0x180015b46  lea     r9, [rbp+Args]; Args
0x180015b4a  lea     rdi, [rdx-1]
0x180015b4e  mov     rdx, rdi; BufferCount
0x180015b51  call    cs:__imp__vsnwprintf
0x180015b57  test    eax, eax
0x180015b59  js      short loc_180015B6E
0x180015b5b  cdqe
0x180015b5d  cmp     rax, rdi
0x180015b60  ja      short loc_180015B6E
0x180015b62  xor     ebx, ebx
0x180015b64  cmp     rax, rdi
0x180015b67  jz      short loc_180015B73
0x180015b69  mov     rdi, rax
0x180015b6c  jmp     short loc_180015B79
0x180015b6e  mov     ebx, 8007007Ah
0x180015b73  xor     eax, eax
0x180015b75  mov     [rsi+rdi*2], ax
0x180015b79  sub     r14, rdi
0x180015b7c  lea     r12, [rsi+rdi*2]
0x180015b80  mov     [rbp+ppszDestEnd], r12
0x180015b84  mov     [rbp+var_10], r14
0x180015b88  test    ebx, ebx
0x180015b8a  js      loc_180015ABD
0x180015b90  bt      r13d, 9
0x180015b95  jnb     loc_180015AFD
0x180015b9b  cmp     r14, 1
0x180015b9f  jbe     loc_180015AFD
0x180015ba5  lea     rdx, [r14+r14]; cbRemaining
0x180015ba9  mov     r8d, r13d; dwFlags
0x180015bac  mov     rcx, r12; pszDestEnd
0x180015baf  call    StringExHandleFillBehindNullW
0x180015bb4  jmp     loc_180015AFD
0x180015bb9  test    r15, r15
0x180015bbc  jz      short loc_180015BC1
0x180015bbe  mov     [rcx], di
0x180015bc1  mov     eax, ebx
0x180015bc3  add     rsp, 48h
0x180015bc7  pop     r15
0x180015bc9  pop     r14
0x180015bcb  pop     r13
0x180015bcd  pop     r12
0x180015bcf  pop     rdi
0x180015bd0  pop     rsi
0x180015bd1  pop     rbx
0x180015bd2  pop     rbp
0x180015bd3  retn
```
