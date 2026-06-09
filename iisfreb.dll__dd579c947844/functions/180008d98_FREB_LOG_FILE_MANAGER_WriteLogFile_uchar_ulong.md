# FREB_LOG_FILE_MANAGER::WriteLogFile(uchar *,ulong)

- ea: `0x180008d98`
- end: `0x18000903f`
- name: `?WriteLogFile@FREB_LOG_FILE_MANAGER@@QEAAJPEAEK@Z`
- size: `679`
- prototype: `__int64 __fastcall(FREB_SITE_META_STORED_CONTEXT **this, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009050`

## callees

- `0x180006f98`
- `0x180008178`
- `0x180008d98`
- `0x18000ac52`
- `0x18000ac90`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008e42`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008e42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008fc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009034`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008fc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009034`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180008f27`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180008f27`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008e5c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008e5c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180008dfe`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180008dfe`
- `iisutil!PuDbgPrint` at `0x180008f05`
- `iisutil!PuDbgPrint` at `0x18000901a`
- `iisutil!PuDbgPrint` at `0x180008f05`
- `iisutil!PuDbgPrint` at `0x18000901a`
- `iisutil!PuDbgPrintError` at `0x180008f7a`
- `iisutil!PuDbgPrintError` at `0x180008f7a`

## string_xrefs

- `0x180008edd`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\freb_log_file_manager.cxx`
- `0x180008f70`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\freb_log_file_manager.cxx`
- `0x180008ff2`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\freb_log_file_manager.cxx`
- `0x180008ef9`: `Freb: Log file %S opened for writing\n`
- `0x180008ec0`: `FREB_LOG_FILE_MANAGER::WriteLogFile`
- `0x180008f53`: `Failed to write to FREB log file\n`
- `0x180008faa`: `Failed to write all the data to FREB log file\n`

## pseudocode

```c
__int64 __fastcall FREB_LOG_FILE_MANAGER::WriteLogFile(
        FREB_SITE_META_STORED_CONTEXT **this,
        LPCVOID lpBuffer,
        DWORD nNumberOfBytesToWrite)
{
  FREB_SITE_META_STORED_CONTEXT *v6; // rdx
  FREB_SITE_META_STORED_CONTEXT *v7; // rbx
  unsigned int v8; // eax
  int v9; // edi
  DWORD TickCount; // eax
  signed int LogFileHandle; // ebx
  __int64 v13; // rdi
  signed int v14; // eax
  signed int LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hFile; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v18[32]; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v19; // [rsp+60h] [rbp-A0h]
  unsigned __int16 v20[264]; // [rsp+80h] [rbp-80h] BYREF

  hFile = (HANDLE)-1LL;
  NumberOfBytesWritten = 0;
  memset_0(v20, 0, 0x208u);
  STRU::STRU((STRU *)v18, v20, 0x104u);
  v6 = *this;
  if ( (unsigned int)(*((_DWORD *)v6 + 190) + _InterlockedIncrement((volatile signed __int32 *)*this + 189)) >= *((_DWORD *)v6 + 18) )
    FREB_SITE_META_STORED_CONTEXT::ScavengeFrebLogFiles(v6);
  v7 = *this;
  v8 = *((_DWORD *)*this + 187);
  if ( v8 > *((_DWORD *)*this + 18) || v8 > 0x1E )
  {
    v9 = *((_DWORD *)v7 + 188);
    TickCount = GetTickCount();
    if ( !v9 )
    {
      *((_DWORD *)v7 + 188) = TickCount;
LABEL_7:
      LogFileHandle = -2147467259;
      goto LABEL_8;
    }
    if ( TickCount - v9 <= 0x7530 )
      goto LABEL_7;
    *(_QWORD *)((char *)v7 + 748) = 0;
  }
  LogFileHandle = FREB_LOG_FILE_MANAGER::GetLogFileHandle((FREB_LOG_FILE_MANAGER *)this, &hFile, (struct STRU *)v18);
  if ( LogFileHandle < 0 )
  {
    v13 = (__int64)hFile;
  }
  else
  {
    if ( (g_dwDebugFlags & 3) != 0 && g_dwDebugFlags < 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_log_file_manager.cxx",
        916,
        "FREB_LOG_FILE_MANAGER::WriteLogFile",
        "Freb: Log file %S opened for writing\n",
        v19);
    v13 = (__int64)hFile;
    if ( WriteFile(hFile, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
    {
      if ( NumberOfBytesWritten == nNumberOfBytesToWrite )
      {
        CloseHandle((HANDLE)v13);
        v13 = -1;
        if ( (g_dwDebugFlags & 3) == 0 || g_dwDebugFlags >= 0 )
          goto LABEL_8;
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_log_file_manager.cxx",
          951,
          "FREB_LOG_FILE_MANAGER::WriteLogFile",
          "Freb: Log file %S closed for writing (freb events are persisted now)\n",
          v19);
      }
      else
      {
        LastError = GetLastError();
        LogFileHandle = LastError;
        if ( LastError > 0 )
          LogFileHandle = (unsigned __int16)LastError | 0x80070000;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_log_file_manager.cxx",
            939,
            "FREB_LOG_FILE_MANAGER::WriteLogFile",
            -2147467259,
            "Failed to write all the data to FREB log file\n");
      }
    }
    else
    {
      v14 = GetLastError();
      LogFileHandle = v14;
      if ( v14 > 0 )
        LogFileHandle = (unsigned __int16)v14 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_log_file_manager.cxx",
          930,
          "FREB_LOG_FILE_MANAGER::WriteLogFile",
          LogFileHandle,
          "Failed to write to FREB log file\n");
    }
  }
  if ( v13 != -1 )
    CloseHandle((HANDLE)v13);
LABEL_8:
  STRU::~STRU((STRU *)v18);
  return (unsigned int)LogFileHandle;
}

```

