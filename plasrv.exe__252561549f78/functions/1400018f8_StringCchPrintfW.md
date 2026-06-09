# StringCchPrintfW

- ea: `0x1400018f8`
- end: `0x14000197c`
- name: `StringCchPrintfW`
- size: `132`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001984`

## callees

- `0x1400018f8`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x140001937`
- `msvcrt!_vsnwprintf` at `0x140001937`

## pseudocode

```c
HRESULT StringCchPrintfW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)
{
  HRESULT v4; // edx
  size_t v5; // rbx
  int v6; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, pszFormat);
  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
  {
    v5 = cchDest - 1;
    v6 = _vsnwprintf(pszDest, cchDest - 1, pszFormat, Args);
    if ( v6 < 0 || v6 > v5 )
    {
      v4 = -2147024774;
      pszDest[v5] = 0;
    }
    else
    {
      v4 = 0;
      if ( v6 == v5 )
        pszDest[v5] = 0;
    }
  }
  else
  {
    v4 = -2147024809;
    *pszDest = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x1400018f8  mov     [rsp+arg_10], r8
0x1400018fd  mov     qword ptr [rsp+Args], r9
0x140001902  push    rbx
0x140001903  push    rdi
0x140001904  sub     rsp, 38h
0x140001908  mov     rax, rdx
0x14000190b  mov     rdi, rcx
0x14000190e  test    rdx, rdx
0x140001911  jz      short loc_140001964
0x140001913  cmp     rax, 7FFFFFFFh
0x140001919  jbe     short loc_140001922
0x14000191b  mov     edx, 80070057h
0x140001920  jmp     short loc_14000196E
0x140001922  lea     rbx, [rdx-1]
0x140001926  mov     [rsp+48h+var_28], 0
0x14000192f  mov     rdx, rbx; BufferCount
0x140001932  lea     r9, [rsp+48h+Args]; Args
0x140001937  call    cs:__imp__vsnwprintf
0x14000193d  test    eax, eax
0x14000193f  js      short loc_140001957
0x140001941  cdqe
0x140001943  cmp     rax, rbx
0x140001946  ja      short loc_140001957
0x140001948  xor     edx, edx
0x14000194a  cmp     rax, rbx
0x14000194d  jnz     short loc_140001973
0x14000194f  xor     eax, eax
0x140001951  mov     [rdi+rbx*2], ax
0x140001955  jmp     short loc_140001973
0x140001957  xor     eax, eax
0x140001959  mov     edx, 8007007Ah
0x14000195e  mov     [rdi+rbx*2], ax
0x140001962  jmp     short loc_140001973
0x140001964  mov     edx, 80070057h
0x140001969  test    rax, rax
0x14000196c  jz      short loc_140001973
0x14000196e  xor     ecx, ecx
0x140001970  mov     [rdi], cx
0x140001973  mov     eax, edx
0x140001975  add     rsp, 38h
0x140001979  pop     rdi
0x14000197a  pop     rbx
0x14000197b  retn
```
