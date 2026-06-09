# try_get_function_slow

- ea: `0x18012f708`
- end: `0x18012f8ba`
- name: `try_get_function_slow`
- size: `434`
- prototype: ``
- caller_count: `17`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18012f6d0`
- `0x18012f8bc`
- `0x18012f918`
- `0x18012f974`
- `0x18012fa84`
- `0x18012fb54`
- `0x18012fc1c`
- `0x18012fcb0`
- `0x18012fd68`
- `0x18012fdd8`
- `0x18012fe40`
- `0x18012fec8`
- `0x18012ffbc`
- `0x180130020`
- `0x180130070`
- `0x1801300c8`
- `0x1801302a0`

## callees

- `0x18011e2a8`
- `0x18011e980`
- `0x180129598`
- `0x1801295f8`
- `0x18012f708`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x18012f825`
- `KERNEL32!VirtualProtect` at `0x18012f856`
- `KERNEL32!VirtualProtect` at `0x18012f825`
- `KERNEL32!VirtualProtect` at `0x18012f856`
- `KERNEL32!GetLastError` at `0x18012f787`
- `KERNEL32!GetLastError` at `0x18012f787`
- `KERNEL32!LoadLibraryExW` at `0x18012f775`
- `KERNEL32!LoadLibraryExW` at `0x18012f7c9`
- `KERNEL32!LoadLibraryExW` at `0x18012f775`
- `KERNEL32!LoadLibraryExW` at `0x18012f7c9`
- `KERNEL32!FreeLibrary` at `0x18012f89a`
- `KERNEL32!FreeLibrary` at `0x18012f89a`
- `KERNEL32!GetProcAddress` at `0x18012f8a6`
- `KERNEL32!GetProcAddress` at `0x18012f8a6`

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
    Library = (HMODULE)qword_180310AC0[v8];
    if ( !Library )
      break;
    if ( Library != (HMODULE)-1LL )
      goto LABEL_20;
LABEL_11:
    if ( ++v6 == a4 )
      goto LABEL_12;
  }
  v10 = off_180274DC0[v8];
  Library = LoadLibraryExW(v10, 0, 0x800u);
  if ( !Library
    && (GetLastError() != 87
     || !wcsncmp(v10, L"api-ms-", 7u)
     || !wcsncmp(v10, L"ext-ms-", 7u)
     || (Library = LoadLibraryExW(v10, 0, 0)) == 0) )
  {
    _InterlockedExchange64(&qword_180310AC0[v8], -1);
    goto LABEL_11;
  }
  if ( _InterlockedExchange64(&qword_180310AC0[v8], (__int64)Library) )
    FreeLibrary(Library);
LABEL_20:
  ProcAddress = GetProcAddress(Library, a2);
LABEL_13:
  _acrt_lock(14);
  flOldProtect = 0;
  if ( !VirtualProtect(qword_180333000, 0x100u, 4u, &flOldProtect) )
    goto LABEL_21;
  v12 = (__int64)ProcAddress;
  if ( !ProcAddress )
    v12 = -1;
  _InterlockedExchange64(&qword_180333000[v4], v12);
  if ( !VirtualProtect(qword_180333000, 0x100u, 2u, &flOldProtect) )
LABEL_21:
    abort();
  _acrt_unlock(14);
  return ProcAddress;
}

