# TaskBlock

- ea: `0x180005ea4`
- end: `0x180005f19`
- name: `TaskBlock`
- size: `117`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x180002a90`

## callees

- `0x180005e7c`
- `0x180005ea4`
- `0x180005ff0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005efd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005efd`
- `USER32!DispatchMessageW` at `0x180005ed5`
- `USER32!DispatchMessageW` at `0x180005ed5`
- `USER32!GetMessageW` at `0x180005ee8`
- `USER32!GetMessageW` at `0x180005ee8`

## pseudocode

```c
__int64 __fastcall TaskBlock(__int64 a1, __int64 a2, __int64 a3)
{
  MSG Msg; // [rsp+20h] [rbp-48h] BYREF

  memset(&Msg, 0, sizeof(Msg));
  LeaveSeq(a1, a2, a3);
  while ( 1 )
  {
    GetMessageW(&Msg, 0, 0, 0);
    if ( !Msg.hwnd )
      break;
    DispatchMessageW(&Msg);
  }
  EnterCriticalSection(&SeqCritSec);
  return Msg.message;
}

```

## disassembly

```asm
0x180005ea4  sub     rsp, 68h
0x180005ea8  mov     rax, cs:__security_cookie
0x180005eaf  xor     rax, rsp
0x180005eb2  mov     [rsp+68h+var_18], rax
0x180005eb7  xorps   xmm0, xmm0
0x180005eba  movups  xmmword ptr [rsp+68h+Msg.hwnd], xmm0
0x180005ebf  movups  xmmword ptr [rsp+68h+Msg.wParam], xmm0
0x180005ec4  movups  xmmword ptr [rsp+68h+Msg.time], xmm0
0x180005ec9  call    LeaveSeq
0x180005ece  jmp     short loc_180005EDB
0x180005ed0  lea     rcx, [rsp+68h+Msg]; lpMsg
0x180005ed5  call    cs:__imp_DispatchMessageW
0x180005edb  xor     r9d, r9d; wMsgFilterMax
0x180005ede  lea     rcx, [rsp+68h+Msg]; lpMsg
0x180005ee3  xor     r8d, r8d; wMsgFilterMin
0x180005ee6  xor     edx, edx; hWnd
0x180005ee8  call    cs:__imp_GetMessageW
0x180005eee  cmp     [rsp+68h+Msg.hwnd], 0
0x180005ef4  jnz     short loc_180005ED0
0x180005ef6  lea     rcx, SeqCritSec; lpCriticalSection
0x180005efd  call    cs:__imp_EnterCriticalSection
0x180005f03  mov     eax, [rsp+68h+Msg.message]
0x180005f07  mov     rcx, [rsp+68h+var_18]
0x180005f0c  xor     rcx, rsp; StackCookie
0x180005f0f  call    __security_check_cookie
0x180005f14  add     rsp, 68h
0x180005f18  retn
```
