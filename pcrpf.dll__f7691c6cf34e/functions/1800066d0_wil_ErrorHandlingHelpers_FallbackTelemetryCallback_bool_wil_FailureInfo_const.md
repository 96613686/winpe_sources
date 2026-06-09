# wil::ErrorHandlingHelpers::FallbackTelemetryCallback(bool,wil::FailureInfo const &)

- ea: `0x1800066d0`
- end: `0x1800067bc`
- name: `?FallbackTelemetryCallback@ErrorHandlingHelpers@wil@@SAX_NAEBUFailureInfo@2@@Z`
- size: `236`
- prototype: `void __fastcall(char, const struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003620`
- `0x1800066d0`
- `0x1800093c0`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180006706`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180006706`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180006788`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180006788`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ErrorHandlingHelpers::FallbackTelemetryCallback(char a1, const struct wil::FailureInfo *a2)
{
  __int64 v4; // rdx
  void (*v5)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v6; // [rsp+40h] [rbp+18h] BYREF
  LPVOID v7; // [rsp+48h] [rbp+20h] BYREF

  v7 = 0;
  v6 = 0;
  if ( InitOnceBeginInitialize(&`wil::ErrorHandlingHelpers::Instance'::`2'::wrapper, 0, &v6, &v7) && v6 )
  {
    qword_180072A68 = 0;
    v7 = &qword_180072A60;
    qword_180072A60 = &PpfTraceLoggingProvider::`vftable';
    byte_180072A70 = 0;
    dword_180072A74 = 0;
    qword_180072A78 = (struct _tlgProvider_t *)&`wil::ErrorHandlingHelpers::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_8d5ca15cf69e69dee1fdb0dcddeb1e66_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180072A60, qword_180072A78, v5);
    InitOnceComplete(&`wil::ErrorHandlingHelpers::Instance'::`2'::wrapper, 0, &qword_180072A60);
  }
  LOBYTE(v4) = a1;
  (*(void (__fastcall **)(LPVOID, __int64, const struct wil::FailureInfo *))(*(_QWORD *)v7 + 16LL))(v7, v4, a2);
}

```

## disassembly

```asm
0x1800066d0  mov     rax, rsp
0x1800066d3  mov     [rax+8], rbx
0x1800066d7  mov     [rax+10h], rsi
0x1800066db  push    rdi
0x1800066dc  sub     rsp, 20h
0x1800066e0  mov     rbx, rdx
0x1800066e3  mov     qword ptr [rax+20h], 0
0x1800066eb  mov     dil, cl
0x1800066ee  mov     dword ptr [rax+18h], 0
0x1800066f5  xor     edx, edx; dwFlags
0x1800066f7  lea     rcx, ?wrapper@?1??Instance@ErrorHandlingHelpers@wil@@KAPEAV23@XZ@4V?$static_lazy@VErrorHandlingHelpers@wil@@@details@3@A; lpInitOnce
0x1800066fe  lea     r9, [rax+20h]; lpContext
0x180006702  lea     r8, [rax+18h]; fPending
0x180006706  call    cs:__imp_InitOnceBeginInitialize
0x18000670d  nop     dword ptr [rax+rax+00h]
0x180006712  test    eax, eax
0x180006714  jz      short loc_180006794
0x180006716  cmp     [rsp+28h+arg_10], 0
0x18000671b  jz      short loc_180006794
0x18000671d  lea     rsi, qword_180072A60
0x180006724  mov     cs:qword_180072A68, 0
0x18000672f  lea     rax, ??_7PpfTraceLoggingProvider@@6B@; const PpfTraceLoggingProvider::`vftable'
0x180006736  mov     [rsp+28h+arg_18], rsi
0x18000673b  mov     cs:qword_180072A60, rax
0x180006742  mov     cs:byte_180072A70, 0
0x180006749  mov     cs:dword_180072A74, 0
0x180006753  lea     rax, ?__hInner@?1???0StaticHandle@ErrorHandlingHelpers@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::ErrorHandlingHelpers::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000675a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_8d5ca15cf69e69dee1fdb0dcddeb1e66_@@CA@XZ; void (__cdecl *)()
0x180006761  mov     cs:qword_180072A78, rax
0x180006768  call    atexit
0x18000676d  mov     rdx, cs:qword_180072A78; struct _tlgProvider_t *
0x180006774  mov     rcx, rsi; this
0x180006777  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18000677c  mov     r8, rsi; lpContext
0x18000677f  lea     rcx, ?wrapper@?1??Instance@ErrorHandlingHelpers@wil@@KAPEAV23@XZ@4V?$static_lazy@VErrorHandlingHelpers@wil@@@details@3@A; lpInitOnce
0x180006786  xor     edx, edx; dwFlags
0x180006788  call    cs:__imp_InitOnceComplete
0x18000678f  nop     dword ptr [rax+rax+00h]
0x180006794  mov     rcx, [rsp+28h+arg_18]
0x180006799  mov     r8, rbx
0x18000679c  mov     dl, dil
0x18000679f  mov     rax, [rcx]
0x1800067a2  mov     rax, [rax+10h]
0x1800067a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067ab  mov     rbx, [rsp+28h+arg_0]
0x1800067b0  mov     rsi, [rsp+28h+arg_8]
0x1800067b5  add     rsp, 20h
0x1800067b9  pop     rdi
0x1800067ba  retn
```
