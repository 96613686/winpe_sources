# try_get_function_0

- ea: `0x180018c54`
- end: `0x180018df4`
- name: `try_get_function_0`
- size: `416`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018df4`
- `0x180018e4c`
- `0x180018ea4`
- `0x180018efc`
- `0x180018f64`
- `0x180018fdc`
- `0x1800190cc`
- `0x180019178`

## callees

- `0x180018c54`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180018cfe`
- `KERNEL32!GetLastError` at `0x180018cfe`
- `KERNEL32!FreeLibrary` at `0x180018d4a`
- `KERNEL32!FreeLibrary` at `0x180018d4a`
- `KERNEL32!GetProcAddress` at `0x180018d76`
- `KERNEL32!GetProcAddress` at `0x180018d76`
- `KERNEL32!LoadLibraryExW` at `0x180018cf0`
- `KERNEL32!LoadLibraryExW` at `0x180018d11`
- `KERNEL32!LoadLibraryExW` at `0x180018cf0`
- `KERNEL32!LoadLibraryExW` at `0x180018d11`

## pseudocode

```c
FARPROC __fastcall try_get_function_0(unsigned int a1, const CHAR *a2, unsigned int *a3, unsigned int *a4)
{
  __int64 v4; // r14
  unsigned int *v6; // rbp
  uintptr_t v8; // r10
  __int64 v9; // rdx
  FARPROC result; // rax
  __int64 v11; // rsi
  HMODULE Library; // rbx
  const WCHAR *v13; // r15

  v4 = a1;
  v6 = a3;
  v8 = _security_cookie;
  v9 = __ROR8__(qword_18002E5B0[a1] ^ _security_cookie, _security_cookie & 0x3F);
  if ( v9 == -1 )
    return 0;
  if ( v9 )
    return (FARPROC)v9;
  if ( a3 == a4 )
  {
LABEL_19:
    Library = 0;
    goto LABEL_20;
  }
  while ( 1 )
  {
    v11 = *v6;
    Library = (HMODULE)qword_18002E510[v11];
    if ( !Library )
      break;
    if ( Library != (HMODULE)-1LL )
      goto LABEL_23;
LABEL_17:
    if ( ++v6 == a4 )
    {
      v8 = _security_cookie;
      goto LABEL_19;
    }
  }
  v13 = off_180022D80[v11];
  Library = LoadLibraryExW(v13, 0, 0x800u);
  if ( !Library )
  {
    if ( GetLastError() == 87 )
      Library = LoadLibraryExW(v13, 0, 0);
    else
      Library = 0;
  }
  if ( !Library )
  {
    _InterlockedExchange64(&qword_18002E510[v11], -1);
    goto LABEL_17;
  }
  if ( _InterlockedExchange64(&qword_18002E510[v11], (__int64)Library) )
    FreeLibrary(Library);
LABEL_23:
  v8 = _security_cookie;
LABEL_20:
  if ( Library )
  {
    result = GetProcAddress(Library, a2);
    if ( result )
    {
      _InterlockedExchange64(
        &qword_18002E5B0[v4],
        _security_cookie ^ __ROR8__(result, 64 - ((unsigned __int8)_security_cookie & 0x3Fu)));
      return result;
    }
    v8 = _security_cookie;
  }
  _InterlockedExchange64(&qword_18002E5B0[v4], v8 ^ __ROR8__(-1, 64 - ((unsigned __int8)v8 & 0x3Fu)));
  return 0;
}

```

## disassembly

