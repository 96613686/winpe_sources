# StringCchCopyW

- ea: `0x180009c00`
- end: `0x180009c6d`
- name: `StringCchCopyW`
- size: `109`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180001600`
- `0x180004bd0`
- `0x180006130`
- `0x18000cd10`
- `0x18000e494`
- `0x18000edb4`
- `0x18000f048`

## callees

- `0x180009c00`

## pseudocode

```c
HRESULT __stdcall StringCchCopyW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  STRSAFE_LPWSTR v3; // r9
  HRESULT result; // eax
  __int64 v5; // rcx
  STRSAFE_LPWSTR v6; // rax

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
    v6 = v3 - 1;
    if ( cchDest )
      v6 = v3;
    *v6 = 0;
    result = -2147024774;
    if ( cchDest )
      return 0;
  }
  else
  {
    result = -2147024809;
    *pszDest = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180009c00  mov     r9, rcx
0x180009c03  test    rdx, rdx
0x180009c06  jz      short loc_180009C5C
0x180009c08  cmp     rdx, 7FFFFFFFh
0x180009c0f  jbe     short loc_180009C18
0x180009c11  mov     eax, 80070057h
0x180009c16  jmp     short loc_180009C66
0x180009c18  mov     ecx, 7FFFFFFEh
0x180009c1d  test    rcx, rcx
0x180009c20  jz      short loc_180009C40
0x180009c22  movzx   eax, word ptr [r8]
0x180009c26  test    ax, ax
0x180009c29  jz      short loc_180009C40
0x180009c2b  mov     [r9], ax
0x180009c2f  add     r8, 2
0x180009c33  add     r9, 2
0x180009c37  dec     rcx
0x180009c3a  sub     rdx, 1
0x180009c3e  jnz     short loc_180009C1D
0x180009c40  test    rdx, rdx
0x180009c43  lea     rax, [r9-2]
0x180009c47  cmovnz  rax, r9
0x180009c4b  xor     ecx, ecx
0x180009c4d  test    rdx, rdx
0x180009c50  mov     [rax], cx
0x180009c53  mov     eax, 8007007Ah
0x180009c58  cmovnz  eax, ecx
0x180009c5b  retn
0x180009c5c  mov     eax, 80070057h
0x180009c61  test    rdx, rdx
0x180009c64  jz      short locret_180009C6C
0x180009c66  xor     ecx, ecx
0x180009c68  mov     [r9], cx
0x180009c6c  retn
```
