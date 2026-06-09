# EVENT_LOG::LazyInit(ulong)

- ea: `0x1800220c0`
- end: `0x18002224d`
- name: `?LazyInit@EVENT_LOG@@CAPEAXK@Z`
- size: `397`
- prototype: `void *__fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022570`

## callees

- `0x180008000`
- `0x1800220c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800221aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800221aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002222d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002222d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022109`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022109`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x180022143`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x180022143`

## string_xrefs

- `0x180022207`: `servercommon\inetsrv\iis\iisrearc\core\common\util\eventlog.cxx`

## pseudocode

```c
__int64 __fastcall EVENT_LOG::LazyInit(unsigned int a1)
{
  __int64 v1; // rdi
  __int64 v2; // rbx
  const WCHAR *v3; // rsi
  const WCHAR *v4; // rdx
  unsigned int v5; // r8d
  char *v6; // rax
  DWORD LastError; // eax
  bool v8; // zf

  v1 = 0;
  if ( a1 != -1 && a1 < EVENT_LOG::sm_cEventLogSource )
  {
    v2 = 3LL * a1;
    if ( *((_DWORD *)EVENT_LOG::sm_pEventLogSource + 6 * a1) )
      return *((_QWORD *)EVENT_LOG::sm_pEventLogSource + 3 * a1 + 1);
    EnterCriticalSection(&EVENT_LOG::sm_csLock);
    if ( *((_DWORD *)EVENT_LOG::sm_pEventLogSource + 2 * v2) )
    {
      v1 = *((_QWORD *)EVENT_LOG::sm_pEventLogSource + v2 + 1);
LABEL_19:
      LeaveCriticalSection(&EVENT_LOG::sm_csLock);
      return v1;
    }
    v3 = &pServiceName;
    v4 = &pServiceName;
    if ( *((_QWORD *)EVENT_LOG::sm_pEventLogSource + v2 + 2) )
      v4 = (const WCHAR *)*((_QWORD *)EVENT_LOG::sm_pEventLogSource + v2 + 2);
    *((_QWORD *)EVENT_LOG::sm_pEventLogSource + v2 + 1) = RegisterEventSourceW(0, v4);
    if ( *((_QWORD *)EVENT_LOG::sm_pEventLogSource + v2 + 1) )
    {
      v1 = *((_QWORD *)EVENT_LOG::sm_pEventLogSource + v2 + 1);
      if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 8) != 0 )
      {
        v5 = 382;
        if ( *((_QWORD *)EVENT_LOG::sm_pEventLogSource + v2 + 2) )
          LOBYTE(v3) = *((_QWORD *)EVENT_LOG::sm_pEventLogSource + v2 + 2);
        v6 = " Event Log for %S initialized (hEventSource=%p)\n";
LABEL_17:
        PuDbgPrint(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\eventlog.cxx",
          v5,
          "EVENT_LOG::LazyInit",
          v6,
          (char)v3);
      }
    }
    else
    {
      LastError = GetLastError();
      v8 = (g_dwDebugFlagsIISUtil & 3) == 0;
      *((_DWORD *)EVENT_LOG::sm_pEventLogSource + 2 * v2 + 1) = LastError;
      if ( !v8 )
      {
        v5 = 391;
        v6 = "Could not register event source (%S) ( Error %lu)\n";
        if ( *((_QWORD *)EVENT_LOG::sm_pEventLogSource + v2 + 2) )
          LOBYTE(v3) = *((_QWORD *)EVENT_LOG::sm_pEventLogSource + v2 + 2);
        goto LABEL_17;
      }
    }
    *((_DWORD *)EVENT_LOG::sm_pEventLogSource + 2 * v2) = 1;
    goto LABEL_19;
  }
  return v1;
}