```asm
0x180018c54  mov     [rsp+arg_0], rbx
0x180018c59  mov     [rsp+arg_8], rbp
0x180018c5e  mov     [rsp+arg_10], rsi
0x180018c63  push    rdi
0x180018c64  push    r12
0x180018c66  push    r13
0x180018c68  push    r14
0x180018c6a  push    r15
0x180018c6c  sub     rsp, 20h
0x180018c70  mov     r14d, ecx
0x180018c73  lea     r15, cs:180000000h
0x180018c7a  mov     r12, r9
0x180018c7d  mov     rbp, r8
0x180018c80  mov     r13, rdx
0x180018c83  mov     rcx, rva qword_18002E5B0[r15+r14*8]
0x180018c8b  mov     r10, cs:__security_cookie
0x180018c92  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180018c96  mov     eax, r10d
0x180018c99  mov     rdx, r10
0x180018c9c  xor     rdx, rcx
0x180018c9f  and     eax, 3Fh
0x180018ca2  mov     cl, al
0x180018ca4  ror     rdx, cl
0x180018ca7  cmp     rdx, rdi
0x180018caa  jz      loc_180018DD5
0x180018cb0  test    rdx, rdx
0x180018cb3  jz      short loc_180018CBD
0x180018cb5  mov     rax, rdx
0x180018cb8  jmp     loc_180018DD7
0x180018cbd  cmp     r8, r9
0x180018cc0  jz      loc_180018D69
0x180018cc6  mov     esi, [rbp+0]
0x180018cc9  mov     rbx, rva qword_18002E510[r15+rsi*8]
0x180018cd1  test    rbx, rbx
0x180018cd4  jz      short loc_180018CDD
0x180018cd6  cmp     rbx, rdi
0x180018cd9  jz      short loc_180018D55
0x180018cdb  jmp     short loc_180018D50
0x180018cdd  mov     r15, ds:rva off_180022D80[r15+rsi*8]
0x180018ce5  xor     edx, edx; hFile
0x180018ce7  mov     rcx, r15; lpLibFileName
0x180018cea  mov     r8d, 800h; dwFlags
0x180018cf0  call    cs:__imp_LoadLibraryExW
0x180018cf6  mov     rbx, rax
0x180018cf9  test    rax, rax
0x180018cfc  jnz     short loc_180018D1E
0x180018cfe  call    cs:__imp_GetLastError
0x180018d04  cmp     eax, 57h ; 'W'
0x180018d07  jnz     short loc_180018D1C
0x180018d09  xor     r8d, r8d; dwFlags
0x180018d0c  xor     edx, edx; hFile
0x180018d0e  mov     rcx, r15; lpLibFileName
0x180018d11  call    cs:__imp_LoadLibraryExW
0x180018d17  mov     rbx, rax
0x180018d1a  jmp     short loc_180018D1E
0x180018d1c  xor     ebx, ebx
0x180018d1e  lea     r15, cs:180000000h
0x180018d25  test    rbx, rbx
0x180018d28  jnz     short loc_180018D37
0x180018d2a  mov     rax, rdi
0x180018d2d  xchg    rax, rva qword_18002E510[r15+rsi*8]
0x180018d35  jmp     short loc_180018D55
0x180018d37  mov     rax, rbx
0x180018d3a  xchg    rax, rva qword_18002E510[r15+rsi*8]
0x180018d42  test    rax, rax
0x180018d45  jz      short loc_180018D50
0x180018d47  mov     rcx, rbx; hLibModule
0x180018d4a  call    cs:__imp_FreeLibrary
0x180018d50  test    rbx, rbx
0x180018d53  jnz     short loc_180018DAA
0x180018d55  add     rbp, 4
0x180018d59  cmp     rbp, r12
0x180018d5c  jnz     loc_180018CC6
0x180018d62  mov     r10, cs:__security_cookie
0x180018d69  xor     ebx, ebx
0x180018d6b  test    rbx, rbx
0x180018d6e  jz      short loc_180018DBA
0x180018d70  mov     rdx, r13; lpProcName
0x180018d73  mov     rcx, rbx; hModule
0x180018d76  call    cs:__imp_GetProcAddress
0x180018d7c  test    rax, rax
0x180018d7f  jz      short loc_180018DB3
0x180018d81  mov     r8, cs:__security_cookie
0x180018d88  mov     edx, 40h ; '@'
0x180018d8d  mov     ecx, r8d
0x180018d90  and     ecx, 3Fh
0x180018d93  sub     edx, ecx
0x180018d95  mov     cl, dl
0x180018d97  mov     rdx, rax
0x180018d9a  ror     rdx, cl
0x180018d9d  xor     rdx, r8
0x180018da0  xchg    rdx, rva qword_18002E5B0[r15+r14*8]
0x180018da8  jmp     short loc_180018DD7
0x180018daa  mov     r10, cs:__security_cookie
0x180018db1  jmp     short loc_180018D6B
0x180018db3  mov     r10, cs:__security_cookie
0x180018dba  mov     eax, r10d
0x180018dbd  mov     ecx, 40h ; '@'
0x180018dc2  and     eax, 3Fh
0x180018dc5  sub     ecx, eax
0x180018dc7  ror     rdi, cl
0x180018dca  xor     rdi, r10
0x180018dcd  xchg    rdi, rva qword_18002E5B0[r15+r14*8]
0x180018dd5  xor     eax, eax
0x180018dd7  mov     rbx, [rsp+48h+arg_0]
0x180018ddc  mov     rbp, [rsp+48h+arg_8]
0x180018de1  mov     rsi, [rsp+48h+arg_10]
0x180018de6  add     rsp, 20h
0x180018dea  pop     r15
0x180018dec  pop     r14
0x180018dee  pop     r13
0x180018df0  pop     r12
0x180018df2  pop     rdi
0x180018df3  retn
```
