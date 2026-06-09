# StringCchCopyW

- ea: `0x180010580`
- end: `0x1800105cc`
- name: `StringCchCopyW`
- size: `76`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180010280`

## callees

- `0x180010580`

## pseudocode

```c
HRESULT __stdcall StringCchCopyW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  __int64 v4; // rax
  __int64 v5; // r9
  STRSAFE_LPWSTR v6; // rdx
  HRESULT result; // eax

  v4 = 2147483646;
  v5 = 64;
  do
  {
    if ( !v4 )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --v4;
    --v5;
  }
  while ( v5 );
  v6 = pszDest - 1;
  result = -2147024774;
  if ( v5 )
  {
    v6 = pszDest;
    result = 0;
  }
  *v6 = 0;
  return result;
}

```

## disassembly

```asm
0x180010580  mov     r10, rcx
0x180010583  mov     eax, 7FFFFFFEh
0x180010588  mov     r9d, 40h ; '@'
0x18001058e  xchg    ax, ax
0x180010590  test    rax, rax
0x180010593  jz      short loc_1800105B3
0x180010595  movzx   edx, word ptr [r8]
0x180010599  test    dx, dx
0x18001059c  jz      short loc_1800105B3
0x18001059e  mov     [r10], dx
0x1800105a2  add     r8, 2
0x1800105a6  add     r10, 2
0x1800105aa  dec     rax
0x1800105ad  sub     r9, 1
0x1800105b1  jnz     short loc_180010590
0x1800105b3  xor     ecx, ecx
0x1800105b5  lea     rdx, [r10-2]
0x1800105b9  test    r9, r9
0x1800105bc  mov     eax, 8007007Ah
0x1800105c1  cmovnz  rdx, r10
0x1800105c5  cmovnz  eax, ecx
0x1800105c8  mov     [rdx], cx
0x1800105cb  retn
```
