# StringCbCopyA

- ea: `0x180004134`
- end: `0x180004196`
- name: `StringCbCopyA`
- size: `98`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cbDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x1800023a8`
- `0x180004388`
- `0x180014d00`
- `0x1800152a0`
- `0x180015320`
- `0x180015ae0`
- `0x180017790`
- `0x18001b910`
- `0x18001d7b0`
- `0x180020ee0`
- `0x180022270`
- `0x180023620`
- `0x180023ab0`
- `0x180023b34`
- `0x180023e30`
- `0x180025300`
- `0x180026060`
- `0x180029400`
- `0x180029a2c`
- `0x180029b8c`
- `0x180029d0c`

## callees

- `0x180004134`

## pseudocode

```c
HRESULT __stdcall StringCbCopyA(STRSAFE_LPSTR pszDest, size_t cbDest, STRSAFE_LPCSTR pszSrc)
{
  HRESULT result; // eax
  __int64 v4; // rax
  STRSAFE_LPSTR v5; // rax

  if ( !cbDest )
    return -2147024809;
  if ( cbDest <= 0x7FFFFFFF )
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
      --cbDest;
    }
    while ( cbDest );
    v5 = pszDest - 1;
    if ( cbDest )
      v5 = pszDest;
    *v5 = 0;
    return cbDest == 0 ? 0x8007007A : 0;
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
0x180004134  test    rdx, rdx
0x180004137  jz      short loc_180004188
0x180004139  cmp     rdx, 7FFFFFFFh
0x180004140  jbe     short loc_180004149
0x180004142  mov     eax, 80070057h
0x180004147  jmp     short loc_180004192
0x180004149  mov     eax, 7FFFFFFEh
0x18000414e  test    rax, rax
0x180004151  jz      short loc_18000416D
0x180004153  mov     r9b, [r8]
0x180004156  test    r9b, r9b
0x180004159  jz      short loc_18000416D
0x18000415b  mov     [rcx], r9b
0x18000415e  inc     r8
0x180004161  inc     rcx
0x180004164  dec     rax
0x180004167  sub     rdx, 1
0x18000416b  jnz     short loc_18000414E
0x18000416d  test    rdx, rdx
0x180004170  lea     rax, [rcx-1]
0x180004174  cmovnz  rax, rcx
0x180004178  neg     rdx
0x18000417b  mov     byte ptr [rax], 0
0x18000417e  sbb     eax, eax
0x180004180  not     eax
0x180004182  and     eax, 8007007Ah
0x180004187  retn
0x180004188  mov     eax, 80070057h
0x18000418d  test    rdx, rdx
0x180004190  jz      short locret_180004195
0x180004192  mov     byte ptr [rcx], 0
0x180004195  retn
```
