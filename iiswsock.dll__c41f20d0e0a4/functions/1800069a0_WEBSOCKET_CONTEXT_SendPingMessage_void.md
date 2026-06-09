# WEBSOCKET_CONTEXT::SendPingMessage(void)

- ea: `0x1800069a0`
- end: `0x180006c90`
- name: `?SendPingMessage@WEBSOCKET_CONTEXT@@QEAAJXZ`
- size: `752`
- prototype: `__int64 __fastcall(WEBSOCKET_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003480`

## callees

- `0x180002974`
- `0x180004ebc`
- `0x1800069a0`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180006a30`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180006a30`
- `iisutil!WriteRefTraceLog` at `0x180006b1a`
- `iisutil!WriteRefTraceLog` at `0x180006bae`
- `iisutil!WriteRefTraceLog` at `0x180006c12`
- `iisutil!WriteRefTraceLog` at `0x180006b1a`
- `iisutil!WriteRefTraceLog` at `0x180006bae`
- `iisutil!WriteRefTraceLog` at `0x180006c12`
- `iisutil!PuDbgPrint` at `0x1800069f2`
- `iisutil!PuDbgPrint` at `0x180006a90`
- `iisutil!PuDbgPrint` at `0x180006af3`
- `iisutil!PuDbgPrint` at `0x180006b7d`
- `iisutil!PuDbgPrint` at `0x180006c73`
- `iisutil!PuDbgPrint` at `0x1800069f2`
- `iisutil!PuDbgPrint` at `0x180006a90`
- `iisutil!PuDbgPrint` at `0x180006af3`
- `iisutil!PuDbgPrint` at `0x180006b7d`
- `iisutil!PuDbgPrint` at `0x180006c73`

## string_xrefs

- `0x1800069ca`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\websocketcontext.cxx`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_CONTEXT::SendPingMessage(WEBSOCKET_CONTEXT *this)
{
  __int64 v2; // rdi
  ULONGLONG v3; // rbx
  TRACE_HELPER *v4; // rcx
  unsigned int v5; // r8d
  signed __int32 v6; // edx
  __int64 v7; // rcx
  __int64 v8; // rdx
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rcx
  __int64 v13; // rcx
  int v14; // [rsp+60h] [rbp+8h] BYREF

  v14 = 0;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\websocketcontext.cxx",
      1319,
      "WEBSOCKET_CONTEXT::SendPingMessage",
      "Send Ping\n");
  if ( *((_DWORD *)this + 89) || *((_DWORD *)this + 90) || *((_DWORD *)this + 93) )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\websocketcontext.cxx",
        1328,
        "WEBSOCKET_CONTEXT::SendPingMessage",
        "Connection is going away, return\n");
    return 2147500037LL;
  }
  v2 = *((_QWORD *)this + 14);
  v3 = *(unsigned int *)(*((_QWORD *)this + 33) + 24LL);
  if ( GetTickCount64() - v2 <= v3
    || !*((_DWORD *)this + 92) && *(_DWORD *)(*((_QWORD *)this + 34) + 76LL) < *(_DWORD *)(*((_QWORD *)this + 34) + 8LL) )
  {
    return 0;
  }
  if ( *((_DWORD *)this + 91) )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\websocketcontext.cxx",
        1362,
        "WEBSOCKET_CONTEXT::SendPingMessage",
        "Pong Pending, closing connection\n");
    (*(void (__fastcall **)(WEBSOCKET_CONTEXT *))(*(_QWORD *)this + 40LL))(this);
    TRACE_HELPER::RaiseTraceEventOnModuleCloseConnection(v4, *((struct IHttpContext **)this + 43), v5);
    return 2147500037LL;
  }
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 94, 1, 0) )
    return 0;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\websocketcontext.cxx",
      1386,
      "WEBSOCKET_CONTEXT::SendPingMessage",
      "Sending Ping\n");
  *((_DWORD *)this + 91) = 1;
  v6 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 95, 1u);
  v7 = *((_QWORD *)this + 54);
  v8 = (unsigned int)(v6 + 1);
  if ( v7 )
    WriteRefTraceLog(v7, v8, this);
  v9 = WEBSOCKET_WRAPPER::Send(
         (ULONGLONG *)this + 14,
         0x80000005,
         0,
         (__int64)WEBSOCKET_CONTEXT::OnWebSocketSendPingCompletion,
         (__int64)this,
         &v14);
  v10 = v9;
  if ( v9 >= 0 )
  {
    if ( !v14 )
    {
      _InterlockedCompareExchange((volatile signed __int32 *)this + 94, 0, 1);
      v13 = *((_QWORD *)this + 54);
      if ( v13 )
        WriteRefTraceLog(v13, *((unsigned int *)this + 95), this);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 95, 0xFFFFFFFF) == 1 && *((_DWORD *)this + 88) == 3 )
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 43) + 64LL))(*((_QWORD *)this + 43), 0);
    }
    return 0;
  }
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\websocketcontext.cxx",
      1407,
      "WEBSOCKET_CONTEXT::SendPingMessage",
      "ERROR = %08x\n",
      v9);
  *((_DWORD *)this + 91) = 0;
  _InterlockedCompareExchange((volatile signed __int32 *)this + 94, 0, 1);
  v11 = *((_QWORD *)this + 54);
  if ( v11 )
    WriteRefTraceLog(v11, *((unsigned int *)this + 95), this);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 95, 0xFFFFFFFF) == 1 && *((_DWORD *)this + 88) == 3 )
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 43) + 64LL))(*((_QWORD *)this + 43), 0);
  return v10;
}

```

