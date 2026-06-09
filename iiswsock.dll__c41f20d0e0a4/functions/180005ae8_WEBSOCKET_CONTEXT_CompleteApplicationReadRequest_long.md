# WEBSOCKET_CONTEXT::CompleteApplicationReadRequest(long)

- ea: `0x180005ae8`
- end: `0x180005cb0`
- name: `?CompleteApplicationReadRequest@WEBSOCKET_CONTEXT@@AEAAJJ@Z`
- size: `456`
- prototype: `__int64 __fastcall(WEBSOCKET_CONTEXT *this, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180005d88`
- `0x180005ed0`

## callees

- `0x180002168`
- `0x180002500`
- `0x1800042e0`
- `0x180005ae8`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005b8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005b9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005c38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005b8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005b9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005c38`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005b53`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005b7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005b53`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005b7d`
- `iisutil!PuDbgPrint` at `0x180005b43`
- `iisutil!PuDbgPrint` at `0x180005c90`
- `iisutil!PuDbgPrint` at `0x180005b43`
- `iisutil!PuDbgPrint` at `0x180005c90`

## string_xrefs

- `0x180005b3c`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\websocketcontext.cxx`
- `0x180005c89`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\websocketcontext.cxx`
- `0x180005b23`: `Completing Application Read Request\n`
- `0x180005b2a`: `WEBSOCKET_CONTEXT::CompleteApplicationReadRequest`
- `0x180005c77`: `WEBSOCKET_CONTEXT::CompleteApplicationReadRequest`
- `0x180005c70`: `Completed Application Read Request\n`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_CONTEXT::CompleteApplicationReadRequest(WEBSOCKET_CONTEXT *this, int a2)
{
  unsigned int v2; // ebx
  unsigned int v5; // r13d
  TRACE_HELPER *v6; // rcx
  __int64 v7; // rdi
  __int64 v8; // rbx
  void (__fastcall *v9)(_QWORD, __int64, _QWORD, _QWORD, int, int); // rsi
  __int64 v10; // rdi
  char *v11; // rdx
  TRACE_HELPER *v12; // rcx
  int v14[4]; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v15; // [rsp+90h] [rbp+40h] BYREF
  int v16; // [rsp+A0h] [rbp+50h] BYREF
  int v17; // [rsp+A8h] [rbp+58h] BYREF

  v2 = 0;
  v5 = 0;
  v16 = 0;
  v14[0] = 0;
  v17 = 0;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\websocketcontext.cxx",
      1121,
      "WEBSOCKET_CONTEXT::CompleteApplicationReadRequest",
      "Completing Application Read Request\n");
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 392));
  if ( !*((_DWORD *)this + 26) )
  {
    if ( a2 < 0 )
      *((_DWORD *)this + 96) = a2;
    goto LABEL_8;
  }
  if ( a2 < 0 )
  {
LABEL_10:
    v9 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD, int, int))*((_QWORD *)this + 5);
    v10 = *((_QWORD *)this + 6);
    v11 = (char *)*((_QWORD *)this + 7);
    v15 = *((_DWORD *)this + 16);
    *((_QWORD *)this + 7) = 0;
    *((_DWORD *)this + 16) = 0;
    *((_QWORD *)this + 5) = 0;
    *((_QWORD *)this + 6) = 0;
    if ( a2 >= 0 )
    {
      RECEIVE_QUEUE::QueryData(*((RECEIVE_QUEUE **)this + 34), v11, &v15, &v16, v14, &v17);
      v2 = v15;
      TRACE_HELPER::RaiseTraceEventGeneral(v12, *((struct IHttpContext **)this + 43), 0x12u, v15);
      v5 = v16;
    }
    else
    {
      TRACE_HELPER::RaiseTraceEventError(v6, *((struct IHttpContext **)this + 43), 0x13u, a2);
    }
    _InterlockedCompareExchange((volatile signed __int32 *)this + 26, 0, 1);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 392));
    v9((unsigned int)a2, v10, v2, v5, v14[0], v17);
    goto LABEL_14;
  }
  v7 = *((_QWORD *)this + 34);
  EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 16));
  v8 = *(_QWORD *)(v7 + 56);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 16));
  if ( v8 != v7 + 56 )
  {
    v2 = 0;
    goto LABEL_10;
  }
LABEL_8:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 392));
LABEL_14:
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\websocketcontext.cxx",
      1250,
      "WEBSOCKET_CONTEXT::CompleteApplicationReadRequest",
      "Completed Application Read Request\n");
  return 0;
}

