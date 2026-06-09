# FREB_LOG_FILE_MANAGER::OpenFile(ushort const *,ulong,void * *)

- ea: `0x180008548`
- end: `0x1800087a1`
- name: `?OpenFile@FREB_LOG_FILE_MANAGER@@AEAAJPEBGKPEAPEAX@Z`
- size: `601`
- prototype: `__int64 __fastcall(FREB_LOG_FILE_MANAGER *this, LPCWSTR lpFileName, __int64, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180008178`

## callees

- `0x180007f70`
- `0x180008548`
- `0x18000a4dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000859d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008612`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008635`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008736`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000859d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008612`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008635`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008736`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000858d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000872a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000858d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000872a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180008604`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180008604`
- `iisutil!PuDbgPrint` at `0x1800085f5`
- `iisutil!PuDbgPrint` at `0x1800085f5`
- `iisutil!PuDbgPrintError` at `0x1800086b1`
- `iisutil!PuDbgPrintError` at `0x1800086fc`
- `iisutil!PuDbgPrintError` at `0x1800086b1`
- `iisutil!PuDbgPrintError` at `0x1800086fc`

## string_xrefs

- `0x1800085d2`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\freb_log_file_manager.cxx`
- `0x1800086a6`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\freb_log_file_manager.cxx`
- `0x1800086f1`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\freb_log_file_manager.cxx`
- `0x1800085dd`: `Freb: attempt to create directory %S\n`
- `0x1800085c5`: `FREB_LOG_FILE_MANAGER::OpenFile`
- `0x18000869a`: `FREB_LOG_FILE_MANAGER::OpenFile`
- `0x1800086e3`: `FREB_LOG_FILE_MANAGER::OpenFile`
- `0x180008687`: `Failed to create FREB log directory %S\n`
- `0x1800086d1`: `Failed to create FREB XSL file\n`
- `0x180008778`: `Failed to create/open FREB log file %S\n`

## pseudocode

```c
__int64 __fastcall FREB_LOG_FILE_MANAGER::OpenFile(
        FREB_LOG_FILE_MANAGER *this,
        LPCWSTR lpFileName,
        __int64 a3,
        void **a4)
{
  HANDLE FileW; // rax
  signed int LastError; // eax
  unsigned int v9; // ebx
  __int64 v10; // r8
  const char *v11; // rax
  int XslFileFromResource; // eax
  signed int v13; // eax
  unsigned __int16 *v15[2]; // [rsp+40h] [rbp-28h] BYREF
  __int64 v16; // [rsp+50h] [rbp-18h]

  *a4 = 0;
  FileW = CreateFileW(lpFileName, 0x40000000u, 7u, 0, 1u, 0, 0);
  if ( FileW != (HANDLE)-1LL )
    goto LABEL_20;
  if ( GetLastError() == 3 )
  {
    if ( (g_dwDebugFlags & 3) != 0 && g_dwDebugFlags < 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_log_file_manager.cxx",
        499,
        "FREB_LOG_FILE_MANAGER::OpenFile",
        "Freb: attempt to create directory %S\n",
        *(const wchar_t **)(*(_QWORD *)this + 48LL));
    if ( !CreateDirectoryW(*(LPCWSTR *)(*(_QWORD *)this + 48LL), 0) && GetLastError() != 183 )
    {
      v15[0] = 0;
      v15[1] = 0;
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      v16 = *(_QWORD *)(*(_QWORD *)this + 48LL);
      FREB_LOG_NT_EVENT_TABLE::LogEvent(0x800008EB, 3u, (const unsigned __int16 **const)v15, v9);
      if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        v10 = 529;
        v11 = "Failed to create FREB log directory %S\n";
LABEL_11:
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_log_file_manager.cxx",
          v10,
          "FREB_LOG_FILE_MANAGER::OpenFile",
          v9,
          v11);
        return v9;
      }
      return v9;
    }
    XslFileFromResource = FREB_LOG_FILE_MANAGER::CreateXslFileFromResource(this);
    if ( XslFileFromResource < 0 && (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_log_file_manager.cxx",
        543,
        "FREB_LOG_FILE_MANAGER::OpenFile",
        XslFileFromResource,
        "Failed to create FREB XSL file\n");
    FileW = CreateFileW(lpFileName, 0x40000000u, 7u, 0, 1u, 0, 0);
    if ( FileW != (HANDLE)-1LL )
    {
LABEL_20:
      *a4 = FileW;
      return 0;
    }
  }
  v13 = GetLastError();
  v9 = v13;
  if ( v13 > 0 )
    v9 = (unsigned __int16)v13 | 0x80070000;
  *(_OWORD *)v15 = 0;
  FREB_LOG_NT_EVENT_TABLE::LogEvent(0x800008EC, 2u, (const unsigned __int16 **const)v15, v9);
  if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    v11 = "Failed to create/open FREB log file %S\n";
    v10 = 573;
    goto LABEL_11;
  }
  return v9;
}

```

