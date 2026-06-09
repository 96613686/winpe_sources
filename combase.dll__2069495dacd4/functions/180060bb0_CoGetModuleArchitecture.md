# CoGetModuleArchitecture

- ea: `0x180060bb0`
- end: `0x180061073`
- name: `CoGetModuleArchitecture`
- size: `1219`
- prototype: `HRESULT __fastcall(const wchar_t *pwszModule, unsigned int *pModuleArchitecture)`
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180060318`
- `0x180062788`
- `0x18011686c`
- `0x18015de18`
- `0x1801d9d70`

## callees

- `0x180060bb0`
- `0x180086038`
- `0x180087534`
- `0x18008db2c`
- `0x1801999b0`
- `0x180255010`

## import_xrefs

- `ntdll!RtlWow64GetEquivalentMachineCHPE` at `0x180060f63`
- `ntdll!RtlWow64GetEquivalentMachineCHPE` at `0x180060f63`
- `ntdll!RtlImageNtHeaderEx` at `0x180060f4c`
- `ntdll!RtlImageNtHeaderEx` at `0x180060f4c`
- `ntdll!RtlNtStatusToDosError` at `0x180060f7b`
- `ntdll!RtlNtStatusToDosError` at `0x180060f7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060c3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060d35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060d77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060df8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060e64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060ecc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060c3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060d35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060d77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060df8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060e64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060ecc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180060c23`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180060d1e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180060c23`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180060d1e`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180060dee`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180060dee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061017`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006102a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061017`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006102a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180061009`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180061009`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180060ebd`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180060ebd`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180060e52`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180060e52`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180060cef`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180060cef`

## string_xrefs

- `0x180060dd6`: `onecore\com\combase\catalog\class.cxx`
- `0x180060f23`: `onecore\com\combase\catalog\class.cxx`
- `0x180060fd5`: `onecore\com\combase\catalog\class.cxx`

## pseudocode

