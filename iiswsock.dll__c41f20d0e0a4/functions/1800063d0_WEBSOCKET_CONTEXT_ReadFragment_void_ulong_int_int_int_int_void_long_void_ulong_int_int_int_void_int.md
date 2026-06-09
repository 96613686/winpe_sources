# WEBSOCKET_CONTEXT::ReadFragment(void *,ulong *,int,int *,int *,int *,void (*)(long,void *,ulong,int,int,int),void *,int *)

- ea: `0x1800063d0`
- end: `0x1800066ae`
- name: `?ReadFragment@WEBSOCKET_CONTEXT@@UEAAJPEAXPEAKHPEAH22P6AXJ0KHHH@Z02@Z`
- size: `734`
- prototype: `__int64 __fastcall(WEBSOCKET_CONTEXT *this, void *, unsigned int *, int, int *, int *, int *, void (*)(int, void *, unsigned int, int, int, int), void *, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180002168`
- `0x180002500`
- `0x1800042e0`
- `0x1800061e0`
- `0x1800063d0`
- `0x180007318`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006511`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000661e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006511`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000661e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000649f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006500`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000649f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006500`
- `iisutil!WriteRefTraceLog` at `0x1800065af`
- `iisutil!WriteRefTraceLog` at `0x1800065af`
- `iisutil!PuDbgPrint` at `0x180006422`
- `iisutil!PuDbgPrint` at `0x180006689`
- `iisutil!PuDbgPrint` at `0x180006422`
- `iisutil!PuDbgPrint` at `0x180006689`

## string_xrefs

- `0x18000641b`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\websocketcontext.cxx`
- `0x18000667c`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\websocketcontext.cxx`
- `0x180006402`: `ReadFragment\n`
- `0x180006409`: `WEBSOCKET_CONTEXT::ReadFragment`
- `0x18000666e`: `WEBSOCKET_CONTEXT::ReadFragment`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_CONTEXT::ReadFragment(
        WEBSOCKET_CONTEXT *this,
        void *a2,
        unsigned int *a3,
        int a4,
        int *a5,
        int *a6,
        int *a7,
        void (*a8)(int, void *, unsigned int, int, int, int),
        void *a9,
        int *a10)
{
  WEBSOCKET_CONTEXT *v12; // rbp
  int Loop; // ebx
  TRACE_HELPER *v14; // rcx
  int v15; // r12d
  __int64 v16; // rsi
  __int64 v17; // rbx
  signed __int32 v18; // edx
  __int64 v19; // rcx
  __int64 v20; // rdx

  v12 = this;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\websocketcontext.cxx",
      255,
      "WEBSOCKET_CONTEXT::ReadFragment",
      "ReadFragment\n");
  if ( !a4 )
  {
    Loop = -2147467263;
    goto LABEL_31;
  }
  if ( !a3 || !a5 || !a6 || !a7 || !a8 )
  {
    Loop = -2147024809;
    goto LABEL_31;
  }
  if ( *((_DWORD *)v12 + 93) )
  {
    Loop = -2147020579;
    goto LABEL_31;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v12 + 392));
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)v12 + 26, 1, 0) )
  {
    TRACE_HELPER::RaiseTraceEventGeneral(v14, *((struct IHttpContext **)v12 + 43), 0x10u, *a3);
    v15 = 1;
    if ( *((int *)v12 + 96) >= 0 )
    {
      v16 = *((_QWORD *)v12 + 34);
      EnterCriticalSection((LPCRITICAL_SECTION)(v16 + 16));
      v17 = *(_QWORD *)(v16 + 56);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v16 + 16));
      if ( v17 == v16 + 56 )
      {
        *((_DWORD *)v12 + 16) = *a3;
        *((_QWORD *)v12 + 6) = a9;
        *((_QWORD *)v12 + 7) = a2;
        *((_QWORD *)v12 + 5) = a8;
        if ( a10 )
          *a10 = 1;
      }
      else if ( a10 )
      {
        RECEIVE_QUEUE::QueryData(*((RECEIVE_QUEUE **)v12 + 34), a2, a3, a5, a6, a7);
        _InterlockedCompareExchange((volatile signed __int32 *)v12 + 26, 0, 1);
        *a10 = 0;
        v15 = 0;
        TRACE_HELPER::RaiseTraceEventGeneral(0, *((struct IHttpContext **)v12 + 43), 0x12u, *a3);
      }
      else
      {
        *((_DWORD *)v12 + 16) = *a3;
        *((_QWORD *)v12 + 7) = a2;
        *((_QWORD *)v12 + 6) = a9;
        *((_QWORD *)v12 + 5) = a8;
        Loop = WEBSOCKET_CONTEXT::PostCompletion(v12, 0);
        if ( Loop < 0 )
        {
          *((_QWORD *)v12 + 7) = 0;
          *((_DWORD *)v12 + 16) = 0;
          *((_QWORD *)v12 + 5) = 0;
          *((_QWORD *)v12 + 6) = 0;
          goto LABEL_27;
        }
        v18 = _InterlockedExchangeAdd((volatile signed __int32 *)v12 + 95, 1u);
        v19 = *((_QWORD *)v12 + 54);
        v20 = (unsigned int)(v18 + 1);
        if ( v19 )
          WriteRefTraceLog(v19, v20, v12);
      }
    }
    else
    {
      Loop = *((_DWORD *)v12 + 96);
      if ( Loop < 0 )
        goto LABEL_27;
    }
    Loop = WEBSOCKET_CONTEXT::TryStartReadLoop(v12);
    goto LABEL_27;
  }
  v15 = 0;
  Loop = -2147023899;
