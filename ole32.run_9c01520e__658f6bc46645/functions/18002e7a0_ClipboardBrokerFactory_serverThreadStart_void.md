# ClipboardBrokerFactory::serverThreadStart(void *)

- ea: `0x18002e7a0`
- end: `0x18002e9d4`
- name: `?serverThreadStart@ClipboardBrokerFactory@@CAKPEAX@Z`
- size: `564`
- prototype: `unsigned int __fastcall(void *pvhr)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800085a8`
- `0x18001b63c`
- `0x18001b7b0`
- `0x18001c654`
- `0x18002e7a0`
- `0x18002ec1c`
- `0x18003aa98`
- `0x180042af8`
- `0x18008aa84`
- `0x18008ab04`
- `0x18008b4c4`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002e7dd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002e7dd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002e851`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002e851`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002e9c3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002e9c3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002e9b3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002e9b3`
- `USER32!GetClipboardOwner` at `0x18002e877`
- `USER32!GetClipboardOwner` at `0x18002e877`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18002e7f8`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18002e7f8`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18002e82a`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18002e82a`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18002e95c`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18002e95c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e996`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e996`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18002e91b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18002e91b`

## pseudocode

```c
__int64 __fastcall ClipboardBrokerFactory::serverThreadStart(HRESULT *pvhr)
{
  HRESULT v2; // edi
  HANDLE v3; // rcx
  unsigned int v4; // edx
  unsigned int v5; // edi
  HRESULT v6; // eax
  HRESULT v7; // ebx
  HWND ClipboardOwner; // rax
  Microsoft::WRL::ComPtr<CClipboardBroker> *v10; // rax
  IClipboardBroker *ptr; // rbx
  CBrokerInstanceHolder **v12; // rdx
  CClipboardBroker *v13; // rcx
  wchar_t *v14; // rbx
  ClipboardWatchdog watchdog; // [rsp+30h] [rbp-10h] BYREF
  Microsoft::WRL::ComPtr<CClipboardBroker> dwIndex; // [rsp+60h] [rbp+20h] BYREF
  const wchar_t *pszOwnerPackageFullName; // [rsp+68h] [rbp+28h] BYREF

  v2 = OleInitializeEx(0);
  if ( v2 >= 0 )
  {
    v10 = Microsoft::WRL::Details::Make<CClipboardBroker,>(&dwIndex);
    pszOwnerPackageFullName = 0;
    ptr = v10->ptr_;
    v10->ptr_ = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&pszOwnerPackageFullName);
    v13 = dwIndex.ptr_;
    if ( dwIndex.ptr_ )
    {
      dwIndex.ptr_ = 0;
      ((void (__fastcall *)(CClipboardBroker *))v13->lpVtbl->Release)(v13);
    }
    if ( ptr )
    {
      v2 = CBrokerInstanceHolder::Create(ptr, v12);
      ((void (__fastcall *)(IClipboardBroker *))ptr->lpVtbl->Release)(ptr);
    }
    else
    {
      v2 = -2147024882;
      RoOriginateError(2147942414LL, 0);
    }
  }
  watchdog.m_timer = 0;
  watchdog.m_monitoredThreadID = 0;
  if ( v2 >= 0 )
    v2 = ClipboardWatchdog::Initialize(&watchdog);
  v3 = ClipboardBrokerFactory::s_hServerThreadEvent;
  *pvhr = v2;
  SetEvent(v3);
  if ( v2 >= 0 )
  {
    v5 = (unsigned int)CoEnableCallCancellation(0) >> 31;
    do
    {
      LODWORD(dwIndex.ptr_) = 0;
      v6 = CoWaitForMultipleHandles(
             0x18u,
             0x3A98u,
             1u,
             &ClipboardBrokerFactory::s_hServerThreadStopEvent,
             (LPDWORD)&dwIndex);
      pszOwnerPackageFullName = (const wchar_t *)-300000000LL;
      v7 = v6;
      SetThreadpoolTimer(watchdog.m_timer, (PFILETIME)&pszOwnerPackageFullName, 0, 0x1388u);
    }
    while ( v7 == -2147417835 );
    if ( !(_BYTE)v5 )
      CoDisableCallCancellation(0);
    pszOwnerPackageFullName = 0;
    LODWORD(dwIndex.ptr_) = 0;
    ClipboardOwner = GetClipboardOwner();
    if ( GetClipboardOwnerWindowProperty(ClipboardOwner, &pszOwnerPackageFullName, (unsigned int *)&dwIndex) >= 0 )
    {
      v14 = (wchar_t *)pszOwnerPackageFullName;
      if ( pszOwnerPackageFullName )
      {
        OleClipboardTracing::ClipboardBroker_TryFlushClipboardOnShutdown(
          pszOwnerPackageFullName,
          (unsigned int)dwIndex.ptr_);
        OleFlushClipboardInternal(v14, 1, 0);
        CoTaskMemFree(v14);
      }
    }
  }
  if ( ClipboardBrokerFactory::s_pServerBroker )
    CBrokerInstanceHolder::`scalar deleting destructor'(ClipboardBrokerFactory::s_pServerBroker, v4);
  ClipboardBrokerFactory::s_pServerBroker = 0;
  OleUninitialize();
  if ( watchdog.m_timer )
  {
    WaitForThreadpoolTimerCallbacks(watchdog.m_timer, 1);
    CloseThreadpoolTimer(watchdog.m_timer);
  }
  return 0;
}

```

