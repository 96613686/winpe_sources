# StringCchCopyW

- ea: `0x18001bc7c`
- end: `0x18001bce7`
- name: `StringCchCopyW`
- size: `107`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180008938`
- `0x18001f904`
- `0x1800225fc`

## callees

- `0x18001bc7c`

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
0x18001bc7c  xor     r10d, r10d
0x18001bc7f  mov     r9, rcx
0x18001bc82  test    rdx, rdx
0x18001bc85  jz      short loc_18001BCD8
0x18001bc87  cmp     rdx, 7FFFFFFFh
0x18001bc8e  jbe     short loc_18001BC97
0x18001bc90  mov     eax, 80070057h
0x18001bc95  jmp     short loc_18001BCE2
0x18001bc97  mov     eax, 7FFFFFFEh
0x18001bc9c  test    rax, rax
0x18001bc9f  jz      short loc_18001BCBF
0x18001bca1  movzx   ecx, word ptr [r8]
0x18001bca5  test    cx, cx
0x18001bca8  jz      short loc_18001BCBF
0x18001bcaa  mov     [r9], cx
0x18001bcae  add     r8, 2
0x18001bcb2  add     r9, 2
0x18001bcb6  dec     rax
0x18001bcb9  sub     rdx, 1
0x18001bcbd  jnz     short loc_18001BC9C
0x18001bcbf  test    rdx, rdx
0x18001bcc2  lea     rcx, [r9-2]
0x18001bcc6  cmovnz  rcx, r9
0x18001bcca  neg     rdx
0x18001bccd  sbb     eax, eax
0x18001bccf  not     eax
0x18001bcd1  and     eax, 8007007Ah
0x18001bcd6  jmp     short loc_18001BCE2
0x18001bcd8  mov     eax, 80070057h
0x18001bcdd  test    rdx, rdx
0x18001bce0  jz      short locret_18001BCE6
0x18001bce2  mov     [rcx], r10w
0x18001bce6  retn
```
