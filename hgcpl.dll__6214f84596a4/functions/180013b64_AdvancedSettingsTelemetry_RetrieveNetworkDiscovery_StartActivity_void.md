# AdvancedSettingsTelemetry::RetrieveNetworkDiscovery::StartActivity(void)

- ea: `0x180013b64`
- end: `0x180013c1b`
- name: `?StartActivity@RetrieveNetworkDiscovery@AdvancedSettingsTelemetry@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(AdvancedSettingsTelemetry::RetrieveNetworkDiscovery *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800159cc`

## callees

- `0x1800013ac`
- `0x180001bac`
- `0x180007648`
- `0x18000845c`
- `0x18000b0e4`
- `0x180013b64`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013b9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013b9f`

## pseudocode

```c
void __fastcall AdvancedSettingsTelemetry::RetrieveNetworkDiscovery::StartActivity(
        AdvancedSettingsTelemetry::RetrieveNetworkDiscovery *this)
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
      (unsigned int)byte_180022C7D,
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
0x180013b64  mov     [rsp+arg_10], rbx
0x180013b69  push    rdi
0x180013b6a  sub     rsp, 30h
0x180013b6e  mov     rbx, rcx
0x180013b71  call    ?zInternalStart@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180013b76  call    ?Provider@AdvancedSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; AdvancedSettingsLogging::Provider(void)
0x180013b7b  mov     rdi, rax
0x180013b7e  mov     edx, [rax]
0x180013b80  cmp     edx, 5
0x180013b83  jbe     loc_180013C09
0x180013b89  mov     rdx, 200000000000h
0x180013b93  mov     rcx, rax
0x180013b96  call    _tlgKeywordOn
0x180013b9b  test    al, al
0x180013b9d  jz      short loc_180013C09
0x180013b9f  call    cs:__imp_GetCurrentThreadId
0x180013ba5  mov     r8, [rbx+110h]
0x180013bac  mov     [rsp+38h+arg_0], eax
0x180013bb0  mov     [rsp+38h+arg_8], 0
0x180013bb9  cmp     byte ptr [r8+4], 0
0x180013bbe  jz      short loc_180013BDF
0x180013bc0  lea     r9, [r8+18h]
0x180013bc4  cmp     dword ptr [r9], 0
0x180013bc8  jnz     short loc_180013BE2
0x180013bca  cmp     dword ptr [r9+4], 0
0x180013bcf  jnz     short loc_180013BE2
0x180013bd1  cmp     dword ptr [r9+8], 0
0x180013bd6  jnz     short loc_180013BE2
0x180013bd8  cmp     dword ptr [r9+0Ch], 0
0x180013bdd  jnz     short loc_180013BE2
0x180013bdf  xor     r9d, r9d
0x180013be2  lea     rax, [rsp+38h+arg_0]
0x180013be7  add     r8, 8
0x180013beb  mov     [rsp+38h+var_10], rax
0x180013bf0  lea     rdx, byte_180022C7D
0x180013bf7  lea     rax, [rsp+38h+arg_8]
0x180013bfc  mov     rcx, rdi
0x180013bff  mov     [rsp+38h+var_18], rax
0x180013c04  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180013c09  mov     rcx, rbx
0x180013c0c  mov     rbx, [rsp+38h+arg_10]
0x180013c11  add     rsp, 30h
0x180013c15  pop     rdi
0x180013c16  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
