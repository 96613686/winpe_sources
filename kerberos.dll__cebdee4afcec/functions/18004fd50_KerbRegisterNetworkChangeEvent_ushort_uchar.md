# KerbRegisterNetworkChangeEvent(ushort,uchar)

- ea: `0x18004fd50`
- end: `0x180050071`
- name: `?KerbRegisterNetworkChangeEvent@@YAJGE@Z`
- size: `801`
- prototype: `__int64 __fastcall(unsigned __int16, unsigned __int8)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18004fcb0`
- `0x180091810`

## callees

- `0x18004fd50`
- `0x18008b70c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004feab`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004feab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fed8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fed8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050020`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050020`
- `ntdll!RtlRegisterWait` at `0x18004ff69`
- `ntdll!RtlRegisterWait` at `0x18004ff69`
- `ntdll!RtlDeregisterWait` at `0x18004ff3f`
- `ntdll!RtlDeregisterWait` at `0x18005000e`
- `ntdll!RtlDeregisterWait` at `0x18004ff3f`
- `ntdll!RtlDeregisterWait` at `0x18005000e`
- `WS2_32!WSASocketW` at `0x18004fe31`
- `WS2_32!WSASocketW` at `0x18004fe31`
- `WS2_32!WSAIoctl` at `0x18004ffc8`
- `WS2_32!WSAIoctl` at `0x18004ffc8`
- `WS2_32!WSAEventSelect` at `0x18004feed`
- `WS2_32!WSAEventSelect` at `0x18004feed`
- `WS2_32!__imp_closesocket` at `0x180050032`
- `WS2_32!__imp_closesocket` at `0x180050032`
- `WS2_32!__imp_WSAGetLastError` at `0x18004fe40`
- `WS2_32!__imp_WSAGetLastError` at `0x18004fef7`
- `WS2_32!__imp_WSAGetLastError` at `0x18004ffd2`
- `WS2_32!__imp_WSAGetLastError` at `0x18004fe40`
- `WS2_32!__imp_WSAGetLastError` at `0x18004fef7`
- `WS2_32!__imp_WSAGetLastError` at `0x18004ffd2`

## string_xrefs

- `0x18004fecb`: `Cannot create Winsock PNP event %ld\n`

## pseudocode

```c
__int64 __fastcall KerbRegisterNetworkChangeEvent(unsigned __int16 a1, char a2)
{
  unsigned __int64 v2; // rax
  unsigned __int64 *v3; // r14
  void **v4; // rbp
  HANDLE *v5; // r15
  SOCKET v7; // rax
  DWORD Error; // eax
  unsigned int v9; // r13d
  const char *v10; // r12
  HANDLE EventW; // rax
  unsigned int v12; // ebx
  NTSTATUS v13; // eax
  int v14; // eax
  GROUP g[2]; // [rsp+20h] [rbp-58h]
  DWORD cbBytesReturned; // [rsp+80h] [rbp+8h] BYREF

  cbBytesReturned = 0;
  if ( a1 == 2 )
  {
    v2 = KerbPNPSocket;
    v3 = &KerbPNPSocket;
    v4 = &KerbPNPSocketEvent;
    v5 = &KerbPNPSocketWaitHandle;
  }
  else
  {
    if ( a1 != 23 )
    {
      KerbTracerT::Log(1, "KerbRegisterNetworkChangeEvent", 123, "Invalid address family: %x\n", a1);
      return 3221225485LL;
    }
    v2 = KerbPNPSocketV6;
    v3 = &KerbPNPSocketV6;
    v4 = &KerbPNPSocketEventV6;
    v5 = &KerbPNPSocketWaitHandleV6;
  }
  if ( !a2 )
    goto LABEL_17;
  if ( !v2 )
  {
    v7 = WSASocketW(a1, 2, 0, 0, 0, 0);
    *v3 = v7;
    if ( v7 == -1 )
    {
      Error = WSAGetLastError();
      if ( Error == 10047 )
        return 0;
      if ( Error == 10022 )
      {
        KerbTracerT::Log(1, "KerbRegisterNetworkChangeEvent", 160, "WSASocket failed with %ld\n", 10022);
        KerbTracerT::Log(
          1,
          "KerbRegisterNetworkChangeEvent",
          161,
          "This failure can be caused by disabling IP using netsh netio bindingfilter\n");
        return 0;
      }
      v9 = 166;
      v10 = "WSASocket failed with %ld\n";
LABEL_19:
      v12 = -1073741595;
      goto LABEL_20;
    }
    EventW = CreateEventW(0, 0, 0, 0);
    *v4 = EventW;
    if ( !EventW )
    {
      v12 = -1073741595;
      v10 = "Cannot create Winsock PNP event %ld\n";
      v9 = 182;
      Error = GetLastError();
LABEL_20:
      g[0] = Error;
      KerbTracerT::Log(1, "KerbRegisterNetworkChangeEvent", v9, v10, *(_QWORD *)g);
      goto LABEL_28;
    }
LABEL_17:
    if ( !WSAEventSelect(*v3, *v4, 512) )
    {
      if ( *v5 )
      {
        RtlDeregisterWait(*v5);
        *v5 = 0;
      }
      v13 = RtlRegisterWait(v5, *v4, KerbSocketChangeHandler, v3, 0xFFFFFFFF, 8u);
      v12 = v13;
      if ( v13 >= 0 )
      {
        if ( !WSAIoctl(*v3, 0x28000017u, 0, 0, 0, 0, &cbBytesReturned, 0, 0) )
          return v12;
        v14 = WSAGetLastError();
        if ( v14 == 10035 )
          return v12;
        KerbTracerT::Log(1, "KerbRegisterNetworkChangeEvent", 246, "WSAIOCTL failed %x\n", v14);
        v12 = -1073741595;
      }
      else
      {
        KerbTracerT::Log(1, "KerbRegisterNetworkChangeEvent", 221, "RtlRegisterWait failed %x\n", v13);
      }
LABEL_28:
      if ( *v5 )
      {
        RtlDeregisterWait(*v5);
        *v5 = 0;
      }
      if ( *v4 )
      {
        CloseHandle(*v4);
        *v4 = 0;
      }
      if ( *v3 )
      {
        closesocket(*v3);
        *v3 = 0;
      }
      return v12;
    }
    Error = WSAGetLastError();
    v9 = 199;
    v10 = "Can't WSAEventSelect %ld\n";
    goto LABEL_19;
  }
  KerbTracerT::Log(1, "KerbRegisterNetworkChangeEvent", 134, "Second init of network change event\n");
  return 0;
}

```

