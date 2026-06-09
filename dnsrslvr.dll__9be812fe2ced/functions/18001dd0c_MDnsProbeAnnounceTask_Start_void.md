# MDnsProbeAnnounceTask::Start(void)

- ea: `0x18001dd0c`
- end: `0x18001ddcd`
- name: `?Start@MDnsProbeAnnounceTask@@SAXXZ`
- size: `193`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001bf58`

## callees

- `0x18001dd0c`
- `0x180046ec0`
- `0x18007cee4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001dd2f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001dd2f`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18001dd4a`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18001dd4a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001dd62`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001dd62`

## pseudocode

```c
void MDnsProbeAnnounceTask::Start(void)
{
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp-18h] BYREF

  pftDueTime = (struct _FILETIME)-10000000LL;
  ResetEvent(MDnsProbeAnnounceTask::s_hProbeAnnounceStop);
  ++MDnsProbeAnnounceTask::s_cNetChanges;
  GetLocalTime(&MDnsProbeAnnounceTask::s_timeStamp);
  SetThreadpoolTimer(MDnsProbeAnnounceTask::s_pTimer, &pftDueTime, 0, 0);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_ddddd(
      MDnsProbeAnnounceTask::s_timeStamp.wSecond,
      12,
      WPP_f1363454a052307e4f87df134c372536_Traceguids,
      MDnsProbeAnnounceTask::s_cNetChanges,
      MDnsProbeAnnounceTask::s_timeStamp.wHour,
      MDnsProbeAnnounceTask::s_timeStamp.wMinute,
      MDnsProbeAnnounceTask::s_timeStamp.wSecond,
      MDnsProbeAnnounceTask::s_timeStamp.wMilliseconds);
}

```

## disassembly

```asm
0x18001dd0c  sub     rsp, 58h
0x18001dd10  mov     rax, cs:__security_cookie
0x18001dd17  xor     rax, rsp
0x18001dd1a  mov     [rsp+58h+var_10], rax
0x18001dd1f  mov     rcx, cs:?s_hProbeAnnounceStop@MDnsProbeAnnounceTask@@0PEAXEA; hEvent
0x18001dd26  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], 0FFFFFFFFFF676980h
0x18001dd2f  call    cs:__imp_ResetEvent
0x18001dd35  mov     eax, cs:?s_cNetChanges@MDnsProbeAnnounceTask@@0IC; uint volatile MDnsProbeAnnounceTask::s_cNetChanges
0x18001dd3b  lea     rcx, ?s_timeStamp@MDnsProbeAnnounceTask@@0U_SYSTEMTIME@@A; lpSystemTime
0x18001dd42  inc     eax
0x18001dd44  mov     cs:?s_cNetChanges@MDnsProbeAnnounceTask@@0IC, eax; uint volatile MDnsProbeAnnounceTask::s_cNetChanges
0x18001dd4a  call    cs:__imp_GetLocalTime
0x18001dd50  mov     rcx, cs:?s_pTimer@MDnsProbeAnnounceTask@@0PEAU_TP_TIMER@@EA; pti
0x18001dd57  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18001dd5c  xor     r9d, r9d; msWindowLength
0x18001dd5f  xor     r8d, r8d; msPeriod
0x18001dd62  call    cs:__imp_SetThreadpoolTimer
0x18001dd68  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18001dd6f  jnz     short loc_18001DD83
0x18001dd71  mov     rcx, [rsp+58h+var_10]
0x18001dd76  xor     rcx, rsp; StackCookie
0x18001dd79  call    __security_check_cookie
0x18001dd7e  add     rsp, 58h
0x18001dd82  retn
0x18001dd83  movzx   r8d, cs:?s_timeStamp@MDnsProbeAnnounceTask@@0U_SYSTEMTIME@@A.wMinute; _SYSTEMTIME MDnsProbeAnnounceTask::s_timeStamp ...
0x18001dd8b  mov     edx, 0Ch
0x18001dd90  movzx   r9d, cs:?s_timeStamp@MDnsProbeAnnounceTask@@0U_SYSTEMTIME@@A.wHour; _SYSTEMTIME MDnsProbeAnnounceTask::s_timeStamp ...
0x18001dd98  movzx   eax, cs:?s_timeStamp@MDnsProbeAnnounceTask@@0U_SYSTEMTIME@@A.wMilliseconds; _SYSTEMTIME MDnsProbeAnnounceTask::s_timeStamp ...
0x18001dd9f  movzx   ecx, cs:?s_timeStamp@MDnsProbeAnnounceTask@@0U_SYSTEMTIME@@A.wSecond; _SYSTEMTIME MDnsProbeAnnounceTask::s_timeStamp ...
0x18001dda6  mov     [rsp+58h+var_20], eax
0x18001ddaa  mov     [rsp+58h+var_28], ecx
0x18001ddae  mov     [rsp+58h+var_30], r8d
0x18001ddb3  lea     r8, WPP_f1363454a052307e4f87df134c372536_Traceguids
0x18001ddba  mov     [rsp+58h+var_38], r9d
0x18001ddbf  mov     r9d, cs:?s_cNetChanges@MDnsProbeAnnounceTask@@0IC; uint volatile MDnsProbeAnnounceTask::s_cNetChanges
0x18001ddc6  call    WPP_SF_ddddd
0x18001ddcb  jmp     short loc_18001DD71
```
