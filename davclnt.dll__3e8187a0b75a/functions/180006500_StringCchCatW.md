# StringCchCatW

- ea: `0x180006500`
- end: `0x1800065a4`
- name: `StringCchCatW`
- size: `164`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004bd0`
- `0x1800056e0`

## callees

- `0x180006500`

## pseudocode

```c
HRESULT __stdcall StringCchCatW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  __int64 v3; // r10
  size_t v4; // r9
  STRSAFE_LPWSTR v5; // rax
  wchar_t *v6; // rax
  size_t v7; // rdx
  wchar_t *v8; // rcx
  HRESULT result; // eax

  v3 = 2147483646;
  if ( cchDest - 1 > 0x7FFFFFFE )
    return -2147024809;
  v4 = cchDest;
  v5 = pszDest;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v4;
  }
  while ( v4 );
  if ( !v4 )
    return -2147024809;
  v6 = &pszDest[cchDest - v4];
  v7 = v4;
  do
  {
    if ( !v3 )
      break;
    if ( !*pszSrc )
      break;
    *v6++ = *pszSrc++;
    --v3;
    --v7;
  }
  while ( v7 );
  v8 = v6 - 1;
  if ( v7 )
    v8 = v6;
  *v8 = 0;
  result = -2147024774;
  if ( v7 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180006500  mov     [rsp+arg_0], rbx
0x180006505  lea     rax, [rdx-1]
0x180006509  mov     r10d, 7FFFFFFEh
0x18000650f  cmp     rax, r10
0x180006512  ja      loc_180006597
0x180006518  mov     r9, rdx
0x18000651b  mov     rax, rcx
0x18000651e  xchg    ax, ax
0x180006520  cmp     word ptr [rax], 0
0x180006524  jz      short loc_180006530
0x180006526  add     rax, 2
0x18000652a  sub     r9, 1
0x18000652e  jnz     short loc_180006520
0x180006530  xor     eax, eax
0x180006532  mov     r11, rdx
0x180006535  sub     r11, r9
0x180006538  mov     ebx, 80070057h
0x18000653d  test    r9, r9
0x180006540  cmovz   r11, rax
0x180006544  cmovnz  ebx, eax
0x180006547  jz      short loc_18000659C
0x180006549  lea     rax, [rcx+r11*2]
0x18000654d  sub     rdx, r11
0x180006550  jz      short loc_180006574
0x180006552  test    r10, r10
0x180006555  jz      short loc_180006574
0x180006557  movzx   ecx, word ptr [r8]
0x18000655b  test    cx, cx
0x18000655e  jz      short loc_180006574
0x180006560  mov     [rax], cx
0x180006563  add     r8, 2
0x180006567  add     rax, 2
0x18000656b  dec     r10
0x18000656e  sub     rdx, 1
0x180006572  jnz     short loc_180006552
0x180006574  lea     rcx, [rax-2]
0x180006578  test    rdx, rdx
0x18000657b  cmovnz  rcx, rax
0x18000657f  xor     eax, eax
0x180006581  mov     [rcx], ax
0x180006584  xor     ecx, ecx
0x180006586  test    rdx, rdx
0x180006589  mov     eax, 8007007Ah
0x18000658e  cmovnz  eax, ecx
0x180006591  mov     rbx, [rsp+arg_0]
0x180006596  retn
0x180006597  mov     ebx, 80070057h
0x18000659c  mov     eax, ebx
0x18000659e  mov     rbx, [rsp+arg_0]
0x1800065a3  retn
```
