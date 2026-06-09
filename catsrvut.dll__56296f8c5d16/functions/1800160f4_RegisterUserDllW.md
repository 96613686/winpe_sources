# RegisterUserDllW

- ea: `0x1800160f4`
- end: `0x180016253`
- name: `RegisterUserDllW`
- size: `351`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR *, const WCHAR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000eaf8`

## callees

- `0x1800160f4`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016187`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016187`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016131`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016131`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016149`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016149`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180016240`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180016240`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180016116`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180016116`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001615d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001621d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001615d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001621d`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180016122`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180016178`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180016122`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180016178`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800161ec`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800161ec`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x1800161c3`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x1800161c3`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180016211`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180016211`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001623a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001623a`

## string_xrefs

- `0x18001613f`: `DllRegisterServer`

## pseudocode

```c
__int64 __fastcall RegisterUserDllW(__int64 a1, __int64 a2, const WCHAR *a3, const WCHAR *a4)
{
  signed int v5; // ebx
  HMODULE Library; // rax
  HMODULE v7; // rdi
  __int64 (*ProcAddress)(void); // rax
  signed int LastError; // eax
  signed int v10; // eax
  HANDLE v11; // rax
  void *v12; // rdi
  _DWORD *v13; // rax
  signed int v14; // eax
  int v16; // eax
  _DWORD *v17; // [rsp+40h] [rbp+8h]
  HANDLE v18; // [rsp+48h] [rbp+10h]
  signed int v20; // [rsp+60h] [rbp+28h]

  v5 = 0;
  CoInitializeEx(0, 2u);
  try
  {
    SetErrorMode(0x8001u);
    Library = LoadLibraryExW(a3, 0, 8u);
    v7 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "DllRegisterServer");
      if ( ProcAddress )
      {
        v5 = ProcAddress();
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    v20 = v5;
    SetErrorMode(0);
  }
  catch ( ... )
  {
    goto LABEL_9;
  }
  if ( v7 )
  {
    try
    {
      FreeLibrary(v7);
    }
    catch ( ... )
    {
      v5 = v20;
    }
  }
  else
  {
LABEL_9:
    v10 = GetLastError();
    v5 = v10;
    if ( v10 > 0 )
      v5 = (unsigned __int16)v10 | 0x80070000;
    if ( !v5 )
      v5 = -2147467259;
  }
  v11 = OpenFileMappingW(2u, 0, a4);
  v12 = v11;
  v18 = v11;
  if ( v11 )
  {
    v13 = MapViewOfFile(v11, 2u, 0, 0, 8u);
    v17 = v13;
    if ( v13 )
    {
      try
      {
        *v13 = v5;
      }
      catch ( ... )
      {
        v16 = v5;
        if ( v5 >= 0 )
          v16 = -2147467259;
        v12 = v18;
        v5 = v16;
        v13 = v17;
      }
      UnmapViewOfFile(v13);
LABEL_21:
      CloseHandle(v12);
      goto LABEL_22;
    }
  }
  if ( v5 >= 0 )
  {
    v14 = GetLastError();
    v5 = v14;
    if ( v14 > 0 )
      v5 = (unsigned __int16)v14 | 0x80070000;
  }
  if ( v12 )
    goto LABEL_21;
LABEL_22:
  CoUninitialize();
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800160f4  mov     rax, rsp
0x1800160f7  mov     [rax+18h], rbx
0x1800160fb  mov     [rax+20h], r9
0x1800160ff  mov     [rax+10h], rdx
0x180016103  mov     [rax+8], rcx
0x180016107  push    rdi
0x180016108  sub     rsp, 30h
0x18001610c  mov     rdi, r8
0x18001610f  xor     ebx, ebx
0x180016111  lea     edx, [rbx+2]; dwCoInit
0x180016114  xor     ecx, ecx; pvReserved
0x180016116  call    cs:__imp_CoInitializeEx
0x18001611c  nop
0x18001611d  mov     ecx, 8001h; uMode
0x180016122  call    cs:__imp_SetErrorMode
0x180016128  xor     edx, edx; hFile
0x18001612a  lea     r8d, [rbx+8]; dwFlags
0x18001612e  mov     rcx, rdi; lpLibFileName
0x180016131  call    cs:__imp_LoadLibraryExW
0x180016137  mov     rdi, rax
0x18001613a  test    rax, rax
0x18001613d  jz      short loc_180016172
0x18001613f  lea     rdx, aDllregisterser_0; "DllRegisterServer"
0x180016146  mov     rcx, rax; hModule
0x180016149  call    cs:__imp_GetProcAddress
0x18001614f  test    rax, rax
0x180016152  jz      short loc_18001615D
0x180016154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016159  mov     ebx, eax
0x18001615b  jmp     short loc_180016172
0x18001615d  call    cs:__imp_GetLastError
0x180016163  mov     ebx, eax
0x180016165  test    eax, eax
0x180016167  jle     short loc_180016172
0x180016169  movzx   ebx, ax
0x18001616c  or      ebx, 80070000h
0x180016172  mov     [rsp+38h+arg_20], ebx
0x180016176  xor     ecx, ecx; uMode
0x180016178  call    cs:__imp_SetErrorMode
0x18001617e  nop
0x18001617f  test    rdi, rdi
0x180016182  jz      short loc_180016196
0x180016184  mov     rcx, rdi; hLibModule
0x180016187  call    cs:__imp_FreeLibrary
0x18001618d  nop
0x18001618e  jmp     short loc_1800161B5
0x180016190  mov     ebx, [rsp+38h+arg_20]
0x180016194  jmp     short loc_1800161B5
0x180016196  call    cs:__imp_GetLastError
0x18001619c  mov     ebx, eax
0x18001619e  test    eax, eax
0x1800161a0  jle     short loc_1800161AB
0x1800161a2  movzx   ebx, ax
0x1800161a5  or      ebx, 80070000h
0x1800161ab  mov     eax, 80004005h
0x1800161b0  test    ebx, ebx
0x1800161b2  cmovz   ebx, eax
0x1800161b5  mov     [rsp+38h+arg_20], ebx
0x1800161b9  mov     r8, [rsp+38h+lpName]; lpName
0x1800161be  xor     edx, edx; bInheritHandle
0x1800161c0  lea     ecx, [rdx+2]; dwDesiredAccess
0x1800161c3  call    cs:__imp_OpenFileMappingW
0x1800161c9  mov     rdi, rax
0x1800161cc  mov     [rsp+38h+arg_8], rax
0x1800161d1  test    rax, rax
0x1800161d4  jz      short loc_180016219
0x1800161d6  mov     [rsp+38h+dwNumberOfBytesToMap], 8; dwNumberOfBytesToMap
0x1800161df  xor     r9d, r9d; dwFileOffsetLow
0x1800161e2  xor     r8d, r8d; dwFileOffsetHigh
0x1800161e5  lea     edx, [r9+2]; dwDesiredAccess
0x1800161e9  mov     rcx, rax; hFileMappingObject
0x1800161ec  call    cs:__imp_MapViewOfFile
0x1800161f2  mov     [rsp+38h+arg_0], rax
0x1800161f7  test    rax, rax
0x1800161fa  jz      short loc_180016219
0x1800161fc  mov     [rax], ebx
0x1800161fe  jmp     short loc_18001620E
0x180016200  mov     rdi, [rsp+38h+arg_8]
0x180016205  mov     ebx, [rsp+38h+arg_20]
0x180016209  mov     rax, [rsp+38h+arg_0]
0x18001620e  mov     rcx, rax; lpBaseAddress
0x180016211  call    cs:__imp_UnmapViewOfFile
0x180016217  jmp     short loc_180016237
0x180016219  test    ebx, ebx
0x18001621b  js      short loc_180016232
0x18001621d  call    cs:__imp_GetLastError
0x180016223  mov     ebx, eax
0x180016225  test    eax, eax
0x180016227  jle     short loc_180016232
0x180016229  movzx   ebx, ax
0x18001622c  or      ebx, 80070000h
0x180016232  test    rdi, rdi
0x180016235  jz      short loc_180016240
0x180016237  mov     rcx, rdi; hObject
0x18001623a  call    cs:__imp_CloseHandle
0x180016240  call    cs:__imp_CoUninitialize
0x180016246  mov     eax, ebx
0x180016248  mov     rbx, [rsp+38h+arg_10]
0x18001624d  add     rsp, 30h
0x180016251  pop     rdi
0x180016252  retn
```
