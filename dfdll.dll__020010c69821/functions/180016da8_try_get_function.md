# try_get_function

- ea: `0x180016da8`
- end: `0x180016ef6`
- name: `try_get_function`
- size: `334`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180016ef8`
- `0x180016f40`
- `0x180016f88`
- `0x180016fd0`
- `0x180017024`

## callees

- `0x180016da8`
- `0x1800185f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180016e3b`
- `KERNEL32!GetLastError` at `0x180016e3b`
- `KERNEL32!FreeLibrary` at `0x180016eab`
- `KERNEL32!FreeLibrary` at `0x180016eab`
- `KERNEL32!GetProcAddress` at `0x180016eb7`
- `KERNEL32!GetProcAddress` at `0x180016eb7`
- `KERNEL32!LoadLibraryExW` at `0x180016e2d`
- `KERNEL32!LoadLibraryExW` at `0x180016e65`
- `KERNEL32!LoadLibraryExW` at `0x180016e2d`
- `KERNEL32!LoadLibraryExW` at `0x180016e65`

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
  result = (FARPROC)qword_18002E158[a1];
  if ( result != (FARPROC)-1LL )
  {
    if ( result )
      return result;
    for ( i = a3 == a4; !i; i = v6 == a4 )
    {
      v10 = *v6;
      Library = (HMODULE)qword_18002E140[v10];
      if ( Library )
      {
        if ( Library != (HMODULE)-1LL )
          goto LABEL_16;
      }
      else
      {
        v12 = off_180022A48[v10];
        Library = LoadLibraryExW(v12, 0, 0x800u);
        if ( Library
          || GetLastError() == 87 && wcsncmp(v12, L"api-ms-", 7u) && (Library = LoadLibraryExW(v12, 0, 0)) != 0 )
        {
          if ( _InterlockedExchange64(&qword_18002E140[v10], (__int64)Library) )
            FreeLibrary(Library);
LABEL_16:
          result = GetProcAddress(Library, a2);
          if ( result )
          {
            _InterlockedExchange64(&qword_18002E158[v4], (__int64)result);
            return result;
          }
          break;
        }
        _InterlockedExchange64(&qword_18002E140[v10], -1);
      }
      ++v6;
    }
    _InterlockedExchange64(&qword_18002E158[v4], -1);
  }
  return 0;
}

```

## disassembly

```asm
0x180016da8  mov     [rsp+arg_0], rbx
0x180016dad  mov     [rsp+arg_8], rbp
0x180016db2  mov     [rsp+arg_10], rsi
0x180016db7  push    rdi
0x180016db8  push    r12
0x180016dba  push    r13
0x180016dbc  push    r14
0x180016dbe  push    r15
0x180016dc0  sub     rsp, 20h
0x180016dc4  mov     edi, ecx
0x180016dc6  lea     r15, cs:180000000h
0x180016dcd  or      r14, 0FFFFFFFFFFFFFFFFh
0x180016dd1  mov     r12, r9
0x180016dd4  mov     rbp, r8
0x180016dd7  mov     r13, rdx
0x180016dda  mov     rax, rva qword_18002E158[r15+rdi*8]
0x180016de2  nop
0x180016de3  cmp     rax, r14
0x180016de6  jz      loc_180016ED7
0x180016dec  test    rax, rax
0x180016def  jnz     loc_180016ED9
0x180016df5  cmp     r8, r9
0x180016df8  jz      loc_180016ECF
0x180016dfe  mov     esi, [rbp+0]
0x180016e01  mov     rbx, rva qword_18002E140[r15+rsi*8]
0x180016e09  nop
0x180016e0a  test    rbx, rbx
0x180016e0d  jz      short loc_180016E1A
0x180016e0f  cmp     rbx, r14
0x180016e12  jnz     loc_180016EB1
0x180016e18  jmp     short loc_180016E85
0x180016e1a  mov     r15, ds:rva off_180022A48[r15+rsi*8]
0x180016e22  xor     edx, edx; hFile
0x180016e24  mov     rcx, r15; lpLibFileName
0x180016e27  mov     r8d, 800h; dwFlags
0x180016e2d  call    cs:__imp_LoadLibraryExW
0x180016e33  mov     rbx, rax
0x180016e36  test    rax, rax
0x180016e39  jnz     short loc_180016E91
0x180016e3b  call    cs:__imp_GetLastError
0x180016e41  cmp     eax, 57h ; 'W'
0x180016e44  jnz     short loc_180016E73
0x180016e46  lea     r8d, [rbx+7]; MaxCount
0x180016e4a  mov     rcx, r15; String1
0x180016e4d  lea     rdx, aApiMs
0x180016e54  call    wcsncmp
0x180016e59  test    eax, eax
0x180016e5b  jz      short loc_180016E73
0x180016e5d  xor     r8d, r8d; dwFlags
0x180016e60  xor     edx, edx; hFile
0x180016e62  mov     rcx, r15; lpLibFileName
0x180016e65  call    cs:__imp_LoadLibraryExW
0x180016e6b  mov     rbx, rax
0x180016e6e  test    rax, rax
0x180016e71  jnz     short loc_180016E91
0x180016e73  mov     rax, r14
0x180016e76  lea     r15, cs:180000000h
0x180016e7d  xchg    rax, rva qword_18002E140[r15+rsi*8]
0x180016e85  add     rbp, 4
0x180016e89  cmp     rbp, r12
0x180016e8c  jmp     loc_180016DF8
0x180016e91  mov     rax, rbx
0x180016e94  lea     r15, cs:180000000h
0x180016e9b  xchg    rax, rva qword_18002E140[r15+rsi*8]
0x180016ea3  test    rax, rax
0x180016ea6  jz      short loc_180016EB1
0x180016ea8  mov     rcx, rbx; hLibModule
0x180016eab  call    cs:__imp_FreeLibrary
0x180016eb1  mov     rdx, r13; lpProcName
0x180016eb4  mov     rcx, rbx; hModule
0x180016eb7  call    cs:__imp_GetProcAddress
0x180016ebd  test    rax, rax
0x180016ec0  jz      short loc_180016ECF
0x180016ec2  mov     rcx, rax
0x180016ec5  xchg    rcx, rva qword_18002E158[r15+rdi*8]
0x180016ecd  jmp     short loc_180016ED9
0x180016ecf  xchg    r14, rva qword_18002E158[r15+rdi*8]
0x180016ed7  xor     eax, eax
0x180016ed9  mov     rbx, [rsp+48h+arg_0]
0x180016ede  mov     rbp, [rsp+48h+arg_8]
0x180016ee3  mov     rsi, [rsp+48h+arg_10]
0x180016ee8  add     rsp, 20h
0x180016eec  pop     r15
0x180016eee  pop     r14
0x180016ef0  pop     r13
0x180016ef2  pop     r12
0x180016ef4  pop     rdi
0x180016ef5  retn
```
