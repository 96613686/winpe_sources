# StringCchCatA

- ea: `0x180002cfc`
- end: `0x180002d75`
- name: `StringCchCatA`
- size: `121`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180001bd8`
- `0x180002f0c`
- `0x180014904`

## callees

- `0x180002cfc`
- `0x180004700`

## pseudocode

```c
HRESULT __stdcall StringCchCatA(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)
{
  size_t v5; // r9
  STRSAFE_LPSTR v6; // rax
  HRESULT v7; // edx
  size_t v8; // r8
  size_t v10; // [rsp+20h] [rbp-18h]

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
    return StringCopyWorkerA(&pszDest[v8], cchDest - v8, (size_t *)v8, pszSrc, v10);
  }
  return v7;
}

```

## disassembly

```asm
0x180002cfc  push    rbx
0x180002cfe  sub     rsp, 30h
0x180002d02  lea     rax, [rdx-1]
0x180002d06  mov     rbx, r8
0x180002d09  mov     r10, rdx
0x180002d0c  mov     r11, rcx
0x180002d0f  cmp     rax, 7FFFFFFEh
0x180002d15  ja      short loc_180002D6E
0x180002d17  mov     r9, rdx
0x180002d1a  mov     rax, rcx
0x180002d1d  cmp     byte ptr [rax], 0
0x180002d20  jz      short loc_180002D2B
0x180002d22  inc     rax
0x180002d25  sub     r9, 1
0x180002d29  jnz     short loc_180002D1D
0x180002d2b  mov     rax, r9
0x180002d2e  mov     rcx, r10
0x180002d31  neg     rax
0x180002d34  mov     rax, r9
0x180002d37  sbb     edx, edx
0x180002d39  sub     rcx, r9
0x180002d3c  not     edx
0x180002d3e  and     edx, 80070057h
0x180002d44  neg     rax
0x180002d47  sbb     r8, r8
0x180002d4a  and     r8, rcx; pcchNewDestLength
0x180002d4d  test    r9, r9
0x180002d50  jz      short loc_180002D66
0x180002d52  sub     r10, r8
0x180002d55  lea     rcx, [r8+r11]; pszDest
0x180002d59  mov     rdx, r10; cchDest
0x180002d5c  mov     r9, rbx; pszSrc
0x180002d5f  call    StringCopyWorkerA
0x180002d64  mov     edx, eax
0x180002d66  mov     eax, edx
0x180002d68  add     rsp, 30h
0x180002d6c  pop     rbx
0x180002d6d  retn
0x180002d6e  mov     edx, 80070057h
0x180002d73  jmp     short loc_180002D66
```
