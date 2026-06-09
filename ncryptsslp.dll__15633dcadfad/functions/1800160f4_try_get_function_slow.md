# try_get_function_slow

- ea: `0x1800160f4`
- end: `0x180016297`
- name: `try_get_function_slow`
- size: `419`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800162a0`
- `0x180016344`
- `0x180016428`

## callees

- `0x1800150f8`
- `0x1800160b4`
- `0x1800160d4`
- `0x1800160f4`
- `0x180017610`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016168`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016168`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016283`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016283`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016277`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016277`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016156`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800161aa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016156`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800161aa`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18001620f`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18001623f`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18001620f`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18001623f`

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
    Library = (HMODULE)qword_18003E170[v8];
    if ( !Library )
      break;
    if ( Library != (HMODULE)-1LL )
      goto LABEL_20;
LABEL_11:
    if ( ++v6 == a4 )
      goto LABEL_12;
  }
  v10 = off_180029040[v8];
  Library = LoadLibraryExW(v10, 0, 0x800u);
  if ( !Library
    && (GetLastError() != 87
     || !wcsncmp(v10, L"api-ms-", 7u)
     || !wcsncmp(v10, L"ext-ms-", 7u)
     || (Library = LoadLibraryExW(v10, 0, 0)) == 0) )
  {
    _InterlockedExchange64(&qword_18003E170[v8], -1);
    goto LABEL_11;
  }
  if ( _InterlockedExchange64(&qword_18003E170[v8], (__int64)Library) )
    FreeLibrary(Library);
LABEL_20:
  ProcAddress = GetProcAddress(Library, a2);
LABEL_13:
  _acrt_lock(14);
  flOldProtect = 0;
  if ( !VirtualProtect(qword_180043000, 0x100u, 4u, &flOldProtect) )
    goto LABEL_21;
  v12 = (__int64)ProcAddress;
  if ( !ProcAddress )
    v12 = -1;
  _InterlockedExchange64(&qword_180043000[v4], v12);
  if ( !VirtualProtect(qword_180043000, 0x100u, 2u, &flOldProtect) )
LABEL_21:
    abort();
  _acrt_unlock(14);
  return ProcAddress;
}

```

## disassembly

```asm
0x1800160f4  push    rbx
0x1800160f6  push    rbp
0x1800160f7  push    rsi
0x1800160f8  push    rdi
0x1800160f9  push    r12
0x1800160fb  push    r13
0x1800160fd  push    r14
0x1800160ff  push    r15
0x180016101  sub     rsp, 28h
0x180016105  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016109  mov     r12d, ecx
0x18001610c  mov     r14, r9
0x18001610f  mov     rsi, r8
0x180016112  mov     r15, rdx
0x180016115  cmp     r8, r9
0x180016118  jz      loc_1800161D9
0x18001611e  lea     r13, __ImageBase
0x180016125  mov     edi, [rsi]
0x180016127  mov     rbx, rva qword_18003E170[r13+rdi*8]
0x18001612f  nop
0x180016130  test    rbx, rbx
0x180016133  jz      short loc_180016143
0x180016135  cmp     rbx, rax
0x180016138  jnz     loc_18001627D
0x18001613e  jmp     loc_1800161CC
0x180016143  mov     rbp, ds:rva off_180029040[r13+rdi*8]; "api-ms-win-core-datetime-l1-1-1" ...
0x18001614b  xor     edx, edx; hFile
0x18001614d  mov     rcx, rbp; lpLibFileName
0x180016150  mov     r8d, 800h; dwFlags
0x180016156  call    cs:__imp_LoadLibraryExW
0x18001615c  mov     rbx, rax
0x18001615f  test    rax, rax
0x180016162  jnz     loc_180016264
0x180016168  call    cs:__imp_GetLastError
0x18001616e  cmp     eax, 57h ; 'W'
0x180016171  jnz     short loc_1800161BC
0x180016173  lea     ebx, [rax-50h]
0x180016176  mov     rcx, rbp; String1
0x180016179  mov     r8d, ebx; MaxCount
0x18001617c  lea     rdx, aApiMs; "api-ms-"
0x180016183  call    wcsncmp
0x180016188  test    eax, eax
0x18001618a  jz      short loc_1800161BC
0x18001618c  mov     r8d, ebx; MaxCount
0x18001618f  lea     rdx, aExtMs; "ext-ms-"
0x180016196  mov     rcx, rbp; String1
0x180016199  call    wcsncmp
0x18001619e  test    eax, eax
0x1800161a0  jz      short loc_1800161BC
0x1800161a2  xor     r8d, r8d; dwFlags
0x1800161a5  xor     edx, edx; hFile
0x1800161a7  mov     rcx, rbp; lpLibFileName
0x1800161aa  call    cs:__imp_LoadLibraryExW
0x1800161b0  mov     rbx, rax
0x1800161b3  test    rax, rax
0x1800161b6  jnz     loc_180016264
0x1800161bc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800161c0  xchg    rax, rva qword_18003E170[r13+rdi*8]
0x1800161c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800161cc  add     rsi, 4
0x1800161d0  cmp     rsi, r14
0x1800161d3  jnz     loc_180016125
0x1800161d9  xor     ebx, ebx
0x1800161db  mov     edi, 0Eh
0x1800161e0  mov     ecx, edi
0x1800161e2  call    __acrt_lock
0x1800161e7  mov     ebp, 100h
0x1800161ec  mov     [rsp+68h+flOldProtect], 0
0x1800161f7  lea     rsi, qword_180043000
0x1800161fe  mov     edx, ebp; dwSize
0x180016200  mov     rcx, rsi; lpAddress
0x180016203  lea     r9, [rsp+68h+flOldProtect]; lpflOldProtect
0x18001620b  lea     r8d, [rdi-0Ah]; flNewProtect
0x18001620f  call    cs:__imp_VirtualProtect
0x180016215  test    eax, eax
0x180016217  jz      short loc_180016291
0x180016219  test    rbx, rbx
0x18001621c  mov     rax, rbx
0x18001621f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180016226  cmovz   rax, rcx
0x18001622a  xchg    rax, [rsi+r12*8]
0x18001622e  lea     r9, [rsp+68h+flOldProtect]; lpflOldProtect
0x180016236  mov     edx, ebp; dwSize
0x180016238  lea     r8d, [rdi-0Ch]; flNewProtect
0x18001623c  mov     rcx, rsi; lpAddress
0x18001623f  call    cs:__imp_VirtualProtect
0x180016245  test    eax, eax
0x180016247  jz      short loc_180016291
0x180016249  mov     ecx, edi
0x18001624b  call    __acrt_unlock
0x180016250  mov     rax, rbx
0x180016253  add     rsp, 28h
0x180016257  pop     r15
0x180016259  pop     r14
0x18001625b  pop     r13
0x18001625d  pop     r12
0x18001625f  pop     rdi
0x180016260  pop     rsi
0x180016261  pop     rbp
0x180016262  pop     rbx
0x180016263  retn
0x180016264  mov     rax, rbx
0x180016267  xchg    rax, rva qword_18003E170[r13+rdi*8]
0x18001626f  test    rax, rax
0x180016272  jz      short loc_18001627D
0x180016274  mov     rcx, rbx; hLibModule
0x180016277  call    cs:__imp_FreeLibrary
0x18001627d  mov     rdx, r15; lpProcName
0x180016280  mov     rcx, rbx; hModule
0x180016283  call    cs:__imp_GetProcAddress
0x180016289  mov     rbx, rax
0x18001628c  jmp     loc_1800161DB
0x180016291  call    abort
```