```

## disassembly

```asm
0x180005ae8  mov     [rsp-38h+arg_8], rbx
0x180005aed  push    rbp
0x180005aee  push    rsi
0x180005aef  push    rdi
0x180005af0  push    r12
0x180005af2  push    r13
0x180005af4  push    r14
0x180005af6  push    r15
0x180005af8  mov     rbp, rsp
0x180005afb  sub     rsp, 50h
0x180005aff  xor     ebx, ebx
0x180005b01  mov     r15d, edx
0x180005b04  test    byte ptr cs:g_dwDebugFlags, 3
0x180005b0b  mov     r14, rcx
0x180005b0e  mov     r13d, ebx
0x180005b11  mov     [rbp+arg_10], ebx
0x180005b14  mov     [rbp+var_10], ebx
0x180005b17  mov     [rbp+arg_18], ebx
0x180005b1a  jz      short loc_180005B49
0x180005b1c  mov     rcx, cs:g_pDebug
0x180005b23  lea     rax, aCompletingAppl; "Completing Application Read Request\n"
0x180005b2a  lea     r9, aWebsocketConte_3; "WEBSOCKET_CONTEXT::CompleteApplicationR"...
0x180005b31  mov     [rsp+50h+var_30], rax
0x180005b36  mov     r8d, 461h
0x180005b3c  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005b43  call    cs:__imp_PuDbgPrint
0x180005b49  lea     r12, [r14+188h]
0x180005b50  mov     rcx, r12; lpCriticalSection
0x180005b53  call    cs:__imp_EnterCriticalSection
0x180005b59  cmp     [r14+68h], ebx
0x180005b5d  jnz     short loc_180005B6D
0x180005b5f  test    r15d, r15d
0x180005b62  jns     short loc_180005B99
0x180005b64  mov     [r14+180h], r15d
0x180005b6b  jmp     short loc_180005B99
0x180005b6d  test    r15d, r15d
0x180005b70  js      short loc_180005BA9
0x180005b72  mov     rdi, [r14+110h]
0x180005b79  lea     rcx, [rdi+10h]; lpCriticalSection
0x180005b7d  call    cs:__imp_EnterCriticalSection
0x180005b83  lea     rsi, [rdi+38h]
0x180005b87  mov     rbx, [rsi]
0x180005b8a  lea     rcx, [rdi+10h]; lpCriticalSection
0x180005b8e  call    cs:__imp_LeaveCriticalSection
0x180005b94  cmp     rbx, rsi
0x180005b97  jnz     short loc_180005BA7
0x180005b99  mov     rcx, r12; lpCriticalSection
0x180005b9c  call    cs:__imp_LeaveCriticalSection
0x180005ba2  jmp     loc_180005C60
0x180005ba7  xor     ebx, ebx
0x180005ba9  mov     eax, [r14+40h]
0x180005bad  mov     rsi, [r14+28h]
0x180005bb1  mov     rdi, [r14+30h]
0x180005bb5  mov     rdx, [r14+38h]; void *
0x180005bb9  mov     [rbp+arg_0], eax
0x180005bbc  mov     [r14+38h], rbx
0x180005bc0  mov     [r14+40h], ebx
0x180005bc4  mov     [r14+28h], rbx
0x180005bc8  mov     [r14+30h], rbx
0x180005bcc  test    r15d, r15d
0x180005bcf  jns     short loc_180005BE8
0x180005bd1  mov     rdx, [r14+158h]; struct IHttpContext *
0x180005bd8  mov     r9d, r15d; int
0x180005bdb  mov     r8d, 13h; unsigned int
0x180005be1  call    ?RaiseTraceEventError@TRACE_HELPER@@QEAAXPEAVIHttpContext@@KJ@Z; TRACE_HELPER::RaiseTraceEventError(IHttpContext *,ulong,long)
0x180005be6  jmp     short loc_180005C2A
0x180005be8  mov     rcx, [r14+110h]; this
0x180005bef  lea     rax, [rbp+arg_18]
0x180005bf3  mov     [rsp+50h+var_28], rax; int *
0x180005bf8  lea     r9, [rbp+arg_10]; int *
0x180005bfc  lea     rax, [rbp+var_10]
0x180005c00  lea     r8, [rbp+arg_0]; unsigned int *
0x180005c04  mov     [rsp+50h+var_30], rax; int *
0x180005c09  call    ?QueryData@RECEIVE_QUEUE@@QEAAXPEAXPEAKPEAH22@Z; RECEIVE_QUEUE::QueryData(void *,ulong *,int *,int *,int *)
0x180005c0e  mov     ebx, [rbp+arg_0]
0x180005c11  mov     r8d, 12h; unsigned int
0x180005c17  mov     rdx, [r14+158h]; struct IHttpContext *
0x180005c1e  mov     r9d, ebx; unsigned int
0x180005c21  call    ?RaiseTraceEventGeneral@TRACE_HELPER@@QEAAXPEAVIHttpContext@@KK@Z; TRACE_HELPER::RaiseTraceEventGeneral(IHttpContext *,ulong,ulong)
0x180005c26  mov     r13d, [rbp+arg_10]
0x180005c2a  xor     ecx, ecx
0x180005c2c  lea     eax, [rcx+1]
0x180005c2f  lock cmpxchg [r14+68h], ecx
0x180005c35  mov     rcx, r12; lpCriticalSection
0x180005c38  call    cs:__imp_LeaveCriticalSection
0x180005c3e  mov     ecx, [rbp+arg_18]
0x180005c41  mov     r9d, r13d
0x180005c44  mov     dword ptr [rsp+50h+var_28], ecx
0x180005c48  mov     r8d, ebx
0x180005c4b  mov     ecx, [rbp+var_10]
0x180005c4e  mov     rdx, rdi
0x180005c51  mov     dword ptr [rsp+50h+var_30], ecx
0x180005c55  mov     rax, rsi
0x180005c58  mov     ecx, r15d
0x180005c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c60  test    byte ptr cs:g_dwDebugFlags, 3
0x180005c67  jz      short loc_180005C96
0x180005c69  mov     rcx, cs:g_pDebug
0x180005c70  lea     rax, aCompletedAppli; "Completed Application Read Request\n"
0x180005c77  lea     r9, aWebsocketConte_3; "WEBSOCKET_CONTEXT::CompleteApplicationR"...
0x180005c7e  mov     [rsp+50h+var_30], rax
0x180005c83  mov     r8d, 4E2h
0x180005c89  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005c90  call    cs:__imp_PuDbgPrint
0x180005c96  mov     rbx, [rsp+50h+arg_8]
0x180005c9e  xor     eax, eax
0x180005ca0  add     rsp, 50h
0x180005ca4  pop     r15
0x180005ca6  pop     r14
0x180005ca8  pop     r13
0x180005caa  pop     r12
0x180005cac  pop     rdi
0x180005cad  pop     rsi
0x180005cae  pop     rbp
0x180005caf  retn
```
