# IntlCplTraceLoggingTelemetry::CopySettingsToSystemAccounts::StartActivity(void)

- ea: `0x18001809c`
- end: `0x180018155`
- name: `?StartActivity@CopySettingsToSystemAccounts@IntlCplTraceLoggingTelemetry@@QEAAXXZ`
- size: `185`
- prototype: `void __fastcall(IntlCplTraceLoggingTelemetry::CopySettingsToSystemAccounts *__hidden this)`
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
- `0x18001809c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800180d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800180d7`

## pseudocode

```c
void __fastcall IntlCplTraceLoggingTelemetry::CopySettingsToSystemAccounts::StartActivity(
        IntlCplTraceLoggingTelemetry::CopySettingsToSystemAccounts *this)
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
      (unsigned int)&unk_180033DBE,
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
0x18001809c  mov     [rsp+arg_10], rbx
0x1800180a1  push    rdi
0x1800180a2  sub     rsp, 30h
0x1800180a6  mov     rbx, rcx
0x1800180a9  call    ?zInternalStart@?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800180ae  call    ?Provider@IntlCplTraceLogging@@SAPEBU_tlgProvider_t@@XZ; IntlCplTraceLogging::Provider(void)
0x1800180b3  mov     rdi, rax
0x1800180b6  mov     edx, [rax]
0x1800180b8  cmp     edx, 5
0x1800180bb  jbe     loc_180018141
0x1800180c1  mov     rdx, 200000000000h
0x1800180cb  mov     rcx, rax
0x1800180ce  call    _tlgKeywordOn
0x1800180d3  test    al, al
0x1800180d5  jz      short loc_180018141
0x1800180d7  call    cs:__imp_GetCurrentThreadId
0x1800180dd  mov     [rsp+38h+arg_0], eax
0x1800180e1  mov     [rsp+38h+arg_8], 0
0x1800180ea  mov     r8, [rbx+110h]
0x1800180f1  cmp     byte ptr [r8+4], 0
0x1800180f6  jz      short loc_180018117
0x1800180f8  lea     r9, [r8+18h]
0x1800180fc  cmp     dword ptr [r9], 0
0x180018100  jnz     short loc_18001811A
0x180018102  cmp     dword ptr [r9+4], 0
0x180018107  jnz     short loc_18001811A
0x180018109  cmp     dword ptr [r9+8], 0
0x18001810e  jnz     short loc_18001811A
0x180018110  cmp     dword ptr [r9+0Ch], 0
0x180018115  jnz     short loc_18001811A
0x180018117  xor     r9d, r9d
0x18001811a  add     r8, 8
0x18001811e  lea     rax, [rsp+38h+arg_0]
0x180018123  mov     [rsp+38h+var_10], rax
0x180018128  lea     rax, [rsp+38h+arg_8]
0x18001812d  mov     [rsp+38h+var_18], rax
0x180018132  lea     rdx, unk_180033DBE
0x180018139  mov     rcx, rdi
0x18001813c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180018141  mov     rcx, rbx
0x180018144  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VIntlCplTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180018149  nop
0x18001814a  mov     rbx, [rsp+38h+arg_10]
0x18001814f  add     rsp, 30h
0x180018153  pop     rdi
0x180018154  retn
```
