# try_get_function

- ea: `0x1800f5348`
- end: `0x1800f5496`
- name: `try_get_function`
- size: `334`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800f5498`
- `0x1800f54e0`
- `0x1800f5528`
- `0x1800f5570`
- `0x1800f55c4`

## callees

- `0x1800f5348`
- `0x1800f9a9c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800f53db`
- `KERNEL32!GetLastError` at `0x1800f53db`
- `KERNEL32!GetProcAddress` at `0x1800f5457`
- `KERNEL32!GetProcAddress` at `0x1800f5457`
- `KERNEL32!FreeLibrary` at `0x1800f544b`
- `KERNEL32!FreeLibrary` at `0x1800f544b`
- `KERNEL32!LoadLibraryExW` at `0x1800f53cd`
- `KERNEL32!LoadLibraryExW` at `0x1800f5405`
- `KERNEL32!LoadLibraryExW` at `0x1800f53cd`
- `KERNEL32!LoadLibraryExW` at `0x1800f5405`

## pseudocode

```c
FARPROC __fastcall try_get_function(unsigned int a1, const CHAR *a2, unsigned int *a3, unsigned int *a4)
{
  __int64 v4; // rdi
  unsigned int *v6; // rbp
  FARPROC result; // rax
  bool i; // zf
  __int64 v10; // rsi
  HMODULE Library; // rbx
  const WCHAR *v12; // r15

  v4 = a1;
  v6 = a3;
  result = (FARPROC)qword_180162A88[a1];
  if ( result != (FARPROC)-1LL )
  {
    if ( result )
      return result;
    for ( i = a3 == a4; !i; i = v6 == a4 )
    {
      v10 = *v6;
      Library = (HMODULE)qword_180162A70[v10];
      if ( Library )
      {
        if ( Library != (HMODULE)-1LL )
          goto LABEL_16;
      }
      else
      {
        v12 = off_18011F480[v10];
        Library = LoadLibraryExW(v12, 0, 0x800u);
        if ( Library
          || GetLastError() == 87 && wcsncmp(v12, L"api-ms-", 7u) && (Library = LoadLibraryExW(v12, 0, 0)) != 0 )
        {
          if ( _InterlockedExchange64(&qword_180162A70[v10], (__int64)Library) )
            FreeLibrary(Library);
LABEL_16:
          result = GetProcAddress(Library, a2);
          if ( result )
          {
            _InterlockedExchange64(&qword_180162A88[v4], (__int64)result);
            return result;
          }
          break;
        }
        _InterlockedExchange64(&qword_180162A70[v10], -1);
      }
      ++v6;
    }
    _InterlockedExchange64(&qword_180162A88[v4], -1);
  }
  return 0;
}

```

## disassembly

```asm
0x1800f5348  mov     [rsp+arg_0], rbx
0x1800f534d  mov     [rsp+arg_8], rbp
0x1800f5352  mov     [rsp+arg_10], rsi
0x1800f5357  push    rdi
0x1800f5358  push    r12
0x1800f535a  push    r13
0x1800f535c  push    r14
0x1800f535e  push    r15
0x1800f5360  sub     rsp, 20h
0x1800f5364  mov     edi, ecx
0x1800f5366  lea     r15, __ImageBase
0x1800f536d  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800f5371  mov     r12, r9
0x1800f5374  mov     rbp, r8
0x1800f5377  mov     r13, rdx
0x1800f537a  mov     rax, rva qword_180162A88[r15+rdi*8]
0x1800f5382  nop
0x1800f5383  cmp     rax, r14
0x1800f5386  jz      loc_1800F5477
0x1800f538c  test    rax, rax
0x1800f538f  jnz     loc_1800F5479
0x1800f5395  cmp     r8, r9
0x1800f5398  jz      loc_1800F546F
0x1800f539e  mov     esi, [rbp+0]
0x1800f53a1  mov     rbx, rva qword_180162A70[r15+rsi*8]
0x1800f53a9  nop
0x1800f53aa  test    rbx, rbx
0x1800f53ad  jz      short loc_1800F53BA
0x1800f53af  cmp     rbx, r14
0x1800f53b2  jnz     loc_1800F5451
0x1800f53b8  jmp     short loc_1800F5425
0x1800f53ba  mov     r15, ds:rva off_18011F480[r15+rsi*8]
0x1800f53c2  xor     edx, edx; hFile
0x1800f53c4  mov     rcx, r15; lpLibFileName
0x1800f53c7  mov     r8d, 800h; dwFlags
0x1800f53cd  call    cs:__imp_LoadLibraryExW
0x1800f53d3  mov     rbx, rax
0x1800f53d6  test    rax, rax
0x1800f53d9  jnz     short loc_1800F5431
0x1800f53db  call    cs:__imp_GetLastError
0x1800f53e1  cmp     eax, 57h ; 'W'
0x1800f53e4  jnz     short loc_1800F5413
0x1800f53e6  lea     r8d, [rbx+7]; MaxCount
0x1800f53ea  mov     rcx, r15; String1
0x1800f53ed  lea     rdx, aApiMs
0x1800f53f4  call    wcsncmp
0x1800f53f9  test    eax, eax
0x1800f53fb  jz      short loc_1800F5413
0x1800f53fd  xor     r8d, r8d; dwFlags
0x1800f5400  xor     edx, edx; hFile
0x1800f5402  mov     rcx, r15; lpLibFileName
0x1800f5405  call    cs:__imp_LoadLibraryExW
0x1800f540b  mov     rbx, rax
0x1800f540e  test    rax, rax
0x1800f5411  jnz     short loc_1800F5431
0x1800f5413  mov     rax, r14
0x1800f5416  lea     r15, __ImageBase
0x1800f541d  xchg    rax, rva qword_180162A70[r15+rsi*8]
0x1800f5425  add     rbp, 4
0x1800f5429  cmp     rbp, r12
0x1800f542c  jmp     loc_1800F5398
0x1800f5431  mov     rax, rbx
0x1800f5434  lea     r15, __ImageBase
0x1800f543b  xchg    rax, rva qword_180162A70[r15+rsi*8]
0x1800f5443  test    rax, rax
0x1800f5446  jz      short loc_1800F5451
0x1800f5448  mov     rcx, rbx; hLibModule
0x1800f544b  call    cs:__imp_FreeLibrary
0x1800f5451  mov     rdx, r13; lpProcName
0x1800f5454  mov     rcx, rbx; hModule
0x1800f5457  call    cs:__imp_GetProcAddress
0x1800f545d  test    rax, rax
0x1800f5460  jz      short loc_1800F546F
0x1800f5462  mov     rcx, rax
0x1800f5465  xchg    rcx, rva qword_180162A88[r15+rdi*8]
0x1800f546d  jmp     short loc_1800F5479
0x1800f546f  xchg    r14, rva qword_180162A88[r15+rdi*8]
0x1800f5477  xor     eax, eax
0x1800f5479  mov     rbx, [rsp+48h+arg_0]
0x1800f547e  mov     rbp, [rsp+48h+arg_8]
0x1800f5483  mov     rsi, [rsp+48h+arg_10]
0x1800f5488  add     rsp, 20h
0x1800f548c  pop     r15
0x1800f548e  pop     r14
0x1800f5490  pop     r13
0x1800f5492  pop     r12
0x1800f5494  pop     rdi
0x1800f5495  retn
```
