# WEBSOCKET_CONTEXT::SendWebSocketHandshake(ISendResponseProvider *)

- ea: `0x180006c98`
- end: `0x180007311`
- name: `?SendWebSocketHandshake@WEBSOCKET_CONTEXT@@QEAAJPEAVISendResponseProvider@@@Z`
- size: `1657`
- prototype: `__int64 __fastcall(WEBSOCKET_CONTEXT *__hidden this, struct ISendResponseProvider *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008080`

## callees

- `0x180001008`
- `0x180001ce0`
- `0x180002168`
- `0x180002e44`
- `0x180006c98`
- `0x1800085b6`
- `0x1800085c2`
- `0x180008600`
- `0x180009010`

## import_xrefs

- `msvcrt!_stricmp` at `0x180007005`
- `msvcrt!_stricmp` at `0x180007005`
- `websocket!WebSocketBeginServerHandshake` at `0x180006eac`
- `websocket!WebSocketBeginServerHandshake` at `0x180006eac`
- `websocket!WebSocketCreateServerHandle` at `0x180006dea`
- `websocket!WebSocketCreateServerHandle` at `0x180006dea`
- `websocket!WebSocketEndServerHandshake` at `0x1800071cd`
- `websocket!WebSocketEndServerHandshake` at `0x1800071cd`
- `iisutil!IISInitializeCriticalSection` at `0x180007276`
- `iisutil!IISInitializeCriticalSection` at `0x180007276`
- `iisutil!PuDbgPrint` at `0x180006ef1`
- `iisutil!PuDbgPrint` at `0x180006f25`
- `iisutil!PuDbgPrint` at `0x18000720d`
- `iisutil!PuDbgPrint` at `0x180006ef1`
- `iisutil!PuDbgPrint` at `0x180006f25`
- `iisutil!PuDbgPrint` at `0x18000720d`

## string_xrefs

