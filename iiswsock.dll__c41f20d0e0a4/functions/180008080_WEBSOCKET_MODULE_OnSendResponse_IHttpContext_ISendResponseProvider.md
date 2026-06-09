# WEBSOCKET_MODULE::OnSendResponse(IHttpContext *,ISendResponseProvider *)

- ea: `0x180008080`
- end: `0x180008385`
- name: `?OnSendResponse@WEBSOCKET_MODULE@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVISendResponseProvider@@@Z`
- size: `773`
- prototype: `__int64 __fastcall(__int64, struct IHttpContext *, struct ISendResponseProvider *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001008`
- `0x180001048`
- `0x180003180`
- `0x1800033a4`
- `0x180005970`
- `0x180006c98`
- `0x180007850`
- `0x180008080`
- `0x1800085ce`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000830a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000830a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800082a8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800082a8`
- `iisutil!PuDbgPrint` at `0x18000834b`
- `iisutil!PuDbgPrint` at `0x18000834b`

## string_xrefs

- `0x180008332`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\module.cxx`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_MODULE::OnSendResponse(
        __int64 a1,
        struct IHttpContext *a2,
        struct ISendResponseProvider *a3)
{
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rcx
  WEBSOCKET_CONTEXT *v8; // rbx
  int Extended; // eax
  __int64 (__fastcall ***v10)(_QWORD, const wchar_t *); // rax
  WEBSOCKET_CONTEXT *v11; // rax
  WEBSOCKET_CONTEXT *v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 (__fastcall ***v15)(_QWORD, void *); // rax
  _QWORD *v16; // rcx
  __int64 v18; // [rsp+60h] [rbp-10h] BYREF
  wchar_t *String1; // [rsp+68h] [rbp-8h] BYREF
  __int16 v20; // [rsp+98h] [rbp+28h] BYREF
  int v21; // [rsp+A8h] [rbp+38h] BYREF

  v20 = 0;
  v18 = 0;
  (*(void (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
  v5 = *(_QWORD *)a2;
  String1 = 0;
  v21 = 0;
  if ( (*(int (__fastcall **)(struct IHttpContext *, const char *, wchar_t **, int *))(v5 + 128))(
         a2,
         "IIS_WEBSOCK",
         &String1,
         &v21) < 0 )
    return 0;
  if ( wcscmp_0(String1, L"websockets") )
    return 0;
  v6 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
  (*(void (__fastcall **)(__int64, __int16 *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v6 + 184LL))(
    v6,
    &v20,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0);
  if ( v20 != 101 )
    return 0;
  v8 = 0;
  Extended = HttpGetExtendedInterface<IHttpContext,IHttpContext3>(v7, a2, &v18);
  if ( Extended >= 0 )
  {
    v10 = (__int64 (__fastcall ***)(_QWORD, const wchar_t *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 320LL))(v18);
    if ( (**v10)(v10, L"websockets") )
      return 0;
    v11 = (WEBSOCKET_CONTEXT *)operator new(0x1C8u);
    if ( v11 && (v12 = WEBSOCKET_CONTEXT::WEBSOCKET_CONTEXT(v11, a2), (v8 = v12) != 0) )
    {
      Extended = WEBSOCKET_CONTEXT::SendWebSocketHandshake(v12, a3);
      if ( Extended >= 0 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 328LL))(v18);
        v13 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 176LL))(v13);
        v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 320LL))(v18);
        Extended = (*(__int64 (__fastcall **)(__int64, WEBSOCKET_CONTEXT *, const wchar_t *))(*(_QWORD *)v14 + 8LL))(
                     v14,
                     v8,
                     L"websockets");
        if ( Extended >= 0 )
        {
          v15 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 56LL))(a2);
          *(_DWORD *)((**v15)(v15, g_pWebSocketModuleId) + 8) = 1;
          if ( *(_DWORD *)(*((_QWORD *)v8 + 33) + 24LL) )
          {
            AcquireSRWLockExclusive(&WEBSOCKET_PING_MANAGER::sm_RequestsListLock);
            if ( WEBSOCKET_PING_MANAGER::sm_dwInitializationFlags != 2
              && (WEBSOCKET_PING_MANAGER::sm_dwInitializationFlags
               || (int)WEBSOCKET_PING_MANAGER::DelayStart(*(_DWORD *)(*((_QWORD *)v8 + 33) + 24LL)) >= 0) )
            {
              _InterlockedIncrement((volatile signed __int32 *)v8 + 2);
              v16 = (_QWORD *)qword_18000E6C8;
              if ( *(struct _LIST_ENTRY **)qword_18000E6C8 != &WEBSOCKET_PING_MANAGER::sm_trackerListHead )
                __fastfail(3u);
              *((_QWORD *)v8 + 2) = &WEBSOCKET_PING_MANAGER::sm_trackerListHead;
              *((_QWORD *)v8 + 3) = v16;
              *v16 = (char *)v8 + 16;
              qword_18000E6C8 = (__int64)v8 + 16;
            }
            ReleaseSRWLockExclusive(&WEBSOCKET_PING_MANAGER::sm_RequestsListLock);
          }
          return 0;
        }
      }
    }
    else
    {
      Extended = -2147024882;
    }
  }
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\module.cxx",
      479,
      "WEBSOCKET_MODULE::OnSendResponse",
      "ERROR = %08x\n",
      Extended);
  if ( v8 && _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 2, 0xFFFFFFFF) == 1 )
  {
    WEBSOCKET_CONTEXT::~WEBSOCKET_CONTEXT(v8);
    operator delete(v8);
  }
  return 0;
}

