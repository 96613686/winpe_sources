# StringCchPrintfW

- ea: `0x18000bdb0`
- end: `0x18000be33`
- name: `StringCchPrintfW`
- size: `131`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ae70`
- `0x18000ec10`
- `0x18000f504`
- `0x1800116fc`
- `0x180014960`
- `0x180014b74`
- `0x180015384`
- `0x180016de8`
- `0x18001717c`
- `0x1800187e4`
- `0x18001ae6c`
- `0x18001bc24`

## callees

- `0x180001d0c`
- `0x18000bdb0`

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
0x18000bdb0  mov     [rsp+arg_10], r8
0x18000bdb5  mov     qword ptr [rsp+Args], r9
0x18000bdba  push    rbx
0x18000bdbb  push    rdi
0x18000bdbc  sub     rsp, 38h
0x18000bdc0  mov     rax, rdx
0x18000bdc3  mov     rdi, rcx
0x18000bdc6  test    rdx, rdx
0x18000bdc9  jz      short loc_18000BE1B
0x18000bdcb  cmp     rax, 7FFFFFFFh
0x18000bdd1  jbe     short loc_18000BDDA
0x18000bdd3  mov     edx, 80070057h
0x18000bdd8  jmp     short loc_18000BE25
0x18000bdda  lea     rbx, [rdx-1]
0x18000bdde  mov     [rsp+48h+var_28], 0
0x18000bde7  mov     rdx, rbx; BufferCount
0x18000bdea  lea     r9, [rsp+48h+Args]; Args
0x18000bdef  call    _vsnwprintf
0x18000bdf4  test    eax, eax
0x18000bdf6  js      short loc_18000BE0E
0x18000bdf8  cdqe
0x18000bdfa  cmp     rax, rbx
0x18000bdfd  ja      short loc_18000BE0E
0x18000bdff  xor     edx, edx
0x18000be01  cmp     rax, rbx
0x18000be04  jnz     short loc_18000BE2A
0x18000be06  xor     eax, eax
0x18000be08  mov     [rdi+rbx*2], ax
0x18000be0c  jmp     short loc_18000BE2A
0x18000be0e  xor     eax, eax
0x18000be10  mov     edx, 8007007Ah
0x18000be15  mov     [rdi+rbx*2], ax
0x18000be19  jmp     short loc_18000BE2A
0x18000be1b  mov     edx, 80070057h
0x18000be20  test    rax, rax
0x18000be23  jz      short loc_18000BE2A
0x18000be25  xor     ecx, ecx
0x18000be27  mov     [rdi], cx
0x18000be2a  mov     eax, edx
0x18000be2c  add     rsp, 38h
0x18000be30  pop     rdi
0x18000be31  pop     rbx
0x18000be32  retn
```
