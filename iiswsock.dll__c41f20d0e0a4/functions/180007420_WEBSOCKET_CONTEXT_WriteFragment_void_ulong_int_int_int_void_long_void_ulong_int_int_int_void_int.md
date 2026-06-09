# WEBSOCKET_CONTEXT::WriteFragment(void *,ulong *,int,int,int,void (*)(long,void *,ulong,int,int,int),void *,int *)

- ea: `0x180007420`
- end: `0x18000766b`
- name: `?WriteFragment@WEBSOCKET_CONTEXT@@UEAAJPEAXPEAKHHHP6AXJ0KHHH@Z0PEAH@Z`
- size: `587`
- prototype: `__int64 __fastcall(WEBSOCKET_CONTEXT *this, void *, unsigned int *, int, int, int, void (*)(int, void *, unsigned int, int, int, int), void *, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001bb8`
- `0x180002168`
- `0x180007318`
- `0x180007420`
- `0x180007674`
- `0x180009010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180007476`
- `iisutil!PuDbgPrint` at `0x18000762e`
- `iisutil!PuDbgPrint` at `0x180007476`
- `iisutil!PuDbgPrint` at `0x18000762e`

## string_xrefs

- `0x180007458`: `WriteFragment\n`
- `0x18000745f`: `WEBSOCKET_CONTEXT::WriteFragment`
- `0x180007615`: `WEBSOCKET_CONTEXT::WriteFragment`
- `0x18000746f`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\websocketcontext.cxx`
- `0x180007627`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\websocketcontext.cxx`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_CONTEXT::WriteFragment(
        WEBSOCKET_CONTEXT *this,
        void *a2,
        unsigned int *a3,
        int a4,
        int a5,
        int a6,
        void (*a7)(int, void *, unsigned int, int, int, int),
        void *a8,
        int *a9)
{
  int v9; // r14d
  TRACE_HELPER *v14; // rcx
  int Loop; // ebx
  unsigned int v16; // ebx
  __int64 v17; // r15
  unsigned int v18; // r12d
  int (__fastcall ***v19)(_QWORD, GUID **); // rax
  struct IHttpTraceContext *v20; // rax
  const struct _GUID *v21; // rdx
  __int128 v23; // [rsp+48h] [rbp-70h] BYREF
  GUID *v24; // [rsp+58h] [rbp-60h] BYREF
  __int128 v25; // [rsp+60h] [rbp-58h]

  v9 = 0;
  v23 = 0;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\websocketcontext.cxx",
      92,
      "WEBSOCKET_CONTEXT::WriteFragment",
      "WriteFragment\n");
  Loop = WEBSOCKET_CONTEXT::TryStartReadLoop(this);
  if ( Loop < 0 )
    goto LABEL_26;
  if ( !a4 )
  {
    Loop = -2147467263;
LABEL_26:
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\websocketcontext.cxx",
        196,
        "WEBSOCKET_CONTEXT::WriteFragment",
        "ERROR = %08x\n",
        Loop);
    if ( v9 )
    {
      v14 = 0;
      _InterlockedCompareExchange((volatile signed __int32 *)this + 27, 0, 1);
    }
    TRACE_HELPER::RaiseTraceEventError(v14, *((struct IHttpContext **)this + 43), 0x23u, Loop);
    return (unsigned int)Loop;
  }
  if ( !a3 || !a7 )
  {
    Loop = -2147024809;
    goto LABEL_26;
  }
  if ( *((_DWORD *)this + 93) )
  {
    Loop = -2147020579;
    goto LABEL_26;
  }
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 27, 1, 0) )
  {
    Loop = -2147023899;
    goto LABEL_26;
  }
  v9 = 1;
  if ( a5 )
    v16 = -(a6 != 0) - 0x7FFFFFFF;
  else
    v16 = -(a6 != 0) - 2147483645;
  v17 = *((_QWORD *)this + 43);
  v18 = *a3;
  v19 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 272LL))(v17);
  v24 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v25 = 0;
  if ( (**v19)(v19, &v24) >= 0 && DWORD2(v25) && DWORD1(v25) >= 5 && ((_DWORD)v25 == 0x4000 || (v25 & 0x4000) != 0) )
  {
    v20 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 272LL))(v17);
    IISWebSocketEvents::WEBSOCKET_WRITE_FRAGMENT_START::RaiseEvent(v20, v21, v16, v18);
  }
  DWORD2(v23) = *a3;
  *(_QWORD *)&v23 = a2;
  Loop = WEBSOCKET_CONTEXT::WriteMessage(this, v16, &v23);
  if ( Loop < 0 )
    goto LABEL_26;
  if ( a9 && !*a9 )
    _InterlockedCompareExchange((volatile signed __int32 *)this + 27, 0, 1);
  return (unsigned int)Loop;
}

