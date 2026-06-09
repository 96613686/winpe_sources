# try_get_function

- ea: `0x18033e8a4`
- end: `0x18033e9f3`
- name: `try_get_function`
- size: `335`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18033e9f4`
- `0x18033ea3c`
- `0x18033ea84`
- `0x18033eacc`
- `0x18033eb20`

## callees

- `0x18033e8a4`
- `0x180354790`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18033e929`
- `KERNEL32!LoadLibraryExW` at `0x18033e961`
- `KERNEL32!LoadLibraryExW` at `0x18033e929`
- `KERNEL32!LoadLibraryExW` at `0x18033e961`
- `KERNEL32!GetLastError` at `0x18033e937`
- `KERNEL32!GetLastError` at `0x18033e937`
- `KERNEL32!FreeLibrary` at `0x18033e9cf`
- `KERNEL32!FreeLibrary` at `0x18033e9cf`
- `KERNEL32!GetProcAddress` at `0x18033e9db`
- `KERNEL32!GetProcAddress` at `0x18033e9db`

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
  result = (FARPROC)qword_18053F8D0[a1];
  if ( result == (FARPROC)-1LL )
    return 0;
  if ( !result )
  {
    if ( a3 == a4 )
      goto LABEL_13;
    while ( 1 )
    {
      v9 = *v6;
      Library = (HMODULE)qword_18053F8B8[v9];
      if ( Library )
      {
        if ( Library != (HMODULE)-1LL )
          goto LABEL_18;
      }
      else
      {
        v11 = off_18043B310[v9];
        Library = LoadLibraryExW(v11, 0, 0x800u);
        if ( Library
          || GetLastError() == 87 && wcsncmp(v11, L"api-ms-", 7u) && (Library = LoadLibraryExW(v11, 0, 0)) != 0 )
        {
          if ( _InterlockedExchange64(&qword_18053F8B8[v9], (__int64)Library) )
            FreeLibrary(Library);
LABEL_18:
          result = GetProcAddress(Library, a2);
          if ( result )
          {
            _InterlockedExchange64(&qword_18053F8D0[v4], (__int64)result);
            return result;
          }
LABEL_13:
          _InterlockedExchange64(&qword_18053F8D0[v4], -1);
          return 0;
        }
        _InterlockedExchange64(&qword_18053F8B8[v9], -1);
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
0x18033e8a4  mov     [rsp+arg_0], rbx
0x18033e8a9  mov     [rsp+arg_8], rbp
0x18033e8ae  mov     [rsp+arg_10], rsi
0x18033e8b3  push    rdi
0x18033e8b4  push    r12
0x18033e8b6  push    r13
0x18033e8b8  push    r14
0x18033e8ba  push    r15
0x18033e8bc  sub     rsp, 20h
0x18033e8c0  mov     edi, ecx
0x18033e8c2  lea     r15, __ImageBase
0x18033e8c9  or      r14, 0FFFFFFFFFFFFFFFFh
0x18033e8cd  mov     r12, r9
0x18033e8d0  mov     rbp, r8
0x18033e8d3  mov     r13, rdx
0x18033e8d6  mov     rax, rva qword_18053F8D0[r15+rdi*8]
0x18033e8de  nop
0x18033e8df  cmp     rax, r14
0x18033e8e2  jz      loc_18033E996
0x18033e8e8  test    rax, rax
0x18033e8eb  jnz     loc_18033E998
0x18033e8f1  cmp     r8, r9
0x18033e8f4  jz      loc_18033E98E
0x18033e8fa  mov     esi, [rbp+0]
0x18033e8fd  mov     rbx, rva qword_18053F8B8[r15+rsi*8]
0x18033e905  nop
0x18033e906  test    rbx, rbx
0x18033e909  jz      short loc_18033E916
0x18033e90b  cmp     rbx, r14
0x18033e90e  jnz     loc_18033E9D5
0x18033e914  jmp     short loc_18033E981
0x18033e916  mov     r15, ds:rva off_18043B310[r15+rsi*8]; "api-ms-win-core-fibers-l1-1-1" ...
0x18033e91e  xor     edx, edx; hFile
0x18033e920  mov     rcx, r15; lpLibFileName
0x18033e923  mov     r8d, 800h; dwFlags
0x18033e929  call    cs:__imp_LoadLibraryExW
0x18033e92f  mov     rbx, rax
0x18033e932  test    rax, rax
0x18033e935  jnz     short loc_18033E9B5
0x18033e937  call    cs:__imp_GetLastError
0x18033e93d  cmp     eax, 57h ; 'W'
0x18033e940  jnz     short loc_18033E96F
0x18033e942  lea     r8d, [rbx+7]; MaxCount
0x18033e946  mov     rcx, r15; String1
0x18033e949  lea     rdx, aApiMs; "api-ms-"
0x18033e950  call    wcsncmp
0x18033e955  test    eax, eax
0x18033e957  jz      short loc_18033E96F
0x18033e959  xor     r8d, r8d; dwFlags
0x18033e95c  xor     edx, edx; hFile
0x18033e95e  mov     rcx, r15; lpLibFileName
0x18033e961  call    cs:__imp_LoadLibraryExW
0x18033e967  mov     rbx, rax
0x18033e96a  test    rax, rax
0x18033e96d  jnz     short loc_18033E9B5
0x18033e96f  mov     rax, r14
0x18033e972  lea     r15, __ImageBase
0x18033e979  xchg    rax, rva qword_18053F8B8[r15+rsi*8]
0x18033e981  add     rbp, 4
0x18033e985  cmp     rbp, r12
0x18033e988  jnz     loc_18033E8FA
0x18033e98e  xchg    r14, rva qword_18053F8D0[r15+rdi*8]
0x18033e996  xor     eax, eax
0x18033e998  mov     rbx, [rsp+48h+arg_0]
0x18033e99d  mov     rbp, [rsp+48h+arg_8]
0x18033e9a2  mov     rsi, [rsp+48h+arg_10]
0x18033e9a7  add     rsp, 20h
0x18033e9ab  pop     r15
0x18033e9ad  pop     r14
0x18033e9af  pop     r13
0x18033e9b1  pop     r12
0x18033e9b3  pop     rdi
0x18033e9b4  retn
0x18033e9b5  mov     rax, rbx
0x18033e9b8  lea     r15, __ImageBase
0x18033e9bf  xchg    rax, rva qword_18053F8B8[r15+rsi*8]
0x18033e9c7  test    rax, rax
0x18033e9ca  jz      short loc_18033E9D5
0x18033e9cc  mov     rcx, rbx; hLibModule
0x18033e9cf  call    cs:__imp_FreeLibrary
0x18033e9d5  mov     rdx, r13; lpProcName
0x18033e9d8  mov     rcx, rbx; hModule
0x18033e9db  call    cs:__imp_GetProcAddress
0x18033e9e1  test    rax, rax
0x18033e9e4  jz      short loc_18033E98E
0x18033e9e6  mov     rcx, rax
0x18033e9e9  xchg    rcx, rva qword_18053F8D0[r15+rdi*8]
0x18033e9f1  jmp     short loc_18033E998
```
