# StringCchPrintfA

- ea: `0x1800044e0`
- end: `0x18000455a`
- name: `StringCchPrintfA`
- size: `122`
- prototype: `HRESULT(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszFormat, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180005bcc`
- `0x180005e5c`
- `0x180005fc4`
- `0x180006590`

## callees

- `0x1800044e0`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x18000451d`
- `msvcrt!_vsnprintf` at `0x18000451d`

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
    v6 = _vsnprintf(pszDest, cchDest - 1, pszFormat, ArgList);
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
0x1800044e0  mov     [rsp+arg_10], r8
0x1800044e5  mov     qword ptr [rsp+ArgList], r9
0x1800044ea  push    rbx
0x1800044eb  push    rdi
0x1800044ec  sub     rsp, 38h
0x1800044f0  mov     rdi, rcx
0x1800044f3  test    rdx, rdx
0x1800044f6  jz      short loc_180004546
0x1800044f8  cmp     rdx, 7FFFFFFFh
0x1800044ff  jbe     short loc_180004508
0x180004501  mov     eax, 80070057h
0x180004506  jmp     short loc_180004550
0x180004508  lea     rbx, [rdx-1]
0x18000450c  mov     [rsp+48h+var_28], 0
0x180004515  mov     rdx, rbx; BufferCount
0x180004518  lea     r9, [rsp+48h+ArgList]; ArgList
0x18000451d  call    cs:__imp__vsnprintf
0x180004523  test    eax, eax
0x180004525  js      short loc_18000453B
0x180004527  movsxd  rcx, eax
0x18000452a  cmp     rcx, rbx
0x18000452d  ja      short loc_18000453B
0x18000452f  xor     eax, eax
0x180004531  cmp     rcx, rbx
0x180004534  jnz     short loc_180004553
0x180004536  mov     [rbx+rdi], al
0x180004539  jmp     short loc_180004553
0x18000453b  mov     byte ptr [rbx+rdi], 0
0x18000453f  mov     eax, 8007007Ah
0x180004544  jmp     short loc_180004553
0x180004546  mov     eax, 80070057h
0x18000454b  test    rdx, rdx
0x18000454e  jz      short loc_180004553
0x180004550  mov     byte ptr [rcx], 0
0x180004553  add     rsp, 38h
0x180004557  pop     rdi
0x180004558  pop     rbx
0x180004559  retn
```
