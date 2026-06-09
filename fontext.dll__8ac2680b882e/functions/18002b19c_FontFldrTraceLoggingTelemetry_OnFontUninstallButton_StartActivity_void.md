# FontFldrTraceLoggingTelemetry::OnFontUninstallButton::StartActivity(void)

- ea: `0x18002b19c`
- end: `0x18002b253`
- name: `?StartActivity@OnFontUninstallButton@FontFldrTraceLoggingTelemetry@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(FontFldrTraceLoggingTelemetry::OnFontUninstallButton *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18002c100`

## callees

- `0x180001628`
- `0x180001f1c`
- `0x180009304`
- `0x180009930`
- `0x18001ad08`
- `0x18002b19c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b1d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b1d7`

## pseudocode

```c
void __fastcall FontFldrTraceLoggingTelemetry::OnFontUninstallButton::StartActivity(
        FontFldrTraceLoggingTelemetry::OnFontUninstallButton *this)
{
  const struct _tlgProvider_t *v2; // rax
  int v3; // edi
  DWORD CurrentThreadId; // eax
  __int64 v5; // r8
  int v6; // r9d
  DWORD v7; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<FontFldrTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = FontFldrTraceLogging::Provider();
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
      (unsigned int)&unk_18003DCF8,
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
0x18002b19c  mov     [rsp+arg_10], rbx
0x18002b1a1  push    rdi
0x18002b1a2  sub     rsp, 30h
0x18002b1a6  mov     rbx, rcx
0x18002b1a9  call    ?zInternalStart@?$ActivityBase@VFontFldrTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontFldrTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18002b1ae  call    ?Provider@FontFldrTraceLogging@@SAPEBU_tlgProvider_t@@XZ; FontFldrTraceLogging::Provider(void)
0x18002b1b3  mov     rdi, rax
0x18002b1b6  mov     edx, [rax]
0x18002b1b8  cmp     edx, 5
0x18002b1bb  jbe     loc_18002B241
0x18002b1c1  mov     rdx, 200000000000h
0x18002b1cb  mov     rcx, rax
0x18002b1ce  call    _tlgKeywordOn
0x18002b1d3  test    al, al
0x18002b1d5  jz      short loc_18002B241
0x18002b1d7  call    cs:__imp_GetCurrentThreadId
0x18002b1dd  mov     r8, [rbx+110h]
0x18002b1e4  mov     [rsp+38h+arg_0], eax
0x18002b1e8  mov     [rsp+38h+arg_8], 0
0x18002b1f1  cmp     byte ptr [r8+4], 0
0x18002b1f6  jz      short loc_18002B217
0x18002b1f8  lea     r9, [r8+18h]
0x18002b1fc  cmp     dword ptr [r9], 0
0x18002b200  jnz     short loc_18002B21A
0x18002b202  cmp     dword ptr [r9+4], 0
0x18002b207  jnz     short loc_18002B21A
0x18002b209  cmp     dword ptr [r9+8], 0
0x18002b20e  jnz     short loc_18002B21A
0x18002b210  cmp     dword ptr [r9+0Ch], 0
0x18002b215  jnz     short loc_18002B21A
0x18002b217  xor     r9d, r9d
0x18002b21a  lea     rax, [rsp+38h+arg_0]
0x18002b21f  add     r8, 8
0x18002b223  mov     [rsp+38h+var_10], rax
0x18002b228  lea     rdx, unk_18003DCF8
0x18002b22f  lea     rax, [rsp+38h+arg_8]
0x18002b234  mov     rcx, rdi
0x18002b237  mov     [rsp+38h+var_18], rax
0x18002b23c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18002b241  mov     rcx, rbx
0x18002b244  mov     rbx, [rsp+38h+arg_10]
0x18002b249  add     rsp, 30h
0x18002b24d  pop     rdi
0x18002b24e  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VFontFldrTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<FontFldrTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
