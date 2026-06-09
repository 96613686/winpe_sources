# Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch::StartActivity(void)

- ea: `0x180013958`
- end: `0x1800139f0`
- name: `?StartActivity@BackgroundTaskLaunch@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAAXXZ`
- size: `152`
- prototype: `void __fastcall(Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f710`

## callees

- `0x180002034`
- `0x180008858`
- `0x180008ca0`
- `0x1800095bc`
- `0x180013958`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013979`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013979`

## pseudocode

```c
void __fastcall Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch::StartActivity(
        Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch *this)
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
      (__int64)byte_18001FCC5,
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
0x180013958  mov     [rsp+arg_10], rbx
0x18001395d  push    rdi
0x18001395e  sub     rsp, 30h
0x180013962  mov     rbx, rcx
0x180013965  call    ?zInternalStart@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001396a  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x18001396f  mov     rdi, rax
0x180013972  mov     edx, [rax]
0x180013974  cmp     edx, 5
0x180013977  jbe     short loc_1800139DC
0x180013979  call    cs:__imp_GetCurrentThreadId
0x18001397f  mov     [rsp+38h+arg_0], eax
0x180013983  xor     eax, eax
0x180013985  mov     [rsp+38h+arg_8], rax
0x18001398a  mov     r8, [rbx+110h]
0x180013991  cmp     [r8+4], al
0x180013995  jz      short loc_1800139B2
0x180013997  lea     r9, [r8+18h]
0x18001399b  cmp     [r9], eax
0x18001399e  jnz     short loc_1800139B5
0x1800139a0  cmp     [r9+4], eax
0x1800139a4  jnz     short loc_1800139B5
0x1800139a6  cmp     [r9+8], eax
0x1800139aa  jnz     short loc_1800139B5
0x1800139ac  cmp     [r9+0Ch], eax
0x1800139b0  jnz     short loc_1800139B5
0x1800139b2  mov     r9, rax
0x1800139b5  add     r8, 8
0x1800139b9  lea     rax, [rsp+38h+arg_0]
0x1800139be  mov     [rsp+38h+var_10], rax
0x1800139c3  lea     rax, [rsp+38h+arg_8]
0x1800139c8  mov     [rsp+38h+var_18], rax
0x1800139cd  lea     rdx, byte_18001FCC5
0x1800139d4  mov     rcx, rdi
0x1800139d7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800139dc  mov     rcx, rbx
0x1800139df  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1800139e4  nop
0x1800139e5  mov     rbx, [rsp+38h+arg_10]
0x1800139ea  add     rsp, 30h
0x1800139ee  pop     rdi
0x1800139ef  retn
```
