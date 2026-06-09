# AdvancedSettingsTelemetry::CommitFileSharing::StartActivity(void)

- ea: `0x1800136e4`
- end: `0x18001379b`
- name: `?StartActivity@CommitFileSharing@AdvancedSettingsTelemetry@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(AdvancedSettingsTelemetry::CommitFileSharing *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014f30`

## callees

- `0x1800013ac`
- `0x180001bac`
- `0x180007648`
- `0x18000845c`
- `0x18000b0e4`
- `0x1800136e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001371f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001371f`

## pseudocode

```c
void __fastcall AdvancedSettingsTelemetry::CommitFileSharing::StartActivity(
        AdvancedSettingsTelemetry::CommitFileSharing *this)
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
      (unsigned int)&unk_180022AB8,
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
0x1800136e4  mov     [rsp+arg_10], rbx
0x1800136e9  push    rdi
0x1800136ea  sub     rsp, 30h
0x1800136ee  mov     rbx, rcx
0x1800136f1  call    ?zInternalStart@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800136f6  call    ?Provider@AdvancedSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; AdvancedSettingsLogging::Provider(void)
0x1800136fb  mov     rdi, rax
0x1800136fe  mov     edx, [rax]
0x180013700  cmp     edx, 5
0x180013703  jbe     loc_180013789
0x180013709  mov     rdx, 200000000000h
0x180013713  mov     rcx, rax
0x180013716  call    _tlgKeywordOn
0x18001371b  test    al, al
0x18001371d  jz      short loc_180013789
0x18001371f  call    cs:__imp_GetCurrentThreadId
0x180013725  mov     r8, [rbx+110h]
0x18001372c  mov     [rsp+38h+arg_0], eax
0x180013730  mov     [rsp+38h+arg_8], 0
0x180013739  cmp     byte ptr [r8+4], 0
0x18001373e  jz      short loc_18001375F
0x180013740  lea     r9, [r8+18h]
0x180013744  cmp     dword ptr [r9], 0
0x180013748  jnz     short loc_180013762
0x18001374a  cmp     dword ptr [r9+4], 0
0x18001374f  jnz     short loc_180013762
0x180013751  cmp     dword ptr [r9+8], 0
0x180013756  jnz     short loc_180013762
0x180013758  cmp     dword ptr [r9+0Ch], 0
0x18001375d  jnz     short loc_180013762
0x18001375f  xor     r9d, r9d
0x180013762  lea     rax, [rsp+38h+arg_0]
0x180013767  add     r8, 8
0x18001376b  mov     [rsp+38h+var_10], rax
0x180013770  lea     rdx, unk_180022AB8
0x180013777  lea     rax, [rsp+38h+arg_8]
0x18001377c  mov     rcx, rdi
0x18001377f  mov     [rsp+38h+var_18], rax
0x180013784  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180013789  mov     rcx, rbx
0x18001378c  mov     rbx, [rsp+38h+arg_10]
0x180013791  add     rsp, 30h
0x180013795  pop     rdi
0x180013796  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
