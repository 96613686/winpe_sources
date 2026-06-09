# StringCchCatW

- ea: `0x180002198`
- end: `0x180002226`
- name: `StringCchCatW`
- size: `142`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180001fd8`
- `0x180003bf0`
- `0x180003ca0`
- `0x1800043b0`
- `0x18000eb40`
- `0x180012ac4`
- `0x180014adc`
- `0x180015234`

## callees

- `0x180002198`
- `0x18000231c`

## pseudocode

```c
HRESULT __stdcall StringCchCatW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  size_t v5; // r9
  STRSAFE_LPWSTR v6; // rax
  HRESULT v7; // edx
  size_t v8; // r8

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
  if ( v5 )
  {
    v8 = (cchDest - v5) & -(__int64)(v5 != 0);
    return StringCopyWorkerW(&pszDest[v8], cchDest - v8, (size_t *)v8, pszSrc, 0x7FFFFFFEu);
  }
  return v7;
}

```

## disassembly

```asm
0x180002198  mov     [rsp+arg_0], rbx
0x18000219d  push    rdi
0x18000219e  sub     rsp, 30h
0x1800021a2  lea     rax, [rdx-1]
0x1800021a6  mov     rbx, r8
0x1800021a9  mov     r10, rdx
0x1800021ac  mov     r11, rcx
0x1800021af  cmp     rax, 7FFFFFFEh
0x1800021b5  ja      short loc_180002214
0x1800021b7  mov     r9, rdx
0x1800021ba  mov     rax, rcx
0x1800021bd  xor     edi, edi
0x1800021bf  cmp     [rax], di
0x1800021c2  jz      short loc_1800021CE
0x1800021c4  add     rax, 2
0x1800021c8  sub     r9, 1
0x1800021cc  jnz     short loc_1800021BF
0x1800021ce  mov     rax, r9
0x1800021d1  mov     rcx, r10
0x1800021d4  neg     rax
0x1800021d7  mov     rax, r9
0x1800021da  sbb     edx, edx
0x1800021dc  sub     rcx, r9
0x1800021df  not     edx
0x1800021e1  and     edx, 80070057h
0x1800021e7  neg     rax
0x1800021ea  sbb     r8, r8
0x1800021ed  and     r8, rcx; pcchNewDestLength
0x1800021f0  test    r9, r9
0x1800021f3  jz      short loc_180002219
0x1800021f5  sub     r10, r8
0x1800021f8  mov     [rsp+38h+cchToCopy], 7FFFFFFEh; cchToCopy
0x180002201  mov     rdx, r10; cchDest
0x180002204  lea     rcx, [r11+r8*2]; pszDest
0x180002208  mov     r9, rbx; pszSrc
0x18000220b  call    StringCopyWorkerW
0x180002210  mov     edx, eax
0x180002212  jmp     short loc_180002219
0x180002214  mov     edx, 80070057h
0x180002219  mov     rbx, [rsp+38h+arg_0]
0x18000221e  mov     eax, edx
0x180002220  add     rsp, 30h
0x180002224  pop     rdi
0x180002225  retn
```
