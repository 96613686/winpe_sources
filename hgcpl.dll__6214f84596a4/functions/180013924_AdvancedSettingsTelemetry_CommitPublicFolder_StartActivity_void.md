# AdvancedSettingsTelemetry::CommitPublicFolder::StartActivity(void)

- ea: `0x180013924`
- end: `0x1800139db`
- name: `?StartActivity@CommitPublicFolder@AdvancedSettingsTelemetry@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(AdvancedSettingsTelemetry::CommitPublicFolder *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800154e8`

## callees

- `0x1800013ac`
- `0x180001bac`
- `0x180007648`
- `0x18000845c`
- `0x18000b0e4`
- `0x180013924`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001395f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001395f`

## pseudocode

```c
void __fastcall AdvancedSettingsTelemetry::CommitPublicFolder::StartActivity(
        AdvancedSettingsTelemetry::CommitPublicFolder *this)
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
      (unsigned int)byte_180022675,
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
0x180013924  mov     [rsp+arg_10], rbx
0x180013929  push    rdi
0x18001392a  sub     rsp, 30h
0x18001392e  mov     rbx, rcx
0x180013931  call    ?zInternalStart@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180013936  call    ?Provider@AdvancedSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; AdvancedSettingsLogging::Provider(void)
0x18001393b  mov     rdi, rax
0x18001393e  mov     edx, [rax]
0x180013940  cmp     edx, 5
0x180013943  jbe     loc_1800139C9
0x180013949  mov     rdx, 200000000000h
0x180013953  mov     rcx, rax
0x180013956  call    _tlgKeywordOn
0x18001395b  test    al, al
0x18001395d  jz      short loc_1800139C9
0x18001395f  call    cs:__imp_GetCurrentThreadId
0x180013965  mov     r8, [rbx+110h]
0x18001396c  mov     [rsp+38h+arg_0], eax
0x180013970  mov     [rsp+38h+arg_8], 0
0x180013979  cmp     byte ptr [r8+4], 0
0x18001397e  jz      short loc_18001399F
0x180013980  lea     r9, [r8+18h]
0x180013984  cmp     dword ptr [r9], 0
0x180013988  jnz     short loc_1800139A2
0x18001398a  cmp     dword ptr [r9+4], 0
0x18001398f  jnz     short loc_1800139A2
0x180013991  cmp     dword ptr [r9+8], 0
0x180013996  jnz     short loc_1800139A2
0x180013998  cmp     dword ptr [r9+0Ch], 0
0x18001399d  jnz     short loc_1800139A2
0x18001399f  xor     r9d, r9d
0x1800139a2  lea     rax, [rsp+38h+arg_0]
0x1800139a7  add     r8, 8
0x1800139ab  mov     [rsp+38h+var_10], rax
0x1800139b0  lea     rdx, byte_180022675
0x1800139b7  lea     rax, [rsp+38h+arg_8]
0x1800139bc  mov     rcx, rdi
0x1800139bf  mov     [rsp+38h+var_18], rax
0x1800139c4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800139c9  mov     rcx, rbx
0x1800139cc  mov     rbx, [rsp+38h+arg_10]
0x1800139d1  add     rsp, 30h
0x1800139d5  pop     rdi
0x1800139d6  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
