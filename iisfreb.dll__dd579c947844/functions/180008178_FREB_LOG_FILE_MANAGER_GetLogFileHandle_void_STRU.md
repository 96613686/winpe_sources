# FREB_LOG_FILE_MANAGER::GetLogFileHandle(void * *,STRU *)

- ea: `0x180008178`
- end: `0x18000841e`
- name: `?GetLogFileHandle@FREB_LOG_FILE_MANAGER@@AEAAJPEAPEAXPEAVSTRU@@@Z`
- size: `678`
- prototype: `__int64 __fastcall(FREB_LOG_FILE_MANAGER *__hidden this, void **, struct STRU *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180008d98`

## callees

- `0x180003570`
- `0x180008178`
- `0x180008548`
- `0x180008ad8`
- `0x18000ac52`
- `0x18000ac90`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008206`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008229`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008253`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008206`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008229`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008253`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008302`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008302`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800083e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800083e0`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000824d`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800083cf`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000824d`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800083cf`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800083ea`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800083f5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800083ea`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800083f5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800081ce`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800081ed`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800081ce`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800081ed`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180008297`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800083b6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180008297`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800083b6`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800082b0`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800082b0`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000821c`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000821c`
- `iisutil!PuDbgPrint` at `0x1800083a8`
- `iisutil!PuDbgPrint` at `0x1800083a8`
- `iisutil!PuDbgPrintError` at `0x180008359`
- `iisutil!PuDbgPrintError` at `0x180008359`

## string_xrefs

- `0x180008337`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\freb_log_file_manager.cxx`
- `0x18000838a`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\freb_log_file_manager.cxx`
- `0x18000826b`: `fr%06u.xml`
- `0x180008349`: `Failed to open FREB log file %S\n`
- `0x18000839c`: `Freb: Log file %S opened for writing\n`

## pseudocode

