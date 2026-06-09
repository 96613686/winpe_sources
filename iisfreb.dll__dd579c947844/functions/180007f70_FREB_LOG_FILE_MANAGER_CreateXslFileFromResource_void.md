# FREB_LOG_FILE_MANAGER::CreateXslFileFromResource(void)

- ea: `0x180007f70`
- end: `0x180008170`
- name: `?CreateXslFileFromResource@FREB_LOG_FILE_MANAGER@@AEAAJXZ`
- size: `512`
- prototype: `__int64 __fastcall(FREB_LOG_FILE_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180008548`

## callees

- `0x180007f70`
- `0x18000a4dc`
- `0x18000ac52`
- `0x18000ac90`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180008061`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180008061`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18000806f`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18000806f`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000804e`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000804e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008026`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008026`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008100`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008100`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800080cf`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800080cf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800080a5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800080a5`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x180008018`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x180008018`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008141`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008141`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007fc9`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007fc9`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007fdb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007fdb`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180007ff7`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180007ff7`

## pseudocode

```c
__int64 __fastcall FREB_LOG_FILE_MANAGER::CreateXslFileFromResource(FREB_LOG_FILE_MANAGER *this)
{
  int v2; // ebx
  HRSRC ResourceW; // rax
  HRSRC v4; // rdi
  signed int v5; // eax
  DWORD v6; // r14d
  HGLOBAL Resource; // rax
  const void *v8; // rsi
  HANDLE FileW; // rax
  void *v10; // rdi
  signed int LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v14[3]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v15[32]; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpFileName; // [rsp+80h] [rbp-80h]
  unsigned __int16 v17[264]; // [rsp+A0h] [rbp-60h] BYREF

  NumberOfBytesWritten = 0;
  memset_0(v17, 0, 0x208u);
  STRU::STRU((STRU *)v15, v17, 0x104u);
  v2 = STRU::Copy((STRU *)v15, *(const unsigned __int16 **)(*(_QWORD *)this + 48LL));
  if ( v2 < 0 )
    goto LABEL_16;
  v2 = STRU::Append((STRU *)v15, L"freb.xsl");
  if ( v2 < 0 )
    goto LABEL_16;
  ResourceW = FindResourceW(g_DllInstance, L"FREB_XSL_FILE", L"FREB_XSL_FILE");
  v4 = ResourceW;
  if ( ResourceW
    && (v6 = SizeofResource(g_DllInstance, ResourceW), (Resource = LoadResource(g_DllInstance, v4)) != 0)
    && (v8 = LockResource(Resource)) != 0
    && (FileW = CreateFileW(lpFileName, 0x40000000u, 0, 0, 1u, 0x80u, 0), v10 = FileW, FileW != (HANDLE)-1LL) )
  {
    if ( WriteFile(FileW, v8, v6, &NumberOfBytesWritten, 0) )
    {
      if ( NumberOfBytesWritten != v6 )
        v2 = -2147467259;
    }
    else
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseHandle(v10);
  }
  else
  {
    v5 = GetLastError();
    v2 = v5;
    if ( v5 > 0 )
      v2 = (unsigned __int16)v5 | 0x80070000;
  }
  if ( v2 < 0 )
  {
LABEL_16:
    v14[2] = (unsigned __int16 *)lpFileName;
    v14[0] = 0;
    v14[1] = 0;
    FREB_LOG_NT_EVENT_TABLE::LogEvent(0x800008F4, 3u, (const unsigned __int16 **const)v14, v2);
  }
  STRU::~STRU((STRU *)v15);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180007f70  mov     [rsp-8+arg_8], rbx
0x180007f75  mov     [rsp-8+arg_10], rsi
0x180007f7a  push    rbp
0x180007f7b  push    rdi
0x180007f7c  push    r14
0x180007f7e  lea     rbp, [rsp-1C0h]
0x180007f86  sub     rsp, 2C0h
0x180007f8d  mov     rax, cs:__security_cookie
0x180007f94  xor     rax, rsp
0x180007f97  mov     [rbp+1D0h+var_20], rax
0x180007f9e  mov     rbx, rcx
0x180007fa1  mov     [rsp+2D0h+NumberOfBytesWritten], 0
0x180007fa9  lea     rcx, [rbp+1D0h+var_230]; void *
0x180007fad  xor     edx, edx; Val
0x180007faf  mov     r8d, 208h; Size
0x180007fb5  call    memset_0
0x180007fba  mov     r8d, 104h
0x180007fc0  lea     rdx, [rbp+1D0h+var_230]
0x180007fc4  lea     rcx, [rsp+2D0h+var_270]
0x180007fc9  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180007fcf  mov     rdx, [rbx]
0x180007fd2  lea     rcx, [rsp+2D0h+var_270]
0x180007fd7  mov     rdx, [rdx+30h]
0x180007fdb  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180007fe1  mov     ebx, eax
0x180007fe3  test    eax, eax
0x180007fe5  js      loc_18000810A
0x180007feb  lea     rdx, aFrebXsl; "freb.xsl"
0x180007ff2  lea     rcx, [rsp+2D0h+var_270]
0x180007ff7  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180007ffd  mov     ebx, eax
0x180007fff  test    eax, eax
0x180008001  js      loc_18000810A
0x180008007  mov     rcx, cs:?g_DllInstance@@3PEAUHINSTANCE__@@EA; hModule
0x18000800e  lea     rdx, Name; "FREB_XSL_FILE"
0x180008015  mov     r8, rdx; lpType
0x180008018  call    cs:__imp_FindResourceW
0x18000801e  mov     rdi, rax
0x180008021  test    rax, rax
0x180008024  jnz     short loc_180008044
0x180008026  call    cs:__imp_GetLastError
0x18000802c  mov     ebx, eax
0x18000802e  test    eax, eax
0x180008030  jle     loc_180008106
0x180008036  movzx   ebx, ax
0x180008039  or      ebx, 80070000h
0x18000803f  jmp     loc_180008106
0x180008044  mov     rcx, cs:?g_DllInstance@@3PEAUHINSTANCE__@@EA; hModule
0x18000804b  mov     rdx, rdi; hResInfo
0x18000804e  call    cs:__imp_SizeofResource
0x180008054  mov     rcx, cs:?g_DllInstance@@3PEAUHINSTANCE__@@EA; hModule
0x18000805b  mov     rdx, rdi; hResInfo
0x18000805e  mov     r14d, eax
0x180008061  call    cs:__imp_LoadResource
0x180008067  test    rax, rax
0x18000806a  jz      short loc_180008026
0x18000806c  mov     rcx, rax; hResData
0x18000806f  call    cs:__imp_LockResource
0x180008075  mov     rsi, rax
0x180008078  test    rax, rax
0x18000807b  jz      short loc_180008026
0x18000807d  mov     rcx, [rbp+1D0h+lpFileName]; lpFileName
0x180008081  xor     r9d, r9d; lpSecurityAttributes
0x180008084  mov     [rsp+2D0h+hTemplateFile], 0; hTemplateFile
0x18000808d  xor     r8d, r8d; dwShareMode
0x180008090  mov     [rsp+2D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180008098  mov     edx, 40000000h; dwDesiredAccess
0x18000809d  mov     [rsp+2D0h+dwCreationDisposition], 1; dwCreationDisposition
0x1800080a5  call    cs:__imp_CreateFileW
0x1800080ab  mov     rdi, rax
0x1800080ae  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800080b2  jz      loc_180008026
0x1800080b8  lea     r9, [rsp+2D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800080bd  mov     qword ptr [rsp+2D0h+dwCreationDisposition], 0; lpOverlapped
0x1800080c6  mov     r8d, r14d; nNumberOfBytesToWrite
0x1800080c9  mov     rdx, rsi; lpBuffer
0x1800080cc  mov     rcx, rax; hFile
0x1800080cf  call    cs:__imp_WriteFile
0x1800080d5  test    eax, eax
0x1800080d7  jnz     short loc_1800080F0
0x1800080d9  call    cs:__imp_GetLastError
0x1800080df  mov     ebx, eax
0x1800080e1  test    eax, eax
0x1800080e3  jle     short loc_1800080FD
0x1800080e5  movzx   ebx, ax
0x1800080e8  or      ebx, 80070000h
0x1800080ee  jmp     short loc_1800080FD
0x1800080f0  cmp     [rsp+2D0h+NumberOfBytesWritten], r14d
0x1800080f5  mov     eax, 80004005h
0x1800080fa  cmovnz  ebx, eax
0x1800080fd  mov     rcx, rdi; hObject
0x180008100  call    cs:__imp_CloseHandle
0x180008106  test    ebx, ebx
0x180008108  jns     short loc_18000813C
0x18000810a  mov     rax, [rbp+1D0h+lpFileName]
0x18000810e  lea     r8, [rsp+2D0h+var_288]; unsigned __int16 **
0x180008113  mov     edx, 3; unsigned __int16
0x180008118  mov     [rsp+2D0h+var_278], rax
0x18000811d  mov     r9d, ebx; unsigned int
0x180008120  mov     [rsp+2D0h+var_288], 0
0x180008129  mov     ecx, 800008F4h; unsigned int
0x18000812e  mov     [rsp+2D0h+var_280], 0
0x180008137  call    ?LogEvent@FREB_LOG_NT_EVENT_TABLE@@SAXKGQEAPEBGK@Z; FREB_LOG_NT_EVENT_TABLE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18000813c  lea     rcx, [rsp+2D0h+var_270]
0x180008141  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180008147  mov     eax, ebx
0x180008149  mov     rcx, [rbp+1D0h+var_20]
0x180008150  xor     rcx, rsp; StackCookie
0x180008153  call    __security_check_cookie
0x180008158  lea     r11, [rsp+2D0h+var_10]
0x180008160  mov     rbx, [r11+28h]
0x180008164  mov     rsi, [r11+30h]
0x180008168  mov     rsp, r11
0x18000816b  pop     r14
0x18000816d  pop     rdi
0x18000816e  pop     rbp
0x18000816f  retn
```