## disassembly

```asm
0x18002e7a0  mov     [rsp-18h+arg_10], rbx
0x18002e7a5  push    rbp
0x18002e7a6  push    rsi
0x18002e7a7  push    rdi
0x18002e7a8  mov     rbp, rsp
0x18002e7ab  sub     rsp, 40h
0x18002e7af  mov     rsi, pvhr
0x18002e7b2  xor     ecx, ecx; pvReserved
0x18002e7b4  call    OleInitializeEx
0x18002e7b9  mov     edi, eax
0x18002e7bb  test    eax, eax
0x18002e7bd  jns     loc_18002E8D5
0x18002e7c3  and     [rbp+watchdog.m_timer], 0
0x18002e7c8  and     [rbp+watchdog.m_monitoredThreadID], 0
0x18002e7cc  test    edi, edi
0x18002e7ce  jns     loc_18002E94A
0x18002e7d4  mov     pvhr, cs:?s_hServerThreadEvent@ClipboardBrokerFactory@@0PEAXEA; hEvent
0x18002e7db  mov     [rsi], edi
0x18002e7dd  call    cs:__imp_SetEvent
0x18002e7e4  nop     dword ptr [rax+rax+00h]
0x18002e7e9  mov     esi, 1
0x18002e7ee  test    edi, edi
0x18002e7f0  js      loc_18002E89B
0x18002e7f6  xor     ecx, ecx; pReserved
0x18002e7f8  call    cs:__imp_CoEnableCallCancellation
0x18002e7ff  nop     dword ptr [rax+rax+00h]
0x18002e804  mov     edi, eax
0x18002e806  shr     edi, 1Fh
0x18002e809  and     dword ptr [rbp+dwIndex], 0
0x18002e80d  lea     rax, [rbp+dwIndex]
0x18002e811  lea     r9, ?s_hServerThreadStopEvent@ClipboardBrokerFactory@@0PEAXEA; pHandles
0x18002e818  mov     [rsp+40h+lpdwindex], rax; lpdwindex
0x18002e81d  mov     r8d, esi; cHandles
0x18002e820  mov     edx, 3A98h; dwTimeout
0x18002e825  mov     ecx, 18h; dwFlags
0x18002e82a  call    cs:__imp_CoWaitForMultipleHandles
0x18002e831  nop     dword ptr [rax+rax+00h]
0x18002e836  mov     pvhr, [rbp+watchdog.m_timer]; pti
0x18002e83a  lea     rdx, [rbp+pszOwnerPackageFullName]; pftDueTime
0x18002e83e  mov     r9d, 1388h; msWindowLength
0x18002e844  mov     [rbp+pszOwnerPackageFullName], 0FFFFFFFFEE1E5D00h
0x18002e84c  xor     r8d, r8d; msPeriod
0x18002e84f  mov     ebx, eax
0x18002e851  call    cs:__imp_SetThreadpoolTimer
0x18002e858  nop     dword ptr [rax+rax+00h]
0x18002e85d  cmp     ebx, 80010115h
0x18002e863  jz      short loc_18002E809
0x18002e865  test    dil, dil
0x18002e868  jz      loc_18002E95A
0x18002e86e  and     [rbp+pszOwnerPackageFullName], 0
0x18002e873  and     dword ptr [rbp+dwIndex], 0
0x18002e877  call    cs:__imp_GetClipboardOwner
0x18002e87e  nop     dword ptr [rax+rax+00h]
0x18002e883  mov     pvhr, rax; hWnd
0x18002e886  lea     r8, [rbp+dwIndex]; pdwProcessId
0x18002e88a  lea     rdx, [rbp+pszOwnerPackageFullName]; pszPackageId
0x18002e88e  call    ?GetClipboardOwnerWindowProperty@@YAJPEAUHWND__@@PEAPEBGPEAK@Z; GetClipboardOwnerWindowProperty(HWND__ *,ushort const * *,ulong *)
0x18002e893  test    eax, eax
0x18002e895  jns     loc_18002E96D
0x18002e89b  mov     pvhr, cs:?s_pServerBroker@ClipboardBrokerFactory@@0PEAVCBrokerInstanceHolder@@EA; this
0x18002e8a2  test    pvhr, pvhr
0x18002e8a5  jnz     loc_18002E9A7
0x18002e8ab  and     cs:?s_pServerBroker@ClipboardBrokerFactory@@0PEAVCBrokerInstanceHolder@@EA, 0; CBrokerInstanceHolder * ClipboardBrokerFactory::s_pServerBroker
0x18002e8b3  call    OleUninitialize
0x18002e8b8  mov     pvhr, [rbp+watchdog.m_timer]; pti
0x18002e8bc  test    pvhr, pvhr
0x18002e8bf  jnz     loc_18002E9B1
0x18002e8c5  mov     rbx, [rsp+40h+arg_10]
0x18002e8ca  xor     eax, eax
0x18002e8cc  add     rsp, 40h
0x18002e8d0  pop     rdi
0x18002e8d1  pop     rsi
0x18002e8d2  pop     rbp
0x18002e8d3  retn
0x18002e8d5  lea     pvhr, [rbp+dwIndex]; result
0x18002e8d9  call    ??$Make@VCClipboardBroker@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCClipboardBroker@@@12@XZ; Microsoft::WRL::Details::Make<CClipboardBroker,>(void)
0x18002e8de  and     [rbp+pszOwnerPackageFullName], 0
0x18002e8e3  lea     pvhr, [rbp+pszOwnerPackageFullName]; this
0x18002e8e7  mov     rbx, [rax]
0x18002e8ea  and     qword ptr [rax], 0
0x18002e8ee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e8f3  mov     pvhr, [rbp+dwIndex]
0x18002e8f7  test    pvhr, pvhr
0x18002e8fa  jz      short loc_18002E90D
0x18002e8fc  and     [rbp+dwIndex], 0
0x18002e901  mov     rax, [pvhr]
0x18002e904  mov     rax, [rax+10h]
0x18002e908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e90d  test    rbx, rbx
0x18002e910  jnz     short loc_18002E92C
0x18002e912  mov     edi, 8007000Eh
0x18002e917  xor     edx, edx
0x18002e919  mov     ecx, edi
0x18002e91b  call    cs:__imp_RoOriginateError
0x18002e922  nop     dword ptr [rax+rax+00h]
0x18002e927  jmp     loc_18002E7C3
0x18002e92c  mov     pvhr, rbx; broker
0x18002e92f  call    ?Create@CBrokerInstanceHolder@@SAJPEAUIClipboardBroker@@PEAPEAV1@@Z; CBrokerInstanceHolder::Create(IClipboardBroker *,CBrokerInstanceHolder * *)
0x18002e934  mov     edi, eax
0x18002e936  mov     pvhr, rbx
0x18002e939  mov     rax, [rbx]
0x18002e93c  mov     rax, [rax+10h]
0x18002e940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e945  jmp     loc_18002E7C3
0x18002e94a  lea     pvhr, [rbp+watchdog]; this
0x18002e94e  call    ?Initialize@ClipboardWatchdog@@QEAAJXZ; ClipboardWatchdog::Initialize(void)
0x18002e953  mov     edi, eax
0x18002e955  jmp     loc_18002E7D4
0x18002e95a  xor     ecx, ecx; pReserved
0x18002e95c  call    cs:__imp_CoDisableCallCancellation
0x18002e963  nop     dword ptr [rax+rax+00h]
0x18002e968  jmp     loc_18002E86E
0x18002e96d  mov     rbx, [rbp+pszOwnerPackageFullName]
0x18002e971  test    rbx, rbx
0x18002e974  jz      loc_18002E89B
0x18002e97a  mov     edx, dword ptr [rbp+dwIndex]; ownerPid
0x18002e97d  mov     pvhr, rbx; pszOwnerPackageFullName
0x18002e980  call    ?ClipboardBroker_TryFlushClipboardOnShutdown@OleClipboardTracing@@SAXPEBGK@Z; OleClipboardTracing::ClipboardBroker_TryFlushClipboardOnShutdown(ushort const *,ulong)
0x18002e985  xor     r8d, r8d; fTextOnly
0x18002e988  mov     dl, sil; fInBroker
0x18002e98b  mov     pvhr, rbx; pszCallerPackgeFullName
0x18002e98e  call    ?OleFlushClipboardInternal@@YAJPEBG_N1@Z; OleFlushClipboardInternal(ushort const *,bool,bool)
0x18002e993  mov     pvhr, rbx; pv
0x18002e996  call    cs:__imp_CoTaskMemFree
0x18002e99d  nop     dword ptr [rax+rax+00h]
0x18002e9a2  jmp     loc_18002E89B
0x18002e9a7  call    ??_GCBrokerInstanceHolder@@QEAAPEAXI@Z; CBrokerInstanceHolder::`scalar deleting destructor'(uint)
0x18002e9ac  jmp     loc_18002E8AB
0x18002e9b1  mov     edx, esi; fCancelPendingCallbacks
0x18002e9b3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002e9ba  nop     dword ptr [rax+rax+00h]
0x18002e9bf  mov     pvhr, [rbp+watchdog.m_timer]; pti
0x18002e9c3  call    cs:__imp_CloseThreadpoolTimer
0x18002e9ca  nop     dword ptr [rax+rax+00h]
0x18002e9cf  jmp     loc_18002E8C5
```
