# StringCchCopyW

- ea: `0x180007380`
- end: `0x1800073ed`
- name: `StringCchCopyW`
- size: `109`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x1800012a0`
- `0x180004b70`
- `0x180005760`
- `0x180007cf0`
- `0x18000e520`
- `0x18000e7d4`
- `0x18000ef10`
- `0x18000f028`
- `0x180010c10`
- `0x180011018`
- `0x1800119c0`

## callees

- `0x180007380`

## pseudocode

```c
HRESULT __stdcall StringCchCopyW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  STRSAFE_LPWSTR v3; // r9
  __int64 v4; // rax
  STRSAFE_LPWSTR v5; // rax
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
0x180007380  mov     r9, rcx
0x180007383  test    rdx, rdx
0x180007386  jz      short loc_1800073DC
0x180007388  cmp     rdx, 7FFFFFFFh
0x18000738f  ja      short loc_1800073D5
0x180007391  mov     eax, 7FFFFFFEh
0x180007396  test    rax, rax
0x180007399  jz      short loc_1800073B9
0x18000739b  movzx   ecx, word ptr [r8]
0x18000739f  test    cx, cx
0x1800073a2  jz      short loc_1800073B9
0x1800073a4  mov     [r9], cx
0x1800073a8  add     r8, 2
0x1800073ac  add     r9, 2
0x1800073b0  dec     rax
0x1800073b3  sub     rdx, 1
0x1800073b7  jnz     short loc_180007396
0x1800073b9  test    rdx, rdx
0x1800073bc  lea     rax, [r9-2]
0x1800073c0  cmovnz  rax, r9
0x1800073c4  xor     ecx, ecx
0x1800073c6  test    rdx, rdx
0x1800073c9  mov     [rax], cx
0x1800073cc  mov     eax, 8007007Ah
0x1800073d1  cmovnz  eax, ecx
0x1800073d4  retn
0x1800073d5  mov     eax, 80070057h
0x1800073da  jmp     short loc_1800073E6
0x1800073dc  mov     eax, 80070057h
0x1800073e1  test    rdx, rdx
0x1800073e4  jz      short locret_1800073D4
0x1800073e6  xor     ecx, ecx
0x1800073e8  mov     [r9], cx
0x1800073ec  retn
```
