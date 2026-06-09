# try_get_function_0

- ea: `0x1800fdc98`
- end: `0x1800fde38`
- name: `try_get_function_0`
- size: `416`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800fde38`
- `0x1800fde90`
- `0x1800fdee8`
- `0x1800fdf40`
- `0x1800fdfa8`
- `0x1800fe020`
- `0x1800fe110`
- `0x1800fe1b8`

## callees

- `0x1800fdc98`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800fdd42`
- `KERNEL32!GetLastError` at `0x1800fdd42`
- `KERNEL32!GetProcAddress` at `0x1800fddba`
- `KERNEL32!GetProcAddress` at `0x1800fddba`
- `KERNEL32!FreeLibrary` at `0x1800fdd8e`
- `KERNEL32!FreeLibrary` at `0x1800fdd8e`
- `KERNEL32!LoadLibraryExW` at `0x1800fdd34`
- `KERNEL32!LoadLibraryExW` at `0x1800fdd55`
- `KERNEL32!LoadLibraryExW` at `0x1800fdd34`
- `KERNEL32!LoadLibraryExW` at `0x1800fdd55`

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
  v9 = __ROR8__(qword_180163110[a1] ^ _security_cookie, _security_cookie & 0x3F);
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
    Library = (HMODULE)qword_180163070[v11];
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
  v13 = off_1801208E0[v11];
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
    _InterlockedExchange64(&qword_180163070[v11], -1);
    goto LABEL_17;
  }
  if ( _InterlockedExchange64(&qword_180163070[v11], (__int64)Library) )
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
        &qword_180163110[v4],
        _security_cookie ^ __ROR8__(result, 64 - ((unsigned __int8)_security_cookie & 0x3Fu)));
      return result;
    }
    v8 = _security_cookie;
  }
  _InterlockedExchange64(&qword_180163110[v4], v8 ^ __ROR8__(-1, 64 - ((unsigned __int8)v8 & 0x3Fu)));
  return 0;
}

