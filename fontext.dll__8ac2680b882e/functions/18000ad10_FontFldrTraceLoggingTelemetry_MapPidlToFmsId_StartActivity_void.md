# FontFldrTraceLoggingTelemetry::_MapPidlToFmsId::StartActivity(void)

- ea: `0x18000ad10`
- end: `0x18000ada6`
- name: `?StartActivity@_MapPidlToFmsId@FontFldrTraceLoggingTelemetry@@QEAAXXZ`
- size: `150`
- prototype: `void __fastcall(FontFldrTraceLoggingTelemetry::_MapPidlToFmsId *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180010024`

## callees

- `0x180001628`
- `0x180009304`
- `0x180009930`
- `0x18000ad10`
- `0x1800103c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ad31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ad31`

## pseudocode

```c
void __fastcall FontFldrTraceLoggingTelemetry::_MapPidlToFmsId::StartActivity(
        FontFldrTraceLoggingTelemetry::_MapPidlToFmsId *this)
{
  const struct _tlgProvider_t *v2; // rax
  int v3; // edi
  DWORD CurrentThreadId; // eax
  __int64 v5; // r8
  int v6; // r9d
  DWORD v7; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = FontFldrTraceLogging::Provider();
  v3 = (int)v2;
  if ( *(_DWORD *)v2 > 5u )
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
      (unsigned int)byte_18003CBED,
      v5 + 8,
      v6,
      (__int64)&v8,
      (__int64)&v7);
  }
  wil::ActivityBase<FontFldrTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x18000ad10  mov     [rsp+arg_10], rbx
0x18000ad15  push    rdi
0x18000ad16  sub     rsp, 30h
0x18000ad1a  mov     rbx, rcx
0x18000ad1d  call    ?zInternalStart@?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000ad22  call    ?Provider@FontFldrTraceLogging@@SAPEBU_tlgProvider_t@@XZ; FontFldrTraceLogging::Provider(void)
0x18000ad27  mov     rdi, rax
0x18000ad2a  mov     edx, [rax]
0x18000ad2c  cmp     edx, 5
0x18000ad2f  jbe     short loc_18000AD94
0x18000ad31  call    cs:__imp_GetCurrentThreadId
0x18000ad37  mov     r8, [rbx+110h]
0x18000ad3e  mov     [rsp+38h+arg_0], eax
0x18000ad42  xor     eax, eax
0x18000ad44  mov     [rsp+38h+arg_8], rax
0x18000ad49  cmp     [r8+4], al
0x18000ad4d  jz      short loc_18000AD6A
0x18000ad4f  lea     r9, [r8+18h]
0x18000ad53  cmp     [r9], eax
0x18000ad56  jnz     short loc_18000AD6D
0x18000ad58  cmp     [r9+4], eax
0x18000ad5c  jnz     short loc_18000AD6D
0x18000ad5e  cmp     [r9+8], eax
0x18000ad62  jnz     short loc_18000AD6D
0x18000ad64  cmp     [r9+0Ch], eax
0x18000ad68  jnz     short loc_18000AD6D
0x18000ad6a  mov     r9, rax
0x18000ad6d  lea     rax, [rsp+38h+arg_0]
0x18000ad72  add     r8, 8
0x18000ad76  mov     [rsp+38h+var_10], rax
0x18000ad7b  lea     rdx, byte_18003CBED
0x18000ad82  lea     rax, [rsp+38h+arg_8]
0x18000ad87  mov     rcx, rdi
0x18000ad8a  mov     [rsp+38h+var_18], rax
0x18000ad8f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18000ad94  mov     rcx, rbx
0x18000ad97  mov     rbx, [rsp+38h+arg_10]
0x18000ad9c  add     rsp, 30h
0x18000ada0  pop     rdi
0x18000ada1  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VFontFldrTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<FontFldrTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
