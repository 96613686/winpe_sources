# StpCreateDirectories(ushort *)

- ea: `0x18001e270`
- end: `0x18001e343`
- name: `?StpCreateDirectories@@YAKPEAG@Z`
- size: `211`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001d828`

## callees

- `0x18001e270`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001e29d`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001e29d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e2c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e2ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e2d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e321`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e2c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e2ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e2d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e321`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001e2b7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001e30a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001e2b7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001e30a`

## pseudocode

```c
__int64 __fastcall StpCreateDirectories(LPCWSTR lpPathName)
{
  DWORD LastError; // ebx
  __int64 v3; // rdi
  wchar_t *v4; // rax
  wchar_t *v5; // rsi
  const WCHAR *v6; // rdi
  __int64 v7; // rax

  LastError = 0;
  v3 = -1;
  do
    ++v3;
  while ( lpPathName[v3] );
  while ( 1 )
  {
    v4 = wcsrchr(lpPathName, 0x5Cu);
    v5 = v4;
    if ( !v4 )
      return 161;
    *v4 = 0;
    if ( CreateDirectoryW(lpPathName, 0) || GetLastError() == 183 )
      break;
    if ( GetLastError() != 3 )
    {
      LastError = GetLastError();
      if ( LastError )
        return LastError;
    }
  }
  v6 = &lpPathName[v3];
  while ( 1 )
  {
    *v5 = 92;
    v7 = -1;
    do
      ++v7;
    while ( v5[v7] );
    v5 += v7;
    if ( v5 >= v6 )
      break;
    if ( !CreateDirectoryW(lpPathName, 0) && GetLastError() != 183 )
    {
      LastError = GetLastError();
      if ( LastError )
        break;
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18001e270  push    rbx
0x18001e272  push    rbp
0x18001e273  push    rsi
0x18001e274  push    rdi
0x18001e275  push    r12
0x18001e277  push    r14
0x18001e279  sub     rsp, 28h
0x18001e27d  xor     ebp, ebp
0x18001e27f  mov     r14, rcx
0x18001e282  mov     ebx, ebp
0x18001e284  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001e288  inc     rdi
0x18001e28b  cmp     [rcx+rdi*2], bp
0x18001e28f  jnz     short loc_18001E288
0x18001e291  mov     r12d, 5Ch ; '\'
0x18001e297  mov     edx, r12d; Ch
0x18001e29a  mov     rcx, r14; Str
0x18001e29d  call    cs:__imp_wcsrchr
0x18001e2a3  mov     rsi, rax
0x18001e2a6  test    rax, rax
0x18001e2a9  jz      loc_18001E32F
0x18001e2af  xor     edx, edx; lpSecurityAttributes
0x18001e2b1  mov     [rax], bp
0x18001e2b4  mov     rcx, r14; lpPathName
0x18001e2b7  call    cs:__imp_CreateDirectoryW
0x18001e2bd  test    eax, eax
0x18001e2bf  jnz     short loc_18001E2E7
0x18001e2c1  call    cs:__imp_GetLastError
0x18001e2c7  cmp     eax, 0B7h
0x18001e2cc  jz      short loc_18001E2E7
0x18001e2ce  call    cs:__imp_GetLastError
0x18001e2d4  cmp     eax, 3
0x18001e2d7  jz      short loc_18001E297
0x18001e2d9  call    cs:__imp_GetLastError
0x18001e2df  mov     ebx, eax
0x18001e2e1  test    eax, eax
0x18001e2e3  jz      short loc_18001E297
0x18001e2e5  jmp     short loc_18001E334
0x18001e2e7  lea     rdi, [r14+rdi*2]
0x18001e2eb  mov     [rsi], r12w
0x18001e2ef  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e2f3  inc     rax
0x18001e2f6  cmp     [rsi+rax*2], bp
0x18001e2fa  jnz     short loc_18001E2F3
0x18001e2fc  lea     rsi, [rsi+rax*2]
0x18001e300  cmp     rsi, rdi
0x18001e303  jnb     short loc_18001E334
0x18001e305  xor     edx, edx; lpSecurityAttributes
0x18001e307  mov     rcx, r14; lpPathName
0x18001e30a  call    cs:__imp_CreateDirectoryW
0x18001e310  test    eax, eax
0x18001e312  jnz     short loc_18001E2EB
0x18001e314  call    cs:__imp_GetLastError
0x18001e31a  cmp     eax, 0B7h
0x18001e31f  jz      short loc_18001E2EB
0x18001e321  call    cs:__imp_GetLastError
0x18001e327  mov     ebx, eax
0x18001e329  test    eax, eax
0x18001e32b  jz      short loc_18001E2EB
0x18001e32d  jmp     short loc_18001E334
0x18001e32f  mov     ebx, 0A1h
0x18001e334  mov     eax, ebx
0x18001e336  add     rsp, 28h
0x18001e33a  pop     r14
0x18001e33c  pop     r12
0x18001e33e  pop     rdi
0x18001e33f  pop     rsi
0x18001e340  pop     rbp
0x18001e341  pop     rbx
0x18001e342  retn
```
