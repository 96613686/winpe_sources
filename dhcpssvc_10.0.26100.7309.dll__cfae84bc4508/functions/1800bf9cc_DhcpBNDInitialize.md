# DhcpBNDInitialize

- ea: `0x1800bf9cc`
- end: `0x1800bfde4`
- name: `DhcpBNDInitialize`
- size: `1048`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800a032c`

## callees

- `0x18001ceb4`
- `0x1800be358`
- `0x1800bf9cc`
- `0x1800cbae8`
- `0x1800cc99a`

## import_xrefs

- `WS2_32!WSACreateEvent` at `0x1800bfa57`
- `WS2_32!WSACreateEvent` at `0x1800bfa8d`
- `WS2_32!WSACreateEvent` at `0x1800bfab9`
- `WS2_32!WSACreateEvent` at `0x1800bfae5`
- `WS2_32!WSACreateEvent` at `0x1800bfb14`
- `WS2_32!WSACreateEvent` at `0x1800bfb43`
- `WS2_32!WSACreateEvent` at `0x1800bfb72`
- `WS2_32!WSACreateEvent` at `0x1800bfba1`
- `WS2_32!WSACreateEvent` at `0x1800bfbd0`
- `WS2_32!WSACreateEvent` at `0x1800bfbff`
- `WS2_32!WSACreateEvent` at `0x1800bfa57`
- `WS2_32!WSACreateEvent` at `0x1800bfa8d`
- `WS2_32!WSACreateEvent` at `0x1800bfab9`
- `WS2_32!WSACreateEvent` at `0x1800bfae5`
- `WS2_32!WSACreateEvent` at `0x1800bfb14`
- `WS2_32!WSACreateEvent` at `0x1800bfb43`
- `WS2_32!WSACreateEvent` at `0x1800bfb72`
- `WS2_32!WSACreateEvent` at `0x1800bfba1`
- `WS2_32!WSACreateEvent` at `0x1800bfbd0`
- `WS2_32!WSACreateEvent` at `0x1800bfbff`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bfa6f`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bfaa5`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bfad1`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bfafd`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bfb2c`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bfb5b`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bfb8a`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bfbb9`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bfbe8`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bfc17`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bfa6f`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bfaa5`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bfad1`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bfafd`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bfb2c`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bfb5b`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bfb8a`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bfbb9`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bfbe8`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bfc17`
- `KERNEL32!HeapAlloc` at `0x1800bfc53`
- `KERNEL32!HeapAlloc` at `0x1800bfc53`
- `KERNEL32!InitializeCriticalSection` at `0x1800bfc35`
- `KERNEL32!InitializeCriticalSection` at `0x1800bfc35`
- `KERNEL32!CreateThread` at `0x1800bfcc7`
- `KERNEL32!CreateThread` at `0x1800bfd19`
- `KERNEL32!CreateThread` at `0x1800bfd68`
- `KERNEL32!CreateThread` at `0x1800bfcc7`
- `KERNEL32!CreateThread` at `0x1800bfd19`
- `KERNEL32!CreateThread` at `0x1800bfd68`
- `KERNEL32!GetLastError` at `0x1800bfcdf`
- `KERNEL32!GetLastError` at `0x1800bfd31`
- `KERNEL32!GetLastError` at `0x1800bfd80`
- `KERNEL32!GetLastError` at `0x1800bfcdf`
- `KERNEL32!GetLastError` at `0x1800bfd31`
- `KERNEL32!GetLastError` at `0x1800bfd80`

## string_xrefs

- `0x1800bfa81`: `WSACreateEvent`
- `0x1800bfd43`: `CreateThread_DhcpBNDSendThread`
- `0x1800bfd92`: `CreateThread_DhcpBNDSendCorePacketsThread`
- `0x1800bfcf1`: `CreateThread_DhcpBNDReceiveThread`

## pseudocode

```c
__int64 DhcpBNDInitialize()
{
  _QWORD *v0; // rsi
  DWORD Error; // eax
  __int64 v2; // r9
  const char *v3; // r8
  unsigned int i; // edi
  _DWORD *v5; // rax
  unsigned int v6; // eax
  unsigned int v7; // ebx
  DWORD ThreadId; // [rsp+50h] [rbp+8h] BYREF
  DWORD lpThreadId; // [rsp+58h] [rbp+10h] BYREF
  DWORD v11; // [rsp+60h] [rbp+18h] BYREF

  v0 = &gBndFailoverEndpointsQueue;
  ThreadId = 0;
  lpThreadId = 0;
  v11 = 0;
  gLeaseDBupdateQFullEvent = 0;
  gStartBndSendProcessingReqEvent = 0;
  gStartBndRecvProcessingReqEvent = 0;
  gTerminateBndSendThreadEvent = 0;
  gTerminateBndRecvThreadEvent = 0;
  gTerminateBndSendThreadCompleteEvent = 0;
  gTerminateBndRecvThreadCompleteEvent = 0;
  gStartBndCoreProcessingReqEvent = 0;
  gTerminateBndCoreThreadEvent = 0;
  gTerminateBndCoreThreadCompleteEvent = 0;
  memset_0(&gBndFailoverEndpointsQueue, 0, 0x100u);
  gBndRecvThreadHandle = 0;
  gBndSendThreadHandle = 0;
  gBndCoreThreadHandle = 0;
  gLeaseDBupdateQFullEvent = WSACreateEvent();
  if ( !gLeaseDBupdateQFullEvent )
  {
    Error = WSAGetLastError();
    v2 = 3881;
    goto LABEL_3;
  }
  gStartBndSendProcessingReqEvent = WSACreateEvent();
  if ( !gStartBndSendProcessingReqEvent )
  {
    Error = WSAGetLastError();
    v2 = 3882;
    goto LABEL_3;
  }
  gStartBndRecvProcessingReqEvent = WSACreateEvent();
  if ( !gStartBndRecvProcessingReqEvent )
  {
    Error = WSAGetLastError();
    v2 = 3883;
    goto LABEL_3;
  }
  gTerminateBndSendThreadEvent = WSACreateEvent();
  if ( !gTerminateBndSendThreadEvent )
  {
    Error = WSAGetLastError();
    v2 = 3884;
    goto LABEL_3;
  }
  gTerminateBndRecvThreadEvent = WSACreateEvent();
  if ( !gTerminateBndRecvThreadEvent )
  {
    Error = WSAGetLastError();
    v2 = 3885;
    goto LABEL_3;
  }
  gTerminateBndSendThreadCompleteEvent = WSACreateEvent();
  if ( !gTerminateBndSendThreadCompleteEvent )
  {
    Error = WSAGetLastError();
    v2 = 3886;
    goto LABEL_3;
  }
  gTerminateBndRecvThreadCompleteEvent = WSACreateEvent();
  if ( !gTerminateBndRecvThreadCompleteEvent )
  {
    Error = WSAGetLastError();
    v2 = 3887;
    goto LABEL_3;
  }
  gStartBndCoreProcessingReqEvent = WSACreateEvent();
  if ( !gStartBndCoreProcessingReqEvent )
  {
    Error = WSAGetLastError();
    v2 = 3888;
    goto LABEL_3;
  }
  gTerminateBndCoreThreadEvent = WSACreateEvent();
  if ( !gTerminateBndCoreThreadEvent )
  {
    Error = WSAGetLastError();
    v2 = 3889;
    goto LABEL_3;
  }
  gTerminateBndCoreThreadCompleteEvent = WSACreateEvent();
  if ( !gTerminateBndCoreThreadCompleteEvent )
  {
    Error = WSAGetLastError();
    v2 = 3890;
LABEL_3:
    v3 = "WSACreateEvent";
LABEL_33:
    v7 = Error;
    DhcpPrintFOErrorEx(Error, "DhcpBNDInitialize", v3, v2);
    goto LABEL_34;
  }
  InitializeCriticalSection(&gBndFailoverEndpointCS);
  for ( i = 0; i < 0x20; ++i )
  {
    v5 = HeapAlloc(gDhcpHeap, 8u, 0x10u);
    *v0 = v5;
    if ( !v5 )
    {
      v7 = 8;
      DhcpPrintFOErrorEx(8, "DhcpBNDInitialize", "DhcpAllocateMemory", 3897);
      goto LABEL_37;
    }
    v5[2] = 0;
    v6 = MessageQInitialize(v5, *(unsigned int *)&gFailoverLeaseDbQMaxSize, 0);
    v7 = v6;
    if ( v6 )
      DhcpPrintFOErrorEx(v6, "DhcpBNDInitialize", "MessageQInitialize", 3900);
    ++v0;
  }
  gBndRecvThreadHandle = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)DhcpBNDReceiveThread, 0, 0, &ThreadId);
  if ( !gBndRecvThreadHandle )
  {
    Error = GetLastError();
    v2 = 3910;
    v3 = "CreateThread_DhcpBNDReceiveThread";
    goto LABEL_33;
  }
  gBndSendThreadHandle = CreateThread(0, 0, DhcpBNDSendThread, 0, 0, &lpThreadId);
  if ( !gBndSendThreadHandle )
  {
    Error = GetLastError();
    v2 = 3919;
    v3 = "CreateThread_DhcpBNDSendThread";
    goto LABEL_33;
  }
  gBndCoreThreadHandle = CreateThread(0, 0, DhcpBNDSendCorePacketsThread, 0, 0, &v11);
  if ( !gBndCoreThreadHandle )
  {
    Error = GetLastError();
    v2 = 3928;
    v3 = "CreateThread_DhcpBNDSendCorePacketsThread";
    goto LABEL_33;
  }
