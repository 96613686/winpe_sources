# Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskRelaunch::StartActivity(void)

- ea: `0x180013a98`
- end: `0x180013b30`
- name: `?StartActivity@BackgroundTaskRelaunch@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAAXXZ`
- size: `152`
- prototype: `void __fastcall(Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskRelaunch *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f748`

## callees

- `0x180002034`
- `0x180008858`
- `0x180008ca0`
- `0x1800095bc`
- `0x180013a98`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013ab9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013ab9`

## pseudocode

```c
void __fastcall Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskRelaunch::StartActivity(
        Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskRelaunch *this)
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
      (__int64)&unk_18001FD60,
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
0x180013a98  mov     [rsp+arg_10], rbx
0x180013a9d  push    rdi
0x180013a9e  sub     rsp, 30h
0x180013aa2  mov     rbx, rcx
0x180013aa5  call    ?zInternalStart@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180013aaa  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x180013aaf  mov     rdi, rax
0x180013ab2  mov     edx, [rax]
0x180013ab4  cmp     edx, 5
0x180013ab7  jbe     short loc_180013B1C
0x180013ab9  call    cs:__imp_GetCurrentThreadId
0x180013abf  mov     [rsp+38h+arg_0], eax
0x180013ac3  xor     eax, eax
0x180013ac5  mov     [rsp+38h+arg_8], rax
0x180013aca  mov     r8, [rbx+110h]
0x180013ad1  cmp     [r8+4], al
0x180013ad5  jz      short loc_180013AF2
0x180013ad7  lea     r9, [r8+18h]
0x180013adb  cmp     [r9], eax
0x180013ade  jnz     short loc_180013AF5
0x180013ae0  cmp     [r9+4], eax
0x180013ae4  jnz     short loc_180013AF5
0x180013ae6  cmp     [r9+8], eax
0x180013aea  jnz     short loc_180013AF5
0x180013aec  cmp     [r9+0Ch], eax
0x180013af0  jnz     short loc_180013AF5
0x180013af2  mov     r9, rax
0x180013af5  add     r8, 8
0x180013af9  lea     rax, [rsp+38h+arg_0]
0x180013afe  mov     [rsp+38h+var_10], rax
0x180013b03  lea     rax, [rsp+38h+arg_8]
0x180013b08  mov     [rsp+38h+var_18], rax
0x180013b0d  lea     rdx, unk_18001FD60
0x180013b14  mov     rcx, rdi
0x180013b17  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180013b1c  mov     rcx, rbx
0x180013b1f  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180013b24  nop
0x180013b25  mov     rbx, [rsp+38h+arg_10]
0x180013b2a  add     rsp, 30h
0x180013b2e  pop     rdi
0x180013b2f  retn
```
