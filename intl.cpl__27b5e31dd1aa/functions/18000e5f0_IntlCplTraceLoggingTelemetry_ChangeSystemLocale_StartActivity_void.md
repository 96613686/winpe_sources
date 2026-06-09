# IntlCplTraceLoggingTelemetry::ChangeSystemLocale::StartActivity(void)

- ea: `0x18000e5f0`
- end: `0x18000e688`
- name: `?StartActivity@ChangeSystemLocale@IntlCplTraceLoggingTelemetry@@QEAAXXZ`
- size: `152`
- prototype: `void __fastcall(IntlCplTraceLoggingTelemetry::ChangeSystemLocale *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000ba98`

## callees

- `0x180001c24`
- `0x1800093fc`
- `0x18000cf70`
- `0x18000e5f0`
- `0x18000f558`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e611`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e611`

## pseudocode

```c
void __fastcall IntlCplTraceLoggingTelemetry::ChangeSystemLocale::StartActivity(
        IntlCplTraceLoggingTelemetry::ChangeSystemLocale *this)
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
      (unsigned int)&unk_180032EF2,
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
0x18000e5f0  mov     [rsp+arg_10], rbx
0x18000e5f5  push    rdi
0x18000e5f6  sub     rsp, 30h
0x18000e5fa  mov     rbx, rcx
0x18000e5fd  call    ?zInternalStart@?$ActivityBase@VIntlCplTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000e602  call    ?Provider@IntlCplTraceLogging@@SAPEBU_tlgProvider_t@@XZ; IntlCplTraceLogging::Provider(void)
0x18000e607  mov     rdi, rax
0x18000e60a  mov     edx, [rax]
0x18000e60c  cmp     edx, 5
0x18000e60f  jbe     short loc_18000E674
0x18000e611  call    cs:__imp_GetCurrentThreadId
0x18000e617  mov     [rsp+38h+arg_0], eax
0x18000e61b  xor     eax, eax
0x18000e61d  mov     [rsp+38h+arg_8], rax
0x18000e622  mov     r8, [rbx+110h]
0x18000e629  cmp     [r8+4], al
0x18000e62d  jz      short loc_18000E64A
0x18000e62f  lea     r9, [r8+18h]
0x18000e633  cmp     [r9], eax
0x18000e636  jnz     short loc_18000E64D
0x18000e638  cmp     [r9+4], eax
0x18000e63c  jnz     short loc_18000E64D
0x18000e63e  cmp     [r9+8], eax
0x18000e642  jnz     short loc_18000E64D
0x18000e644  cmp     [r9+0Ch], eax
0x18000e648  jnz     short loc_18000E64D
0x18000e64a  mov     r9, rax
0x18000e64d  add     r8, 8
0x18000e651  lea     rax, [rsp+38h+arg_0]
0x18000e656  mov     [rsp+38h+var_10], rax
0x18000e65b  lea     rax, [rsp+38h+arg_8]
0x18000e660  mov     [rsp+38h+var_18], rax
0x18000e665  lea     rdx, unk_180032EF2
0x18000e66c  mov     rcx, rdi
0x18000e66f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18000e674  mov     rcx, rbx
0x18000e677  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VIntlCplTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18000e67c  nop
0x18000e67d  mov     rbx, [rsp+38h+arg_10]
0x18000e682  add     rsp, 30h
0x18000e686  pop     rdi
0x18000e687  retn
```