LABEL_34:
  if ( v7 )
LABEL_37:
    DhcpBNDCleanup();
  return v7;
}

```

## disassembly

```asm
0x1800bf9cc  mov     rax, rsp
0x1800bf9cf  mov     [rax+20h], rbx
0x1800bf9d3  push    rbp
0x1800bf9d4  push    rsi
0x1800bf9d5  push    rdi
0x1800bf9d6  sub     rsp, 30h
0x1800bf9da  xor     ebp, ebp
0x1800bf9dc  lea     rsi, gBndFailoverEndpointsQueue
0x1800bf9e3  mov     rcx, rsi; void *
0x1800bf9e6  mov     [rax+8], ebp
0x1800bf9e9  xor     edx, edx; Val
0x1800bf9eb  mov     [rax+10h], ebp
0x1800bf9ee  mov     r8d, 100h; Size
0x1800bf9f4  mov     [rax+18h], ebp
0x1800bf9f7  mov     cs:gLeaseDBupdateQFullEvent, rbp
0x1800bf9fe  mov     cs:gStartBndSendProcessingReqEvent, rbp
0x1800bfa05  mov     cs:gStartBndRecvProcessingReqEvent, rbp
0x1800bfa0c  mov     cs:gTerminateBndSendThreadEvent, rbp
0x1800bfa13  mov     cs:gTerminateBndRecvThreadEvent, rbp
0x1800bfa1a  mov     cs:gTerminateBndSendThreadCompleteEvent, rbp
0x1800bfa21  mov     cs:gTerminateBndRecvThreadCompleteEvent, rbp
0x1800bfa28  mov     cs:gStartBndCoreProcessingReqEvent, rbp
0x1800bfa2f  mov     cs:gTerminateBndCoreThreadEvent, rbp
0x1800bfa36  mov     cs:gTerminateBndCoreThreadCompleteEvent, rbp
0x1800bfa3d  call    memset_0
0x1800bfa42  mov     cs:gBndRecvThreadHandle, rbp
0x1800bfa49  mov     cs:gBndSendThreadHandle, rbp
0x1800bfa50  mov     cs:gBndCoreThreadHandle, rbp
0x1800bfa57  call    cs:__imp_WSACreateEvent
0x1800bfa5e  nop     dword ptr [rax+rax+00h]
0x1800bfa63  mov     cs:gLeaseDBupdateQFullEvent, rax
0x1800bfa6a  test    rax, rax
0x1800bfa6d  jnz     short loc_1800BFA8D
0x1800bfa6f  call    cs:__imp_WSAGetLastError
0x1800bfa76  nop     dword ptr [rax+rax+00h]
0x1800bfa7b  mov     r9d, 0F29h
0x1800bfa81  lea     r8, aWsacreateevent; "WSACreateEvent"
0x1800bfa88  jmp     loc_1800BFD99
0x1800bfa8d  call    cs:__imp_WSACreateEvent
0x1800bfa94  nop     dword ptr [rax+rax+00h]
0x1800bfa99  mov     cs:gStartBndSendProcessingReqEvent, rax
0x1800bfaa0  test    rax, rax
0x1800bfaa3  jnz     short loc_1800BFAB9
0x1800bfaa5  call    cs:__imp_WSAGetLastError
0x1800bfaac  nop     dword ptr [rax+rax+00h]
0x1800bfab1  mov     r9d, 0F2Ah
0x1800bfab7  jmp     short loc_1800BFA81
0x1800bfab9  call    cs:__imp_WSACreateEvent
0x1800bfac0  nop     dword ptr [rax+rax+00h]
0x1800bfac5  mov     cs:gStartBndRecvProcessingReqEvent, rax
0x1800bfacc  test    rax, rax
0x1800bfacf  jnz     short loc_1800BFAE5
0x1800bfad1  call    cs:__imp_WSAGetLastError
0x1800bfad8  nop     dword ptr [rax+rax+00h]
0x1800bfadd  mov     r9d, 0F2Bh
0x1800bfae3  jmp     short loc_1800BFA81
0x1800bfae5  call    cs:__imp_WSACreateEvent
0x1800bfaec  nop     dword ptr [rax+rax+00h]
0x1800bfaf1  mov     cs:gTerminateBndSendThreadEvent, rax
0x1800bfaf8  test    rax, rax
0x1800bfafb  jnz     short loc_1800BFB14
0x1800bfafd  call    cs:__imp_WSAGetLastError
0x1800bfb04  nop     dword ptr [rax+rax+00h]
0x1800bfb09  mov     r9d, 0F2Ch
0x1800bfb0f  jmp     loc_1800BFA81
0x1800bfb14  call    cs:__imp_WSACreateEvent
0x1800bfb1b  nop     dword ptr [rax+rax+00h]
0x1800bfb20  mov     cs:gTerminateBndRecvThreadEvent, rax
0x1800bfb27  test    rax, rax
0x1800bfb2a  jnz     short loc_1800BFB43
0x1800bfb2c  call    cs:__imp_WSAGetLastError
0x1800bfb33  nop     dword ptr [rax+rax+00h]
0x1800bfb38  mov     r9d, 0F2Dh
0x1800bfb3e  jmp     loc_1800BFA81
0x1800bfb43  call    cs:__imp_WSACreateEvent
0x1800bfb4a  nop     dword ptr [rax+rax+00h]
0x1800bfb4f  mov     cs:gTerminateBndSendThreadCompleteEvent, rax
0x1800bfb56  test    rax, rax
0x1800bfb59  jnz     short loc_1800BFB72
0x1800bfb5b  call    cs:__imp_WSAGetLastError
0x1800bfb62  nop     dword ptr [rax+rax+00h]
0x1800bfb67  mov     r9d, 0F2Eh
0x1800bfb6d  jmp     loc_1800BFA81
0x1800bfb72  call    cs:__imp_WSACreateEvent
0x1800bfb79  nop     dword ptr [rax+rax+00h]
0x1800bfb7e  mov     cs:gTerminateBndRecvThreadCompleteEvent, rax
0x1800bfb85  test    rax, rax
0x1800bfb88  jnz     short loc_1800BFBA1
0x1800bfb8a  call    cs:__imp_WSAGetLastError
0x1800bfb91  nop     dword ptr [rax+rax+00h]
0x1800bfb96  mov     r9d, 0F2Fh
0x1800bfb9c  jmp     loc_1800BFA81
0x1800bfba1  call    cs:__imp_WSACreateEvent
0x1800bfba8  nop     dword ptr [rax+rax+00h]
0x1800bfbad  mov     cs:gStartBndCoreProcessingReqEvent, rax
0x1800bfbb4  test    rax, rax
0x1800bfbb7  jnz     short loc_1800BFBD0
0x1800bfbb9  call    cs:__imp_WSAGetLastError
0x1800bfbc0  nop     dword ptr [rax+rax+00h]
0x1800bfbc5  mov     r9d, 0F30h
0x1800bfbcb  jmp     loc_1800BFA81
0x1800bfbd0  call    cs:__imp_WSACreateEvent
0x1800bfbd7  nop     dword ptr [rax+rax+00h]
0x1800bfbdc  mov     cs:gTerminateBndCoreThreadEvent, rax
0x1800bfbe3  test    rax, rax
0x1800bfbe6  jnz     short loc_1800BFBFF
0x1800bfbe8  call    cs:__imp_WSAGetLastError
0x1800bfbef  nop     dword ptr [rax+rax+00h]
0x1800bfbf4  mov     r9d, 0F31h
0x1800bfbfa  jmp     loc_1800BFA81
0x1800bfbff  call    cs:__imp_WSACreateEvent
0x1800bfc06  nop     dword ptr [rax+rax+00h]
0x1800bfc0b  mov     cs:gTerminateBndCoreThreadCompleteEvent, rax
0x1800bfc12  test    rax, rax
0x1800bfc15  jnz     short loc_1800BFC2E
0x1800bfc17  call    cs:__imp_WSAGetLastError
0x1800bfc1e  nop     dword ptr [rax+rax+00h]
0x1800bfc23  mov     r9d, 0F32h
0x1800bfc29  jmp     loc_1800BFA81
0x1800bfc2e  lea     rcx, gBndFailoverEndpointCS; lpCriticalSection
0x1800bfc35  call    cs:__imp_InitializeCriticalSection
0x1800bfc3c  nop     dword ptr [rax+rax+00h]
0x1800bfc41  mov     edi, ebp
0x1800bfc43  mov     rcx, cs:gDhcpHeap; hHeap
0x1800bfc4a  mov     edx, 8; dwFlags
0x1800bfc4f  lea     r8d, [rdx+8]; dwBytes
0x1800bfc53  call    cs:__imp_HeapAlloc
0x1800bfc5a  nop     dword ptr [rax+rax+00h]
0x1800bfc5f  mov     [rsi], rax
0x1800bfc62  test    rax, rax
0x1800bfc65  jz      loc_1800BFDAF
0x1800bfc6b  mov     [rax+8], ebp
0x1800bfc6e  xor     r8d, r8d
0x1800bfc71  mov     edx, cs:gFailoverLeaseDbQMaxSize
0x1800bfc77  mov     rcx, rax
0x1800bfc7a  call    MessageQInitialize
0x1800bfc7f  mov     ebx, eax
0x1800bfc81  test    eax, eax
0x1800bfc83  jz      short loc_1800BFCA0
0x1800bfc85  mov     r9d, 0F3Ch
0x1800bfc8b  lea     r8, aMessageqinitia; "MessageQInitialize"
0x1800bfc92  lea     rdx, aDhcpbndinitial; "DhcpBNDInitialize"
0x1800bfc99  mov     ecx, eax
0x1800bfc9b  call    DhcpPrintFOErrorEx
0x1800bfca0  inc     edi
0x1800bfca2  add     rsi, 8
0x1800bfca6  cmp     edi, 20h ; ' '
0x1800bfca9  jb      short loc_1800BFC43
0x1800bfcab  lea     rax, [rsp+48h+ThreadId]
0x1800bfcb0  xor     r9d, r9d; lpParameter
0x1800bfcb3  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x1800bfcb8  lea     r8, DhcpBNDReceiveThread; lpStartAddress
0x1800bfcbf  xor     edx, edx; dwStackSize
0x1800bfcc1  mov     [rsp+48h+dwCreationFlags], ebp; dwCreationFlags
0x1800bfcc5  xor     ecx, ecx; lpThreadAttributes
0x1800bfcc7  call    cs:__imp_CreateThread
0x1800bfcce  nop     dword ptr [rax+rax+00h]
0x1800bfcd3  mov     cs:gBndRecvThreadHandle, rax
0x1800bfcda  test    rax, rax
0x1800bfcdd  jnz     short loc_1800BFCFD
0x1800bfcdf  call    cs:__imp_GetLastError
0x1800bfce6  nop     dword ptr [rax+rax+00h]
0x1800bfceb  mov     r9d, 0F46h
0x1800bfcf1  lea     r8, aCreatethreadDh_1; "CreateThread_DhcpBNDReceiveThread"
0x1800bfcf8  jmp     loc_1800BFD99
0x1800bfcfd  lea     rax, [rsp+48h+arg_8]
0x1800bfd02  xor     r9d, r9d; lpParameter
0x1800bfd05  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x1800bfd0a  lea     r8, DhcpBNDSendThread; lpStartAddress
0x1800bfd11  xor     edx, edx; dwStackSize
0x1800bfd13  mov     [rsp+48h+dwCreationFlags], ebp; dwCreationFlags
0x1800bfd17  xor     ecx, ecx; lpThreadAttributes
0x1800bfd19  call    cs:__imp_CreateThread
0x1800bfd20  nop     dword ptr [rax+rax+00h]
0x1800bfd25  mov     cs:gBndSendThreadHandle, rax
0x1800bfd2c  test    rax, rax
0x1800bfd2f  jnz     short loc_1800BFD4C
0x1800bfd31  call    cs:__imp_GetLastError
0x1800bfd38  nop     dword ptr [rax+rax+00h]
0x1800bfd3d  mov     r9d, 0F4Fh
0x1800bfd43  lea     r8, aCreatethreadDh_0; "CreateThread_DhcpBNDSendThread"
0x1800bfd4a  jmp     short loc_1800BFD99
0x1800bfd4c  lea     rax, [rsp+48h+arg_10]
0x1800bfd51  xor     r9d, r9d; lpParameter
0x1800bfd54  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x1800bfd59  lea     r8, DhcpBNDSendCorePacketsThread; lpStartAddress
0x1800bfd60  xor     edx, edx; dwStackSize
0x1800bfd62  mov     [rsp+48h+dwCreationFlags], ebp; dwCreationFlags
0x1800bfd66  xor     ecx, ecx; lpThreadAttributes
0x1800bfd68  call    cs:__imp_CreateThread
0x1800bfd6f  nop     dword ptr [rax+rax+00h]
0x1800bfd74  mov     cs:gBndCoreThreadHandle, rax
0x1800bfd7b  test    rax, rax
0x1800bfd7e  jnz     short loc_1800BFDA9
0x1800bfd80  call    cs:__imp_GetLastError
0x1800bfd87  nop     dword ptr [rax+rax+00h]
0x1800bfd8c  mov     r9d, 0F58h
0x1800bfd92  lea     r8, aCreatethreadDh; "CreateThread_DhcpBNDSendCorePacketsThre"...
0x1800bfd99  lea     rdx, aDhcpbndinitial; "DhcpBNDInitialize"
0x1800bfda0  mov     ecx, eax
0x1800bfda2  mov     ebx, eax
0x1800bfda4  call    DhcpPrintFOErrorEx
0x1800bfda9  test    ebx, ebx
0x1800bfdab  jz      short loc_1800BFDD4
0x1800bfdad  jmp     short loc_1800BFDCF
0x1800bfdaf  mov     ebx, 8
0x1800bfdb4  lea     r8, aDhcpallocateme; "DhcpAllocateMemory"
0x1800bfdbb  mov     ecx, ebx
0x1800bfdbd  lea     rdx, aDhcpbndinitial; "DhcpBNDInitialize"
0x1800bfdc4  mov     r9d, 0F39h
0x1800bfdca  call    DhcpPrintFOErrorEx
0x1800bfdcf  call    DhcpBNDCleanup
0x1800bfdd4  mov     eax, ebx
0x1800bfdd6  mov     rbx, [rsp+48h+arg_18]
0x1800bfddb  add     rsp, 30h
0x1800bfddf  pop     rdi
0x1800bfde0  pop     rsi
0x1800bfde1  pop     rbp
0x1800bfde2  retn
```