```

## disassembly

```asm
0x18012f708  mov     [rsp+arg_0], rbx
0x18012f70d  mov     [rsp+arg_8], rbp
0x18012f712  mov     [rsp+arg_18], rsi
0x18012f717  push    rdi
0x18012f718  push    r12
0x18012f71a  push    r13
0x18012f71c  push    r14
0x18012f71e  push    r15
0x18012f720  sub     rsp, 20h
0x18012f724  or      rax, 0FFFFFFFFFFFFFFFFh
0x18012f728  mov     r12d, ecx
0x18012f72b  mov     r14, r9
0x18012f72e  mov     rsi, r8
0x18012f731  mov     r15, rdx
0x18012f734  cmp     r8, r9
0x18012f737  jz      loc_18012F7F8
0x18012f73d  lea     r13, __ImageBase
0x18012f744  mov     edi, [rsi]
0x18012f746  mov     rbx, rva qword_180310AC0[r13+rdi*8]
0x18012f74e  nop
0x18012f74f  test    rbx, rbx
0x18012f752  jz      short loc_18012F762
0x18012f754  cmp     rbx, rax
0x18012f757  jnz     loc_18012F8A0
0x18012f75d  jmp     loc_18012F7EB
0x18012f762  mov     rbp, ds:rva off_180274DC0[r13+rdi*8]; "api-ms-win-core-datetime-l1-1-1" ...
0x18012f76a  xor     edx, edx; hFile
0x18012f76c  mov     rcx, rbp; lpLibFileName
0x18012f76f  mov     r8d, 800h; dwFlags
0x18012f775  call    cs:__imp_LoadLibraryExW
0x18012f77b  mov     rbx, rax
0x18012f77e  test    rax, rax
0x18012f781  jnz     loc_18012F887
0x18012f787  call    cs:__imp_GetLastError
0x18012f78d  cmp     eax, 57h ; 'W'
0x18012f790  jnz     short loc_18012F7DB
0x18012f792  lea     ebx, [rax-50h]
0x18012f795  mov     rcx, rbp; String1
0x18012f798  mov     r8d, ebx; MaxCount
0x18012f79b  lea     rdx, aApiMs; "api-ms-"
0x18012f7a2  call    wcsncmp
0x18012f7a7  test    eax, eax
0x18012f7a9  jz      short loc_18012F7DB
0x18012f7ab  mov     r8d, ebx; MaxCount
0x18012f7ae  lea     rdx, aExtMs; "ext-ms-"
0x18012f7b5  mov     rcx, rbp; String1
0x18012f7b8  call    wcsncmp
0x18012f7bd  test    eax, eax
0x18012f7bf  jz      short loc_18012F7DB
0x18012f7c1  xor     r8d, r8d; dwFlags
0x18012f7c4  xor     edx, edx; hFile
0x18012f7c6  mov     rcx, rbp; lpLibFileName
0x18012f7c9  call    cs:__imp_LoadLibraryExW
0x18012f7cf  mov     rbx, rax
0x18012f7d2  test    rax, rax
0x18012f7d5  jnz     loc_18012F887
0x18012f7db  or      rax, 0FFFFFFFFFFFFFFFFh
0x18012f7df  xchg    rax, rva qword_180310AC0[r13+rdi*8]
0x18012f7e7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18012f7eb  add     rsi, 4
0x18012f7ef  cmp     rsi, r14
0x18012f7f2  jnz     loc_18012F744
0x18012f7f8  xor     ebx, ebx
0x18012f7fa  mov     edi, 0Eh
0x18012f7ff  mov     ecx, edi
0x18012f801  call    __acrt_lock
0x18012f806  and     [rsp+48h+flOldProtect], 0
0x18012f80b  lea     rsi, qword_180333000
0x18012f812  mov     ebp, 100h
0x18012f817  lea     r9, [rsp+48h+flOldProtect]; lpflOldProtect
0x18012f81c  mov     edx, ebp; dwSize
0x18012f81e  lea     r8d, [rdi-0Ah]; flNewProtect
0x18012f822  mov     rcx, rsi; lpAddress
0x18012f825  call    cs:__imp_VirtualProtect
0x18012f82b  test    eax, eax
0x18012f82d  jz      loc_18012F8B4
0x18012f833  test    rbx, rbx
0x18012f836  mov     rax, rbx
0x18012f839  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18012f840  cmovz   rax, rcx
0x18012f844  xchg    rax, [rsi+r12*8]
0x18012f848  lea     r9, [rsp+48h+flOldProtect]; lpflOldProtect
0x18012f84d  mov     edx, ebp; dwSize
0x18012f84f  lea     r8d, [rdi-0Ch]; flNewProtect
0x18012f853  mov     rcx, rsi; lpAddress
0x18012f856  call    cs:__imp_VirtualProtect
0x18012f85c  test    eax, eax
0x18012f85e  jz      short loc_18012F8B4
0x18012f860  mov     ecx, edi
0x18012f862  call    __acrt_unlock
0x18012f867  mov     rbp, [rsp+48h+arg_8]
0x18012f86c  mov     rax, rbx
0x18012f86f  mov     rbx, [rsp+48h+arg_0]
0x18012f874  mov     rsi, [rsp+48h+arg_18]
0x18012f879  add     rsp, 20h
0x18012f87d  pop     r15
0x18012f87f  pop     r14
0x18012f881  pop     r13
0x18012f883  pop     r12
0x18012f885  pop     rdi
0x18012f886  retn
0x18012f887  mov     rax, rbx
0x18012f88a  xchg    rax, rva qword_180310AC0[r13+rdi*8]
0x18012f892  test    rax, rax
0x18012f895  jz      short loc_18012F8A0
0x18012f897  mov     rcx, rbx; hLibModule
0x18012f89a  call    cs:__imp_FreeLibrary
0x18012f8a0  mov     rdx, r15; lpProcName
0x18012f8a3  mov     rcx, rbx; hModule
0x18012f8a6  call    cs:__imp_GetProcAddress
0x18012f8ac  mov     rbx, rax
0x18012f8af  jmp     loc_18012F7FA
0x18012f8b4  call    abort
```
