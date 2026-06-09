# Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskActivation::StartActivity(ushort const *)

- ea: `0x180013648`
- end: `0x18001376f`
- name: `?StartActivity@BackgroundTaskActivation@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAAXPEBG@Z`
- size: `295`
- prototype: `void __fastcall(Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskActivation *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800114f0`

## callees

- `0x1800019bc`
- `0x180001f70`
- `0x180008710`
- `0x1800088d0`
- `0x180008ca0`
- `0x180009150`
- `0x180013648`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800136e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800136e1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180013694`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180013694`

## pseudocode

```c
void __fastcall Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskActivation::StartActivity(
        Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskActivation *this,
        const unsigned __int16 *a2)
{
  __int64 v4; // rbx
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r9
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  __int64 v14; // r9
  RTL_SRWLOCK *v15; // [rsp+60h] [rbp+8h] BYREF
  __int64 *v16; // [rsp+70h] [rbp+18h] BYREF
  __int64 v17; // [rsp+78h] [rbp+20h] BYREF

  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &v15);
  v4 = *((_QWORD *)this + 34);
  v5 = Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider();
  v7 = *(unsigned int *)v5;
  if ( (unsigned int)v7 > 5 && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL, v7, v6) )
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  else
    *(_OWORD *)(v4 + 8) = 0;
  *(_DWORD *)v4 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v15);
  v8 = Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider();
  v11 = (__int64)v8;
  if ( *(_DWORD *)v8 > 5u && (unsigned __int8)tlgKeywordOn(v8, 0x200000000000LL, v9, v10) )
  {
    v16 = (__int64 *)a2;
    CurrentThreadId = GetCurrentThreadId();
    v13 = *((_QWORD *)this + 34);
    LODWORD(v15) = CurrentThreadId;
    v17 = 0;
    if ( !*(_BYTE *)(v13 + 4)
      || (v14 = v13 + 24, !*(_DWORD *)(v13 + 24))
      && !*(_DWORD *)(v13 + 28)
      && !*(_DWORD *)(v13 + 32)
      && !*(_DWORD *)(v13 + 36) )
    {
      v14 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v11,
      (__int64)&dword_18001FC64,
      v13 + 8,
      v14,
      (__int64)&v17,
      (__int64)&v15,
      &v16);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskActivation *)((char *)this + 288));
}

```

## disassembly

```asm
0x180013648  push    rbx
0x18001364a  push    rsi
0x18001364b  push    rdi
0x18001364c  sub     rsp, 40h
0x180013650  mov     rsi, rdx
0x180013653  mov     rdi, rcx
0x180013656  lea     rdx, [rsp+58h+arg_0]
0x18001365b  call    ?LockExclusive@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180013660  mov     rbx, [rdi+110h]
0x180013667  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x18001366c  mov     r8d, [rax]
0x18001366f  cmp     r8d, 5
0x180013673  jbe     short loc_18001369C
0x180013675  mov     rdx, 200000000000h
0x18001367f  mov     rcx, rax
0x180013682  call    _tlgKeywordOn
0x180013687  test    al, al
0x180013689  jz      short loc_18001369C
0x18001368b  lea     rdx, [rbx+8]; ActivityId
0x18001368f  mov     ecx, 3; ControlCode
0x180013694  call    cs:__imp_EventActivityIdControl
0x18001369a  jmp     short loc_1800136A3
0x18001369c  xorps   xmm0, xmm0
0x18001369f  movups  xmmword ptr [rbx+8], xmm0
0x1800136a3  lea     rcx, [rsp+58h+arg_0]
0x1800136a8  mov     dword ptr [rbx], 1
0x1800136ae  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800136b3  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x1800136b8  mov     rbx, rax
0x1800136bb  mov     ecx, [rax]
0x1800136bd  cmp     ecx, 5
0x1800136c0  jbe     loc_180013755
0x1800136c6  mov     rdx, 200000000000h
0x1800136d0  mov     rcx, rax
0x1800136d3  call    _tlgKeywordOn
0x1800136d8  test    al, al
0x1800136da  jz      short loc_180013755
0x1800136dc  mov     [rsp+58h+arg_10], rsi
0x1800136e1  call    cs:__imp_GetCurrentThreadId
0x1800136e7  mov     r8, [rdi+110h]
0x1800136ee  mov     dword ptr [rsp+58h+arg_0], eax
0x1800136f2  mov     [rsp+58h+arg_18], 0
0x1800136fb  cmp     byte ptr [r8+4], 0
0x180013700  jz      short loc_180013721
0x180013702  lea     r9, [r8+18h]
0x180013706  cmp     dword ptr [r9], 0
0x18001370a  jnz     short loc_180013724
0x18001370c  cmp     dword ptr [r9+4], 0
0x180013711  jnz     short loc_180013724
0x180013713  cmp     dword ptr [r9+8], 0
0x180013718  jnz     short loc_180013724
0x18001371a  cmp     dword ptr [r9+0Ch], 0
0x18001371f  jnz     short loc_180013724
0x180013721  xor     r9d, r9d
0x180013724  lea     rax, [rsp+58h+arg_10]
0x180013729  add     r8, 8
0x18001372d  mov     [rsp+58h+var_28], rax
0x180013732  lea     rdx, dword_18001FC64
0x180013739  lea     rax, [rsp+58h+arg_0]
0x18001373e  mov     rcx, rbx
0x180013741  mov     [rsp+58h+var_30], rax
0x180013746  lea     rax, [rsp+58h+arg_18]
0x18001374b  mov     [rsp+58h+var_38], rax
0x180013750  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180013755  lea     rcx, [rdi+120h]; this
0x18001375c  cmp     dword ptr [rcx+18h], 0
0x180013760  jnz     short loc_180013767
0x180013762  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180013767  add     rsp, 40h
0x18001376b  pop     rdi
0x18001376c  pop     rsi
0x18001376d  pop     rbx
0x18001376e  retn
```
