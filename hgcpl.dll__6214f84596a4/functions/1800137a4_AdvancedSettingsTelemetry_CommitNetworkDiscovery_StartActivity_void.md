# AdvancedSettingsTelemetry::CommitNetworkDiscovery::StartActivity(void)

- ea: `0x1800137a4`
- end: `0x18001385b`
- name: `?StartActivity@CommitNetworkDiscovery@AdvancedSettingsTelemetry@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(AdvancedSettingsTelemetry::CommitNetworkDiscovery *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800151fc`

## callees

- `0x1800013ac`
- `0x180001bac`
- `0x180007648`
- `0x18000845c`
- `0x18000b0e4`
- `0x1800137a4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800137df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800137df`

## pseudocode

```c
void __fastcall AdvancedSettingsTelemetry::CommitNetworkDiscovery::StartActivity(
        AdvancedSettingsTelemetry::CommitNetworkDiscovery *this)
{
  const struct _tlgProvider_t *v2; // rax
  int v3; // edi
  DWORD CurrentThreadId; // eax
  __int64 v5; // r8
  int v6; // r9d
  DWORD v7; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = AdvancedSettingsLogging::Provider();
  v3 = (int)v2;
  if ( *(_DWORD *)v2 > 5u && (unsigned __int8)tlgKeywordOn(v2, 0x200000000000LL) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v5 = *((_QWORD *)this + 34);
    v7 = CurrentThreadId;
    v8 = 0;
    if ( !*(_BYTE *)(v5 + 4)
      || (v6 = v5 + 24, !*(_DWORD *)(v5 + 24))
      && !*(_DWORD *)(v5 + 28)
      && !*(_DWORD *)(v5 + 32)
      && !*(_DWORD *)(v5 + 36) )
    {
      v6 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v3,
      (unsigned int)byte_180022B01,
      v5 + 8,
      v6,
      (__int64)&v8,
      (__int64)&v7);
  }
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x1800137a4  mov     [rsp+arg_10], rbx
0x1800137a9  push    rdi
0x1800137aa  sub     rsp, 30h
0x1800137ae  mov     rbx, rcx
0x1800137b1  call    ?zInternalStart@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800137b6  call    ?Provider@AdvancedSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; AdvancedSettingsLogging::Provider(void)
0x1800137bb  mov     rdi, rax
0x1800137be  mov     edx, [rax]
0x1800137c0  cmp     edx, 5
0x1800137c3  jbe     loc_180013849
0x1800137c9  mov     rdx, 200000000000h
0x1800137d3  mov     rcx, rax
0x1800137d6  call    _tlgKeywordOn
0x1800137db  test    al, al
0x1800137dd  jz      short loc_180013849
0x1800137df  call    cs:__imp_GetCurrentThreadId
0x1800137e5  mov     r8, [rbx+110h]
0x1800137ec  mov     [rsp+38h+arg_0], eax
0x1800137f0  mov     [rsp+38h+arg_8], 0
0x1800137f9  cmp     byte ptr [r8+4], 0
0x1800137fe  jz      short loc_18001381F
0x180013800  lea     r9, [r8+18h]
0x180013804  cmp     dword ptr [r9], 0
0x180013808  jnz     short loc_180013822
0x18001380a  cmp     dword ptr [r9+4], 0
0x18001380f  jnz     short loc_180013822
0x180013811  cmp     dword ptr [r9+8], 0
0x180013816  jnz     short loc_180013822
0x180013818  cmp     dword ptr [r9+0Ch], 0
0x18001381d  jnz     short loc_180013822
0x18001381f  xor     r9d, r9d
0x180013822  lea     rax, [rsp+38h+arg_0]
0x180013827  add     r8, 8
0x18001382b  mov     [rsp+38h+var_10], rax
0x180013830  lea     rdx, byte_180022B01
0x180013837  lea     rax, [rsp+38h+arg_8]
0x18001383c  mov     rcx, rdi
0x18001383f  mov     [rsp+38h+var_18], rax
0x180013844  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180013849  mov     rcx, rbx
0x18001384c  mov     rbx, [rsp+38h+arg_10]
0x180013851  add     rsp, 30h
0x180013855  pop     rdi
0x180013856  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
