# Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskInstanceActivation::StartActivity(void)

- ea: `0x1800138b8`
- end: `0x180013950`
- name: `?StartActivity@BackgroundTaskInstanceActivation@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAAXXZ`
- size: `152`
- prototype: `void __fastcall(Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskInstanceActivation *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180012790`

## callees

- `0x180002034`
- `0x180008858`
- `0x180008ca0`
- `0x1800095bc`
- `0x1800138b8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800138d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800138d9`

## pseudocode

```c
void __fastcall Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskInstanceActivation::StartActivity(
        Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskInstanceActivation *this)
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
      (__int64)byte_18001FDFD,
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
0x1800138b8  mov     [rsp+arg_10], rbx
0x1800138bd  push    rdi
0x1800138be  sub     rsp, 30h
0x1800138c2  mov     rbx, rcx
0x1800138c5  call    ?zInternalStart@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800138ca  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x1800138cf  mov     rdi, rax
0x1800138d2  mov     edx, [rax]
0x1800138d4  cmp     edx, 5
0x1800138d7  jbe     short loc_18001393C
0x1800138d9  call    cs:__imp_GetCurrentThreadId
0x1800138df  mov     [rsp+38h+arg_0], eax
0x1800138e3  xor     eax, eax
0x1800138e5  mov     [rsp+38h+arg_8], rax
0x1800138ea  mov     r8, [rbx+110h]
0x1800138f1  cmp     [r8+4], al
0x1800138f5  jz      short loc_180013912
0x1800138f7  lea     r9, [r8+18h]
0x1800138fb  cmp     [r9], eax
0x1800138fe  jnz     short loc_180013915
0x180013900  cmp     [r9+4], eax
0x180013904  jnz     short loc_180013915
0x180013906  cmp     [r9+8], eax
0x18001390a  jnz     short loc_180013915
0x18001390c  cmp     [r9+0Ch], eax
0x180013910  jnz     short loc_180013915
0x180013912  mov     r9, rax
0x180013915  add     r8, 8
0x180013919  lea     rax, [rsp+38h+arg_0]
0x18001391e  mov     [rsp+38h+var_10], rax
0x180013923  lea     rax, [rsp+38h+arg_8]
0x180013928  mov     [rsp+38h+var_18], rax
0x18001392d  lea     rdx, byte_18001FDFD
0x180013934  mov     rcx, rdi
0x180013937  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18001393c  mov     rcx, rbx
0x18001393f  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180013944  nop
0x180013945  mov     rbx, [rsp+38h+arg_10]
0x18001394a  add     rsp, 30h
0x18001394e  pop     rdi
0x18001394f  retn
```
