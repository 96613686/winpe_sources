# FREB_TIMEOUT_MONITOR_LIST::~FREB_TIMEOUT_MONITOR_LIST(void)

- ea: `0x180003b04`
- end: `0x180003bb4`
- name: `??1FREB_TIMEOUT_MONITOR_LIST@@QEAA@XZ`
- size: `176`
- prototype: `void __fastcall(FREB_TIMEOUT_MONITOR_LIST *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800054e8`

## callees

- `0x180003b04`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b36`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180003b23`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180003b23`
- `iisutil!PuDbgPrint` at `0x180003b73`
- `iisutil!PuDbgPrint` at `0x180003b73`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180003b90`

## string_xrefs

- `0x180003b61`: `failed to call DeleteTimerQueueEx(): hr=0x%x\n`
- `0x180003b5a`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\freb_timeout_monitor.hxx`

## pseudocode

```c
void __fastcall FREB_TIMEOUT_MONITOR_LIST::~FREB_TIMEOUT_MONITOR_LIST(FREB_TIMEOUT_MONITOR_LIST *this)
{
  void *v1; // rdx
  signed int LastError; // eax
  __int64 v4; // rdi
  char *v5; // rbx

  v1 = (void *)*((_QWORD *)this + 901);
  if ( v1 )
  {
    if ( !DeleteTimerQueueTimer(0, v1, (HANDLE)0xFFFFFFFFFFFFFFFFLL) && (g_dwDebugFlags & 3) != 0 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_timeout_monitor.hxx",
        163,
        "FREB_TIMEOUT_MONITOR_LIST::~FREB_TIMEOUT_MONITOR_LIST",
        "failed to call DeleteTimerQueueEx(): hr=0x%x\n",
        LastError);
    }
    *((_QWORD *)this + 901) = 0;
  }
  v4 = 300;
  v5 = (char *)this + 7200;
  do
  {
    v5 -= 8;
    ((void (__fastcall *)(char *))CReaderWriterLock3::~CReaderWriterLock3)(v5);
    --v4;
  }
  while ( v4 );
}

```

## disassembly

```asm
0x180003b04  mov     [rsp+arg_0], rbx
0x180003b09  push    rdi
0x180003b0a  sub     rsp, 30h
0x180003b0e  mov     rdx, [rcx+1C28h]; Timer
0x180003b15  mov     rbx, rcx
0x180003b18  test    rdx, rdx
0x180003b1b  jz      short loc_180003B84
0x180003b1d  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180003b21  xor     ecx, ecx; TimerQueue
0x180003b23  call    cs:__imp_DeleteTimerQueueTimer
0x180003b29  test    eax, eax
0x180003b2b  jnz     short loc_180003B79
0x180003b2d  test    byte ptr cs:g_dwDebugFlags, 3
0x180003b34  jz      short loc_180003B79
0x180003b36  call    cs:__imp_GetLastError
0x180003b3c  test    eax, eax
0x180003b3e  jle     short loc_180003B48
0x180003b40  movzx   eax, ax
0x180003b43  or      eax, 80070000h
0x180003b48  mov     rcx, cs:g_pDebug
0x180003b4f  lea     r9, aFrebTimeoutMon; "FREB_TIMEOUT_MONITOR_LIST::~FREB_TIMEOU"...
0x180003b56  mov     [rsp+38h+var_10], eax
0x180003b5a  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003b61  lea     rax, aFailedToCallDe; "failed to call DeleteTimerQueueEx(): hr"...
0x180003b68  mov     r8d, 0A3h
0x180003b6e  mov     [rsp+38h+var_18], rax
0x180003b73  call    cs:__imp_PuDbgPrint
0x180003b79  mov     qword ptr [rbx+1C28h], 0
0x180003b84  mov     edi, 12Ch
0x180003b89  add     rbx, 1C20h
0x180003b90  mov     rax, cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x180003b97  sub     rbx, 8
0x180003b9b  mov     rcx, rbx
0x180003b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ba3  sub     rdi, 1
0x180003ba7  jnz     short loc_180003B90
0x180003ba9  mov     rbx, [rsp+38h+arg_0]
0x180003bae  add     rsp, 30h
0x180003bb2  pop     rdi
0x180003bb3  retn
```
