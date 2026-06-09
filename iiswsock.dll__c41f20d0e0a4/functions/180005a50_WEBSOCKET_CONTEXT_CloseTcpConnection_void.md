# WEBSOCKET_CONTEXT::CloseTcpConnection(void)

- ea: `0x180005a50`
- end: `0x180005ae2`
- name: `?CloseTcpConnection@WEBSOCKET_CONTEXT@@UEAAXXZ`
- size: `146`
- prototype: `void __fastcall(WEBSOCKET_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001ce0`
- `0x180005a50`
- `0x180009010`

## import_xrefs

- `websocket!WebSocketAbortHandle` at `0x180005aa0`
- `websocket!WebSocketAbortHandle` at `0x180005aa0`
- `iisutil!PuDbgPrint` at `0x180005a93`
- `iisutil!PuDbgPrint` at `0x180005a93`

## string_xrefs

- `0x180005a8c`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\websocketcontext.cxx`

## pseudocode

```c
void __fastcall WEBSOCKET_CONTEXT::CloseTcpConnection(WEBSOCKET_CONTEXT *this)
{
  bool v1; // zf
  __int64 v3; // rax
  TRACE_HELPER *v4; // rcx

  v1 = (g_dwDebugFlags & 0xF) == 0;
  *((_DWORD *)this + 93) = 1;
  if ( !v1 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\websocketcontext.cxx",
      1007,
      "WEBSOCKET_CONTEXT::CloseTcpConnection",
      "Reset Connection \n");
  WebSocketAbortHandle(*((_QWORD *)this + 17));
  v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 19) + 32LL))(*((_QWORD *)this + 19));
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 104LL))(v3);
  TRACE_HELPER::RaiseTraceEvent(v4, *((struct IHttpContext **)this + 43), 0x40u);
}

```

## disassembly

```asm
0x180005a50  push    rbx
0x180005a52  sub     rsp, 30h
0x180005a56  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005a5d  mov     rbx, rcx
0x180005a60  mov     dword ptr [rcx+174h], 1
0x180005a6a  jz      short loc_180005A99
0x180005a6c  mov     rcx, cs:g_pDebug
0x180005a73  lea     rax, aResetConnectio; "Reset Connection \n"
0x180005a7a  lea     r9, aWebsocketConte_1; "WEBSOCKET_CONTEXT::CloseTcpConnection"
0x180005a81  mov     [rsp+38h+var_18], rax
0x180005a86  mov     r8d, 3EFh
0x180005a8c  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005a93  call    cs:__imp_PuDbgPrint
0x180005a99  mov     rcx, [rbx+88h]
0x180005aa0  call    cs:__imp_WebSocketAbortHandle
0x180005aa6  mov     rcx, [rbx+98h]
0x180005aad  mov     rax, [rcx]
0x180005ab0  mov     rax, [rax+20h]
0x180005ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ab9  mov     rdx, rax
0x180005abc  mov     rcx, [rax]
0x180005abf  mov     rax, [rcx+68h]
0x180005ac3  mov     rcx, rdx
0x180005ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005acb  mov     rdx, [rbx+158h]; struct IHttpContext *
0x180005ad2  mov     r8d, 40h ; '@'; unsigned int
0x180005ad8  add     rsp, 30h
0x180005adc  pop     rbx
0x180005add  jmp     ?RaiseTraceEvent@TRACE_HELPER@@QEAAXPEAVIHttpContext@@K@Z; TRACE_HELPER::RaiseTraceEvent(IHttpContext *,ulong)
```
