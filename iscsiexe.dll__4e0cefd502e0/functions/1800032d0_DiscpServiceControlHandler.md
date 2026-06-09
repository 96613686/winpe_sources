# DiscpServiceControlHandler

- ea: `0x1800032d0`
- end: `0x180003359`
- name: `DiscpServiceControlHandler`
- size: `137`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x1800032d0`
- `0x180003360`
- `0x180012a18`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18000332c`
- `ntdll!RtlLeaveCriticalSection` at `0x18000332c`
- `ntdll!RtlEnterCriticalSection` at `0x180003318`
- `ntdll!RtlEnterCriticalSection` at `0x180003318`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000334b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000334b`

## pseudocode

```c
__int64 __fastcall DiscpServiceControlHandler(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  unsigned int v4; // ebx
  DWORD v5; // ecx
  DWORD v6; // ecx
  DWORD v7; // ecx

  v4 = 120;
  v5 = dwControl - 1;
  if ( v5 )
  {
    v6 = v5 - 3;
    if ( !v6 )
      goto LABEL_6;
    v7 = v6 - 1;
    if ( v7 )
    {
      if ( v7 != 6 )
      {
LABEL_7:
        ReportStatusToSCMgr((unsigned int)dword_180027544, 0, 0);
        return v4;
      }
      DiscpDeviceChange(dwEventType, lpEventData);
LABEL_6:
      v4 = 0;
      goto LABEL_7;
    }
  }
  RtlEnterCriticalSection(&DiscpShutdownCritSection);
  DiscpShutdownInProgress = 1;
  RtlLeaveCriticalSection(&DiscpShutdownCritSection);
  ReportStatusToSCMgr(3, 0, 0);
  if ( DiscpServerStopEvent )
    SetEvent(DiscpServerStopEvent);
  return 0;
}

```

## disassembly

```asm
0x1800032d0  push    rbx
0x1800032d2  sub     rsp, 20h
0x1800032d6  mov     eax, edx
0x1800032d8  mov     ebx, 78h ; 'x'
0x1800032dd  sub     ecx, 1
0x1800032e0  jz      short loc_180003311
0x1800032e2  sub     ecx, 3
0x1800032e5  jz      short loc_1800032FB
0x1800032e7  sub     ecx, 1
0x1800032ea  jz      short loc_180003311
0x1800032ec  cmp     ecx, 6
0x1800032ef  jnz     short loc_1800032FD
0x1800032f1  mov     rdx, r8
0x1800032f4  mov     ecx, eax
0x1800032f6  call    DiscpDeviceChange
0x1800032fb  xor     ebx, ebx
0x1800032fd  mov     ecx, cs:dword_180027544
0x180003303  xor     r8d, r8d
0x180003306  xor     edx, edx
0x180003308  call    ReportStatusToSCMgr
0x18000330d  mov     eax, ebx
0x18000330f  jmp     short loc_180003353
0x180003311  lea     rcx, DiscpShutdownCritSection; CriticalSection
0x180003318  call    cs:__imp_RtlEnterCriticalSection
0x18000331e  lea     rcx, DiscpShutdownCritSection; CriticalSection
0x180003325  mov     cs:DiscpShutdownInProgress, 1
0x18000332c  call    cs:__imp_RtlLeaveCriticalSection
0x180003332  xor     edx, edx
0x180003334  xor     r8d, r8d
0x180003337  lea     ecx, [rdx+3]
0x18000333a  call    ReportStatusToSCMgr
0x18000333f  mov     rcx, cs:DiscpServerStopEvent; hEvent
0x180003346  test    rcx, rcx
0x180003349  jz      short loc_180003351
0x18000334b  call    cs:__imp_SetEvent
0x180003351  xor     eax, eax
0x180003353  add     rsp, 20h
0x180003357  pop     rbx
0x180003358  retn
```