## disassembly

```asm
0x180008d98  mov     [rsp-8+arg_18], rbx
0x180008d9d  push    rbp
0x180008d9e  push    rsi
0x180008d9f  push    rdi
0x180008da0  push    r14
0x180008da2  push    r15
0x180008da4  lea     rbp, [rsp-1A0h]
0x180008dac  sub     rsp, 2A0h
0x180008db3  mov     rax, cs:__security_cookie
0x180008dba  xor     rax, rsp
0x180008dbd  mov     [rbp+1C0h+var_30], rax
0x180008dc4  mov     r14d, r8d
0x180008dc7  mov     [rsp+2C0h+hFile], 0FFFFFFFFFFFFFFFFh
0x180008dd0  mov     r15, rdx
0x180008dd3  mov     [rsp+2C0h+NumberOfBytesWritten], 0
0x180008ddb  mov     rsi, rcx
0x180008dde  xor     edx, edx; Val
0x180008de0  mov     r8d, 208h; Size
0x180008de6  lea     rcx, [rbp+1C0h+var_240]; void *
0x180008dea  call    memset_0
0x180008def  mov     r8d, 104h
0x180008df5  lea     rdx, [rbp+1C0h+var_240]
0x180008df9  lea     rcx, [rsp+2C0h+var_280]
0x180008dfe  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180008e04  mov     rdx, [rsi]
0x180008e07  mov     ecx, 1
0x180008e0c  lock xadd [rdx+2F4h], ecx
0x180008e14  inc     ecx
0x180008e16  add     ecx, [rdx+2F8h]
0x180008e1c  cmp     ecx, [rdx+48h]
0x180008e1f  jb      short loc_180008E29
0x180008e21  mov     rcx, rdx; this
0x180008e24  call    ?ScavengeFrebLogFiles@FREB_SITE_META_STORED_CONTEXT@@AEAAJXZ; FREB_SITE_META_STORED_CONTEXT::ScavengeFrebLogFiles(void)
0x180008e29  mov     rbx, [rsi]
0x180008e2c  mov     eax, [rbx+2ECh]
0x180008e32  cmp     eax, [rbx+48h]
0x180008e35  ja      short loc_180008E3C
0x180008e37  cmp     eax, 1Eh
0x180008e3a  jbe     short loc_180008E9E
0x180008e3c  mov     edi, [rbx+2F0h]
0x180008e42  call    cs:__imp_GetTickCount
0x180008e48  test    edi, edi
0x180008e4a  jnz     short loc_180008E8A
0x180008e4c  mov     [rbx+2F0h], eax
0x180008e52  mov     ebx, 80004005h
0x180008e57  lea     rcx, [rsp+2C0h+var_280]
0x180008e5c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180008e62  mov     eax, ebx
0x180008e64  mov     rcx, [rbp+1C0h+var_30]
0x180008e6b  xor     rcx, rsp; StackCookie
0x180008e6e  call    __security_check_cookie
0x180008e73  mov     rbx, [rsp+2C0h+arg_18]
0x180008e7b  add     rsp, 2A0h
0x180008e82  pop     r15
0x180008e84  pop     r14
0x180008e86  pop     rdi
0x180008e87  pop     rsi
0x180008e88  pop     rbp
0x180008e89  retn
0x180008e8a  sub     eax, edi
0x180008e8c  cmp     eax, 7530h
0x180008e91  jbe     short loc_180008E52
0x180008e93  mov     qword ptr [rbx+2ECh], 0
0x180008e9e  lea     r8, [rsp+2C0h+var_280]; struct STRU *
0x180008ea3  mov     rcx, rsi; this
0x180008ea6  lea     rdx, [rsp+2C0h+hFile]; void **
0x180008eab  call    ?GetLogFileHandle@FREB_LOG_FILE_MANAGER@@AEAAJPEAPEAXPEAVSTRU@@@Z; FREB_LOG_FILE_MANAGER::GetLogFileHandle(void * *,STRU *)
0x180008eb0  mov     ebx, eax
0x180008eb2  test    eax, eax
0x180008eb4  js      loc_180009022
0x180008eba  mov     ecx, cs:g_dwDebugFlags
0x180008ec0  lea     rsi, aFrebLogFileMan_0; "FREB_LOG_FILE_MANAGER::WriteLogFile"
0x180008ec7  test    cl, 3
0x180008eca  setnz   dl
0x180008ecd  bt      ecx, 1Fh
0x180008ed1  setb    cl
0x180008ed4  test    cl, dl
0x180008ed6  jz      short loc_180008F0B
0x180008ed8  mov     rax, [rsp+2C0h+var_260]
0x180008edd  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008ee4  mov     rcx, cs:g_pDebug
0x180008eeb  mov     r9, rsi
0x180008eee  mov     [rsp+2C0h+var_298], rax
0x180008ef3  mov     r8d, 394h
0x180008ef9  lea     rax, aFrebLogFileSOp; "Freb: Log file %S opened for writing\n"
0x180008f00  mov     [rsp+2C0h+lpOverlapped], rax
0x180008f05  call    cs:__imp_PuDbgPrint
0x180008f0b  mov     rdi, [rsp+2C0h+hFile]
0x180008f10  lea     r9, [rsp+2C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180008f15  mov     rcx, rdi; hFile
0x180008f18  mov     [rsp+2C0h+lpOverlapped], 0; lpOverlapped
0x180008f21  mov     r8d, r14d; nNumberOfBytesToWrite
0x180008f24  mov     rdx, r15; lpBuffer
0x180008f27  call    cs:__imp_WriteFile
0x180008f2d  test    eax, eax
0x180008f2f  jnz     short loc_180008F85
0x180008f31  call    cs:__imp_GetLastError
0x180008f37  mov     ebx, eax
0x180008f39  test    eax, eax
0x180008f3b  jle     short loc_180008F46
0x180008f3d  movzx   ebx, ax
0x180008f40  or      ebx, 80070000h
0x180008f46  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180008f4d  jz      loc_180009027
0x180008f53  lea     rax, aFailedToWriteT; "Failed to write to FREB log file\n"
0x180008f5a  mov     r8d, 3A2h
0x180008f60  mov     [rsp+2C0h+var_298], rax
0x180008f65  mov     dword ptr [rsp+2C0h+lpOverlapped], ebx
0x180008f69  mov     rcx, cs:g_pDebug
0x180008f70  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008f77  mov     r9, rsi
0x180008f7a  call    cs:__imp_PuDbgPrintError
0x180008f80  jmp     loc_180009027
0x180008f85  cmp     [rsp+2C0h+NumberOfBytesWritten], r14d
0x180008f8a  jz      short loc_180008FC6
0x180008f8c  call    cs:__imp_GetLastError
0x180008f92  mov     ebx, eax
0x180008f94  test    eax, eax
0x180008f96  jle     short loc_180008FA1
0x180008f98  movzx   ebx, ax
0x180008f9b  or      ebx, 80070000h
0x180008fa1  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180008fa8  jz      short loc_180009027
0x180008faa  lea     rax, aFailedToWriteA; "Failed to write all the data to FREB lo"...
0x180008fb1  mov     r8d, 3ABh
0x180008fb7  mov     [rsp+2C0h+var_298], rax
0x180008fbc  mov     dword ptr [rsp+2C0h+lpOverlapped], 80004005h
0x180008fc4  jmp     short loc_180008F69
0x180008fc6  mov     rcx, rdi; hObject
0x180008fc9  call    cs:__imp_CloseHandle
0x180008fcf  mov     eax, cs:g_dwDebugFlags
0x180008fd5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180008fd9  test    al, 3
0x180008fdb  setnz   cl
0x180008fde  bt      eax, 1Fh
0x180008fe2  setb    al
0x180008fe5  test    al, cl
0x180008fe7  jz      loc_180008E57
0x180008fed  mov     rax, [rsp+2C0h+var_260]
0x180008ff2  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008ff9  mov     rcx, cs:g_pDebug
0x180009000  mov     r9, rsi
0x180009003  mov     [rsp+2C0h+var_298], rax
0x180009008  mov     r8d, 3B7h
0x18000900e  lea     rax, aFrebLogFileSCl; "Freb: Log file %S closed for writing (f"...
0x180009015  mov     [rsp+2C0h+lpOverlapped], rax
0x18000901a  call    cs:__imp_PuDbgPrint
0x180009020  jmp     short loc_180009027
0x180009022  mov     rdi, [rsp+2C0h+hFile]
0x180009027  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000902b  jz      loc_180008E57
0x180009031  mov     rcx, rdi; hObject
0x180009034  call    cs:__imp_CloseHandle
0x18000903a  jmp     loc_180008E57
```
