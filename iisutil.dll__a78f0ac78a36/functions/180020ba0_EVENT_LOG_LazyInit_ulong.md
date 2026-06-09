# EVENT_LOG::LazyInit(ulong)

- ea: `0x180020ba0`
- end: `0x180020d14`
- name: `?LazyInit@EVENT_LOG@@CAPEAXK@Z`
- size: `372`
- prototype: `void *__fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180020ff0`

## callees

- `0x180007300`
- `0x180020ba0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020cfb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020cfb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020be9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020be9`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x180020c1d`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x180020c1d`

## string_xrefs

- `0x180020cd5`: `servercommon\inetsrv\iis\iisrearc\core\common\util\eventlog.cxx`

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
0x180020ba0  mov     [rsp+arg_0], rbx
0x180020ba5  mov     [rsp+arg_8], rsi
0x180020baa  push    rdi
0x180020bab  sub     rsp, 40h
0x180020baf  xor     edi, edi
0x180020bb1  cmp     ecx, 0FFFFFFFFh
0x180020bb4  jz      loc_180020D01
0x180020bba  cmp     ecx, cs:?sm_cEventLogSource@EVENT_LOG@@0KA; ulong EVENT_LOG::sm_cEventLogSource
0x180020bc0  jnb     loc_180020D01
0x180020bc6  mov     eax, ecx
0x180020bc8  lea     rbx, [rax+rax*2]
0x180020bcc  mov     rax, cs:?sm_pEventLogSource@EVENT_LOG@@0PEAU_EVENT_LOG_SOURCE@@EA; _EVENT_LOG_SOURCE * EVENT_LOG::sm_pEventLogSource
0x180020bd3  cmp     [rax+rbx*8], edi
0x180020bd6  jz      short loc_180020BE2
0x180020bd8  mov     rdi, [rax+rbx*8+8]
0x180020bdd  jmp     loc_180020D01
0x180020be2  lea     rcx, ?sm_csLock@EVENT_LOG@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180020be9  call    cs:__imp_EnterCriticalSection
0x180020bef  mov     rax, cs:?sm_pEventLogSource@EVENT_LOG@@0PEAU_EVENT_LOG_SOURCE@@EA; _EVENT_LOG_SOURCE * EVENT_LOG::sm_pEventLogSource
0x180020bf6  cmp     [rax+rbx*8], edi
0x180020bf9  jz      short loc_180020C05
0x180020bfb  mov     rdi, [rax+rbx*8+8]
0x180020c00  jmp     loc_180020CF4
0x180020c05  mov     rax, [rax+rbx*8+10h]
0x180020c0a  lea     rsi, pServiceName
0x180020c11  test    rax, rax
0x180020c14  mov     rdx, rsi
0x180020c17  cmovnz  rdx, rax; lpSourceName
0x180020c1b  xor     ecx, ecx; lpUNCServerName
0x180020c1d  call    cs:__imp_RegisterEventSourceW
0x180020c23  mov     rcx, rax
0x180020c26  mov     rax, cs:?sm_pEventLogSource@EVENT_LOG@@0PEAU_EVENT_LOG_SOURCE@@EA; _EVENT_LOG_SOURCE * EVENT_LOG::sm_pEventLogSource
0x180020c2d  mov     [rax+rbx*8+8], rcx
0x180020c32  mov     r8, cs:?sm_pEventLogSource@EVENT_LOG@@0PEAU_EVENT_LOG_SOURCE@@EA; _EVENT_LOG_SOURCE * EVENT_LOG::sm_pEventLogSource
0x180020c39  mov     rdx, [r8+rbx*8+8]
0x180020c3e  test    rdx, rdx
0x180020c41  jz      short loc_180020C7E
0x180020c43  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180020c49  mov     rdi, rdx
0x180020c4c  test    al, 3
0x180020c4e  setnz   cl
0x180020c51  test    al, 8
0x180020c53  setnz   al
0x180020c56  test    al, cl
0x180020c58  jz      loc_180020CE6
0x180020c5e  mov     rax, [r8+rbx*8+10h]
0x180020c63  mov     r8d, 17Eh
0x180020c69  test    rax, rax
0x180020c6c  mov     [rsp+48h+var_18], rdx
0x180020c71  cmovnz  rsi, rax
0x180020c75  lea     rax, aEventLogForSIn; " Event Log for %S initialized (hEventSo"...
0x180020c7c  jmp     short loc_180020CC2
0x180020c7e  call    cs:__imp_GetLastError
0x180020c84  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180020c8b  mov     ecx, eax
0x180020c8d  mov     rax, cs:?sm_pEventLogSource@EVENT_LOG@@0PEAU_EVENT_LOG_SOURCE@@EA; _EVENT_LOG_SOURCE * EVENT_LOG::sm_pEventLogSource
0x180020c94  mov     [rax+rbx*8+4], ecx
0x180020c98  jz      short loc_180020CE6
0x180020c9a  mov     rax, cs:?sm_pEventLogSource@EVENT_LOG@@0PEAU_EVENT_LOG_SOURCE@@EA; _EVENT_LOG_SOURCE * EVENT_LOG::sm_pEventLogSource
0x180020ca1  mov     r8d, 187h; unsigned int
0x180020ca7  mov     rcx, [rax+rbx*8+10h]
0x180020cac  mov     edx, [rax+rbx*8+4]
0x180020cb0  test    rcx, rcx
0x180020cb3  mov     dword ptr [rsp+48h+var_18], edx
0x180020cb7  lea     rax, aCouldNotRegist; "Could not register event source (%S) ( "...
0x180020cbe  cmovnz  rsi, rcx
0x180020cc2  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180020cc9  lea     r9, aEventLogLazyin; "EVENT_LOG::LazyInit"
0x180020cd0  mov     qword ptr [rsp+48h+var_20], rsi; char
0x180020cd5  lea     rdx, aServercommonIn_9; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180020cdc  mov     [rsp+48h+var_28], rax; char *
0x180020ce1  call    PuDbgPrint
0x180020ce6  mov     rdx, cs:?sm_pEventLogSource@EVENT_LOG@@0PEAU_EVENT_LOG_SOURCE@@EA; _EVENT_LOG_SOURCE * EVENT_LOG::sm_pEventLogSource
0x180020ced  mov     dword ptr [rdx+rbx*8], 1
0x180020cf4  lea     rcx, ?sm_csLock@EVENT_LOG@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180020cfb  call    cs:__imp_LeaveCriticalSection
0x180020d01  mov     rbx, [rsp+48h+arg_0]
0x180020d06  mov     rax, rdi
0x180020d09  mov     rsi, [rsp+48h+arg_8]
0x180020d0e  add     rsp, 40h
0x180020d12  pop     rdi
0x180020d13  retn
```
