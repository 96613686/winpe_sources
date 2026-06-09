# KerbBuildScLogonInfo

- ea: `0x180006d58`
- end: `0x18000700b`
- name: `KerbBuildScLogonInfo`
- size: `691`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005068`

## callees

- `0x1800056d4`
- `0x180006d58`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180006e09`
- `KERNEL32!LocalAlloc` at `0x180006e09`
- `KERNEL32!LocalFree` at `0x180006e43`
- `KERNEL32!LocalFree` at `0x180006e43`
- `rtutils!TracePrintfExA` at `0x180006e33`
- `rtutils!TracePrintfExA` at `0x180006fbc`
- `rtutils!TracePrintfExA` at `0x180006ff5`
- `rtutils!TracePrintfExA` at `0x180006e33`
- `rtutils!TracePrintfExA` at `0x180006fbc`
- `rtutils!TracePrintfExA` at `0x180006ff5`

## string_xrefs

- `0x180006eb8`: `Failed StringCchCopyW`
- `0x180006fb0`: `Failed StringCchCopyW`

## pseudocode

```c
__int64 __fastcall KerbBuildScLogonInfo(
        const wchar_t *a1,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        int a5,
        HLOCAL *a6,
        _DWORD *a7)
{
  const wchar_t *v7; // r12
  const wchar_t *v8; // r15
  const wchar_t *v9; // r14
  const wchar_t *v10; // rbp
  __int64 v11; // rdi
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rax
  SIZE_T v16; // r13
  HLOCAL v17; // rax
  HRESULT v18; // ebx
  __int64 v20; // rdx
  wchar_t *v21; // r11
  __int64 v22; // r11
  DWORD v23; // ecx
  __int64 v24; // rax
  wchar_t *v25; // r11
  __int64 v26; // rdx
  __int64 v27; // r11
  __int64 v28; // rax
  wchar_t *v29; // r11
  __int64 v30; // rdx
  __int64 v31; // r11
  __int64 v32; // rax
  __int64 v33; // r9

  v7 = a4;
  v8 = a3;
  v9 = a2;
  v10 = a1;
  if ( a6 && a7 )
  {
    if ( !a1 )
      v10 = &Data;
    if ( !a2 )
      v9 = &Data;
    if ( !a3 )
      v8 = &Data;
    if ( !a4 )
      v7 = &Data;
    v11 = -1;
    v12 = -1;
    do
      ++v12;
    while ( v10[v12] );
    v13 = -1;
    do
      ++v13;
    while ( v9[v13] );
    v14 = -1;
    do
      ++v14;
    while ( v8[v14] );
    v15 = -1;
    do
      ++v15;
    while ( v7[v15] );
    v16 = (unsigned int)(2 * (v12 + v13 + v14 + v15) + 48);
    v17 = LocalAlloc(0x40u, v16);
    *a6 = v17;
    if ( !v17 )
    {
      v18 = -2147467259;
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "Failed LocalAlloc, *pLI");
      goto LABEL_22;
    }
    *((_DWORD *)v17 + 1) = 1;
    v20 = -1;
    *((_DWORD *)*a6 + 5) = a5;
    *((_QWORD *)*a6 + 1) = 0;
    *(_DWORD *)*a6 = v16;
    v21 = (wchar_t *)((char *)*a6 + 40);
    *((_DWORD *)*a6 + 6) = 0;
    do
      ++v20;
    while ( v10[v20] );
    v18 = StringCchCopyW(v21, v20 + 1, v10);
    if ( v18 >= 0 )
    {
      v24 = -1;
      do
        ++v24;
      while ( v10[v24] );
      v25 = (wchar_t *)(v22 + 2 * v24 + 2);
      v26 = -1;
      *((_DWORD *)*a6 + 7) = ((char *)v25 - (_BYTE *)*a6 - 40) >> 1;
      do
        ++v26;
      while ( v9[v26] );
      v18 = StringCchCopyW(v25, v26 + 1, v9);
      if ( v18 >= 0 )
      {
        v28 = -1;
        do
          ++v28;
        while ( v9[v28] );
        v29 = (wchar_t *)(v27 + 2 * v28 + 2);
        v30 = -1;
        *((_DWORD *)*a6 + 8) = ((char *)v29 - (_BYTE *)*a6 - 40) >> 1;
        do
          ++v30;
        while ( v8[v30] );
        v18 = StringCchCopyW(v29, v30 + 1, v8);
        if ( v18 >= 0 )
        {
          v32 = -1;
          do
            ++v32;
          while ( v8[v32] );
          v33 = v31 + 2 * v32;
          *((_DWORD *)*a6 + 9) = (v33 + 2 - (__int64)*a6 - 40) >> 1;
          do
            ++v11;
          while ( v7[v11] );
          v18 = StringCchCopyW((STRSAFE_LPWSTR)(v33 + 2), v11 + 1, v7);
          if ( v18 >= 0 )
          {
            v18 = 0;
            *a7 = v16;
            return (unsigned int)v18;
          }
        }
      }
      v23 = g_dwTraceId;
      if ( g_dwTraceId == -1 )
        goto LABEL_22;
    }
    else
    {
      v23 = g_dwTraceId;
      if ( g_dwTraceId == -1 )
        goto LABEL_22;
    }
    TracePrintfExA(v23, 0xCu, "Failed StringCchCopyW");
LABEL_22:
    if ( *a6 )
    {
      LocalFree(*a6);
      *a6 = 0;
    }
    return (unsigned int)v18;
  }
  v18 = -2147024809;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "Invalid arg(s)");
  if ( a6 )
    goto LABEL_22;
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180006d58  push    rbx
0x180006d5a  push    rbp
0x180006d5b  push    rsi
0x180006d5c  push    rdi
0x180006d5d  push    r12
0x180006d5f  push    r13
0x180006d61  push    r14
0x180006d63  push    r15
0x180006d65  sub     rsp, 28h
0x180006d69  mov     rsi, [rsp+68h+arg_28]
0x180006d71  xor     ebx, ebx
0x180006d73  mov     r12, r9
0x180006d76  mov     r15, r8
0x180006d79  mov     r14, rdx
0x180006d7c  mov     rbp, rcx
0x180006d7f  test    rsi, rsi
0x180006d82  jz      loc_180006FD9
0x180006d88  cmp     [rsp+68h+arg_30], rbx
0x180006d90  jz      loc_180006FD9
0x180006d96  test    rcx, rcx
0x180006d99  lea     rax, Data
0x180006da0  cmovz   rbp, rax
0x180006da4  test    rdx, rdx
0x180006da7  cmovz   r14, rax
0x180006dab  test    r8, r8
0x180006dae  cmovz   r15, rax
0x180006db2  test    r9, r9
0x180006db5  cmovz   r12, rax
0x180006db9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180006dbd  mov     r8, rdi
0x180006dc0  inc     r8
0x180006dc3  cmp     [rbp+r8*2+0], bx
0x180006dc9  jnz     short loc_180006DC0
0x180006dcb  mov     rdx, rdi
0x180006dce  inc     rdx
0x180006dd1  cmp     [r14+rdx*2], bx
0x180006dd6  jnz     short loc_180006DCE
0x180006dd8  mov     rcx, rdi
0x180006ddb  inc     rcx
0x180006dde  cmp     [r15+rcx*2], bx
0x180006de3  jnz     short loc_180006DDB
0x180006de5  mov     rax, rdi
0x180006de8  inc     rax
0x180006deb  cmp     [r12+rax*2], bx
0x180006df0  jnz     short loc_180006DE8
0x180006df2  add     eax, ecx
0x180006df4  mov     ecx, 40h ; '@'; uFlags
0x180006df9  add     eax, edx
0x180006dfb  add     eax, r8d
0x180006dfe  lea     r13d, ds:30h[rax*2]
0x180006e06  mov     edx, r13d; uBytes
0x180006e09  call    cs:__imp_LocalAlloc
0x180006e0f  mov     [rsi], rax
0x180006e12  test    rax, rax
0x180006e15  jnz     short loc_180006E5F
0x180006e17  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180006e1d  mov     ebx, 80004005h
0x180006e22  cmp     ecx, 0FFFFFFFFh
0x180006e25  jz      short loc_180006E39
0x180006e27  lea     r8, aFailedLocalall; "Failed LocalAlloc, *pLI"
0x180006e2e  mov     edx, 0Ch; dwFlags
0x180006e33  call    cs:__imp_TracePrintfExA
0x180006e39  xor     ebp, ebp
0x180006e3b  mov     rcx, [rsi]; hMem
0x180006e3e  test    rcx, rcx
0x180006e41  jz      short loc_180006E4C
0x180006e43  call    cs:__imp_LocalFree
0x180006e49  mov     [rsi], rbp
0x180006e4c  mov     eax, ebx
0x180006e4e  add     rsp, 28h
0x180006e52  pop     r15
0x180006e54  pop     r14
0x180006e56  pop     r13
0x180006e58  pop     r12
0x180006e5a  pop     rdi
0x180006e5b  pop     rsi
0x180006e5c  pop     rbp
0x180006e5d  pop     rbx
0x180006e5e  retn
0x180006e5f  mov     dword ptr [rax+4], 1
0x180006e66  mov     rdx, rdi
0x180006e69  mov     rcx, [rsi]
0x180006e6c  mov     eax, [rsp+68h+arg_20]
0x180006e73  mov     [rcx+14h], eax
0x180006e76  mov     rax, [rsi]
0x180006e79  mov     [rax+8], rbx
0x180006e7d  mov     rax, [rsi]
0x180006e80  mov     [rax], r13d
0x180006e83  mov     rax, [rsi]
0x180006e86  lea     r11, [rax+28h]
0x180006e8a  mov     [rax+18h], ebx
0x180006e8d  inc     rdx
0x180006e90  cmp     [rbp+rdx*2+0], bx
0x180006e95  jnz     short loc_180006E8D
0x180006e97  inc     rdx; cchDest
0x180006e9a  mov     r8, rbp; pszSrc
0x180006e9d  mov     rcx, r11; pszDest
0x180006ea0  call    StringCchCopyW
0x180006ea5  xor     ecx, ecx
0x180006ea7  mov     ebx, eax
0x180006ea9  test    eax, eax
0x180006eab  jns     short loc_180006EC4
0x180006ead  mov     ecx, cs:g_dwTraceId
0x180006eb3  cmp     ecx, 0FFFFFFFFh
0x180006eb6  jz      short loc_180006E39
0x180006eb8  lea     r8, aFailedStringcc; "Failed StringCchCopyW"
0x180006ebf  jmp     loc_180006E2E
0x180006ec4  mov     rax, rdi
0x180006ec7  inc     rax
0x180006eca  cmp     [rbp+rax*2+0], cx
0x180006ecf  jnz     short loc_180006EC7
0x180006ed1  mov     rcx, [rsi]
0x180006ed4  lea     r11, [r11+rax*2]
0x180006ed8  add     r11, 2
0x180006edc  mov     rdx, rdi
0x180006edf  mov     rax, r11
0x180006ee2  sub     rax, rcx
0x180006ee5  sub     rax, 28h ; '('
0x180006ee9  sar     rax, 1
0x180006eec  mov     [rcx+1Ch], eax
0x180006eef  xor     ebp, ebp
0x180006ef1  inc     rdx
0x180006ef4  cmp     [r14+rdx*2], bp
0x180006ef9  jnz     short loc_180006EF1
0x180006efb  inc     rdx; cchDest
0x180006efe  mov     r8, r14; pszSrc
0x180006f01  mov     rcx, r11; pszDest
0x180006f04  call    StringCchCopyW
0x180006f09  mov     ebx, eax
0x180006f0b  test    eax, eax
0x180006f0d  js      loc_180006FA1
0x180006f13  mov     rax, rdi
0x180006f16  inc     rax
0x180006f19  cmp     [r14+rax*2], bp
0x180006f1e  jnz     short loc_180006F16
0x180006f20  mov     rcx, [rsi]
0x180006f23  lea     r11, [r11+rax*2]
0x180006f27  add     r11, 2
0x180006f2b  mov     rdx, rdi
0x180006f2e  mov     rax, r11
0x180006f31  sub     rax, rcx
0x180006f34  sub     rax, 28h ; '('
0x180006f38  sar     rax, 1
0x180006f3b  mov     [rcx+20h], eax
0x180006f3e  inc     rdx
0x180006f41  cmp     [r15+rdx*2], bp
0x180006f46  jnz     short loc_180006F3E
0x180006f48  inc     rdx; cchDest
0x180006f4b  mov     r8, r15; pszSrc
0x180006f4e  mov     rcx, r11; pszDest
0x180006f51  call    StringCchCopyW
0x180006f56  mov     ebx, eax
0x180006f58  test    eax, eax
0x180006f5a  js      short loc_180006FA1
0x180006f5c  mov     rax, rdi
0x180006f5f  inc     rax
0x180006f62  cmp     [r15+rax*2], bp
0x180006f67  jnz     short loc_180006F5F
0x180006f69  mov     rcx, [rsi]
0x180006f6c  lea     r9, [r11+rax*2]
0x180006f70  lea     rax, [r9+2]
0x180006f74  sub     rax, rcx
0x180006f77  sub     rax, 28h ; '('
0x180006f7b  sar     rax, 1
0x180006f7e  mov     [rcx+24h], eax
0x180006f81  inc     rdi
0x180006f84  cmp     [r12+rdi*2], bp
0x180006f89  jnz     short loc_180006F81
0x180006f8b  lea     rdx, [rdi+1]; cchDest
0x180006f8f  mov     r8, r12; pszSrc
0x180006f92  lea     rcx, [r9+2]; pszDest
0x180006f96  call    StringCchCopyW
0x180006f9b  mov     ebx, eax
0x180006f9d  test    eax, eax
0x180006f9f  jns     short loc_180006FC7
0x180006fa1  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180006fa7  cmp     ecx, 0FFFFFFFFh
0x180006faa  jz      loc_180006E3B
0x180006fb0  lea     r8, aFailedStringcc; "Failed StringCchCopyW"
0x180006fb7  mov     edx, 0Ch; dwFlags
0x180006fbc  call    cs:__imp_TracePrintfExA
0x180006fc2  jmp     loc_180006E3B
0x180006fc7  mov     rax, [rsp+68h+arg_30]
0x180006fcf  mov     ebx, ebp
0x180006fd1  mov     [rax], r13d
0x180006fd4  jmp     loc_180006E4C
0x180006fd9  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180006fdf  mov     ebx, 80070057h
0x180006fe4  cmp     ecx, 0FFFFFFFFh
0x180006fe7  jz      short loc_180006FFB
0x180006fe9  lea     r8, aInvalidArgS; "Invalid arg(s)"
0x180006ff0  mov     edx, 0Ch; dwFlags
0x180006ff5  call    cs:__imp_TracePrintfExA
0x180006ffb  xor     ebp, ebp
0x180006ffd  test    rsi, rsi
0x180007000  jz      loc_180006E4C
0x180007006  jmp     loc_180006E3B
```
