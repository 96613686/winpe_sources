# try_get_function_slow

- ea: `0x180358ec8`
- end: `0x18035907a`
- name: `try_get_function_slow`
- size: `434`
- prototype: ``
- caller_count: `18`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180358e90`
- `0x18035907c`
- `0x1803590d8`
- `0x180359134`
- `0x180359244`
- `0x180359314`
- `0x1803593dc`
- `0x180359470`
- `0x180359528`
- `0x1803595a0`
- `0x180359608`
- `0x180359690`
- `0x180359784`
- `0x1803597e8`
- `0x180359838`
- `0x18035987c`
- `0x1803598f0`
- `0x180359ad0`

## callees

- `0x180344c2c`
- `0x180350298`
- `0x1803502f8`
- `0x180354790`
- `0x180358ec8`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180358f35`
- `KERNEL32!LoadLibraryExW` at `0x180358f89`
- `KERNEL32!LoadLibraryExW` at `0x180358f35`
- `KERNEL32!LoadLibraryExW` at `0x180358f89`
- `KERNEL32!VirtualProtect` at `0x180358fe5`
- `KERNEL32!VirtualProtect` at `0x180359016`
- `KERNEL32!VirtualProtect` at `0x180358fe5`
- `KERNEL32!VirtualProtect` at `0x180359016`
- `KERNEL32!GetLastError` at `0x180358f47`
- `KERNEL32!GetLastError` at `0x180358f47`
- `KERNEL32!FreeLibrary` at `0x18035905a`
- `KERNEL32!FreeLibrary` at `0x18035905a`
- `KERNEL32!GetProcAddress` at `0x180359066`
- `KERNEL32!GetProcAddress` at `0x180359066`

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
  DWORD flOldProtect; // [rsp+60h] [rbp+18h] BYREF

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
    Library = (HMODULE)qword_180540170[v8];
    if ( !Library )
      break;
    if ( Library != (HMODULE)-1LL )
      goto LABEL_20;
LABEL_11:
    if ( ++v6 == a4 )
      goto LABEL_12;
  }
  v10 = off_18043DBA0[v8];
  Library = LoadLibraryExW(v10, 0, 0x800u);
  if ( !Library
    && (GetLastError() != 87
     || !wcsncmp(v10, L"api-ms-", 7u)
     || !wcsncmp(v10, L"ext-ms-", 7u)
     || (Library = LoadLibraryExW(v10, 0, 0)) == 0) )
  {
    _InterlockedExchange64(&qword_180540170[v8], -1);
    goto LABEL_11;
  }
  if ( _InterlockedExchange64(&qword_180540170[v8], (__int64)Library) )
    FreeLibrary(Library);
LABEL_20:
  ProcAddress = GetProcAddress(Library, a2);
LABEL_13:
  _acrt_lock(14);
  flOldProtect = 0;
  if ( !VirtualProtect(qword_180576000, 0x100u, 4u, &flOldProtect) )
    goto LABEL_21;
  v12 = (__int64)ProcAddress;
  if ( !ProcAddress )
    v12 = -1;
  _InterlockedExchange64(&qword_180576000[v4], v12);
  if ( !VirtualProtect(qword_180576000, 0x100u, 2u, &flOldProtect) )
LABEL_21:
    abort();
  _acrt_unlock(14);
  return ProcAddress;
}

