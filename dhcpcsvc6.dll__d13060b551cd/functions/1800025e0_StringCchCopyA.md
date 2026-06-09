# StringCchCopyA

- ea: `0x1800025e0`
- end: `0x180002646`
- name: `StringCchCopyA`
- size: `102`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`

## callees

- `0x1800025e0`

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
0x1800025e0  mov     r9, rcx
0x1800025e3  test    rdx, rdx
0x1800025e6  jz      short loc_180002638
0x1800025e8  cmp     rdx, 7FFFFFFFh
0x1800025ef  ja      short loc_180002631
0x1800025f1  mov     eax, 7FFFFFFEh
0x1800025f6  test    rax, rax
0x1800025f9  jz      short loc_180002615
0x1800025fb  movzx   ecx, byte ptr [r8]
0x1800025ff  test    cl, cl
0x180002601  jz      short loc_180002615
0x180002603  mov     [r9], cl
0x180002606  inc     r8
0x180002609  inc     r9
0x18000260c  dec     rax
0x18000260f  sub     rdx, 1
0x180002613  jnz     short loc_1800025F6
0x180002615  test    rdx, rdx
0x180002618  lea     rax, [r9-1]
0x18000261c  cmovnz  rax, r9
0x180002620  xor     ecx, ecx
0x180002622  test    rdx, rdx
0x180002625  mov     byte ptr [rax], 0
0x180002628  mov     eax, 8007007Ah
0x18000262d  cmovnz  eax, ecx
0x180002630  retn
0x180002631  mov     eax, 80070057h
0x180002636  jmp     short loc_180002642
0x180002638  mov     eax, 80070057h
0x18000263d  test    rdx, rdx
0x180002640  jz      short locret_180002630
0x180002642  mov     byte ptr [rcx], 0
0x180002645  retn
```
