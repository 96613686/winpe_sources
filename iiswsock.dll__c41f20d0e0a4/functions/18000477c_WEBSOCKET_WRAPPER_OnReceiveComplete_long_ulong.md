# WEBSOCKET_WRAPPER::OnReceiveComplete(long,ulong)

- ea: `0x18000477c`
- end: `0x180004ace`
- name: `?OnReceiveComplete@WEBSOCKET_WRAPPER@@AEAAJJK@Z`
- size: `850`
- prototype: `__int64 __fastcall(WEBSOCKET_WRAPPER *__hidden this, int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004eb0`

## callees

- `0x180001048`
- `0x1800044d8`
- `0x18000477c`
- `0x180004ad4`
- `0x180005394`
- `0x180005568`
- `0x180009010`

## import_xrefs

- `websocket!WebSocketCompleteAction` at `0x180004819`
- `websocket!WebSocketCompleteAction` at `0x1800048e1`
- `websocket!WebSocketCompleteAction` at `0x1800049fe`
- `websocket!WebSocketCompleteAction` at `0x180004819`
- `websocket!WebSocketCompleteAction` at `0x1800048e1`
- `websocket!WebSocketCompleteAction` at `0x1800049fe`
- `websocket!WebSocketAbortHandle` at `0x180004804`
- `websocket!WebSocketAbortHandle` at `0x18000494f`
- `websocket!WebSocketAbortHandle` at `0x1800049e1`
- `websocket!WebSocketAbortHandle` at `0x180004804`
- `websocket!WebSocketAbortHandle` at `0x18000494f`
- `websocket!WebSocketAbortHandle` at `0x1800049e1`
- `websocket!WebSocketGetAction` at `0x180004886`
- `websocket!WebSocketGetAction` at `0x180004886`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800047f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800047f3`
- `iisutil!PuDbgPrint` at `0x1800047ed`
- `iisutil!PuDbgPrint` at `0x180004945`
- `iisutil!PuDbgPrint` at `0x1800049d7`
- `iisutil!PuDbgPrint` at `0x180004ab5`
- `iisutil!PuDbgPrint` at `0x1800047ed`
- `iisutil!PuDbgPrint` at `0x180004945`
- `iisutil!PuDbgPrint` at `0x1800049d7`
- `iisutil!PuDbgPrint` at `0x180004ab5`

## string_xrefs

- `0x1800047e6`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\wswrapper.cxx`
- `0x180004933`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\wswrapper.cxx`
- `0x1800049b9`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\wswrapper.cxx`
- `0x180004aae`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\wswrapper.cxx`
- `0x1800047d4`: `WEBSOCKET_WRAPPER::OnReceiveComplete`
- `0x180004925`: `WEBSOCKET_WRAPPER::OnReceiveComplete`
- `0x1800049ab`: `WEBSOCKET_WRAPPER::OnReceiveComplete`
- `0x180004a9c`: `WEBSOCKET_WRAPPER::OnReceiveComplete`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_WRAPPER::OnReceiveComplete(WEBSOCKET_WRAPPER *this, int a2, unsigned int a3)
{
  int v6; // esi
  unsigned int v7; // r13d
  __int64 v8; // rcx
  unsigned int v9; // r14d
  int v10; // edx
  void (*v11)(void *, int, unsigned int); // r9
  int Action; // r15d
  int v13; // r14d
  unsigned int v14; // r9d
  int v16; // [rsp+40h] [rbp-38h] BYREF
  int v17; // [rsp+44h] [rbp-34h] BYREF
  void *Block; // [rsp+48h] [rbp-30h]
  void *v19; // [rsp+50h] [rbp-28h] BYREF
  unsigned int v20; // [rsp+58h] [rbp-20h]
  __int128 v21; // [rsp+60h] [rbp-18h] BYREF
  int v22; // [rsp+C0h] [rbp+48h] BYREF
  unsigned int v23; // [rsp+D0h] [rbp+58h] BYREF
  unsigned int v24; // [rsp+D8h] [rbp+60h] BYREF

  v22 = 0;
  v24 = 0;
  v6 = 0;
  v16 = 0;
  Block = 0;
  v7 = 0;
  v21 = 0;
  v17 = 0;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\wswrapper.cxx",
      723,
      "WEBSOCKET_WRAPPER::OnReceiveComplete",
      "Calling WebSocketReceive\n");
  *(_QWORD *)this = GetTickCount64();
  if ( a2 < 0 )
    WebSocketAbortHandle(*((_QWORD *)this + 3));
  WebSocketCompleteAction(*((_QWORD *)this + 3), *((_QWORD *)this + 1), a3);
  if ( *((_DWORD *)this + 36) )
  {
    *((_DWORD *)this + 36) = 0;
    WEBSOCKET_WRAPPER::OnSendComplete(this, 0, a3, 0);
  }
  do
  {
    v8 = *((_QWORD *)this + 3);
    v22 = 0;
    v24 = 1;
    v9 = 0;
    v16 = 0;
    v23 = 0;
    Action = WebSocketGetAction(v8, 2, &v19, &v24, &v22);
    if ( Action < 0 || !v22 )
      break;
    switch ( v22 )
    {
      case 1:
        v14 = v24;
        *((_DWORD *)this + 36) = 1;
        v6 = WEBSOCKET_IO_MANAGER::Send(
               (WEBSOCKET_WRAPPER *)((char *)this + 32),
               v10,
               (union _WEB_SOCKET_BUFFER *)&v19,
               v14,
               &v23,
               (void (*)(void *, int, unsigned int))WEBSOCKET_WRAPPER::ReceiveLoopCompletionCallback,
               this,
               &v17);
        if ( v6 >= 0 )
        {
          if ( v17 )
            goto LABEL_26;
        }
        else
        {
          if ( (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\wswrapper.cxx",
              854,
              "WEBSOCKET_WRAPPER::OnReceiveComplete",
              "Aborting Handle %08x\n",
              *((_QWORD *)this + 3));
          WebSocketAbortHandle(*((_QWORD *)this + 3));
        }
        v9 = v23;
        break;
      case 3:
        v6 = WEBSOCKET_IO_MANAGER::Receive((WEBSOCKET_WRAPPER *)((char *)this + 32), v19, v20, v11, this, &v16);
        if ( v6 >= 0 )
          goto LABEL_26;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\wswrapper.cxx",
            792,
            "WEBSOCKET_WRAPPER::OnReceiveComplete",
            "Aborting Handle %08x\n",
            *((_QWORD *)this + 3));
        WebSocketAbortHandle(*((_QWORD *)this + 3));
        break;
      case 4:
        v7 = v16;
        Action = WEBSOCKET_WRAPPER::CopyReceivedData((unsigned int)(v22 - 3), v16, (__int64)&v19, (__int64)&v21);
        v13 = 1;
        WebSocketCompleteAction(*((_QWORD *)this + 3), *((_QWORD *)this + 1), 0);
        goto LABEL_27;
    }
    WebSocketCompleteAction(*((_QWORD *)this + 3), *((_QWORD *)this + 1), v9);
    if ( *((_DWORD *)this + 36) )
    {
      *((_DWORD *)this + 36) = 0;
      WEBSOCKET_WRAPPER::OnSendComplete(this, v6, v9, 0);
    }
  }
  while ( v22 );
LABEL_26:
  v13 = 0;
LABEL_27:
  if ( a2 >= 0 )
  {
    if ( v6 >= 0 )
    {
      a2 = Action;
      if ( Action >= 0 && !v13 )
        return (unsigned int)a2;
    }
    else
    {
      a2 = v6;
    }
  }
  if ( Block )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD, __int128 *, _QWORD))Block)(
      *((_QWORD *)Block + 1),
      (unsigned int)a2,
      &v21,
      v7);
    operator delete(Block);
    Block = 0;
  }
  if ( a2 < 0 && (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\wswrapper.cxx",
      934,
      "WEBSOCKET_WRAPPER::OnReceiveComplete",
      "ERROR = %08x\n",
      a2);
  return (unsigned int)a2;
}

```

