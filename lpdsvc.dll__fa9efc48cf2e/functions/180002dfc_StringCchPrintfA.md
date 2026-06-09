# StringCchPrintfA

- ea: `0x180002dfc`
- end: `0x180002e75`
- name: `StringCchPrintfA`
- size: `121`
- prototype: `HRESULT(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszFormat, ...)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18000276c`
- `0x1800043d0`
- `0x18000453c`
- `0x180004c28`
- `0x1800064e4`
- `0x180006b18`

## callees

- `0x180002678`
- `0x180002dfc`

## pseudocode

```c
HRESULT StringCchPrintfA(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszFormat, ...)
{
  HRESULT result; // eax
  size_t v5; // rbx
  int v6; // eax
  __int64 v7; // rcx
  va_list ArgList; // [rsp+68h] [rbp+20h] BYREF

  va_start(ArgList, pszFormat);
  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
  {
    v5 = cchDest - 1;
    v6 = vsnprintf(pszDest, cchDest - 1, pszFormat, ArgList);
    if ( v6 < 0 || (v7 = v6, v6 > v5) )
    {
      pszDest[v5] = 0;
      return -2147024774;
    }
    else
    {
      result = 0;
      if ( v7 == v5 )
        pszDest[v5] = 0;
    }
  }
  else
  {
    result = -2147024809;
    *pszDest = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180002dfc  mov     [rsp+arg_10], r8
0x180002e01  mov     qword ptr [rsp+ArgList], r9
0x180002e06  push    rbx
0x180002e07  push    rdi
0x180002e08  sub     rsp, 38h
0x180002e0c  mov     rdi, rcx
0x180002e0f  test    rdx, rdx
0x180002e12  jz      short loc_180002E61
0x180002e14  cmp     rdx, 7FFFFFFFh
0x180002e1b  jbe     short loc_180002E24
0x180002e1d  mov     eax, 80070057h
0x180002e22  jmp     short loc_180002E6B
0x180002e24  lea     rbx, [rdx-1]
0x180002e28  mov     [rsp+48h+var_28], 0
0x180002e31  mov     rdx, rbx; BufferCount
0x180002e34  lea     r9, [rsp+48h+ArgList]; ArgList
0x180002e39  call    _vsnprintf
0x180002e3e  test    eax, eax
0x180002e40  js      short loc_180002E56
0x180002e42  movsxd  rcx, eax
0x180002e45  cmp     rcx, rbx
0x180002e48  ja      short loc_180002E56
0x180002e4a  xor     eax, eax
0x180002e4c  cmp     rcx, rbx
0x180002e4f  jnz     short loc_180002E6E
0x180002e51  mov     [rbx+rdi], al
0x180002e54  jmp     short loc_180002E6E
0x180002e56  mov     byte ptr [rbx+rdi], 0
0x180002e5a  mov     eax, 8007007Ah
0x180002e5f  jmp     short loc_180002E6E
0x180002e61  mov     eax, 80070057h
0x180002e66  test    rdx, rdx
0x180002e69  jz      short loc_180002E6E
0x180002e6b  mov     byte ptr [rcx], 0
0x180002e6e  add     rsp, 38h
0x180002e72  pop     rdi
0x180002e73  pop     rbx
0x180002e74  retn
```
