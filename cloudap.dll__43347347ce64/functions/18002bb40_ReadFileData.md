# ReadFileData

- ea: `0x18002bb40`
- end: `0x18002be87`
- name: `ReadFileData`
- size: `839`
- prototype: `__int64 __fastcall(__int64, __int64, WCHAR *, WCHAR *, _QWORD *, DWORD *, LPFILETIME lpLastWriteTime)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18000fb70`
- `0x18002b9a4`
- `0x18005c464`

## callees

- `0x180006fa0`
- `0x180007fc0`
- `0x18000a600`
- `0x18002bb40`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002be26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002be26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bc72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bc72`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002bc26`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002bc26`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18002bcfb`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18002bcfb`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18002bbcb`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18002bbcb`

## string_xrefs

- `0x18002bc99`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18002bd1e`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18002bd80`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18002bdb4`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18002bded`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18002be3b`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18002be56`: `ReadFile`

## pseudocode

```c
__int64 __fastcall ReadFileData(
        __int64 a1,
        __int64 a2,
        WCHAR *a3,
        WCHAR *a4,
        _QWORD *a5,
        DWORD *a6,
        LPFILETIME lpLastWriteTime)
{
  void *v7; // rbx
  unsigned int File; // eax
  HANDLE v9; // rdi
  unsigned int v10; // esi
  DWORD LowPart; // r12d
  void *v12; // rax
  DWORD v13; // eax
  const UCHAR *v15; // r9
  char v16; // al
  const UCHAR *v17; // rdx
  bool v18; // zf
  signed int v19; // eax
  const char *v20; // r9
  signed int LastError; // eax
  const char *v22; // rax
  int v23; // r8d
  const char *v24; // r9
  signed int v25; // eax
  const char *v26; // r9
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-68h]
  LPOVERLAPPED lpOverlappeda; // [rsp+20h] [rbp-68h]
  const char *v29; // [rsp+28h] [rbp-60h]
  __int64 v30; // [rsp+30h] [rbp-58h]
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-48h] BYREF
  _LARGE_INTEGER FileSize; // [rsp+48h] [rbp-40h] BYREF
  HANDLE hFile[2]; // [rsp+50h] [rbp-38h] BYREF

  v7 = 0;
  FileSize.QuadPart = 0;
  NumberOfBytesRead = 0;
  hFile[0] = (HANDLE)-1LL;
  *a5 = 0;
  *a6 = 0;
  if ( lpLastWriteTime )
    *lpLastWriteTime = 0;
  File = GetFile(a1, a2, a3, a4, 1, 0, hFile);
  v9 = hFile[0];
  v10 = File;
  if ( File )
  {
    v15 = "";
    while ( 1 )
    {
      v16 = *(v15 - 1);
      v17 = v15--;
      v18 = v16 == 92;
      if ( v16 == 92 )
        break;
      if ( v15 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
      {
        v18 = v16 == 92;
        break;
      }
    }
    if ( v18 )
      v15 = v17;
    v29 = "GetFile";
    LODWORD(lpOverlapped) = 2109;
    goto LABEL_22;
  }
  if ( !GetFileSizeEx(hFile[0], &FileSize) )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0xC0070000;
    v15 = (const UCHAR *)_DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    v29 = "GetFileSizeEx";
    LODWORD(lpOverlapped) = 2115;
LABEL_22:
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v10, v15, lpOverlapped, v29, &Class);
    goto LABEL_10;
  }
  if ( FileSize.HighPart )
  {
    v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    LODWORD(v30) = v23;
    v10 = -1073282849;
    LODWORD(lpOverlapped) = 2122;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%u", 3221684447LL, v22, lpOverlapped, "Large File", v30);
  }
  else
  {
    LowPart = FileSize.LowPart;
    v12 = (void *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(FileSize.LowPart);
    v7 = v12;
    if ( v12 )
    {
      if ( ReadFile(v9, v12, LowPart, &NumberOfBytesRead, 0) )
      {
        if ( !lpLastWriteTime || GetFileTime(v9, 0, 0, lpLastWriteTime) )
        {
          v13 = NumberOfBytesRead;
          *a5 = v7;
          v7 = 0;
          *a6 = v13;
        }
        else
        {
          v19 = GetLastError();
          v10 = v19;
          if ( v19 > 0 )
            v10 = (unsigned __int16)v19 | 0xC0070000;
          v20 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
          LODWORD(lpOverlappeda) = 2155;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v10, v20, lpOverlappeda, "GetFileTime", &Class);
        }
      }
      else
      {
        v25 = GetLastError();
        v10 = v25;
        if ( v25 > 0 )
          v10 = (unsigned __int16)v25 | 0xC0070000;
        v26 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        LODWORD(lpOverlappeda) = 2142;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v10, v26, lpOverlappeda, "ReadFile", &Class);
      }
    }
    else
    {
      v10 = -1073741801;
      v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      LODWORD(lpOverlapped) = 2130;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v24, lpOverlapped, "AllocateLsaHeap", &Class);
    }
  }
