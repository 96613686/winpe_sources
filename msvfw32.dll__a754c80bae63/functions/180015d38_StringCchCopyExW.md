# StringCchCopyExW

- ea: `0x180015d38`
- end: `0x180015dd8`
- name: `StringCchCopyExW`
- size: `160`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc, STRSAFE_LPWSTR *ppszDestEnd, size_t *pcchRemaining, DWORD dwFlags)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012ac4`

## callees

- `0x180015d38`
- `0x180015eb4`

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
  HRESULT v9; // edx
  size_t v10; // rbx
  size_t v12; // [rsp+20h] [rbp-28h]
  size_t pcchNewDestLength[3]; // [rsp+30h] [rbp-18h] BYREF

  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
  {
    pcchNewDestLength[0] = 0;
    v9 = StringCopyWorkerW_0(pszDest, cchDest, pcchNewDestLength, pszSrc, v12);
    v10 = cchDest - pcchNewDestLength[0];
    if ( (int)(v9 + 0x80000000) < 0 || v9 == -2147024774 )
    {
      if ( ppszDestEnd )
        *ppszDestEnd = &pszDest[pcchNewDestLength[0]];
      if ( pcchRemaining )
        *pcchRemaining = v10;
    }
  }
  else
  {
    v9 = -2147024809;
    *pszDest = 0;
  }
  return v9;
}

```

## disassembly

```asm
0x180015d38  mov     [rsp+arg_0], rbx
0x180015d3d  mov     [rsp+arg_8], rsi
0x180015d42  push    rdi
0x180015d43  sub     rsp, 40h
0x180015d47  mov     rdi, r9
0x180015d4a  mov     rbx, rdx
0x180015d4d  mov     rsi, rcx
0x180015d50  test    rdx, rdx
0x180015d53  jz      short loc_180015DB7
0x180015d55  cmp     rdx, 7FFFFFFFh
0x180015d5c  jbe     short loc_180015D65
0x180015d5e  mov     edx, 80070057h; cchDest
0x180015d63  jmp     short loc_180015DC1
0x180015d65  mov     r9, r8; pszSrc
0x180015d68  mov     [rsp+48h+pcchNewDestLength], 0
0x180015d71  lea     r8, [rsp+48h+pcchNewDestLength]; pcchNewDestLength
0x180015d76  call    StringCopyWorkerW_0
0x180015d7b  mov     rcx, [rsp+48h+pcchNewDestLength]
0x180015d80  mov     edx, eax
0x180015d82  mov     r8d, 80000000h
0x180015d88  sub     rbx, rcx
0x180015d8b  lea     rax, [rsi+rcx*2]
0x180015d8f  lea     ecx, [rdx+r8]
0x180015d93  test    r8d, ecx
0x180015d96  jnz     short loc_180015DA0
0x180015d98  cmp     edx, 8007007Ah
0x180015d9e  jnz     short loc_180015DC6
0x180015da0  test    rdi, rdi
0x180015da3  jz      short loc_180015DA8
0x180015da5  mov     [rdi], rax
0x180015da8  mov     rax, [rsp+48h+pcchRemaining]
0x180015dad  test    rax, rax
0x180015db0  jz      short loc_180015DC6
0x180015db2  mov     [rax], rbx
0x180015db5  jmp     short loc_180015DC6
0x180015db7  mov     edx, 80070057h
0x180015dbc  test    rbx, rbx
0x180015dbf  jz      short loc_180015DC6
0x180015dc1  xor     eax, eax
0x180015dc3  mov     [rcx], ax
0x180015dc6  mov     rbx, [rsp+48h+arg_0]
0x180015dcb  mov     eax, edx
0x180015dcd  mov     rsi, [rsp+48h+arg_8]
0x180015dd2  add     rsp, 40h
0x180015dd6  pop     rdi
0x180015dd7  retn
```
