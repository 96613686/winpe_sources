# try_get_function_slow

- ea: `0x180009480`
- end: `0x180009623`
- name: `try_get_function_slow`
- size: `419`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000962c`
- `0x180009690`
- `0x180009740`
- `0x180009824`
- `0x1800098cc`

## callees

- `0x180007034`
- `0x180009400`
- `0x180009460`
- `0x180009480`
- `0x18000ab50`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000960f`
- `KERNEL32!GetProcAddress` at `0x18000960f`
- `KERNEL32!FreeLibrary` at `0x180009603`
- `KERNEL32!FreeLibrary` at `0x180009603`
- `KERNEL32!GetLastError` at `0x1800094f4`
- `KERNEL32!GetLastError` at `0x1800094f4`
- `KERNEL32!VirtualProtect` at `0x18000959b`
- `KERNEL32!VirtualProtect` at `0x1800095cb`
- `KERNEL32!VirtualProtect` at `0x18000959b`
- `KERNEL32!VirtualProtect` at `0x1800095cb`
- `KERNEL32!LoadLibraryExW` at `0x1800094e2`
- `KERNEL32!LoadLibraryExW` at `0x180009536`
- `KERNEL32!LoadLibraryExW` at `0x1800094e2`
- `KERNEL32!LoadLibraryExW` at `0x180009536`

## pseudocode

```c
FARPROC __fastcall try_get_function_slow(unsigned int a1, const CHAR *a2, unsigned int *a3, unsigned int *a4)
{
  __int64 v4; // r12
  unsigned int *v6; // rsi
  __int64 v8; // rdi
  HMODULE Library; // rbx
  const WCHAR *v10; // rbp
  FARPROC ProcAddress; // rbx
  __int64 v12; // rax
  DWORD flOldProtect; // [rsp+80h] [rbp+18h] BYREF

  v4 = a1;
  v6 = a3;
  if ( a3 == a4 )
  {
LABEL_12:
    ProcAddress = 0;
    goto LABEL_13;
  }
  while ( 1 )
  {
    v8 = *v6;
    Library = (HMODULE)qword_1800A5610[v8];
    if ( !Library )
      break;
    if ( Library != (HMODULE)-1LL )
      goto LABEL_20;
LABEL_11:
    if ( ++v6 == a4 )
      goto LABEL_12;
  }
  v10 = off_180091340[v8];
  Library = LoadLibraryExW(v10, 0, 0x800u);
  if ( !Library
    && (GetLastError() != 87
     || !wcsncmp(v10, L"api-ms-", 7u)
     || !wcsncmp(v10, L"ext-ms-", 7u)
     || (Library = LoadLibraryExW(v10, 0, 0)) == 0) )
  {
    _InterlockedExchange64(&qword_1800A5610[v8], -1);
    goto LABEL_11;
  }
  if ( _InterlockedExchange64(&qword_1800A5610[v8], (__int64)Library) )
    FreeLibrary(Library);
LABEL_20:
  ProcAddress = GetProcAddress(Library, a2);
LABEL_13:
  _acrt_lock(14);
  flOldProtect = 0;
  if ( !VirtualProtect(qword_1800AC000, 0x100u, 4u, &flOldProtect) )
    goto LABEL_21;
  v12 = (__int64)ProcAddress;
  if ( !ProcAddress )
    v12 = -1;
  _InterlockedExchange64(&qword_1800AC000[v4], v12);
  if ( !VirtualProtect(qword_1800AC000, 0x100u, 2u, &flOldProtect) )
LABEL_21:
    abort();
  _acrt_unlock(14);
  return ProcAddress;
}

```

## disassembly

