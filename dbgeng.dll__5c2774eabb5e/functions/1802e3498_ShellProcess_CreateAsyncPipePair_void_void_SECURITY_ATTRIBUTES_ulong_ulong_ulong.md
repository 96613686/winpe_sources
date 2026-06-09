# ShellProcess::CreateAsyncPipePair(void * *,void * *,_SECURITY_ATTRIBUTES *,ulong,ulong,ulong)

- ea: `0x1802e3498`
- end: `0x1802e35d5`
- name: `?CreateAsyncPipePair@ShellProcess@@SAHPEAPEAX0PEAU_SECURITY_ATTRIBUTES@@KKK@Z`
- size: `317`
- prototype: `static int(void **, void **, struct _SECURITY_ATTRIBUTES *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1802e35dc`

## callees

- `0x1800f0f40`
- `0x1802e3498`
- `0x18041649c`
- `0x180416d9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e3586`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e3586`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1802e34d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1802e34d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1802e34f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1802e34f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802e3597`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802e3597`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1802e3574`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1802e3574`

## pseudocode

```c
__int64 __fastcall ShellProcess::CreateAsyncPipePair(
        void **a1,
        void **a2,
        struct _SECURITY_ATTRIBUTES *a3,
        __int64 a4,
        unsigned int a5)
{
  DWORD v8; // ecx
  unsigned int v10; // ebx
  DWORD CurrentProcessId; // eax
  unsigned int v12; // r8d
  unsigned int v13; // r9d
  void *NamedPipeA; // rdi
  HANDLE FileA; // rax
  DWORD LastError; // ebx
  unsigned int hTemplateFile; // [rsp+30h] [rbp-158h]
  CHAR FileName[272]; // [rsp+40h] [rbp-148h] BYREF

  if ( (a5 & 0xBFFFFFFF) != 0 )
  {
    v8 = 87;
LABEL_3:
    SetLastError(v8);
    return 0;
  }
  v10 = ShellProcess::s_PipeSerialNumber++;
  CurrentProcessId = GetCurrentProcessId();
  PrintString(FileName, 260, "\\\\.\\Pipe\\Win32PipesEx.DBGENG.%08x.%08x", CurrentProcessId, v10);
  NamedPipeA = DbgCreateNamedPipeA(FileName, a5 | 1, v12, v13, 0x1000u, 0x1000u, hTemplateFile, a3);
  if ( NamedPipeA == (void *)-1LL )
    return 0;
  FileA = CreateFileA(FileName, 0x40000000u, 0, a3, 3u, 0x80u, 0);
  if ( FileA == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    CloseHandle(NamedPipeA);
    v8 = LastError;
    goto LABEL_3;
  }
  *a1 = NamedPipeA;
  *a2 = FileA;
  return 1;
}

```

## disassembly

```asm
0x1802e3498  push    rbx
0x1802e349a  push    rsi
0x1802e349b  push    rdi
0x1802e349c  push    r14
0x1802e349e  push    r15
0x1802e34a0  sub     rsp, 160h
0x1802e34a7  mov     rax, cs:__security_cookie
0x1802e34ae  xor     rax, rsp
0x1802e34b1  mov     [rsp+188h+var_38], rax
0x1802e34b9  mov     edi, [rsp+188h+arg_20]
0x1802e34c0  mov     rsi, r8
0x1802e34c3  mov     r15, rdx
0x1802e34c6  mov     r14, rcx
0x1802e34c9  test    edi, 0BFFFFFFFh
0x1802e34cf  jz      short loc_1802E34E9
0x1802e34d1  mov     ecx, 57h ; 'W'; dwErrCode
0x1802e34d6  call    cs:__imp_SetLastError
0x1802e34dd  nop     dword ptr [rax+rax+00h]
0x1802e34e2  xor     eax, eax
0x1802e34e4  jmp     loc_1802E35B5
0x1802e34e9  mov     ebx, cs:?s_PipeSerialNumber@ShellProcess@@2KA; ulong ShellProcess::s_PipeSerialNumber
0x1802e34ef  lea     eax, [rbx+1]
0x1802e34f2  mov     cs:?s_PipeSerialNumber@ShellProcess@@2KA, eax; ulong ShellProcess::s_PipeSerialNumber
0x1802e34f8  call    cs:__imp_GetCurrentProcessId
0x1802e34ff  nop     dword ptr [rax+rax+00h]
0x1802e3504  lea     r8, aPipeWin32pipes; "\\\\.\\Pipe\\Win32PipesEx.DBGENG.%08x.%"...
0x1802e350b  mov     [rsp+188h+dwCreationDisposition], ebx
0x1802e350f  mov     r9d, eax
0x1802e3512  lea     rcx, [rsp+188h+FileName]
0x1802e3517  mov     edx, 104h
0x1802e351c  call    PrintString
0x1802e3521  mov     eax, 1000h
0x1802e3526  mov     [rsp+188h+var_150], rsi; struct _SECURITY_ATTRIBUTES *
0x1802e352b  mov     [rsp+188h+dwFlagsAndAttributes], eax; unsigned int
0x1802e352f  lea     rcx, [rsp+188h+FileName]; char *
0x1802e3534  or      edi, 1
0x1802e3537  mov     [rsp+188h+dwCreationDisposition], eax; unsigned int
0x1802e353b  mov     edx, edi; unsigned int
0x1802e353d  call    ?DbgCreateNamedPipeA@@YAPEAXPEBDKKKKKKPEAU_SECURITY_ATTRIBUTES@@@Z; DbgCreateNamedPipeA(char const *,ulong,ulong,ulong,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *)
0x1802e3542  mov     rdi, rax
0x1802e3545  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1802e3549  jz      short loc_1802E34E2
0x1802e354b  mov     [rsp+188h+hTemplateFile], 0; hTemplateFile
0x1802e3554  lea     rcx, [rsp+188h+FileName]; lpFileName
0x1802e3559  mov     [rsp+188h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1802e3561  mov     r9, rsi; lpSecurityAttributes
0x1802e3564  xor     r8d, r8d; dwShareMode
0x1802e3567  mov     [rsp+188h+dwCreationDisposition], 3; dwCreationDisposition
0x1802e356f  mov     edx, 40000000h; dwDesiredAccess
0x1802e3574  call    cs:__imp_CreateFileA
0x1802e357b  nop     dword ptr [rax+rax+00h]
0x1802e3580  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1802e3584  jnz     short loc_1802E35AA
0x1802e3586  call    cs:__imp_GetLastError
0x1802e358d  nop     dword ptr [rax+rax+00h]
0x1802e3592  mov     rcx, rdi; hObject
0x1802e3595  mov     ebx, eax
0x1802e3597  call    cs:__imp_CloseHandle
0x1802e359e  nop     dword ptr [rax+rax+00h]
0x1802e35a3  mov     ecx, ebx
0x1802e35a5  jmp     loc_1802E34D6
0x1802e35aa  mov     [r14], rdi
0x1802e35ad  mov     [r15], rax
0x1802e35b0  mov     eax, 1
0x1802e35b5  mov     rcx, [rsp+188h+var_38]
0x1802e35bd  xor     rcx, rsp; StackCookie
0x1802e35c0  call    __security_check_cookie
0x1802e35c5  add     rsp, 160h
0x1802e35cc  pop     r15
0x1802e35ce  pop     r14
0x1802e35d0  pop     rdi
0x1802e35d1  pop     rsi
0x1802e35d2  pop     rbx
0x1802e35d3  retn
```
