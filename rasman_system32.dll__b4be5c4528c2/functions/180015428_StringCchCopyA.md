# StringCchCopyA

- ea: `0x180015428`
- end: `0x18001548b`
- name: `StringCchCopyA`
- size: `99`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001ff0`
- `0x1800030d0`
- `0x180012330`

## callees

- `0x180015428`

## pseudocode

```c
HRESULT __stdcall StringCchCopyA(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)
{
  HRESULT result; // eax
  __int64 v4; // rax
  STRSAFE_LPSTR v5; // rax

  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*pszSrc )
        break;
      *pszDest++ = *pszSrc++;
      --v4;
      --cchDest;
    }
    while ( cchDest );
    v5 = pszDest - 1;
    if ( cchDest )
      v5 = pszDest;
    *v5 = 0;
    return cchDest == 0 ? 0x8007007A : 0;
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
0x180015428  test    rdx, rdx
0x18001542b  jz      short loc_18001547D
0x18001542d  cmp     rdx, 7FFFFFFFh
0x180015434  jbe     short loc_18001543D
0x180015436  mov     eax, 80070057h
0x18001543b  jmp     short loc_180015487
0x18001543d  mov     eax, 7FFFFFFEh
0x180015442  test    rax, rax
0x180015445  jz      short loc_180015461
0x180015447  mov     r9b, [r8]
0x18001544a  test    r9b, r9b
0x18001544d  jz      short loc_180015461
0x18001544f  mov     [rcx], r9b
0x180015452  inc     r8
0x180015455  inc     rcx
0x180015458  dec     rax
0x18001545b  sub     rdx, 1
0x18001545f  jnz     short loc_180015442
0x180015461  test    rdx, rdx
0x180015464  lea     rax, [rcx-1]
0x180015468  cmovnz  rax, rcx
0x18001546c  neg     rdx
0x18001546f  mov     byte ptr [rax], 0
0x180015472  sbb     eax, eax
0x180015474  not     eax
0x180015476  and     eax, 8007007Ah
0x18001547b  retn
0x18001547d  mov     eax, 80070057h
0x180015482  test    rdx, rdx
0x180015485  jz      short locret_18001548A
0x180015487  mov     byte ptr [rcx], 0
0x18001548a  retn
```