LABEL_27:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v12 + 392));
  if ( Loop >= 0 )
    return (unsigned int)Loop;
  if ( v15 )
  {
    this = 0;
    _InterlockedCompareExchange((volatile signed __int32 *)v12 + 26, 0, 1);
  }
LABEL_31:
  TRACE_HELPER::RaiseTraceEventError(this, *((struct IHttpContext **)v12 + 43), 0x13u, Loop);
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\websocketcontext.cxx",
      447,
      "WEBSOCKET_CONTEXT::ReadFragment",
      "ERROR = %08x\n",
      Loop);
  if ( a10 )
    *a10 = 0;
  return (unsigned int)Loop;
}

```

## disassembly

```asm
0x1800063d0  mov     [rsp+arg_0], rbx
0x1800063d5  mov     [rsp+arg_8], rdx
0x1800063da  push    rbp
0x1800063db  push    rsi
0x1800063dc  push    rdi
0x1800063dd  push    r12
0x1800063df  push    r13
0x1800063e1  push    r14
0x1800063e3  push    r15
0x1800063e5  sub     rsp, 30h
0x1800063e9  test    byte ptr cs:g_dwDebugFlags, 3
0x1800063f0  mov     ebx, r9d
0x1800063f3  mov     r15, r8
0x1800063f6  mov     rbp, rcx
0x1800063f9  jz      short loc_180006428
0x1800063fb  mov     rcx, cs:g_pDebug
0x180006402  lea     rax, aReadfragment; "ReadFragment\n"
0x180006409  lea     r9, aWebsocketConte_4; "WEBSOCKET_CONTEXT::ReadFragment"
0x180006410  mov     [rsp+68h+var_48], rax
0x180006415  mov     r8d, 0FFh
0x18000641b  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180006422  call    cs:__imp_PuDbgPrint
0x180006428  mov     r14, [rsp+68h+arg_48]
0x180006430  xor     edi, edi
0x180006432  test    ebx, ebx
0x180006434  jnz     short loc_180006440
0x180006436  mov     ebx, 80004001h
0x18000643b  jmp     loc_180006640
0x180006440  test    r15, r15
0x180006443  jz      loc_18000663B
0x180006449  cmp     [rsp+68h+arg_20], rdi
0x180006451  jz      loc_18000663B
0x180006457  cmp     [rsp+68h+arg_28], rdi
0x18000645f  jz      loc_18000663B
0x180006465  cmp     [rsp+68h+arg_30], rdi
0x18000646d  jz      loc_18000663B
0x180006473  mov     r13, [rsp+68h+arg_38]
0x18000647b  test    r13, r13
0x18000647e  jz      loc_18000663B
0x180006484  mov     eax, [rbp+174h]
0x18000648a  test    eax, eax
0x18000648c  jz      short loc_180006498
0x18000648e  mov     ebx, 800710DDh
0x180006493  jmp     loc_180006640
0x180006498  lea     rcx, [rbp+188h]; lpCriticalSection
0x18000649f  call    cs:__imp_EnterCriticalSection
0x1800064a5  xor     eax, eax
0x1800064a7  mov     esi, 1
0x1800064ac  lock cmpxchg [rbp+68h], esi
0x1800064b1  jz      short loc_1800064C0
0x1800064b3  mov     r12d, edi
0x1800064b6  mov     ebx, 800703E5h
0x1800064bb  jmp     loc_180006617
0x1800064c0  mov     r9d, [r15]; unsigned int
0x1800064c3  mov     r8d, 10h; unsigned int
0x1800064c9  mov     rdx, [rbp+158h]; struct IHttpContext *
0x1800064d0  call    ?RaiseTraceEventGeneral@TRACE_HELPER@@QEAAXPEAVIHttpContext@@KK@Z; TRACE_HELPER::RaiseTraceEventGeneral(IHttpContext *,ulong,ulong)
0x1800064d5  mov     eax, [rbp+180h]
0x1800064db  mov     r12d, esi
0x1800064de  test    eax, eax
0x1800064e0  jns     short loc_1800064F5
0x1800064e2  mov     ebx, [rbp+180h]
0x1800064e8  test    ebx, ebx
0x1800064ea  jns     loc_18000660D
0x1800064f0  jmp     loc_180006617
0x1800064f5  mov     rsi, [rbp+110h]
0x1800064fc  lea     rcx, [rsi+10h]; lpCriticalSection
0x180006500  call    cs:__imp_EnterCriticalSection
0x180006506  lea     rdi, [rsi+38h]
0x18000650a  mov     rbx, [rdi]
0x18000650d  lea     rcx, [rsi+10h]; lpCriticalSection
0x180006511  call    cs:__imp_LeaveCriticalSection
0x180006517  mov     rdx, [rsp+68h+arg_8]; void *
0x18000651c  cmp     rbx, rdi
0x18000651f  jnz     short loc_18000654E
0x180006521  mov     eax, [r15]
0x180006524  xor     edi, edi
0x180006526  mov     [rbp+40h], eax
0x180006529  mov     rax, [rsp+68h+arg_40]
0x180006531  mov     [rbp+30h], rax
0x180006535  mov     [rbp+38h], rdx
0x180006539  mov     [rbp+28h], r13
0x18000653d  test    r14, r14
0x180006540  jz      loc_18000660D
0x180006546  mov     [r14], r12d
0x180006549  jmp     loc_18000660D
0x18000654e  xor     edi, edi
0x180006550  test    r14, r14
0x180006553  jnz     short loc_1800065B7
0x180006555  mov     eax, [r15]
0x180006558  mov     rcx, rbp; this
0x18000655b  mov     [rbp+40h], eax
0x18000655e  mov     rax, [rsp+68h+arg_40]
0x180006566  mov     [rbp+38h], rdx
0x18000656a  xor     edx, edx; unsigned int
0x18000656c  mov     [rbp+30h], rax
0x180006570  mov     [rbp+28h], r13
0x180006574  call    ?PostCompletion@WEBSOCKET_CONTEXT@@AEAAJK@Z; WEBSOCKET_CONTEXT::PostCompletion(ulong)
0x180006579  mov     ebx, eax
0x18000657b  test    eax, eax
0x18000657d  jns     short loc_180006593
0x18000657f  mov     [rbp+38h], rdi
0x180006583  mov     [rbp+40h], edi
0x180006586  mov     [rbp+28h], rdi
0x18000658a  mov     [rbp+30h], rdi
0x18000658e  jmp     loc_180006617
0x180006593  mov     edx, r12d
0x180006596  lock xadd [rbp+17Ch], edx
0x18000659e  mov     rcx, [rbp+1B0h]
0x1800065a5  inc     edx
0x1800065a7  test    rcx, rcx
0x1800065aa  jz      short loc_18000660D
0x1800065ac  mov     r8, rbp
0x1800065af  call    cs:__imp_WriteRefTraceLog
0x1800065b5  jmp     short loc_18000660D
0x1800065b7  mov     rax, [rsp+68h+arg_30]
0x1800065bf  mov     r8, r15; unsigned int *
0x1800065c2  mov     r9, [rsp+68h+arg_20]; int *
0x1800065ca  mov     rcx, [rbp+110h]; this
0x1800065d1  mov     [rsp+68h+var_40], rax; int *
0x1800065d6  mov     rax, [rsp+68h+arg_28]
0x1800065de  mov     [rsp+68h+var_48], rax; int *
0x1800065e3  call    ?QueryData@RECEIVE_QUEUE@@QEAAXPEAXPEAKPEAH22@Z; RECEIVE_QUEUE::QueryData(void *,ulong *,int *,int *,int *)
0x1800065e8  mov     ecx, edi; this
0x1800065ea  mov     eax, r12d
0x1800065ed  lock cmpxchg [rbp+68h], ecx
0x1800065f2  mov     [r14], edi
0x1800065f5  mov     r8d, 12h; unsigned int
0x1800065fb  mov     r9d, [r15]; unsigned int
0x1800065fe  mov     r12d, edi
0x180006601  mov     rdx, [rbp+158h]; struct IHttpContext *
0x180006608  call    ?RaiseTraceEventGeneral@TRACE_HELPER@@QEAAXPEAVIHttpContext@@KK@Z; TRACE_HELPER::RaiseTraceEventGeneral(IHttpContext *,ulong,ulong)
0x18000660d  mov     rcx, rbp; this
0x180006610  call    ?TryStartReadLoop@WEBSOCKET_CONTEXT@@AEAAJXZ; WEBSOCKET_CONTEXT::TryStartReadLoop(void)
0x180006615  mov     ebx, eax
0x180006617  lea     rcx, [rbp+188h]; lpCriticalSection
0x18000661e  call    cs:__imp_LeaveCriticalSection
0x180006624  test    ebx, ebx
0x180006626  jns     short loc_180006697
0x180006628  test    r12d, r12d
0x18000662b  jz      short loc_180006640
0x18000662d  mov     ecx, edi
0x18000662f  mov     eax, 1
0x180006634  lock cmpxchg [rbp+68h], ecx
0x180006639  jmp     short loc_180006640
0x18000663b  mov     ebx, 80070057h
0x180006640  mov     rdx, [rbp+158h]; struct IHttpContext *
0x180006647  mov     r9d, ebx; int
0x18000664a  mov     r8d, 13h; unsigned int
0x180006650  call    ?RaiseTraceEventError@TRACE_HELPER@@QEAAXPEAVIHttpContext@@KJ@Z; TRACE_HELPER::RaiseTraceEventError(IHttpContext *,ulong,long)
0x180006655  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000665c  jz      short loc_18000668F
0x18000665e  lea     rcx, aError08x; "ERROR = %08x\n"
0x180006665  mov     dword ptr [rsp+68h+var_40], ebx
0x180006669  mov     [rsp+68h+var_48], rcx
0x18000666e  lea     r9, aWebsocketConte_4; "WEBSOCKET_CONTEXT::ReadFragment"
0x180006675  mov     rcx, cs:g_pDebug
0x18000667c  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180006683  mov     r8d, 1BFh
0x180006689  call    cs:__imp_PuDbgPrint
0x18000668f  test    r14, r14
0x180006692  jz      short loc_180006697
0x180006694  mov     [r14], edi
0x180006697  mov     eax, ebx
0x180006699  mov     rbx, [rsp+68h+arg_0]
0x18000669e  add     rsp, 30h
0x1800066a2  pop     r15
0x1800066a4  pop     r14
0x1800066a6  pop     r13
0x1800066a8  pop     r12
0x1800066aa  pop     rdi
0x1800066ab  pop     rsi
0x1800066ac  pop     rbp
0x1800066ad  retn
```
