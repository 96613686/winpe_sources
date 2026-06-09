# CSessionTerminateHandler::StartWait(ICsrEventSink *,void *,void *,long)

- ea: `0x180070c00`
- end: `0x180070dde`
- name: `?StartWait@CSessionTerminateHandler@@QEAAJPEAVICsrEventSink@@PEAX1J@Z`
- size: `478`
- prototype: `int(CSessionTerminateHandler *__hidden this, struct ICsrEventSink *, void *, void *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180029d14`

## callees

- `0x1800074c0`
- `0x18000f260`
- `0x180070c00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070c5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070cd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070d5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070c5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070cd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070d5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180070c1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180070c24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180070c93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180070c9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180070c1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180070c24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180070c93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180070c9c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180070c4f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180070cc7`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180070c4f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180070cc7`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180070d4e`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180070d89`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180070dbc`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180070d4e`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180070d89`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180070dbc`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180070cfb`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180070d9d`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180070cfb`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180070d9d`
- `dwmapi!__imp_DwmpCreateSessionShutdownEvent` at `0x180070d0b`
- `dwmapi!__imp_DwmpCreateSessionShutdownEvent` at `0x180070d0b`

## string_xrefs

- `0x180070ce6`: `DuplicateHandle on InitialCommandProcess failed: 0x%x in %s`
- `0x180070d1a`: `DwmpCreateSessionShutdownEvent failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CSessionTerminateHandler::StartWait(
        HANDLE *this,
        struct ICsrEventSink *a2,
        void *a3,
        void *a4,
        unsigned int a5)
{
  HANDLE CurrentProcess; // rbx
  HANDLE v10; // rax
  signed int LastError; // eax
  signed int v12; // ebx
  const char *v13; // rdx
  HANDLE v14; // rbx
  HANDLE v15; // rax
  signed int v16; // eax
  int SessionShutdownEvent; // eax
  __int64 v18; // rax
  signed int v19; // eax
  __int64 v20; // rax
  __int64 v21; // rax

  CurrentProcess = GetCurrentProcess();
  v10 = GetCurrentProcess();
  if ( !DuplicateHandle(v10, a3, CurrentProcess, this + 4, 0, 0, 6u) )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    if ( v12 < 0 )
    {
      v13 = "DuplicateHandle on WindowsSubSysProcess failed: 0x%x in %s";
LABEL_6:
      _DbgPrintMessage(8, v13, (unsigned int)v12, "CSessionTerminateHandler::StartWait");
      return (unsigned int)v12;
    }
  }
  v14 = GetCurrentProcess();
  v15 = GetCurrentProcess();
  if ( !DuplicateHandle(v15, a4, v14, this + 5, 0, 0, 6u) )
  {
    v16 = GetLastError();
    v12 = v16;
    if ( v16 > 0 )
      v12 = (unsigned __int16)v16 | 0x80070000;
    if ( v12 < 0 )
    {
      v13 = "DuplicateHandle on InitialCommandProcess failed: 0x%x in %s";
      goto LABEL_6;
    }
  }
  if ( a5 == -1
    || a5 == (unsigned int)WTSGetServiceSessionId()
    || (SessionShutdownEvent = DwmpCreateSessionShutdownEvent(a5, this + 6),
        v12 = SessionShutdownEvent,
        SessionShutdownEvent >= 0) )
  {
    SmartPtr<IWinlogonNotify>::operator=(this, a2);
    v18 = RegisterWaitForSingleObjectEx(
            this[4],
            CSessionTerminateHandler::staticWindowsSubSysProcessWaitCallback,
            this,
            0xFFFFFFFFLL,
            24);
    this[1] = (HANDLE)v18;
    if ( v18
      && (v20 = RegisterWaitForSingleObjectEx(
                  this[5],
                  CSessionTerminateHandler::staticInitialCommandProcessWaitCallback,
                  this,
                  0xFFFFFFFFLL,
                  24),
          (this[2] = (HANDLE)v20) != 0)
      && (a5 == -1
       || a5 == (unsigned int)WTSGetServiceSessionId()
       || (v21 = RegisterWaitForSingleObjectEx(
                   this[6],
                   CSessionTerminateHandler::staticWindowManagerProcessWaitCallback,
                   this,
                   0xFFFFFFFFLL,
                   24),
           (this[3] = (HANDLE)v21) != 0)) )
    {
      return 0;
    }
    else
    {
      v19 = GetLastError();
      v12 = v19;
      if ( v19 > 0 )
        return (unsigned __int16)v19 | 0x80070000;
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "DwmpCreateSessionShutdownEvent failed: 0x%x in %s",
      (unsigned int)SessionShutdownEvent,
      "CSessionTerminateHandler::StartWait");
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180070c00  push    rbx
0x180070c02  push    rbp
0x180070c03  push    rsi
0x180070c04  push    rdi
0x180070c05  push    r12
0x180070c07  push    r14
0x180070c09  push    r15
0x180070c0b  sub     rsp, 40h
0x180070c0f  mov     rbp, r9
0x180070c12  mov     rdi, r8
0x180070c15  mov     r12, rdx
0x180070c18  mov     rsi, rcx
0x180070c1b  call    cs:__imp_GetCurrentProcess
0x180070c21  mov     rbx, rax
0x180070c24  call    cs:__imp_GetCurrentProcess
0x180070c2a  mov     [rsp+78h+dwOptions], 6; dwOptions
0x180070c32  lea     r9, [rsi+20h]; lpTargetHandle
0x180070c36  mov     rcx, rax; hSourceProcessHandle
0x180070c39  mov     [rsp+78h+bInheritHandle], 0; bInheritHandle
0x180070c41  mov     r8, rbx; hTargetProcessHandle
0x180070c44  mov     [rsp+78h+dwDesiredAccess], 0; dwDesiredAccess
0x180070c4c  mov     rdx, rdi; hSourceHandle
0x180070c4f  call    cs:__imp_DuplicateHandle
0x180070c55  mov     edi, 80070000h
0x180070c5a  test    eax, eax
0x180070c5c  jnz     short loc_180070C93
0x180070c5e  call    cs:__imp_GetLastError
0x180070c64  mov     ebx, eax
0x180070c66  test    eax, eax
0x180070c68  jle     short loc_180070C6F
0x180070c6a  movzx   ebx, ax
0x180070c6d  or      ebx, edi
0x180070c6f  test    ebx, ebx
0x180070c71  jns     short loc_180070C93
0x180070c73  lea     rdx, aDuplicatehandl_0; "DuplicateHandle on WindowsSubSysProcess"...
0x180070c7a  mov     r8d, ebx
0x180070c7d  lea     r9, aCsessiontermin; "CSessionTerminateHandler::StartWait"
0x180070c84  mov     ecx, 8; int
0x180070c89  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180070c8e  jmp     loc_180070DCD
0x180070c93  call    cs:__imp_GetCurrentProcess
0x180070c99  mov     rbx, rax
0x180070c9c  call    cs:__imp_GetCurrentProcess
0x180070ca2  mov     [rsp+78h+dwOptions], 6; dwOptions
0x180070caa  lea     r9, [rsi+28h]; lpTargetHandle
0x180070cae  mov     rcx, rax; hSourceProcessHandle
0x180070cb1  mov     [rsp+78h+bInheritHandle], 0; bInheritHandle
0x180070cb9  mov     r8, rbx; hTargetProcessHandle
0x180070cbc  mov     [rsp+78h+dwDesiredAccess], 0; dwDesiredAccess
0x180070cc4  mov     rdx, rbp; hSourceHandle
0x180070cc7  call    cs:__imp_DuplicateHandle
0x180070ccd  test    eax, eax
0x180070ccf  jnz     short loc_180070CEF
0x180070cd1  call    cs:__imp_GetLastError
0x180070cd7  mov     ebx, eax
0x180070cd9  test    eax, eax
0x180070cdb  jle     short loc_180070CE2
0x180070cdd  movzx   ebx, ax
0x180070ce0  or      ebx, edi
0x180070ce2  test    ebx, ebx
0x180070ce4  jns     short loc_180070CEF
0x180070ce6  lea     rdx, aDuplicatehandl_5; "DuplicateHandle on InitialCommandProces"...
0x180070ced  jmp     short loc_180070C7A
0x180070cef  mov     edi, [rsp+78h+arg_20]
0x180070cf6  cmp     edi, 0FFFFFFFFh
0x180070cf9  jz      short loc_180070D26
0x180070cfb  call    cs:__imp_WTSGetServiceSessionId
0x180070d01  cmp     edi, eax
0x180070d03  jz      short loc_180070D26
0x180070d05  lea     rdx, [rsi+30h]
0x180070d09  mov     ecx, edi
0x180070d0b  call    cs:__imp_DwmpCreateSessionShutdownEvent
0x180070d11  mov     ebx, eax
0x180070d13  test    eax, eax
0x180070d15  jns     short loc_180070D26
0x180070d17  mov     r8d, eax
0x180070d1a  lea     rdx, aDwmpcreatesess; "DwmpCreateSessionShutdownEvent failed: "...
0x180070d21  jmp     loc_180070C7D
0x180070d26  mov     rdx, r12
0x180070d29  mov     rcx, rsi
0x180070d2c  call    ??4?$SmartPtr@VIWinlogonNotify@@@@QEAAAEAV0@PEAVIWinlogonNotify@@@Z; SmartPtr<IWinlogonNotify>::operator=(IWinlogonNotify *)
0x180070d31  mov     rcx, [rsi+20h]
0x180070d35  lea     rdx, ?staticWindowsSubSysProcessWaitCallback@CSessionTerminateHandler@@CAXPEAXE@Z; CSessionTerminateHandler::staticWindowsSubSysProcessWaitCallback(void *,uchar)
0x180070d3c  or      ebp, 0FFFFFFFFh
0x180070d3f  mov     ebx, 18h
0x180070d44  mov     r9d, ebp
0x180070d47  mov     [rsp+78h+dwDesiredAccess], ebx
0x180070d4b  mov     r8, rsi
0x180070d4e  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180070d54  mov     [rsi+8], rax
0x180070d58  test    rax, rax
0x180070d5b  jnz     short loc_180070D74
0x180070d5d  call    cs:__imp_GetLastError
0x180070d63  mov     ebx, eax
0x180070d65  test    eax, eax
0x180070d67  jle     short loc_180070DCD
0x180070d69  movzx   ebx, ax
0x180070d6c  or      ebx, 80070000h
0x180070d72  jmp     short loc_180070DCD
0x180070d74  mov     rcx, [rsi+28h]
0x180070d78  lea     rdx, ?staticInitialCommandProcessWaitCallback@CSessionTerminateHandler@@CAXPEAXE@Z; CSessionTerminateHandler::staticInitialCommandProcessWaitCallback(void *,uchar)
0x180070d7f  mov     r9d, ebp
0x180070d82  mov     [rsp+78h+dwDesiredAccess], ebx
0x180070d86  mov     r8, rsi
0x180070d89  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180070d8f  mov     [rsi+10h], rax
0x180070d93  test    rax, rax
0x180070d96  jz      short loc_180070D5D
0x180070d98  cmp     edi, 0FFFFFFFFh
0x180070d9b  jz      short loc_180070DCB
0x180070d9d  call    cs:__imp_WTSGetServiceSessionId
0x180070da3  cmp     edi, eax
0x180070da5  jz      short loc_180070DCB
0x180070da7  mov     rcx, [rsi+30h]
0x180070dab  lea     rdx, ?staticWindowManagerProcessWaitCallback@CSessionTerminateHandler@@CAXPEAXE@Z; CSessionTerminateHandler::staticWindowManagerProcessWaitCallback(void *,uchar)
0x180070db2  mov     r9d, ebp
0x180070db5  mov     [rsp+78h+dwDesiredAccess], ebx
0x180070db9  mov     r8, rsi
0x180070dbc  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180070dc2  mov     [rsi+18h], rax
0x180070dc6  test    rax, rax
0x180070dc9  jz      short loc_180070D5D
0x180070dcb  xor     ebx, ebx
0x180070dcd  mov     eax, ebx
0x180070dcf  add     rsp, 40h
0x180070dd3  pop     r15
0x180070dd5  pop     r14
0x180070dd7  pop     r12
0x180070dd9  pop     rdi
0x180070dda  pop     rsi
0x180070ddb  pop     rbp
0x180070ddc  pop     rbx
0x180070ddd  retn
```