```c
__int64 __fastcall CoGetModuleArchitecture(wchar_t *pwszModule, unsigned int *pModuleArchitecture)
{
  void *v4; // r13
  wchar_t *lpBuffer; // rsi
  char *FileW; // r15
  void *v7; // rsp
  wchar_t *v8; // rax
  unsigned int v9; // edi
  signed int v10; // eax
  int v11; // r8d
  signed int LastError; // eax
  signed int v13; // eax
  HANDLE FileMappingW; // rax
  signed int v15; // eax
  void *v16; // rax
  signed int v17; // eax
  void *v18; // rcx
  int v19; // eax
  signed int v20; // eax
  char v22; // [rsp+20h] [rbp-220h] BYREF
  void *pBase; // [rsp+240h] [rbp+0h]
  HRESULT hr; // [rsp+24Ch] [rbp+Ch]
  _LARGE_INTEGER liFileSize; // [rsp+250h] [rbp+10h] BYREF
  _IMAGE_NT_HEADERS64 *pImage; // [rsp+258h] [rbp+18h] BYREF
  void *hFile; // [rsp+260h] [rbp+20h]
  wchar_t *pwszFullPath; // [rsp+268h] [rbp+28h]
  wchar_t *pszTmpFileName; // [rsp+270h] [rbp+30h] BYREF
  void *hFileMapping; // [rsp+278h] [rbp+38h]

  liFileSize.QuadPart = 0;
  *pModuleArchitecture = 0;
  if ( !pwszModule || *pwszModule == 34 )
    return 2147942487LL;
  v4 = 0;
  lpBuffer = 0;
  pwszFullPath = 0;
  FileW = (char *)CreateFileW(pwszModule, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
  hFile = FileW;
  if ( FileW != (char *)-1LL || GetLastError() != 2 )
    goto LABEL_18;
  pszTmpFileName = 0;
  if ( g_ulMaxStackAllocSize >= 0x20A && g_ulAdditionalProbeSize + 530 >= 0x20A )
  {
    if ( VerifyStackAvailable(g_ulAdditionalProbeSize + 530) )
    {
      v7 = alloca(544);
      lpBuffer = (wchar_t *)&v22;
    }
    if ( !lpBuffer )
      goto LABEL_12;
    *(_DWORD *)lpBuffer = 1801679955;
    lpBuffer += 4;
  }
  if ( !lpBuffer )
  {
LABEL_12:
    v8 = (wchar_t *)g_pfnAllocate(530u);
    lpBuffer = v8;
    if ( v8 )
    {
      *(_DWORD *)v8 = 1885431112;
      lpBuffer = v8 + 4;
    }
  }
  pwszFullPath = lpBuffer;
  if ( !lpBuffer )
  {
    v9 = -2147024882;
    goto LABEL_64;
  }
  if ( SearchPathW(0, pwszModule, 0, 0x104u, lpBuffer, &pszTmpFileName) - 1 > 0x103 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
      goto LABEL_64;
    v11 = 2262;
    goto LABEL_31;
  }
  FileW = (char *)CreateFileW(lpBuffer, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
  hFile = FileW;
LABEL_18:
  if ( FileW == (char *)-1LL )
  {
    v10 = GetLastError();
    v9 = v10;
    if ( v10 > 0 )
      v9 = (unsigned __int16)v10 | 0x80070000;
    if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
      goto LABEL_64;
    v11 = 2280;
    goto LABEL_31;
  }
  if ( !GetFileSizeEx(FileW, &liFileSize) )
  {
    v13 = GetLastError();
    v9 = v13;
    if ( v13 > 0 )
      v9 = (unsigned __int16)v13 | 0x80070000;
    if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
      goto LABEL_64;
    v11 = 2286;
    goto LABEL_31;
  }
  FileMappingW = CreateFileMappingW(FileW, 0, 2u, 0, 0, 0);
  v4 = FileMappingW;
  hFileMapping = FileMappingW;
  if ( FileMappingW )
  {
    v9 = 0;
    v16 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
    pBase = v16;
    if ( v16 )
    {
      pImage = 0;
      v19 = RtlImageNtHeaderEx(2u, v16, liFileSize.QuadPart, &pImage);
      if ( v19 >= 0 && pImage )
      {
        *pModuleArchitecture = (unsigned __int16)RtlWow64GetEquivalentMachineCHPE(pImage->FileHeader.Machine);
        v18 = pBase;
      }
      else
      {
        v20 = RtlNtStatusToDosError(v19);
        v9 = v20;
        if ( v20 > 0 )
          v9 = (unsigned __int16)v20 | 0x80070000;
        hr = v9;
        if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
          ComTraceMessageT<unsigned short *,long>(
            "onecore\\com\\combase\\catalog\\class.cxx",
            "CoGetModuleArchitecture",
            2321,
            ERRORS,
            L"Module:%ws %!HRESULT!",
            pwszModule,
            v9);
        v18 = pBase;
      }
    }
    else
    {
      v17 = GetLastError();
      v9 = v17;
      if ( v17 > 0 )
        v9 = (unsigned __int16)v17 | 0x80070000;
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        ComTraceMessageT<unsigned short *,long>(
          "onecore\\com\\combase\\catalog\\class.cxx",
          "CoGetModuleArchitecture",
          2310,
          ERRORS,
          L"Module:%ws %!HRESULT!",
          pwszModule,
          v9);
      v18 = pBase;
    }
    goto $Cleanup_1;
  }
  v15 = GetLastError();
  v9 = v15;
  if ( v15 > 0 )
    v9 = (unsigned __int16)v15 | 0x80070000;
  if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
  {
    v11 = 2302;
LABEL_31:
    ComTraceMessageT<unsigned short *,long>(
      "onecore\\com\\combase\\catalog\\class.cxx",
      "CoGetModuleArchitecture",
      v11,
      ERRORS,
      L"Module:%ws %!HRESULT!",
      pwszModule,
      v9);
  }
LABEL_64:
  v18 = 0;
$Cleanup_1:
  if ( v18 )
    UnmapViewOfFile(v18);
  if ( v4 )
    CloseHandle(v4);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  if ( lpBuffer )
  {
    if ( *((_DWORD *)lpBuffer - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  return v9;
}

```

## disassembly

