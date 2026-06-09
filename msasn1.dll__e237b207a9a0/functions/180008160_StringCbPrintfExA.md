# StringCbPrintfExA

- ea: `0x180008160`
- end: `0x18000830d`
- name: `StringCbPrintfExA`
- size: `429`
- prototype: `HRESULT(STRSAFE_LPSTR pszDest, size_t cbDest, STRSAFE_LPSTR *ppszDestEnd, size_t *pcbRemaining, DWORD dwFlags, STRSAFE_LPCSTR pszFormat, ...)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180007ef4`
- `0x180008344`

## callees

- `0x180008160`
- `0x180008314`
- `0x180009b98`
- `0x18000a970`
- `0x18000a99c`

## pseudocode

```c
HRESULT StringCbPrintfExA(
        STRSAFE_LPSTR pszDest,
        size_t cbDest,
        STRSAFE_LPSTR *ppszDestEnd,
        size_t *pcbRemaining,
        DWORD dwFlags,
        STRSAFE_LPCSTR pszFormat,
        ...)
{
  size_t v8; // rdx
  char *v9; // rcx
  int v10; // ebx
  size_t *v11; // r10
  const char *v12; // r8
  char *v13; // r12
  size_t v14; // r14
  unsigned __int64 v15; // rdi
  int v16; // eax
  STRSAFE_LPSTR ppszDestEnda; // [rsp+30h] [rbp-18h] BYREF
  size_t pcchRemaining[2]; // [rsp+38h] [rbp-10h] BYREF
  va_list ArgList; // [rsp+C0h] [rbp+78h] BYREF

  va_start(ArgList, pszFormat);
  v10 = StringExValidateDestA(pszDest, cbDest, (const size_t)ppszDestEnd, dwFlags);
  if ( v10 < 0 )
  {
    if ( cbDest )
      *v9 = 0;
  }
  else
  {
    v12 = pszFormat;
    v13 = v9;
    ppszDestEnda = v9;
    v14 = v8;
    pcchRemaining[0] = v8;
    if ( (dwFlags & 0x100) != 0 && !pszFormat )
      v12 = (const char *)word_18000C7B2;
    if ( (dwFlags & 0xFFFFE000) != 0 )
    {
      v10 = -2147024809;
      if ( cbDest )
        *v9 = 0;
    }
    else if ( cbDest )
    {
      v15 = v8 - 1;
      pcchRemaining[0] = 0;
      v16 = vsnprintf(v9, v8 - 1, v12, ArgList);
      if ( v16 < 0 || v16 > v15 )
      {
        pszDest[v15] = 0;
        v10 = -2147024774;
      }
      else
      {
        v10 = 0;
        if ( v16 == v15 )
          pszDest[v15] = 0;
        else
          v15 = v16;
      }
      v14 -= v15;
      v13 = &pszDest[v15];
      ppszDestEnda = &pszDest[v15];
      pcchRemaining[0] = v14;
      if ( v10 >= 0 )
      {
        if ( (dwFlags & 0x200) != 0 && v14 > 1 )
          StringExHandleFillBehindNullA(&pszDest[v15], v14, dwFlags);
        goto LABEL_17;
      }
    }
    else
    {
      v10 = 0;
      if ( !*v12 )
        goto LABEL_18;
      v10 = pszDest != 0 ? -2147024774 : -2147024809;
    }
    if ( (dwFlags & 0x1C00) != 0 && cbDest )
    {
      StringExHandleOtherFlagsA(pszDest, cbDest, (size_t)v12, &ppszDestEnda, pcchRemaining, dwFlags);
      v13 = ppszDestEnda;
      v14 = pcchRemaining[0];
    }
    if ( v10 == -2147024774 )
    {
LABEL_17:
      v11 = pcbRemaining;
LABEL_18:
      if ( ppszDestEnd )
        *ppszDestEnd = v13;
      if ( v11 )
        *v11 = v14;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180008160  mov     [rsp-40h+arg_18], r9
0x180008165  mov     [rsp-40h+arg_10], r8
0x18000816a  push    rbp
0x18000816b  push    rbx
0x18000816c  push    rsi
0x18000816d  push    rdi
0x18000816e  push    r12
0x180008170  push    r13
0x180008172  push    r14
0x180008174  push    r15
0x180008176  mov     rbp, rsp
0x180008179  sub     rsp, 48h
0x18000817d  mov     r13d, [rbp+dwFlags]
0x180008181  mov     r10, r9
0x180008184  mov     r9d, r13d; dwFlags
0x180008187  mov     r15, rdx
0x18000818a  mov     rsi, rcx
0x18000818d  call    StringExValidateDestA
0x180008192  mov     ebx, eax
0x180008194  test    eax, eax
0x180008196  js      loc_180008291
0x18000819c  mov     r8, [rbp+pszFormat]; Format
0x1800081a0  mov     r12, rcx
0x1800081a3  mov     [rbp+ppszDestEnd], rcx
0x1800081a7  mov     r14, rdx
0x1800081aa  mov     [rbp+var_10], rdx
0x1800081ae  bt      r13d, 8
0x1800081b3  jb      loc_18000829B
0x1800081b9  test    r13d, 0FFFFE000h
0x1800081c0  jnz     loc_1800082B4
0x1800081c6  test    r15, r15
0x1800081c9  jz      loc_1800082CA
0x1800081cf  lea     rdi, [rdx-1]
0x1800081d3  mov     [rbp+var_10], 0
0x1800081db  mov     rdx, rdi; BufferCount
0x1800081de  lea     r9, [rbp+ArgList]; ArgList
0x1800081e2  call    _vsnprintf
0x1800081e7  test    eax, eax
0x1800081e9  js      short loc_180008250
0x1800081eb  cdqe
0x1800081ed  cmp     rax, rdi
0x1800081f0  ja      short loc_180008250
0x1800081f2  xor     ebx, ebx
0x1800081f4  cmp     rax, rdi
0x1800081f7  jz      loc_1800082E8
0x1800081fd  mov     rdi, rax
0x180008200  sub     r14, rdi
0x180008203  lea     r12, [rdi+rsi]
0x180008207  mov     [rbp+ppszDestEnd], r12
0x18000820b  mov     [rbp+var_10], r14
0x18000820f  test    ebx, ebx
0x180008211  jns     short loc_18000825B
0x180008213  test    r13d, 1C00h
0x18000821a  jz      short loc_180008246
0x18000821c  test    r15, r15
0x18000821f  jz      short loc_180008246
0x180008221  lea     rax, [rbp+var_10]
0x180008225  mov     [rsp+48h+var_20], r13d; dwFlags
0x18000822a  lea     r9, [rbp+ppszDestEnd]; ppszDestEnd
0x18000822e  mov     [rsp+48h+pcchRemaining], rax; pcchRemaining
0x180008233  mov     rdx, r15; cbDest
0x180008236  mov     rcx, rsi; pszDest
0x180008239  call    StringExHandleOtherFlagsA
0x18000823e  mov     r12, [rbp+ppszDestEnd]
0x180008242  mov     r14, [rbp+var_10]
0x180008246  cmp     ebx, 8007007Ah
0x18000824c  jnz     short loc_18000827E
0x18000824e  jmp     short loc_180008266
0x180008250  mov     byte ptr [rdi+rsi], 0
0x180008254  mov     ebx, 8007007Ah
0x180008259  jmp     short loc_180008200
0x18000825b  bt      r13d, 9
0x180008260  jb      loc_1800082F0
0x180008266  mov     r10, [rbp+arg_18]
0x18000826a  mov     rax, [rbp+arg_10]
0x18000826e  test    rax, rax
0x180008271  jz      short loc_180008276
0x180008273  mov     [rax], r12
0x180008276  test    r10, r10
0x180008279  jz      short loc_18000827E
0x18000827b  mov     [r10], r14
0x18000827e  mov     eax, ebx
0x180008280  add     rsp, 48h
0x180008284  pop     r15
0x180008286  pop     r14
0x180008288  pop     r13
0x18000828a  pop     r12
0x18000828c  pop     rdi
0x18000828d  pop     rsi
0x18000828e  pop     rbx
0x18000828f  pop     rbp
0x180008290  retn
0x180008291  test    r15, r15
0x180008294  jz      short loc_18000827E
0x180008296  mov     byte ptr [rcx], 0
0x180008299  jmp     short loc_18000827E
0x18000829b  test    r8, r8
0x18000829e  jnz     loc_1800081B9
0x1800082a4  lea     r8, word_18000C7B2
0x1800082ab  mov     [rbp+pszFormat], r8
0x1800082af  jmp     loc_1800081B9
0x1800082b4  mov     ebx, 80070057h
0x1800082b9  test    r15, r15
0x1800082bc  jz      loc_180008213
0x1800082c2  mov     byte ptr [rcx], 0
0x1800082c5  jmp     loc_180008213
0x1800082ca  xor     ebx, ebx
0x1800082cc  cmp     [r8], bl
0x1800082cf  jz      short loc_18000826A
0x1800082d1  mov     rax, rsi
0x1800082d4  mov     ebx, 80070057h
0x1800082d9  neg     rax
0x1800082dc  sbb     ecx, ecx
0x1800082de  and     ecx, 23h
0x1800082e1  add     ebx, ecx
0x1800082e3  jmp     loc_180008213
0x1800082e8  mov     [rdi+rsi], bl
0x1800082eb  jmp     loc_180008200
0x1800082f0  cmp     r14, 1
0x1800082f4  jbe     loc_180008266
0x1800082fa  mov     r8d, r13d; dwFlags
0x1800082fd  mov     rdx, r14; cbRemaining
0x180008300  mov     rcx, r12; pszDestEnd
0x180008303  call    StringExHandleFillBehindNullA
0x180008308  jmp     loc_180008266
```