```

## disassembly

```asm
0x180358ec8  mov     [rsp+arg_0], rbx
0x180358ecd  mov     [rsp+arg_8], rbp
0x180358ed2  mov     [rsp+arg_18], rsi
0x180358ed7  push    rdi
0x180358ed8  push    r12
0x180358eda  push    r13
0x180358edc  push    r14
0x180358ede  push    r15
0x180358ee0  sub     rsp, 20h
0x180358ee4  or      rax, 0FFFFFFFFFFFFFFFFh
0x180358ee8  mov     r12d, ecx
0x180358eeb  mov     r14, r9
0x180358eee  mov     rsi, r8
0x180358ef1  mov     r15, rdx
0x180358ef4  cmp     r8, r9
0x180358ef7  jz      loc_180358FB8
0x180358efd  lea     r13, __ImageBase
0x180358f04  mov     edi, [rsi]
0x180358f06  mov     rbx, rva qword_180540170[r13+rdi*8]
0x180358f0e  nop
0x180358f0f  test    rbx, rbx
0x180358f12  jz      short loc_180358F22
0x180358f14  cmp     rbx, rax
0x180358f17  jnz     loc_180359060
0x180358f1d  jmp     loc_180358FAB
0x180358f22  mov     rbp, ds:rva off_18043DBA0[r13+rdi*8]; "api-ms-win-core-datetime-l1-1-1" ...
0x180358f2a  xor     edx, edx; hFile
0x180358f2c  mov     rcx, rbp; lpLibFileName
0x180358f2f  mov     r8d, 800h; dwFlags
0x180358f35  call    cs:__imp_LoadLibraryExW
0x180358f3b  mov     rbx, rax
0x180358f3e  test    rax, rax
0x180358f41  jnz     loc_180359047
0x180358f47  call    cs:__imp_GetLastError
0x180358f4d  cmp     eax, 57h ; 'W'
0x180358f50  jnz     short loc_180358F9B
0x180358f52  lea     ebx, [rax-50h]
0x180358f55  mov     rcx, rbp; String1
0x180358f58  mov     r8d, ebx; MaxCount
0x180358f5b  lea     rdx, aApiMs; "api-ms-"
0x180358f62  call    wcsncmp
0x180358f67  test    eax, eax
0x180358f69  jz      short loc_180358F9B
0x180358f6b  mov     r8d, ebx; MaxCount
0x180358f6e  lea     rdx, aExtMs; "ext-ms-"
0x180358f75  mov     rcx, rbp; String1
0x180358f78  call    wcsncmp
0x180358f7d  test    eax, eax
0x180358f7f  jz      short loc_180358F9B
0x180358f81  xor     r8d, r8d; dwFlags
0x180358f84  xor     edx, edx; hFile
0x180358f86  mov     rcx, rbp; lpLibFileName
0x180358f89  call    cs:__imp_LoadLibraryExW
0x180358f8f  mov     rbx, rax
0x180358f92  test    rax, rax
0x180358f95  jnz     loc_180359047
0x180358f9b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180358f9f  xchg    rax, rva qword_180540170[r13+rdi*8]
0x180358fa7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180358fab  add     rsi, 4
0x180358faf  cmp     rsi, r14
0x180358fb2  jnz     loc_180358F04
0x180358fb8  xor     ebx, ebx
0x180358fba  mov     edi, 0Eh
0x180358fbf  mov     ecx, edi
0x180358fc1  call    __acrt_lock
0x180358fc6  and     [rsp+48h+flOldProtect], 0
0x180358fcb  lea     rsi, qword_180576000
0x180358fd2  mov     ebp, 100h
0x180358fd7  lea     r9, [rsp+48h+flOldProtect]; lpflOldProtect
0x180358fdc  mov     edx, ebp; dwSize
0x180358fde  lea     r8d, [rdi-0Ah]; flNewProtect
0x180358fe2  mov     rcx, rsi; lpAddress
0x180358fe5  call    cs:__imp_VirtualProtect
0x180358feb  test    eax, eax
0x180358fed  jz      loc_180359074
0x180358ff3  test    rbx, rbx
0x180358ff6  mov     rax, rbx
0x180358ff9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180359000  cmovz   rax, rcx
0x180359004  xchg    rax, [rsi+r12*8]
0x180359008  lea     r9, [rsp+48h+flOldProtect]; lpflOldProtect
0x18035900d  mov     edx, ebp; dwSize
0x18035900f  lea     r8d, [rdi-0Ch]; flNewProtect
0x180359013  mov     rcx, rsi; lpAddress
0x180359016  call    cs:__imp_VirtualProtect
0x18035901c  test    eax, eax
0x18035901e  jz      short loc_180359074
0x180359020  mov     ecx, edi
0x180359022  call    __acrt_unlock
0x180359027  mov     rbp, [rsp+48h+arg_8]
0x18035902c  mov     rax, rbx
0x18035902f  mov     rbx, [rsp+48h+arg_0]
0x180359034  mov     rsi, [rsp+48h+arg_18]
0x180359039  add     rsp, 20h
0x18035903d  pop     r15
0x18035903f  pop     r14
0x180359041  pop     r13
0x180359043  pop     r12
0x180359045  pop     rdi
0x180359046  retn
0x180359047  mov     rax, rbx
0x18035904a  xchg    rax, rva qword_180540170[r13+rdi*8]
0x180359052  test    rax, rax
0x180359055  jz      short loc_180359060
0x180359057  mov     rcx, rbx; hLibModule
0x18035905a  call    cs:__imp_FreeLibrary
0x180359060  mov     rdx, r15; lpProcName
0x180359063  mov     rcx, rbx; hModule
0x180359066  call    cs:__imp_GetProcAddress
0x18035906c  mov     rbx, rax
0x18035906f  jmp     loc_180358FBA
0x180359074  call    abort
```
