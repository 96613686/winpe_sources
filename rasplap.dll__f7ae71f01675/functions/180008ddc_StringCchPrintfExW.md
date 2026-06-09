# StringCchPrintfExW

- ea: `0x180008ddc`
- end: `0x180008f70`
- name: `StringCchPrintfExW`
- size: `404`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPWSTR *ppszDestEnd, size_t *pcchRemaining, DWORD dwFlags, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800089d8`
- `0x18000a2b0`

## callees

- `0x180008ddc`
- `0x180008ff4`
- `0x180009020`
- `0x1800090c4`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180008eed`
- `msvcrt!_vsnwprintf` at `0x180008eed`

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
    v12 = &Data;
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
0x180008ddc  mov     [rsp-40h+arg_18], r9
0x180008de1  mov     [rsp-40h+arg_10], r8
0x180008de6  push    rbp
0x180008de7  push    rbx
0x180008de8  push    rsi
0x180008de9  push    rdi
0x180008dea  push    r12
0x180008dec  push    r13
0x180008dee  push    r14
0x180008df0  push    r15
0x180008df2  mov     rbp, rsp
0x180008df5  sub     rsp, 48h
0x180008df9  mov     r13d, [rbp+dwFlags]
0x180008dfd  mov     r10, r9
0x180008e00  mov     r9d, r13d; dwFlags
0x180008e03  mov     r15, rdx
0x180008e06  mov     rsi, rcx
0x180008e09  call    StringExValidateDestW
0x180008e0e  xor     edi, edi
0x180008e10  mov     ebx, eax
0x180008e12  test    eax, eax
0x180008e14  js      loc_180008F55
0x180008e1a  mov     r8, [rbp+pszFormat]
0x180008e1e  mov     r12, rcx
0x180008e21  mov     [rbp+ppszDestEnd], rcx
0x180008e25  mov     r14, rdx
0x180008e28  mov     [rbp+var_10], rdx
0x180008e2c  bt      r13d, 8
0x180008e31  jnb     short loc_180008E43
0x180008e33  test    r8, r8
0x180008e36  jnz     short loc_180008E43
0x180008e38  lea     r8, Data; Format
0x180008e3f  mov     [rbp+pszFormat], r8
0x180008e43  test    r13d, 0FFFFE000h
0x180008e4a  jz      short loc_180008EBA
0x180008e4c  mov     ebx, 80070057h
0x180008e51  test    r15, r15
0x180008e54  jz      short loc_180008E59
0x180008e56  mov     [rcx], di
0x180008e59  test    r13d, 1C00h
0x180008e60  jz      short loc_180008E8D
0x180008e62  test    r15, r15
0x180008e65  jz      short loc_180008E8D
0x180008e67  lea     rax, [rbp+var_10]
0x180008e6b  mov     [rsp+48h+var_20], r13d; dwFlags
0x180008e70  lea     rdx, [r15+r15]; cbDest
0x180008e74  mov     [rsp+48h+pcchRemaining], rax; pcchRemaining
0x180008e79  lea     r9, [rbp+ppszDestEnd]; ppszDestEnd
0x180008e7d  mov     rcx, rsi; pszDest
0x180008e80  call    StringExHandleOtherFlagsW
0x180008e85  mov     r12, [rbp+ppszDestEnd]
0x180008e89  mov     r14, [rbp+var_10]
0x180008e8d  cmp     ebx, 8007007Ah
0x180008e93  jnz     loc_180008F5D
0x180008e99  mov     r10, [rbp+arg_18]
0x180008e9d  mov     rax, [rbp+arg_10]
0x180008ea1  test    rax, rax
0x180008ea4  jz      short loc_180008EA9
0x180008ea6  mov     [rax], r12
0x180008ea9  test    r10, r10
0x180008eac  jz      loc_180008F5D
0x180008eb2  mov     [r10], r14
0x180008eb5  jmp     loc_180008F5D
0x180008eba  test    r15, r15
0x180008ebd  jnz     short loc_180008EDE
0x180008ebf  mov     ebx, edi
0x180008ec1  cmp     [r8], di
0x180008ec5  jz      short loc_180008E9D
0x180008ec7  mov     rax, rsi
0x180008eca  mov     ebx, 80070057h
0x180008ecf  neg     rax
0x180008ed2  sbb     ecx, ecx
0x180008ed4  and     ecx, 23h
0x180008ed7  add     ebx, ecx
0x180008ed9  jmp     loc_180008E59
0x180008ede  mov     [rbp+var_10], rdi
0x180008ee2  lea     r9, [rbp+Args]; Args
0x180008ee6  lea     rdi, [rdx-1]
0x180008eea  mov     rdx, rdi; BufferCount
0x180008eed  call    cs:__imp__vsnwprintf
0x180008ef3  test    eax, eax
0x180008ef5  js      short loc_180008F0A
0x180008ef7  cdqe
0x180008ef9  cmp     rax, rdi
0x180008efc  ja      short loc_180008F0A
0x180008efe  xor     ebx, ebx
0x180008f00  cmp     rax, rdi
0x180008f03  jz      short loc_180008F0F
0x180008f05  mov     rdi, rax
0x180008f08  jmp     short loc_180008F15
0x180008f0a  mov     ebx, 8007007Ah
0x180008f0f  xor     eax, eax
0x180008f11  mov     [rsi+rdi*2], ax
0x180008f15  sub     r14, rdi
0x180008f18  lea     r12, [rsi+rdi*2]
0x180008f1c  mov     [rbp+ppszDestEnd], r12
0x180008f20  mov     [rbp+var_10], r14
0x180008f24  test    ebx, ebx
0x180008f26  js      loc_180008E59
0x180008f2c  bt      r13d, 9
0x180008f31  jnb     loc_180008E99
0x180008f37  cmp     r14, 1
0x180008f3b  jbe     loc_180008E99
0x180008f41  lea     rdx, [r14+r14]; cbRemaining
0x180008f45  mov     r8d, r13d; dwFlags
0x180008f48  mov     rcx, r12; pszDestEnd
0x180008f4b  call    StringExHandleFillBehindNullW
0x180008f50  jmp     loc_180008E99
0x180008f55  test    r15, r15
0x180008f58  jz      short loc_180008F5D
0x180008f5a  mov     [rcx], di
0x180008f5d  mov     eax, ebx
0x180008f5f  add     rsp, 48h
0x180008f63  pop     r15
0x180008f65  pop     r14
0x180008f67  pop     r13
0x180008f69  pop     r12
0x180008f6b  pop     rdi
0x180008f6c  pop     rsi
0x180008f6d  pop     rbx
0x180008f6e  pop     rbp
0x180008f6f  retn
```
