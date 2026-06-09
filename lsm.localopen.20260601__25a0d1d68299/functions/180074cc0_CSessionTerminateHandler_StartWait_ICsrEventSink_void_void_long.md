# CSessionTerminateHandler::StartWait(ICsrEventSink *,void *,void *,long)

- ea: `0x180074cc0`
- end: `0x180074f00`
- name: `?StartWait@CSessionTerminateHandler@@QEAAJPEAVICsrEventSink@@PEAX1J@Z`
- size: `576`
- prototype: `int(CSessionTerminateHandler *__hidden this, struct ICsrEventSink *, void *, void *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180018260`

## callees

- `0x1800077a0`
- `0x180012e04`
- `0x180074cc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074d30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074dbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074e62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074d30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074dbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074e62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180074cdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180074cea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180074d6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180074d7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180074cdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180074cea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180074d6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180074d7a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180074d1b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180074dab`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180074d1b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180074dab`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180074e4d`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180074e94`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180074ed3`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180074e4d`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180074e94`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180074ed3`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180074dee`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180074eae`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180074dee`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180074eae`
- `dwmapi!__imp_DwmpCreateSessionShutdownEvent` at `0x180074e04`
- `dwmapi!__imp_DwmpCreateSessionShutdownEvent` at `0x180074e04`

## string_xrefs

- `0x180074dd6`: `DuplicateHandle on InitialCommandProcess failed: 0x%x in %s`
- `0x180074e19`: `DwmpCreateSessionShutdownEvent failed: 0x%x in %s`

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
0x180074cc0  push    rbx
0x180074cc2  push    rbp
0x180074cc3  push    rsi
0x180074cc4  push    rdi
0x180074cc5  push    r12
0x180074cc7  push    r14
0x180074cc9  push    r15
0x180074ccb  sub     rsp, 40h
0x180074ccf  mov     rbp, r9
0x180074cd2  mov     rdi, r8
0x180074cd5  mov     r12, rdx
0x180074cd8  mov     rsi, rcx
0x180074cdb  call    cs:__imp_GetCurrentProcess
0x180074ce2  nop     dword ptr [rax+rax+00h]
0x180074ce7  mov     rbx, rax
0x180074cea  call    cs:__imp_GetCurrentProcess
0x180074cf1  nop     dword ptr [rax+rax+00h]
0x180074cf6  mov     [rsp+78h+dwOptions], 6; dwOptions
0x180074cfe  lea     r9, [rsi+20h]; lpTargetHandle
0x180074d02  mov     rcx, rax; hSourceProcessHandle
0x180074d05  mov     [rsp+78h+bInheritHandle], 0; bInheritHandle
0x180074d0d  mov     r8, rbx; hTargetProcessHandle
0x180074d10  mov     [rsp+78h+dwDesiredAccess], 0; dwDesiredAccess
0x180074d18  mov     rdx, rdi; hSourceHandle
0x180074d1b  call    cs:__imp_DuplicateHandle
0x180074d22  nop     dword ptr [rax+rax+00h]
0x180074d27  mov     edi, 80070000h
0x180074d2c  test    eax, eax
0x180074d2e  jnz     short loc_180074D6B
0x180074d30  call    cs:__imp_GetLastError
0x180074d37  nop     dword ptr [rax+rax+00h]
0x180074d3c  mov     ebx, eax
0x180074d3e  test    eax, eax
0x180074d40  jle     short loc_180074D47
0x180074d42  movzx   ebx, ax
0x180074d45  or      ebx, edi
0x180074d47  test    ebx, ebx
0x180074d49  jns     short loc_180074D6B
0x180074d4b  lea     rdx, aDuplicatehandl_0; "DuplicateHandle on WindowsSubSysProcess"...
0x180074d52  mov     r8d, ebx
0x180074d55  lea     r9, aCsessiontermin; "CSessionTerminateHandler::StartWait"
0x180074d5c  mov     ecx, 8; int
0x180074d61  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180074d66  jmp     loc_180074EEE
0x180074d6b  call    cs:__imp_GetCurrentProcess
0x180074d72  nop     dword ptr [rax+rax+00h]
0x180074d77  mov     rbx, rax
0x180074d7a  call    cs:__imp_GetCurrentProcess
0x180074d81  nop     dword ptr [rax+rax+00h]
0x180074d86  mov     [rsp+78h+dwOptions], 6; dwOptions
0x180074d8e  lea     r9, [rsi+28h]; lpTargetHandle
0x180074d92  mov     rcx, rax; hSourceProcessHandle
0x180074d95  mov     [rsp+78h+bInheritHandle], 0; bInheritHandle
0x180074d9d  mov     r8, rbx; hTargetProcessHandle
0x180074da0  mov     [rsp+78h+dwDesiredAccess], 0; dwDesiredAccess
0x180074da8  mov     rdx, rbp; hSourceHandle
0x180074dab  call    cs:__imp_DuplicateHandle
0x180074db2  nop     dword ptr [rax+rax+00h]
0x180074db7  test    eax, eax
0x180074db9  jnz     short loc_180074DE2
0x180074dbb  call    cs:__imp_GetLastError
0x180074dc2  nop     dword ptr [rax+rax+00h]
0x180074dc7  mov     ebx, eax
0x180074dc9  test    eax, eax
0x180074dcb  jle     short loc_180074DD2
0x180074dcd  movzx   ebx, ax
0x180074dd0  or      ebx, edi
0x180074dd2  test    ebx, ebx
0x180074dd4  jns     short loc_180074DE2
0x180074dd6  lea     rdx, aDuplicatehandl_5; "DuplicateHandle on InitialCommandProces"...
0x180074ddd  jmp     loc_180074D52
0x180074de2  mov     edi, [rsp+78h+arg_20]
0x180074de9  cmp     edi, 0FFFFFFFFh
0x180074dec  jz      short loc_180074E25
0x180074dee  call    cs:__imp_WTSGetServiceSessionId
0x180074df5  nop     dword ptr [rax+rax+00h]
0x180074dfa  cmp     edi, eax
0x180074dfc  jz      short loc_180074E25
0x180074dfe  lea     rdx, [rsi+30h]
0x180074e02  mov     ecx, edi
0x180074e04  call    cs:__imp_DwmpCreateSessionShutdownEvent
0x180074e0b  nop     dword ptr [rax+rax+00h]
0x180074e10  mov     ebx, eax
0x180074e12  test    eax, eax
0x180074e14  jns     short loc_180074E25
0x180074e16  mov     r8d, eax
0x180074e19  lea     rdx, aDwmpcreatesess; "DwmpCreateSessionShutdownEvent failed: "...
0x180074e20  jmp     loc_180074D55
0x180074e25  mov     rdx, r12
0x180074e28  mov     rcx, rsi
0x180074e2b  call    ??4?$SmartPtr@VIWinlogonNotify@@@@QEAAAEAV0@PEAVIWinlogonNotify@@@Z; SmartPtr<IWinlogonNotify>::operator=(IWinlogonNotify *)
0x180074e30  mov     rcx, [rsi+20h]
0x180074e34  lea     rdx, ?staticWindowsSubSysProcessWaitCallback@CSessionTerminateHandler@@CAXPEAXE@Z; CSessionTerminateHandler::staticWindowsSubSysProcessWaitCallback(void *,uchar)
0x180074e3b  or      ebp, 0FFFFFFFFh
0x180074e3e  mov     ebx, 18h
0x180074e43  mov     r9d, ebp
0x180074e46  mov     [rsp+78h+dwDesiredAccess], ebx
0x180074e4a  mov     r8, rsi
0x180074e4d  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180074e54  nop     dword ptr [rax+rax+00h]
0x180074e59  mov     [rsi+8], rax
0x180074e5d  test    rax, rax
0x180074e60  jnz     short loc_180074E7F
0x180074e62  call    cs:__imp_GetLastError
0x180074e69  nop     dword ptr [rax+rax+00h]
0x180074e6e  mov     ebx, eax
0x180074e70  test    eax, eax
0x180074e72  jle     short loc_180074EEE
0x180074e74  movzx   ebx, ax
0x180074e77  or      ebx, 80070000h
0x180074e7d  jmp     short loc_180074EEE
0x180074e7f  mov     rcx, [rsi+28h]
0x180074e83  lea     rdx, ?staticInitialCommandProcessWaitCallback@CSessionTerminateHandler@@CAXPEAXE@Z; CSessionTerminateHandler::staticInitialCommandProcessWaitCallback(void *,uchar)
0x180074e8a  mov     r9d, ebp
0x180074e8d  mov     [rsp+78h+dwDesiredAccess], ebx
0x180074e91  mov     r8, rsi
0x180074e94  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180074e9b  nop     dword ptr [rax+rax+00h]
0x180074ea0  mov     [rsi+10h], rax
0x180074ea4  test    rax, rax
0x180074ea7  jz      short loc_180074E62
0x180074ea9  cmp     edi, 0FFFFFFFFh
0x180074eac  jz      short loc_180074EEC
0x180074eae  call    cs:__imp_WTSGetServiceSessionId
0x180074eb5  nop     dword ptr [rax+rax+00h]
0x180074eba  cmp     edi, eax
0x180074ebc  jz      short loc_180074EEC
0x180074ebe  mov     rcx, [rsi+30h]
0x180074ec2  lea     rdx, ?staticWindowManagerProcessWaitCallback@CSessionTerminateHandler@@CAXPEAXE@Z; CSessionTerminateHandler::staticWindowManagerProcessWaitCallback(void *,uchar)
0x180074ec9  mov     r9d, ebp
0x180074ecc  mov     [rsp+78h+dwDesiredAccess], ebx
0x180074ed0  mov     r8, rsi
0x180074ed3  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180074eda  nop     dword ptr [rax+rax+00h]
0x180074edf  mov     [rsi+18h], rax
0x180074ee3  test    rax, rax
0x180074ee6  jz      loc_180074E62
0x180074eec  xor     ebx, ebx
0x180074eee  mov     eax, ebx
0x180074ef0  add     rsp, 40h
0x180074ef4  pop     r15
0x180074ef6  pop     r14
0x180074ef8  pop     r12
0x180074efa  pop     rdi
0x180074efb  pop     rsi
0x180074efc  pop     rbp
0x180074efd  pop     rbx
0x180074efe  retn
```