## disassembly

```asm
0x1800069a0  mov     [rsp+arg_10], rbx
0x1800069a5  push    rsi
0x1800069a6  push    rdi
0x1800069a7  push    r12
0x1800069a9  push    r14
0x1800069ab  push    r15
0x1800069ad  sub     rsp, 30h
0x1800069b1  test    byte ptr cs:g_dwDebugFlags, 3
0x1800069b8  lea     r15, aWebsocketConte_7; "WEBSOCKET_CONTEXT::SendPingMessage"
0x1800069bf  mov     rsi, rcx
0x1800069c2  mov     [rsp+58h+arg_0], 0
0x1800069ca  lea     r12, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800069d1  jz      short loc_1800069F8
0x1800069d3  mov     rcx, cs:g_pDebug
0x1800069da  lea     rax, aSendPing; "Send Ping\n"
0x1800069e1  mov     r9, r15
0x1800069e4  mov     [rsp+58h+var_38], rax
0x1800069e9  mov     r8d, 527h
0x1800069ef  mov     rdx, r12
0x1800069f2  call    cs:__imp_PuDbgPrint
0x1800069f8  mov     eax, [rsi+164h]
0x1800069fe  test    eax, eax
0x180006a00  jnz     loc_180006C4B
0x180006a06  mov     eax, [rsi+168h]
0x180006a0c  test    eax, eax
0x180006a0e  jnz     loc_180006C4B
0x180006a14  mov     eax, [rsi+174h]
0x180006a1a  test    eax, eax
0x180006a1c  jnz     loc_180006C4B
0x180006a22  mov     rax, [rsi+108h]
0x180006a29  mov     rdi, [rsi+70h]
0x180006a2d  mov     ebx, [rax+18h]
0x180006a30  call    cs:__imp_GetTickCount64
0x180006a36  sub     rax, rdi
0x180006a39  cmp     rax, rbx
0x180006a3c  jbe     loc_180006C47
0x180006a42  cmp     dword ptr [rsi+170h], 0
0x180006a49  jnz     short loc_180006A5E
0x180006a4b  mov     rcx, [rsi+110h]
0x180006a52  mov     eax, [rcx+8]
0x180006a55  cmp     [rcx+4Ch], eax
0x180006a58  jb      loc_180006C47
0x180006a5e  mov     eax, [rsi+16Ch]
0x180006a64  test    eax, eax
0x180006a66  jz      short loc_180006AB6
0x180006a68  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006a6f  jz      short loc_180006A96
0x180006a71  mov     rcx, cs:g_pDebug
0x180006a78  lea     rax, aPongPendingClo; "Pong Pending, closing connection\n"
0x180006a7f  mov     r9, r15
0x180006a82  mov     [rsp+58h+var_38], rax
0x180006a87  mov     r8d, 552h
0x180006a8d  mov     rdx, r12
0x180006a90  call    cs:__imp_PuDbgPrint
0x180006a96  mov     rax, [rsi]
0x180006a99  mov     rcx, rsi
0x180006a9c  mov     rax, [rax+28h]
0x180006aa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006aa5  mov     rdx, [rsi+158h]; struct IHttpContext *
0x180006aac  call    ?RaiseTraceEventOnModuleCloseConnection@TRACE_HELPER@@QEAAXPEAVIHttpContext@@K@Z; TRACE_HELPER::RaiseTraceEventOnModuleCloseConnection(IHttpContext *,ulong)
0x180006ab1  jmp     loc_180006C79
0x180006ab6  mov     edi, 1
0x180006abb  xor     eax, eax
0x180006abd  lock cmpxchg [rsi+178h], edi
0x180006ac5  jnz     loc_180006C47
0x180006acb  test    byte ptr cs:g_dwDebugFlags, 3
0x180006ad2  jz      short loc_180006AF9
0x180006ad4  mov     rcx, cs:g_pDebug
0x180006adb  lea     rax, aSendingPing; "Sending Ping\n"
0x180006ae2  mov     r9, r15
0x180006ae5  mov     [rsp+58h+var_38], rax
0x180006aea  mov     r8d, 56Ah
0x180006af0  mov     rdx, r12
0x180006af3  call    cs:__imp_PuDbgPrint
0x180006af9  mov     [rsi+16Ch], edi
0x180006aff  mov     edx, edi
0x180006b01  lock xadd [rsi+17Ch], edx
0x180006b09  mov     rcx, [rsi+1B0h]
0x180006b10  add     edx, edi
0x180006b12  test    rcx, rcx
0x180006b15  jz      short loc_180006B20
0x180006b17  mov     r8, rsi
0x180006b1a  call    cs:__imp_WriteRefTraceLog
0x180006b20  lea     rax, [rsp+58h+arg_0]
0x180006b25  xor     r8d, r8d
0x180006b28  mov     [rsp+58h+var_30], rax
0x180006b2d  lea     r9, ?OnWebSocketSendPingCompletion@WEBSOCKET_CONTEXT@@CAXPEAXJ@Z; WEBSOCKET_CONTEXT::OnWebSocketSendPingCompletion(void *,long)
0x180006b34  mov     edx, 80000005h
0x180006b39  mov     [rsp+58h+var_38], rsi
0x180006b3e  lea     rcx, [rsi+70h]
0x180006b42  call    ?Send@WEBSOCKET_WRAPPER@@QEAAJW4_WEB_SOCKET_BUFFER_TYPE@@PEAT_WEB_SOCKET_BUFFER@@P6AXPEAXJ@Z2PEAH@Z; WEBSOCKET_WRAPPER::Send(_WEB_SOCKET_BUFFER_TYPE,_WEB_SOCKET_BUFFER *,void (*)(void *,long),void *,int *)
0x180006b47  mov     ebx, eax
0x180006b49  test    eax, eax
0x180006b4b  jns     loc_180006BEA
0x180006b51  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006b58  jz      short loc_180006B83
0x180006b5a  lea     rcx, aError08x; "ERROR = %08x\n"
0x180006b61  mov     dword ptr [rsp+58h+var_30], eax
0x180006b65  mov     [rsp+58h+var_38], rcx
0x180006b6a  mov     r9, r15
0x180006b6d  mov     rcx, cs:g_pDebug
0x180006b74  mov     r8d, 57Fh
0x180006b7a  mov     rdx, r12
0x180006b7d  call    cs:__imp_PuDbgPrint
0x180006b83  mov     dword ptr [rsi+16Ch], 0
0x180006b8d  xor     ecx, ecx
0x180006b8f  mov     eax, edi
0x180006b91  lock cmpxchg [rsi+178h], ecx
0x180006b99  mov     rcx, [rsi+1B0h]
0x180006ba0  test    rcx, rcx
0x180006ba3  jz      short loc_180006BB4
0x180006ba5  mov     edx, [rsi+17Ch]
0x180006bab  mov     r8, rsi
0x180006bae  call    cs:__imp_WriteRefTraceLog
0x180006bb4  or      eax, 0FFFFFFFFh
0x180006bb7  lock xadd [rsi+17Ch], eax
0x180006bbf  cmp     eax, edi
0x180006bc1  jnz     short loc_180006BE3
0x180006bc3  mov     eax, [rsi+160h]
0x180006bc9  cmp     eax, 3
0x180006bcc  jnz     short loc_180006BE3
0x180006bce  mov     rcx, [rsi+158h]
0x180006bd5  xor     edx, edx
0x180006bd7  mov     rax, [rcx]
0x180006bda  mov     rax, [rax+40h]
0x180006bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006be3  mov     eax, ebx
0x180006be5  jmp     loc_180006C7E
0x180006bea  cmp     [rsp+58h+arg_0], 0
0x180006bef  jnz     short loc_180006C47
0x180006bf1  xor     ecx, ecx
0x180006bf3  mov     eax, edi
0x180006bf5  lock cmpxchg [rsi+178h], ecx
0x180006bfd  mov     rcx, [rsi+1B0h]
0x180006c04  test    rcx, rcx
0x180006c07  jz      short loc_180006C18
0x180006c09  mov     edx, [rsi+17Ch]
0x180006c0f  mov     r8, rsi
0x180006c12  call    cs:__imp_WriteRefTraceLog
0x180006c18  or      eax, 0FFFFFFFFh
0x180006c1b  lock xadd [rsi+17Ch], eax
0x180006c23  cmp     eax, edi
0x180006c25  jnz     short loc_180006C47
0x180006c27  mov     eax, [rsi+160h]
0x180006c2d  cmp     eax, 3
0x180006c30  jnz     short loc_180006C47
0x180006c32  mov     rcx, [rsi+158h]
0x180006c39  xor     edx, edx
0x180006c3b  mov     rax, [rcx]
0x180006c3e  mov     rax, [rax+40h]
0x180006c42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c47  xor     eax, eax
0x180006c49  jmp     short loc_180006C7E
0x180006c4b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006c52  jz      short loc_180006C79
0x180006c54  mov     rcx, cs:g_pDebug
0x180006c5b  lea     rax, aConnectionIsGo; "Connection is going away, return\n"
0x180006c62  mov     r9, r15
0x180006c65  mov     [rsp+58h+var_38], rax
0x180006c6a  mov     r8d, 530h
0x180006c70  mov     rdx, r12
0x180006c73  call    cs:__imp_PuDbgPrint
0x180006c79  mov     eax, 80004005h
0x180006c7e  mov     rbx, [rsp+58h+arg_10]
0x180006c83  add     rsp, 30h
0x180006c87  pop     r15
0x180006c89  pop     r14
0x180006c8b  pop     r12
0x180006c8d  pop     rdi
0x180006c8e  pop     rsi
0x180006c8f  retn
```
