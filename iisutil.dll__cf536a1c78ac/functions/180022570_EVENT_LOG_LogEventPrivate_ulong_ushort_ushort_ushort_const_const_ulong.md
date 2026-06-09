# EVENT_LOG::LogEventPrivate(ulong,ushort,ushort,ushort const * * const,ulong)

- ea: `0x180022570`
- end: `0x180022793`
- name: `?LogEventPrivate@EVENT_LOG@@AEAAXKGGQEAPEBGK@Z`
- size: `547`
- prototype: `void __fastcall(EVENT_LOG *this, DWORD dwEventID, WORD, WORD, const unsigned __int16 **const lpStrings, unsigned int RawData)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022450`

## callees

- `0x180008000`
- `0x1800220c0`
- `0x180022570`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022777`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022777`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022594`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800225cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800225ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800226fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022594`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800225cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800225ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800226fe`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800225bf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800225bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800225a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800225a2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002274b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002274b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002275c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002275c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180022630`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180022630`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x1800226d6`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x1800226d6`

## string_xrefs

- `0x18002260d`: `servercommon\inetsrv\iis\iisrearc\core\common\util\eventlog.cxx`
- `0x180022683`: `servercommon\inetsrv\iis\iisrearc\core\common\util\eventlog.cxx`
- `0x18002271c`: `servercommon\inetsrv\iis\iisrearc\core\common\util\eventlog.cxx`
- `0x180022614`: `Could not retrieve thread impersonation token ( Error %lu)\n`
- `0x18002266a`: `Attempt to log with no event source\n`

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
0x180022570  push    rbx
0x180022572  push    rbp
0x180022573  push    rsi
0x180022574  push    rdi
0x180022575  push    r12
0x180022577  push    r14
0x180022579  push    r15
0x18002257b  sub     rsp, 60h
0x18002257f  xor     ebx, ebx
0x180022581  movzx   r14d, r9w
0x180022585  mov     [rsp+98h+TokenHandle], rbx
0x18002258a  movzx   r15d, r8w
0x18002258e  mov     r12d, edx
0x180022591  mov     rsi, rcx
0x180022594  call    cs:__imp_GetLastError
0x18002259b  nop     dword ptr [rax+rax+00h]
0x1800225a0  mov     ebp, eax
0x1800225a2  call    cs:__imp_GetCurrentThread
0x1800225a9  nop     dword ptr [rax+rax+00h]
0x1800225ae  lea     edi, [rbx+4]
0x1800225b1  mov     rcx, rax; ThreadHandle
0x1800225b4  mov     edx, edi; DesiredAccess
0x1800225b6  lea     r9, [rsp+98h+TokenHandle]; TokenHandle
0x1800225bb  lea     r8d, [rbx+1]; OpenAsSelf
0x1800225bf  call    cs:__imp_OpenThreadToken
0x1800225c6  nop     dword ptr [rax+rax+00h]
0x1800225cb  test    eax, eax
0x1800225cd  jnz     short loc_180022630
0x1800225cf  call    cs:__imp_GetLastError
0x1800225d6  nop     dword ptr [rax+rax+00h]
0x1800225db  cmp     eax, 3F0h
0x1800225e0  jz      short loc_18002263C
0x1800225e2  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800225e9  jz      loc_18002273F
0x1800225ef  call    cs:__imp_GetLastError
0x1800225f6  nop     dword ptr [rax+rax+00h]
0x1800225fb  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180022602  lea     r9, aEventLogLogeve; "EVENT_LOG::LogEventPrivate"
0x180022609  mov     dword ptr [rsp+98h+wNumStrings], eax; char
0x18002260d  lea     rdx, aServercommonIn_9; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180022614  lea     rax, aCouldNotRetrie; "Could not retrieve thread impersonation"...
0x18002261b  mov     r8d, 1E6h; unsigned int
0x180022621  mov     [rsp+98h+lpUserSid], rax; char *
0x180022626  call    PuDbgPrint
0x18002262b  jmp     loc_18002273F
0x180022630  call    cs:__imp_RevertToSelf
0x180022637  nop     dword ptr [rax+rax+00h]
0x18002263c  mov     ecx, [rsi]; unsigned int
0x18002263e  call    ?LazyInit@EVENT_LOG@@CAPEAXK@Z; EVENT_LOG::LazyInit(ulong)
0x180022643  mov     rcx, rax; hEventLog
0x180022646  test    rax, rax
0x180022649  jnz     short loc_180022694
0x18002264b  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180022651  test    al, 3
0x180022653  setnz   cl
0x180022656  test    al, 8
0x180022658  setnz   al
0x18002265b  test    al, cl
0x18002265d  jz      loc_18002273F
0x180022663  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002266a  lea     rax, aAttemptToLogWi; "Attempt to log with no event source\n"
0x180022671  lea     r9, aEventLogLogeve; "EVENT_LOG::LogEventPrivate"
0x180022678  mov     [rsp+98h+lpUserSid], rax; char *
0x18002267d  mov     r8d, 1F6h; unsigned int
0x180022683  lea     rdx, aServercommonIn_9; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002268a  call    PuDbgPrint
0x18002268f  jmp     loc_18002273F
0x180022694  cmp     [rsp+98h+RawData], ebx
0x18002269b  jz      short loc_1800226A7
0x18002269d  lea     rax, [rsp+98h+RawData]
0x1800226a5  jmp     short loc_1800226AB
0x1800226a7  xor     eax, eax
0x1800226a9  xor     edi, edi
0x1800226ab  mov     [rsp+98h+lpRawData], rax; lpRawData
0x1800226b0  xor     r8d, r8d; wCategory
0x1800226b3  mov     rax, [rsp+98h+arg_20]
0x1800226bb  mov     r9d, r12d; dwEventID
0x1800226be  mov     [rsp+98h+lpStrings], rax; lpStrings
0x1800226c3  movzx   edx, r15w; wType
0x1800226c7  mov     [rsp+98h+dwDataSize], edi; dwDataSize
0x1800226cb  mov     [rsp+98h+wNumStrings], r14w; wNumStrings
0x1800226d1  mov     [rsp+98h+lpUserSid], rbx; lpUserSid
0x1800226d6  call    cs:__imp_ReportEventW
0x1800226dd  nop     dword ptr [rax+rax+00h]
0x1800226e2  mov     ebx, eax
0x1800226e4  test    eax, eax
0x1800226e6  jnz     short loc_18002273F
0x1800226e8  mov     ecx, cs:g_dwDebugFlagsIISUtil
0x1800226ee  test    cl, 3
0x1800226f1  setnz   dl
0x1800226f4  test    cl, 8
0x1800226f7  setnz   cl
0x1800226fa  test    cl, dl
0x1800226fc  jz      short loc_18002273F
0x1800226fe  call    cs:__imp_GetLastError
0x180022705  nop     dword ptr [rax+rax+00h]
0x18002270a  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180022711  lea     r9, aEventLogLogeve; "EVENT_LOG::LogEventPrivate"
0x180022718  mov     [rsp+98h+dwDataSize], eax
0x18002271c  lea     rdx, aServercommonIn_9; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180022723  lea     rax, aCannotReportEv; "Cannot report event for %p, error %lu\n"
0x18002272a  mov     qword ptr [rsp+98h+wNumStrings], rsi; char
0x18002272f  mov     r8d, 212h; unsigned int
0x180022735  mov     [rsp+98h+lpUserSid], rax; char *
0x18002273a  call    PuDbgPrint
0x18002273f  mov     rdx, [rsp+98h+TokenHandle]; Token
0x180022744  test    rdx, rdx
0x180022747  jz      short loc_180022771
0x180022749  xor     ecx, ecx; Thread
0x18002274b  call    cs:__imp_SetThreadToken
0x180022752  nop     dword ptr [rax+rax+00h]
0x180022757  mov     rcx, [rsp+98h+TokenHandle]; hObject
0x18002275c  call    cs:__imp_CloseHandle
0x180022763  nop     dword ptr [rax+rax+00h]
0x180022768  mov     [rsp+98h+TokenHandle], 0
0x180022771  test    ebx, ebx
0x180022773  jz      short loc_180022783
0x180022775  mov     ecx, ebp; dwErrCode
0x180022777  call    cs:__imp_SetLastError
0x18002277e  nop     dword ptr [rax+rax+00h]
0x180022783  add     rsp, 60h
0x180022787  pop     r15
0x180022789  pop     r14
0x18002278b  pop     r12
0x18002278d  pop     rdi
0x18002278e  pop     rsi
0x18002278f  pop     rbp
0x180022790  pop     rbx
0x180022791  retn
```
