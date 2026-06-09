# Microsoft::IoT::ShellExtension::CTelemetryProvider::BrokerActivation::StartActivity(ushort const *)

- ea: `0x1800090a4`
- end: `0x180009149`
- name: `?StartActivity@BrokerActivation@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAAXPEBG@Z`
- size: `165`
- prototype: `void __fastcall(Microsoft::IoT::ShellExtension::CTelemetryProvider::BrokerActivation *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009690`

## callees

- `0x180001f70`
- `0x180008858`
- `0x180008ca0`
- `0x1800090a4`
- `0x1800095bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800090cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800090cd`

## pseudocode

```c
void __fastcall Microsoft::IoT::ShellExtension::CTelemetryProvider::BrokerActivation::StartActivity(
        Microsoft::IoT::ShellExtension::CTelemetryProvider::BrokerActivation *this,
        const unsigned __int16 *a2)
{
  const struct _tlgProvider_t *v4; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v6; // r8
  __int64 v7; // r9
  DWORD v8; // [rsp+60h] [rbp+8h] BYREF
  __int64 *v9; // [rsp+70h] [rbp+18h] BYREF
  __int64 v10; // [rsp+78h] [rbp+20h] BYREF

  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v4 = Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider();
  if ( *(_DWORD *)v4 > 5u )
  {
    v9 = (__int64 *)a2;
    CurrentThreadId = GetCurrentThreadId();
    v6 = *((_QWORD *)this + 34);
    v8 = CurrentThreadId;
    v10 = 0;
    if ( !*(_BYTE *)(v6 + 4)
      || (v7 = v6 + 24, !*(_DWORD *)(v6 + 24))
      && !*(_DWORD *)(v6 + 28)
      && !*(_DWORD *)(v6 + 32)
      && !*(_DWORD *)(v6 + 36) )
    {
      v7 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      (__int64)v4,
      (__int64)word_18001F3AA,
      v6 + 8,
      v7,
      (__int64)&v10,
      (__int64)&v8,
      &v9);
  }
  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x1800090a4  push    rbx
0x1800090a6  push    rsi
0x1800090a7  push    rdi
0x1800090a8  sub     rsp, 40h
0x1800090ac  mov     rdi, rdx
0x1800090af  mov     rbx, rcx
0x1800090b2  call    ?zInternalStart@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800090b7  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x1800090bc  mov     rsi, rax
0x1800090bf  mov     r8d, [rax]
0x1800090c2  cmp     r8d, 5
0x1800090c6  jbe     short loc_18000913A
0x1800090c8  mov     [rsp+58h+arg_10], rdi
0x1800090cd  call    cs:__imp_GetCurrentThreadId
0x1800090d3  mov     r8, [rbx+110h]
0x1800090da  mov     [rsp+58h+arg_0], eax
0x1800090de  xor     eax, eax
0x1800090e0  mov     [rsp+58h+arg_18], rax
0x1800090e5  cmp     [r8+4], al
0x1800090e9  jz      short loc_180009106
0x1800090eb  lea     r9, [r8+18h]
0x1800090ef  cmp     [r9], eax
0x1800090f2  jnz     short loc_180009109
0x1800090f4  cmp     [r9+4], eax
0x1800090f8  jnz     short loc_180009109
0x1800090fa  cmp     [r9+8], eax
0x1800090fe  jnz     short loc_180009109
0x180009100  cmp     [r9+0Ch], eax
0x180009104  jnz     short loc_180009109
0x180009106  mov     r9, rax
0x180009109  lea     rax, [rsp+58h+arg_10]
0x18000910e  add     r8, 8
0x180009112  mov     [rsp+58h+var_28], rax
0x180009117  lea     rdx, word_18001F3AA
0x18000911e  lea     rax, [rsp+58h+arg_0]
0x180009123  mov     rcx, rsi
0x180009126  mov     [rsp+58h+var_30], rax
0x18000912b  lea     rax, [rsp+58h+arg_18]
0x180009130  mov     [rsp+58h+var_38], rax
0x180009135  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18000913a  mov     rcx, rbx
0x18000913d  add     rsp, 40h
0x180009141  pop     rdi
0x180009142  pop     rsi
0x180009143  pop     rbx
0x180009144  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
