# EVENT_LOG::LogEventPrivate(ulong,ushort,ushort,ushort const * * const,ulong)

- ea: `0x180020ff0`
- end: `0x1800211d0`
- name: `?LogEventPrivate@EVENT_LOG@@AEAAXKGGQEAPEBGK@Z`
- size: `480`
- prototype: `void __usercall(EVENT_LOG *__hidden this@<rcx>, DWORD dwEventID@<edx>, unsigned __int16@<r8w>, unsigned __int16@<r9w>, const unsigned __int16 **const, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020ed0`

## callees

- `0x180007300`
- `0x180020ba0`
- `0x180020ff0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800211bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800211bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021014`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002103d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021057`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021154`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021014`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002103d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021057`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021154`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180021033`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180021033`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002101c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002101c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002119b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002119b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800211a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800211a6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180021092`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180021092`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x180021132`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x180021132`

## string_xrefs

- `0x18002106f`: `servercommon\inetsrv\iis\iisrearc\core\common\util\eventlog.cxx`
- `0x1800210df`: `servercommon\inetsrv\iis\iisrearc\core\common\util\eventlog.cxx`
- `0x18002116c`: `servercommon\inetsrv\iis\iisrearc\core\common\util\eventlog.cxx`
- `0x180021076`: `Could not retrieve thread impersonation token ( Error %lu)\n`
- `0x1800210c6`: `Attempt to log with no event source\n`

## pseudocode

```c
void __fastcall EVENT_LOG::LogEventPrivate(
        EVENT_LOG *this,
        DWORD dwEventID,
        WORD a3,
        WORD a4,
        const unsigned __int16 **const lpStrings,
        unsigned int RawData)
{
  BOOL v6; // ebx
  DWORD LastError; // ebp
  HANDLE CurrentThread; // rax
  DWORD dwDataSize; // edi
  char v14; // al
  void *v15; // rcx
  unsigned int *lpRawData; // rax
  char wNumStrings; // [rsp+28h] [rbp-70h]
  void *TokenHandle; // [rsp+50h] [rbp-48h] BYREF

  v6 = 0;
  TokenHandle = 0;
  LastError = GetLastError();
  CurrentThread = GetCurrentThread();
  dwDataSize = 4;
  if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
  {
    RevertToSelf();
  }
  else if ( GetLastError() != 1008 )
  {
    if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
    {
      v14 = GetLastError();
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\eventlog.cxx",
        0x1E6u,
        "EVENT_LOG::LogEventPrivate",
        "Could not retrieve thread impersonation token ( Error %lu)\n",
        v14);
    }
    goto LABEL_15;
  }
  v15 = EVENT_LOG::LazyInit(*(_DWORD *)this);
  if ( v15 )
  {
    if ( RawData )
    {
      lpRawData = &RawData;
    }
    else
    {
      lpRawData = 0;
      dwDataSize = 0;
    }
    v6 = ReportEventW(v15, a3, 0, dwEventID, 0, a4, dwDataSize, lpStrings, lpRawData);
    if ( !v6 && (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 8) != 0 )
    {
      GetLastError();
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\eventlog.cxx",
        0x212u,
        "EVENT_LOG::LogEventPrivate",
        "Cannot report event for %p, error %lu\n",
        (char)this);
    }
  }
  else if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 8) != 0 )
  {
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\eventlog.cxx",
      0x1F6u,
      "EVENT_LOG::LogEventPrivate",
      "Attempt to log with no event source\n",
      wNumStrings);
  }
LABEL_15:
  if ( TokenHandle )
  {
    SetThreadToken(0, TokenHandle);
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( v6 )
    SetLastError(LastError);
}

