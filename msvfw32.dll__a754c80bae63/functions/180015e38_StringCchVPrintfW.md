# StringCchVPrintfW

- ea: `0x180015e38`
- end: `0x180015eab`
- name: `StringCchVPrintfW`
- size: `115`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, va_list argList)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180010884`
- `0x180010aa4`
- `0x1800129a0`

## callees

- `0x180001d70`
- `0x180015e38`

## pseudocode

```c
HRESULT __stdcall StringCchVPrintfW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, va_list argList)
{
  HRESULT v5; // edx
  size_t v6; // rbx
  int v7; // eax

  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
  {
    v6 = cchDest - 1;
    v7 = vsnwprintf(pszDest, cchDest - 1, pszFormat, argList);
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
0x180015e38  mov     [rsp+arg_0], rbx
0x180015e3d  push    rdi
0x180015e3e  sub     rsp, 20h
0x180015e42  mov     rax, rdx
0x180015e45  mov     rdi, rcx
0x180015e48  test    rdx, rdx
0x180015e4b  jz      short loc_180015E8F
0x180015e4d  cmp     rax, 7FFFFFFFh
0x180015e53  jbe     short loc_180015E5C
0x180015e55  mov     edx, 80070057h
0x180015e5a  jmp     short loc_180015E99
0x180015e5c  lea     rbx, [rdx-1]
0x180015e60  mov     rdx, rbx; BufferCount
0x180015e63  call    _vsnwprintf
0x180015e68  test    eax, eax
0x180015e6a  js      short loc_180015E82
0x180015e6c  cdqe
0x180015e6e  cmp     rax, rbx
0x180015e71  ja      short loc_180015E82
0x180015e73  xor     edx, edx
0x180015e75  cmp     rax, rbx
0x180015e78  jnz     short loc_180015E9E
0x180015e7a  xor     eax, eax
0x180015e7c  mov     [rdi+rbx*2], ax
0x180015e80  jmp     short loc_180015E9E
0x180015e82  xor     eax, eax
0x180015e84  mov     edx, 8007007Ah
0x180015e89  mov     [rdi+rbx*2], ax
0x180015e8d  jmp     short loc_180015E9E
0x180015e8f  mov     edx, 80070057h
0x180015e94  test    rax, rax
0x180015e97  jz      short loc_180015E9E
0x180015e99  xor     ecx, ecx
0x180015e9b  mov     [rdi], cx
0x180015e9e  mov     rbx, [rsp+28h+arg_0]
0x180015ea3  mov     eax, edx
0x180015ea5  add     rsp, 20h
0x180015ea9  pop     rdi
0x180015eaa  retn
```
