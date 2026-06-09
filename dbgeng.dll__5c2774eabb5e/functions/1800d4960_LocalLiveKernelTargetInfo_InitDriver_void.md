# LocalLiveKernelTargetInfo::InitDriver(void)

- ea: `0x1800d4960`
- end: `0x1800d4c4b`
- name: `?InitDriver@LocalLiveKernelTargetInfo@@IEAAJXZ`
- size: `747`
- prototype: `__int64 __fastcall(LocalLiveKernelTargetInfo *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1802d0630`

## callees

- `0x18008e740`
- `0x1800b94c4`
- `0x1800d4960`
- `0x1800d4c54`
- `0x1800dad20`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LockResource` at `0x1800d4a0f`
- `api-ms-win-core-libraryloader-l1-1-0!LockResource` at `0x1800d4a0f`
- `api-ms-win-core-libraryloader-l1-1-0!SizeofResource` at `0x1800d49db`
- `api-ms-win-core-libraryloader-l1-1-0!SizeofResource` at `0x1800d49db`
- `api-ms-win-core-libraryloader-l1-1-0!LoadResource` at `0x1800d49f7`
- `api-ms-win-core-libraryloader-l1-1-0!LoadResource` at `0x1800d49f7`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800d49a0`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800d49a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4a9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4ab7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4b9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4bb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4a9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4ab7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4b9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4bb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d4b15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d4bf1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d4b15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d4bf1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d4af9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d4af9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800d4c1b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800d4c1b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d4a89`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d4b81`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d4a89`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d4b81`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800d4a38`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800d4a38`

## string_xrefs

- `0x1800d4999`: `dbgeng.dll`

## pseudocode

```c
__int64 __fastcall LocalLiveKernelTargetInfo::InitDriver(LocalLiveKernelTargetInfo *this)
{
  __int64 v2; // rbp
  HMODULE ModuleHandleW; // rdi
  HRSRC v4; // rax
  HRSRC v5; // rsi
  DWORD v6; // ebx
  HGLOBAL Resource; // rax
  const void *v8; // r14
  const WCHAR *v9; // rdi
  __int64 v10; // r8
  char *v11; // rax
  char *v12; // rsi
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  unsigned int v17; // ebx
  signed int v18; // eax
  __int64 v19; // rcx
  HANDLE FileW; // rax
  __int64 v22; // rcx
  signed int LastError; // eax
  int v24; // [rsp+78h] [rbp+10h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp+18h] BYREF

  v24 = 0;
  IsNtDriverControlRunning(this, &v24);
  v2 = -1;
  if ( v24 )
  {
    v9 = (const WCHAR *)((char *)this + 4240);
    *((_WORD *)this + 2120) = 0;
LABEL_20:
    FileW = CreateFileW(L"\\\\.\\kldbgdrv", 0xC0000000, 3u, 0, 3u, 0x80u, 0);
    *((_QWORD *)this + 595) = FileW;
    if ( FileW != (HANDLE)-1LL )
      return 0;
    if ( GetLastError() )
    {
      LastError = GetLastError();
      v17 = LastError;
      if ( LastError > 0 )
        v17 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v17 = -2147467259;
    }
    ControlNtDriver(v22, 0, 8);
    goto LABEL_26;
  }
  ModuleHandleW = GetModuleHandleW(L"dbgeng.dll");
  v4 = (HRSRC)MEMORY[0](ModuleHandleW, 30583, 17476);
  v5 = v4;
  if ( !v4 )
    return 2147500033LL;
  v6 = SizeofResource(ModuleHandleW, v4);
  if ( !v6 )
    return 2147500033LL;
  Resource = LoadResource(ModuleHandleW, v5);
  if ( !Resource )
    return 2147500033LL;
  v8 = LockResource(Resource);
  if ( !v8 )
    return 2147500033LL;
  v9 = (const WCHAR *)((char *)this + 4240);
  if ( !GetSystemDirectoryW((LPWSTR)this + 2120, 0x104u)
    || !(unsigned int)CatNStringW((char *)this + 4240, L"\\kldbgdrv.sys", v10, 260) )
  {
    return 2147942487LL;
  }
  v11 = (char *)CreateFileW(v9, 0xC0000000, 0, 0, 2u, 0x80u, 0);
  v12 = v11;
  if ( v11 == (char *)-1LL
    || (NumberOfBytesWritten = 0, !WriteFile(v11, v8, v6, &NumberOfBytesWritten, 0))
    || NumberOfBytesWritten < v6 )
  {
    if ( GetLastError() )
    {
      v18 = GetLastError();
      v17 = v18;
      if ( v18 > 0 )
        v17 = (unsigned __int16)v18 | 0x80070000;
    }
    else
    {
      v17 = -2147467259;
    }
    goto LABEL_27;
  }
  CloseHandle(v12);
  v17 = ControlNtDriver(v19, (char *)this + 4240, 3);
  if ( !v17 )
    goto LABEL_20;
LABEL_26:
  v12 = 0;
LABEL_27:
  *((_QWORD *)this + 595) = 0;
  if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v12);
  if ( !v24 )
  {
    do
      ++v2;
    while ( v9[v2] );
    if ( !v2 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v14, v13, v15, v16);
    DeleteFileW(v9);
    *v9 = 0;
  }
  return v17;
}

```