## disassembly

```asm
0x18000477c  push    rbp
0x18000477e  push    rbx
0x18000477f  push    rsi
0x180004780  push    rdi
0x180004781  push    r12
0x180004783  push    r13
0x180004785  push    r14
0x180004787  push    r15
0x180004789  mov     rbp, rsp
0x18000478c  sub     rsp, 78h
0x180004790  xor     r15d, r15d
0x180004793  xorps   xmm0, xmm0
0x180004796  test    byte ptr cs:g_dwDebugFlags, 3
0x18000479d  mov     r14d, r8d
0x1800047a0  mov     edi, edx
0x1800047a2  mov     [rbp+arg_0], r15d
0x1800047a6  mov     rbx, rcx
0x1800047a9  mov     [rbp+arg_18], r15d
0x1800047ad  mov     esi, r15d
0x1800047b0  mov     [rbp+var_38], r15d
0x1800047b4  mov     [rbp+Block], r15
0x1800047b8  mov     r13d, r15d
0x1800047bb  movdqu  [rbp+var_18], xmm0
0x1800047c0  mov     [rbp+var_34], r15d
0x1800047c4  jz      short loc_1800047F3
0x1800047c6  mov     rcx, cs:g_pDebug
0x1800047cd  lea     rax, aCallingWebsock; "Calling WebSocketReceive\n"
0x1800047d4  lea     r9, aWebsocketWrapp; "WEBSOCKET_WRAPPER::OnReceiveComplete"
0x1800047db  mov     [rsp+78h+var_58], rax
0x1800047e0  mov     r8d, 2D3h
0x1800047e6  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800047ed  call    cs:__imp_PuDbgPrint
0x1800047f3  call    cs:__imp_GetTickCount64
0x1800047f9  mov     [rbx], rax
0x1800047fc  test    edi, edi
0x1800047fe  jns     short loc_18000480A
0x180004800  mov     rcx, [rbx+18h]
0x180004804  call    cs:__imp_WebSocketAbortHandle
0x18000480a  mov     rcx, [rbx+18h]
0x18000480e  lea     r12, [rbx+8]
0x180004812  mov     rdx, [r12]
0x180004816  mov     r8d, r14d
0x180004819  call    cs:__imp_WebSocketCompleteAction
0x18000481f  cmp     [rbx+90h], r15d
0x180004826  jz      short loc_18000483F
0x180004828  xor     r9d, r9d; int
0x18000482b  mov     [rbx+90h], r15d
0x180004832  mov     r8d, r14d; unsigned int
0x180004835  xor     edx, edx; int
0x180004837  mov     rcx, rbx; this
0x18000483a  call    ?OnSendComplete@WEBSOCKET_WRAPPER@@AEAAJJKH@Z; WEBSOCKET_WRAPPER::OnSendComplete(long,ulong,int)
0x18000483f  mov     rcx, [rbx+18h]
0x180004843  lea     rax, [rbp+Block]
0x180004847  mov     [rsp+78h+var_40], r12
0x18000484c  lea     r9, [rbp+arg_18]
0x180004850  mov     [rsp+78h+var_48], rax
0x180004855  lea     r8, [rbp+var_28]
0x180004859  lea     rax, [rbp+var_38]
0x18000485d  mov     [rbp+arg_0], r15d
0x180004861  mov     [rsp+78h+var_50], rax; int *
0x180004866  mov     edx, 2
0x18000486b  lea     rax, [rbp+arg_0]
0x18000486f  mov     [rbp+arg_18], 1
0x180004876  mov     [rsp+78h+var_58], rax
0x18000487b  mov     r14d, r15d
0x18000487e  mov     [rbp+var_38], r15d
0x180004882  mov     [rbp+arg_10], r15d
0x180004886  call    cs:__imp_WebSocketGetAction
0x18000488c  mov     r15d, eax
0x18000488f  test    eax, eax
0x180004891  js      loc_180004A32
0x180004897  mov     ecx, [rbp+arg_0]
0x18000489a  test    ecx, ecx
0x18000489c  jz      loc_180004A32
0x1800048a2  sub     ecx, 1
0x1800048a5  jz      loc_18000495A
0x1800048ab  sub     ecx, 2
0x1800048ae  jz      short loc_1800048EC
0x1800048b0  cmp     ecx, 1
0x1800048b3  jnz     loc_1800049F3
0x1800048b9  mov     r13d, [rbp+var_38]
0x1800048bd  lea     r9, [rbp+var_18]
0x1800048c1  mov     edx, r13d
0x1800048c4  lea     r8, [rbp+var_28]
0x1800048c8  call    ?CopyReceivedData@WEBSOCKET_WRAPPER@@AEAAJW4_WEB_SOCKET_BUFFER_TYPE@@PEAT_WEB_SOCKET_BUFFER@@1@Z; WEBSOCKET_WRAPPER::CopyReceivedData(_WEB_SOCKET_BUFFER_TYPE,_WEB_SOCKET_BUFFER *,_WEB_SOCKET_BUFFER *)
0x1800048cd  mov     rdx, [r12]
0x1800048d1  xor     r8d, r8d
0x1800048d4  mov     rcx, [rbx+18h]
0x1800048d8  mov     r15d, eax
0x1800048db  mov     r14d, 1
0x1800048e1  call    cs:__imp_WebSocketCompleteAction
0x1800048e7  jmp     loc_180004A35
0x1800048ec  mov     r8d, [rbp+var_20]; unsigned int
0x1800048f0  lea     rcx, [rbx+20h]; this
0x1800048f4  mov     rdx, [rbp+var_28]; void *
0x1800048f8  mov     [rsp+78h+var_58], rbx; void *
0x1800048fd  call    ?Receive@WEBSOCKET_IO_MANAGER@@QEAAJPEAXKP6AX0JK@Z0PEAH@Z; WEBSOCKET_IO_MANAGER::Receive(void *,ulong,void (*)(void *,long,ulong),void *,int *)
0x180004902  mov     esi, eax
0x180004904  test    eax, eax
0x180004906  jns     loc_180004A32
0x18000490c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180004913  jz      short loc_18000494B
0x180004915  mov     rcx, [rbx+18h]
0x180004919  lea     rax, aAbortingHandle; "Aborting Handle %08x\n"
0x180004920  mov     [rsp+78h+var_50], rcx
0x180004925  lea     r9, aWebsocketWrapp; "WEBSOCKET_WRAPPER::OnReceiveComplete"
0x18000492c  mov     rcx, cs:g_pDebug
0x180004933  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000493a  mov     r8d, 318h
0x180004940  mov     [rsp+78h+var_58], rax
0x180004945  call    cs:__imp_PuDbgPrint
0x18000494b  mov     rcx, [rbx+18h]
0x18000494f  call    cs:__imp_WebSocketAbortHandle
0x180004955  jmp     loc_1800049F3
0x18000495a  mov     r9d, [rbp+arg_18]; unsigned int
0x18000495e  lea     rax, [rbp+var_34]
0x180004962  mov     [rsp+78h+var_40], rax; int *
0x180004967  lea     rcx, [rbx+20h]; this
0x18000496b  lea     rax, ?ReceiveLoopCompletionCallback@WEBSOCKET_WRAPPER@@CAXPEAXJK@Z; WEBSOCKET_WRAPPER::ReceiveLoopCompletionCallback(void *,long,ulong)
0x180004972  mov     [rsp+78h+var_48], rbx; void *
0x180004977  mov     [rsp+78h+var_50], rax; void (*)(void *, int, unsigned int)
0x18000497c  lea     r8, [rbp+var_28]; union _WEB_SOCKET_BUFFER *
0x180004980  lea     rax, [rbp+arg_10]
0x180004984  mov     dword ptr [rbx+90h], 1
0x18000498e  mov     [rsp+78h+var_58], rax; unsigned int *
0x180004993  call    ?Send@WEBSOCKET_IO_MANAGER@@QEAAJHPEAT_WEB_SOCKET_BUFFER@@KPEAKP6AXPEAXJK@Z2PEAH@Z; WEBSOCKET_IO_MANAGER::Send(int,_WEB_SOCKET_BUFFER *,ulong,ulong *,void (*)(void *,long,ulong),void *,int *)
0x180004998  mov     esi, eax
0x18000499a  test    eax, eax
0x18000499c  jns     short loc_1800049E9
0x18000499e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800049a5  jz      short loc_1800049DD
0x1800049a7  mov     rax, [rbx+18h]
0x1800049ab  lea     r9, aWebsocketWrapp; "WEBSOCKET_WRAPPER::OnReceiveComplete"
0x1800049b2  mov     rcx, cs:g_pDebug
0x1800049b9  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800049c0  mov     [rsp+78h+var_50], rax
0x1800049c5  mov     r8d, 356h
0x1800049cb  lea     rax, aAbortingHandle; "Aborting Handle %08x\n"
0x1800049d2  mov     [rsp+78h+var_58], rax
0x1800049d7  call    cs:__imp_PuDbgPrint
0x1800049dd  mov     rcx, [rbx+18h]
0x1800049e1  call    cs:__imp_WebSocketAbortHandle
0x1800049e7  jmp     short loc_1800049EF
0x1800049e9  cmp     [rbp+var_34], r13d
0x1800049ed  jnz     short loc_180004A32
0x1800049ef  mov     r14d, [rbp+arg_10]
0x1800049f3  mov     rdx, [rbx+8]
0x1800049f7  mov     r8d, r14d
0x1800049fa  mov     rcx, [rbx+18h]
0x1800049fe  call    cs:__imp_WebSocketCompleteAction
0x180004a04  cmp     [rbx+90h], r13d
0x180004a0b  jz      short loc_180004A24
0x180004a0d  xor     r9d, r9d; int
0x180004a10  mov     [rbx+90h], r13d
0x180004a17  mov     r8d, r14d; unsigned int
0x180004a1a  mov     edx, esi; int
0x180004a1c  mov     rcx, rbx; this
0x180004a1f  call    ?OnSendComplete@WEBSOCKET_WRAPPER@@AEAAJJKH@Z; WEBSOCKET_WRAPPER::OnSendComplete(long,ulong,int)
0x180004a24  cmp     [rbp+arg_0], r13d
0x180004a28  jz      short loc_180004A32
0x180004a2a  xor     r15d, r15d
0x180004a2d  jmp     loc_18000483F
0x180004a32  mov     r14d, r13d
0x180004a35  test    edi, edi
0x180004a37  js      short loc_180004A4E
0x180004a39  test    esi, esi
0x180004a3b  jns     short loc_180004A41
0x180004a3d  mov     edi, esi
0x180004a3f  jmp     short loc_180004A4E
0x180004a41  mov     edi, r15d
0x180004a44  test    r15d, r15d
0x180004a47  js      short loc_180004A4E
0x180004a49  test    r14d, r14d
0x180004a4c  jz      short loc_180004ABB
0x180004a4e  mov     rax, [rbp+Block]
0x180004a52  test    rax, rax
0x180004a55  jz      short loc_180004A7D
0x180004a57  mov     rcx, [rax+8]
0x180004a5b  lea     r8, [rbp+var_18]
0x180004a5f  mov     rax, [rax]
0x180004a62  mov     r9d, r13d
0x180004a65  mov     edx, edi
0x180004a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a6c  mov     rcx, [rbp+Block]; Block
0x180004a70  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004a75  mov     [rbp+Block], 0
0x180004a7d  test    edi, edi
0x180004a7f  jns     short loc_180004ABB
0x180004a81  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180004a88  jz      short loc_180004ABB
0x180004a8a  mov     rcx, cs:g_pDebug
0x180004a91  lea     rax, aError08x; "ERROR = %08x\n"
0x180004a98  mov     dword ptr [rsp+78h+var_50], edi
0x180004a9c  lea     r9, aWebsocketWrapp; "WEBSOCKET_WRAPPER::OnReceiveComplete"
0x180004aa3  mov     r8d, 3A6h
0x180004aa9  mov     [rsp+78h+var_58], rax
0x180004aae  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004ab5  call    cs:__imp_PuDbgPrint
0x180004abb  mov     eax, edi
0x180004abd  add     rsp, 78h
0x180004ac1  pop     r15
0x180004ac3  pop     r14
0x180004ac5  pop     r13
0x180004ac7  pop     r12
0x180004ac9  pop     rdi
0x180004aca  pop     rsi
0x180004acb  pop     rbx
0x180004acc  pop     rbp
0x180004acd  retn
```
