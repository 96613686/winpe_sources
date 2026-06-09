# StringCchCopyNA

- ea: `0x18002402c`
- end: `0x18002407b`
- name: `StringCchCopyNA`
- size: `79`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180023e30`

## callees

- `0x18002402c`

## pseudocode

```c
HRESULT __stdcall StringCchCopyNA(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)
{
  HRESULT result; // eax
  __int64 v5; // rdx
  STRSAFE_LPSTR v6; // rax

  if ( cchToCopy <= 0x7FFFFFFE )
  {
    v5 = 257;
    do
    {
      if ( !cchToCopy )
        break;
      if ( !*pszSrc )
        break;
      *pszDest++ = *pszSrc++;
      --cchToCopy;
      --v5;
    }
    while ( v5 );
    v6 = pszDest - 1;
    if ( v5 )
      v6 = pszDest;
    *v6 = 0;
    return v5 == 0 ? 0x8007007A : 0;
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
0x18002402c  cmp     r9, 7FFFFFFEh
0x180024033  jbe     short loc_18002403E
0x180024035  mov     eax, 80070057h
0x18002403a  mov     byte ptr [rcx], 0
0x18002403d  retn
0x18002403e  mov     edx, 101h
0x180024043  test    r9, r9
0x180024046  jz      short loc_180024060
0x180024048  mov     al, [r8]
0x18002404b  test    al, al
0x18002404d  jz      short loc_180024060
0x18002404f  mov     [rcx], al
0x180024051  inc     r8
0x180024054  inc     rcx
0x180024057  dec     r9
0x18002405a  sub     rdx, 1
0x18002405e  jnz     short loc_180024043
0x180024060  test    rdx, rdx
0x180024063  lea     rax, [rcx-1]
0x180024067  cmovnz  rax, rcx
0x18002406b  neg     rdx
0x18002406e  mov     byte ptr [rax], 0
0x180024071  sbb     eax, eax
0x180024073  not     eax
0x180024075  and     eax, 8007007Ah
0x18002407a  retn
```
