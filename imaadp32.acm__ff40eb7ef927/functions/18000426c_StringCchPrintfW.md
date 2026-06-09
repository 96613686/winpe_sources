# StringCchPrintfW

- ea: `0x18000426c`
- end: `0x1800042ef`
- name: `StringCchPrintfW`
- size: `131`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004300`

## callees

- `0x180001cb8`
- `0x18000426c`

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
0x18000426c  mov     [rsp+arg_10], r8
0x180004271  mov     qword ptr [rsp+Args], r9
0x180004276  push    rbx
0x180004277  push    rdi
0x180004278  sub     rsp, 38h
0x18000427c  mov     rax, rdx
0x18000427f  mov     rdi, rcx
0x180004282  test    rdx, rdx
0x180004285  jz      short loc_1800042D7
0x180004287  cmp     rax, 7FFFFFFFh
0x18000428d  jbe     short loc_180004296
0x18000428f  mov     edx, 80070057h
0x180004294  jmp     short loc_1800042E1
0x180004296  lea     rbx, [rdx-1]
0x18000429a  mov     [rsp+48h+var_28], 0
0x1800042a3  mov     rdx, rbx; BufferCount
0x1800042a6  lea     r9, [rsp+48h+Args]; Args
0x1800042ab  call    _vsnwprintf
0x1800042b0  test    eax, eax
0x1800042b2  js      short loc_1800042CA
0x1800042b4  cdqe
0x1800042b6  cmp     rax, rbx
0x1800042b9  ja      short loc_1800042CA
0x1800042bb  xor     edx, edx
0x1800042bd  cmp     rax, rbx
0x1800042c0  jnz     short loc_1800042E6
0x1800042c2  xor     eax, eax
0x1800042c4  mov     [rdi+rbx*2], ax
0x1800042c8  jmp     short loc_1800042E6
0x1800042ca  xor     eax, eax
0x1800042cc  mov     edx, 8007007Ah
0x1800042d1  mov     [rdi+rbx*2], ax
0x1800042d5  jmp     short loc_1800042E6
0x1800042d7  mov     edx, 80070057h
0x1800042dc  test    rax, rax
0x1800042df  jz      short loc_1800042E6
0x1800042e1  xor     ecx, ecx
0x1800042e3  mov     [rdi], cx
0x1800042e6  mov     eax, edx
0x1800042e8  add     rsp, 38h
0x1800042ec  pop     rdi
0x1800042ed  pop     rbx
0x1800042ee  retn
```
