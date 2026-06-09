# StringCbPrintfW

- ea: `0x180002888`
- end: `0x18000290c`
- name: `StringCbPrintfW`
- size: `132`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002658`

## callees

- `0x180002888`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1800028c7`
- `msvcrt!_vsnwprintf` at `0x1800028c7`

## pseudocode

```c
HRESULT StringCbPrintfW(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszFormat, ...)
{
  size_t v4; // rax
  HRESULT v5; // edx
  unsigned __int64 v6; // rbx
  int v7; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, pszFormat);
  v4 = cbDest >> 1;
  if ( !(cbDest >> 1) )
    return -2147024809;
  if ( v4 <= 0x7FFFFFFF )
  {
    v6 = v4 - 1;
    v7 = _vsnwprintf(pszDest, v4 - 1, pszFormat, Args);
    if ( v7 < 0 || v7 > v6 )
    {
      v5 = -2147024774;
      pszDest[v6] = 0;
    }
    else
    {
      v5 = 0;
      if ( v7 == v6 )
        pszDest[v6] = 0;
    }
  }
  else
  {
    v5 = -2147024809;
    *pszDest = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180002888  mov     [rsp+arg_10], r8
0x18000288d  mov     qword ptr [rsp+Args], r9
0x180002892  push    rbx
0x180002893  push    rdi
0x180002894  sub     rsp, 38h
0x180002898  mov     rax, rdx
0x18000289b  mov     rdi, rcx
0x18000289e  shr     rax, 1
0x1800028a1  jz      short loc_1800028F4
0x1800028a3  cmp     rax, 7FFFFFFFh
0x1800028a9  jbe     short loc_1800028B2
0x1800028ab  mov     edx, 80070057h
0x1800028b0  jmp     short loc_1800028FE
0x1800028b2  lea     rbx, [rax-1]
0x1800028b6  mov     [rsp+48h+var_28], 0
0x1800028bf  mov     rdx, rbx; BufferCount
0x1800028c2  lea     r9, [rsp+48h+Args]; Args
0x1800028c7  call    cs:__imp__vsnwprintf
0x1800028cd  test    eax, eax
0x1800028cf  js      short loc_1800028E7
0x1800028d1  cdqe
0x1800028d3  cmp     rax, rbx
0x1800028d6  ja      short loc_1800028E7
0x1800028d8  xor     edx, edx
0x1800028da  cmp     rax, rbx
0x1800028dd  jnz     short loc_180002903
0x1800028df  xor     eax, eax
0x1800028e1  mov     [rdi+rbx*2], ax
0x1800028e5  jmp     short loc_180002903
0x1800028e7  xor     eax, eax
0x1800028e9  mov     edx, 8007007Ah
0x1800028ee  mov     [rdi+rbx*2], ax
0x1800028f2  jmp     short loc_180002903
0x1800028f4  mov     edx, 80070057h
0x1800028f9  test    rax, rax
0x1800028fc  jz      short loc_180002903
0x1800028fe  xor     ecx, ecx
0x180002900  mov     [rdi], cx
0x180002903  mov     eax, edx
0x180002905  add     rsp, 38h
0x180002909  pop     rdi
0x18000290a  pop     rbx
0x18000290b  retn
```
