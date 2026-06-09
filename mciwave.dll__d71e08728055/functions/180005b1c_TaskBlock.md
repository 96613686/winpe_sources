# TaskBlock

- ea: `0x180005b1c`
- end: `0x180005b87`
- name: `TaskBlock`
- size: `107`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x180001860`
- `0x180002d40`
- `0x180005170`

## callees

- `0x180005b1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005b78`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005b78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005b39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005b39`
- `USER32!DispatchMessageW` at `0x180005b5f`
- `USER32!DispatchMessageW` at `0x180005b5f`
- `USER32!GetMessageW` at `0x180005b4c`
- `USER32!GetMessageW` at `0x180005b4c`

## pseudocode

```c
__int64 TaskBlock()
{
  tagMSG Msg; // [rsp+20h] [rbp-38h] BYREF

  memset(&Msg, 0, sizeof(Msg));
  LeaveCriticalSection(&CritSec);
  do
  {
    while ( 1 )
    {
      GetMessageW(&Msg, 0, 0, 0);
      if ( !Msg.hwnd )
        break;
      DispatchMessageW(&Msg);
    }
  }
  while ( Msg.message == 960 );
  EnterCriticalSection(&CritSec);
  return Msg.message;
}

```

## disassembly

```asm
0x180005b1c  sub     rsp, 58h
0x180005b20  xorps   xmm0, xmm0
0x180005b23  lea     rcx, CritSec; lpCriticalSection
0x180005b2a  movups  xmmword ptr [rsp+58h+Msg.hwnd], xmm0
0x180005b2f  movups  xmmword ptr [rsp+58h+Msg.wParam], xmm0
0x180005b34  movups  xmmword ptr [rsp+58h+Msg.time], xmm0
0x180005b39  call    cs:__imp_LeaveCriticalSection
0x180005b3f  xor     r9d, r9d; wMsgFilterMax
0x180005b42  lea     rcx, [rsp+58h+Msg]; lpMsg
0x180005b47  xor     r8d, r8d; wMsgFilterMin
0x180005b4a  xor     edx, edx; hWnd
0x180005b4c  call    cs:__imp_GetMessageW
0x180005b52  cmp     [rsp+58h+Msg.hwnd], 0
0x180005b58  jz      short loc_180005B67
0x180005b5a  lea     rcx, [rsp+58h+Msg]; lpMsg
0x180005b5f  call    cs:__imp_DispatchMessageW
0x180005b65  jmp     short loc_180005B3F
0x180005b67  cmp     [rsp+58h+Msg.message], 3C0h
0x180005b6f  jz      short loc_180005B3F
0x180005b71  lea     rcx, CritSec; lpCriticalSection
0x180005b78  call    cs:__imp_EnterCriticalSection
0x180005b7e  mov     eax, [rsp+58h+Msg.message]
0x180005b82  add     rsp, 58h
0x180005b86  retn
```
