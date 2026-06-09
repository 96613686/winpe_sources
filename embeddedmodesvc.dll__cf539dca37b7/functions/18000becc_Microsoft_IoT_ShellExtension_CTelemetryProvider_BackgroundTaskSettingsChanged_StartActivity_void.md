# Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskSettingsChanged::StartActivity(void)

- ea: `0x18000becc`
- end: `0x18000bf64`
- name: `?StartActivity@BackgroundTaskSettingsChanged@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAAXXZ`
- size: `152`
- prototype: `void __fastcall(Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskSettingsChanged *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000af90`

## callees

- `0x180002034`
- `0x180008858`
- `0x180008ca0`
- `0x1800095bc`
- `0x18000becc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000beed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000beed`

## pseudocode

```c
void __fastcall Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskSettingsChanged::StartActivity(
        Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskSettingsChanged *this)
{
  const struct _tlgProvider_t *v2; // rdi
  __int64 v3; // r8
  __int64 v4; // r9
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v6; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v6 = 0;
    v3 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v3 + 4)
      || (v4 = v3 + 24, !*(_DWORD *)(v3 + 24))
      && !*(_DWORD *)(v3 + 28)
      && !*(_DWORD *)(v3 + 32)
      && !*(_DWORD *)(v3 + 36) )
    {
      v4 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (__int64)v2,
      (__int64)byte_18001FA03,
      v3 + 8,
      v4,
      (__int64)&v6,
      (__int64)&CurrentThreadId);
  }
  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18000becc  mov     [rsp+arg_10], rbx
0x18000bed1  push    rdi
0x18000bed2  sub     rsp, 30h
0x18000bed6  mov     rbx, rcx
0x18000bed9  call    ?zInternalStart@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000bede  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x18000bee3  mov     rdi, rax
0x18000bee6  mov     edx, [rax]
0x18000bee8  cmp     edx, 5
0x18000beeb  jbe     short loc_18000BF50
0x18000beed  call    cs:__imp_GetCurrentThreadId
0x18000bef3  mov     [rsp+38h+arg_0], eax
0x18000bef7  xor     eax, eax
0x18000bef9  mov     [rsp+38h+arg_8], rax
0x18000befe  mov     r8, [rbx+110h]
0x18000bf05  cmp     [r8+4], al
0x18000bf09  jz      short loc_18000BF26
0x18000bf0b  lea     r9, [r8+18h]
0x18000bf0f  cmp     [r9], eax
0x18000bf12  jnz     short loc_18000BF29
0x18000bf14  cmp     [r9+4], eax
0x18000bf18  jnz     short loc_18000BF29
0x18000bf1a  cmp     [r9+8], eax
0x18000bf1e  jnz     short loc_18000BF29
0x18000bf20  cmp     [r9+0Ch], eax
0x18000bf24  jnz     short loc_18000BF29
0x18000bf26  mov     r9, rax
0x18000bf29  add     r8, 8
0x18000bf2d  lea     rax, [rsp+38h+arg_0]
0x18000bf32  mov     [rsp+38h+var_10], rax
0x18000bf37  lea     rax, [rsp+38h+arg_8]
0x18000bf3c  mov     [rsp+38h+var_18], rax
0x18000bf41  lea     rdx, byte_18001FA03
0x18000bf48  mov     rcx, rdi
0x18000bf4b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18000bf50  mov     rcx, rbx
0x18000bf53  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18000bf58  nop
0x18000bf59  mov     rbx, [rsp+38h+arg_10]
0x18000bf5e  add     rsp, 30h
0x18000bf62  pop     rdi
0x18000bf63  retn
```
