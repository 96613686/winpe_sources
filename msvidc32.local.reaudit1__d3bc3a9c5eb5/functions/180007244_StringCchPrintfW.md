# StringCchPrintfW

- ea: `0x180007244`
- end: `0x1800072c7`
- name: `StringCchPrintfW`
- size: `131`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006940`

## callees

- `0x180001cd8`
- `0x180007244`

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
    v6 = vsnwprintf(pszDest, cchDest - 1, pszFormat, Args);
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
0x180007244  mov     [rsp+arg_10], r8
0x180007249  mov     qword ptr [rsp+Args], r9
0x18000724e  push    rbx
0x18000724f  push    rdi
0x180007250  sub     rsp, 38h
0x180007254  mov     rax, rdx
0x180007257  mov     rdi, rcx
0x18000725a  test    rdx, rdx
0x18000725d  jz      short loc_1800072AF
0x18000725f  cmp     rax, 7FFFFFFFh
0x180007265  jbe     short loc_18000726E
0x180007267  mov     edx, 80070057h
0x18000726c  jmp     short loc_1800072B9
0x18000726e  lea     rbx, [rdx-1]
0x180007272  mov     [rsp+48h+var_28], 0
0x18000727b  mov     rdx, rbx; BufferCount
0x18000727e  lea     r9, [rsp+48h+Args]; Args
0x180007283  call    _vsnwprintf
0x180007288  test    eax, eax
0x18000728a  js      short loc_1800072A2
0x18000728c  cdqe
0x18000728e  cmp     rax, rbx
0x180007291  ja      short loc_1800072A2
0x180007293  xor     edx, edx
0x180007295  cmp     rax, rbx
0x180007298  jnz     short loc_1800072BE
0x18000729a  xor     eax, eax
0x18000729c  mov     [rdi+rbx*2], ax
0x1800072a0  jmp     short loc_1800072BE
0x1800072a2  xor     eax, eax
0x1800072a4  mov     edx, 8007007Ah
0x1800072a9  mov     [rdi+rbx*2], ax
0x1800072ad  jmp     short loc_1800072BE
0x1800072af  mov     edx, 80070057h
0x1800072b4  test    rax, rax
0x1800072b7  jz      short loc_1800072BE
0x1800072b9  xor     ecx, ecx
0x1800072bb  mov     [rdi], cx
0x1800072be  mov     eax, edx
0x1800072c0  add     rsp, 38h
0x1800072c4  pop     rdi
0x1800072c5  pop     rbx
0x1800072c6  retn
```
