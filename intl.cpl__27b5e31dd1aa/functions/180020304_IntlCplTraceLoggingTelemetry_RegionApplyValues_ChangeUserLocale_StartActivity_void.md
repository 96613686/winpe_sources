# IntlCplTraceLoggingTelemetry::RegionApplyValues_ChangeUserLocale::StartActivity(void)

- ea: `0x180020304`
- end: `0x1800203bd`
- name: `?StartActivity@RegionApplyValues_ChangeUserLocale@IntlCplTraceLoggingTelemetry@@QEAAXXZ`
- size: `185`
- prototype: `void __fastcall(IntlCplTraceLoggingTelemetry::RegionApplyValues_ChangeUserLocale *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001ebc8`

## callees

- `0x1800017fc`
- `0x180001c24`
- `0x1800093fc`
- `0x18000cf70`
- `0x1800178f0`
- `0x180020304`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002033f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002033f`

## pseudocode

```c
void __fastcall IntlCplTraceLoggingTelemetry::RegionApplyValues_ChangeUserLocale::StartActivity(
        IntlCplTraceLoggingTelemetry::RegionApplyValues_ChangeUserLocale *this)
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
      (unsigned int)&unk_180034136,
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
0x180020304  mov     [rsp+arg_10], rbx
0x180020309  push    rdi
0x18002030a  sub     rsp, 30h
0x18002030e  mov     rbx, rcx
0x180020311  call    ?zInternalStart@?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180020316  call    ?Provider@IntlCplTraceLogging@@SAPEBU_tlgProvider_t@@XZ; IntlCplTraceLogging::Provider(void)
0x18002031b  mov     rdi, rax
0x18002031e  mov     edx, [rax]
0x180020320  cmp     edx, 5
0x180020323  jbe     loc_1800203A9
0x180020329  mov     rdx, 200000000000h
0x180020333  mov     rcx, rax
0x180020336  call    _tlgKeywordOn
0x18002033b  test    al, al
0x18002033d  jz      short loc_1800203A9
0x18002033f  call    cs:__imp_GetCurrentThreadId
0x180020345  mov     [rsp+38h+arg_0], eax
0x180020349  mov     [rsp+38h+arg_8], 0
0x180020352  mov     r8, [rbx+110h]
0x180020359  cmp     byte ptr [r8+4], 0
0x18002035e  jz      short loc_18002037F
0x180020360  lea     r9, [r8+18h]
0x180020364  cmp     dword ptr [r9], 0
0x180020368  jnz     short loc_180020382
0x18002036a  cmp     dword ptr [r9+4], 0
0x18002036f  jnz     short loc_180020382
0x180020371  cmp     dword ptr [r9+8], 0
0x180020376  jnz     short loc_180020382
0x180020378  cmp     dword ptr [r9+0Ch], 0
0x18002037d  jnz     short loc_180020382
0x18002037f  xor     r9d, r9d
0x180020382  add     r8, 8
0x180020386  lea     rax, [rsp+38h+arg_0]
0x18002038b  mov     [rsp+38h+var_10], rax
0x180020390  lea     rax, [rsp+38h+arg_8]
0x180020395  mov     [rsp+38h+var_18], rax
0x18002039a  lea     rdx, unk_180034136
0x1800203a1  mov     rcx, rdi
0x1800203a4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800203a9  mov     rcx, rbx
0x1800203ac  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VIntlCplTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1800203b1  nop
0x1800203b2  mov     rbx, [rsp+38h+arg_10]
0x1800203b7  add     rsp, 30h
0x1800203bb  pop     rdi
0x1800203bc  retn
```
