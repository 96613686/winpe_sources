# StringCchCopyW

- ea: `0x180014230`
- end: `0x18001429e`
- name: `StringCchCopyW`
- size: `110`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800030d0`
- `0x180012330`
- `0x180025798`

## callees

- `0x180014230`

## pseudocode

```c
HRESULT __stdcall StringCchCopyW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  STRSAFE_LPWSTR v3; // r9
  __int64 v4; // rax
  STRSAFE_LPWSTR v5; // rax
  HRESULT result; // eax

  v3 = pszDest;
  if ( !cchDest )
    return -2147024809;
  if ( cchDest > 0x7FFFFFFF )
  {
    result = -2147024809;
    *pszDest = 0;
  }
  else
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*pszSrc )
        break;
      *v3++ = *pszSrc++;
      --v4;
      --cchDest;
    }
    while ( cchDest );
    v5 = v3 - 1;
    if ( cchDest )
      v5 = v3;
    *v5 = 0;
    result = -2147024774;
    if ( cchDest )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180014230  mov     r9, rcx
0x180014233  test    rdx, rdx
0x180014236  jz      short loc_18001428D
0x180014238  cmp     rdx, 7FFFFFFFh
0x18001423f  ja      short loc_180014286
0x180014241  mov     eax, 7FFFFFFEh
0x180014246  test    rax, rax
0x180014249  jz      short loc_180014269
0x18001424b  movzx   ecx, word ptr [r8]
0x18001424f  test    cx, cx
0x180014252  jz      short loc_180014269
0x180014254  mov     [r9], cx
0x180014258  add     r8, 2
0x18001425c  add     r9, 2
0x180014260  dec     rax
0x180014263  sub     rdx, 1
0x180014267  jnz     short loc_180014246
0x180014269  test    rdx, rdx
0x18001426c  lea     rax, [r9-2]
0x180014270  cmovnz  rax, r9
0x180014274  xor     ecx, ecx
0x180014276  test    rdx, rdx
0x180014279  mov     [rax], cx
0x18001427c  mov     eax, 8007007Ah
0x180014281  cmovnz  eax, ecx
0x180014284  retn
0x180014286  mov     eax, 80070057h
0x18001428b  jmp     short loc_180014297
0x18001428d  mov     eax, 80070057h
0x180014292  test    rdx, rdx
0x180014295  jz      short locret_180014284
0x180014297  xor     ecx, ecx
0x180014299  mov     [r9], cx
0x18001429d  retn
```
