# IntlCplTraceLoggingTelemetry::CopySettingsToNewUserAccounts::StartActivity(void)

- ea: `0x180017fdc`
- end: `0x180018095`
- name: `?StartActivity@CopySettingsToNewUserAccounts@IntlCplTraceLoggingTelemetry@@QEAAXXZ`
- size: `185`
- prototype: `void __fastcall(IntlCplTraceLoggingTelemetry::CopySettingsToNewUserAccounts *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180017cf0`

## callees

- `0x1800017fc`
- `0x180001c24`
- `0x1800093fc`
- `0x18000cf70`
- `0x1800178f0`
- `0x180017fdc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018017`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018017`

## pseudocode

```c
void __fastcall IntlCplTraceLoggingTelemetry::CopySettingsToNewUserAccounts::StartActivity(
        IntlCplTraceLoggingTelemetry::CopySettingsToNewUserAccounts *this)
{
  const struct _tlgProvider_t *v2; // rax
  int v3; // edi
  __int64 v4; // r8
  int v5; // r9d
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v7; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = IntlCplTraceLogging::Provider();
  v3 = (int)v2;
  if ( *(_DWORD *)v2 > 5u && (unsigned __int8)tlgKeywordOn(v2, 0x200000000000LL) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v7 = 0;
    v4 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v4 + 4)
      || (v5 = v4 + 24, !*(_DWORD *)(v4 + 24))
      && !*(_DWORD *)(v4 + 28)
      && !*(_DWORD *)(v4 + 32)
      && !*(_DWORD *)(v4 + 36) )
    {
      v5 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v3,
      (unsigned int)&unk_180033D69,
      v4 + 8,
      v5,
      (__int64)&v7,
      (__int64)&CurrentThreadId);
  }
  wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x180017fdc  mov     [rsp+arg_10], rbx
0x180017fe1  push    rdi
0x180017fe2  sub     rsp, 30h
0x180017fe6  mov     rbx, rcx
0x180017fe9  call    ?zInternalStart@?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180017fee  call    ?Provider@IntlCplTraceLogging@@SAPEBU_tlgProvider_t@@XZ; IntlCplTraceLogging::Provider(void)
0x180017ff3  mov     rdi, rax
0x180017ff6  mov     edx, [rax]
0x180017ff8  cmp     edx, 5
0x180017ffb  jbe     loc_180018081
0x180018001  mov     rdx, 200000000000h
0x18001800b  mov     rcx, rax
0x18001800e  call    _tlgKeywordOn
0x180018013  test    al, al
0x180018015  jz      short loc_180018081
0x180018017  call    cs:__imp_GetCurrentThreadId
0x18001801d  mov     [rsp+38h+arg_0], eax
0x180018021  mov     [rsp+38h+arg_8], 0
0x18001802a  mov     r8, [rbx+110h]
0x180018031  cmp     byte ptr [r8+4], 0
0x180018036  jz      short loc_180018057
0x180018038  lea     r9, [r8+18h]
0x18001803c  cmp     dword ptr [r9], 0
0x180018040  jnz     short loc_18001805A
0x180018042  cmp     dword ptr [r9+4], 0
0x180018047  jnz     short loc_18001805A
0x180018049  cmp     dword ptr [r9+8], 0
0x18001804e  jnz     short loc_18001805A
0x180018050  cmp     dword ptr [r9+0Ch], 0
0x180018055  jnz     short loc_18001805A
0x180018057  xor     r9d, r9d
0x18001805a  add     r8, 8
0x18001805e  lea     rax, [rsp+38h+arg_0]
0x180018063  mov     [rsp+38h+var_10], rax
0x180018068  lea     rax, [rsp+38h+arg_8]
0x18001806d  mov     [rsp+38h+var_18], rax
0x180018072  lea     rdx, unk_180033D69
0x180018079  mov     rcx, rdi
0x18001807c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180018081  mov     rcx, rbx
0x180018084  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VIntlCplTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180018089  nop
0x18001808a  mov     rbx, [rsp+38h+arg_10]
0x18001808f  add     rsp, 30h
0x180018093  pop     rdi
0x180018094  retn
```
