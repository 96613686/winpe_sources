# DhcpBNDInitialize

- ea: `0x1800c09e8`
- end: `0x1800c0e00`
- name: `DhcpBNDInitialize`
- size: `1048`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800a1004`

## callees

- `0x18001c45c`
- `0x1800bf348`
- `0x1800c09e8`
- `0x1800ccba0`
- `0x1800cda7a`

## import_xrefs

- `WS2_32!WSACreateEvent` at `0x1800c0a73`
- `WS2_32!WSACreateEvent` at `0x1800c0aa9`
- `WS2_32!WSACreateEvent` at `0x1800c0ad5`
- `WS2_32!WSACreateEvent` at `0x1800c0b01`
- `WS2_32!WSACreateEvent` at `0x1800c0b30`
- `WS2_32!WSACreateEvent` at `0x1800c0b5f`
- `WS2_32!WSACreateEvent` at `0x1800c0b8e`
- `WS2_32!WSACreateEvent` at `0x1800c0bbd`
- `WS2_32!WSACreateEvent` at `0x1800c0bec`
- `WS2_32!WSACreateEvent` at `0x1800c0c1b`
- `WS2_32!WSACreateEvent` at `0x1800c0a73`
- `WS2_32!WSACreateEvent` at `0x1800c0aa9`
- `WS2_32!WSACreateEvent` at `0x1800c0ad5`
- `WS2_32!WSACreateEvent` at `0x1800c0b01`
- `WS2_32!WSACreateEvent` at `0x1800c0b30`
- `WS2_32!WSACreateEvent` at `0x1800c0b5f`
- `WS2_32!WSACreateEvent` at `0x1800c0b8e`
- `WS2_32!WSACreateEvent` at `0x1800c0bbd`
- `WS2_32!WSACreateEvent` at `0x1800c0bec`
- `WS2_32!WSACreateEvent` at `0x1800c0c1b`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c0a8b`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c0ac1`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c0aed`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c0b19`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c0b48`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c0b77`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c0ba6`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c0bd5`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c0c04`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c0c33`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c0a8b`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c0ac1`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c0aed`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c0b19`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c0b48`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c0b77`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c0ba6`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c0bd5`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c0c04`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c0c33`
- `KERNEL32!HeapAlloc` at `0x1800c0c6f`
- `KERNEL32!HeapAlloc` at `0x1800c0c6f`
- `KERNEL32!InitializeCriticalSection` at `0x1800c0c51`
- `KERNEL32!InitializeCriticalSection` at `0x1800c0c51`
- `KERNEL32!GetLastError` at `0x1800c0cfb`
- `KERNEL32!GetLastError` at `0x1800c0d4d`
- `KERNEL32!GetLastError` at `0x1800c0d9c`
- `KERNEL32!GetLastError` at `0x1800c0cfb`
- `KERNEL32!GetLastError` at `0x1800c0d4d`
- `KERNEL32!GetLastError` at `0x1800c0d9c`
- `KERNEL32!CreateThread` at `0x1800c0ce3`
- `KERNEL32!CreateThread` at `0x1800c0d35`
- `KERNEL32!CreateThread` at `0x1800c0d84`
- `KERNEL32!CreateThread` at `0x1800c0ce3`
- `KERNEL32!CreateThread` at `0x1800c0d35`
- `KERNEL32!CreateThread` at `0x1800c0d84`

## string_xrefs

- `0x1800c0a9d`: `WSACreateEvent`
- `0x1800c0dae`: `CreateThread_DhcpBNDSendCorePacketsThread`
- `0x1800c0d5f`: `CreateThread_DhcpBNDSendThread`
- `0x1800c0d0d`: `CreateThread_DhcpBNDReceiveThread`

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
  gBndRecvThreadHandle = CreateThread(0, 0, DhcpBNDReceiveThread, 0, 0, &ThreadId);
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
0x1800c09e8  mov     rax, rsp
0x1800c09eb  mov     [rax+20h], rbx
0x1800c09ef  push    rbp
0x1800c09f0  push    rsi
0x1800c09f1  push    rdi
0x1800c09f2  sub     rsp, 30h
0x1800c09f6  xor     ebp, ebp
0x1800c09f8  lea     rsi, gBndFailoverEndpointsQueue
0x1800c09ff  mov     rcx, rsi; void *
0x1800c0a02  mov     [rax+8], ebp
0x1800c0a05  xor     edx, edx; Val
0x1800c0a07  mov     [rax+10h], ebp
0x1800c0a0a  mov     r8d, 100h; Size
0x1800c0a10  mov     [rax+18h], ebp
0x1800c0a13  mov     cs:gLeaseDBupdateQFullEvent, rbp
0x1800c0a1a  mov     cs:gStartBndSendProcessingReqEvent, rbp
0x1800c0a21  mov     cs:gStartBndRecvProcessingReqEvent, rbp
0x1800c0a28  mov     cs:gTerminateBndSendThreadEvent, rbp
0x1800c0a2f  mov     cs:gTerminateBndRecvThreadEvent, rbp
0x1800c0a36  mov     cs:gTerminateBndSendThreadCompleteEvent, rbp
0x1800c0a3d  mov     cs:gTerminateBndRecvThreadCompleteEvent, rbp
0x1800c0a44  mov     cs:gStartBndCoreProcessingReqEvent, rbp
0x1800c0a4b  mov     cs:gTerminateBndCoreThreadEvent, rbp
0x1800c0a52  mov     cs:gTerminateBndCoreThreadCompleteEvent, rbp
0x1800c0a59  call    memset_0
0x1800c0a5e  mov     cs:gBndRecvThreadHandle, rbp
0x1800c0a65  mov     cs:gBndSendThreadHandle, rbp
0x1800c0a6c  mov     cs:gBndCoreThreadHandle, rbp
0x1800c0a73  call    cs:__imp_WSACreateEvent
0x1800c0a7a  nop     dword ptr [rax+rax+00h]
0x1800c0a7f  mov     cs:gLeaseDBupdateQFullEvent, rax
0x1800c0a86  test    rax, rax
0x1800c0a89  jnz     short loc_1800C0AA9
0x1800c0a8b  call    cs:__imp_WSAGetLastError
0x1800c0a92  nop     dword ptr [rax+rax+00h]
0x1800c0a97  mov     r9d, 0F29h
0x1800c0a9d  lea     r8, aWsacreateevent; "WSACreateEvent"
0x1800c0aa4  jmp     loc_1800C0DB5
0x1800c0aa9  call    cs:__imp_WSACreateEvent
0x1800c0ab0  nop     dword ptr [rax+rax+00h]
0x1800c0ab5  mov     cs:gStartBndSendProcessingReqEvent, rax
0x1800c0abc  test    rax, rax
0x1800c0abf  jnz     short loc_1800C0AD5
0x1800c0ac1  call    cs:__imp_WSAGetLastError
0x1800c0ac8  nop     dword ptr [rax+rax+00h]
0x1800c0acd  mov     r9d, 0F2Ah
0x1800c0ad3  jmp     short loc_1800C0A9D
0x1800c0ad5  call    cs:__imp_WSACreateEvent
0x1800c0adc  nop     dword ptr [rax+rax+00h]
0x1800c0ae1  mov     cs:gStartBndRecvProcessingReqEvent, rax
0x1800c0ae8  test    rax, rax
0x1800c0aeb  jnz     short loc_1800C0B01
0x1800c0aed  call    cs:__imp_WSAGetLastError
0x1800c0af4  nop     dword ptr [rax+rax+00h]
0x1800c0af9  mov     r9d, 0F2Bh
0x1800c0aff  jmp     short loc_1800C0A9D
0x1800c0b01  call    cs:__imp_WSACreateEvent
0x1800c0b08  nop     dword ptr [rax+rax+00h]
0x1800c0b0d  mov     cs:gTerminateBndSendThreadEvent, rax
0x1800c0b14  test    rax, rax
0x1800c0b17  jnz     short loc_1800C0B30
0x1800c0b19  call    cs:__imp_WSAGetLastError
0x1800c0b20  nop     dword ptr [rax+rax+00h]
0x1800c0b25  mov     r9d, 0F2Ch
0x1800c0b2b  jmp     loc_1800C0A9D
0x1800c0b30  call    cs:__imp_WSACreateEvent
0x1800c0b37  nop     dword ptr [rax+rax+00h]
0x1800c0b3c  mov     cs:gTerminateBndRecvThreadEvent, rax
0x1800c0b43  test    rax, rax
0x1800c0b46  jnz     short loc_1800C0B5F
0x1800c0b48  call    cs:__imp_WSAGetLastError
0x1800c0b4f  nop     dword ptr [rax+rax+00h]
0x1800c0b54  mov     r9d, 0F2Dh
0x1800c0b5a  jmp     loc_1800C0A9D
0x1800c0b5f  call    cs:__imp_WSACreateEvent
0x1800c0b66  nop     dword ptr [rax+rax+00h]
0x1800c0b6b  mov     cs:gTerminateBndSendThreadCompleteEvent, rax
0x1800c0b72  test    rax, rax
0x1800c0b75  jnz     short loc_1800C0B8E
0x1800c0b77  call    cs:__imp_WSAGetLastError
0x1800c0b7e  nop     dword ptr [rax+rax+00h]
0x1800c0b83  mov     r9d, 0F2Eh
0x1800c0b89  jmp     loc_1800C0A9D
0x1800c0b8e  call    cs:__imp_WSACreateEvent
0x1800c0b95  nop     dword ptr [rax+rax+00h]
0x1800c0b9a  mov     cs:gTerminateBndRecvThreadCompleteEvent, rax
0x1800c0ba1  test    rax, rax
0x1800c0ba4  jnz     short loc_1800C0BBD
0x1800c0ba6  call    cs:__imp_WSAGetLastError
0x1800c0bad  nop     dword ptr [rax+rax+00h]
0x1800c0bb2  mov     r9d, 0F2Fh
0x1800c0bb8  jmp     loc_1800C0A9D
0x1800c0bbd  call    cs:__imp_WSACreateEvent
0x1800c0bc4  nop     dword ptr [rax+rax+00h]
0x1800c0bc9  mov     cs:gStartBndCoreProcessingReqEvent, rax
0x1800c0bd0  test    rax, rax
0x1800c0bd3  jnz     short loc_1800C0BEC
0x1800c0bd5  call    cs:__imp_WSAGetLastError
0x1800c0bdc  nop     dword ptr [rax+rax+00h]
0x1800c0be1  mov     r9d, 0F30h
0x1800c0be7  jmp     loc_1800C0A9D
0x1800c0bec  call    cs:__imp_WSACreateEvent
0x1800c0bf3  nop     dword ptr [rax+rax+00h]
0x1800c0bf8  mov     cs:gTerminateBndCoreThreadEvent, rax
0x1800c0bff  test    rax, rax
0x1800c0c02  jnz     short loc_1800C0C1B
0x1800c0c04  call    cs:__imp_WSAGetLastError
0x1800c0c0b  nop     dword ptr [rax+rax+00h]
0x1800c0c10  mov     r9d, 0F31h
0x1800c0c16  jmp     loc_1800C0A9D
0x1800c0c1b  call    cs:__imp_WSACreateEvent
0x1800c0c22  nop     dword ptr [rax+rax+00h]
0x1800c0c27  mov     cs:gTerminateBndCoreThreadCompleteEvent, rax
0x1800c0c2e  test    rax, rax
0x1800c0c31  jnz     short loc_1800C0C4A
0x1800c0c33  call    cs:__imp_WSAGetLastError
0x1800c0c3a  nop     dword ptr [rax+rax+00h]
0x1800c0c3f  mov     r9d, 0F32h
0x1800c0c45  jmp     loc_1800C0A9D
0x1800c0c4a  lea     rcx, gBndFailoverEndpointCS; lpCriticalSection
0x1800c0c51  call    cs:__imp_InitializeCriticalSection
0x1800c0c58  nop     dword ptr [rax+rax+00h]
0x1800c0c5d  mov     edi, ebp
0x1800c0c5f  mov     rcx, cs:gDhcpHeap; hHeap
0x1800c0c66  mov     edx, 8; dwFlags
0x1800c0c6b  lea     r8d, [rdx+8]; dwBytes
0x1800c0c6f  call    cs:__imp_HeapAlloc
0x1800c0c76  nop     dword ptr [rax+rax+00h]
0x1800c0c7b  mov     [rsi], rax
0x1800c0c7e  test    rax, rax
0x1800c0c81  jz      loc_1800C0DCB
0x1800c0c87  mov     [rax+8], ebp
0x1800c0c8a  xor     r8d, r8d
0x1800c0c8d  mov     edx, cs:gFailoverLeaseDbQMaxSize
0x1800c0c93  mov     rcx, rax
0x1800c0c96  call    MessageQInitialize
0x1800c0c9b  mov     ebx, eax
0x1800c0c9d  test    eax, eax
0x1800c0c9f  jz      short loc_1800C0CBC
0x1800c0ca1  mov     r9d, 0F3Ch
0x1800c0ca7  lea     r8, aMessageqinitia; "MessageQInitialize"
0x1800c0cae  lea     rdx, aDhcpbndinitial; "DhcpBNDInitialize"
0x1800c0cb5  mov     ecx, eax
0x1800c0cb7  call    DhcpPrintFOErrorEx
0x1800c0cbc  inc     edi
0x1800c0cbe  add     rsi, 8
0x1800c0cc2  cmp     edi, 20h ; ' '
0x1800c0cc5  jb      short loc_1800C0C5F
0x1800c0cc7  lea     rax, [rsp+48h+ThreadId]
0x1800c0ccc  xor     r9d, r9d; lpParameter
0x1800c0ccf  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x1800c0cd4  lea     r8, DhcpBNDReceiveThread; lpStartAddress
0x1800c0cdb  xor     edx, edx; dwStackSize
0x1800c0cdd  mov     [rsp+48h+dwCreationFlags], ebp; dwCreationFlags
0x1800c0ce1  xor     ecx, ecx; lpThreadAttributes
0x1800c0ce3  call    cs:__imp_CreateThread
0x1800c0cea  nop     dword ptr [rax+rax+00h]
0x1800c0cef  mov     cs:gBndRecvThreadHandle, rax
0x1800c0cf6  test    rax, rax
0x1800c0cf9  jnz     short loc_1800C0D19
0x1800c0cfb  call    cs:__imp_GetLastError
0x1800c0d02  nop     dword ptr [rax+rax+00h]
0x1800c0d07  mov     r9d, 0F46h
0x1800c0d0d  lea     r8, aCreatethreadDh_1; "CreateThread_DhcpBNDReceiveThread"
0x1800c0d14  jmp     loc_1800C0DB5
0x1800c0d19  lea     rax, [rsp+48h+arg_8]
0x1800c0d1e  xor     r9d, r9d; lpParameter
0x1800c0d21  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x1800c0d26  lea     r8, DhcpBNDSendThread; lpStartAddress
0x1800c0d2d  xor     edx, edx; dwStackSize
0x1800c0d2f  mov     [rsp+48h+dwCreationFlags], ebp; dwCreationFlags
0x1800c0d33  xor     ecx, ecx; lpThreadAttributes
0x1800c0d35  call    cs:__imp_CreateThread
0x1800c0d3c  nop     dword ptr [rax+rax+00h]
0x1800c0d41  mov     cs:gBndSendThreadHandle, rax
0x1800c0d48  test    rax, rax
0x1800c0d4b  jnz     short loc_1800C0D68
0x1800c0d4d  call    cs:__imp_GetLastError
0x1800c0d54  nop     dword ptr [rax+rax+00h]
0x1800c0d59  mov     r9d, 0F4Fh
0x1800c0d5f  lea     r8, aCreatethreadDh_0; "CreateThread_DhcpBNDSendThread"
0x1800c0d66  jmp     short loc_1800C0DB5
0x1800c0d68  lea     rax, [rsp+48h+arg_10]
0x1800c0d6d  xor     r9d, r9d; lpParameter
0x1800c0d70  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x1800c0d75  lea     r8, DhcpBNDSendCorePacketsThread; lpStartAddress
0x1800c0d7c  xor     edx, edx; dwStackSize
0x1800c0d7e  mov     [rsp+48h+dwCreationFlags], ebp; dwCreationFlags
0x1800c0d82  xor     ecx, ecx; lpThreadAttributes
0x1800c0d84  call    cs:__imp_CreateThread
0x1800c0d8b  nop     dword ptr [rax+rax+00h]
0x1800c0d90  mov     cs:gBndCoreThreadHandle, rax
0x1800c0d97  test    rax, rax
0x1800c0d9a  jnz     short loc_1800C0DC5
0x1800c0d9c  call    cs:__imp_GetLastError
0x1800c0da3  nop     dword ptr [rax+rax+00h]
0x1800c0da8  mov     r9d, 0F58h
0x1800c0dae  lea     r8, aCreatethreadDh; "CreateThread_DhcpBNDSendCorePacketsThre"...
0x1800c0db5  lea     rdx, aDhcpbndinitial; "DhcpBNDInitialize"
0x1800c0dbc  mov     ecx, eax
0x1800c0dbe  mov     ebx, eax
0x1800c0dc0  call    DhcpPrintFOErrorEx
0x1800c0dc5  test    ebx, ebx
0x1800c0dc7  jz      short loc_1800C0DF0
0x1800c0dc9  jmp     short loc_1800C0DEB
0x1800c0dcb  mov     ebx, 8
0x1800c0dd0  lea     r8, aDhcpallocateme; "DhcpAllocateMemory"
0x1800c0dd7  mov     ecx, ebx
0x1800c0dd9  lea     rdx, aDhcpbndinitial; "DhcpBNDInitialize"
0x1800c0de0  mov     r9d, 0F39h
0x1800c0de6  call    DhcpPrintFOErrorEx
0x1800c0deb  call    DhcpBNDCleanup
0x1800c0df0  mov     eax, ebx
0x1800c0df2  mov     rbx, [rsp+48h+arg_18]
0x1800c0df7  add     rsp, 30h
0x1800c0dfb  pop     rdi
0x1800c0dfc  pop     rsi
0x1800c0dfd  pop     rbp
0x1800c0dfe  retn
```
