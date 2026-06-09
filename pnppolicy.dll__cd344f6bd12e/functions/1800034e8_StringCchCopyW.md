# StringCchCopyW

- ea: `0x1800034e8`
- end: `0x180003553`
- name: `StringCchCopyW`
- size: `107`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180004658`
- `0x180006e28`
- `0x180006f1c`
- `0x1800079f0`
- `0x180009f1c`

## callees

- `0x1800034e8`

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
0x1800034e8  xor     r10d, r10d
0x1800034eb  mov     r9, rcx
0x1800034ee  test    rdx, rdx
0x1800034f1  jz      short loc_180003544
0x1800034f3  cmp     rdx, 7FFFFFFFh
0x1800034fa  jbe     short loc_180003503
0x1800034fc  mov     eax, 80070057h
0x180003501  jmp     short loc_18000354E
0x180003503  mov     eax, 7FFFFFFEh
0x180003508  test    rax, rax
0x18000350b  jz      short loc_18000352B
0x18000350d  movzx   ecx, word ptr [r8]
0x180003511  test    cx, cx
0x180003514  jz      short loc_18000352B
0x180003516  mov     [r9], cx
0x18000351a  add     r8, 2
0x18000351e  add     r9, 2
0x180003522  dec     rax
0x180003525  sub     rdx, 1
0x180003529  jnz     short loc_180003508
0x18000352b  test    rdx, rdx
0x18000352e  lea     rcx, [r9-2]
0x180003532  cmovnz  rcx, r9
0x180003536  neg     rdx
0x180003539  sbb     eax, eax
0x18000353b  not     eax
0x18000353d  and     eax, 8007007Ah
0x180003542  jmp     short loc_18000354E
0x180003544  mov     eax, 80070057h
0x180003549  test    rdx, rdx
0x18000354c  jz      short locret_180003552
0x18000354e  mov     [rcx], r10w
0x180003552  retn
```
