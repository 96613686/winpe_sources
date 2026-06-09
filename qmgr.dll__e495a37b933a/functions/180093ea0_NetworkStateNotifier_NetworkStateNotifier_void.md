# NetworkStateNotifier::~NetworkStateNotifier(void)

- ea: `0x180093ea0`
- end: `0x180094027`
- name: `??1NetworkStateNotifier@@UEAA@XZ`
- size: `391`
- prototype: `void __fastcall(NetworkStateNotifier *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800b2bd0`

## callees

- `0x18002c6ac`
- `0x180081600`
- `0x180084e54`
- `0x180090524`
- `0x180093ea0`
- `0x1800b3114`
- `0x1800b4700`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180093f1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180093f1c`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180093f3e`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180093f3e`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180093fc1`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180093fc1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180093fd7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180093fd7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180093f77`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180093f77`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall NetworkStateNotifier::~NetworkStateNotifier(NetworkStateNotifier *this)
{
  NetworkStateNotifier *v1; // rbx
  _QWORD *v2; // rsi
  _QWORD *v3; // r14
  unsigned __int64 v4; // rdx
  unsigned __int8 v5; // cl
  __int64 v6; // rcx
  CTelemetry *v7; // rcx
  const ComError *v8; // [rsp+40h] [rbp-48h] BYREF
  DWORD Parameter; // [rsp+48h] [rbp-40h] BYREF
  char v10; // [rsp+4Ch] [rbp-3Ch]
  HRESULT v11; // [rsp+50h] [rbp-38h]
  void *phNewTimer; // [rsp+58h] [rbp-30h] BYREF
  char *v15; // [rsp+98h] [rbp+10h]
  char *v17; // [rsp+A0h] [rbp+18h]

  v1 = this;
  *(_QWORD *)this = &NetworkStateNotifier::`vftable'{for `INotifier'};
  v2 = (_QWORD *)((char *)this + 8);
  v15 = (char *)this + 8;
  *((_QWORD *)this + 1) = &NetworkStateNotifier::`vftable'{for `IQueryableNotifier'};
  *((_QWORD *)this + 2) = &NetworkStateNotifier::`vftable'{for `INetworkConnectionEvents'};
  v3 = (_QWORD *)((char *)this + 24);
  v17 = (char *)this + 24;
  *((_QWORD *)this + 3) = &NetworkStateNotifier::`vftable'{for `RefCountedObject'};
  if ( *((_QWORD *)this + 5) )
  {
    try
    {
      NetworkStateNotifier::UnsubscribeAndWaitForNotifications(this);
    }
    catch ( const ComError *v8 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          121,
          WPP_7d97e8f08c103805412e520f8fe9c630_Traceguids,
          *((unsigned int *)v8 + 6),
          *((_DWORD *)v8 + 7));
      v1 = this;
      v2 = v15;
      v3 = v17;
    }
  }
  Parameter = GetCurrentThreadId();
  v10 = 0;
  v11 = -2147467259;
  phNewTimer = 0;
  v11 = CoEnableCallCancellation(0);
  if ( v11 >= 0 )
    CreateTimerQueueTimer(&phNewTimer, 0, CBaseRPCTimeout::s_Callback, &Parameter, 0x2710u, 0x3E8u, 0);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)v1 + 72);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)v1 + 64);
  if ( v10 && CTelemetry::IsEnabled(v5, v4) )
  {
    wil::details::static_lazy<CTelemetry>::get(v6, _lambda_522be0d8c7a8171f2eb2c3a9bc6a1151_::_lambda_invoker_cdecl_);
    CTelemetry::NlmFinalReleaseHangDetected_(v7);
  }
  if ( v11 >= 0 )
  {
    v11 = -2147467259;
    CoDisableCallCancellation(0);
    if ( phNewTimer )
      DeleteTimerQueueTimer(0, phNewTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  }
  StatelessInternallyTriggeredNotifier::~StatelessInternallyTriggeredNotifier((NetworkStateNotifier *)((char *)v1 + 80));
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)v1 + 72);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)v1 + 64);
  *v3 = &RefCountedObject::`vftable';
  *v2 = &IQueryableNotifier::`vftable';
  *(_QWORD *)v1 = &INotifier::`vftable';
}

```

## disassembly

