# StringCchPrintfW

- ea: `0x180002e08`
- end: `0x180002e93`
- name: `StringCchPrintfW`
- size: `139`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002660`

## callees

- `0x180002e08`

## import_xrefs

- `ntdll!_vsnwprintf` at `0x180002e47`
- `ntdll!_vsnwprintf` at `0x180002e47`

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
0x180002e08  mov     [rsp+arg_10], r8
0x180002e0d  mov     qword ptr [rsp+Args], r9
0x180002e12  push    rbx
0x180002e13  push    rdi
0x180002e14  sub     rsp, 38h
0x180002e18  mov     rax, rdx
0x180002e1b  mov     rdi, rcx
0x180002e1e  test    rdx, rdx
0x180002e21  jz      short loc_180002E7A
0x180002e23  cmp     rax, 7FFFFFFFh
0x180002e29  jbe     short loc_180002E32
0x180002e2b  mov     edx, 80070057h
0x180002e30  jmp     short loc_180002E84
0x180002e32  lea     rbx, [rdx-1]
0x180002e36  mov     [rsp+48h+var_28], 0
0x180002e3f  mov     rdx, rbx; BufferCount
0x180002e42  lea     r9, [rsp+48h+Args]; Args
0x180002e47  call    cs:__imp__vsnwprintf
0x180002e4e  nop     dword ptr [rax+rax+00h]
0x180002e53  test    eax, eax
0x180002e55  js      short loc_180002E6D
0x180002e57  cdqe
0x180002e59  cmp     rax, rbx
0x180002e5c  ja      short loc_180002E6D
0x180002e5e  xor     edx, edx
0x180002e60  cmp     rax, rbx
0x180002e63  jnz     short loc_180002E89
0x180002e65  xor     eax, eax
0x180002e67  mov     [rdi+rbx*2], ax
0x180002e6b  jmp     short loc_180002E89
0x180002e6d  xor     eax, eax
0x180002e6f  mov     edx, 8007007Ah
0x180002e74  mov     [rdi+rbx*2], ax
0x180002e78  jmp     short loc_180002E89
0x180002e7a  mov     edx, 80070057h
0x180002e7f  test    rax, rax
0x180002e82  jz      short loc_180002E89
0x180002e84  xor     ecx, ecx
0x180002e86  mov     [rdi], cx
0x180002e89  mov     eax, edx
0x180002e8b  add     rsp, 38h
0x180002e8f  pop     rdi
0x180002e90  pop     rbx
0x180002e91  retn
```