```

## disassembly

```asm
0x1800220c0  mov     [rsp+arg_0], rbx
0x1800220c5  mov     [rsp+arg_8], rsi
0x1800220ca  push    rdi
0x1800220cb  sub     rsp, 40h
0x1800220cf  xor     edi, edi
0x1800220d1  cmp     ecx, 0FFFFFFFFh
0x1800220d4  jz      loc_180022239
0x1800220da  cmp     ecx, cs:?sm_cEventLogSource@EVENT_LOG@@0KA; ulong EVENT_LOG::sm_cEventLogSource
0x1800220e0  jnb     loc_180022239
0x1800220e6  mov     eax, ecx
0x1800220e8  lea     rbx, [rax+rax*2]
0x1800220ec  mov     rax, cs:?sm_pEventLogSource@EVENT_LOG@@0PEAU_EVENT_LOG_SOURCE@@EA; _EVENT_LOG_SOURCE * EVENT_LOG::sm_pEventLogSource
0x1800220f3  cmp     [rax+rbx*8], edi
0x1800220f6  jz      short loc_180022102
0x1800220f8  mov     rdi, [rax+rbx*8+8]
0x1800220fd  jmp     loc_180022239
0x180022102  lea     rcx, ?sm_csLock@EVENT_LOG@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180022109  call    cs:__imp_EnterCriticalSection
0x180022110  nop     dword ptr [rax+rax+00h]
0x180022115  mov     rax, cs:?sm_pEventLogSource@EVENT_LOG@@0PEAU_EVENT_LOG_SOURCE@@EA; _EVENT_LOG_SOURCE * EVENT_LOG::sm_pEventLogSource
0x18002211c  cmp     [rax+rbx*8], edi
0x18002211f  jz      short loc_18002212B
0x180022121  mov     rdi, [rax+rbx*8+8]
0x180022126  jmp     loc_180022226
0x18002212b  mov     rax, [rax+rbx*8+10h]
0x180022130  lea     rsi, pServiceName
0x180022137  test    rax, rax
0x18002213a  mov     rdx, rsi
0x18002213d  cmovnz  rdx, rax; lpSourceName
0x180022141  xor     ecx, ecx; lpUNCServerName
0x180022143  call    cs:__imp_RegisterEventSourceW
0x18002214a  nop     dword ptr [rax+rax+00h]
0x18002214f  mov     rcx, rax
0x180022152  mov     rax, cs:?sm_pEventLogSource@EVENT_LOG@@0PEAU_EVENT_LOG_SOURCE@@EA; _EVENT_LOG_SOURCE * EVENT_LOG::sm_pEventLogSource
0x180022159  mov     [rax+rbx*8+8], rcx
0x18002215e  mov     r8, cs:?sm_pEventLogSource@EVENT_LOG@@0PEAU_EVENT_LOG_SOURCE@@EA; _EVENT_LOG_SOURCE * EVENT_LOG::sm_pEventLogSource
0x180022165  mov     rdx, [r8+rbx*8+8]
0x18002216a  test    rdx, rdx
0x18002216d  jz      short loc_1800221AA
0x18002216f  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180022175  mov     rdi, rdx
0x180022178  test    al, 3
0x18002217a  setnz   cl
0x18002217d  test    al, 8
0x18002217f  setnz   al
0x180022182  test    al, cl
0x180022184  jz      loc_180022218
0x18002218a  mov     rax, [r8+rbx*8+10h]
0x18002218f  mov     r8d, 17Eh
0x180022195  test    rax, rax
0x180022198  mov     [rsp+48h+var_18], rdx
0x18002219d  cmovnz  rsi, rax
0x1800221a1  lea     rax, aEventLogForSIn; " Event Log for %S initialized (hEventSo"...
0x1800221a8  jmp     short loc_1800221F4
0x1800221aa  call    cs:__imp_GetLastError
0x1800221b1  nop     dword ptr [rax+rax+00h]
0x1800221b6  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800221bd  mov     ecx, eax
0x1800221bf  mov     rax, cs:?sm_pEventLogSource@EVENT_LOG@@0PEAU_EVENT_LOG_SOURCE@@EA; _EVENT_LOG_SOURCE * EVENT_LOG::sm_pEventLogSource
0x1800221c6  mov     [rax+rbx*8+4], ecx
0x1800221ca  jz      short loc_180022218
0x1800221cc  mov     rax, cs:?sm_pEventLogSource@EVENT_LOG@@0PEAU_EVENT_LOG_SOURCE@@EA; _EVENT_LOG_SOURCE * EVENT_LOG::sm_pEventLogSource
0x1800221d3  mov     r8d, 187h; unsigned int
0x1800221d9  mov     rcx, [rax+rbx*8+10h]
0x1800221de  mov     edx, [rax+rbx*8+4]
0x1800221e2  test    rcx, rcx
0x1800221e5  mov     dword ptr [rsp+48h+var_18], edx
0x1800221e9  lea     rax, aCouldNotRegist; "Could not register event source (%S) ( "...
0x1800221f0  cmovnz  rsi, rcx
0x1800221f4  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800221fb  lea     r9, aEventLogLazyin; "EVENT_LOG::LazyInit"
0x180022202  mov     qword ptr [rsp+48h+var_20], rsi; char
0x180022207  lea     rdx, aServercommonIn_9; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002220e  mov     [rsp+48h+var_28], rax; char *
0x180022213  call    PuDbgPrint
0x180022218  mov     rdx, cs:?sm_pEventLogSource@EVENT_LOG@@0PEAU_EVENT_LOG_SOURCE@@EA; _EVENT_LOG_SOURCE * EVENT_LOG::sm_pEventLogSource
0x18002221f  mov     dword ptr [rdx+rbx*8], 1
0x180022226  lea     rcx, ?sm_csLock@EVENT_LOG@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002222d  call    cs:__imp_LeaveCriticalSection
0x180022234  nop     dword ptr [rax+rax+00h]
0x180022239  mov     rbx, [rsp+48h+arg_0]
0x18002223e  mov     rax, rdi
0x180022241  mov     rsi, [rsp+48h+arg_8]
0x180022246  add     rsp, 40h
0x18002224a  pop     rdi
0x18002224b  retn
```