```asm
0x180093ea0  mov     [rsp+arg_0], rcx
0x180093ea5  push    rbx
0x180093ea6  push    rsi
0x180093ea7  push    r12
0x180093ea9  push    r14
0x180093eab  push    r15
0x180093ead  sub     rsp, 60h
0x180093eb1  mov     rbx, rcx
0x180093eb4  lea     rax, ??_7NetworkStateNotifier@@6BINotifier@@@; const NetworkStateNotifier::`vftable'{for `INotifier'}
0x180093ebb  mov     [rcx], rax
0x180093ebe  lea     rsi, [rcx+8]
0x180093ec2  mov     [rsp+88h+arg_8], rsi
0x180093eca  lea     rax, ??_7NetworkStateNotifier@@6BIQueryableNotifier@@@; const NetworkStateNotifier::`vftable'{for `IQueryableNotifier'}
0x180093ed1  mov     [rsi], rax
0x180093ed4  lea     rax, ??_7NetworkStateNotifier@@6BINetworkConnectionEvents@@@; const NetworkStateNotifier::`vftable'{for `INetworkConnectionEvents'}
0x180093edb  mov     [rcx+10h], rax
0x180093edf  lea     r14, [rcx+18h]
0x180093ee3  mov     [rsp+88h+arg_10], r14
0x180093eeb  lea     rax, ??_7NetworkStateNotifier@@6BRefCountedObject@@@; const NetworkStateNotifier::`vftable'{for `RefCountedObject'}
0x180093ef2  mov     [r14], rax
0x180093ef5  cmp     qword ptr [rcx+28h], 0
0x180093efa  jz      short loc_180093F1C
0x180093efc  call    ?UnsubscribeAndWaitForNotifications@NetworkStateNotifier@@UEAAXXZ; NetworkStateNotifier::UnsubscribeAndWaitForNotifications(void)
0x180093f01  nop
0x180093f02  jmp     short loc_180093F1C
0x180093f04  mov     rbx, [rsp+88h+arg_0]
0x180093f0c  mov     rsi, [rsp+88h+arg_8]
0x180093f14  mov     r14, [rsp+88h+arg_10]
0x180093f1c  call    cs:__imp_GetCurrentThreadId
0x180093f22  mov     [rsp+88h+Parameter], eax
0x180093f26  mov     [rsp+88h+var_3C], 0
0x180093f2b  mov     [rsp+88h+var_38], 80004005h
0x180093f33  mov     [rsp+88h+phNewTimer], 0
0x180093f3c  xor     ecx, ecx; pReserved
0x180093f3e  call    cs:__imp_CoEnableCallCancellation
0x180093f44  mov     [rsp+88h+var_38], eax
0x180093f48  test    eax, eax
0x180093f4a  js      short loc_180093F7D
0x180093f4c  mov     [rsp+88h+Flags], 0; Flags
0x180093f54  mov     [rsp+88h+Period], 3E8h; Period
0x180093f5c  mov     [rsp+88h+DueTime], 2710h; DueTime
0x180093f64  lea     r9, [rsp+88h+Parameter]; Parameter
0x180093f69  lea     r8, ?s_Callback@CBaseRPCTimeout@@CAXPEAXE@Z; Callback
0x180093f70  xor     edx, edx; TimerQueue
0x180093f72  lea     rcx, [rsp+88h+phNewTimer]; phNewTimer
0x180093f77  call    cs:__imp_CreateTimerQueueTimer
0x180093f7d  lea     rcx, [rbx+48h]
0x180093f81  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180093f86  lea     rcx, [rbx+40h]
0x180093f8a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180093f8f  cmp     [rsp+88h+var_3C], 0
0x180093f94  jz      short loc_180093FB0
0x180093f96  call    ?IsEnabled@CTelemetry@@SA_NE_K@Z; CTelemetry::IsEnabled(uchar,unsigned __int64)
0x180093f9b  test    al, al
0x180093f9d  jz      short loc_180093FB0
0x180093f9f  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_522be0d8c7a8171f2eb2c3a9bc6a1151_@@CA@XZ; _lambda_522be0d8c7a8171f2eb2c3a9bc6a1151_::_lambda_invoker_cdecl_(void)
0x180093fa6  call    ?get@?$static_lazy@VCTelemetry@@@details@wil@@QEAAPEAVCTelemetry@@P6AXXZ@Z; wil::details::static_lazy<CTelemetry>::get(void (*)(void))
0x180093fab  call    ?NlmFinalReleaseHangDetected_@CTelemetry@@QEAAXXZ; CTelemetry::NlmFinalReleaseHangDetected_(void)
0x180093fb0  cmp     [rsp+88h+var_38], 0
0x180093fb5  jl      short loc_180093FDE
0x180093fb7  mov     [rsp+88h+var_38], 80004005h
0x180093fbf  xor     ecx, ecx; pReserved
0x180093fc1  call    cs:__imp_CoDisableCallCancellation
0x180093fc7  mov     rdx, [rsp+88h+phNewTimer]; Timer
0x180093fcc  test    rdx, rdx
0x180093fcf  jz      short loc_180093FDE
0x180093fd1  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180093fd5  xor     ecx, ecx; TimerQueue
0x180093fd7  call    cs:__imp_DeleteTimerQueueTimer
0x180093fdd  nop
0x180093fde  lea     rcx, [rbx+50h]; this
0x180093fe2  call    ??1StatelessInternallyTriggeredNotifier@@UEAA@XZ; StatelessInternallyTriggeredNotifier::~StatelessInternallyTriggeredNotifier(void)
0x180093fe7  nop
0x180093fe8  lea     rcx, [rbx+48h]
0x180093fec  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180093ff1  nop
0x180093ff2  lea     rcx, [rbx+40h]
0x180093ff6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180093ffb  nop
0x180093ffc  lea     rax, ??_7RefCountedObject@@6B@; const RefCountedObject::`vftable'
0x180094003  mov     [r14], rax
0x180094006  lea     rax, ??_7IQueryableNotifier@@6B@; const IQueryableNotifier::`vftable'
0x18009400d  mov     [rsi], rax
0x180094010  lea     rax, ??_7INotifier@@6B@; const INotifier::`vftable'
0x180094017  mov     [rbx], rax
0x18009401a  add     rsp, 60h
0x18009401e  pop     r15
0x180094020  pop     r14
0x180094022  pop     r12
0x180094024  pop     rsi
0x180094025  pop     rbx
0x180094026  retn
```
