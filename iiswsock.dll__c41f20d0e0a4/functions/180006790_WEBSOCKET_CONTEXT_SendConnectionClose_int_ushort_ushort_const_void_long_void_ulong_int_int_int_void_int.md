# WEBSOCKET_CONTEXT::SendConnectionClose(int,ushort,ushort const *,void (*)(long,void *,ulong,int,int,int),void *,int *)

- ea: `0x180006790`
- end: `0x180006997`
- name: `?SendConnectionClose@WEBSOCKET_CONTEXT@@UEAAJHGPEBGP6AXJPEAXKHHH@Z1PEAH@Z`
- size: `519`
- prototype: `__int64 __fastcall(WEBSOCKET_CONTEXT *this, int, unsigned __int16, const unsigned __int16 *, void (*)(int, void *, unsigned int, int, int, int), void *, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002168`
- `0x18000282c`
- `0x180006790`
- `0x180007674`
- `0x180008600`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x18000696b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000696b`
- `iisutil!PuDbgPrint` at `0x18000681f`
- `iisutil!PuDbgPrint` at `0x18000694b`
- `iisutil!PuDbgPrint` at `0x18000681f`
- `iisutil!PuDbgPrint` at `0x18000694b`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800067e9`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800067e9`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z` at `0x1800068ac`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z` at `0x1800068ac`

## string_xrefs

- `0x180006818`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\websocketcontext.cxx`
- `0x180006944`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\websocketcontext.cxx`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_CONTEXT::SendConnectionClose(
        WEBSOCKET_CONTEXT *this,
        int a2,
        unsigned __int16 a3,
        const unsigned __int16 *a4,
        void (*a5)(int, void *, unsigned int, int, int, int),
        void *a6,
        int *a7)
{
  unsigned int v9; // ebp
  TRACE_HELPER *v11; // rcx
  int v12; // ebx
  __int64 v13; // r8
  __int128 v15; // [rsp+40h] [rbp-A8h] BYREF
  _BYTE v16[32]; // [rsp+58h] [rbp-90h] BYREF
  __int64 v17; // [rsp+78h] [rbp-70h]
  int v18; // [rsp+88h] [rbp-60h]

  v15 = 0;
  v9 = a3;
  STRA::STRA((STRA *)v16);
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\websocketcontext.cxx",
      477,
      "WEBSOCKET_CONTEXT::SendConnectionClose",
      "SendConnectionClose\n");
  if ( !a2 )
  {
    v12 = -2147467263;
    goto LABEL_23;
  }
  if ( !a5 )
  {
    v12 = -2147024809;
LABEL_20:
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\websocketcontext.cxx",
        577,
        "WEBSOCKET_CONTEXT::SendConnectionClose",
        "ERROR = %08x\n",
        v12);
    TRACE_HELPER::RaiseTraceEventError(v11, *((struct IHttpContext **)this + 43), 0x33u, v12);
    goto LABEL_23;
  }
  if ( *((_DWORD *)this + 93) )
  {
    v12 = -2147020579;
    goto LABEL_20;
  }
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 27, 1, 0) )
  {
    v12 = -2147023899;
    goto LABEL_20;
  }
  TRACE_HELPER::RaiseTraceEventOnClose(v11, *((struct IHttpContext **)this + 43), 0x31u, v9, a4);
  WORD6(v15) = v9;
  if ( a4 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a4[v13] );
    STRA::CopyWToUTF8Unescaped((STRA *)v16, a4, v13);
    *(_QWORD *)&v15 = v17;
    DWORD2(v15) = v18;
  }
  *((_DWORD *)this + 90) = 1;
  v12 = WEBSOCKET_CONTEXT::WriteMessage(this, 2147483652LL, &v15);
  if ( v12 < 0 )
  {
    v11 = 0;
    _InterlockedCompareExchange((volatile signed __int32 *)this + 27, 0, 1);
    goto LABEL_20;
  }
  if ( a7 && !*a7 )
    _InterlockedCompareExchange((volatile signed __int32 *)this + 27, 0, 1);
LABEL_23:
  STRA::~STRA((STRA *)v16);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180006790  push    rbx
0x180006792  push    rbp
0x180006793  push    rsi
0x180006794  push    rdi
0x180006795  push    r12
0x180006797  push    r13
0x180006799  push    r14
0x18000679b  push    r15
0x18000679d  sub     rsp, 0A8h
0x1800067a4  mov     rax, cs:__security_cookie
0x1800067ab  xor     rax, rsp
0x1800067ae  mov     [rsp+0E8h+var_58], rax
0x1800067b6  mov     r15, [rsp+0E8h+arg_20]
0x1800067be  mov     rdi, rcx
0x1800067c1  mov     r12, [rsp+0E8h+arg_28]
0x1800067c9  lea     rcx, [rsp+0E8h+var_90]
0x1800067ce  mov     rsi, [rsp+0E8h+arg_30]
0x1800067d6  xorps   xmm0, xmm0
0x1800067d9  movdqu  [rsp+0E8h+var_A8], xmm0
0x1800067df  mov     rbx, r9
0x1800067e2  movzx   ebp, r8w
0x1800067e6  mov     r14d, edx
0x1800067e9  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x1800067ef  test    byte ptr cs:g_dwDebugFlags, 3
0x1800067f6  jz      short loc_180006825
0x1800067f8  mov     rcx, cs:g_pDebug
0x1800067ff  lea     rax, aSendconnection; "SendConnectionClose\n"
0x180006806  lea     r9, aWebsocketConte_9; "WEBSOCKET_CONTEXT::SendConnectionClose"
0x18000680d  mov     [rsp+0E8h+var_C8], rax
0x180006812  mov     r8d, 1DDh
0x180006818  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000681f  call    cs:__imp_PuDbgPrint
0x180006825  xor     r13d, r13d
0x180006828  test    r14d, r14d
0x18000682b  jnz     short loc_180006837
0x18000682d  mov     ebx, 80004001h
0x180006832  jmp     loc_180006966
0x180006837  test    r15, r15
0x18000683a  jnz     short loc_180006846
0x18000683c  mov     ebx, 80070057h
0x180006841  jmp     loc_180006917
0x180006846  mov     eax, [rdi+174h]
0x18000684c  test    eax, eax
0x18000684e  jz      short loc_18000685A
0x180006850  mov     ebx, 800710DDh
0x180006855  jmp     loc_180006917
0x18000685a  xor     eax, eax
0x18000685c  lea     r14d, [rax+1]
0x180006860  lock cmpxchg [rdi+6Ch], r14d
0x180006866  jz      short loc_180006872
0x180006868  mov     ebx, 800703E5h
0x18000686d  jmp     loc_180006917
0x180006872  mov     rdx, [rdi+158h]; struct IHttpContext *
0x180006879  mov     r9d, ebp; unsigned int
0x18000687c  mov     r8d, 31h ; '1'; unsigned int
0x180006882  mov     [rsp+0E8h+var_C8], rbx; unsigned __int16 *
0x180006887  call    ?RaiseTraceEventOnClose@TRACE_HELPER@@QEAAXPEAVIHttpContext@@KKPEBG@Z; TRACE_HELPER::RaiseTraceEventOnClose(IHttpContext *,ulong,ulong,ushort const *)
0x18000688c  mov     word ptr [rsp+0E8h+var_A8+0Ch], bp
0x180006891  test    rbx, rbx
0x180006894  jz      short loc_1800068C7
0x180006896  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000689a  inc     r8
0x18000689d  cmp     [rbx+r8*2], r13w
0x1800068a2  jnz     short loc_18000689A
0x1800068a4  mov     rdx, rbx
0x1800068a7  lea     rcx, [rsp+0E8h+var_90]
0x1800068ac  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z; STRA::CopyWToUTF8Unescaped(ushort const *,ulong)
0x1800068b2  mov     rax, [rsp+0E8h+var_70]
0x1800068b7  mov     qword ptr [rsp+0E8h+var_A8], rax
0x1800068bc  mov     eax, [rsp+0E8h+var_60]
0x1800068c3  mov     dword ptr [rsp+0E8h+var_A8+8], eax
0x1800068c7  mov     [rsp+0E8h+var_B8], rsi
0x1800068cc  lea     r8, [rsp+0E8h+var_A8]
0x1800068d1  mov     [rsp+0E8h+var_C0], r12
0x1800068d6  mov     edx, 80000004h
0x1800068db  mov     rcx, rdi
0x1800068de  mov     [rsp+0E8h+var_C8], r15
0x1800068e3  mov     [rdi+168h], r14d
0x1800068ea  call    ?WriteMessage@WEBSOCKET_CONTEXT@@AEAAJW4_WEB_SOCKET_BUFFER_TYPE@@PEAT_WEB_SOCKET_BUFFER@@HP6AXJPEAXKHHH@Z2PEAH@Z; WEBSOCKET_CONTEXT::WriteMessage(_WEB_SOCKET_BUFFER_TYPE,_WEB_SOCKET_BUFFER *,int,void (*)(long,void *,ulong,int,int,int),void *,int *)
0x1800068ef  mov     ebx, eax
0x1800068f1  test    eax, eax
0x1800068f3  js      short loc_18000690C
0x1800068f5  test    rsi, rsi
0x1800068f8  jz      short loc_180006966
0x1800068fa  cmp     [rsi], r13d
0x1800068fd  jnz     short loc_180006966
0x1800068ff  mov     ecx, r13d
0x180006902  mov     eax, r14d
0x180006905  lock cmpxchg [rdi+6Ch], ecx
0x18000690a  jmp     short loc_180006966
0x18000690c  mov     ecx, r13d
0x18000690f  mov     eax, r14d
0x180006912  lock cmpxchg [rdi+6Ch], ecx
0x180006917  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000691e  jz      short loc_180006951
0x180006920  mov     rcx, cs:g_pDebug
0x180006927  lea     rax, aError08x; "ERROR = %08x\n"
0x18000692e  mov     dword ptr [rsp+0E8h+var_C0], ebx
0x180006932  lea     r9, aWebsocketConte_9; "WEBSOCKET_CONTEXT::SendConnectionClose"
0x180006939  mov     r8d, 241h
0x18000693f  mov     [rsp+0E8h+var_C8], rax
0x180006944  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000694b  call    cs:__imp_PuDbgPrint
0x180006951  mov     rdx, [rdi+158h]; struct IHttpContext *
0x180006958  mov     r9d, ebx; int
0x18000695b  mov     r8d, 33h ; '3'; unsigned int
0x180006961  call    ?RaiseTraceEventError@TRACE_HELPER@@QEAAXPEAVIHttpContext@@KJ@Z; TRACE_HELPER::RaiseTraceEventError(IHttpContext *,ulong,long)
0x180006966  lea     rcx, [rsp+0E8h+var_90]
0x18000696b  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180006971  mov     eax, ebx
0x180006973  mov     rcx, [rsp+0E8h+var_58]
0x18000697b  xor     rcx, rsp; StackCookie
0x18000697e  call    __security_check_cookie
0x180006983  add     rsp, 0A8h
0x18000698a  pop     r15
0x18000698c  pop     r14
0x18000698e  pop     r13
0x180006990  pop     r12
0x180006992  pop     rdi
0x180006993  pop     rsi
0x180006994  pop     rbp
0x180006995  pop     rbx
0x180006996  retn
```
