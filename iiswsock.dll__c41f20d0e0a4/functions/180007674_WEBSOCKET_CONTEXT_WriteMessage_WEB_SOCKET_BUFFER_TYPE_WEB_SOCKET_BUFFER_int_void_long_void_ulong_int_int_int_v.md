# WEBSOCKET_CONTEXT::WriteMessage(_WEB_SOCKET_BUFFER_TYPE,_WEB_SOCKET_BUFFER *,int,void (*)(long,void *,ulong,int,int,int),void *,int *)

- ea: `0x180007674`
- end: `0x180007848`
- name: `?WriteMessage@WEBSOCKET_CONTEXT@@AEAAJW4_WEB_SOCKET_BUFFER_TYPE@@PEAT_WEB_SOCKET_BUFFER@@HP6AXJPEAXKHHH@Z2PEAH@Z`
- size: `468`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, __int64, __int64, _DWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180006790`
- `0x180007420`

## callees

- `0x180001ce0`
- `0x180002500`
- `0x180004ebc`
- `0x1800061e0`
- `0x180007674`
- `0x180009010`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x1800076d1`
- `iisutil!WriteRefTraceLog` at `0x180007728`
- `iisutil!WriteRefTraceLog` at `0x1800077c0`
- `iisutil!WriteRefTraceLog` at `0x1800076d1`
- `iisutil!WriteRefTraceLog` at `0x180007728`
- `iisutil!WriteRefTraceLog` at `0x1800077c0`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_CONTEXT::WriteMessage(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        _DWORD *a7)
{
  signed __int32 v10; // edx
  __int64 v11; // rcx
  __int64 v12; // rdx
  void (__fastcall *v13)(WEBSOCKET_CONTEXT *, int); // r9
  int v14; // r14d
  __int64 v15; // rcx
  _DWORD *v16; // rdi
  TRACE_HELPER *v17; // rcx
  struct IHttpContext *v18; // rdx
  int v20; // [rsp+68h] [rbp+20h] BYREF

  v20 = 0;
  *(_QWORD *)(a1 + 72) = a5;
  *(_QWORD *)(a1 + 80) = a6;
  *(_DWORD *)(a1 + 96) = 0;
  v10 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 380), 1u);
  v11 = *(_QWORD *)(a1 + 432);
  v12 = (unsigned int)(v10 + 1);
  if ( v11 )
    WriteRefTraceLog(v11, v12, a1);
  v13 = WEBSOCKET_CONTEXT::OnWebSocketSendCloseCompletion;
  if ( a2 != -2147483644 )
    v13 = WEBSOCKET_CONTEXT::OnWebSocketSendFragmentCompletion;
  v14 = WEBSOCKET_WRAPPER::Send(a1 + 112, a2, a3, v13, a1, &v20);
  if ( v14 >= 0 )
  {
    if ( v20 )
    {
      if ( a7 )
        *a7 = 1;
    }
    else
    {
      v16 = a7;
      if ( a7 )
      {
        v17 = *(TRACE_HELPER **)(a1 + 432);
        if ( v17 )
          WriteRefTraceLog(v17, *(unsigned int *)(a1 + 380), a1);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 380), 0xFFFFFFFF) == 1
          && *(_DWORD *)(a1 + 352) == 3 )
        {
          (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 344) + 64LL))(*(_QWORD *)(a1 + 344), 0);
        }
        *v16 = v20;
        *(_OWORD *)(a1 + 72) = 0;
        *(_OWORD *)(a1 + 88) = 0;
        v18 = *(struct IHttpContext **)(a1 + 344);
        if ( a2 == -2147483644 )
          TRACE_HELPER::RaiseTraceEvent(v17, v18, 0x32u);
        else
          TRACE_HELPER::RaiseTraceEventGeneral(v17, v18, 0x22u, *(_DWORD *)(a3 + 8));
      }
      else
      {
        WEBSOCKET_CONTEXT::PostCompletion((WEBSOCKET_CONTEXT *)a1, 1u);
      }
    }
  }
  else
  {
    v15 = *(_QWORD *)(a1 + 432);
    if ( v15 )
      WriteRefTraceLog(v15, *(unsigned int *)(a1 + 380), a1);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 380), 0xFFFFFFFF) == 1 && *(_DWORD *)(a1 + 352) == 3 )
      (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 344) + 64LL))(*(_QWORD *)(a1 + 344), 0);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180007674  mov     rax, rsp
