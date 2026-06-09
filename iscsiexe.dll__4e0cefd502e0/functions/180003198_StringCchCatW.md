# StringCchCatW

- ea: `0x180003198`
- end: `0x180003253`
- name: `StringCchCatW`
- size: `187`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180001fb8`
- `0x180002ea0`
- `0x180005630`
- `0x1800061a8`
- `0x180012bfc`
- `0x180017ccc`
- `0x180018dd0`
- `0x18001afc0`

## callees

- `0x180003198`

## pseudocode

```c
HRESULT __stdcall StringCchCatW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  __int64 v3; // r10
  size_t v5; // r11
  STRSAFE_LPWSTR v6; // rax
  HRESULT v7; // edx
  size_t v8; // rax
  size_t v9; // r9
  wchar_t *i; // rax
  wchar_t *v11; // rcx

  v3 = 2147483646;
  if ( cchDest - 1 > 0x7FFFFFFE )
    return -2147024809;
  v5 = cchDest;
  v6 = pszDest;
  do
  {
    if ( !*v6 )
      break;
    ++v6;
    --v5;
  }
  while ( v5 );
  v7 = v5 == 0 ? 0x80070057 : 0;
  v8 = (cchDest - v5) & -(__int64)(v5 != 0);
  if ( v5 )
  {
    v9 = cchDest - v8;
    for ( i = &pszDest[v8]; v9; --v9 )
    {
      if ( !v3 )
        break;
      if ( !*pszSrc )
        break;
      *i++ = *pszSrc++;
      --v3;
    }
    v11 = i - 1;
    if ( v9 )
      v11 = i;
    v7 = v9 == 0 ? 0x8007007A : 0;
    *v11 = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180003198  mov     [rsp+arg_0], rbx
0x18000319d  mov     [rsp+arg_8], rdi
0x1800031a2  lea     rax, [rdx-1]
0x1800031a6  mov     r10d, 7FFFFFFEh
0x1800031ac  mov     r9, rdx
0x1800031af  mov     rbx, rcx
0x1800031b2  cmp     rax, r10
0x1800031b5  ja      loc_180003241
0x1800031bb  mov     r11, rdx
0x1800031be  mov     rax, rcx
0x1800031c1  xor     edi, edi
0x1800031c3  cmp     [rax], di
0x1800031c6  jz      short loc_1800031D2
0x1800031c8  add     rax, 2
0x1800031cc  sub     r11, 1
0x1800031d0  jnz     short loc_1800031C3
0x1800031d2  mov     rax, r11
0x1800031d5  mov     rcx, r9
0x1800031d8  neg     rax
0x1800031db  mov     rax, r11
0x1800031de  sbb     edx, edx
0x1800031e0  sub     rcx, r11
0x1800031e3  not     edx
0x1800031e5  and     edx, 80070057h
0x1800031eb  neg     rax
0x1800031ee  sbb     rax, rax
0x1800031f1  and     rax, rcx
0x1800031f4  test    r11, r11
0x1800031f7  jz      short loc_180003246
0x1800031f9  sub     r9, rax
0x1800031fc  lea     rax, [rbx+rax*2]
0x180003200  jz      short loc_180003224
0x180003202  test    r10, r10
0x180003205  jz      short loc_180003224
0x180003207  movzx   ecx, word ptr [r8]
0x18000320b  test    cx, cx
0x18000320e  jz      short loc_180003224
0x180003210  mov     [rax], cx
0x180003213  add     r8, 2
0x180003217  add     rax, 2
0x18000321b  dec     r10
0x18000321e  sub     r9, 1
0x180003222  jnz     short loc_180003202
0x180003224  test    r9, r9
0x180003227  lea     rcx, [rax-2]
0x18000322b  cmovnz  rcx, rax
0x18000322f  neg     r9
0x180003232  sbb     edx, edx
0x180003234  not     edx
0x180003236  and     edx, 8007007Ah
0x18000323c  mov     [rcx], di
0x18000323f  jmp     short loc_180003246
0x180003241  mov     edx, 80070057h
0x180003246  mov     rbx, [rsp+arg_0]
0x18000324b  mov     eax, edx
0x18000324d  mov     rdi, [rsp+arg_8]
0x180003252  retn
```