- `0x180006ee5`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\wswrapper.cxx`
- `0x180007206`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\wswrapper.cxx`
- `0x180006e61`: `Sec-WebSocket-Protocol`
- `0x180006f13`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\websocketcontext.cxx`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_CONTEXT::SendWebSocketHandshake(WEBSOCKET_CONTEXT *this, struct ISendResponseProvider *a2)
{
  unsigned int v3; // esi
  struct IHttpContext *v4; // rdx
  TRACE_HELPER *v5; // rcx
  __int64 v6; // r12
  __int64 v7; // r15
  int ServerHandle; // edi
  TRACE_HELPER *v9; // rcx
  __int64 v11; // rax
  __int64 i; // rbx
  __int64 v13; // rax
  __int64 v14; // rdx
  int v15; // ecx
  int v16; // eax
  __int64 v17; // rax
  _QWORD *v18; // r13
  __int64 v19; // rcx
  __int64 v20; // rdx
  const char *v21; // r8
  __int64 v22; // r9
  unsigned int v23; // r12d
  __int64 v24; // rcx
  __int64 v25; // rsi
  bool v26; // zf
  __int64 v27; // rax
  __int64 v28; // rbx
  __int64 v29; // r13
  __int64 v30; // rax
  __int64 v31; // rcx
  size_t v32; // rbx
  char *v33; // rcx
  __int64 v34; // rax
  struct ISendResponseProvider *v35; // rdi
  __int64 v36; // rbx
  int v37; // eax
  int v38; // eax
  _DWORD *v39; // rsi
  int v40; // edx
  void (__fastcall ***v41)(_QWORD, __int64, __int64); // rax
  void (__fastcall ***v42)(_QWORD, __int64, __int64); // rax
  TRACE_HELPER *v43; // rcx
  int v44; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v45; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v46; // [rsp+48h] [rbp-B8h] BYREF
  void *v47; // [rsp+50h] [rbp-B0h] BYREF
  struct IAppHostConfigException *v48; // [rsp+58h] [rbp-A8h] BYREF
  void *v49; // [rsp+60h] [rbp-A0h]
  void *v50; // [rsp+68h] [rbp-98h]
  __int64 v51; // [rsp+70h] [rbp-90h]
  struct ISendResponseProvider *v52; // [rsp+78h] [rbp-88h]
  _QWORD v53[4]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v54; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v55[46]; // [rsp+A8h] [rbp-58h] BYREF

  v52 = a2;
  v3 = 0;
  v54 = 0;
  memset_0(v55, 0, sizeof(v55));
  v4 = (struct IHttpContext *)*((_QWORD *)this + 43);
  v46 = 0;
  v45 = 0;
  v48 = 0;
  TRACE_HELPER::RaiseTraceEvent(v5, v4, 1u);
  v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 43) + 24LL))(*((_QWORD *)this + 43));
  v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 43) + 32LL))(*((_QWORD *)this + 43));
  ServerHandle = WEBSOCKET_CONFIG::ReadConfig(
                   *((struct IHttpContext **)this + 43),
                   (struct WEBSOCKET_CONFIG **)this + 33,
                   &v48);
  if ( ServerHandle < 0 )
  {
    (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, struct IAppHostConfigException *, _DWORD))(*(_QWORD *)v7 + 24LL))(
      v7,
      500,
      "Internal Server Error",
      19,
      ServerHandle,
      v48,
      0);
    goto LABEL_3;
  }
  v11 = *((_QWORD *)this + 33);
  v53[0] = 0;
  v53[2] = 4;
  v44 = *(_DWORD *)(v11 + 20);
  v53[1] = &v44;
  ServerHandle = WebSocketCreateServerHandle(v53, 1, (char *)this + 136);
  if ( ServerHandle < 0 )
    goto LABEL_3;
  for ( i = 0; i != 6; ++i )
  {
    LOWORD(v44) = 0;
    v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v6 + 24LL))(
            v6,
            *(&WEBSOCKET_CONTEXT::sm_rgWebSocketHeaders + 2 * i),
            &v44);
    if ( v13 )
    {
      v14 = 8LL * v3++;
      *(_QWORD *)&v55[v14 - 2] = *(&WEBSOCKET_CONTEXT::sm_rgWebSocketHeaders + 2 * i);
      v15 = *((unsigned __int16 *)&WEBSOCKET_CONTEXT::sm_rgWebSocketHeaders + 8 * i + 4);
      *(_QWORD *)&v55[v14 + 2] = v13;
      v16 = (unsigned __int16)v44;
      v55[v14] = v15;
      v55[v14 + 4] = v16;
    }
  }
  v17 = (*(__int64 (__fastcall **)(__int64, const char *, _QWORD))(*(_QWORD *)v7 + 72LL))(
          v7,
          "Sec-WebSocket-Protocol",
          0);
  v18 = (_QWORD *)((char *)this + 136);
  ServerHandle = WebSocketBeginServerHandshake(*((_QWORD *)this + 17), v17, 0, 0, &v54, v3, &v46, &v45);
  if ( ServerHandle < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\wswrapper.cxx",
        99,
        "WEBSOCKET_WRAPPER::BeginServerHandshake",
        "ERROR = %08x\n",
        ServerHandle);
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\websocketcontext.cxx",
          733,
          "WEBSOCKET_CONTEXT::SendWebSocketHandshake",
          "ERROR = %08x\n",
          ServerHandle);
    }
    if ( ServerHandle == -2089418747 )
    {
      v19 = *((_QWORD *)this + 43);
      v47 = 0;
      v44 = 0;
      if ( (*(int (__fastcall **)(__int64, const char *, void **, int *))(*(_QWORD *)v19 + 120LL))(
             v19,
             "WEBSOCKET_VERSION",
             &v47,
             &v44) >= 0 )
        (*(void (__fastcall **)(__int64, const char *, void *, _QWORD, int))(*(_QWORD *)v7 + 40LL))(
          v7,
          "Sec-WebSocket-Version",
          v47,
          (unsigned __int16)v44,
          1);
    }
    v20 = 400;
    v21 = "Bad Request";
    v22 = 11;
LABEL_18:
    (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, _QWORD, _DWORD))(*(_QWORD *)v7 + 24LL))(
      v7,
      v20,
      v21,
      v22,
      ServerHandle,
      0,
      0);
    goto LABEL_3;
  }
  v23 = 0;
  if ( v45 )
  {
    while ( 1 )
    {
      v24 = v46;
      v25 = 32LL * v23;
      if ( *(_DWORD *)(v25 + v46 + 24) > 0xFFFFu )
      {
        *(_BYTE *)(*(_QWORD *)(v25 + v46 + 16) + 65534LL) = 0;
        *(_DWORD *)(v25 + v46 + 24) = 0xFFFF;
        v24 = v46;
      }
      v26 = _stricmp(*(const char **)(v25 + v24), "connection") == 0;
      v27 = *(_QWORD *)v7;
      if ( v26 )
      {
        v28 = *((_QWORD *)this + 43);
        v29 = v46;
        v30 = (*(__int64 (__fastcall **)(__int64))(v27 + 8))(v7);
        v31 = *(_QWORD *)v7;
        v51 = v30;
        LOWORD(v44) = *(_WORD *)(v30 + 24);
        ServerHandle = (*(__int64 (__fastcall **)(__int64, const char *))(v31 + 56))(v7, "Connection");
        if ( ServerHandle >= 0 )
        {
          v47 = (void *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v28 + 144LL))(
                          v28,
                          24 * ((unsigned int)(unsigned __int16)v44 + 1));
          if ( v47
            && (v49 = (void *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v28 + 144LL))(
                                v28,
                                *(unsigned int *)(v25 + v29 + 8))) != 0
            && (v50 = (void *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v28 + 144LL))(
                                v28,
                                *(unsigned int *)(v25 + v29 + 24))) != 0 )
          {
            v32 = 24LL * (unsigned __int16)v44;
            memcpy_0(v47, *(const void **)(v51 + 32), v32);
            memcpy_0(v49, *(const void **)(v25 + v29), *(unsigned int *)(v25 + v29 + 8));
            memcpy_0(v50, *(const void **)(v25 + v29 + 16), *(unsigned int *)(v25 + v29 + 24));
            v33 = (char *)v47;
            *(_QWORD *)((char *)v47 + v32 + 8) = v49;
            *(_WORD *)&v33[v32] = *(_WORD *)(v25 + v29 + 8);
            *(_QWORD *)&v33[v32 + 16] = v50;
            *(_WORD *)&v33[v32 + 2] = *(_WORD *)(v25 + v29 + 24);
            v34 = v51;
            ++*(_WORD *)(v51 + 24);
            *(_QWORD *)(v34 + 32) = v33;
          }
          else
          {
            ServerHandle = -2147024882;
          }
        }
      }
      else
      {
        ServerHandle = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, int))(v27 + 40))(
                         v7,
                         *(_QWORD *)(v25 + v46),
                         *(_QWORD *)(v25 + v46 + 16),
                         *(unsigned __int16 *)(v25 + v46 + 24),
                         1);
      }
      if ( ServerHandle < 0 )
        break;
      if ( ++v23 >= v45 )
      {
        v18 = (_QWORD *)((char *)this + 136);
        goto LABEL_34;
      }
    }
    v22 = 0;
    v21 = "Internal Server Error";
    v20 = 500;
    goto LABEL_18;
  }
LABEL_34:
  v35 = v52;
  v36 = *(_QWORD *)v52;
  v37 = (*(__int64 (__fastcall **)(struct ISendResponseProvider *))(*(_QWORD *)v52 + 16LL))(v52);
  (*(void (__fastcall **)(struct ISendResponseProvider *, _QWORD))(v36 + 24))(v35, v37 | 0x40u);
  v38 = WebSocketEndServerHandshake(*v18);
  ServerHandle = v38;
  if ( v38 >= 0 )
  {
    *((_DWORD *)this + 88) = 1;
    v39 = operator new(0x58u);
    if ( v39 )
    {
      v40 = *(_DWORD *)(*((_QWORD *)this + 33) + 16LL);
      *(_QWORD *)v39 = &RECEIVE_QUEUE::`vftable';
      v39[2] = v40;
      *((_QWORD *)v39 + 9) = 0;
      *((_QWORD *)v39 + 10) = 0;
      IISInitializeCriticalSection(v39 + 4);
      *((_QWORD *)v39 + 8) = v39 + 14;
      *((_QWORD *)v39 + 7) = v39 + 14;
    }
    else
    {
      v39 = 0;
    }
    *((_QWORD *)this + 34) = v39;
    if ( v39 )
    {
      v41 = (void (__fastcall ***)(_QWORD, __int64, __int64))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 96LL))(g_pGlobalInfo);
      (**v41)(v41, 29, 1);
      v42 = (void (__fastcall ***)(_QWORD, __int64, __int64))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 96LL))(g_pGlobalInfo);
      (**v42)(v42, 32, 1);
      TRACE_HELPER::RaiseTraceEvent(v43, *((struct IHttpContext **)this + 43), 2u);
      return (unsigned int)ServerHandle;
    }
    ServerHandle = -2147024882;
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\wswrapper.cxx",
      125,
      "WEBSOCKET_WRAPPER::EndServerHandshake",
      "ERROR = %08x\n",
      v38);
  }
