# StringCchCopyA

- ea: `0x140072598`
- end: `0x1400725fa`
- name: `StringCchCopyA`
- size: `98`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400821c0`
- `0x140082754`
- `0x14008595c`
- `0x140086cf4`
- `0x1400898d0`
- `0x14008a0f0`

## callees

- `0x140072598`

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
0x140072598  test    rdx, rdx
0x14007259b  jz      short loc_1400725EC
0x14007259d  cmp     rdx, 7FFFFFFFh
0x1400725a4  jbe     short loc_1400725AD
0x1400725a6  mov     eax, 80070057h
0x1400725ab  jmp     short loc_1400725F6
0x1400725ad  mov     eax, 7FFFFFFEh
0x1400725b2  test    rax, rax
0x1400725b5  jz      short loc_1400725D1
0x1400725b7  mov     r9b, [r8]
0x1400725ba  test    r9b, r9b
0x1400725bd  jz      short loc_1400725D1
0x1400725bf  mov     [rcx], r9b
0x1400725c2  inc     r8
0x1400725c5  inc     rcx
0x1400725c8  dec     rax
0x1400725cb  sub     rdx, 1
0x1400725cf  jnz     short loc_1400725B2
0x1400725d1  test    rdx, rdx
0x1400725d4  lea     rax, [rcx-1]
0x1400725d8  cmovnz  rax, rcx
0x1400725dc  neg     rdx
0x1400725df  mov     byte ptr [rax], 0
0x1400725e2  sbb     eax, eax
0x1400725e4  not     eax
0x1400725e6  and     eax, 8007007Ah
0x1400725eb  retn
0x1400725ec  mov     eax, 80070057h
0x1400725f1  test    rdx, rdx
0x1400725f4  jz      short locret_1400725F9
0x1400725f6  mov     byte ptr [rcx], 0
0x1400725f9  retn
```