```c
__int64 __fastcall FREB_LOG_FILE_MANAGER::GetLogFileHandle(FREB_LOG_FILE_MANAGER *this, void **a2, struct STRU *a3)
{
  int v6; // r14d
  int v7; // ebx
  int v8; // ebx
  signed int updated; // ebx
  signed __int32 v10; // r9d
  __int64 v11; // r8
  int v12; // eax
  signed int LastError; // eax
  HANDLE hObject; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v16[32]; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpFileName; // [rsp+68h] [rbp-98h]
  _BYTE v18[32]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v19; // [rsp+A0h] [rbp-60h]
  unsigned int v20; // [rsp+A8h] [rbp-58h]
  unsigned __int16 v21[64]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v22[64]; // [rsp+140h] [rbp+40h] BYREF

  memset_0(v21, 0, sizeof(v21));
  STRU::STRU((STRU *)v16, v21, 0x40u);
  memset_0(v22, 0, sizeof(v22));
  STRU::STRU((STRU *)v18, v22, 0x40u);
  v6 = 0;
  hObject = (HANDLE)-1LL;
  while ( 1 )
  {
    v7 = *((_DWORD *)this + 5);
    if ( !v7 || GetTickCount() - v7 > 0x2BF20 )
    {
      CReaderWriterLock3::WriteLock((FREB_LOG_FILE_MANAGER *)((char *)this + 8));
      v8 = *((_DWORD *)this + 5);
      if ( !v8 || GetTickCount() - v8 > 0x2BF20 )
      {
        updated = FREB_LOG_FILE_MANAGER::UpdateNextLogFileSequenceNumber(this);
        if ( updated < 0 )
        {
          CReaderWriterLock3::WriteUnlock((FREB_LOG_FILE_MANAGER *)((char *)this + 8));
          goto LABEL_25;
        }
      }
      CReaderWriterLock3::WriteUnlock((FREB_LOG_FILE_MANAGER *)((char *)this + 8));
    }
    *((_DWORD *)this + 5) = GetTickCount();
    v10 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 4, 1u);
    updated = StringCchPrintfW(v19, (unsigned __int64)v20 >> 1, L"fr%06u.xml", (unsigned int)(v10 + 1));
    if ( updated < 0 )
      goto LABEL_25;
    updated = STRU::Copy((STRU *)v16, *(const unsigned __int16 **)(*(_QWORD *)this + 48LL));
    if ( updated < 0 )
      goto LABEL_25;
    updated = STRU::Append((STRU *)v16, v19);
    if ( updated < 0 )
      goto LABEL_25;
    v12 = FREB_LOG_FILE_MANAGER::OpenFile(this, lpFileName, v11, &hObject);
    if ( v12 != -2147024713 && v12 != -2147024816 )
      break;
    if ( (unsigned int)++v6 > 0x28 )
    {
      *((_DWORD *)this + 5) = 0;
      updated = -2147467259;
      goto LABEL_25;
    }
  }
  if ( v12 >= 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 && g_dwDebugFlags < 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_log_file_manager.cxx",
        415,
        "FREB_LOG_FILE_MANAGER::GetLogFileHandle",
        "Freb: Log file %S opened for writing\n",
        lpFileName);
    updated = STRU::Copy(a3, lpFileName);
    if ( updated >= 0 )
    {
      *a2 = hObject;
      goto LABEL_27;
    }
  }
  else
  {
    LastError = GetLastError();
    updated = LastError;
    if ( LastError > 0 )
      updated = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_log_file_manager.cxx",
        407,
        "FREB_LOG_FILE_MANAGER::GetLogFileHandle",
        updated,
        "Failed to open FREB log file %S\n",
        lpFileName);
  }
LABEL_25:
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
LABEL_27:
  STRU::~STRU((STRU *)v18);
  STRU::~STRU((STRU *)v16);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180008178  push    rbp
0x18000817a  push    rbx
0x18000817b  push    rsi
0x18000817c  push    rdi
0x18000817d  push    r12
0x18000817f  push    r14
0x180008181  push    r15
0x180008183  lea     rbp, [rsp-0D0h]
0x18000818b  sub     rsp, 1D0h
0x180008192  mov     rax, cs:__security_cookie
0x180008199  xor     rax, rsp
0x18000819c  mov     [rbp+100h+var_40], rax
0x1800081a3  mov     r12, r8
0x1800081a6  mov     r15, rdx
0x1800081a9  mov     rdi, rcx
0x1800081ac  mov     esi, 80h
0x1800081b1  mov     r8d, esi; Size
0x1800081b4  lea     rcx, [rbp+100h+var_140]; void *
0x1800081b8  xor     edx, edx; Val
0x1800081ba  call    memset_0
0x1800081bf  lea     ebx, [rsi-40h]
0x1800081c2  mov     r8d, ebx
0x1800081c5  lea     rdx, [rbp+100h+var_140]
0x1800081c9  lea     rcx, [rsp+200h+var_1B8]
0x1800081ce  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800081d4  mov     r8d, esi; Size
0x1800081d7  lea     rcx, [rbp+100h+var_C0]; void *
0x1800081db  xor     edx, edx; Val
0x1800081dd  call    memset_0
0x1800081e2  mov     r8d, ebx
0x1800081e5  lea     rdx, [rbp+100h+var_C0]
0x1800081e9  lea     rcx, [rbp+100h+var_180]
0x1800081ed  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800081f3  xor     r14d, r14d
0x1800081f6  mov     [rsp+200h+hObject], 0FFFFFFFFFFFFFFFFh
0x1800081ff  mov     ebx, [rdi+14h]
0x180008202  test    ebx, ebx
0x180008204  jz      short loc_180008215
0x180008206  call    cs:__imp_GetTickCount
0x18000820c  sub     eax, ebx
0x18000820e  cmp     eax, 2BF20h
0x180008213  jbe     short loc_180008253
0x180008215  lea     rsi, [rdi+8]
0x180008219  mov     rcx, rsi
0x18000821c  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180008222  mov     ebx, [rdi+14h]
0x180008225  test    ebx, ebx
0x180008227  jz      short loc_180008238
0x180008229  call    cs:__imp_GetTickCount
0x18000822f  sub     eax, ebx
0x180008231  cmp     eax, 2BF20h
0x180008236  jbe     short loc_18000824A
0x180008238  mov     rcx, rdi; this
0x18000823b  call    ?UpdateNextLogFileSequenceNumber@FREB_LOG_FILE_MANAGER@@AEAAJXZ; FREB_LOG_FILE_MANAGER::UpdateNextLogFileSequenceNumber(void)
0x180008240  mov     ebx, eax
0x180008242  test    eax, eax
0x180008244  js      loc_1800083CC
0x18000824a  mov     rcx, rsi
0x18000824d  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180008253  call    cs:__imp_GetTickCount
0x180008259  mov     [rdi+14h], eax
0x18000825c  mov     r9d, 1
0x180008262  lock xadd [rdi+10h], r9d
0x180008268  mov     edx, [rbp+100h+var_158]
0x18000826b  lea     r8, aFr06uXml; "fr%06u.xml"
0x180008272  mov     rcx, [rbp+100h+var_160]; unsigned __int16 *
0x180008276  inc     r9d
0x180008279  shr     rdx, 1; unsigned __int64
0x18000827c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008281  mov     ebx, eax
0x180008283  test    eax, eax
0x180008285  js      loc_1800083D5
0x18000828b  mov     rdx, [rdi]
0x18000828e  lea     rcx, [rsp+200h+var_1B8]
0x180008293  mov     rdx, [rdx+30h]
0x180008297  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000829d  mov     ebx, eax
0x18000829f  test    eax, eax
0x1800082a1  js      loc_1800083D5
0x1800082a7  mov     rdx, [rbp+100h+var_160]
0x1800082ab  lea     rcx, [rsp+200h+var_1B8]
0x1800082b0  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800082b6  mov     ebx, eax
0x1800082b8  test    eax, eax
0x1800082ba  js      loc_1800083D5
0x1800082c0  mov     rdx, [rsp+200h+lpFileName]; lpFileName
0x1800082c5  lea     r9, [rsp+200h+hObject]; void **
0x1800082ca  mov     rcx, rdi; this
0x1800082cd  call    ?OpenFile@FREB_LOG_FILE_MANAGER@@AEAAJPEBGKPEAPEAX@Z; FREB_LOG_FILE_MANAGER::OpenFile(ushort const *,ulong,void * *)
0x1800082d2  cmp     eax, 800700B7h
0x1800082d7  jz      short loc_1800082E0
0x1800082d9  cmp     eax, 80070050h
0x1800082de  jnz     short loc_1800082FE
0x1800082e0  inc     r14d
0x1800082e3  cmp     r14d, 28h ; '('
0x1800082e7  jbe     loc_1800081FF
0x1800082ed  mov     dword ptr [rdi+14h], 0
0x1800082f4  mov     ebx, 80004005h
0x1800082f9  jmp     loc_1800083D5
0x1800082fe  test    eax, eax
0x180008300  jns     short loc_180008361
0x180008302  call    cs:__imp_GetLastError
0x180008308  mov     ebx, eax
0x18000830a  test    eax, eax
0x18000830c  jle     short loc_180008317
0x18000830e  movzx   ebx, ax
0x180008311  or      ebx, 80070000h
0x180008317  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000831e  jz      loc_1800083D5
0x180008324  mov     rax, [rsp+200h+lpFileName]
0x180008329  lea     r9, aFrebLogFileMan_2; "FREB_LOG_FILE_MANAGER::GetLogFileHandle"
0x180008330  mov     rcx, cs:g_pDebug
0x180008337  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000833e  mov     [rsp+200h+var_1D0], rax
0x180008343  mov     r8d, 197h
0x180008349  lea     rax, aFailedToOpenFr; "Failed to open FREB log file %S\n"
0x180008350  mov     [rsp+200h+var_1D8], rax
0x180008355  mov     dword ptr [rsp+200h+var_1E0], ebx
0x180008359  call    cs:__imp_PuDbgPrintError
0x18000835f  jmp     short loc_1800083D5
0x180008361  mov     eax, cs:g_dwDebugFlags
0x180008367  test    al, 3
0x180008369  setnz   cl
0x18000836c  bt      eax, 1Fh
0x180008370  setb    al
0x180008373  test    al, cl
0x180008375  jz      short loc_1800083AE
0x180008377  mov     rax, [rsp+200h+lpFileName]
0x18000837c  lea     r9, aFrebLogFileMan_2; "FREB_LOG_FILE_MANAGER::GetLogFileHandle"
0x180008383  mov     rcx, cs:g_pDebug
0x18000838a  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008391  mov     [rsp+200h+var_1D8], rax
0x180008396  mov     r8d, 19Fh
0x18000839c  lea     rax, aFrebLogFileSOp; "Freb: Log file %S opened for writing\n"
0x1800083a3  mov     [rsp+200h+var_1E0], rax
0x1800083a8  call    cs:__imp_PuDbgPrint
0x1800083ae  mov     rdx, [rsp+200h+lpFileName]
0x1800083b3  mov     rcx, r12
0x1800083b6  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800083bc  mov     ebx, eax
0x1800083be  test    eax, eax
0x1800083c0  js      short loc_1800083D5
0x1800083c2  mov     rax, [rsp+200h+hObject]
0x1800083c7  mov     [r15], rax
0x1800083ca  jmp     short loc_1800083E6
0x1800083cc  mov     rcx, rsi
0x1800083cf  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800083d5  mov     rcx, [rsp+200h+hObject]; hObject
0x1800083da  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800083de  jz      short loc_1800083E6
0x1800083e0  call    cs:__imp_CloseHandle
0x1800083e6  lea     rcx, [rbp+100h+var_180]
0x1800083ea  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800083f0  lea     rcx, [rsp+200h+var_1B8]
0x1800083f5  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800083fb  mov     eax, ebx
0x1800083fd  mov     rcx, [rbp+100h+var_40]
0x180008404  xor     rcx, rsp; StackCookie
0x180008407  call    __security_check_cookie
0x18000840c  add     rsp, 1D0h
0x180008413  pop     r15
0x180008415  pop     r14
0x180008417  pop     r12
0x180008419  pop     rdi
0x18000841a  pop     rsi
0x18000841b  pop     rbx
0x18000841c  pop     rbp
0x18000841d  retn
```
