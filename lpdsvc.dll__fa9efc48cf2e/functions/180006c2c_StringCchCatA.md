# StringCchCatA

- ea: `0x180006c2c`
- end: `0x180006cd1`
- name: `StringCchCatA`
- size: `165`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800064e4`
- `0x180006cd8`

## callees

- `0x180006c2c`

## pseudocode

```c
HRESULT __stdcall StringCchCatA(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)
{
  __int64 v3; // r10
  size_t v5; // r11
  STRSAFE_LPSTR v6; // rax
  HRESULT v7; // edx
  size_t v8; // rax
  char *v9; // rcx
  size_t i; // r9
  char *v11; // rax

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
    v9 = &pszDest[v8];
    for ( i = cchDest - v8; i; --i )
    {
      if ( !v3 )
        break;
      if ( !*pszSrc )
        break;
      *v9++ = *pszSrc++;
      --v3;
    }
    v11 = v9 - 1;
    if ( i )
      v11 = v9;
    v7 = i == 0 ? 0x8007007A : 0;
    *v11 = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180006c2c  mov     [rsp+arg_0], rbx
0x180006c31  lea     rax, [rdx-1]
0x180006c35  mov     r10d, 7FFFFFFEh
0x180006c3b  mov     r9, rdx
0x180006c3e  mov     rbx, rcx
0x180006c41  cmp     rax, r10
0x180006c44  ja      short loc_180006CC4
0x180006c46  mov     r11, rdx
0x180006c49  mov     rax, rcx
0x180006c4c  cmp     byte ptr [rax], 0
0x180006c4f  jz      short loc_180006C5A
0x180006c51  inc     rax
0x180006c54  sub     r11, 1
0x180006c58  jnz     short loc_180006C4C
0x180006c5a  mov     rax, r11
0x180006c5d  mov     rcx, r9
0x180006c60  neg     rax
0x180006c63  mov     rax, r11
0x180006c66  sbb     edx, edx
0x180006c68  sub     rcx, r11
0x180006c6b  not     edx
0x180006c6d  and     edx, 80070057h
0x180006c73  neg     rax
0x180006c76  sbb     rax, rax
0x180006c79  and     rax, rcx
0x180006c7c  test    r11, r11
0x180006c7f  jz      short loc_180006CC9
0x180006c81  lea     rcx, [rax+rbx]
0x180006c85  sub     r9, rax
0x180006c88  jz      short loc_180006CA7
0x180006c8a  test    r10, r10
0x180006c8d  jz      short loc_180006CA7
0x180006c8f  mov     al, [r8]
0x180006c92  test    al, al
0x180006c94  jz      short loc_180006CA7
0x180006c96  mov     [rcx], al
0x180006c98  inc     r8
0x180006c9b  inc     rcx
0x180006c9e  dec     r10
0x180006ca1  sub     r9, 1
0x180006ca5  jnz     short loc_180006C8A
0x180006ca7  test    r9, r9
0x180006caa  lea     rax, [rcx-1]
0x180006cae  cmovnz  rax, rcx
0x180006cb2  neg     r9
0x180006cb5  sbb     edx, edx
0x180006cb7  not     edx
0x180006cb9  and     edx, 8007007Ah
0x180006cbf  mov     byte ptr [rax], 0
0x180006cc2  jmp     short loc_180006CC9
0x180006cc4  mov     edx, 80070057h
0x180006cc9  mov     rbx, [rsp+arg_0]
0x180006cce  mov     eax, edx
0x180006cd0  retn
```
