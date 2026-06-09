# StringCchCopyW

- ea: `0x18000325c`
- end: `0x1800032c7`
- name: `StringCchCopyW`
- size: `107`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `27`
- callee_count: `1`
- tags: ``

## callers

- `0x180001fb8`
- `0x180002474`
- `0x180002ea0`
- `0x180003840`
- `0x1800045d0`
- `0x180005630`
- `0x180005720`
- `0x180005d2c`
- `0x1800060e0`
- `0x1800061a8`
- `0x180006c30`
- `0x1800074e8`
- `0x180007f80`
- `0x1800080b0`
- `0x18000be3c`
- `0x18000c474`
- `0x18000ec10`
- `0x180010e4c`
- `0x1800116fc`
- `0x180012bfc`
- `0x180012e28`
- `0x180017ccc`
- `0x1800187e4`
- `0x180018974`
- `0x180018dd0`
- `0x180018e80`
- `0x18001ae6c`

## callees

- `0x18000325c`

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
0x18000325c  xor     r10d, r10d
0x18000325f  mov     r9, rcx
0x180003262  test    rdx, rdx
0x180003265  jz      short loc_1800032B8
0x180003267  cmp     rdx, 7FFFFFFFh
0x18000326e  jbe     short loc_180003277
0x180003270  mov     eax, 80070057h
0x180003275  jmp     short loc_1800032C2
0x180003277  mov     eax, 7FFFFFFEh
0x18000327c  test    rax, rax
0x18000327f  jz      short loc_18000329F
0x180003281  movzx   ecx, word ptr [r8]
0x180003285  test    cx, cx
0x180003288  jz      short loc_18000329F
0x18000328a  mov     [r9], cx
0x18000328e  add     r8, 2
0x180003292  add     r9, 2
0x180003296  dec     rax
0x180003299  sub     rdx, 1
0x18000329d  jnz     short loc_18000327C
0x18000329f  test    rdx, rdx
0x1800032a2  lea     rcx, [r9-2]
0x1800032a6  cmovnz  rcx, r9
0x1800032aa  neg     rdx
0x1800032ad  sbb     eax, eax
0x1800032af  not     eax
0x1800032b1  and     eax, 8007007Ah
0x1800032b6  jmp     short loc_1800032C2
0x1800032b8  mov     eax, 80070057h
0x1800032bd  test    rdx, rdx
0x1800032c0  jz      short locret_1800032C6
0x1800032c2  mov     [rcx], r10w
0x1800032c6  retn
```
