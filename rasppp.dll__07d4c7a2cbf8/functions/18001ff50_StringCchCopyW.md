# StringCchCopyW

- ea: `0x18001ff50`
- end: `0x18001ffbb`
- name: `StringCchCopyW`
- size: `107`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x18001df60`
- `0x18001ffc4`
- `0x18002038c`
- `0x1800205d4`
- `0x18002a350`
- `0x18002a7e0`
- `0x18002bd68`
- `0x18002bee8`
- `0x18002d904`
- `0x18002e34c`
- `0x18002e4ec`
- `0x18002e63c`

## callees

- `0x18001ff50`

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
0x18001ff50  xor     r10d, r10d
0x18001ff53  mov     r9, rcx
0x18001ff56  test    rdx, rdx
0x18001ff59  jz      short loc_18001FFAC
0x18001ff5b  cmp     rdx, 7FFFFFFFh
0x18001ff62  jbe     short loc_18001FF6B
0x18001ff64  mov     eax, 80070057h
0x18001ff69  jmp     short loc_18001FFB6
0x18001ff6b  mov     eax, 7FFFFFFEh
0x18001ff70  test    rax, rax
0x18001ff73  jz      short loc_18001FF93
0x18001ff75  movzx   ecx, word ptr [r8]
0x18001ff79  test    cx, cx
0x18001ff7c  jz      short loc_18001FF93
0x18001ff7e  mov     [r9], cx
0x18001ff82  add     r8, 2
0x18001ff86  add     r9, 2
0x18001ff8a  dec     rax
0x18001ff8d  sub     rdx, 1
0x18001ff91  jnz     short loc_18001FF70
0x18001ff93  test    rdx, rdx
0x18001ff96  lea     rcx, [r9-2]
0x18001ff9a  cmovnz  rcx, r9
0x18001ff9e  neg     rdx
0x18001ffa1  sbb     eax, eax
0x18001ffa3  not     eax
0x18001ffa5  and     eax, 8007007Ah
0x18001ffaa  jmp     short loc_18001FFB6
0x18001ffac  mov     eax, 80070057h
0x18001ffb1  test    rdx, rdx
0x18001ffb4  jz      short locret_18001FFBA
0x18001ffb6  mov     [rcx], r10w
0x18001ffba  retn
```
