# WEBSOCKET_WRAPPER::Receive(_WEB_SOCKET_BUFFER *,_WEB_SOCKET_BUFFER_TYPE *,void (*)(void *,long,_WEB_SOCKET_BUFFER *,_WEB_SOCKET_BUFFER_TYPE),void *,int *)

- ea: `0x180004bac`
- end: `0x180004ea5`
- name: `?Receive@WEBSOCKET_WRAPPER@@QEAAJPEAT_WEB_SOCKET_BUFFER@@PEAW4_WEB_SOCKET_BUFFER_TYPE@@P6AXPEAXJ0W43@@Z2PEAH@Z`
- size: `761`
- prototype: `__int64 __fastcall(WEBSOCKET_WRAPPER *this, union _WEB_SOCKET_BUFFER *, enum _WEB_SOCKET_BUFFER_TYPE *, void (__high *)(void *, int, union _WEB_SOCKET_BUFFER *, enum _WEB_SOCKET_BUFFER_TYPE), __int64 (__fastcall *)(__int64 a1), int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800066b4`

## callees

- `0x180001008`
- `0x180001048`
- `0x1800044d8`
- `0x180004bac`
- `0x180005394`
- `0x180005568`

## import_xrefs

- `websocket!WebSocketCompleteAction` at `0x180004e1d`
- `websocket!WebSocketCompleteAction` at `0x180004e1d`
- `websocket!WebSocketAbortHandle` at `0x180004e03`
- `websocket!WebSocketAbortHandle` at `0x180004e03`
- `websocket!WebSocketGetAction` at `0x180004cb8`
- `websocket!WebSocketGetAction` at `0x180004cb8`
- `websocket!WebSocketReceive` at `0x180004c64`
- `websocket!WebSocketReceive` at `0x180004c64`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180004be8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180004be8`
- `iisutil!PuDbgPrint` at `0x180004c55`
- `iisutil!PuDbgPrint` at `0x180004d21`
- `iisutil!PuDbgPrint` at `0x180004df9`
- `iisutil!PuDbgPrint` at `0x180004e8c`
- `iisutil!PuDbgPrint` at `0x180004c55`
- `iisutil!PuDbgPrint` at `0x180004d21`
- `iisutil!PuDbgPrint` at `0x180004df9`
- `iisutil!PuDbgPrint` at `0x180004e8c`

## string_xrefs

- `0x180004c4e`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\wswrapper.cxx`
- `0x180004d0f`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\wswrapper.cxx`
- `0x180004df2`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\wswrapper.cxx`
- `0x180004e85`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\wswrapper.cxx`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_WRAPPER::Receive(
        WEBSOCKET_WRAPPER *this,
        union _WEB_SOCKET_BUFFER *a2,
        enum _WEB_SOCKET_BUFFER_TYPE *a3,
        void (__high *a4)(void *, int, union _WEB_SOCKET_BUFFER *, enum _WEB_SOCKET_BUFFER_TYPE),
        __int64 (__fastcall *a5)(__int64 a1),
        int *a6)
{
  int v6; // ebx
  __int64 (__fastcall **v9)(__int64); // rax
  int *v10; // r15
  __int64 (__fastcall **v11)(__int64); // rsi
  int Action; // r14d
  bool v13; // zf
  __int64 v14; // rcx
  void (*v15)(void *, int, unsigned int); // r9
  __int64 v16; // rcx
  __int64 v17; // rdx
  union _WEB_SOCKET_BUFFER *v18; // r9
  int v20; // [rsp+40h] [rbp-28h] BYREF
  void *v21[2]; // [rsp+48h] [rbp-20h] BYREF
  int v22; // [rsp+B0h] [rbp+48h] BYREF
  union _WEB_SOCKET_BUFFER *v23; // [rsp+B8h] [rbp+50h]
  unsigned int v24; // [rsp+C0h] [rbp+58h] BYREF
  int v25; // [rsp+C8h] [rbp+60h] BYREF
  int v26; // [rsp+CCh] [rbp+64h]

  v26 = HIDWORD(a4);
  v23 = a2;
  v6 = 0;
  v25 = 0;
  *(_OWORD *)v21 = 0;
  v24 = 0;
  v22 = 0;
  v20 = 0;
  *(_DWORD *)a3 = 0;
  *(_QWORD *)this = GetTickCount64();
  v9 = (__int64 (__fastcall **)(__int64))operator new(0x10u);
  v10 = a6;
  v11 = v9;
  if ( !v9 )
  {
    Action = -2147024882;
    goto LABEL_25;
  }
  v13 = (g_dwDebugFlags & 3) == 0;
  *v9 = WEBSOCKET_CONTEXT::OnWebSocketReceiveCompletion;
  v9[1] = a5;
  *v10 = 0;
  if ( !v13 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\wswrapper.cxx",
      520,
      "WEBSOCKET_WRAPPER::Receive",
      "Calling WebSocketReceive\n");
  Action = WebSocketReceive(*((_QWORD *)this + 3), 0, v11);
  if ( Action >= 0 )
  {
    while ( 1 )
    {
      v14 = *((_QWORD *)this + 3);
      v25 = 0;
      v22 = 0;
      LODWORD(a6) = 0;
      v24 = 1;
      Action = WebSocketGetAction(v14, 2, v21, &v24, &v25);
      if ( Action < 0 || !v25 )
        goto LABEL_25;
      if ( v25 != 1 )
        break;
      v6 = WEBSOCKET_IO_MANAGER::Send(
             (WEBSOCKET_WRAPPER *)((char *)this + 32),
             1,
             (union _WEB_SOCKET_BUFFER *)v21,
             v24,
             (unsigned int *)&a6,
             (void (*)(void *, int, unsigned int))WEBSOCKET_WRAPPER::ReceiveLoopCompletionCallback,
             this,
             &v20);
      if ( v6 < 0 )
      {
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\wswrapper.cxx",
            636,
            "WEBSOCKET_WRAPPER::Receive",
            "Aborting Handle %08x\n",
            *((_QWORD *)this + 3));
LABEL_20:
        WebSocketAbortHandle(*((_QWORD *)this + 3));
        goto LABEL_22;
      }
      if ( v20 )
      {
LABEL_24:
        *v10 = 1;
        goto LABEL_25;
      }
LABEL_22:
      WebSocketCompleteAction(*((_QWORD *)this + 3), *((_QWORD *)this + 1), (unsigned int)a6);
      if ( !v25 )
        goto LABEL_25;
    }
    v16 = (unsigned int)(v25 - 3);
    if ( v25 != 3 )
    {
      if ( v25 == 4 )
      {
        v17 = (unsigned int)v22;
        v18 = v23;
        *(_DWORD *)a3 = v22;
        Action = WEBSOCKET_WRAPPER::CopyReceivedData(v16, v17, v21, v18);
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\wswrapper.cxx",
          660,
          "WEBSOCKET_WRAPPER::Receive",
          "Unexpected Socket Action (%d)\n",
          v25);
      }
      goto LABEL_22;
    }
    v6 = WEBSOCKET_IO_MANAGER::Receive(
           (WEBSOCKET_WRAPPER *)((char *)this + 32),
           v21[0],
           (unsigned int)v21[1],
           v15,
           this,
           &v22);
    if ( v6 >= 0 )
      goto LABEL_24;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\wswrapper.cxx",
        583,
        "WEBSOCKET_WRAPPER::Receive",
        "Aborting Handle %08x\n",
        *((_QWORD *)this + 3));
    goto LABEL_20;
  }
LABEL_25:
  if ( v6 >= 0 )
    v6 = Action;
  if ( !*v10 || v6 < 0 )
  {
    if ( v11 )
      operator delete(v11);
    if ( v6 < 0 && (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\wswrapper.cxx",
        693,
        "WEBSOCKET_WRAPPER::Receive",
        "ERROR = %08x\n",
        v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180004bac  mov     qword ptr [rsp-40h+arg_18], r9
0x180004bb1  mov     [rsp-40h+arg_8], rdx
0x180004bb6  push    rbp
0x180004bb7  push    rbx
0x180004bb8  push    rsi
0x180004bb9  push    rdi
0x180004bba  push    r12
0x180004bbc  push    r13
0x180004bbe  push    r14
0x180004bc0  push    r15
0x180004bc2  mov     rbp, rsp
0x180004bc5  sub     rsp, 68h
0x180004bc9  xor     ebx, ebx
0x180004bcb  xorps   xmm0, xmm0
0x180004bce  mov     [rbp+arg_18], ebx
0x180004bd1  mov     r13, r8
0x180004bd4  movdqu  xmmword ptr [rbp+var_20], xmm0
0x180004bd9  mov     [rbp+arg_10], ebx
0x180004bdc  mov     rdi, rcx
0x180004bdf  mov     [rbp+arg_0], ebx
0x180004be2  mov     [rbp+var_28], ebx
0x180004be5  mov     [r8], ebx
0x180004be8  call    cs:__imp_GetTickCount64
0x180004bee  lea     ecx, [rbx+10h]; Size
0x180004bf1  mov     [rdi], rax
0x180004bf4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004bf9  mov     r15, [rbp+arg_28]
0x180004bfd  mov     rsi, rax
0x180004c00  test    rax, rax
0x180004c03  jnz     short loc_180004C10
0x180004c05  mov     r14d, 8007000Eh
0x180004c0b  jmp     loc_180004E37
0x180004c10  test    byte ptr cs:g_dwDebugFlags, 3
0x180004c17  lea     rax, ?OnWebSocketReceiveCompletion@WEBSOCKET_CONTEXT@@CAXPEAXJPEAT_WEB_SOCKET_BUFFER@@W4_WEB_SOCKET_BUFFER_TYPE@@@Z; WEBSOCKET_CONTEXT::OnWebSocketReceiveCompletion(void *,long,_WEB_SOCKET_BUFFER *,_WEB_SOCKET_BUFFER_TYPE)
0x180004c1e  mov     [rsi], rax
0x180004c21  mov     rax, [rbp+arg_20]
0x180004c25  mov     [rsi+8], rax
0x180004c29  mov     [r15], ebx
0x180004c2c  jz      short loc_180004C5B
0x180004c2e  mov     rcx, cs:g_pDebug
0x180004c35  lea     rax, aCallingWebsock; "Calling WebSocketReceive\n"
0x180004c3c  lea     r9, aWebsocketWrapp_0; "WEBSOCKET_WRAPPER::Receive"
0x180004c43  mov     [rsp+68h+var_48], rax
0x180004c48  mov     r8d, 208h
0x180004c4e  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004c55  call    cs:__imp_PuDbgPrint
0x180004c5b  mov     rcx, [rdi+18h]
0x180004c5f  mov     r8, rsi
0x180004c62  xor     edx, edx
0x180004c64  call    cs:__imp_WebSocketReceive
0x180004c6a  mov     r14d, eax
0x180004c6d  test    eax, eax
0x180004c6f  js      loc_180004E37
0x180004c75  lea     r12, [rdi+8]
0x180004c79  xor     eax, eax
0x180004c7b  mov     rcx, [rdi+18h]
0x180004c7f  lea     r9, [rbp+arg_10]
0x180004c83  mov     [rsp+68h+var_30], r12
0x180004c88  lea     r8, [rbp+var_20]
0x180004c8c  mov     [rsp+68h+var_38], rax
0x180004c91  mov     edx, 2
0x180004c96  mov     [rbp+arg_18], eax
0x180004c99  mov     [rbp+arg_0], eax
0x180004c9c  mov     dword ptr [rbp+arg_28], eax
0x180004c9f  lea     rax, [rbp+arg_0]
0x180004ca3  mov     [rsp+68h+var_40], rax; int *
0x180004ca8  lea     rax, [rbp+arg_18]
0x180004cac  mov     [rsp+68h+var_48], rax
0x180004cb1  mov     [rbp+arg_10], 1
0x180004cb8  call    cs:__imp_WebSocketGetAction
0x180004cbe  mov     r14d, eax
0x180004cc1  test    eax, eax
0x180004cc3  js      loc_180004E37
0x180004cc9  mov     edx, [rbp+arg_18]; int
0x180004ccc  mov     ecx, edx
0x180004cce  test    edx, edx
0x180004cd0  jz      loc_180004E37
0x180004cd6  sub     ecx, 1
0x180004cd9  jz      loc_180004D86
0x180004cdf  sub     ecx, 2
0x180004ce2  jz      short loc_180004D48
0x180004ce4  cmp     ecx, 1
0x180004ce7  jz      short loc_180004D2C
0x180004ce9  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180004cf0  jz      loc_180004E11
0x180004cf6  mov     rcx, cs:g_pDebug
0x180004cfd  lea     rax, aUnexpectedSock; "Unexpected Socket Action (%d)\n"
0x180004d04  mov     dword ptr [rsp+68h+var_40], edx
0x180004d08  lea     r9, aWebsocketWrapp_0; "WEBSOCKET_WRAPPER::Receive"
0x180004d0f  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004d16  mov     [rsp+68h+var_48], rax
0x180004d1b  mov     r8d, 294h
0x180004d21  call    cs:__imp_PuDbgPrint
0x180004d27  jmp     loc_180004E11
0x180004d2c  mov     edx, [rbp+arg_0]
0x180004d2f  lea     r8, [rbp+var_20]
0x180004d33  mov     r9, [rbp+arg_8]
0x180004d37  mov     [r13+0], edx
0x180004d3b  call    ?CopyReceivedData@WEBSOCKET_WRAPPER@@AEAAJW4_WEB_SOCKET_BUFFER_TYPE@@PEAT_WEB_SOCKET_BUFFER@@1@Z; WEBSOCKET_WRAPPER::CopyReceivedData(_WEB_SOCKET_BUFFER_TYPE,_WEB_SOCKET_BUFFER *,_WEB_SOCKET_BUFFER *)
0x180004d40  mov     r14d, eax
0x180004d43  jmp     loc_180004E11
0x180004d48  mov     r8d, dword ptr [rbp+var_20+8]; unsigned int
0x180004d4c  lea     rcx, [rdi+20h]; this
0x180004d50  mov     rdx, [rbp+var_20]; void *
0x180004d54  mov     [rsp+68h+var_48], rdi; void *
0x180004d59  call    ?Receive@WEBSOCKET_IO_MANAGER@@QEAAJPEAXKP6AX0JK@Z0PEAH@Z; WEBSOCKET_IO_MANAGER::Receive(void *,ulong,void (*)(void *,long,ulong),void *,int *)
0x180004d5e  mov     ebx, eax
0x180004d60  test    eax, eax
0x180004d62  jns     loc_180004E30
0x180004d68  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180004d6f  jz      loc_180004DFF
0x180004d75  mov     rcx, [rdi+18h]
0x180004d79  mov     r8d, 247h
0x180004d7f  mov     [rsp+68h+var_40], rcx
0x180004d84  jmp     short loc_180004DD8
0x180004d86  mov     r9d, [rbp+arg_10]; unsigned int
0x180004d8a  lea     rax, [rbp+var_28]
0x180004d8e  mov     [rsp+68h+var_30], rax; int *
0x180004d93  lea     rcx, [rdi+20h]; this
0x180004d97  lea     rax, ?ReceiveLoopCompletionCallback@WEBSOCKET_WRAPPER@@CAXPEAXJK@Z; WEBSOCKET_WRAPPER::ReceiveLoopCompletionCallback(void *,long,ulong)
0x180004d9e  mov     [rsp+68h+var_38], rdi; void *
0x180004da3  mov     [rsp+68h+var_40], rax; void (*)(void *, int, unsigned int)
0x180004da8  lea     r8, [rbp+var_20]; union _WEB_SOCKET_BUFFER *
0x180004dac  lea     rax, [rbp+arg_28]
0x180004db0  mov     [rsp+68h+var_48], rax; unsigned int *
0x180004db5  call    ?Send@WEBSOCKET_IO_MANAGER@@QEAAJHPEAT_WEB_SOCKET_BUFFER@@KPEAKP6AXPEAXJK@Z2PEAH@Z; WEBSOCKET_IO_MANAGER::Send(int,_WEB_SOCKET_BUFFER *,ulong,ulong *,void (*)(void *,long,ulong),void *,int *)
0x180004dba  mov     ebx, eax
0x180004dbc  test    eax, eax
0x180004dbe  jns     short loc_180004E0B
0x180004dc0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180004dc7  jz      short loc_180004DFF
0x180004dc9  mov     rax, [rdi+18h]
0x180004dcd  mov     r8d, 27Ch
0x180004dd3  mov     [rsp+68h+var_40], rax
0x180004dd8  mov     rcx, cs:g_pDebug
0x180004ddf  lea     rax, aAbortingHandle; "Aborting Handle %08x\n"
0x180004de6  lea     r9, aWebsocketWrapp_0; "WEBSOCKET_WRAPPER::Receive"
0x180004ded  mov     [rsp+68h+var_48], rax
0x180004df2  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004df9  call    cs:__imp_PuDbgPrint
0x180004dff  mov     rcx, [rdi+18h]
0x180004e03  call    cs:__imp_WebSocketAbortHandle
0x180004e09  jmp     short loc_180004E11
0x180004e0b  cmp     [rbp+var_28], 0
0x180004e0f  jnz     short loc_180004E30
0x180004e11  mov     r8d, dword ptr [rbp+arg_28]
0x180004e15  mov     rdx, [r12]
0x180004e19  mov     rcx, [rdi+18h]
0x180004e1d  call    cs:__imp_WebSocketCompleteAction
0x180004e23  xor     eax, eax
0x180004e25  cmp     [rbp+arg_18], eax
0x180004e28  jnz     loc_180004C7B
0x180004e2e  jmp     short loc_180004E37
0x180004e30  mov     dword ptr [r15], 1
0x180004e37  test    ebx, ebx
0x180004e39  cmovns  ebx, r14d
0x180004e3d  cmp     dword ptr [r15], 0
0x180004e41  jz      short loc_180004E47
0x180004e43  test    ebx, ebx
0x180004e45  jns     short loc_180004E92
0x180004e47  test    rsi, rsi
0x180004e4a  jz      short loc_180004E54
0x180004e4c  mov     rcx, rsi; Block
0x180004e4f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004e54  test    ebx, ebx
0x180004e56  jns     short loc_180004E92
0x180004e58  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180004e5f  jz      short loc_180004E92
0x180004e61  mov     rcx, cs:g_pDebug
0x180004e68  lea     rax, aError08x; "ERROR = %08x\n"
0x180004e6f  mov     dword ptr [rsp+68h+var_40], ebx
0x180004e73  lea     r9, aWebsocketWrapp_0; "WEBSOCKET_WRAPPER::Receive"
0x180004e7a  mov     r8d, 2B5h
0x180004e80  mov     [rsp+68h+var_48], rax
0x180004e85  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004e8c  call    cs:__imp_PuDbgPrint
0x180004e92  mov     eax, ebx
0x180004e94  add     rsp, 68h
0x180004e98  pop     r15
0x180004e9a  pop     r14
0x180004e9c  pop     r13
0x180004e9e  pop     r12
0x180004ea0  pop     rdi
0x180004ea1  pop     rsi
0x180004ea2  pop     rbx
0x180004ea3  pop     rbp
0x180004ea4  retn
```