```

## disassembly

```asm
0x180020ff0  push    rbx
0x180020ff2  push    rbp
0x180020ff3  push    rsi
0x180020ff4  push    rdi
0x180020ff5  push    r12
0x180020ff7  push    r14
0x180020ff9  push    r15
0x180020ffb  sub     rsp, 60h
0x180020fff  xor     ebx, ebx
0x180021001  movzx   r14d, r9w
0x180021005  mov     [rsp+98h+TokenHandle], rbx
0x18002100a  movzx   r15d, r8w
0x18002100e  mov     r12d, edx
0x180021011  mov     rsi, rcx
0x180021014  call    cs:__imp_GetLastError
0x18002101a  mov     ebp, eax
0x18002101c  call    cs:__imp_GetCurrentThread
0x180021022  lea     edi, [rbx+4]
0x180021025  mov     rcx, rax; ThreadHandle
0x180021028  mov     edx, edi; DesiredAccess
0x18002102a  lea     r9, [rsp+98h+TokenHandle]; TokenHandle
0x18002102f  lea     r8d, [rbx+1]; OpenAsSelf
0x180021033  call    cs:__imp_OpenThreadToken
0x180021039  test    eax, eax
0x18002103b  jnz     short loc_180021092
0x18002103d  call    cs:__imp_GetLastError
0x180021043  cmp     eax, 3F0h
0x180021048  jz      short loc_180021098
0x18002104a  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180021051  jz      loc_18002118F
0x180021057  call    cs:__imp_GetLastError
0x18002105d  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180021064  lea     r9, aEventLogLogeve; "EVENT_LOG::LogEventPrivate"
0x18002106b  mov     dword ptr [rsp+98h+wNumStrings], eax; char
0x18002106f  lea     rdx, aServercommonIn_9; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180021076  lea     rax, aCouldNotRetrie; "Could not retrieve thread impersonation"...
0x18002107d  mov     r8d, 1E6h; unsigned int
0x180021083  mov     [rsp+98h+lpUserSid], rax; char *
0x180021088  call    PuDbgPrint
0x18002108d  jmp     loc_18002118F
0x180021092  call    cs:__imp_RevertToSelf
0x180021098  mov     ecx, [rsi]; unsigned int
0x18002109a  call    ?LazyInit@EVENT_LOG@@CAPEAXK@Z; EVENT_LOG::LazyInit(ulong)
0x18002109f  mov     rcx, rax; hEventLog
0x1800210a2  test    rax, rax
0x1800210a5  jnz     short loc_1800210F0
0x1800210a7  mov     eax, cs:g_dwDebugFlagsIISUtil
0x1800210ad  test    al, 3
0x1800210af  setnz   cl
0x1800210b2  test    al, 8
0x1800210b4  setnz   al
0x1800210b7  test    al, cl
0x1800210b9  jz      loc_18002118F
0x1800210bf  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800210c6  lea     rax, aAttemptToLogWi; "Attempt to log with no event source\n"
0x1800210cd  lea     r9, aEventLogLogeve; "EVENT_LOG::LogEventPrivate"
0x1800210d4  mov     [rsp+98h+lpUserSid], rax; char *
0x1800210d9  mov     r8d, 1F6h; unsigned int
0x1800210df  lea     rdx, aServercommonIn_9; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800210e6  call    PuDbgPrint
0x1800210eb  jmp     loc_18002118F
0x1800210f0  cmp     [rsp+98h+RawData], ebx
0x1800210f7  jz      short loc_180021103
0x1800210f9  lea     rax, [rsp+98h+RawData]
0x180021101  jmp     short loc_180021107
0x180021103  xor     eax, eax
0x180021105  xor     edi, edi
0x180021107  mov     [rsp+98h+lpRawData], rax; lpRawData
0x18002110c  xor     r8d, r8d; wCategory
0x18002110f  mov     rax, [rsp+98h+arg_20]
0x180021117  mov     r9d, r12d; dwEventID
0x18002111a  mov     [rsp+98h+lpStrings], rax; lpStrings
0x18002111f  movzx   edx, r15w; wType
0x180021123  mov     [rsp+98h+dwDataSize], edi; dwDataSize
0x180021127  mov     [rsp+98h+wNumStrings], r14w; wNumStrings
0x18002112d  mov     [rsp+98h+lpUserSid], rbx; lpUserSid
0x180021132  call    cs:__imp_ReportEventW
0x180021138  mov     ebx, eax
0x18002113a  test    eax, eax
0x18002113c  jnz     short loc_18002118F
0x18002113e  mov     ecx, cs:g_dwDebugFlagsIISUtil
0x180021144  test    cl, 3
0x180021147  setnz   dl
0x18002114a  test    cl, 8
0x18002114d  setnz   cl
0x180021150  test    cl, dl
0x180021152  jz      short loc_18002118F
0x180021154  call    cs:__imp_GetLastError
0x18002115a  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180021161  lea     r9, aEventLogLogeve; "EVENT_LOG::LogEventPrivate"
0x180021168  mov     [rsp+98h+dwDataSize], eax
0x18002116c  lea     rdx, aServercommonIn_9; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180021173  lea     rax, aCannotReportEv; "Cannot report event for %p, error %lu\n"
0x18002117a  mov     qword ptr [rsp+98h+wNumStrings], rsi; char
0x18002117f  mov     r8d, 212h; unsigned int
0x180021185  mov     [rsp+98h+lpUserSid], rax; char *
0x18002118a  call    PuDbgPrint
0x18002118f  mov     rdx, [rsp+98h+TokenHandle]; Token
0x180021194  test    rdx, rdx
0x180021197  jz      short loc_1800211B5
0x180021199  xor     ecx, ecx; Thread
0x18002119b  call    cs:__imp_SetThreadToken
0x1800211a1  mov     rcx, [rsp+98h+TokenHandle]; hObject
0x1800211a6  call    cs:__imp_CloseHandle
0x1800211ac  mov     [rsp+98h+TokenHandle], 0
0x1800211b5  test    ebx, ebx
0x1800211b7  jz      short loc_1800211C1
0x1800211b9  mov     ecx, ebp; dwErrCode
0x1800211bb  call    cs:__imp_SetLastError
0x1800211c1  add     rsp, 60h
0x1800211c5  pop     r15
0x1800211c7  pop     r14
0x1800211c9  pop     r12
0x1800211cb  pop     rdi
0x1800211cc  pop     rsi
0x1800211cd  pop     rbp
0x1800211ce  pop     rbx
0x1800211cf  retn
```