0x180007677  mov     [rax+8], rbx
0x18000767b  mov     [rax+10h], rbp
0x18000767f  mov     [rax+20h], r9d
0x180007683  push    rsi
0x180007684  push    rdi
0x180007685  push    r14
0x180007687  sub     rsp, 30h
0x18000768b  mov     dword ptr [rax+20h], 0
0x180007692  mov     esi, edx
0x180007694  mov     rax, [rsp+48h+arg_20]
0x180007699  mov     rbp, r8
0x18000769c  mov     [rcx+48h], rax
0x1800076a0  mov     rbx, rcx
0x1800076a3  mov     rax, [rsp+48h+arg_28]
0x1800076a8  mov     edx, 1
0x1800076ad  mov     [rcx+50h], rax
0x1800076b1  mov     dword ptr [rcx+60h], 0
0x1800076b8  lock xadd [rcx+17Ch], edx
0x1800076c0  mov     rcx, [rcx+1B0h]
0x1800076c7  inc     edx
0x1800076c9  test    rcx, rcx
0x1800076cc  jz      short loc_1800076D7
0x1800076ce  mov     r8, rbx
0x1800076d1  call    cs:__imp_WriteRefTraceLog
0x1800076d7  lea     rax, ?OnWebSocketSendFragmentCompletion@WEBSOCKET_CONTEXT@@CAXPEAXJ@Z; WEBSOCKET_CONTEXT::OnWebSocketSendFragmentCompletion(void *,long)
0x1800076de  cmp     esi, 80000004h
0x1800076e4  lea     r9, ?OnWebSocketSendCloseCompletion@WEBSOCKET_CONTEXT@@CAXPEAXJ@Z; WEBSOCKET_CONTEXT::OnWebSocketSendCloseCompletion(void *,long)
0x1800076eb  mov     r8, rbp
0x1800076ee  cmovnz  r9, rax
0x1800076f2  lea     rcx, [rbx+70h]
0x1800076f6  lea     rax, [rsp+48h+arg_18]
0x1800076fb  mov     edx, esi
0x1800076fd  mov     [rsp+48h+var_20], rax
0x180007702  mov     [rsp+48h+var_28], rbx
0x180007707  call    ?Send@WEBSOCKET_WRAPPER@@QEAAJW4_WEB_SOCKET_BUFFER_TYPE@@PEAT_WEB_SOCKET_BUFFER@@P6AXPEAXJ@Z2PEAH@Z; WEBSOCKET_WRAPPER::Send(_WEB_SOCKET_BUFFER_TYPE,_WEB_SOCKET_BUFFER *,void (*)(void *,long),void *,int *)
0x18000770c  mov     r14d, eax
0x18000770f  test    eax, eax
0x180007711  jns     short loc_18000776B
0x180007713  mov     rcx, [rbx+1B0h]
0x18000771a  test    rcx, rcx
0x18000771d  jz      short loc_18000772E
0x18000771f  mov     edx, [rbx+17Ch]
0x180007725  mov     r8, rbx
0x180007728  call    cs:__imp_WriteRefTraceLog
0x18000772e  or      eax, 0FFFFFFFFh
0x180007731  lock xadd [rbx+17Ch], eax
0x180007739  cmp     eax, 1
0x18000773c  jnz     loc_180007832
0x180007742  mov     eax, [rbx+160h]
0x180007748  cmp     eax, 3
0x18000774b  jnz     loc_180007832
0x180007751  mov     rcx, [rbx+158h]
0x180007758  xor     edx, edx
0x18000775a  mov     rax, [rcx]
0x18000775d  mov     rax, [rax+40h]
0x180007761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007766  jmp     loc_180007832
0x18000776b  cmp     [rsp+48h+arg_18], 0
0x180007770  jz      short loc_18000778E
0x180007772  mov     rax, [rsp+48h+arg_30]
0x18000777a  test    rax, rax
0x18000777d  jz      loc_180007832
0x180007783  mov     dword ptr [rax], 1
0x180007789  jmp     loc_180007832
0x18000778e  mov     rdi, [rsp+48h+arg_30]
0x180007796  test    rdi, rdi
0x180007799  jnz     short loc_1800077AB
0x18000779b  lea     edx, [rdi+1]; unsigned int
0x18000779e  mov     rcx, rbx; this
0x1800077a1  call    ?PostCompletion@WEBSOCKET_CONTEXT@@AEAAJK@Z; WEBSOCKET_CONTEXT::PostCompletion(ulong)
0x1800077a6  jmp     loc_180007832
0x1800077ab  mov     rcx, [rbx+1B0h]
0x1800077b2  test    rcx, rcx
0x1800077b5  jz      short loc_1800077C6
0x1800077b7  mov     edx, [rbx+17Ch]
0x1800077bd  mov     r8, rbx
0x1800077c0  call    cs:__imp_WriteRefTraceLog
0x1800077c6  or      eax, 0FFFFFFFFh
0x1800077c9  lock xadd [rbx+17Ch], eax
0x1800077d1  cmp     eax, 1
0x1800077d4  jnz     short loc_1800077F6
0x1800077d6  mov     eax, [rbx+160h]
0x1800077dc  cmp     eax, 3
0x1800077df  jnz     short loc_1800077F6
0x1800077e1  mov     rcx, [rbx+158h]
0x1800077e8  xor     edx, edx
0x1800077ea  mov     rax, [rcx]
0x1800077ed  mov     rax, [rax+40h]
0x1800077f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077f6  mov     eax, [rsp+48h+arg_18]
0x1800077fa  xorps   xmm0, xmm0
0x1800077fd  mov     [rdi], eax
0x1800077ff  movups  xmmword ptr [rbx+48h], xmm0
0x180007803  movups  xmmword ptr [rbx+58h], xmm0
0x180007807  mov     rdx, [rbx+158h]; struct IHttpContext *
0x18000780e  cmp     esi, 80000004h
0x180007814  jnz     short loc_180007823
0x180007816  mov     r8d, 32h ; '2'; unsigned int
0x18000781c  call    ?RaiseTraceEvent@TRACE_HELPER@@QEAAXPEAVIHttpContext@@K@Z; TRACE_HELPER::RaiseTraceEvent(IHttpContext *,ulong)
0x180007821  jmp     short loc_180007832
0x180007823  mov     r9d, [rbp+8]; unsigned int
0x180007827  mov     r8d, 22h ; '"'; unsigned int
0x18000782d  call    ?RaiseTraceEventGeneral@TRACE_HELPER@@QEAAXPEAVIHttpContext@@KK@Z; TRACE_HELPER::RaiseTraceEventGeneral(IHttpContext *,ulong,ulong)
0x180007832  mov     rbx, [rsp+48h+arg_0]
0x180007837  mov     eax, r14d
0x18000783a  mov     rbp, [rsp+48h+arg_8]
0x18000783f  add     rsp, 30h
0x180007843  pop     r14
0x180007845  pop     rdi
0x180007846  pop     rsi
0x180007847  retn
```