```asm
0x180009480  push    rbx
0x180009482  push    rbp
0x180009483  push    rsi
0x180009484  push    rdi
0x180009485  push    r12
0x180009487  push    r13
0x180009489  push    r14
0x18000948b  push    r15
0x18000948d  sub     rsp, 28h
0x180009491  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009495  mov     r12d, ecx
0x180009498  mov     r14, r9
0x18000949b  mov     rsi, r8
0x18000949e  mov     r15, rdx
0x1800094a1  cmp     r8, r9
0x1800094a4  jz      loc_180009565
0x1800094aa  lea     r13, cs:180000000h
0x1800094b1  mov     edi, [rsi]
0x1800094b3  mov     rbx, rva qword_1800A5610[r13+rdi*8]
0x1800094bb  nop
0x1800094bc  test    rbx, rbx
0x1800094bf  jz      short loc_1800094CF
0x1800094c1  cmp     rbx, rax
0x1800094c4  jnz     loc_180009609
0x1800094ca  jmp     loc_180009558
0x1800094cf  mov     rbp, ds:rva off_180091340[r13+rdi*8]; "api-ms-win-core-datetime-l1-1-1" ...
0x1800094d7  xor     edx, edx; hFile
0x1800094d9  mov     rcx, rbp; lpLibFileName
0x1800094dc  mov     r8d, 800h; dwFlags
0x1800094e2  call    cs:__imp_LoadLibraryExW
0x1800094e8  mov     rbx, rax
0x1800094eb  test    rax, rax
0x1800094ee  jnz     loc_1800095F0
0x1800094f4  call    cs:__imp_GetLastError
0x1800094fa  cmp     eax, 57h ; 'W'
0x1800094fd  jnz     short loc_180009548
0x1800094ff  lea     ebx, [rax-50h]
0x180009502  mov     rcx, rbp; String1
0x180009505  mov     r8d, ebx; MaxCount
0x180009508  lea     rdx, aApiMs; "api-ms-"
0x18000950f  call    wcsncmp
0x180009514  test    eax, eax
0x180009516  jz      short loc_180009548
0x180009518  mov     r8d, ebx; MaxCount
0x18000951b  lea     rdx, aExtMs; "ext-ms-"
0x180009522  mov     rcx, rbp; String1
0x180009525  call    wcsncmp
0x18000952a  test    eax, eax
0x18000952c  jz      short loc_180009548
0x18000952e  xor     r8d, r8d; dwFlags
0x180009531  xor     edx, edx; hFile
0x180009533  mov     rcx, rbp; lpLibFileName
0x180009536  call    cs:__imp_LoadLibraryExW
0x18000953c  mov     rbx, rax
0x18000953f  test    rax, rax
0x180009542  jnz     loc_1800095F0
0x180009548  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000954c  xchg    rax, rva qword_1800A5610[r13+rdi*8]
0x180009554  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009558  add     rsi, 4
0x18000955c  cmp     rsi, r14
0x18000955f  jnz     loc_1800094B1
0x180009565  xor     ebx, ebx
0x180009567  mov     edi, 0Eh
0x18000956c  mov     ecx, edi
0x18000956e  call    __acrt_lock
0x180009573  mov     ebp, 100h
0x180009578  mov     [rsp+68h+flOldProtect], 0
0x180009583  lea     rsi, qword_1800AC000
0x18000958a  mov     edx, ebp; dwSize
0x18000958c  mov     rcx, rsi; lpAddress
0x18000958f  lea     r9, [rsp+68h+flOldProtect]; lpflOldProtect
0x180009597  lea     r8d, [rdi-0Ah]; flNewProtect
0x18000959b  call    cs:__imp_VirtualProtect
0x1800095a1  test    eax, eax
0x1800095a3  jz      short loc_18000961D
0x1800095a5  test    rbx, rbx
0x1800095a8  mov     rax, rbx
0x1800095ab  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800095b2  cmovz   rax, rcx
0x1800095b6  xchg    rax, [rsi+r12*8]
0x1800095ba  lea     r9, [rsp+68h+flOldProtect]; lpflOldProtect
0x1800095c2  mov     edx, ebp; dwSize
0x1800095c4  lea     r8d, [rdi-0Ch]; flNewProtect
0x1800095c8  mov     rcx, rsi; lpAddress
0x1800095cb  call    cs:__imp_VirtualProtect
0x1800095d1  test    eax, eax
0x1800095d3  jz      short loc_18000961D
0x1800095d5  mov     ecx, edi
0x1800095d7  call    __acrt_unlock
0x1800095dc  mov     rax, rbx
0x1800095df  add     rsp, 28h
0x1800095e3  pop     r15
0x1800095e5  pop     r14
0x1800095e7  pop     r13
0x1800095e9  pop     r12
0x1800095eb  pop     rdi
0x1800095ec  pop     rsi
0x1800095ed  pop     rbp
0x1800095ee  pop     rbx
0x1800095ef  retn
0x1800095f0  mov     rax, rbx
0x1800095f3  xchg    rax, rva qword_1800A5610[r13+rdi*8]
0x1800095fb  test    rax, rax
0x1800095fe  jz      short loc_180009609
0x180009600  mov     rcx, rbx; hLibModule
0x180009603  call    cs:__imp_FreeLibrary
0x180009609  mov     rdx, r15; lpProcName
0x18000960c  mov     rcx, rbx; hModule
0x18000960f  call    cs:__imp_GetProcAddress
0x180009615  mov     rbx, rax
0x180009618  jmp     loc_180009567
0x18000961d  call    abort
```
