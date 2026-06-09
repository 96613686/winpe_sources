# PipeManager::OnStopEvent(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x1800ecc10`
- end: `0x1800ecc8d`
- name: `?OnStopEvent@PipeManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `125`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001010`
- `0x1800cf300`
- `0x1800ecc10`
- `0x1800ecc94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ecc26`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ecc26`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800ecc1c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800ecc1c`

## pseudocode

```c
void __fastcall PipeManager::OnStopEvent(
        PTP_CALLBACK_INSTANCE Instance,
        HANDLE *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  const char *v8; // [rsp+30h] [rbp-18h] BYREF
  const char *v9; // [rsp+58h] [rbp+10h] BYREF

  CloseThreadpoolWait(Wait);
  SetEvent(Context[1]);
  if ( (unsigned int)CallbackContext > 4 )
  {
    v9 = "PipeManager::OnStopEvent";
    v8 = "LuiPipeManager";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v5,
      (unsigned int)&dword_180134CEC,
      v6,
      v7,
      (__int64)&v8,
      (__int64)&v9);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::GetImpl'::`2'::impl) )
    PipeManager::Release((PipeManager *)Context);
}

```

## disassembly

```asm
0x1800ecc10  push    rbx
0x1800ecc12  sub     rsp, 40h
0x1800ecc16  mov     rcx, r8; pwa
0x1800ecc19  mov     rbx, rdx
0x1800ecc1c  call    cs:__imp_CloseThreadpoolWait
0x1800ecc22  mov     rcx, [rbx+8]; hEvent
0x1800ecc26  call    cs:__imp_SetEvent
0x1800ecc2c  mov     eax, cs:CallbackContext
0x1800ecc32  cmp     eax, 4
0x1800ecc35  jbe     short loc_1800ECC6F
0x1800ecc37  lea     rax, aPipemanagerOns; "PipeManager::OnStopEvent"
0x1800ecc3e  mov     [rsp+48h+arg_8], rax
0x1800ecc43  lea     rdx, dword_180134CEC
0x1800ecc4a  lea     rax, aLuipipemanager; "LuiPipeManager"
0x1800ecc51  mov     [rsp+48h+var_18], rax
0x1800ecc56  lea     rax, [rsp+48h+arg_8]
0x1800ecc5b  mov     [rsp+48h+var_20], rax
0x1800ecc60  lea     rax, [rsp+48h+var_18]
0x1800ecc65  mov     [rsp+48h+var_28], rax
0x1800ecc6a  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800ecc6f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping> `wil::Feature<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::GetImpl(void)'::`2'::impl
0x1800ecc76  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::__private_IsEnabled(void)
0x1800ecc7b  test    al, al
0x1800ecc7d  jz      short loc_1800ECC87
0x1800ecc7f  mov     rcx, rbx; this
0x1800ecc82  call    ?Release@PipeManager@@QEAAXXZ; PipeManager::Release(void)
0x1800ecc87  add     rsp, 40h
0x1800ecc8b  pop     rbx
0x1800ecc8c  retn
```
