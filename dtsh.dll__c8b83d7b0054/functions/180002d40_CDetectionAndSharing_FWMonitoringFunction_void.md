# CDetectionAndSharing::FWMonitoringFunction(void * *)

- ea: `0x180002d40`
- end: `0x180002dc8`
- name: `?FWMonitoringFunction@CDetectionAndSharing@@CAKPEAPEAX@Z`
- size: `136`
- prototype: `unsigned int __stdcall(void *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002d40`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180002da6`
- `KERNEL32!CloseHandle` at `0x180002da6`
- `KERNEL32!SetEvent` at `0x180002d9d`
- `KERNEL32!SetEvent` at `0x180002d9d`
- `KERNEL32!WaitForSingleObject` at `0x180002d71`
- `KERNEL32!WaitForSingleObject` at `0x180002d71`
- `KERNEL32!OpenEventW` at `0x180002d8c`
- `KERNEL32!OpenEventW` at `0x180002d8c`
- `FirewallAPI!FWChangeNotificationCreate` at `0x180002d5b`
- `FirewallAPI!FWChangeNotificationCreate` at `0x180002d5b`
- `FirewallAPI!FWChangeNotificationDestroy` at `0x180002dba`
- `FirewallAPI!FWChangeNotificationDestroy` at `0x180002dba`

## pseudocode

```c
__int64 __fastcall CDetectionAndSharing::FWMonitoringFunction(void *a1)
{
  HANDLE v1; // rax
  void *v2; // rbx
  __int64 v4; // [rsp+38h] [rbp+10h] BYREF

  v4 = 0;
  if ( !(unsigned int)FWChangeNotificationCreate(g_hFWMonitorEvent, &v4) )
  {
    while ( !g_bFWMonitorCancelled )
    {
      WaitForSingleObject(g_hFWMonitorEvent, 0xFFFFFFFF);
      if ( g_bFWMonitorCancelled )
        break;
      v1 = OpenEventW(2u, 0, L"NetCenter_DTSHRefreshEvent");
      v2 = v1;
      if ( v1 )
      {
        SetEvent(v1);
        CloseHandle(v2);
      }
    }
    FWChangeNotificationDestroy(&v4);
  }
  return 0;
}

```

## disassembly

```asm
0x180002d40  push    rbx
0x180002d42  sub     rsp, 20h
0x180002d46  mov     rcx, cs:?g_hFWMonitorEvent@@3PEAXEA; void * g_hFWMonitorEvent
0x180002d4d  lea     rdx, [rsp+28h+arg_8]
0x180002d52  mov     [rsp+28h+arg_8], 0
0x180002d5b  call    cs:__imp_FWChangeNotificationCreate
0x180002d61  test    eax, eax
0x180002d63  jnz     short loc_180002DC0
0x180002d65  jmp     short loc_180002DAC
0x180002d67  mov     rcx, cs:?g_hFWMonitorEvent@@3PEAXEA; hHandle
0x180002d6e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180002d71  call    cs:__imp_WaitForSingleObject
0x180002d77  cmp     cs:?g_bFWMonitorCancelled@@3EA, 0; uchar g_bFWMonitorCancelled
0x180002d7e  jnz     short loc_180002DB5
0x180002d80  xor     edx, edx; bInheritHandle
0x180002d82  lea     r8, Name; "NetCenter_DTSHRefreshEvent"
0x180002d89  lea     ecx, [rdx+2]; dwDesiredAccess
0x180002d8c  call    cs:__imp_OpenEventW
0x180002d92  mov     rbx, rax
0x180002d95  test    rax, rax
0x180002d98  jz      short loc_180002DAC
0x180002d9a  mov     rcx, rax; hEvent
0x180002d9d  call    cs:__imp_SetEvent
0x180002da3  mov     rcx, rbx; hObject
0x180002da6  call    cs:__imp_CloseHandle
0x180002dac  cmp     cs:?g_bFWMonitorCancelled@@3EA, 0; uchar g_bFWMonitorCancelled
0x180002db3  jz      short loc_180002D67
0x180002db5  lea     rcx, [rsp+28h+arg_8]
0x180002dba  call    cs:__imp_FWChangeNotificationDestroy
0x180002dc0  xor     eax, eax
0x180002dc2  add     rsp, 20h
0x180002dc6  pop     rbx
0x180002dc7  retn
```