LABEL_10:
  if ( v9 != (HANDLE)-1LL )
    CloseHandle(v9);
  if ( v7 )
    ((void (__fastcall *)(void *))g_pLsaFunctionTable->FreeLsaHeap)(v7);
  return v10;
}

```

## disassembly

```asm
0x18002bb40  mov     rax, rsp
0x18002bb43  push    rbx
0x18002bb44  push    rsi
0x18002bb45  sub     rsp, 78h
0x18002bb49  mov     [rax+8], rbp
0x18002bb4d  mov     rbp, [rsp+88h+arg_28]
0x18002bb55  mov     [rax+10h], rdi
0x18002bb59  mov     [rax-18h], r13
0x18002bb5d  xor     r13d, r13d
0x18002bb60  mov     [rax-20h], r14
0x18002bb64  mov     ebx, r13d
0x18002bb67  mov     r14, [rsp+88h+lpLastWriteTime]
0x18002bb6f  mov     [rax-28h], r15
0x18002bb73  mov     r15, [rsp+88h+arg_20]
0x18002bb7b  mov     [rax-40h], r13
0x18002bb7f  mov     [rax-48h], r13d
0x18002bb83  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFFh
0x18002bb8b  mov     [r15], r13
0x18002bb8e  mov     [rbp+0], r13d
0x18002bb92  test    r14, r14
0x18002bb95  jnz     loc_18002BD63
0x18002bb9b  lea     rax, [rsp+88h+hFile]
0x18002bba0  mov     [rsp+88h+var_58], rax
0x18002bba5  mov     [rsp+88h+var_60], r13
0x18002bbaa  mov     byte ptr [rsp+88h+lpOverlapped], 1
0x18002bbaf  call    GetFile
0x18002bbb4  mov     rdi, [rsp+88h+hFile]
0x18002bbb9  mov     esi, eax
0x18002bbbb  test    eax, eax
0x18002bbbd  jnz     loc_18002BC92
0x18002bbc3  lea     rdx, [rsp+88h+FileSize]; lpFileSize
0x18002bbc8  mov     rcx, rdi; hFile
0x18002bbcb  call    cs:__imp_GetFileSizeEx
0x18002bbd1  test    eax, eax
0x18002bbd3  jz      loc_18002BD6B
0x18002bbd9  mov     r8d, dword ptr [rsp+88h+FileSize+4]
0x18002bbde  test    r8d, r8d
0x18002bbe1  jnz     loc_18002BDB4
0x18002bbe7  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18002bbee  mov     [rsp+88h+arg_10], r12
0x18002bbf6  mov     r12d, dword ptr [rsp+88h+FileSize]
0x18002bbfb  mov     ecx, r12d
0x18002bbfe  mov     rax, [rax+28h]
0x18002bc02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc07  mov     rbx, rax
0x18002bc0a  test    rax, rax
0x18002bc0d  jz      loc_18002BDED
0x18002bc13  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002bc18  mov     [rsp+88h+lpOverlapped], r13; lpOverlapped
0x18002bc1d  mov     r8d, r12d; nNumberOfBytesToRead
0x18002bc20  mov     rdx, rax; lpBuffer
0x18002bc23  mov     rcx, rdi; hFile
0x18002bc26  call    cs:__imp_ReadFile
0x18002bc2c  test    eax, eax
0x18002bc2e  jz      loc_18002BE26
0x18002bc34  test    r14, r14
0x18002bc37  jnz     loc_18002BCF0
0x18002bc3d  mov     eax, [rsp+88h+NumberOfBytesRead]
0x18002bc41  mov     [r15], rbx
0x18002bc44  mov     rbx, r13
0x18002bc47  mov     [rbp+0], eax
0x18002bc4a  mov     r12, [rsp+88h+arg_10]
0x18002bc52  mov     r15, [rsp+88h+var_28]
0x18002bc57  mov     r14, [rsp+88h+var_20]
0x18002bc5c  mov     r13, [rsp+88h+var_18]
0x18002bc61  mov     rbp, [rsp+88h+arg_0]
0x18002bc69  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18002bc6d  jz      short loc_18002BC78
0x18002bc6f  mov     rcx, rdi; hObject
0x18002bc72  call    cs:__imp_CloseHandle
0x18002bc78  mov     rdi, [rsp+88h+arg_8]
0x18002bc80  test    rbx, rbx
0x18002bc83  jnz     loc_18002BE6F
0x18002bc89  mov     eax, esi
0x18002bc8b  add     rsp, 78h
0x18002bc8f  pop     rsi
0x18002bc90  pop     rbx
0x18002bc91  retn
0x18002bc92  lea     r9, pbInput+24h; ""
0x18002bc99  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18002bca0  movzx   eax, byte ptr [r9-1]
0x18002bca5  mov     rdx, r9
0x18002bca8  dec     r9
0x18002bcab  cmp     al, 5Ch ; '\'
0x18002bcad  jz      short loc_18002BCB6
0x18002bcaf  cmp     r9, rcx
0x18002bcb2  ja      short loc_18002BCA0
0x18002bcb4  cmp     al, 5Ch ; '\'
0x18002bcb6  lea     rax, Class
0x18002bcbd  cmovz   r9, rdx
0x18002bcc1  mov     [rsp+88h+var_58], rax
0x18002bcc6  lea     rax, aGetfile; "GetFile"
0x18002bccd  mov     [rsp+88h+var_60], rax
0x18002bcd2  mov     dword ptr [rsp+88h+lpOverlapped], 83Dh
0x18002bcda  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002bce1  mov     r8d, esi
0x18002bce4  xor     ecx, ecx
0x18002bce6  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002bceb  jmp     loc_18002BC52
0x18002bcf0  mov     r9, r14; lpLastWriteTime
0x18002bcf3  xor     r8d, r8d; lpLastAccessTime
0x18002bcf6  xor     edx, edx; lpCreationTime
0x18002bcf8  mov     rcx, rdi; hFile
0x18002bcfb  call    cs:__imp_GetFileTime
0x18002bd01  test    eax, eax
0x18002bd03  jnz     loc_18002BC3D
0x18002bd09  call    cs:__imp_GetLastError
0x18002bd0f  mov     esi, eax
0x18002bd11  test    eax, eax
0x18002bd13  jle     short loc_18002BD1E
0x18002bd15  movzx   esi, ax
0x18002bd18  or      esi, 0C0070000h
0x18002bd1e  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18002bd25  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002bd2a  mov     r9, rax
0x18002bd2d  lea     rax, Class
0x18002bd34  mov     [rsp+88h+var_58], rax
0x18002bd39  lea     rax, aGetfiletime; "GetFileTime"
0x18002bd40  mov     [rsp+88h+var_60], rax
0x18002bd45  mov     dword ptr [rsp+88h+lpOverlapped], 86Bh
0x18002bd4d  mov     r8d, esi
0x18002bd50  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002bd57  xor     ecx, ecx
0x18002bd59  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002bd5e  jmp     loc_18002BC4A
0x18002bd63  mov     [r14], r13
0x18002bd66  jmp     loc_18002BB9B
0x18002bd6b  call    cs:__imp_GetLastError
0x18002bd71  mov     esi, eax
0x18002bd73  test    eax, eax
0x18002bd75  jle     short loc_18002BD80
0x18002bd77  movzx   esi, ax
0x18002bd7a  or      esi, 0C0070000h
0x18002bd80  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18002bd87  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002bd8c  mov     r9, rax
0x18002bd8f  lea     rax, Class
0x18002bd96  mov     [rsp+88h+var_58], rax
0x18002bd9b  lea     rax, aGetfilesizeex; "GetFileSizeEx"
0x18002bda2  mov     [rsp+88h+var_60], rax
0x18002bda7  mov     dword ptr [rsp+88h+lpOverlapped], 843h
0x18002bdaf  jmp     loc_18002BCDA
0x18002bdb4  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18002bdbb  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002bdc0  mov     dword ptr [rsp+88h+var_58], r8d
0x18002bdc5  lea     rdx, a0x08xSUSU; "0x%08x %s:%u : %s:%u"
0x18002bdcc  mov     r9, rax
0x18002bdcf  mov     esi, 0C00700DFh
0x18002bdd4  lea     rax, aLargeFile; "Large File"
0x18002bddb  mov     [rsp+88h+var_60], rax
0x18002bde0  mov     dword ptr [rsp+88h+lpOverlapped], 84Ah
0x18002bde8  jmp     loc_18002BCE1
0x18002bded  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18002bdf4  mov     esi, 0C0000017h
0x18002bdf9  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002bdfe  mov     r9, rax
0x18002be01  lea     rax, Class
0x18002be08  mov     [rsp+88h+var_58], rax
0x18002be0d  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x18002be14  mov     [rsp+88h+var_60], rax
0x18002be19  mov     dword ptr [rsp+88h+lpOverlapped], 852h
0x18002be21  jmp     loc_18002BD4D
0x18002be26  call    cs:__imp_GetLastError
0x18002be2c  mov     esi, eax
0x18002be2e  test    eax, eax
0x18002be30  jle     short loc_18002BE3B
0x18002be32  movzx   esi, ax
0x18002be35  or      esi, 0C0070000h
0x18002be3b  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18002be42  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002be47  mov     r9, rax
0x18002be4a  lea     rax, Class
0x18002be51  mov     [rsp+88h+var_58], rax
0x18002be56  lea     rax, aReadfile; "ReadFile"
0x18002be5d  mov     [rsp+88h+var_60], rax
0x18002be62  mov     dword ptr [rsp+88h+lpOverlapped], 85Eh
0x18002be6a  jmp     loc_18002BD4D
0x18002be6f  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18002be76  mov     rcx, rbx
0x18002be79  mov     rax, [rax+30h]
0x18002be7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be82  jmp     loc_18002BC89
```