```asm
0x180060bb0  push    rbp
0x180060bb2  push    rbx
0x180060bb3  push    rsi
0x180060bb4  push    rdi
0x180060bb5  push    r12
0x180060bb7  push    r13
0x180060bb9  push    r14
0x180060bbb  push    r15
0x180060bbd  sub     rsp, 98h
0x180060bc4  lea     rbp, [rsp+40h]
0x180060bc9  mov     rax, cs:__security_cookie
0x180060bd0  xor     rax, rbp
0x180060bd3  mov     [rbp+90h+var_50], rax
0x180060bd7  mov     r12, pModuleArchitecture
0x180060bda  mov     r14, pwszModule
0x180060bdd  xor     ebx, ebx
0x180060bdf  mov     qword ptr [rbp+90h+liFileSize], rbx
0x180060be3  mov     [pModuleArchitecture], ebx
0x180060be5  test    pwszModule, pwszModule
0x180060be8  jz      loc_180061051
0x180060bee  cmp     word ptr [pwszModule], 22h ; '"'
0x180060bf2  jz      loc_180061051
0x180060bf8  mov     r13d, ebx
0x180060bfb  mov     esi, ebx
0x180060bfd  mov     [rbp+90h+pwszFullPath], rbx
0x180060c01  mov     [rsp+0D0h+hTemplateFile], rbx; hTemplateFile
0x180060c06  mov     edi, 8000000h
0x180060c0b  mov     [rsp+0D0h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x180060c0f  mov     [rsp+0D0h+dwCreationDisposition], 3; dwCreationDisposition
0x180060c17  xor     r9d, r9d; lpSecurityAttributes
0x180060c1a  mov     edx, 80000000h; dwDesiredAccess
0x180060c1f  lea     r8d, [rbx+1]; dwShareMode
0x180060c23  call    cs:__imp_CreateFileW
0x180060c29  mov     r15, rax
0x180060c2c  mov     [rbp+90h+hFile], rax
0x180060c30  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180060c34  jnz     loc_180060D2B
0x180060c3a  call    cs:__imp_GetLastError
0x180060c40  cmp     eax, 2
0x180060c43  jnz     loc_180060D2B
0x180060c49  mov     [rbp+90h+pszTmpFileName], rbx
0x180060c4d  mov     edx, 20Ah
0x180060c52  cmp     cs:g_ulMaxStackAllocSize, pModuleArchitecture
0x180060c59  jb      short loc_180060C98
0x180060c5b  mov     pwszModule, cs:g_ulAdditionalProbeSize
0x180060c62  add     pwszModule, 212h; Size
0x180060c69  cmp     pwszModule, pModuleArchitecture
0x180060c6c  jb      short loc_180060C98
0x180060c6e  call    VerifyStackAvailable
0x180060c73  test    eax, eax
0x180060c75  jz      short loc_180060C89
0x180060c77  mov     eax, [rsp+0D0h+var_D0]
0x180060c7a  mov     eax, 220h
0x180060c7f  sub     rsp, rax
0x180060c82  lea     rsi, [rsp+2F0h+var_2B0]
0x180060c87  mov     eax, [rsi]
0x180060c89  test    rsi, rsi
0x180060c8c  jz      short loc_180060C9D
0x180060c8e  mov     dword ptr [rsi], 6B637453h
0x180060c94  add     rsi, 8
0x180060c98  test    rsi, rsi
0x180060c9b  jnz     short loc_180060CC0
0x180060c9d  mov     ecx, 212h
0x180060ca2  mov     rax, cs:g_pfnAllocate
0x180060ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060cae  mov     rsi, rax
0x180060cb1  test    rax, rax
0x180060cb4  jz      short loc_180060CC0
0x180060cb6  mov     dword ptr [rax], 70616548h
0x180060cbc  add     rsi, 8
0x180060cc0  mov     [rbp+90h+pwszFullPath], rsi
0x180060cc4  test    rsi, rsi
0x180060cc7  jnz     short loc_180060CD3
0x180060cc9  mov     edi, 8007000Eh
0x180060cce  jmp     loc_180061001
0x180060cd3  lea     rax, [rbp+90h+pszTmpFileName]
0x180060cd7  mov     [rsp+2F0h+lpFilePart], rax; lpFilePart
0x180060cdc  mov     [rsp+2F0h+lpBuffer], rsi; lpBuffer
0x180060ce1  mov     r9d, 104h; nBufferLength
0x180060ce7  xor     r8d, r8d; lpExtension
0x180060cea  mov     pModuleArchitecture, r14; lpFileName
0x180060ced  xor     ecx, ecx; lpPath
0x180060cef  call    cs:__imp_SearchPathW
0x180060cf5  dec     eax
0x180060cf7  cmp     eax, 103h
0x180060cfc  ja      short loc_180060D77
0x180060cfe  mov     [rsp+2F0h+var_2C0], rbx; hTemplateFile
0x180060d03  mov     dword ptr [rsp+2F0h+lpFilePart], edi; dwFlagsAndAttributes
0x180060d07  mov     dword ptr [rsp+2F0h+lpBuffer], 3; dwCreationDisposition
0x180060d0f  xor     r9d, r9d; lpSecurityAttributes
0x180060d12  mov     edx, 80000000h; dwDesiredAccess
0x180060d17  lea     r8d, [r9+1]; dwShareMode
0x180060d1b  mov     pwszModule, rsi; lpFileName
0x180060d1e  call    cs:__imp_CreateFileW
0x180060d24  mov     r15, rax
0x180060d27  mov     [rbp+90h+hFile], rax
0x180060d2b  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x180060d2f  jnz     loc_180060DE7
0x180060d35  call    cs:__imp_GetLastError
0x180060d3b  mov     edi, eax
0x180060d3d  test    eax, eax
0x180060d3f  jle     short loc_180060D4A
0x180060d41  movzx   edi, ax
0x180060d44  or      edi, 80070000h
0x180060d4a  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180060d50  test    eax, eax
0x180060d52  jnz     short loc_180060D6F
0x180060d54  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x180060d5a  jz      loc_180061001
0x180060d60  xor     ecx, ecx; level
0x180060d62  call    IsWppLevelEnabled
0x180060d67  test    al, al
0x180060d69  jz      loc_180061001
0x180060d6f  mov     r8d, 8E8h
0x180060d75  jmp     short loc_180060DB7
0x180060d77  call    cs:__imp_GetLastError
0x180060d7d  mov     edi, eax
0x180060d7f  test    eax, eax
0x180060d81  jle     short loc_180060D8C
0x180060d83  movzx   edi, ax
0x180060d86  or      edi, 80070000h
0x180060d8c  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180060d92  test    eax, eax
0x180060d94  jnz     short loc_180060DB1
0x180060d96  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x180060d9c  jz      loc_180061001
0x180060da2  xor     ecx, ecx; level
0x180060da4  call    IsWppLevelEnabled
0x180060da9  test    al, al
0x180060dab  jz      loc_180061001
0x180060db1  mov     r8d, 8D6h; line
0x180060db7  mov     dword ptr [rsp+2F0h+var_2C0], edi; <args_1>
0x180060dbb  mov     [rsp+2F0h+lpFilePart], r14; <args_0>
0x180060dc0  lea     rax, aModuleWsHresul; "Module:%ws %!HRESULT!"
0x180060dc7  xor     r9d, r9d; level
0x180060dca  mov     [rsp+2F0h+lpBuffer], rax; format
0x180060dcf  lea     pModuleArchitecture, aCogetmodulearc_0; "CoGetModuleArchitecture"
0x180060dd6  lea     pwszModule, aOnecoreComComb_119; "onecore\\com\\combase\\catalog\\class.c"...
0x180060ddd  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x180060de2  jmp     loc_180061001
0x180060de7  lea     pModuleArchitecture, [rbp+90h+liFileSize]; lpFileSize
0x180060deb  mov     pwszModule, r15; hFile
0x180060dee  call    cs:__imp_GetFileSizeEx
0x180060df4  test    eax, eax
0x180060df6  jnz     short loc_180060E3D
0x180060df8  call    cs:__imp_GetLastError
0x180060dfe  mov     edi, eax
0x180060e00  test    eax, eax
0x180060e02  jle     short loc_180060E0D
0x180060e04  movzx   edi, ax
0x180060e07  or      edi, 80070000h
0x180060e0d  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180060e13  test    eax, eax
0x180060e15  jnz     short loc_180060E32
0x180060e17  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x180060e1d  jz      loc_180061001
0x180060e23  xor     ecx, ecx; level
0x180060e25  call    IsWppLevelEnabled
0x180060e2a  test    al, al
0x180060e2c  jz      loc_180061001
0x180060e32  mov     r8d, 8EEh
0x180060e38  jmp     loc_180060DB7
0x180060e3d  mov     [rsp+2F0h+lpFilePart], rbx; lpName
0x180060e42  mov     dword ptr [rsp+2F0h+lpBuffer], ebx; dwMaximumSizeLow
0x180060e46  xor     r9d, r9d; dwMaximumSizeHigh
0x180060e49  xor     edx, edx; lpFileMappingAttributes
0x180060e4b  lea     r8d, [r9+2]; flProtect
0x180060e4f  mov     pwszModule, r15; hFile
0x180060e52  call    cs:__imp_CreateFileMappingW
0x180060e58  mov     r13, rax
0x180060e5b  mov     [rbp+90h+hFileMapping], rax
0x180060e5f  test    rax, rax
0x180060e62  jnz     short loc_180060EA9
0x180060e64  call    cs:__imp_GetLastError
0x180060e6a  mov     edi, eax
0x180060e6c  test    eax, eax
0x180060e6e  jle     short loc_180060E79
0x180060e70  movzx   edi, ax
0x180060e73  or      edi, 80070000h
0x180060e79  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180060e7f  test    eax, eax
0x180060e81  jnz     short loc_180060E9E
0x180060e83  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x180060e89  jz      loc_180061001
0x180060e8f  xor     ecx, ecx; level
0x180060e91  call    IsWppLevelEnabled
0x180060e96  test    al, al
0x180060e98  jz      loc_180061001
0x180060e9e  mov     r8d, 8FEh
0x180060ea4  jmp     loc_180060DB7
0x180060ea9  mov     edi, ebx
0x180060eab  mov     [rsp+2F0h+lpBuffer], rbx; dwNumberOfBytesToMap
0x180060eb0  xor     r9d, r9d; dwFileOffsetLow
0x180060eb3  xor     r8d, r8d; dwFileOffsetHigh
0x180060eb6  lea     edx, [r9+4]; dwDesiredAccess
0x180060eba  mov     pwszModule, rax; hFileMappingObject
0x180060ebd  call    cs:__imp_MapViewOfFile
0x180060ec3  mov     [rbp+90h+pBase], rax
0x180060ec7  test    rax, rax
0x180060eca  jnz     short loc_180060F38
0x180060ecc  call    cs:__imp_GetLastError
0x180060ed2  mov     edi, eax
0x180060ed4  test    eax, eax
0x180060ed6  jle     short loc_180060EE1
0x180060ed8  movzx   edi, ax
0x180060edb  or      edi, 80070000h
0x180060ee1  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180060ee7  test    eax, eax
0x180060ee9  jnz     short loc_180060EFE
0x180060eeb  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x180060ef1  jz      short loc_180060F2F
0x180060ef3  xor     ecx, ecx; level
0x180060ef5  call    IsWppLevelEnabled
0x180060efa  test    al, al
0x180060efc  jz      short loc_180060F2F
0x180060efe  mov     dword ptr [rsp+2F0h+var_2C0], edi; <args_1>
0x180060f02  mov     [rsp+2F0h+lpFilePart], r14; <args_0>
0x180060f07  lea     rax, aModuleWsHresul; "Module:%ws %!HRESULT!"
0x180060f0e  mov     [rsp+2F0h+lpBuffer], rax; format
0x180060f13  xor     r9d, r9d; level
0x180060f16  mov     r8d, 906h; line
0x180060f1c  lea     pModuleArchitecture, aCogetmodulearc_0; "CoGetModuleArchitecture"
0x180060f23  lea     pwszModule, aOnecoreComComb_119; "onecore\\com\\combase\\catalog\\class.c"...
0x180060f2a  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x180060f2f  mov     pwszModule, [rbp+90h+pBase]
0x180060f33  jmp     $Cleanup_1
0x180060f38  mov     [rbp+90h+pImage], rbx
0x180060f3c  lea     r9, [rbp+90h+pImage]; NtHeader
0x180060f40  mov     r8, qword ptr [rbp+90h+liFileSize]; Size
0x180060f44  mov     pModuleArchitecture, rax; BaseAddress
0x180060f47  mov     ecx, 2; Flags
0x180060f4c  call    cs:__imp_RtlImageNtHeaderEx
0x180060f52  test    eax, eax
0x180060f54  js      short loc_180060F79
0x180060f56  mov     pwszModule, [rbp+90h+pImage]
0x180060f5a  test    pwszModule, pwszModule
0x180060f5d  jz      short loc_180060F79
0x180060f5f  movzx   ecx, word ptr [pwszModule+4]
0x180060f63  call    cs:__imp_RtlWow64GetEquivalentMachineCHPE
0x180060f69  movzx   eax, ax
0x180060f6c  mov     [r12], eax
0x180060f70  mov     pwszModule, [rbp+90h+pBase]
0x180060f74  jmp     $Cleanup_1
0x180060f79  mov     ecx, eax; Status
0x180060f7b  call    cs:__imp_RtlNtStatusToDosError
0x180060f81  mov     edi, eax
0x180060f83  test    eax, eax
0x180060f85  jle     short loc_180060F90
0x180060f87  movzx   edi, ax
0x180060f8a  or      edi, 80070000h
0x180060f90  mov     [rbp+90h+hr], edi
0x180060f93  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180060f99  test    eax, eax
0x180060f9b  jnz     short loc_180060FB0
0x180060f9d  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x180060fa3  jz      short loc_180060FE1
0x180060fa5  xor     ecx, ecx; level
0x180060fa7  call    IsWppLevelEnabled
0x180060fac  test    al, al
0x180060fae  jz      short loc_180060FE1
0x180060fb0  mov     dword ptr [rsp+2F0h+var_2C0], edi; <args_1>
0x180060fb4  mov     [rsp+2F0h+lpFilePart], r14; <args_0>
0x180060fb9  lea     rax, aModuleWsHresul; "Module:%ws %!HRESULT!"
0x180060fc0  mov     [rsp+2F0h+lpBuffer], rax; format
0x180060fc5  xor     r9d, r9d; level
0x180060fc8  mov     r8d, 911h; line
0x180060fce  lea     pModuleArchitecture, aCogetmodulearc_0; "CoGetModuleArchitecture"
0x180060fd5  lea     pwszModule, aOnecoreComComb_119; "onecore\\com\\combase\\catalog\\class.c"...
0x180060fdc  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x180060fe1  mov     pwszModule, [rbp+90h+pBase]
0x180060fe5  jmp     short $Cleanup_1
0x180060fe7  mov     edi, 800703E7h
0x180060fec  mov     [rbp+90h+hr], edi
0x180060fef  mov     r15, [rbp+90h+hFile]
0x180060ff3  mov     r13, [rbp+90h+hFileMapping]
0x180060ff7  mov     rsi, [rbp+90h+pwszFullPath]
0x180060ffb  mov     pwszModule, [rbp+90h+pBase]
0x180060fff  jmp     short $Cleanup_1
0x180061001  mov     pwszModule, rbx; lpBaseAddress
0x180061004  test    pwszModule, pwszModule
0x180061007  jz      short loc_18006100F
0x180061009  call    cs:__imp_UnmapViewOfFile
0x18006100f  test    r13, r13
0x180061012  jz      short loc_18006101D
0x180061014  mov     pwszModule, r13; hObject
0x180061017  call    cs:__imp_CloseHandle
0x18006101d  lea     rax, [r15-1]
0x180061021  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180061025  ja      short loc_180061030
0x180061027  mov     pwszModule, r15; hObject
0x18006102a  call    cs:__imp_CloseHandle
0x180061030  test    rsi, rsi
0x180061033  jz      short loc_18006104D
0x180061035  lea     pwszModule, [rsi-8]
0x180061039  cmp     dword ptr [pwszModule], 70616548h
0x18006103f  jnz     short loc_18006104D
0x180061041  mov     rax, cs:g_pfnFree
0x180061048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006104d  mov     eax, edi
0x18006104f  jmp     short loc_180061056
  ... truncated ...
```