```

## disassembly

```asm
0x180008080  mov     [rsp-18h+arg_0], rbx
0x180008085  push    rbp
0x180008086  push    rsi
0x180008087  push    rdi
0x180008088  mov     rbp, rsp
0x18000808b  sub     rsp, 70h
0x18000808f  xor     eax, eax
0x180008091  mov     rcx, rdx
0x180008094  mov     [rbp+arg_8], ax
0x180008098  mov     rsi, r8
0x18000809b  mov     [rbp+var_10], rax
0x18000809f  mov     rdi, rdx
0x1800080a2  mov     rax, [rdx]
0x1800080a5  mov     rax, [rax+18h]
0x1800080a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080ae  mov     rax, [rdi]
0x1800080b1  lea     r9, [rbp+arg_18]
0x1800080b5  lea     r8, [rbp+String1]
0x1800080b9  mov     [rbp+String1], 0
0x1800080c1  lea     rdx, aIisWebsock; "IIS_WEBSOCK"
0x1800080c8  mov     [rbp+arg_18], 0
0x1800080cf  mov     rcx, rdi
0x1800080d2  mov     rax, [rax+80h]
0x1800080d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080de  test    eax, eax
0x1800080e0  js      loc_180008373
0x1800080e6  mov     rcx, [rbp+String1]; String1
0x1800080ea  lea     rdx, aWebsockets; "websockets"
0x1800080f1  call    wcscmp_0
0x1800080f6  test    eax, eax
0x1800080f8  jnz     loc_180008373
0x1800080fe  mov     rax, [rdi]
0x180008101  mov     rcx, rdi
0x180008104  mov     rax, [rax+20h]
0x180008108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000810d  mov     [rsp+70h+var_28], 0
0x180008116  lea     rdx, [rbp+arg_8]
0x18000811a  mov     [rsp+70h+var_30], 0
0x180008123  mov     r10, rax
0x180008126  mov     [rsp+70h+var_38], 0
0x18000812f  xor     r9d, r9d
0x180008132  mov     rcx, [rax]
0x180008135  xor     r8d, r8d
0x180008138  mov     [rsp+70h+var_40], 0
0x180008141  mov     [rsp+70h+var_48], 0
0x18000814a  mov     [rsp+70h+var_50], 0
0x180008153  mov     rax, [rcx+0B8h]
0x18000815a  mov     rcx, r10
0x18000815d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008162  cmp     [rbp+arg_8], 65h ; 'e'
0x180008167  jnz     loc_180008373
0x18000816d  lea     r8, [rbp+var_10]
0x180008171  mov     rdx, rdi
0x180008174  xor     ebx, ebx
0x180008176  call    ??$HttpGetExtendedInterface@VIHttpContext@@VIHttpContext3@@@@YAJPEAVIHttpServer@@PEAVIHttpContext@@PEAPEAVIHttpContext3@@@Z; HttpGetExtendedInterface<IHttpContext,IHttpContext3>(IHttpServer *,IHttpContext *,IHttpContext3 * *)
0x18000817b  test    eax, eax
0x18000817d  js      loc_180008317
0x180008183  mov     rcx, [rbp+var_10]
0x180008187  mov     rax, [rcx]
0x18000818a  mov     rax, [rax+140h]
0x180008191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008196  mov     r8, rax
0x180008199  lea     rdx, aWebsockets; "websockets"
0x1800081a0  mov     rcx, [rax]
0x1800081a3  mov     rax, [rcx]
0x1800081a6  mov     rcx, r8
0x1800081a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081ae  test    rax, rax
0x1800081b1  jnz     loc_180008373
0x1800081b7  mov     ecx, 1C8h; Size
0x1800081bc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800081c1  test    rax, rax
0x1800081c4  jz      loc_180008312
0x1800081ca  mov     rdx, rdi; struct IHttpContext *
0x1800081cd  mov     rcx, rax; this
0x1800081d0  call    ??0WEBSOCKET_CONTEXT@@QEAA@PEAVIHttpContext@@@Z; WEBSOCKET_CONTEXT::WEBSOCKET_CONTEXT(IHttpContext *)
0x1800081d5  mov     rbx, rax
0x1800081d8  test    rax, rax
0x1800081db  jz      loc_180008312
0x1800081e1  mov     rdx, rsi; struct ISendResponseProvider *
0x1800081e4  mov     rcx, rax; this
0x1800081e7  call    ?SendWebSocketHandshake@WEBSOCKET_CONTEXT@@QEAAJPEAVISendResponseProvider@@@Z; WEBSOCKET_CONTEXT::SendWebSocketHandshake(ISendResponseProvider *)
0x1800081ec  test    eax, eax
0x1800081ee  js      loc_180008317
0x1800081f4  mov     rcx, [rbp+var_10]
0x1800081f8  mov     rax, [rcx]
0x1800081fb  mov     rax, [rax+148h]
0x180008202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008207  mov     rax, [rdi]
0x18000820a  mov     rcx, rdi
0x18000820d  mov     rax, [rax+20h]
0x180008211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008216  mov     rdx, rax
0x180008219  mov     rcx, [rax]
0x18000821c  mov     rax, [rcx+0B0h]
0x180008223  mov     rcx, rdx
0x180008226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000822b  mov     rcx, [rbp+var_10]
0x18000822f  mov     rax, [rcx]
0x180008232  mov     rax, [rax+140h]
0x180008239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000823e  mov     r9, rax
0x180008241  lea     r8, aWebsockets; "websockets"
0x180008248  mov     rdx, rbx
0x18000824b  mov     rcx, [rax]
0x18000824e  mov     rax, [rcx+8]
0x180008252  mov     rcx, r9
0x180008255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000825a  test    eax, eax
0x18000825c  js      loc_180008317
0x180008262  mov     rax, [rdi]
0x180008265  mov     rcx, rdi
0x180008268  mov     rax, [rax+38h]
0x18000826c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008271  mov     rdx, cs:?g_pWebSocketModuleId@@3PEAXEA; void * g_pWebSocketModuleId
0x180008278  mov     r8, rax
0x18000827b  mov     rcx, [rax]
0x18000827e  mov     rax, [rcx]
0x180008281  mov     rcx, r8
0x180008284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008289  mov     dword ptr [rax+8], 1
0x180008290  mov     rax, [rbx+108h]
0x180008297  cmp     dword ptr [rax+18h], 0
0x18000829b  jbe     loc_180008373
0x1800082a1  lea     rcx, ?sm_RequestsListLock@WEBSOCKET_PING_MANAGER@@2U_RTL_SRWLOCK@@A; SRWLock
0x1800082a8  call    cs:__imp_AcquireSRWLockExclusive
0x1800082ae  mov     eax, cs:?sm_dwInitializationFlags@WEBSOCKET_PING_MANAGER@@0W4PingManagerInitializationFlags@@A; PingManagerInitializationFlags WEBSOCKET_PING_MANAGER::sm_dwInitializationFlags
0x1800082b4  cmp     eax, 2
0x1800082b7  jz      short loc_180008303
0x1800082b9  test    eax, eax
0x1800082bb  jnz     short loc_1800082D0
0x1800082bd  mov     rcx, [rbx+108h]
0x1800082c4  mov     ecx, [rcx+18h]; msPeriod
0x1800082c7  call    ?DelayStart@WEBSOCKET_PING_MANAGER@@CAJK@Z; WEBSOCKET_PING_MANAGER::DelayStart(ulong)
0x1800082cc  test    eax, eax
0x1800082ce  js      short loc_180008303
0x1800082d0  lock inc dword ptr [rbx+8]
0x1800082d4  mov     rcx, cs:qword_18000E6C8
0x1800082db  lea     rdx, ?sm_trackerListHead@WEBSOCKET_PING_MANAGER@@2U_LIST_ENTRY@@A; _LIST_ENTRY WEBSOCKET_PING_MANAGER::sm_trackerListHead
0x1800082e2  cmp     [rcx], rdx
0x1800082e5  jz      short loc_1800082EE
0x1800082e7  mov     ecx, 3
0x1800082ec  int     29h; Win8: RtlFailFast(ecx)
0x1800082ee  lea     rax, [rbx+10h]
0x1800082f2  mov     [rax], rdx
0x1800082f5  mov     [rax+8], rcx
0x1800082f9  mov     [rcx], rax
0x1800082fc  mov     cs:qword_18000E6C8, rax
0x180008303  lea     rcx, ?sm_RequestsListLock@WEBSOCKET_PING_MANAGER@@2U_RTL_SRWLOCK@@A; SRWLock
0x18000830a  call    cs:__imp_ReleaseSRWLockExclusive
0x180008310  jmp     short loc_180008373
0x180008312  mov     eax, 8007000Eh
0x180008317  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000831e  jz      short loc_180008351
0x180008320  mov     rcx, cs:g_pDebug
0x180008327  lea     r9, aWebsocketModul; "WEBSOCKET_MODULE::OnSendResponse"
0x18000832e  mov     dword ptr [rsp+70h+var_48], eax
0x180008332  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008339  lea     rax, aError08x; "ERROR = %08x\n"
0x180008340  mov     r8d, 1DFh
0x180008346  mov     [rsp+70h+var_50], rax
0x18000834b  call    cs:__imp_PuDbgPrint
0x180008351  test    rbx, rbx
0x180008354  jz      short loc_180008373
0x180008356  or      eax, 0FFFFFFFFh
0x180008359  lock xadd [rbx+8], eax
0x18000835e  cmp     eax, 1
0x180008361  jnz     short loc_180008373
0x180008363  mov     rcx, rbx; this
0x180008366  call    ??1WEBSOCKET_CONTEXT@@QEAA@XZ; WEBSOCKET_CONTEXT::~WEBSOCKET_CONTEXT(void)
0x18000836b  mov     rcx, rbx; Block
0x18000836e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008373  mov     rbx, [rsp+70h+arg_0]
0x18000837b  xor     eax, eax
0x18000837d  add     rsp, 70h
0x180008381  pop     rdi
0x180008382  pop     rsi
0x180008383  pop     rbp
0x180008384  retn
```
