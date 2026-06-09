# StringCchCopyW

- ea: `0x180020b1c`
- end: `0x180020b87`
- name: `StringCchCopyW`
- size: `107`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x18001ea80`
- `0x180020b90`
- `0x180020f88`
- `0x1800211f4`
- `0x18002b304`
- `0x18002b7d4`
- `0x18002cde8`
- `0x18002cf7c`
- `0x18002ebd0`
- `0x18002f6b8`
- `0x18002f864`
- `0x18002f9c4`

## callees

- `0x180020b1c`

## pseudocode

```c
HRESULT __stdcall StringCchCopyW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  STRSAFE_LPWSTR v3; // r9
  HRESULT result; // eax
  __int64 v5; // rax

  v3 = pszDest;
  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*pszSrc )
        break;
      *v3++ = *pszSrc++;
      --v5;
      --cchDest;
    }
    while ( cchDest );
    pszDest = v3 - 1;
    if ( cchDest )
      pszDest = v3;
    result = cchDest == 0 ? 0x8007007A : 0;
  }
  else
  {
    result = -2147024809;
  }
  *pszDest = 0;
  return result;
}

```

## disassembly

```asm
0x180020b1c  xor     r10d, r10d
0x180020b1f  mov     r9, rcx
0x180020b22  test    rdx, rdx
0x180020b25  jz      short loc_180020B78
0x180020b27  cmp     rdx, 7FFFFFFFh
0x180020b2e  jbe     short loc_180020B37
0x180020b30  mov     eax, 80070057h
0x180020b35  jmp     short loc_180020B82
0x180020b37  mov     eax, 7FFFFFFEh
0x180020b3c  test    rax, rax
0x180020b3f  jz      short loc_180020B5F
0x180020b41  movzx   ecx, word ptr [r8]
0x180020b45  test    cx, cx
0x180020b48  jz      short loc_180020B5F
0x180020b4a  mov     [r9], cx
0x180020b4e  add     r8, 2
0x180020b52  add     r9, 2
0x180020b56  dec     rax
0x180020b59  sub     rdx, 1
0x180020b5d  jnz     short loc_180020B3C
0x180020b5f  test    rdx, rdx
0x180020b62  lea     rcx, [r9-2]
0x180020b66  cmovnz  rcx, r9
0x180020b6a  neg     rdx
0x180020b6d  sbb     eax, eax
0x180020b6f  not     eax
0x180020b71  and     eax, 8007007Ah
0x180020b76  jmp     short loc_180020B82
0x180020b78  mov     eax, 80070057h
0x180020b7d  test    rdx, rdx
0x180020b80  jz      short locret_180020B86
0x180020b82  mov     [rcx], r10w
0x180020b86  retn
```
