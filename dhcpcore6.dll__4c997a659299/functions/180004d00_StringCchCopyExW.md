# StringCchCopyExW

- ea: `0x180004d00`
- end: `0x180004d71`
- name: `StringCchCopyExW`
- size: `113`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc, STRSAFE_LPWSTR *ppszDestEnd, size_t *pcchRemaining, DWORD dwFlags)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000490c`
- `0x180004d78`
- `0x180005368`

## callees

- `0x180004d00`

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
  STRSAFE_LPWSTR v6; // rdx
  STRSAFE_LPCWSTR v7; // rax
  __int64 v8; // rcx
  __int64 v9; // r8
  STRSAFE_LPWSTR v10; // rcx
  HRESULT v11; // ecx

  v6 = pszDest;
  if ( pszDest )
  {
    v7 = (STRSAFE_LPCWSTR)&qword_180037F50;
    v8 = 2147483646;
    if ( pszSrc )
      v7 = pszSrc;
    v9 = 80;
    do
    {
      if ( !v8 )
        break;
      if ( !*v7 )
        break;
      *v6++ = *v7++;
      --v8;
      --v9;
    }
    while ( v9 );
    v10 = v6 - 1;
    if ( v9 )
      v10 = v6;
    *v10 = 0;
    return v9 == 0 ? 0x8007007A : 0;
  }
  else
  {
    v11 = -2147024809;
    MEMORY[0] = 0;
  }
  return v11;
}

```

## disassembly

```asm
0x180004d00  xor     r10d, r10d
0x180004d03  mov     rdx, rcx
0x180004d06  test    rcx, rcx
0x180004d09  jz      short loc_180004D66
0x180004d0b  test    r8, r8
0x180004d0e  lea     rax, qword_180037F50
0x180004d15  mov     ecx, 7FFFFFFEh
0x180004d1a  cmovnz  rax, r8
0x180004d1e  lea     r8d, [r10+50h]
0x180004d22  test    rcx, rcx
0x180004d25  jz      short loc_180004D46
0x180004d27  movzx   r9d, word ptr [rax]
0x180004d2b  test    r9w, r9w
0x180004d2f  jz      short loc_180004D46
0x180004d31  mov     [rdx], r9w
0x180004d35  add     rax, 2
0x180004d39  add     rdx, 2
0x180004d3d  dec     rcx
0x180004d40  sub     r8, 1
0x180004d44  jnz     short loc_180004D22
0x180004d46  test    r8, r8
0x180004d49  lea     rcx, [rdx-2]
0x180004d4d  cmovnz  rcx, rdx
0x180004d51  neg     r8
0x180004d54  mov     [rcx], r10w
0x180004d58  sbb     ecx, ecx
0x180004d5a  not     ecx
0x180004d5c  and     ecx, 8007007Ah
0x180004d62  mov     eax, ecx
0x180004d64  retn
0x180004d66  mov     ecx, 80070057h
0x180004d6b  mov     [rdx], r10w
0x180004d6f  jmp     short loc_180004D62
```
