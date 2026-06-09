# PathCchFindExtension

- ea: `0x14001057c`
- end: `0x1400105d0`
- name: `PathCchFindExtension`
- size: `84`
- prototype: `HRESULT __stdcall(PCWSTR pszPath, size_t cchPath, PCWSTR *ppszExt)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callers

- `0x1400094a4`

## callees

- `0x14001057c`

## pseudocode

```c
HRESULT __stdcall PathCchFindExtension(PCWSTR pszPath, size_t cchPath, PCWSTR *ppszExt)
{
  const WCHAR *v3; // rax
  PCWSTR v4; // rdx

  *ppszExt = 0;
  if ( pszPath )
  {
    v3 = 0;
    v4 = pszPath + 260;
    while ( 1 )
    {
      if ( pszPath >= v4 )
        return -2147024809;
      if ( !*pszPath )
      {
        if ( !v3 )
          v3 = pszPath;
        *ppszExt = v3;
        return 0;
      }
      if ( *pszPath == 32 )
        goto LABEL_7;
      if ( *pszPath != 46 )
        break;
      v3 = pszPath;
LABEL_8:
      ++pszPath;
    }
    if ( *pszPath != 92 )
      goto LABEL_8;
LABEL_7:
    v3 = 0;
    goto LABEL_8;
  }
  return -2147024809;
}

```

## disassembly

```asm
0x14001057c  xor     r9d, r9d
0x14001057f  mov     [r8], r9
0x140010582  test    rcx, rcx
0x140010585  jz      short loc_1400105B7
0x140010587  mov     eax, r9d
0x14001058a  lea     rdx, [rcx+208h]
0x140010591  jmp     short loc_1400105B2
0x140010593  cmp     [rcx], r9w
0x140010597  jz      short loc_1400105C3
0x140010599  cmp     word ptr [rcx], 20h ; ' '
0x14001059d  jz      short loc_1400105AB
0x14001059f  cmp     word ptr [rcx], 2Eh ; '.'
0x1400105a3  jz      short loc_1400105BE
0x1400105a5  cmp     word ptr [rcx], 5Ch ; '\'
0x1400105a9  jnz     short loc_1400105AE
0x1400105ab  mov     rax, r9
0x1400105ae  add     rcx, 2
0x1400105b2  cmp     rcx, rdx
0x1400105b5  jb      short loc_140010593
0x1400105b7  mov     eax, 80070057h
0x1400105bc  retn
0x1400105be  mov     rax, rcx
0x1400105c1  jmp     short loc_1400105AE
0x1400105c3  test    rax, rax
0x1400105c6  cmovz   rax, rcx
0x1400105ca  mov     [r8], rax
0x1400105cd  xor     eax, eax
0x1400105cf  retn
```
