# StringCbCopyA

- ea: `0x1400149d4`
- end: `0x140014a37`
- name: `StringCbCopyA`
- size: `99`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cbDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14004e090`

## callees

- `0x1400149d4`

## pseudocode

```c
HRESULT __stdcall StringCbCopyA(STRSAFE_LPSTR pszDest, size_t cbDest, STRSAFE_LPCSTR pszSrc)
{
  __int64 v3; // rax
  STRSAFE_LPSTR v4; // rax
  HRESULT result; // eax

  if ( !cbDest )
    return -2147024809;
  if ( cbDest > 0x7FFFFFFF )
  {
    result = -2147024809;
    *pszDest = 0;
  }
  else
  {
    v3 = 2147483646;
    do
    {
      if ( !v3 )
        break;
      if ( !*pszSrc )
        break;
      *pszDest++ = *pszSrc++;
      --v3;
      --cbDest;
    }
    while ( cbDest );
    v4 = pszDest - 1;
    if ( cbDest )
      v4 = pszDest;
    *v4 = 0;
    return cbDest == 0 ? 0x8007007A : 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400149d4  test    rdx, rdx
0x1400149d7  jz      short loc_140014A29
0x1400149d9  cmp     rdx, 7FFFFFFFh
0x1400149e0  ja      short loc_140014A22
0x1400149e2  mov     eax, 7FFFFFFEh
0x1400149e7  test    rax, rax
0x1400149ea  jz      short loc_140014A06
0x1400149ec  mov     r9b, [r8]
0x1400149ef  test    r9b, r9b
0x1400149f2  jz      short loc_140014A06
0x1400149f4  mov     [rcx], r9b
0x1400149f7  inc     r8
0x1400149fa  inc     rcx
0x1400149fd  dec     rax
0x140014a00  sub     rdx, 1
0x140014a04  jnz     short loc_1400149E7
0x140014a06  test    rdx, rdx
0x140014a09  lea     rax, [rcx-1]
0x140014a0d  cmovnz  rax, rcx
0x140014a11  neg     rdx
0x140014a14  mov     byte ptr [rax], 0
0x140014a17  sbb     eax, eax
0x140014a19  not     eax
0x140014a1b  and     eax, 8007007Ah
0x140014a20  retn
0x140014a22  mov     eax, 80070057h
0x140014a27  jmp     short loc_140014A33
0x140014a29  mov     eax, 80070057h
0x140014a2e  test    rdx, rdx
0x140014a31  jz      short locret_140014A20
0x140014a33  mov     byte ptr [rcx], 0
0x140014a36  retn
```
