# StringCchCopyA

- ea: `0x18000b810`
- end: `0x18000b876`
- name: `StringCchCopyA`
- size: `102`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800047a0`
- `0x180007370`
- `0x18000b460`
- `0x180012bdc`
- `0x180017050`
- `0x180020320`
- `0x180023e30`

## callees

- `0x18000b810`

## pseudocode

```c
HRESULT __stdcall StringCchCopyA(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)
{
  STRSAFE_LPSTR v3; // r9
  __int64 v4; // rax
  STRSAFE_LPSTR v5; // rax
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
0x18000b810  mov     r9, rcx
0x18000b813  test    rdx, rdx
0x18000b816  jz      short loc_18000B868
0x18000b818  cmp     rdx, 7FFFFFFFh
0x18000b81f  ja      short loc_18000B861
0x18000b821  mov     eax, 7FFFFFFEh
0x18000b826  test    rax, rax
0x18000b829  jz      short loc_18000B845
0x18000b82b  movzx   ecx, byte ptr [r8]
0x18000b82f  test    cl, cl
0x18000b831  jz      short loc_18000B845
0x18000b833  mov     [r9], cl
0x18000b836  inc     r8
0x18000b839  inc     r9
0x18000b83c  dec     rax
0x18000b83f  sub     rdx, 1
0x18000b843  jnz     short loc_18000B826
0x18000b845  test    rdx, rdx
0x18000b848  lea     rax, [r9-1]
0x18000b84c  cmovnz  rax, r9
0x18000b850  xor     ecx, ecx
0x18000b852  test    rdx, rdx
0x18000b855  mov     byte ptr [rax], 0
0x18000b858  mov     eax, 8007007Ah
0x18000b85d  cmovnz  eax, ecx
0x18000b860  retn
0x18000b861  mov     eax, 80070057h
0x18000b866  jmp     short loc_18000B872
0x18000b868  mov     eax, 80070057h
0x18000b86d  test    rdx, rdx
0x18000b870  jz      short locret_18000B860
0x18000b872  mov     byte ptr [rcx], 0
0x18000b875  retn
```
