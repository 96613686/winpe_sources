# IntlCplTraceLoggingTelemetry::SetRegionalAndLanguageSettings::StartActivity(void)

- ea: `0x18000e730`
- end: `0x18000e7c8`
- name: `?StartActivity@SetRegionalAndLanguageSettings@IntlCplTraceLoggingTelemetry@@QEAAXXZ`
- size: `152`
- prototype: `void __fastcall(IntlCplTraceLoggingTelemetry::SetRegionalAndLanguageSettings *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000dce0`

## callees

- `0x180001c24`
- `0x1800093fc`
- `0x18000cf70`
- `0x18000e730`
- `0x18000f558`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e751`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e751`

## pseudocode

```c
void __fastcall IntlCplTraceLoggingTelemetry::SetRegionalAndLanguageSettings::StartActivity(
        IntlCplTraceLoggingTelemetry::SetRegionalAndLanguageSettings *this)
{
  const struct _tlgProvider_t *v2; // rax
  int v3; // edi
  __int64 v4; // r8
  int v5; // r9d
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v7; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = IntlCplTraceLogging::Provider();
  v3 = (int)v2;
  if ( *(_DWORD *)v2 > 5u )
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
      (unsigned int)&unk_180032E9C,
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
0x18000e730  mov     [rsp+arg_10], rbx
0x18000e735  push    rdi
0x18000e736  sub     rsp, 30h
0x18000e73a  mov     rbx, rcx
0x18000e73d  call    ?zInternalStart@?$ActivityBase@VIntlCplTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000e742  call    ?Provider@IntlCplTraceLogging@@SAPEBU_tlgProvider_t@@XZ; IntlCplTraceLogging::Provider(void)
0x18000e747  mov     rdi, rax
0x18000e74a  mov     edx, [rax]
0x18000e74c  cmp     edx, 5
0x18000e74f  jbe     short loc_18000E7B4
0x18000e751  call    cs:__imp_GetCurrentThreadId
0x18000e757  mov     [rsp+38h+arg_0], eax
0x18000e75b  xor     eax, eax
0x18000e75d  mov     [rsp+38h+arg_8], rax
0x18000e762  mov     r8, [rbx+110h]
0x18000e769  cmp     [r8+4], al
0x18000e76d  jz      short loc_18000E78A
0x18000e76f  lea     r9, [r8+18h]
0x18000e773  cmp     [r9], eax
0x18000e776  jnz     short loc_18000E78D
0x18000e778  cmp     [r9+4], eax
0x18000e77c  jnz     short loc_18000E78D
0x18000e77e  cmp     [r9+8], eax
0x18000e782  jnz     short loc_18000E78D
0x18000e784  cmp     [r9+0Ch], eax
0x18000e788  jnz     short loc_18000E78D
0x18000e78a  mov     r9, rax
0x18000e78d  add     r8, 8
0x18000e791  lea     rax, [rsp+38h+arg_0]
0x18000e796  mov     [rsp+38h+var_10], rax
0x18000e79b  lea     rax, [rsp+38h+arg_8]
0x18000e7a0  mov     [rsp+38h+var_18], rax
0x18000e7a5  lea     rdx, unk_180032E9C
0x18000e7ac  mov     rcx, rdi
0x18000e7af  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18000e7b4  mov     rcx, rbx
0x18000e7b7  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VIntlCplTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18000e7bc  nop
0x18000e7bd  mov     rbx, [rsp+38h+arg_10]
0x18000e7c2  add     rsp, 30h
0x18000e7c6  pop     rdi
0x18000e7c7  retn
```
