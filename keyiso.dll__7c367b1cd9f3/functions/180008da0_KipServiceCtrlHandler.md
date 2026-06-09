# KipServiceCtrlHandler

- ea: `0x180008da0`
- end: `0x180008df4`
- name: `KipServiceCtrlHandler`
- size: `84`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180008da0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008dea`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008dea`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180008ddc`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180008ddc`

## pseudocode

```c
__int64 __fastcall KipServiceCtrlHandler(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  __int64 result; // rax

  result = 120;
  if ( dwControl == 1 )
  {
    ServiceStatus.dwCurrentState = 3;
    *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
    SetServiceStatus(hServiceStatus, &ServiceStatus);
    if ( lpContext )
      SetEvent(lpContext);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180008da0  push    rbx
0x180008da2  sub     rsp, 20h
0x180008da6  mov     rbx, r9
0x180008da9  mov     eax, 78h ; 'x'
0x180008dae  cmp     ecx, 1
0x180008db1  jz      short loc_180008DB9
0x180008db3  add     rsp, 20h
0x180008db7  pop     rbx
0x180008db8  retn
0x180008db9  mov     rcx, cs:hServiceStatus; hServiceStatus
0x180008dc0  lea     rdx, ServiceStatus; lpServiceStatus
0x180008dc7  mov     cs:ServiceStatus.dwCurrentState, 3
0x180008dd1  mov     qword ptr cs:ServiceStatus.dwCheckPoint, 0
0x180008ddc  call    cs:__imp_SetServiceStatus
0x180008de2  test    rbx, rbx
0x180008de5  jz      short loc_180008DF0
0x180008de7  mov     rcx, rbx; hEvent
0x180008dea  call    cs:__imp_SetEvent
0x180008df0  xor     eax, eax
0x180008df2  jmp     short loc_180008DB3
```
