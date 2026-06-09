# StringCchPrintfW

- ea: `0x180005a90`
- end: `0x180005b14`
- name: `StringCchPrintfW`
- size: `132`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005998`

## callees

- `0x180005a90`

## import_xrefs

- `ntdll!_vsnwprintf` at `0x180005acf`
- `ntdll!_vsnwprintf` at `0x180005acf`

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
0x180005a90  mov     [rsp+arg_10], r8
0x180005a95  mov     qword ptr [rsp+Args], r9
0x180005a9a  push    rbx
0x180005a9b  push    rdi
0x180005a9c  sub     rsp, 38h
0x180005aa0  mov     rax, rdx
0x180005aa3  mov     rdi, rcx
0x180005aa6  test    rdx, rdx
0x180005aa9  jz      short loc_180005AFC
0x180005aab  cmp     rax, 7FFFFFFFh
0x180005ab1  jbe     short loc_180005ABA
0x180005ab3  mov     edx, 80070057h
0x180005ab8  jmp     short loc_180005B06
0x180005aba  lea     rbx, [rdx-1]
0x180005abe  mov     [rsp+48h+var_28], 0
0x180005ac7  mov     rdx, rbx; BufferCount
0x180005aca  lea     r9, [rsp+48h+Args]; Args
0x180005acf  call    cs:__imp__vsnwprintf
0x180005ad5  test    eax, eax
0x180005ad7  js      short loc_180005AEF
0x180005ad9  cdqe
0x180005adb  cmp     rax, rbx
0x180005ade  ja      short loc_180005AEF
0x180005ae0  xor     edx, edx
0x180005ae2  cmp     rax, rbx
0x180005ae5  jnz     short loc_180005B0B
0x180005ae7  xor     eax, eax
0x180005ae9  mov     [rdi+rbx*2], ax
0x180005aed  jmp     short loc_180005B0B
0x180005aef  xor     eax, eax
0x180005af1  mov     edx, 8007007Ah
0x180005af6  mov     [rdi+rbx*2], ax
0x180005afa  jmp     short loc_180005B0B
0x180005afc  mov     edx, 80070057h
0x180005b01  test    rax, rax
0x180005b04  jz      short loc_180005B0B
0x180005b06  xor     ecx, ecx
0x180005b08  mov     [rdi], cx
0x180005b0b  mov     eax, edx
0x180005b0d  add     rsp, 38h
0x180005b11  pop     rdi
0x180005b12  pop     rbx
0x180005b13  retn
```
