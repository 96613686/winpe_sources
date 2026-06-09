# StringCchPrintfW

- ea: `0x180004560`
- end: `0x1800045e4`
- name: `StringCchPrintfW`
- size: `132`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004658`
- `0x180004ec4`

## callees

- `0x180004560`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000459f`
- `msvcrt!_vsnwprintf` at `0x18000459f`

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
0x180004560  mov     [rsp+arg_10], r8
0x180004565  mov     qword ptr [rsp+Args], r9
0x18000456a  push    rbx
0x18000456b  push    rdi
0x18000456c  sub     rsp, 38h
0x180004570  mov     rax, rdx
0x180004573  mov     rdi, rcx
0x180004576  test    rdx, rdx
0x180004579  jz      short loc_1800045CC
0x18000457b  cmp     rax, 7FFFFFFFh
0x180004581  jbe     short loc_18000458A
0x180004583  mov     edx, 80070057h
0x180004588  jmp     short loc_1800045D6
0x18000458a  lea     rbx, [rdx-1]
0x18000458e  mov     [rsp+48h+var_28], 0
0x180004597  mov     rdx, rbx; BufferCount
0x18000459a  lea     r9, [rsp+48h+Args]; Args
0x18000459f  call    cs:__imp__vsnwprintf
0x1800045a5  test    eax, eax
0x1800045a7  js      short loc_1800045BF
0x1800045a9  cdqe
0x1800045ab  cmp     rax, rbx
0x1800045ae  ja      short loc_1800045BF
0x1800045b0  xor     edx, edx
0x1800045b2  cmp     rax, rbx
0x1800045b5  jnz     short loc_1800045DB
0x1800045b7  xor     eax, eax
0x1800045b9  mov     [rdi+rbx*2], ax
0x1800045bd  jmp     short loc_1800045DB
0x1800045bf  xor     eax, eax
0x1800045c1  mov     edx, 8007007Ah
0x1800045c6  mov     [rdi+rbx*2], ax
0x1800045ca  jmp     short loc_1800045DB
0x1800045cc  mov     edx, 80070057h
0x1800045d1  test    rax, rax
0x1800045d4  jz      short loc_1800045DB
0x1800045d6  xor     ecx, ecx
0x1800045d8  mov     [rdi], cx
0x1800045db  mov     eax, edx
0x1800045dd  add     rsp, 38h
0x1800045e1  pop     rdi
0x1800045e2  pop     rbx
0x1800045e3  retn
```