## disassembly

```asm
0x18004fd50  mov     [rsp+arg_18], rbp
0x18004fd55  push    rsi
0x18004fd56  push    rdi
0x18004fd57  push    r13
0x18004fd59  push    r14
0x18004fd5b  push    r15
0x18004fd5d  sub     rsp, 50h
0x18004fd61  xor     r13d, r13d
0x18004fd64  mov     [rsp+78h+cbBytesReturned], r13d
0x18004fd6c  cmp     cx, 2
0x18004fd70  jnz     short loc_18004FD90
0x18004fd72  mov     rax, cs:?KerbPNPSocket@@3_KA; unsigned __int64 KerbPNPSocket
0x18004fd79  lea     r14, ?KerbPNPSocket@@3_KA; unsigned __int64 KerbPNPSocket
0x18004fd80  lea     rbp, ?KerbPNPSocketEvent@@3PEAXEA; void * KerbPNPSocketEvent
0x18004fd87  lea     r15, ?KerbPNPSocketWaitHandle@@3PEAXEA; void * KerbPNPSocketWaitHandle
0x18004fd8e  jmp     short loc_18004FDB6
0x18004fd90  cmp     cx, 17h
0x18004fd94  jnz     loc_180050042
0x18004fd9a  mov     rax, cs:?KerbPNPSocketV6@@3_KA; unsigned __int64 KerbPNPSocketV6
0x18004fda1  lea     r14, ?KerbPNPSocketV6@@3_KA; unsigned __int64 KerbPNPSocketV6
0x18004fda8  lea     rbp, ?KerbPNPSocketEventV6@@3PEAXEA; void * KerbPNPSocketEventV6
0x18004fdaf  lea     r15, ?KerbPNPSocketWaitHandleV6@@3PEAXEA; void * KerbPNPSocketWaitHandleV6
0x18004fdb6  mov     [rsp+78h+arg_8], rbx
0x18004fdbe  mov     [rsp+78h+arg_10], r12
0x18004fdc6  test    dl, dl
0x18004fdc8  jz      loc_18004FEE0
0x18004fdce  test    rax, rax
0x18004fdd1  jz      short loc_18004FE19
0x18004fdd3  lea     r9, aSecondInitOfNe; "Second init of network change event\n"
0x18004fdda  mov     r8d, 86h
0x18004fde0  lea     rdx, aKerbregisterne; "KerbRegisterNetworkChangeEvent"
0x18004fde7  mov     ecx, 1
0x18004fdec  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18004fdf1  mov     eax, r13d
0x18004fdf4  mov     rbx, [rsp+78h+arg_8]
0x18004fdfc  mov     r12, [rsp+78h+arg_10]
0x18004fe04  mov     rbp, [rsp+78h+arg_18]
0x18004fe0c  add     rsp, 50h
0x18004fe10  pop     r15
0x18004fe12  pop     r14
0x18004fe14  pop     r13
0x18004fe16  pop     rdi
0x18004fe17  pop     rsi
0x18004fe18  retn
0x18004fe19  movzx   ecx, cx; af
0x18004fe1c  xor     r9d, r9d; lpProtocolInfo
0x18004fe1f  mov     [rsp+78h+dwFlags], r13d; dwFlags
0x18004fe24  xor     r8d, r8d; protocol
0x18004fe27  mov     edx, 2; type
0x18004fe2c  mov     [rsp+78h+g], r13d; g
0x18004fe31  call    cs:__imp_WSASocketW
0x18004fe37  mov     [r14], rax
0x18004fe3a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004fe3e  jnz     short loc_18004FEA1
0x18004fe40  call    cs:__imp_WSAGetLastError
0x18004fe46  cmp     eax, 273Fh
0x18004fe4b  jz      short loc_18004FDF1
0x18004fe4d  lea     rsi, aKerbregisterne; "KerbRegisterNetworkChangeEvent"
0x18004fe54  mov     edi, 1
0x18004fe59  cmp     eax, 2726h
0x18004fe5e  jnz     short loc_18004FE92
0x18004fe60  lea     r9, aWsasocketFaile; "WSASocket failed with %ld\n"
0x18004fe67  mov     [rsp+78h+g], eax
0x18004fe6b  mov     r8d, 0A0h
0x18004fe71  mov     rdx, rsi
0x18004fe74  mov     ecx, edi
0x18004fe76  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18004fe7b  lea     r9, aThisFailureCan; "This failure can be caused by disabling"...
0x18004fe82  mov     r8d, 0A1h
0x18004fe88  mov     rdx, rsi
0x18004fe8b  mov     ecx, edi
0x18004fe8d  jmp     loc_18004FDEC
0x18004fe92  mov     r13d, 0A6h
0x18004fe98  lea     r12, aWsasocketFaile; "WSASocket failed with %ld\n"
0x18004fe9f  jmp     short loc_18004FF16
0x18004fea1  xor     r9d, r9d; lpName
0x18004fea4  xor     r8d, r8d; bInitialState
0x18004fea7  xor     edx, edx; bManualReset
0x18004fea9  xor     ecx, ecx; lpEventAttributes
0x18004feab  call    cs:__imp_CreateEventW
0x18004feb1  mov     [rbp+0], rax
0x18004feb5  test    rax, rax
0x18004feb8  jnz     short loc_18004FEE0
0x18004feba  mov     ebx, 0C00000E5h
0x18004febf  lea     rsi, aKerbregisterne; "KerbRegisterNetworkChangeEvent"
0x18004fec6  mov     edi, 1
0x18004fecb  lea     r12, aCannotCreateWi; "Cannot create Winsock PNP event %ld\n"
0x18004fed2  mov     r13d, 0B6h
0x18004fed8  call    cs:__imp_GetLastError
0x18004fede  jmp     short loc_18004FF1B
0x18004fee0  mov     rdx, [rbp+0]; hEventObject
0x18004fee4  mov     r8d, 200h; lNetworkEvents
0x18004feea  mov     rcx, [r14]; s
0x18004feed  call    cs:__imp_WSAEventSelect
0x18004fef3  test    eax, eax
0x18004fef5  jz      short loc_18004FF37
0x18004fef7  call    cs:__imp_WSAGetLastError
0x18004fefd  mov     edi, 1
0x18004ff02  lea     rsi, aKerbregisterne; "KerbRegisterNetworkChangeEvent"
0x18004ff09  mov     r13d, 0C7h
0x18004ff0f  lea     r12, aCanTWsaeventse; "Can't WSAEventSelect %ld\n"
0x18004ff16  mov     ebx, 0C00000E5h
0x18004ff1b  mov     r9, r12
0x18004ff1e  mov     [rsp+78h+g], eax
0x18004ff22  mov     r8d, r13d
0x18004ff25  mov     rdx, rsi
0x18004ff28  mov     ecx, edi
0x18004ff2a  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18004ff2f  xor     r13d, r13d
0x18004ff32  jmp     loc_180050006
0x18004ff37  mov     rcx, [r15]; hWaitHandle
0x18004ff3a  test    rcx, rcx
0x18004ff3d  jz      short loc_18004FF48
0x18004ff3f  call    cs:__imp_RtlDeregisterWait
0x18004ff45  mov     [r15], r13
0x18004ff48  mov     rdx, [rbp+0]; hObject
0x18004ff4c  lea     r8, ?KerbSocketChangeHandler@@YAXPEAXE@Z; Callback
0x18004ff53  mov     [rsp+78h+dwFlags], 8; ulFlags
0x18004ff5b  mov     r9, r14; pvContext
0x18004ff5e  mov     rcx, r15; phNewWaitObject
0x18004ff61  mov     [rsp+78h+g], 0FFFFFFFFh; ulMilliseconds
0x18004ff69  call    cs:__imp_RtlRegisterWait
0x18004ff6f  mov     ebx, eax
0x18004ff71  test    eax, eax
0x18004ff73  jns     short loc_18004FF99
0x18004ff75  lea     r9, aRtlregisterwai; "RtlRegisterWait failed %x\n"
0x18004ff7c  mov     [rsp+78h+g], eax
0x18004ff80  mov     r8d, 0DDh
0x18004ff86  lea     rdx, aKerbregisterne; "KerbRegisterNetworkChangeEvent"
0x18004ff8d  mov     ecx, 1
0x18004ff92  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18004ff97  jmp     short loc_180050006
0x18004ff99  mov     rcx, [r14]; s
0x18004ff9c  lea     rax, [rsp+78h+cbBytesReturned]
0x18004ffa4  mov     [rsp+78h+lpCompletionRoutine], r13; lpCompletionRoutine
0x18004ffa9  xor     r9d, r9d; cbInBuffer
0x18004ffac  mov     [rsp+78h+lpOverlapped], r13; lpOverlapped
0x18004ffb1  xor     r8d, r8d; lpvInBuffer
0x18004ffb4  mov     [rsp+78h+lpcbBytesReturned], rax; lpcbBytesReturned
0x18004ffb9  mov     edx, 28000017h; dwIoControlCode
0x18004ffbe  mov     [rsp+78h+dwFlags], r13d; cbOutBuffer
0x18004ffc3  mov     qword ptr [rsp+78h+g], r13; lpvOutBuffer
0x18004ffc8  call    cs:__imp_WSAIoctl
0x18004ffce  test    eax, eax
0x18004ffd0  jz      short loc_18005003B
0x18004ffd2  call    cs:__imp_WSAGetLastError
0x18004ffd8  cmp     eax, 2733h
0x18004ffdd  jz      short loc_18005003B
0x18004ffdf  lea     r9, aWsaioctlFailed; "WSAIOCTL failed %x\n"
0x18004ffe6  mov     [rsp+78h+g], eax
0x18004ffea  mov     r8d, 0F6h
0x18004fff0  lea     rdx, aKerbregisterne; "KerbRegisterNetworkChangeEvent"
0x18004fff7  mov     ecx, 1
0x18004fffc  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180050001  mov     ebx, 0C00000E5h
0x180050006  mov     rcx, [r15]; hWaitHandle
0x180050009  test    rcx, rcx
0x18005000c  jz      short loc_180050017
0x18005000e  call    cs:__imp_RtlDeregisterWait
0x180050014  mov     [r15], r13
0x180050017  mov     rcx, [rbp+0]; hObject
0x18005001b  test    rcx, rcx
0x18005001e  jz      short loc_18005002A
0x180050020  call    cs:__imp_CloseHandle
0x180050026  mov     [rbp+0], r13
0x18005002a  mov     rcx, [r14]; s
0x18005002d  test    rcx, rcx
0x180050030  jz      short loc_18005003B
0x180050032  call    cs:__imp_closesocket
0x180050038  mov     [r14], r13
0x18005003b  mov     eax, ebx
0x18005003d  jmp     loc_18004FDF4
0x180050042  movzx   eax, cx
0x180050045  lea     r9, aInvalidAddress; "Invalid address family: %x\n"
0x18005004c  mov     ecx, 1
0x180050051  mov     [rsp+78h+g], eax
0x180050055  mov     r8d, 7Bh ; '{'
0x18005005b  lea     rdx, aKerbregisterne; "KerbRegisterNetworkChangeEvent"
0x180050062  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180050067  mov     eax, 0C000000Dh
0x18005006c  jmp     loc_18004FE04
```
