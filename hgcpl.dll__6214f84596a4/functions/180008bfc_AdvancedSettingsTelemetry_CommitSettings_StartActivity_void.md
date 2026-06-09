# AdvancedSettingsTelemetry::CommitSettings::StartActivity(void)

- ea: `0x180008bfc`
- end: `0x180008cb3`
- name: `?StartActivity@CommitSettings@AdvancedSettingsTelemetry@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(AdvancedSettingsTelemetry::CommitSettings *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a9c0`

## callees

- `0x1800013ac`
- `0x180001bac`
- `0x180007648`
- `0x18000845c`
- `0x180008bfc`
- `0x18000b0e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008c37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008c37`

## pseudocode

```c
void __fastcall AdvancedSettingsTelemetry::CommitSettings::StartActivity(
        AdvancedSettingsTelemetry::CommitSettings *this)
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
      (unsigned int)&word_1800213DE,
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
0x180008bfc  mov     [rsp+arg_10], rbx
0x180008c01  push    rdi
0x180008c02  sub     rsp, 30h
0x180008c06  mov     rbx, rcx
0x180008c09  call    ?zInternalStart@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180008c0e  call    ?Provider@AdvancedSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; AdvancedSettingsLogging::Provider(void)
0x180008c13  mov     rdi, rax
0x180008c16  mov     edx, [rax]
0x180008c18  cmp     edx, 5
0x180008c1b  jbe     loc_180008CA1
0x180008c21  mov     rdx, 200000000000h
0x180008c2b  mov     rcx, rax
0x180008c2e  call    _tlgKeywordOn
0x180008c33  test    al, al
0x180008c35  jz      short loc_180008CA1
0x180008c37  call    cs:__imp_GetCurrentThreadId
0x180008c3d  mov     r8, [rbx+110h]
0x180008c44  mov     [rsp+38h+arg_0], eax
0x180008c48  mov     [rsp+38h+arg_8], 0
0x180008c51  cmp     byte ptr [r8+4], 0
0x180008c56  jz      short loc_180008C77
0x180008c58  lea     r9, [r8+18h]
0x180008c5c  cmp     dword ptr [r9], 0
0x180008c60  jnz     short loc_180008C7A
0x180008c62  cmp     dword ptr [r9+4], 0
0x180008c67  jnz     short loc_180008C7A
0x180008c69  cmp     dword ptr [r9+8], 0
0x180008c6e  jnz     short loc_180008C7A
0x180008c70  cmp     dword ptr [r9+0Ch], 0
0x180008c75  jnz     short loc_180008C7A
0x180008c77  xor     r9d, r9d
0x180008c7a  lea     rax, [rsp+38h+arg_0]
0x180008c7f  add     r8, 8
0x180008c83  mov     [rsp+38h+var_10], rax
0x180008c88  lea     rdx, word_1800213DE
0x180008c8f  lea     rax, [rsp+38h+arg_8]
0x180008c94  mov     rcx, rdi
0x180008c97  mov     [rsp+38h+var_18], rax
0x180008c9c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180008ca1  mov     rcx, rbx
0x180008ca4  mov     rbx, [rsp+38h+arg_10]
0x180008ca9  add     rsp, 30h
0x180008cad  pop     rdi
0x180008cae  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
