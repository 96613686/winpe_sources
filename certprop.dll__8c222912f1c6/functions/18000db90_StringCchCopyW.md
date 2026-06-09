# StringCchCopyW

- ea: `0x18000db90`
- end: `0x18000dbfb`
- name: `StringCchCopyW`
- size: `107`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180001e90`
- `0x180005830`
- `0x18000e888`
- `0x180015554`
- `0x180018974`
- `0x18001913c`
- `0x1800197a4`
- `0x18001eca8`
- `0x18001fdfc`

## callees

- `0x18000db90`

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
0x18000db90  xor     r10d, r10d
0x18000db93  mov     r9, rcx
0x18000db96  test    rdx, rdx
0x18000db99  jz      short loc_18000DBEC
0x18000db9b  cmp     rdx, 7FFFFFFFh
0x18000dba2  jbe     short loc_18000DBAB
0x18000dba4  mov     eax, 80070057h
0x18000dba9  jmp     short loc_18000DBF6
0x18000dbab  mov     eax, 7FFFFFFEh
0x18000dbb0  test    rax, rax
0x18000dbb3  jz      short loc_18000DBD3
0x18000dbb5  movzx   ecx, word ptr [r8]
0x18000dbb9  test    cx, cx
0x18000dbbc  jz      short loc_18000DBD3
0x18000dbbe  mov     [r9], cx
0x18000dbc2  add     r8, 2
0x18000dbc6  add     r9, 2
0x18000dbca  dec     rax
0x18000dbcd  sub     rdx, 1
0x18000dbd1  jnz     short loc_18000DBB0
0x18000dbd3  test    rdx, rdx
0x18000dbd6  lea     rcx, [r9-2]
0x18000dbda  cmovnz  rcx, r9
0x18000dbde  neg     rdx
0x18000dbe1  sbb     eax, eax
0x18000dbe3  not     eax
0x18000dbe5  and     eax, 8007007Ah
0x18000dbea  jmp     short loc_18000DBF6
0x18000dbec  mov     eax, 80070057h
0x18000dbf1  test    rdx, rdx
0x18000dbf4  jz      short locret_18000DBFA
0x18000dbf6  mov     [rcx], r10w
0x18000dbfa  retn
```
