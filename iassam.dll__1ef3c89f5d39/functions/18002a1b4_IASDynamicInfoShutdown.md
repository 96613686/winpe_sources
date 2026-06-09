# IASDynamicInfoShutdown

- ea: `0x18002a1b4`
- end: `0x18002a241`
- name: `IASDynamicInfoShutdown`
- size: `141`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800291bc`
- `0x1800293ec`

## callees

- `0x18002a1b4`
- `0x18002a748`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18002a1d9`
- `KERNEL32!WaitForSingleObject` at `0x18002a1d9`
- `KERNEL32!SetEvent` at `0x18002a1c9`
- `KERNEL32!SetEvent` at `0x18002a1c9`
- `KERNEL32!DeleteCriticalSection` at `0x18002a20e`
- `KERNEL32!DeleteCriticalSection` at `0x18002a20e`
- `KERNEL32!CloseHandle` at `0x18002a1f6`
- `KERNEL32!CloseHandle` at `0x18002a1f6`
- `ADVAPI32!LsaFreeMemory` at `0x18002a220`
- `ADVAPI32!LsaFreeMemory` at `0x18002a220`

## pseudocode

```c
void IASDynamicInfoShutdown()
{
  theShutdownFlag = 1;
  SetEvent(theChangeEvent);
  WaitForSingleObject(theNotificationThread, 0xFFFFFFFF);
  IASUnregisterDomainNameChangeNotification();
  theChangeEvent = 0;
  CloseHandle(theNotificationThread);
  theNotificationThread = 0;
  DeleteCriticalSection(&critSec);
  if ( ppdi )
  {
    LsaFreeMemory(ppdi);
    ppdi = 0;
  }
  theDnsDomainName = 0;
}

```

## disassembly

```asm
0x18002a1b4  sub     rsp, 28h
0x18002a1b8  mov     rcx, cs:theChangeEvent; hEvent
0x18002a1bf  mov     cs:theShutdownFlag, 1
0x18002a1c9  call    cs:__imp_SetEvent
0x18002a1cf  mov     rcx, cs:theNotificationThread; hHandle
0x18002a1d6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002a1d9  call    cs:__imp_WaitForSingleObject
0x18002a1df  call    IASUnregisterDomainNameChangeNotification
0x18002a1e4  mov     rcx, cs:theNotificationThread; hObject
0x18002a1eb  mov     cs:theChangeEvent, 0
0x18002a1f6  call    cs:__imp_CloseHandle
0x18002a1fc  lea     rcx, critSec; lpCriticalSection
0x18002a203  mov     cs:theNotificationThread, 0
0x18002a20e  call    cs:__imp_DeleteCriticalSection
0x18002a214  mov     rcx, cs:ppdi; Buffer
0x18002a21b  test    rcx, rcx
0x18002a21e  jz      short loc_18002A231
0x18002a220  call    cs:__imp_LsaFreeMemory
0x18002a226  mov     cs:ppdi, 0
0x18002a231  mov     cs:theDnsDomainName, 0
0x18002a23c  add     rsp, 28h
0x18002a240  retn
```