```

## disassembly

```asm
0x1800fdc98  mov     [rsp+arg_0], rbx
0x1800fdc9d  mov     [rsp+arg_8], rbp
0x1800fdca2  mov     [rsp+arg_10], rsi
0x1800fdca7  push    rdi
0x1800fdca8  push    r12
0x1800fdcaa  push    r13
0x1800fdcac  push    r14
0x1800fdcae  push    r15
0x1800fdcb0  sub     rsp, 20h
0x1800fdcb4  mov     r14d, ecx
0x1800fdcb7  lea     r15, __ImageBase
0x1800fdcbe  mov     r12, r9
0x1800fdcc1  mov     rbp, r8
0x1800fdcc4  mov     r13, rdx
0x1800fdcc7  mov     rcx, rva qword_180163110[r15+r14*8]
0x1800fdccf  mov     r10, cs:__security_cookie
0x1800fdcd6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800fdcda  mov     eax, r10d
0x1800fdcdd  mov     rdx, r10
0x1800fdce0  xor     rdx, rcx
0x1800fdce3  and     eax, 3Fh
0x1800fdce6  mov     cl, al
0x1800fdce8  ror     rdx, cl
0x1800fdceb  cmp     rdx, rdi
0x1800fdcee  jz      loc_1800FDE19
0x1800fdcf4  test    rdx, rdx
0x1800fdcf7  jz      short loc_1800FDD01
0x1800fdcf9  mov     rax, rdx
0x1800fdcfc  jmp     loc_1800FDE1B
0x1800fdd01  cmp     r8, r9
0x1800fdd04  jz      loc_1800FDDAD
0x1800fdd0a  mov     esi, [rbp+0]
0x1800fdd0d  mov     rbx, rva qword_180163070[r15+rsi*8]
0x1800fdd15  test    rbx, rbx
0x1800fdd18  jz      short loc_1800FDD21
0x1800fdd1a  cmp     rbx, rdi
0x1800fdd1d  jz      short loc_1800FDD99
0x1800fdd1f  jmp     short loc_1800FDD94
0x1800fdd21  mov     r15, ds:rva off_1801208E0[r15+rsi*8]
0x1800fdd29  xor     edx, edx; hFile
0x1800fdd2b  mov     rcx, r15; lpLibFileName
0x1800fdd2e  mov     r8d, 800h; dwFlags
0x1800fdd34  call    cs:__imp_LoadLibraryExW
0x1800fdd3a  mov     rbx, rax
0x1800fdd3d  test    rax, rax
0x1800fdd40  jnz     short loc_1800FDD62
0x1800fdd42  call    cs:__imp_GetLastError
0x1800fdd48  cmp     eax, 57h ; 'W'
0x1800fdd4b  jnz     short loc_1800FDD60
0x1800fdd4d  xor     r8d, r8d; dwFlags
0x1800fdd50  xor     edx, edx; hFile
0x1800fdd52  mov     rcx, r15; lpLibFileName
0x1800fdd55  call    cs:__imp_LoadLibraryExW
0x1800fdd5b  mov     rbx, rax
0x1800fdd5e  jmp     short loc_1800FDD62
0x1800fdd60  xor     ebx, ebx
0x1800fdd62  lea     r15, __ImageBase
0x1800fdd69  test    rbx, rbx
0x1800fdd6c  jnz     short loc_1800FDD7B
0x1800fdd6e  mov     rax, rdi
0x1800fdd71  xchg    rax, rva qword_180163070[r15+rsi*8]
0x1800fdd79  jmp     short loc_1800FDD99
0x1800fdd7b  mov     rax, rbx
0x1800fdd7e  xchg    rax, rva qword_180163070[r15+rsi*8]
0x1800fdd86  test    rax, rax
0x1800fdd89  jz      short loc_1800FDD94
0x1800fdd8b  mov     rcx, rbx; hLibModule
0x1800fdd8e  call    cs:__imp_FreeLibrary
0x1800fdd94  test    rbx, rbx
0x1800fdd97  jnz     short loc_1800FDDEE
0x1800fdd99  add     rbp, 4
0x1800fdd9d  cmp     rbp, r12
0x1800fdda0  jnz     loc_1800FDD0A
0x1800fdda6  mov     r10, cs:__security_cookie
0x1800fddad  xor     ebx, ebx
0x1800fddaf  test    rbx, rbx
0x1800fddb2  jz      short loc_1800FDDFE
0x1800fddb4  mov     rdx, r13; lpProcName
0x1800fddb7  mov     rcx, rbx; hModule
0x1800fddba  call    cs:__imp_GetProcAddress
0x1800fddc0  test    rax, rax
0x1800fddc3  jz      short loc_1800FDDF7
0x1800fddc5  mov     r8, cs:__security_cookie
0x1800fddcc  mov     edx, 40h ; '@'
0x1800fddd1  mov     ecx, r8d
0x1800fddd4  and     ecx, 3Fh
0x1800fddd7  sub     edx, ecx
0x1800fddd9  mov     cl, dl
0x1800fdddb  mov     rdx, rax
0x1800fddde  ror     rdx, cl
0x1800fdde1  xor     rdx, r8
0x1800fdde4  xchg    rdx, rva qword_180163110[r15+r14*8]
0x1800fddec  jmp     short loc_1800FDE1B
0x1800fddee  mov     r10, cs:__security_cookie
0x1800fddf5  jmp     short loc_1800FDDAF
0x1800fddf7  mov     r10, cs:__security_cookie
0x1800fddfe  mov     eax, r10d
0x1800fde01  mov     ecx, 40h ; '@'
0x1800fde06  and     eax, 3Fh
0x1800fde09  sub     ecx, eax
0x1800fde0b  ror     rdi, cl
0x1800fde0e  xor     rdi, r10
0x1800fde11  xchg    rdi, rva qword_180163110[r15+r14*8]
0x1800fde19  xor     eax, eax
0x1800fde1b  mov     rbx, [rsp+48h+arg_0]
0x1800fde20  mov     rbp, [rsp+48h+arg_8]
0x1800fde25  mov     rsi, [rsp+48h+arg_10]
0x1800fde2a  add     rsp, 20h
0x1800fde2e  pop     r15
0x1800fde30  pop     r14
0x1800fde32  pop     r13
0x1800fde34  pop     r12
0x1800fde36  pop     rdi
0x1800fde37  retn
```