```

## disassembly

```asm
0x180007420  push    rbx
0x180007422  push    rbp
0x180007423  push    rsi
0x180007424  push    rdi
0x180007425  push    r12
0x180007427  push    r13
0x180007429  push    r14
0x18000742b  push    r15
0x18000742d  sub     rsp, 78h
0x180007431  xor     r14d, r14d
0x180007434  xorps   xmm0, xmm0
0x180007437  test    byte ptr cs:g_dwDebugFlags, 3
0x18000743e  mov     ebp, r9d
0x180007441  mov     rsi, r8
0x180007444  mov     r13, rdx
0x180007447  mov     rdi, rcx
0x18000744a  movups  [rsp+0B8h+var_70], xmm0
0x18000744f  jz      short loc_18000747C
0x180007451  mov     rcx, cs:g_pDebug
0x180007458  lea     rax, aWritefragment; "WriteFragment\n"
0x18000745f  lea     r9, aWebsocketConte; "WEBSOCKET_CONTEXT::WriteFragment"
0x180007466  mov     [rsp+0B8h+var_98], rax
0x18000746b  lea     r8d, [r14+5Ch]
0x18000746f  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007476  call    cs:__imp_PuDbgPrint
0x18000747c  mov     rcx, rdi; this
0x18000747f  call    ?TryStartReadLoop@WEBSOCKET_CONTEXT@@AEAAJXZ; WEBSOCKET_CONTEXT::TryStartReadLoop(void)
0x180007484  mov     ebx, eax
0x180007486  mov     r15d, 1
0x18000748c  test    eax, eax
0x18000748e  js      loc_1800075FA
0x180007494  test    ebp, ebp
0x180007496  jnz     short loc_1800074A2
0x180007498  mov     ebx, 80004001h
0x18000749d  jmp     loc_1800075FA
0x1800074a2  test    rsi, rsi
0x1800074a5  jz      loc_1800075ED
0x1800074ab  mov     rbp, [rsp+0B8h+arg_30]
0x1800074b3  test    rbp, rbp
0x1800074b6  jz      loc_1800075ED
0x1800074bc  mov     eax, [rdi+174h]
0x1800074c2  test    eax, eax
0x1800074c4  jz      short loc_1800074D0
0x1800074c6  mov     ebx, 800710DDh
0x1800074cb  jmp     loc_1800075FA
0x1800074d0  xor     eax, eax
0x1800074d2  lock cmpxchg [rdi+6Ch], r15d
0x1800074d8  jz      short loc_1800074E4
0x1800074da  mov     ebx, 800703E5h
0x1800074df  jmp     loc_1800075FA
0x1800074e4  cmp     [rsp+0B8h+arg_20], 0
0x1800074ec  mov     r14d, r15d
0x1800074ef  mov     eax, [rsp+0B8h+arg_28]
0x1800074f6  jz      short loc_180007504
0x1800074f8  neg     eax
0x1800074fa  sbb     ebx, ebx
0x1800074fc  add     ebx, 80000001h
0x180007502  jmp     short loc_18000750E
0x180007504  neg     eax
0x180007506  sbb     ebx, ebx
0x180007508  add     ebx, 80000003h
0x18000750e  mov     r15, [rdi+158h]
0x180007515  mov     r12d, [rsi]
0x180007518  mov     rcx, r15
0x18000751b  mov     rax, [r15]
0x18000751e  mov     rax, [rax+110h]
0x180007525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000752a  mov     r8, rax
0x18000752d  lea     rdx, [rsp+0B8h+var_60]
0x180007532  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180007539  xorps   xmm0, xmm0
0x18000753c  mov     [rsp+0B8h+var_60], rax
0x180007541  movdqu  [rsp+0B8h+var_58], xmm0
0x180007547  mov     rcx, [r8]
0x18000754a  mov     rax, [rcx]
0x18000754d  mov     rcx, r8
0x180007550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007555  test    eax, eax
0x180007557  js      short loc_180007598
0x180007559  cmp     dword ptr [rsp+0B8h+var_58+8], 0
0x18000755e  jz      short loc_180007598
0x180007560  cmp     dword ptr [rsp+0B8h+var_58+4], 5
0x180007565  jb      short loc_180007598
0x180007567  mov     eax, 4000h
0x18000756c  cmp     dword ptr [rsp+0B8h+var_58], eax
0x180007570  jz      short loc_180007578
0x180007572  test    dword ptr [rsp+0B8h+var_58], eax
0x180007576  jz      short loc_180007598
0x180007578  mov     rax, [r15]
0x18000757b  mov     rcx, r15
0x18000757e  mov     rax, [rax+110h]
0x180007585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000758a  mov     rcx, rax; struct IHttpTraceContext *
0x18000758d  mov     r9d, r12d; unsigned int
0x180007590  mov     r8d, ebx; unsigned int
0x180007593  call    ?RaiseEvent@WEBSOCKET_WRITE_FRAGMENT_START@IISWebSocketEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@KK@Z; IISWebSocketEvents::WEBSOCKET_WRITE_FRAGMENT_START::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong,ulong)
0x180007598  mov     eax, [rsi]
0x18000759a  lea     r8, [rsp+0B8h+var_70]
0x18000759f  mov     rsi, [rsp+0B8h+arg_40]
0x1800075a7  mov     edx, ebx
0x1800075a9  mov     dword ptr [rsp+0B8h+var_70+8], eax
0x1800075ad  mov     rcx, rdi
0x1800075b0  mov     rax, [rsp+0B8h+arg_38]
0x1800075b8  mov     [rsp+0B8h+var_88], rsi
0x1800075bd  mov     [rsp+0B8h+var_90], rax
0x1800075c2  mov     [rsp+0B8h+var_98], rbp
0x1800075c7  mov     qword ptr [rsp+0B8h+var_70], r13
0x1800075cc  call    ?WriteMessage@WEBSOCKET_CONTEXT@@AEAAJW4_WEB_SOCKET_BUFFER_TYPE@@PEAT_WEB_SOCKET_BUFFER@@HP6AXJPEAXKHHH@Z2PEAH@Z; WEBSOCKET_CONTEXT::WriteMessage(_WEB_SOCKET_BUFFER_TYPE,_WEB_SOCKET_BUFFER *,int,void (*)(long,void *,ulong,int,int,int),void *,int *)
0x1800075d1  mov     ebx, eax
0x1800075d3  test    eax, eax
0x1800075d5  js      short loc_1800075F4
0x1800075d7  test    rsi, rsi
0x1800075da  jz      short loc_180007658
0x1800075dc  cmp     dword ptr [rsi], 0
0x1800075df  jnz     short loc_180007658
0x1800075e1  xor     ecx, ecx
0x1800075e3  mov     eax, r14d
0x1800075e6  lock cmpxchg [rdi+6Ch], ecx
0x1800075eb  jmp     short loc_180007658
0x1800075ed  mov     ebx, 80070057h
0x1800075f2  jmp     short loc_1800075FA
0x1800075f4  mov     r15d, 1
0x1800075fa  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180007601  jz      short loc_180007634
0x180007603  mov     rcx, cs:g_pDebug
0x18000760a  lea     rax, aError08x; "ERROR = %08x\n"
0x180007611  mov     dword ptr [rsp+0B8h+var_90], ebx
0x180007615  lea     r9, aWebsocketConte; "WEBSOCKET_CONTEXT::WriteFragment"
0x18000761c  mov     r8d, 0C4h
0x180007622  mov     [rsp+0B8h+var_98], rax
0x180007627  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000762e  call    cs:__imp_PuDbgPrint
0x180007634  test    r14d, r14d
0x180007637  jz      short loc_180007643
0x180007639  xor     ecx, ecx; this
0x18000763b  mov     eax, r15d
0x18000763e  lock cmpxchg [rdi+6Ch], ecx
0x180007643  mov     rdx, [rdi+158h]; struct IHttpContext *
0x18000764a  mov     r9d, ebx; int
0x18000764d  mov     r8d, 23h ; '#'; unsigned int
0x180007653  call    ?RaiseTraceEventError@TRACE_HELPER@@QEAAXPEAVIHttpContext@@KJ@Z; TRACE_HELPER::RaiseTraceEventError(IHttpContext *,ulong,long)
0x180007658  mov     eax, ebx
0x18000765a  add     rsp, 78h
0x18000765e  pop     r15
0x180007660  pop     r14
0x180007662  pop     r13
0x180007664  pop     r12
0x180007666  pop     rdi
0x180007667  pop     rsi
0x180007668  pop     rbp
0x180007669  pop     rbx
0x18000766a  retn
```