LABEL_3:
  TRACE_HELPER::RaiseTraceEventError(v9, *((struct IHttpContext **)this + 43), 3u, ServerHandle);
  return (unsigned int)ServerHandle;
}

```

## disassembly

```asm
0x180006c98  mov     [rsp-8+arg_10], rbx
0x180006c9d  push    rbp
0x180006c9e  push    rsi
0x180006c9f  push    rdi
0x180006ca0  push    r12
0x180006ca2  push    r13
0x180006ca4  push    r14
0x180006ca6  push    r15
0x180006ca8  lea     rbp, [rsp-70h]
0x180006cad  sub     rsp, 170h
0x180006cb4  mov     rax, cs:__security_cookie
0x180006cbb  xor     rax, rsp
0x180006cbe  mov     [rbp+0A0h+var_40], rax
0x180006cc2  mov     [rsp+1A0h+var_128], rdx
0x180006cc7  mov     r14, rcx
0x180006cca  xor     esi, esi
0x180006ccc  lea     rcx, [rbp+0A0h+var_F8]; void *
0x180006cd0  xor     edx, edx; Val
0x180006cd2  mov     [rbp+0A0h+var_100], rsi
0x180006cd6  mov     r8d, 0B8h; Size
0x180006cdc  call    memset_0
0x180006ce1  mov     rdx, [r14+158h]; struct IHttpContext *
0x180006ce8  lea     r8d, [rsi+1]; unsigned int
0x180006cec  mov     [rsp+1A0h+var_158], rsi
0x180006cf1  mov     [rsp+1A0h+var_15C], esi
0x180006cf5  mov     [rsp+1A0h+var_148], rsi
0x180006cfa  call    ?RaiseTraceEvent@TRACE_HELPER@@QEAAXPEAVIHttpContext@@K@Z; TRACE_HELPER::RaiseTraceEvent(IHttpContext *,ulong)
0x180006cff  mov     rcx, [r14+158h]
0x180006d06  mov     rax, [rcx]
0x180006d09  mov     rax, [rax+18h]
0x180006d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d12  mov     rcx, [r14+158h]
0x180006d19  mov     r12, rax
0x180006d1c  mov     rdx, [rcx]
0x180006d1f  mov     rax, [rdx+20h]
0x180006d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d28  mov     rcx, [r14+158h]; struct IHttpContext *
0x180006d2f  lea     rbx, [r14+108h]
0x180006d36  mov     rdx, rbx; struct WEBSOCKET_CONFIG **
0x180006d39  lea     r8, [rsp+1A0h+var_148]; struct IAppHostConfigException **
0x180006d3e  mov     r15, rax
0x180006d41  call    ?ReadConfig@WEBSOCKET_CONFIG@@SAJPEAVIHttpContext@@PEAPEAV1@PEAPEAUIAppHostConfigException@@@Z; WEBSOCKET_CONFIG::ReadConfig(IHttpContext *,WEBSOCKET_CONFIG * *,IAppHostConfigException * *)
0x180006d46  mov     edi, eax
0x180006d48  test    eax, eax
0x180006d4a  jns     short loc_180006DBB
0x180006d4c  mov     rcx, [r15]
0x180006d4f  lea     r9d, [rsi+13h]
0x180006d53  mov     dword ptr [rsp+1A0h+var_170], esi
0x180006d57  lea     r8, aInternalServer; "Internal Server Error"
0x180006d5e  mov     edx, 1F4h
0x180006d63  mov     rax, [rcx+18h]
0x180006d67  mov     rcx, [rsp+1A0h+var_148]
0x180006d6c  mov     [rsp+1A0h+var_178], rcx
0x180006d71  mov     rcx, r15
0x180006d74  mov     dword ptr [rsp+1A0h+var_180], edi
0x180006d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d7d  mov     rdx, [r14+158h]; struct IHttpContext *
0x180006d84  mov     r9d, edi; int
0x180006d87  mov     r8d, 3; unsigned int
0x180006d8d  call    ?RaiseTraceEventError@TRACE_HELPER@@QEAAXPEAVIHttpContext@@KJ@Z; TRACE_HELPER::RaiseTraceEventError(IHttpContext *,ulong,long)
0x180006d92  mov     eax, edi
0x180006d94  mov     rcx, [rbp+0A0h+var_40]
0x180006d98  xor     rcx, rsp; StackCookie
0x180006d9b  call    __security_check_cookie
0x180006da0  mov     rbx, [rsp+1A0h+arg_10]
0x180006da8  add     rsp, 170h
0x180006daf  pop     r15
0x180006db1  pop     r14
0x180006db3  pop     r13
0x180006db5  pop     r12
0x180006db7  pop     rdi
0x180006db8  pop     rsi
0x180006db9  pop     rbp
0x180006dba  retn
0x180006dbb  mov     rax, [rbx]
0x180006dbe  lea     r8, [r14+88h]
0x180006dc5  mov     edx, 1
0x180006dca  mov     [rbp+0A0h+var_120], rsi
0x180006dce  mov     [rbp+0A0h+var_110], 4
0x180006dd6  mov     ecx, [rax+14h]
0x180006dd9  lea     rax, [rsp+1A0h+var_160]
0x180006dde  mov     [rsp+1A0h+var_160], ecx
0x180006de2  lea     rcx, [rbp+0A0h+var_120]
0x180006de6  mov     [rbp+0A0h+var_118], rax
0x180006dea  call    cs:__imp_WebSocketCreateServerHandle
0x180006df0  mov     edi, eax
0x180006df2  test    eax, eax
0x180006df4  js      short loc_180006D7D
0x180006df6  xor     ebx, ebx
0x180006df8  lea     r13, ?sm_rgWebSocketHeaders@WEBSOCKET_CONTEXT@@0PAUHEADER_RECORD@@A; HEADER_RECORD near * WEBSOCKET_CONTEXT::sm_rgWebSocketHeaders
0x180006dff  xor     eax, eax
0x180006e01  lea     r8, [rsp+1A0h+var_160]
0x180006e06  mov     word ptr [rsp+1A0h+var_160], ax
0x180006e0b  mov     rdi, rbx
0x180006e0e  mov     rax, [r12]
0x180006e12  add     rdi, rdi
0x180006e15  mov     rcx, r12
0x180006e18  mov     rax, [rax+18h]
0x180006e1c  mov     rdx, [r13+rdi*8+0]
0x180006e21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e26  test    rax, rax
0x180006e29  jz      short loc_180006E55
0x180006e2b  mov     rcx, [r13+rdi*8+0]
0x180006e30  mov     edx, esi
0x180006e32  shl     rdx, 5
0x180006e36  inc     esi
0x180006e38  mov     [rbp+rdx+0A0h+var_100], rcx
0x180006e3d  movzx   ecx, word ptr [r13+rdi*8+8]
0x180006e43  mov     [rbp+rdx+0A0h+var_F0], rax
0x180006e48  movzx   eax, word ptr [rsp+1A0h+var_160]
0x180006e4d  mov     [rbp+rdx+0A0h+var_F8], ecx
0x180006e51  mov     [rbp+rdx+0A0h+var_E8], eax
0x180006e55  inc     rbx
0x180006e58  cmp     rbx, 6
0x180006e5c  jnz     short loc_180006DFF
0x180006e5e  mov     rax, [r15]
0x180006e61  lea     rdx, aSecWebsocketPr; "Sec-WebSocket-Protocol"
0x180006e68  xor     r8d, r8d
0x180006e6b  mov     rcx, r15
0x180006e6e  mov     rax, [rax+48h]
0x180006e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e77  lea     rcx, [rsp+1A0h+var_15C]
0x180006e7c  xor     r9d, r9d
0x180006e7f  mov     [rsp+1A0h+var_168], rcx
0x180006e84  lea     r13, [r14+88h]
0x180006e8b  lea     rcx, [rsp+1A0h+var_158]
0x180006e90  xor     r8d, r8d
0x180006e93  mov     [rsp+1A0h+var_170], rcx
0x180006e98  mov     rdx, rax
0x180006e9b  lea     rcx, [rbp+0A0h+var_100]
0x180006e9f  mov     dword ptr [rsp+1A0h+var_178], esi
0x180006ea3  mov     [rsp+1A0h+var_180], rcx
0x180006ea8  mov     rcx, [r13+0]
0x180006eac  call    cs:__imp_WebSocketBeginServerHandshake
0x180006eb2  xor     esi, esi
0x180006eb4  mov     edi, eax
0x180006eb6  test    eax, eax
0x180006eb8  jns     loc_180006FB4
0x180006ebe  mov     eax, cs:g_dwDebugFlags
0x180006ec4  lea     rbx, aError08x; "ERROR = %08x\n"
0x180006ecb  test    al, 0Fh
0x180006ecd  jz      short loc_180006F2B
0x180006ecf  mov     rcx, cs:g_pDebug
0x180006ed6  lea     r9, aWebsocketWrapp_3; "WEBSOCKET_WRAPPER::BeginServerHandshake"
0x180006edd  mov     dword ptr [rsp+1A0h+var_178], edi
0x180006ee1  lea     r8d, [rsi+63h]
0x180006ee5  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180006eec  mov     [rsp+1A0h+var_180], rbx
0x180006ef1  call    cs:__imp_PuDbgPrint
0x180006ef7  mov     eax, cs:g_dwDebugFlags
0x180006efd  test    al, 0Fh
0x180006eff  jz      short loc_180006F2B
0x180006f01  mov     rcx, cs:g_pDebug
0x180006f08  lea     r9, aWebsocketConte_0; "WEBSOCKET_CONTEXT::SendWebSocketHandsha"...
0x180006f0f  mov     dword ptr [rsp+1A0h+var_178], edi
0x180006f13  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180006f1a  mov     r8d, 2DDh
0x180006f20  mov     [rsp+1A0h+var_180], rbx
0x180006f25  call    cs:__imp_PuDbgPrint
0x180006f2b  cmp     edi, 83760005h
0x180006f31  jnz     short loc_180006F8D
0x180006f33  mov     rcx, [r14+158h]
0x180006f3a  lea     r9, [rsp+1A0h+var_160]
0x180006f3f  mov     [rsp+1A0h+var_150], rsi
0x180006f44  lea     r8, [rsp+1A0h+var_150]
0x180006f49  mov     [rsp+1A0h+var_160], esi
0x180006f4d  lea     rdx, aWebsocketVersi; "WEBSOCKET_VERSION"
0x180006f54  mov     rax, [rcx]
0x180006f57  mov     rax, [rax+78h]
0x180006f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f60  test    eax, eax
0x180006f62  js      short loc_180006F8D
0x180006f64  mov     rax, [r15]
0x180006f67  lea     rdx, aSecWebsocketVe; "Sec-WebSocket-Version"
0x180006f6e  movzx   r9d, word ptr [rsp+1A0h+var_160]
0x180006f74  mov     rcx, r15
0x180006f77  mov     r8, [rsp+1A0h+var_150]
0x180006f7c  mov     dword ptr [rsp+1A0h+var_180], 1
0x180006f84  mov     rax, [rax+28h]
0x180006f88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f8d  mov     edx, 190h
0x180006f92  lea     r8, aBadRequest; "Bad Request"
0x180006f99  mov     r9d, 0Bh
0x180006f9f  mov     rax, [r15]
0x180006fa2  mov     dword ptr [rsp+1A0h+var_170], esi
0x180006fa6  mov     [rsp+1A0h+var_178], rsi
0x180006fab  mov     rax, [rax+18h]
0x180006faf  jmp     loc_180006D71
0x180006fb4  mov     r12d, esi
0x180006fb7  cmp     [rsp+1A0h+var_15C], esi
0x180006fbb  jbe     loc_1800071A4
0x180006fc1  mov     ebx, 1
0x180006fc6  mov     rcx, [rsp+1A0h+var_158]
0x180006fcb  mov     esi, r12d
0x180006fce  shl     rsi, 5
0x180006fd2  cmp     dword ptr [rsi+rcx+18h], 0FFFFh
0x180006fda  jbe     short loc_180006FFA
0x180006fdc  mov     rax, [rsi+rcx+10h]
0x180006fe1  mov     byte ptr [rax+0FFFEh], 0
0x180006fe8  mov     rax, [rsp+1A0h+var_158]
0x180006fed  mov     dword ptr [rsi+rax+18h], 0FFFFh
0x180006ff5  mov     rcx, [rsp+1A0h+var_158]
0x180006ffa  mov     rcx, [rsi+rcx]; String1
0x180006ffe  lea     rdx, String2; "connection"
0x180007005  call    cs:__imp__stricmp
0x18000700b  test    eax, eax
0x18000700d  mov     rcx, r15
0x180007010  mov     rax, [r15]
0x180007013  jnz     loc_180007162
0x180007019  mov     rax, [rax+8]
0x18000701d  mov     rbx, [r14+158h]
0x180007024  mov     r13, [rsp+1A0h+var_158]
0x180007029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000702e  mov     rcx, [r15]
0x180007031  lea     rdx, aConnection; "Connection"
0x180007038  mov     [rsp+1A0h+var_130], rax
0x18000703d  movzx   eax, word ptr [rax+18h]
0x180007041  mov     word ptr [rsp+1A0h+var_160], ax
0x180007046  mov     rax, [rcx+38h]
0x18000704a  mov     rcx, r15
0x18000704d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007052  mov     edi, eax
0x180007054  test    eax, eax
0x180007056  js      short loc_180007086
0x180007058  mov     rcx, [rbx]
0x18000705b  movzx   eax, word ptr [rsp+1A0h+var_160]
0x180007060  inc     eax
0x180007062  lea     edx, [rax+rax*2]
0x180007065  mov     rax, [rcx+90h]
0x18000706c  shl     edx, 3
0x18000706f  mov     rcx, rbx
0x180007072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007077  mov     [rsp+1A0h+var_150], rax
0x18000707c  test    rax, rax
0x18000707f  jnz     short loc_180007090
0x180007081  mov     edi, 8007000Eh
0x180007086  mov     ebx, 1
0x18000708b  jmp     loc_180007185
0x180007090  mov     rax, [rbx]
0x180007093  mov     rcx, rbx
0x180007096  mov     edx, [rsi+r13+8]
0x18000709b  mov     rax, [rax+90h]
0x1800070a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070a7  mov     [rsp+1A0h+var_140], rax
0x1800070ac  test    rax, rax
0x1800070af  jz      short loc_180007081
0x1800070b1  mov     rax, [rbx]
0x1800070b4  mov     rcx, rbx
0x1800070b7  mov     edx, [rsi+r13+18h]
0x1800070bc  mov     rax, [rax+90h]
0x1800070c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070c8  mov     [rsp+1A0h+var_138], rax
0x1800070cd  test    rax, rax
0x1800070d0  jz      short loc_180007081
0x1800070d2  movzx   ecx, word ptr [rsp+1A0h+var_160]
0x1800070d7  mov     rdx, [rsp+1A0h+var_130]
0x1800070dc  lea     rcx, [rcx+rcx*2]
0x1800070e0  mov     rdx, [rdx+20h]; Src
0x1800070e4  lea     rbx, ds:0[rcx*8]
0x1800070ec  mov     rcx, [rsp+1A0h+var_150]; void *
0x1800070f1  mov     r8, rbx; Size
0x1800070f4  call    memcpy_0
0x1800070f9  mov     r8d, [rsi+r13+8]; Size
0x1800070fe  mov     rdx, [rsi+r13]; Src
0x180007102  mov     rcx, [rsp+1A0h+var_140]; void *
0x180007107  call    memcpy_0
0x18000710c  mov     r8d, [rsi+r13+18h]; Size
0x180007111  mov     rdx, [rsi+r13+10h]; Src
0x180007116  mov     rcx, [rsp+1A0h+var_138]; void *
0x18000711b  call    memcpy_0
0x180007120  mov     rcx, [rsp+1A0h+var_150]
0x180007125  mov     rax, [rsp+1A0h+var_140]
0x18000712a  mov     [rcx+rbx+8], rax
0x18000712f  movzx   eax, word ptr [rsi+r13+8]
0x180007135  mov     [rcx+rbx], ax
0x180007139  mov     rax, [rsp+1A0h+var_138]
0x18000713e  mov     [rcx+rbx+10h], rax
0x180007143  movzx   eax, word ptr [rsi+r13+18h]
0x180007149  mov     [rcx+rbx+2], ax
0x18000714e  mov     ebx, 1
0x180007153  mov     rax, [rsp+1A0h+var_130]
0x180007158  add     [rax+18h], bx
0x18000715c  mov     [rax+20h], rcx
0x180007160  jmp     short loc_180007185
0x180007162  mov     rdx, [rsp+1A0h+var_158]
0x180007167  mov     rax, [rax+28h]
0x18000716b  mov     dword ptr [rsp+1A0h+var_180], ebx
0x18000716f  movzx   r9d, word ptr [rsi+rdx+18h]
0x180007175  mov     r8, [rsi+rdx+10h]
0x18000717a  mov     rdx, [rsi+rdx]
0x18000717e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007183  mov     edi, eax
0x180007185  xor     esi, esi
0x180007187  test    edi, edi
0x180007189  js      loc_180007218
0x18000718f  add     r12d, ebx
0x180007192  cmp     r12d, [rsp+1A0h+var_15C]
0x180007197  jb      loc_180006FC6
0x18000719d  lea     r13, [r14+88h]
0x1800071a4  mov     rdi, [rsp+1A0h+var_128]
  ... truncated ...
```
