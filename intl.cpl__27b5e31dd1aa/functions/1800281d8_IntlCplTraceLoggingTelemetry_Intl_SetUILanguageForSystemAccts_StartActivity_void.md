# IntlCplTraceLoggingTelemetry::Intl_SetUILanguageForSystemAccts::StartActivity(void)

- ea: `0x1800281d8`
- end: `0x180028291`
- name: `?StartActivity@Intl_SetUILanguageForSystemAccts@IntlCplTraceLoggingTelemetry@@QEAAXXZ`
- size: `185`
- prototype: `void __fastcall(IntlCplTraceLoggingTelemetry::Intl_SetUILanguageForSystemAccts *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180026994`

## callees

- `0x1800017fc`
- `0x180001c24`
- `0x1800093fc`
- `0x18000cf70`
- `0x1800178f0`
- `0x1800281d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028213`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028213`

## pseudocode

```c
void __fastcall IntlCplTraceLoggingTelemetry::Intl_SetUILanguageForSystemAccts::StartActivity(
        IntlCplTraceLoggingTelemetry::Intl_SetUILanguageForSystemAccts *this)
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
      (unsigned int)&unk_1800345AE,
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
0x1800281d8  mov     [rsp+arg_10], rbx
0x1800281dd  push    rdi
0x1800281de  sub     rsp, 30h
0x1800281e2  mov     rbx, rcx
0x1800281e5  call    ?zInternalStart@?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800281ea  call    ?Provider@IntlCplTraceLogging@@SAPEBU_tlgProvider_t@@XZ; IntlCplTraceLogging::Provider(void)
0x1800281ef  mov     rdi, rax
0x1800281f2  mov     edx, [rax]
0x1800281f4  cmp     edx, 5
0x1800281f7  jbe     loc_18002827D
0x1800281fd  mov     rdx, 200000000000h
0x180028207  mov     rcx, rax
0x18002820a  call    _tlgKeywordOn
0x18002820f  test    al, al
0x180028211  jz      short loc_18002827D
0x180028213  call    cs:__imp_GetCurrentThreadId
0x180028219  mov     [rsp+38h+arg_0], eax
0x18002821d  mov     [rsp+38h+arg_8], 0
0x180028226  mov     r8, [rbx+110h]
0x18002822d  cmp     byte ptr [r8+4], 0
0x180028232  jz      short loc_180028253
0x180028234  lea     r9, [r8+18h]
0x180028238  cmp     dword ptr [r9], 0
0x18002823c  jnz     short loc_180028256
0x18002823e  cmp     dword ptr [r9+4], 0
0x180028243  jnz     short loc_180028256
0x180028245  cmp     dword ptr [r9+8], 0
0x18002824a  jnz     short loc_180028256
0x18002824c  cmp     dword ptr [r9+0Ch], 0
0x180028251  jnz     short loc_180028256
0x180028253  xor     r9d, r9d
0x180028256  add     r8, 8
0x18002825a  lea     rax, [rsp+38h+arg_0]
0x18002825f  mov     [rsp+38h+var_10], rax
0x180028264  lea     rax, [rsp+38h+arg_8]
0x180028269  mov     [rsp+38h+var_18], rax
0x18002826e  lea     rdx, unk_1800345AE
0x180028275  mov     rcx, rdi
0x180028278  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18002827d  mov     rcx, rbx
0x180028280  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VIntlCplTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180028285  nop
0x180028286  mov     rbx, [rsp+38h+arg_10]
0x18002828b  add     rsp, 30h
0x18002828f  pop     rdi
0x180028290  retn
```