## disassembly

```asm
0x1800d4960  mov     rax, rsp
0x1800d4963  mov     [rax+8], rbx
0x1800d4967  mov     [rax+20h], rbp
0x1800d496b  push    rsi
0x1800d496c  push    rdi
0x1800d496d  push    r13
0x1800d496f  push    r14
0x1800d4971  push    r15
0x1800d4973  sub     rsp, 40h
0x1800d4977  xor     r13d, r13d
0x1800d497a  lea     rdx, [rax+10h]
0x1800d497e  mov     [rax+10h], r13d
0x1800d4982  mov     r15, rcx
0x1800d4985  call    IsNtDriverControlRunning
0x1800d498a  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800d498e  cmp     [rsp+68h+arg_8], r13d
0x1800d4993  jnz     loc_1800D4B4E
0x1800d4999  lea     rcx, aDbgengDll_0; "dbgeng.dll"
0x1800d49a0  call    cs:__imp_GetModuleHandleW
0x1800d49a7  nop     dword ptr [rax+rax+00h]
0x1800d49ac  mov     edx, 7777h
0x1800d49b1  mov     r8d, 4444h
0x1800d49b7  mov     rdi, rax
0x1800d49ba  mov     rax, cs:qword_18082D9E0
0x1800d49c1  mov     rcx, rdi
0x1800d49c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d49c9  mov     rsi, rax
0x1800d49cc  test    rax, rax
0x1800d49cf  jz      loc_1800D4B44
0x1800d49d5  mov     rdx, rax; hResInfo
0x1800d49d8  mov     rcx, rdi; hModule
0x1800d49db  call    cs:__imp_SizeofResource
0x1800d49e2  nop     dword ptr [rax+rax+00h]
0x1800d49e7  mov     ebx, eax
0x1800d49e9  test    eax, eax
0x1800d49eb  jz      loc_1800D4B44
0x1800d49f1  mov     rdx, rsi; hResInfo
0x1800d49f4  mov     rcx, rdi; hModule
0x1800d49f7  call    cs:__imp_LoadResource
0x1800d49fe  nop     dword ptr [rax+rax+00h]
0x1800d4a03  test    rax, rax
0x1800d4a06  jz      loc_1800D4B44
0x1800d4a0c  mov     rcx, rax; hResData
0x1800d4a0f  call    cs:__imp_LockResource
0x1800d4a16  nop     dword ptr [rax+rax+00h]
0x1800d4a1b  mov     r14, rax
0x1800d4a1e  test    rax, rax
0x1800d4a21  jz      loc_1800D4B44
0x1800d4a27  lea     rdi, [r15+1090h]
0x1800d4a2e  mov     esi, 104h
0x1800d4a33  mov     edx, esi; uSize
0x1800d4a35  mov     rcx, rdi; lpBuffer
0x1800d4a38  call    cs:__imp_GetSystemDirectoryW
0x1800d4a3f  nop     dword ptr [rax+rax+00h]
0x1800d4a44  test    eax, eax
0x1800d4a46  jz      loc_1800D4B3A
0x1800d4a4c  mov     r9d, esi
0x1800d4a4f  lea     rdx, aKldbgdrvSys; "\\kldbgdrv.sys"
0x1800d4a56  mov     rcx, rdi
0x1800d4a59  call    CatNStringW
0x1800d4a5e  test    eax, eax
0x1800d4a60  jz      loc_1800D4B3A
0x1800d4a66  mov     [rsp+68h+hTemplateFile], r13; hTemplateFile
0x1800d4a6b  xor     r9d, r9d; lpSecurityAttributes
0x1800d4a6e  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800d4a76  xor     r8d, r8d; dwShareMode
0x1800d4a79  mov     edx, 0C0000000h; dwDesiredAccess
0x1800d4a7e  mov     [rsp+68h+dwCreationDisposition], 2; dwCreationDisposition
0x1800d4a86  mov     rcx, rdi; lpFileName
0x1800d4a89  call    cs:__imp_CreateFileW
0x1800d4a90  nop     dword ptr [rax+rax+00h]
0x1800d4a95  mov     rsi, rax
0x1800d4a98  cmp     rax, rbp
0x1800d4a9b  jnz     short loc_1800D4ADB
0x1800d4a9d  call    cs:__imp_GetLastError
0x1800d4aa4  nop     dword ptr [rax+rax+00h]
0x1800d4aa9  test    eax, eax
0x1800d4aab  jnz     short loc_1800D4AB7
0x1800d4aad  mov     ebx, 80004005h
0x1800d4ab2  jmp     loc_1800D4BDD
0x1800d4ab7  call    cs:__imp_GetLastError
0x1800d4abe  nop     dword ptr [rax+rax+00h]
0x1800d4ac3  mov     ebx, eax
0x1800d4ac5  test    eax, eax
0x1800d4ac7  jle     loc_1800D4BDD
0x1800d4acd  movzx   ebx, ax
0x1800d4ad0  or      ebx, 80070000h
0x1800d4ad6  jmp     loc_1800D4BDD
0x1800d4adb  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800d4ae3  mov     [rsp+68h+NumberOfBytesWritten], r13d
0x1800d4aeb  mov     r8d, ebx; nNumberOfBytesToWrite
0x1800d4aee  mov     qword ptr [rsp+68h+dwCreationDisposition], r13; lpOverlapped
0x1800d4af3  mov     rdx, r14; lpBuffer
0x1800d4af6  mov     rcx, rsi; hFile
0x1800d4af9  call    cs:__imp_WriteFile
0x1800d4b00  nop     dword ptr [rax+rax+00h]
0x1800d4b05  test    eax, eax
0x1800d4b07  jz      short loc_1800D4A9D
0x1800d4b09  cmp     [rsp+68h+NumberOfBytesWritten], ebx
0x1800d4b10  jb      short loc_1800D4A9D
0x1800d4b12  mov     rcx, rsi; hObject
0x1800d4b15  call    cs:__imp_CloseHandle
0x1800d4b1c  nop     dword ptr [rax+rax+00h]
0x1800d4b21  mov     r8d, 3
0x1800d4b27  mov     rdx, rdi
0x1800d4b2a  call    ControlNtDriver
0x1800d4b2f  mov     ebx, eax
0x1800d4b31  test    eax, eax
0x1800d4b33  jz      short loc_1800D4B59
0x1800d4b35  jmp     loc_1800D4BDA
0x1800d4b3a  mov     eax, 80070057h
0x1800d4b3f  jmp     loc_1800D4C31
0x1800d4b44  mov     eax, 80004001h
0x1800d4b49  jmp     loc_1800D4C31
0x1800d4b4e  lea     rdi, [r15+1090h]
0x1800d4b55  mov     [rdi], r13w
0x1800d4b59  xor     r9d, r9d; lpSecurityAttributes
0x1800d4b5c  mov     [rsp+68h+hTemplateFile], r13; hTemplateFile
0x1800d4b61  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800d4b69  lea     rcx, FileName; "\\\\.\\kldbgdrv"
0x1800d4b70  mov     edx, 0C0000000h; dwDesiredAccess
0x1800d4b75  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x1800d4b7d  lea     r8d, [r9+3]; dwShareMode
0x1800d4b81  call    cs:__imp_CreateFileW
0x1800d4b88  nop     dword ptr [rax+rax+00h]
0x1800d4b8d  mov     [r15+1298h], rax
0x1800d4b94  cmp     rax, rbp
0x1800d4b97  jnz     loc_1800D4C2F
0x1800d4b9d  call    cs:__imp_GetLastError
0x1800d4ba4  nop     dword ptr [rax+rax+00h]
0x1800d4ba9  test    eax, eax
0x1800d4bab  jnz     short loc_1800D4BB4
0x1800d4bad  mov     ebx, 80004005h
0x1800d4bb2  jmp     short loc_1800D4BCF
0x1800d4bb4  call    cs:__imp_GetLastError
0x1800d4bbb  nop     dword ptr [rax+rax+00h]
0x1800d4bc0  mov     ebx, eax
0x1800d4bc2  test    eax, eax
0x1800d4bc4  jle     short loc_1800D4BCF
0x1800d4bc6  movzx   ebx, ax
0x1800d4bc9  or      ebx, 80070000h
0x1800d4bcf  xor     edx, edx
0x1800d4bd1  lea     r8d, [rdx+8]
0x1800d4bd5  call    ControlNtDriver
0x1800d4bda  mov     rsi, r13
0x1800d4bdd  lea     rax, [rsi-1]
0x1800d4be1  mov     [r15+1298h], r13
0x1800d4be8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800d4bec  ja      short loc_1800D4BFD
0x1800d4bee  mov     rcx, rsi; hObject
0x1800d4bf1  call    cs:__imp_CloseHandle
0x1800d4bf8  nop     dword ptr [rax+rax+00h]
0x1800d4bfd  cmp     [rsp+68h+arg_8], r13d
0x1800d4c02  jnz     short loc_1800D4C2B
0x1800d4c04  inc     rbp
0x1800d4c07  cmp     [rdi+rbp*2], r13w
0x1800d4c0c  jnz     short loc_1800D4C04
0x1800d4c0e  test    rbp, rbp
0x1800d4c11  jnz     short loc_1800D4C18
0x1800d4c13  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800d4c18  mov     rcx, rdi; lpFileName
0x1800d4c1b  call    cs:__imp_DeleteFileW
0x1800d4c22  nop     dword ptr [rax+rax+00h]
0x1800d4c27  mov     [rdi], r13w
0x1800d4c2b  mov     eax, ebx
0x1800d4c2d  jmp     short loc_1800D4C31
0x1800d4c2f  xor     eax, eax
0x1800d4c31  lea     r11, [rsp+68h+var_28]
0x1800d4c36  mov     rbx, [r11+30h]
0x1800d4c3a  mov     rbp, [r11+48h]
0x1800d4c3e  mov     rsp, r11
0x1800d4c41  pop     r15
0x1800d4c43  pop     r14
0x1800d4c45  pop     r13
0x1800d4c47  pop     rdi
0x1800d4c48  pop     rsi
0x1800d4c49  retn
```
