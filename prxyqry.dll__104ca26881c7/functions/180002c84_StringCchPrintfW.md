# StringCchPrintfW

- ea: `0x180002c84`
- end: `0x180002d08`
- name: `StringCchPrintfW`
- size: `132`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002560`

## callees

- `0x180002c84`

## import_xrefs

- `ntdll!_vsnwprintf` at `0x180002cc3`
- `ntdll!_vsnwprintf` at `0x180002cc3`

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
0x180002c84  mov     [rsp+arg_10], r8
0x180002c89  mov     qword ptr [rsp+Args], r9
0x180002c8e  push    rbx
0x180002c8f  push    rdi
0x180002c90  sub     rsp, 38h
0x180002c94  mov     rax, rdx
0x180002c97  mov     rdi, rcx
0x180002c9a  test    rdx, rdx
0x180002c9d  jz      short loc_180002CF0
0x180002c9f  cmp     rax, 7FFFFFFFh
0x180002ca5  jbe     short loc_180002CAE
0x180002ca7  mov     edx, 80070057h
0x180002cac  jmp     short loc_180002CFA
0x180002cae  lea     rbx, [rdx-1]
0x180002cb2  mov     [rsp+48h+var_28], 0
0x180002cbb  mov     rdx, rbx; BufferCount
0x180002cbe  lea     r9, [rsp+48h+Args]; Args
0x180002cc3  call    cs:__imp__vsnwprintf
0x180002cc9  test    eax, eax
0x180002ccb  js      short loc_180002CE3
0x180002ccd  cdqe
0x180002ccf  cmp     rax, rbx
0x180002cd2  ja      short loc_180002CE3
0x180002cd4  xor     edx, edx
0x180002cd6  cmp     rax, rbx
0x180002cd9  jnz     short loc_180002CFF
0x180002cdb  xor     eax, eax
0x180002cdd  mov     [rdi+rbx*2], ax
0x180002ce1  jmp     short loc_180002CFF
0x180002ce3  xor     eax, eax
0x180002ce5  mov     edx, 8007007Ah
0x180002cea  mov     [rdi+rbx*2], ax
0x180002cee  jmp     short loc_180002CFF
0x180002cf0  mov     edx, 80070057h
0x180002cf5  test    rax, rax
0x180002cf8  jz      short loc_180002CFF
0x180002cfa  xor     ecx, ecx
0x180002cfc  mov     [rdi], cx
0x180002cff  mov     eax, edx
0x180002d01  add     rsp, 38h
0x180002d05  pop     rdi
0x180002d06  pop     rbx
0x180002d07  retn
```