## disassembly

```asm
0x180008548  mov     rax, rsp
0x18000854b  mov     [rax+8], rbx
0x18000854f  mov     [rax+10h], rsi
0x180008553  push    rdi
0x180008554  sub     rsp, 60h
0x180008558  mov     rsi, rdx
0x18000855b  mov     qword ptr [rax-38h], 0
0x180008563  mov     rbx, r9
0x180008566  mov     qword ptr [r9], 0
0x18000856d  xor     r9d, r9d; lpSecurityAttributes
0x180008570  mov     dword ptr [rax-40h], 0
0x180008577  mov     rdi, rcx
0x18000857a  mov     dword ptr [rax-48h], 1
0x180008581  mov     edx, 40000000h; dwDesiredAccess
0x180008586  mov     rcx, rsi; lpFileName
0x180008589  lea     r8d, [r9+7]; dwShareMode
0x18000858d  call    cs:__imp_CreateFileW
0x180008593  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008597  jnz     loc_18000878A
0x18000859d  call    cs:__imp_GetLastError
0x1800085a3  cmp     eax, 3
0x1800085a6  jnz     loc_180008736
0x1800085ac  mov     eax, cs:g_dwDebugFlags
0x1800085b2  test    al, 3
0x1800085b4  setnz   cl
0x1800085b7  bt      eax, 1Fh
0x1800085bb  setb    al
0x1800085be  test    al, cl
0x1800085c0  jz      short loc_1800085FB
0x1800085c2  mov     rax, [rdi]
0x1800085c5  lea     r9, aFrebLogFileMan_1; "FREB_LOG_FILE_MANAGER::OpenFile"
0x1800085cc  mov     r8d, 1F3h
0x1800085d2  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800085d9  mov     rcx, [rax+30h]
0x1800085dd  lea     rax, aFrebAttemptToC; "Freb: attempt to create directory %S\n"
0x1800085e4  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rcx
0x1800085e9  mov     rcx, cs:g_pDebug
0x1800085f0  mov     qword ptr [rsp+68h+dwCreationDisposition], rax
0x1800085f5  call    cs:__imp_PuDbgPrint
0x1800085fb  mov     rcx, [rdi]
0x1800085fe  xor     edx, edx; lpSecurityAttributes
0x180008600  mov     rcx, [rcx+30h]; lpPathName
0x180008604  call    cs:__imp_CreateDirectoryW
0x18000860a  test    eax, eax
0x18000860c  jnz     loc_1800086BC
0x180008612  call    cs:__imp_GetLastError
0x180008618  cmp     eax, 0B7h
0x18000861d  jz      loc_1800086BC
0x180008623  mov     [rsp+68h+var_28], 0
0x18000862c  mov     [rsp+68h+var_28+8], 0
0x180008635  call    cs:__imp_GetLastError
0x18000863b  mov     ebx, eax
0x18000863d  test    eax, eax
0x18000863f  jle     short loc_18000864A
0x180008641  movzx   ebx, ax
0x180008644  or      ebx, 80070000h
0x18000864a  mov     rax, [rdi]
0x18000864d  lea     r8, [rsp+68h+var_28]; unsigned __int16 **
0x180008652  mov     edx, 3; unsigned __int16
0x180008657  mov     r9d, ebx; unsigned int
0x18000865a  mov     rcx, [rax+30h]
0x18000865e  mov     [rsp+68h+var_18], rcx
0x180008663  mov     ecx, 800008EBh; unsigned int
0x180008668  call    ?LogEvent@FREB_LOG_NT_EVENT_TABLE@@SAXKGQEAPEBGK@Z; FREB_LOG_NT_EVENT_TABLE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18000866d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180008674  jz      loc_18000878F
0x18000867a  mov     rax, [rdi]
0x18000867d  mov     r8d, 211h
0x180008683  mov     rcx, [rax+30h]
0x180008687  lea     rax, aFailedToCreate_1; "Failed to create FREB log directory %S"...
0x18000868e  mov     [rsp+68h+hTemplateFile], rcx
0x180008693  mov     rcx, cs:g_pDebug
0x18000869a  lea     r9, aFrebLogFileMan_1; "FREB_LOG_FILE_MANAGER::OpenFile"
0x1800086a1  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rax
0x1800086a6  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800086ad  mov     [rsp+68h+dwCreationDisposition], ebx
0x1800086b1  call    cs:__imp_PuDbgPrintError
0x1800086b7  jmp     loc_18000878F
0x1800086bc  mov     rcx, rdi; this
0x1800086bf  call    ?CreateXslFileFromResource@FREB_LOG_FILE_MANAGER@@AEAAJXZ; FREB_LOG_FILE_MANAGER::CreateXslFileFromResource(void)
0x1800086c4  test    eax, eax
0x1800086c6  jns     short loc_180008702
0x1800086c8  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800086cf  jz      short loc_180008702
0x1800086d1  lea     rcx, aFailedToCreate; "Failed to create FREB XSL file\n"
0x1800086d8  mov     r8d, 21Fh
0x1800086de  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rcx
0x1800086e3  lea     r9, aFrebLogFileMan_1; "FREB_LOG_FILE_MANAGER::OpenFile"
0x1800086ea  mov     rcx, cs:g_pDebug
0x1800086f1  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800086f8  mov     [rsp+68h+dwCreationDisposition], eax
0x1800086fc  call    cs:__imp_PuDbgPrintError
0x180008702  xor     r9d, r9d; lpSecurityAttributes
0x180008705  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18000870e  mov     [rsp+68h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180008716  mov     edx, 40000000h; dwDesiredAccess
0x18000871b  mov     rcx, rsi; lpFileName
0x18000871e  mov     [rsp+68h+dwCreationDisposition], 1; dwCreationDisposition
0x180008726  lea     r8d, [r9+7]; dwShareMode
0x18000872a  call    cs:__imp_CreateFileW
0x180008730  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008734  jnz     short loc_18000878A
0x180008736  call    cs:__imp_GetLastError
0x18000873c  mov     ebx, eax
0x18000873e  test    eax, eax
0x180008740  jle     short loc_18000874B
0x180008742  movzx   ebx, ax
0x180008745  or      ebx, 80070000h
0x18000874b  xorps   xmm0, xmm0
0x18000874e  lea     r8, [rsp+68h+var_28]; unsigned __int16 **
0x180008753  mov     edx, 2; unsigned __int16
0x180008758  mov     r9d, ebx; unsigned int
0x18000875b  mov     ecx, 800008ECh; unsigned int
0x180008760  movups  xmmword ptr [rsp+68h+var_28], xmm0
0x180008765  call    ?LogEvent@FREB_LOG_NT_EVENT_TABLE@@SAXKGQEAPEBGK@Z; FREB_LOG_NT_EVENT_TABLE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18000876a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180008771  jz      short loc_18000878F
0x180008773  mov     [rsp+68h+hTemplateFile], rsi
0x180008778  lea     rax, aFailedToCreate_0; "Failed to create/open FREB log file %S"...
0x18000877f  mov     r8d, 23Dh
0x180008785  jmp     loc_180008693
0x18000878a  mov     [rbx], rax
0x18000878d  xor     ebx, ebx
0x18000878f  mov     rsi, [rsp+68h+arg_8]
0x180008794  mov     eax, ebx
0x180008796  mov     rbx, [rsp+68h+arg_0]
0x18000879b  add     rsp, 60h
0x18000879f  pop     rdi
0x1800087a0  retn
```
