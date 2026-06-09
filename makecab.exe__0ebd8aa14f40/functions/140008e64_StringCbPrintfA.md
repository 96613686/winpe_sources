# StringCbPrintfA

- ea: `0x140008e64`
- end: `0x140008ede`
- name: `StringCbPrintfA`
- size: `122`
- prototype: `HRESULT(STRSAFE_LPSTR pszDest, size_t cbDest, STRSAFE_LPCSTR pszFormat, ...)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x14000907c`
- `0x140009454`
- `0x140009b38`
- `0x140009c24`
- `0x14000b5c0`
- `0x14000b680`
- `0x14000b7b0`
- `0x14000bac0`
- `0x14000bb50`
- `0x14000bc70`
- `0x14000d70c`

## callees

- `0x140008e64`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x140008ea1`
- `msvcrt!_vsnprintf` at `0x140008ea1`

## pseudocode

```c
HRESULT StringCbPrintfA(STRSAFE_LPSTR pszDest, size_t cbDest, STRSAFE_LPCSTR pszFormat, ...)
{
  HRESULT result; // eax
  size_t v5; // rbx
  int v6; // eax
  __int64 v7; // rcx
  va_list ArgList; // [rsp+68h] [rbp+20h] BYREF

  va_start(ArgList, pszFormat);
  if ( !cbDest )
    return -2147024809;
  if ( cbDest <= 0x7FFFFFFF )
  {
    v5 = cbDest - 1;
    v6 = _vsnprintf(pszDest, cbDest - 1, pszFormat, ArgList);
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
0x140008e64  mov     [rsp+arg_10], r8
0x140008e69  mov     qword ptr [rsp+ArgList], r9
0x140008e6e  push    rbx
0x140008e6f  push    rdi
0x140008e70  sub     rsp, 38h
0x140008e74  mov     rdi, rcx
0x140008e77  test    rdx, rdx
0x140008e7a  jz      short loc_140008ECA
0x140008e7c  cmp     rdx, 7FFFFFFFh
0x140008e83  jbe     short loc_140008E8C
0x140008e85  mov     eax, 80070057h
0x140008e8a  jmp     short loc_140008ED4
0x140008e8c  lea     rbx, [rdx-1]
0x140008e90  mov     [rsp+48h+var_28], 0
0x140008e99  mov     rdx, rbx; BufferCount
0x140008e9c  lea     r9, [rsp+48h+ArgList]; ArgList
0x140008ea1  call    cs:__imp__vsnprintf
0x140008ea7  test    eax, eax
0x140008ea9  js      short loc_140008EBF
0x140008eab  movsxd  rcx, eax
0x140008eae  cmp     rcx, rbx
0x140008eb1  ja      short loc_140008EBF
0x140008eb3  xor     eax, eax
0x140008eb5  cmp     rcx, rbx
0x140008eb8  jnz     short loc_140008ED7
0x140008eba  mov     [rbx+rdi], al
0x140008ebd  jmp     short loc_140008ED7
0x140008ebf  mov     byte ptr [rbx+rdi], 0
0x140008ec3  mov     eax, 8007007Ah
0x140008ec8  jmp     short loc_140008ED7
0x140008eca  mov     eax, 80070057h
0x140008ecf  test    rdx, rdx
0x140008ed2  jz      short loc_140008ED7
0x140008ed4  mov     byte ptr [rcx], 0
0x140008ed7  add     rsp, 38h
0x140008edb  pop     rdi
0x140008edc  pop     rbx
0x140008edd  retn
```
