# CConnectivityWatcher::WaitForConnectivity(ulong,ulong)

- ea: `0x1800a6ba0`
- end: `0x1800a71d5`
- name: `?WaitForConnectivity@CConnectivityWatcher@@UEAAKKK@Z`
- size: `1589`
- prototype: `unsigned int __fastcall(CConnectivityWatcher *__hidden this, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x18000a52c`
- `0x180039148`
- `0x1800585e8`
- `0x180074774`
- `0x180075ec0`
- `0x18007d770`
- `0x1800a5aa0`
- `0x1800a66a4`
- `0x1800a6ba0`
- `0x1800a7270`
- `0x1800b42f8`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a6c31`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a6c31`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800a6fd3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800a6fd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6c49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6c49`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a6f66`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a6f66`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800a6cf6`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800a6cf6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800a6f5b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800a7167`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800a6f5b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800a7167`

## string_xrefs

- `0x1800a6c69`: `CConnectivityWatcher::WaitForConnectivity: Failed to create the connectivity signal event, Error : %d.`
- `0x1800a6c91`: `CConnectivityWatcher::WaitForConnectivity: Failed to create the connectivity signal event, Error : %d.`
- `0x1800a6cc0`: `CConnectivityWatcher::WaitForConnectivity: Created the connectivity signal event.`
- `0x1800a6ce3`: `CConnectivityWatcher::WaitForConnectivity: Created the connectivity signal event.`
- `0x1800a6d89`: `CConnectivityWatcher::WaitForConnectivity: Created the network sink object successfully.`
- `0x1800a6dac`: `CConnectivityWatcher::WaitForConnectivity: Created the network sink object successfully.`
- `0x1800a7042`: `CConnectivityWatcher::WaitForConnectivity: Completed WaitForSingleObject.`
- `0x1800a7070`: `CConnectivityWatcher::WaitForConnectivity: Completed WaitForSingleObject.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CConnectivityWatcher::WaitForConnectivity(
        int (**this)(struct CNetworkEventSink *, struct _GUID *__struct_ptr),
        unsigned int a2,
        DWORD a3)
{
  HANDLE EventW; // rax
  DWORD LastError; // esi
  HRESULT Instance; // ebx
  struct IUnknown *v8; // rax
  struct IUnknown *v9; // rax
  struct IUnknown *v10; // rbx
  const struct _GUID *v11; // rdx
  void (*v12)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v13; // rdx
  const unsigned __int16 *v14; // rdx
  DWORD TickCount; // eax
  __int64 v16; // r8
  DWORD dwMilliseconds; // [rsp+20h] [rbp-30h] BYREF
  unsigned int v19; // [rsp+24h] [rbp-2Ch] BYREF
  HANDLE hHandle; // [rsp+28h] [rbp-28h] BYREF
  struct IConnectionPoint *v21; // [rsp+30h] [rbp-20h] BYREF
  __int64 v22; // [rsp+38h] [rbp-18h] BYREF
  struct IUnknown *v23[2]; // [rsp+40h] [rbp-10h] BYREF
  NLMConnectionManager *v24; // [rsp+98h] [rbp+48h] BYREF

  v21 = 0;
  v23[0] = 0;
  v22 = 0;
  v19 = 0;
  dwMilliseconds = a3;
  hHandle = 0;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CConnectivityWatcher::WaitForConnectivity: Prior to creating the connectivity signal event.");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(
        4u,
        L"CConnectivityWatcher::WaitForConnectivity: Prior to creating the connectivity signal event.");
    }
  }
  EventW = CreateEventW(0, 0, 0, 0);
  XHandle::operator=(&hHandle, EventW);
  if ( !hHandle )
  {
    LastError = GetLastError();
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(
          2u,
          L"CConnectivityWatcher::WaitForConnectivity: Failed to create the connectivity signal event, Error : %d.",
          LastError);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(
          2u,
          L"CConnectivityWatcher::WaitForConnectivity: Failed to create the connectivity signal event, Error : %d.",
          LastError);
      }
    }
    goto LABEL_112;
  }
  LastError = 0;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CConnectivityWatcher::WaitForConnectivity: Created the connectivity signal event.");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CConnectivityWatcher::WaitForConnectivity: Created the connectivity signal event.");
    }
  }
  Instance = CoInitializeEx(0, 0);
  if ( Instance < 0 )
    goto LABEL_110;
  v24 = 0;
  Instance = NLMConnectionManager::GetInstance(&v24);
  if ( Instance >= 0 )
  {
    v8 = (struct IUnknown *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
    v23[1] = v8;
    if ( !v8
      || (v9 = (struct IUnknown *)CNetworkEventSink::CNetworkEventSink((CNetworkEventSink *)v8, hHandle, this[4], this)) == 0
      || (ATL::AtlComPtrAssign(v23, v9), (v10 = v23[0]) == 0) )
    {
      Instance = -2147024882;
      goto LABEL_107;
    }
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CConnectivityWatcher::WaitForConnectivity: Created the network sink object successfully.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(
          4u,
          L"CConnectivityWatcher::WaitForConnectivity: Created the network sink object successfully.");
      }
    }
    Instance = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v10->lpVtbl->QueryInterface)(
                 v10,
                 &IID_IUnknown,
                 &v22);
    if ( Instance < 0 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v12 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v13 = L"QI on CNetworkEventSink failed, hr = %#x\n";
          goto LABEL_93;
        }
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v14 = L"QI on CNetworkEventSink failed, hr = %#x\n";
          goto LABEL_104;
        }
      }
    }
    else
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"CConnectivityWatcher::WaitForConnectivity: Queried the network sink object successfully.");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(
            4u,
            L"CConnectivityWatcher::WaitForConnectivity: Queried the network sink object successfully.");
        }
      }
      Instance = NLMConnectionManager::GetConnectionPoints(v24, v11, &v21);
      if ( Instance < 0 )
      {
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_107;
        v12 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v13 = L"Failed to retrieve INetworkEvents connection point from INetworkListManager, hr = %#x\n";
          goto LABEL_93;
        }
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v14 = L"Failed to retrieve INetworkEvents connection point from INetworkListManager, hr = %#x\n";
          goto LABEL_104;
        }
      }
      else
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(
              4u,
              L"CConnectivityWatcher::WaitForConnectivity: Retrieved the connection points successfully.");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(
              4u,
              L"CConnectivityWatcher::WaitForConnectivity: Retrieved the connection points successfully.");
          }
        }
        Instance = ((__int64 (__fastcall *)(struct IConnectionPoint *, __int64, unsigned int *))v21->lpVtbl->Advise)(
                     v21,
                     v22,
                     &v19);
        if ( Instance >= 0 )
        {
          LODWORD(v24) = 0;
          LastError = (*((__int64 (__fastcall **)(int (**)(struct CNetworkEventSink *, struct _GUID *__struct_ptr), NLMConnectionManager **))*this
                       + 1))(
                        this,
                        &v24);
          if ( !LastError )
          {
            if ( (_DWORD)v24 == 1 )
            {
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                if ( g_lpDebugMsg )
                {
                  g_lpDebugMsg(
                    4u,
                    L"CConnectivityWatcher::WaitForConnectivity: HaveConnectivity returned TRUE for connectivity check");
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  RedirectDebugMsg(
                    4u,
                    L"CConnectivityWatcher::WaitForConnectivity: HaveConnectivity returned TRUE for connectivity check");
                }
              }
            }
            else
            {
              TickCount = GetTickCount();
              if ( !CalculateTimeLeftToWait(a2, TickCount, &dwMilliseconds) )
              {
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( g_lpDebugMsg )
                  {
                    g_lpDebugMsg(4u, L"CConnectivityWatcher::WaitForConnectivity: Beginning WaitForSingleObject.");
                  }
                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    RedirectDebugMsg(4u, L"CConnectivityWatcher::WaitForConnectivity: Beginning WaitForSingleObject.");
                  }
                }
                LastError = WaitForSingleObject(hHandle, dwMilliseconds);
                if ( !LastError )
                {
                  if ( *(_DWORD *)&g_dwDebugLevel )
                  {
                    if ( g_lpDebugMsg )
                    {
                      g_lpDebugMsg(
                        4u,
                        L"CConnectivityWatcher::WaitForConnectivity: WaitForSingleObject returned with WAIT_OBJECT_0");
                    }
                    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                    {
                      RedirectDebugMsg(
                        4u,
                        L"CConnectivityWatcher::WaitForConnectivity: WaitForSingleObject returned with WAIT_OBJECT_0");
                    }
                  }
                  LastError = 0;
                }
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( g_lpDebugMsg )
                  {
                    g_lpDebugMsg(4u, L"CConnectivityWatcher::WaitForConnectivity: Completed WaitForSingleObject.");
                  }
                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    RedirectDebugMsg(4u, L"CConnectivityWatcher::WaitForConnectivity: Completed WaitForSingleObject.");
                  }
                }
                goto LABEL_107;
              }
              LastError = 258;
            }
            CoUninitialize();
            goto LABEL_108;
          }
          if ( !*(_DWORD *)&g_dwDebugLevel )
            goto LABEL_107;
          v12 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            v16 = LastError;
            v13 = L"CConnectivityWatcher::WaitForConnectivity: HaveConnectivity failed with 0x%x\n";
LABEL_94:
            v12(2u, v13, v16);
            goto LABEL_107;
          }
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            RedirectDebugMsg(
              2u,
              L"CConnectivityWatcher::WaitForConnectivity: HaveConnectivity failed with 0x%x\n",
              LastError);
        }
        else
        {
          if ( !*(_DWORD *)&g_dwDebugLevel )
            goto LABEL_107;
          v12 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            v13 = L"INetworkEvents::Advise failed, hr = %#x\n";
LABEL_93:
            v16 = (unsigned int)Instance;
            goto LABEL_94;
          }
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            v14 = L"INetworkEvents::Advise failed, hr = %#x\n";
LABEL_104:
            RedirectDebugMsg(2u, v14, (unsigned int)Instance);
          }
        }
      }
    }
  }
LABEL_107:
  CoUninitialize();
  if ( Instance >= 0 )
  {
LABEL_108:
    if ( v21 )
      ((void (__fastcall *)(struct IConnectionPoint *, _QWORD))v21->lpVtbl->Unadvise)(v21, v19);
  }
LABEL_110:
  if ( Instance < 0 )
    LastError = (unsigned __int16)Instance;
LABEL_112:
  XHandle::~XHandle(&hHandle);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)v23);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v21);
  return LastError;
}

```

