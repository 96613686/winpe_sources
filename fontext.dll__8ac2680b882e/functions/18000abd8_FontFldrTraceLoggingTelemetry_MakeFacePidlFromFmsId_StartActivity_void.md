# FontFldrTraceLoggingTelemetry::_MakeFacePidlFromFmsId::StartActivity(void)

- ea: `0x18000abd8`
- end: `0x18000ac6e`
- name: `?StartActivity@_MakeFacePidlFromFmsId@FontFldrTraceLoggingTelemetry@@QEAAXXZ`
- size: `150`
- prototype: `void __fastcall(FontFldrTraceLoggingTelemetry::_MakeFacePidlFromFmsId *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18000f6b8`

## callees

- `0x180001628`
- `0x180009304`
- `0x180009930`
- `0x18000abd8`
- `0x1800103c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000abf9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000abf9`

## pseudocode

```c
void __fastcall FontFldrTraceLoggingTelemetry::_MakeFacePidlFromFmsId::StartActivity(
        FontFldrTraceLoggingTelemetry::_MakeFacePidlFromFmsId *this)
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
      (unsigned int)byte_18003BC61,
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
0x18000abd8  mov     [rsp+arg_10], rbx
0x18000abdd  push    rdi
0x18000abde  sub     rsp, 30h
0x18000abe2  mov     rbx, rcx
0x18000abe5  call    ?zInternalStart@?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000abea  call    ?Provider@FontFldrTraceLogging@@SAPEBU_tlgProvider_t@@XZ; FontFldrTraceLogging::Provider(void)
0x18000abef  mov     rdi, rax
0x18000abf2  mov     edx, [rax]
0x18000abf4  cmp     edx, 5
0x18000abf7  jbe     short loc_18000AC5C
0x18000abf9  call    cs:__imp_GetCurrentThreadId
0x18000abff  mov     r8, [rbx+110h]
0x18000ac06  mov     [rsp+38h+arg_0], eax
0x18000ac0a  xor     eax, eax
0x18000ac0c  mov     [rsp+38h+arg_8], rax
0x18000ac11  cmp     [r8+4], al
0x18000ac15  jz      short loc_18000AC32
0x18000ac17  lea     r9, [r8+18h]
0x18000ac1b  cmp     [r9], eax
0x18000ac1e  jnz     short loc_18000AC35
0x18000ac20  cmp     [r9+4], eax
0x18000ac24  jnz     short loc_18000AC35
0x18000ac26  cmp     [r9+8], eax
0x18000ac2a  jnz     short loc_18000AC35
0x18000ac2c  cmp     [r9+0Ch], eax
0x18000ac30  jnz     short loc_18000AC35
0x18000ac32  mov     r9, rax
0x18000ac35  lea     rax, [rsp+38h+arg_0]
0x18000ac3a  add     r8, 8
0x18000ac3e  mov     [rsp+38h+var_10], rax
0x18000ac43  lea     rdx, byte_18003BC61
0x18000ac4a  lea     rax, [rsp+38h+arg_8]
0x18000ac4f  mov     rcx, rdi
0x18000ac52  mov     [rsp+38h+var_18], rax
0x18000ac57  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18000ac5c  mov     rcx, rbx
0x18000ac5f  mov     rbx, [rsp+38h+arg_10]
0x18000ac64  add     rsp, 30h
0x18000ac68  pop     rdi
0x18000ac69  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VFontFldrTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<FontFldrTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
