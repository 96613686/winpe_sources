# try_get_function

- ea: `0x180112a3c`
- end: `0x180112b8b`
- name: `try_get_function`
- size: `335`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180112b8c`
- `0x180112bd4`
- `0x180112c1c`
- `0x180112c64`
- `0x180112cb8`

## callees

- `0x180112a3c`
- `0x18011e980`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180112acf`
- `KERNEL32!GetLastError` at `0x180112acf`
- `KERNEL32!LoadLibraryExW` at `0x180112ac1`
- `KERNEL32!LoadLibraryExW` at `0x180112af9`
- `KERNEL32!LoadLibraryExW` at `0x180112ac1`
- `KERNEL32!LoadLibraryExW` at `0x180112af9`
- `KERNEL32!FreeLibrary` at `0x180112b67`
- `KERNEL32!FreeLibrary` at `0x180112b67`
- `KERNEL32!GetProcAddress` at `0x180112b73`
- `KERNEL32!GetProcAddress` at `0x180112b73`

## pseudocode

```c
FARPROC __fastcall try_get_function(unsigned int a1, const CHAR *a2, unsigned int *a3, unsigned int *a4)
{
  __int64 v4; // rdi
  unsigned int *v6; // rbp
  FARPROC result; // rax
  __int64 v9; // rsi
  HMODULE Library; // rbx
  const WCHAR *v11; // r15

  v4 = a1;
  v6 = a3;
  result = (FARPROC)qword_1803101F0[a1];
  if ( result == (FARPROC)-1LL )
    return 0;
  if ( !result )
  {
    if ( a3 == a4 )
      goto LABEL_13;
    while ( 1 )
    {
      v9 = *v6;
      Library = (HMODULE)qword_1803101D8[v9];
      if ( Library )
      {
        if ( Library != (HMODULE)-1LL )
          goto LABEL_18;
      }
      else
      {
        v11 = off_180272828[v9];
        Library = LoadLibraryExW(v11, 0, 0x800u);
        if ( Library
          || GetLastError() == 87 && wcsncmp(v11, L"api-ms-", 7u) && (Library = LoadLibraryExW(v11, 0, 0)) != 0 )
        {
          if ( _InterlockedExchange64(&qword_1803101D8[v9], (__int64)Library) )
            FreeLibrary(Library);
LABEL_18:
          result = GetProcAddress(Library, a2);
          if ( result )
          {
            _InterlockedExchange64(&qword_1803101F0[v4], (__int64)result);
            return result;
          }
LABEL_13:
          _InterlockedExchange64(&qword_1803101F0[v4], -1);
          return 0;
        }
        _InterlockedExchange64(&qword_1803101D8[v9], -1);
      }
      if ( ++v6 == a4 )
        goto LABEL_13;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180112a3c  mov     [rsp+arg_0], rbx
0x180112a41  mov     [rsp+arg_8], rbp
0x180112a46  mov     [rsp+arg_10], rsi
0x180112a4b  push    rdi
0x180112a4c  push    r12
0x180112a4e  push    r13
0x180112a50  push    r14
0x180112a52  push    r15
0x180112a54  sub     rsp, 20h
0x180112a58  mov     edi, ecx
0x180112a5a  lea     r15, __ImageBase
0x180112a61  or      r14, 0FFFFFFFFFFFFFFFFh
0x180112a65  mov     r12, r9
0x180112a68  mov     rbp, r8
0x180112a6b  mov     r13, rdx
0x180112a6e  mov     rax, rva qword_1803101F0[r15+rdi*8]
0x180112a76  nop
0x180112a77  cmp     rax, r14
0x180112a7a  jz      loc_180112B2E
0x180112a80  test    rax, rax
0x180112a83  jnz     loc_180112B30
0x180112a89  cmp     r8, r9
0x180112a8c  jz      loc_180112B26
0x180112a92  mov     esi, [rbp+0]
0x180112a95  mov     rbx, rva qword_1803101D8[r15+rsi*8]
0x180112a9d  nop
0x180112a9e  test    rbx, rbx
0x180112aa1  jz      short loc_180112AAE
0x180112aa3  cmp     rbx, r14
0x180112aa6  jnz     loc_180112B6D
0x180112aac  jmp     short loc_180112B19
0x180112aae  mov     r15, ds:rva off_180272828[r15+rsi*8]; "api-ms-win-core-fibers-l1-1-1" ...
0x180112ab6  xor     edx, edx; hFile
0x180112ab8  mov     rcx, r15; lpLibFileName
0x180112abb  mov     r8d, 800h; dwFlags
0x180112ac1  call    cs:__imp_LoadLibraryExW
0x180112ac7  mov     rbx, rax
0x180112aca  test    rax, rax
0x180112acd  jnz     short loc_180112B4D
0x180112acf  call    cs:__imp_GetLastError
0x180112ad5  cmp     eax, 57h ; 'W'
0x180112ad8  jnz     short loc_180112B07
0x180112ada  lea     r8d, [rbx+7]; MaxCount
0x180112ade  mov     rcx, r15; String1
0x180112ae1  lea     rdx, aApiMs; "api-ms-"
0x180112ae8  call    wcsncmp
0x180112aed  test    eax, eax
0x180112aef  jz      short loc_180112B07
0x180112af1  xor     r8d, r8d; dwFlags
0x180112af4  xor     edx, edx; hFile
0x180112af6  mov     rcx, r15; lpLibFileName
0x180112af9  call    cs:__imp_LoadLibraryExW
0x180112aff  mov     rbx, rax
0x180112b02  test    rax, rax
0x180112b05  jnz     short loc_180112B4D
0x180112b07  mov     rax, r14
0x180112b0a  lea     r15, __ImageBase
0x180112b11  xchg    rax, rva qword_1803101D8[r15+rsi*8]
0x180112b19  add     rbp, 4
0x180112b1d  cmp     rbp, r12
0x180112b20  jnz     loc_180112A92
0x180112b26  xchg    r14, rva qword_1803101F0[r15+rdi*8]
0x180112b2e  xor     eax, eax
0x180112b30  mov     rbx, [rsp+48h+arg_0]
0x180112b35  mov     rbp, [rsp+48h+arg_8]
0x180112b3a  mov     rsi, [rsp+48h+arg_10]
0x180112b3f  add     rsp, 20h
0x180112b43  pop     r15
0x180112b45  pop     r14
0x180112b47  pop     r13
0x180112b49  pop     r12
0x180112b4b  pop     rdi
0x180112b4c  retn
0x180112b4d  mov     rax, rbx
0x180112b50  lea     r15, __ImageBase
0x180112b57  xchg    rax, rva qword_1803101D8[r15+rsi*8]
0x180112b5f  test    rax, rax
0x180112b62  jz      short loc_180112B6D
0x180112b64  mov     rcx, rbx; hLibModule
0x180112b67  call    cs:__imp_FreeLibrary
0x180112b6d  mov     rdx, r13; lpProcName
0x180112b70  mov     rcx, rbx; hModule
0x180112b73  call    cs:__imp_GetProcAddress
0x180112b79  test    rax, rax
0x180112b7c  jz      short loc_180112B26
0x180112b7e  mov     rcx, rax
0x180112b81  xchg    rcx, rva qword_1803101F0[r15+rdi*8]
0x180112b89  jmp     short loc_180112B30
```