## disassembly

```asm
0x1800a6ba0  mov     [rsp-28h+arg_0], rbx
0x1800a6ba5  mov     [rsp-28h+arg_8], rsi
0x1800a6baa  push    rbp
0x1800a6bab  push    r12
0x1800a6bad  push    r13
0x1800a6baf  push    r14
0x1800a6bb1  push    r15
0x1800a6bb3  mov     rbp, rsp
0x1800a6bb6  sub     rsp, 50h
0x1800a6bba  mov     r15d, edx
0x1800a6bbd  mov     r14, rcx
0x1800a6bc0  xor     r12d, r12d
0x1800a6bc3  mov     [rbp+var_20], r12
0x1800a6bc7  mov     [rbp+var_10], r12
0x1800a6bcb  mov     [rbp+var_18], r12
0x1800a6bcf  mov     [rbp+var_2C], r12d
0x1800a6bd3  mov     [rbp+dwMilliseconds], r8d
0x1800a6bd7  mov     [rbp+hHandle], r12
0x1800a6bdb  lea     r13d, [r12+4]
0x1800a6be0  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a6be7  jz      short loc_1800A6C27
0x1800a6be9  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a6bf0  test    rax, rax
0x1800a6bf3  jz      short loc_1800A6C06
0x1800a6bf5  lea     rdx, aCconnectivityw_8; "CConnectivityWatcher::WaitForConnectivi"...
0x1800a6bfc  mov     ecx, r13d
0x1800a6bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6c04  jmp     short loc_1800A6C27
0x1800a6c06  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a6c0d  jz      short loc_1800A6C27
0x1800a6c0f  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a6c16  jz      short loc_1800A6C27
0x1800a6c18  lea     rdx, aCconnectivityw_8; "CConnectivityWatcher::WaitForConnectivi"...
0x1800a6c1f  mov     ecx, r13d; unsigned int
0x1800a6c22  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800a6c27  xor     r9d, r9d; lpName
0x1800a6c2a  xor     r8d, r8d; bInitialState
0x1800a6c2d  xor     edx, edx; bManualReset
0x1800a6c2f  xor     ecx, ecx; lpEventAttributes
0x1800a6c31  call    cs:__imp_CreateEventW
0x1800a6c37  mov     rdx, rax
0x1800a6c3a  lea     rcx, [rbp+hHandle]
0x1800a6c3e  call    ??4XHandle@@QEAAXPEAX@Z; XHandle::operator=(void *)
0x1800a6c43  cmp     [rbp+hHandle], r12
0x1800a6c47  jnz     short loc_1800A6CA8
0x1800a6c49  call    cs:__imp_GetLastError
0x1800a6c4f  mov     esi, eax
0x1800a6c51  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a6c58  jz      short loc_1800A6CA3
0x1800a6c5a  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a6c61  test    rax, rax
0x1800a6c64  jz      short loc_1800A6C7C
0x1800a6c66  mov     r8d, esi
0x1800a6c69  lea     rdx, aCconnectivityw_4; "CConnectivityWatcher::WaitForConnectivi"...
0x1800a6c70  mov     ecx, 2
0x1800a6c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6c7a  jmp     short loc_1800A6CA3
0x1800a6c7c  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a6c83  jz      short loc_1800A6CA3
0x1800a6c85  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a6c8c  jz      short loc_1800A6CA3
0x1800a6c8e  mov     r8d, esi
0x1800a6c91  lea     rdx, aCconnectivityw_4; "CConnectivityWatcher::WaitForConnectivi"...
0x1800a6c98  mov     ecx, 2; unsigned int
0x1800a6c9d  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800a6ca2  nop
0x1800a6ca3  jmp     loc_1800A7192
0x1800a6ca8  mov     esi, r12d
0x1800a6cab  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a6cb2  jz      short loc_1800A6CF2
0x1800a6cb4  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a6cbb  test    rax, rax
0x1800a6cbe  jz      short loc_1800A6CD1
0x1800a6cc0  lea     rdx, aCconnectivityw_9; "CConnectivityWatcher::WaitForConnectivi"...
0x1800a6cc7  mov     ecx, r13d
0x1800a6cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6ccf  jmp     short loc_1800A6CF2
0x1800a6cd1  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a6cd8  jz      short loc_1800A6CF2
0x1800a6cda  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a6ce1  jz      short loc_1800A6CF2
0x1800a6ce3  lea     rdx, aCconnectivityw_9; "CConnectivityWatcher::WaitForConnectivi"...
0x1800a6cea  mov     ecx, r13d; unsigned int
0x1800a6ced  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800a6cf2  xor     edx, edx; dwCoInit
0x1800a6cf4  xor     ecx, ecx; pvReserved
0x1800a6cf6  call    cs:__imp_CoInitializeEx
0x1800a6cfc  mov     ebx, eax
0x1800a6cfe  test    eax, eax
0x1800a6d00  js      loc_1800A718A
0x1800a6d06  mov     [rbp+arg_10], 1
0x1800a6d0a  mov     [rbp+arg_18], r12
0x1800a6d0e  lea     rcx, [rbp+arg_18]; struct NLMConnectionManager **
0x1800a6d12  call    ?GetInstance@NLMConnectionManager@@SAJPEAPEAV1@@Z; NLMConnectionManager::GetInstance(NLMConnectionManager * *)
0x1800a6d17  mov     ebx, eax
0x1800a6d19  test    eax, eax
0x1800a6d1b  js      loc_1800A7167
0x1800a6d21  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a6d28  mov     ecx, 28h ; '('; unsigned __int64
0x1800a6d2d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800a6d32  mov     [rbp+var_8], rax
0x1800a6d36  test    rax, rax
0x1800a6d39  jz      loc_1800A7162
0x1800a6d3f  mov     r9, r14; void *
0x1800a6d42  mov     r8, [r14+20h]; int (*)(struct CNetworkEventSink *, struct _GUID *__struct_ptr)
0x1800a6d46  mov     rdx, [rbp+hHandle]; void *
0x1800a6d4a  mov     rcx, rax; this
0x1800a6d4d  call    ??0CNetworkEventSink@@QEAA@PEAXP6AJPEAV0@U_GUID@@@Z0@Z; CNetworkEventSink::CNetworkEventSink(void *,long (*)(CNetworkEventSink *,_GUID),void *)
0x1800a6d52  test    rax, rax
0x1800a6d55  jz      loc_1800A7162
0x1800a6d5b  mov     rdx, rax; struct IUnknown *
0x1800a6d5e  lea     rcx, [rbp+var_10]; struct IUnknown **
0x1800a6d62  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800a6d67  mov     rbx, [rbp+var_10]
0x1800a6d6b  test    rbx, rbx
0x1800a6d6e  jz      loc_1800A7162
0x1800a6d74  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a6d7b  jz      short loc_1800A6DBB
0x1800a6d7d  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a6d84  test    rax, rax
0x1800a6d87  jz      short loc_1800A6D9A
0x1800a6d89  lea     rdx, aCconnectivityw_0; "CConnectivityWatcher::WaitForConnectivi"...
0x1800a6d90  mov     ecx, r13d
0x1800a6d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6d98  jmp     short loc_1800A6DBB
0x1800a6d9a  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a6da1  jz      short loc_1800A6DBB
0x1800a6da3  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a6daa  jz      short loc_1800A6DBB
0x1800a6dac  lea     rdx, aCconnectivityw_0; "CConnectivityWatcher::WaitForConnectivi"...
0x1800a6db3  mov     ecx, r13d; unsigned int
0x1800a6db6  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800a6dbb  mov     rax, [rbx]
0x1800a6dbe  lea     r8, [rbp+var_18]
0x1800a6dc2  lea     rdx, IID_IUnknown
0x1800a6dc9  mov     rcx, rbx
0x1800a6dcc  mov     rax, [rax]
0x1800a6dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6dd4  mov     ebx, eax
0x1800a6dd6  test    eax, eax
0x1800a6dd8  js      loc_1800A711C
0x1800a6dde  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a6de5  jz      short loc_1800A6E25
0x1800a6de7  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a6dee  test    rax, rax
0x1800a6df1  jz      short loc_1800A6E04
0x1800a6df3  lea     rdx, aCconnectivityw_7; "CConnectivityWatcher::WaitForConnectivi"...
0x1800a6dfa  mov     ecx, r13d
0x1800a6dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6e02  jmp     short loc_1800A6E25
0x1800a6e04  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a6e0b  jz      short loc_1800A6E25
0x1800a6e0d  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a6e14  jz      short loc_1800A6E25
0x1800a6e16  lea     rdx, aCconnectivityw_7; "CConnectivityWatcher::WaitForConnectivi"...
0x1800a6e1d  mov     ecx, r13d; unsigned int
0x1800a6e20  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800a6e25  lea     r8, [rbp+var_20]; struct IConnectionPoint **
0x1800a6e29  mov     rcx, [rbp+arg_18]; this
0x1800a6e2d  call    ?GetConnectionPoints@NLMConnectionManager@@QEAAJAEBU_GUID@@PEAPEAUIConnectionPoint@@@Z; NLMConnectionManager::GetConnectionPoints(_GUID const &,IConnectionPoint * *)
0x1800a6e32  mov     ebx, eax
0x1800a6e34  test    eax, eax
0x1800a6e36  js      loc_1800A70D2
0x1800a6e3c  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a6e43  jz      short loc_1800A6E83
0x1800a6e45  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a6e4c  test    rax, rax
0x1800a6e4f  jz      short loc_1800A6E62
0x1800a6e51  lea     rdx, aCconnectivityw_2; "CConnectivityWatcher::WaitForConnectivi"...
0x1800a6e58  mov     ecx, r13d
0x1800a6e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6e60  jmp     short loc_1800A6E83
0x1800a6e62  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a6e69  jz      short loc_1800A6E83
0x1800a6e6b  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a6e72  jz      short loc_1800A6E83
0x1800a6e74  lea     rdx, aCconnectivityw_2; "CConnectivityWatcher::WaitForConnectivi"...
0x1800a6e7b  mov     ecx, r13d; unsigned int
0x1800a6e7e  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800a6e83  mov     rcx, [rbp+var_20]
0x1800a6e87  mov     rax, [rcx]
0x1800a6e8a  lea     r8, [rbp+var_2C]
0x1800a6e8e  mov     rdx, [rbp+var_18]
0x1800a6e92  mov     rax, [rax+28h]
0x1800a6e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6e9b  mov     ebx, eax
0x1800a6e9d  test    eax, eax
0x1800a6e9f  jns     short loc_1800A6EEC
0x1800a6ea1  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a6ea8  jz      loc_1800A7167
0x1800a6eae  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a6eb5  test    rax, rax
0x1800a6eb8  jz      short loc_1800A6EC6
0x1800a6eba  lea     rdx, aInetworkevents; "INetworkEvents::Advise failed, hr = %#x"...
0x1800a6ec1  jmp     loc_1800A70F2
0x1800a6ec6  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a6ecd  jz      loc_1800A7167
0x1800a6ed3  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a6eda  jz      loc_1800A7167
0x1800a6ee0  lea     rdx, aInetworkevents; "INetworkEvents::Advise failed, hr = %#x"...
0x1800a6ee7  jmp     loc_1800A7153
0x1800a6eec  mov     dword ptr [rbp+arg_18], r12d
0x1800a6ef0  mov     rax, [r14]
0x1800a6ef3  lea     rdx, [rbp+arg_18]
0x1800a6ef7  mov     rcx, r14
0x1800a6efa  mov     rax, [rax+8]
0x1800a6efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6f03  mov     esi, eax
0x1800a6f05  test    eax, eax
0x1800a6f07  jnz     loc_1800A7084
0x1800a6f0d  cmp     dword ptr [rbp+arg_18], 1
0x1800a6f11  jnz     short loc_1800A6F66
0x1800a6f13  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a6f1a  jz      short loc_1800A6F5B
0x1800a6f1c  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a6f23  test    rax, rax
0x1800a6f26  jz      short loc_1800A6F39
0x1800a6f28  lea     rdx, aCconnectivityw_5; "CConnectivityWatcher::WaitForConnectivi"...
0x1800a6f2f  mov     ecx, r13d
0x1800a6f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6f37  jmp     short loc_1800A6F5B
0x1800a6f39  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a6f40  jz      short loc_1800A6F5B
0x1800a6f42  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a6f49  jz      short loc_1800A6F5B
0x1800a6f4b  lea     rdx, aCconnectivityw_5; "CConnectivityWatcher::WaitForConnectivi"...
0x1800a6f52  mov     ecx, r13d; unsigned int
0x1800a6f55  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800a6f5a  nop
0x1800a6f5b  call    cs:__imp_CoUninitialize
0x1800a6f61  jmp     loc_1800A7171
0x1800a6f66  call    cs:__imp_GetTickCount
0x1800a6f6c  lea     r8, [rbp+dwMilliseconds]; unsigned int *
0x1800a6f70  mov     edx, eax; unsigned int
0x1800a6f72  mov     ecx, r15d; unsigned int
0x1800a6f75  call    ?CalculateTimeLeftToWait@@YAKKKPEAK@Z; CalculateTimeLeftToWait(ulong,ulong,ulong *)
0x1800a6f7a  test    eax, eax
0x1800a6f7c  jz      short loc_1800A6F85
0x1800a6f7e  mov     esi, 102h
0x1800a6f83  jmp     short loc_1800A6F5B
0x1800a6f85  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a6f8c  jz      short loc_1800A6FCC
0x1800a6f8e  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a6f95  test    rax, rax
0x1800a6f98  jz      short loc_1800A6FAB
0x1800a6f9a  lea     rdx, aCconnectivityw; "CConnectivityWatcher::WaitForConnectivi"...
0x1800a6fa1  mov     ecx, r13d
0x1800a6fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6fa9  jmp     short loc_1800A6FCC
0x1800a6fab  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a6fb2  jz      short loc_1800A6FCC
0x1800a6fb4  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a6fbb  jz      short loc_1800A6FCC
0x1800a6fbd  lea     rdx, aCconnectivityw; "CConnectivityWatcher::WaitForConnectivi"...
0x1800a6fc4  mov     ecx, r13d; unsigned int
0x1800a6fc7  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800a6fcc  mov     edx, [rbp+dwMilliseconds]; dwMilliseconds
0x1800a6fcf  mov     rcx, [rbp+hHandle]; hHandle
0x1800a6fd3  call    cs:__imp_WaitForSingleObject
0x1800a6fd9  mov     esi, eax
0x1800a6fdb  test    eax, eax
0x1800a6fdd  jnz     short loc_1800A7029
0x1800a6fdf  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a6fe6  jz      short loc_1800A7026
0x1800a6fe8  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a6fef  test    rax, rax
0x1800a6ff2  jz      short loc_1800A7005
0x1800a6ff4  lea     rdx, aCconnectivityw_6; "CConnectivityWatcher::WaitForConnectivi"...
0x1800a6ffb  mov     ecx, r13d
0x1800a6ffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7003  jmp     short loc_1800A7026
0x1800a7005  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a700c  jz      short loc_1800A7026
0x1800a700e  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a7015  jz      short loc_1800A7026
0x1800a7017  lea     rdx, aCconnectivityw_6; "CConnectivityWatcher::WaitForConnectivi"...
0x1800a701e  mov     ecx, r13d; unsigned int
0x1800a7021  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800a7026  mov     esi, r12d
0x1800a7029  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a7030  jz      loc_1800A7167
0x1800a7036  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a703d  test    rax, rax
0x1800a7040  jz      short loc_1800A7056
0x1800a7042  lea     rdx, aCconnectivityw_3; "CConnectivityWatcher::WaitForConnectivi"...
0x1800a7049  mov     ecx, r13d
0x1800a704c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7051  jmp     loc_1800A7167
0x1800a7056  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800a705d  jz      loc_1800A7167
0x1800a7063  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800a706a  jz      loc_1800A7167
0x1800a7070  lea     rdx, aCconnectivityw_3; "CConnectivityWatcher::WaitForConnectivi"...
0x1800a7077  mov     ecx, r13d; unsigned int
0x1800a707a  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800a707f  jmp     loc_1800A7167
0x1800a7084  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800a708b  jz      loc_1800A7167
0x1800a7091  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800a7098  test    rax, rax
  ... truncated ...
```
