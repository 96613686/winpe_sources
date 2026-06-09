# SQLPostInstallerErrorW

- ea: `0x180004db0`
- end: `0x180004e78`
- name: `SQLPostInstallerErrorW`
- size: `200`
- prototype: `SQLRETURN __stdcall(DWORD dwErrorCode, LPCWSTR lpszErrorMsg)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180007c0c`
- `0x1800085c8`
- `0x18000f8c0`

## callees

- `0x180002e14`
- `0x180004db0`

## import_xrefs

- `msvcrt!calloc` at `0x180004e21`
- `msvcrt!calloc` at `0x180004e21`
- `KERNEL32!LeaveCriticalSection` at `0x180004e5e`
- `KERNEL32!LeaveCriticalSection` at `0x180004e5e`
- `KERNEL32!EnterCriticalSection` at `0x180004dcd`
- `KERNEL32!EnterCriticalSection` at `0x180004dcd`

## pseudocode

```c
SQLRETURN __stdcall SQLPostInstallerErrorW(DWORD dwErrorCode, LPCWSTR lpszErrorMsg)
{
  unsigned int v4; // ebx
  SQLRETURN v5; // bp
  __int64 v6; // rax
  size_t v7; // rdi
  wchar_t *v8; // rax

  EnterCriticalSection(&g_csInstaller);
  v4 = (unsigned __int16)word_18001CA40;
  if ( (unsigned __int16)word_18001CA40 >= 8u || dwErrorCode - 1 > 0x16 )
  {
    v5 = -1;
  }
  else
  {
    v5 = 0;
    LODWORD(qword_18001C9C0[2 * (unsigned __int16)word_18001CA40]) = dwErrorCode;
    if ( lpszErrorMsg )
    {
      v6 = -1;
      do
        ++v6;
      while ( lpszErrorMsg[v6] );
      v7 = v6 + 1;
      v8 = (wchar_t *)calloc(2 * (v6 + 1), 1u);
      qword_18001C9C0[2 * v4 + 1] = (__int64)v8;
      if ( v8 )
      {
        StringCchCopyW(v8, v7, lpszErrorMsg);
        LOWORD(v4) = word_18001CA40;
      }
    }
    word_18001CA40 = v4 + 1;
  }
  LeaveCriticalSection(&g_csInstaller);
  return v5;
}

```

## disassembly

```asm
0x180004db0  push    rbx
0x180004db2  push    rbp
0x180004db3  push    rsi
0x180004db4  push    rdi
0x180004db5  push    r12
0x180004db7  push    r13
0x180004db9  push    r14
0x180004dbb  push    r15
0x180004dbd  sub     rsp, 28h
0x180004dc1  mov     edi, ecx
0x180004dc3  mov     rsi, rdx
0x180004dc6  lea     rcx, g_csInstaller; lpCriticalSection
0x180004dcd  call    cs:__imp_EnterCriticalSection
0x180004dd3  movzx   ebx, cs:word_18001CA40
0x180004dda  cmp     ebx, 8
0x180004ddd  jnb     short loc_180004E53
0x180004ddf  lea     eax, [rdi-1]
0x180004de2  cmp     eax, 16h
0x180004de5  ja      short loc_180004E53
0x180004de7  xor     r15d, r15d
0x180004dea  lea     r13, qword_18001C9C0
0x180004df1  mov     r14d, ebx
0x180004df4  mov     ebp, r15d
0x180004df7  add     r14, r14
0x180004dfa  lea     r12d, [r15+1]
0x180004dfe  mov     [r13+r14*8+0], edi
0x180004e03  test    rsi, rsi
0x180004e06  jz      short loc_180004E46
0x180004e08  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004e0c  inc     rax
0x180004e0f  cmp     [rsi+rax*2], r15w
0x180004e14  jnz     short loc_180004E0C
0x180004e16  lea     rdi, [rax+1]
0x180004e1a  mov     rdx, r12; Size
0x180004e1d  lea     rcx, [rdi+rdi]; Count
0x180004e21  call    cs:__imp_calloc
0x180004e27  mov     [r13+r14*8+8], rax
0x180004e2c  test    rax, rax
0x180004e2f  jz      short loc_180004E46
0x180004e31  mov     r8, rsi; pszSrc
0x180004e34  mov     rdx, rdi; cchDest
0x180004e37  mov     rcx, rax; pszDest
0x180004e3a  call    StringCchCopyW
0x180004e3f  movzx   ebx, cs:word_18001CA40
0x180004e46  add     bx, r12w
0x180004e4a  mov     cs:word_18001CA40, bx
0x180004e51  jmp     short loc_180004E57
0x180004e53  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180004e57  lea     rcx, g_csInstaller; lpCriticalSection
0x180004e5e  call    cs:__imp_LeaveCriticalSection
0x180004e64  movzx   eax, bp
0x180004e67  add     rsp, 28h
0x180004e6b  pop     r15
0x180004e6d  pop     r14
0x180004e6f  pop     r13
0x180004e71  pop     r12
0x180004e73  pop     rdi
0x180004e74  pop     rsi
0x180004e75  pop     rbp
0x180004e76  pop     rbx
0x180004e77  retn
```
