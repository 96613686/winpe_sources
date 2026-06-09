# IntlCplTraceLoggingTelemetry::OpeningIntlCpl::StartActivity(void)

- ea: `0x180016d40`
- end: `0x180016df9`
- name: `?StartActivity@OpeningIntlCpl@IntlCplTraceLoggingTelemetry@@QEAAXXZ`
- size: `185`
- prototype: `void __fastcall(IntlCplTraceLoggingTelemetry::OpeningIntlCpl *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180014c90`

## callees

- `0x1800017fc`
- `0x180001c24`
- `0x1800093fc`
- `0x18000cf70`
- `0x180016d40`
- `0x1800178f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016d7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016d7b`

## pseudocode

```c
void __fastcall IntlCplTraceLoggingTelemetry::OpeningIntlCpl::StartActivity(
        IntlCplTraceLoggingTelemetry::OpeningIntlCpl *this)
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
      (unsigned int)&unk_1800338DC,
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
0x180016d40  mov     [rsp+arg_10], rbx
0x180016d45  push    rdi
0x180016d46  sub     rsp, 30h
0x180016d4a  mov     rbx, rcx
0x180016d4d  call    ?zInternalStart@?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180016d52  call    ?Provider@IntlCplTraceLogging@@SAPEBU_tlgProvider_t@@XZ; IntlCplTraceLogging::Provider(void)
0x180016d57  mov     rdi, rax
0x180016d5a  mov     edx, [rax]
0x180016d5c  cmp     edx, 5
0x180016d5f  jbe     loc_180016DE5
0x180016d65  mov     rdx, 200000000000h
0x180016d6f  mov     rcx, rax
0x180016d72  call    _tlgKeywordOn
0x180016d77  test    al, al
0x180016d79  jz      short loc_180016DE5
0x180016d7b  call    cs:__imp_GetCurrentThreadId
0x180016d81  mov     [rsp+38h+arg_0], eax
0x180016d85  mov     [rsp+38h+arg_8], 0
0x180016d8e  mov     r8, [rbx+110h]
0x180016d95  cmp     byte ptr [r8+4], 0
0x180016d9a  jz      short loc_180016DBB
0x180016d9c  lea     r9, [r8+18h]
0x180016da0  cmp     dword ptr [r9], 0
0x180016da4  jnz     short loc_180016DBE
0x180016da6  cmp     dword ptr [r9+4], 0
0x180016dab  jnz     short loc_180016DBE
0x180016dad  cmp     dword ptr [r9+8], 0
0x180016db2  jnz     short loc_180016DBE
0x180016db4  cmp     dword ptr [r9+0Ch], 0
0x180016db9  jnz     short loc_180016DBE
0x180016dbb  xor     r9d, r9d
0x180016dbe  add     r8, 8
0x180016dc2  lea     rax, [rsp+38h+arg_0]
0x180016dc7  mov     [rsp+38h+var_10], rax
0x180016dcc  lea     rax, [rsp+38h+arg_8]
0x180016dd1  mov     [rsp+38h+var_18], rax
0x180016dd6  lea     rdx, unk_1800338DC
0x180016ddd  mov     rcx, rdi
0x180016de0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180016de5  mov     rcx, rbx
0x180016de8  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VIntlCplTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180016ded  nop
0x180016dee  mov     rbx, [rsp+38h+arg_10]
0x180016df3  add     rsp, 30h
0x180016df7  pop     rdi
0x180016df8  retn
```
