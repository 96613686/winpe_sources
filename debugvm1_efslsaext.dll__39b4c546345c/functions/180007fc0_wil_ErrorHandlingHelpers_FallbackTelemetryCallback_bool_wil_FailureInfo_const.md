# wil::ErrorHandlingHelpers::FallbackTelemetryCallback(bool,wil::FailureInfo const &)

- ea: `0x180007fc0`
- end: `0x18000809f`
- name: `?FallbackTelemetryCallback@ErrorHandlingHelpers@wil@@SAX_NAEBUFailureInfo@2@@Z`
- size: `223`
- prototype: `void __fastcall(bool, const struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001f34`
- `0x180005584`
- `0x180007fc0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008072`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008072`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180007ff6`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180007ff6`

## pseudocode

```c
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
    qword_18001EB00 = 0;
    v7 = &qword_18001EAF8;
    qword_18001EAF8 = &EfsLsaRpcTelemetryProvider::`vftable';
    byte_18001EB08 = 0;
    dword_18001EB0C = 0;
    qword_18001EB10 = (struct _tlgProvider_t *)&`wil::ErrorHandlingHelpers::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_8d5ca15cf69e69dee1fdb0dcddeb1e66_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_18001EAF8, qword_18001EB10, v5);
    InitOnceComplete(&`wil::ErrorHandlingHelpers::Instance'::`2'::wrapper, 0, &qword_18001EAF8);
  }
  LOBYTE(v4) = a1;
  (*(void (__fastcall **)(LPVOID, __int64, const struct wil::FailureInfo *))(*(_QWORD *)v7 + 16LL))(v7, v4, a2);
}

```

## disassembly

```asm
0x180007fc0  mov     rax, rsp
0x180007fc3  mov     [rax+8], rbx
0x180007fc7  mov     [rax+10h], rsi
0x180007fcb  push    rdi
0x180007fcc  sub     rsp, 20h
0x180007fd0  mov     rbx, rdx
0x180007fd3  mov     qword ptr [rax+20h], 0
0x180007fdb  mov     dil, cl
0x180007fde  mov     dword ptr [rax+18h], 0
0x180007fe5  xor     edx, edx; dwFlags
0x180007fe7  lea     rcx, ?wrapper@?1??Instance@ErrorHandlingHelpers@wil@@KAPEAV23@XZ@4V?$static_lazy@VErrorHandlingHelpers@wil@@@details@3@A; lpInitOnce
0x180007fee  lea     r9, [rax+20h]; lpContext
0x180007ff2  lea     r8, [rax+18h]; fPending
0x180007ff6  call    cs:__imp_InitOnceBeginInitialize
0x180007ffc  test    eax, eax
0x180007ffe  jz      short loc_180008078
0x180008000  cmp     [rsp+28h+arg_10], 0
0x180008005  jz      short loc_180008078
0x180008007  lea     rsi, qword_18001EAF8
0x18000800e  mov     cs:qword_18001EB00, 0
0x180008019  lea     rax, ??_7EfsLsaRpcTelemetryProvider@@6B@; const EfsLsaRpcTelemetryProvider::`vftable'
0x180008020  mov     [rsp+28h+arg_18], rsi
0x180008025  mov     cs:qword_18001EAF8, rax
0x18000802c  mov     cs:byte_18001EB08, 0
0x180008033  mov     cs:dword_18001EB0C, 0
0x18000803d  lea     rax, ?__hInner@?1???0StaticHandle@ErrorHandlingHelpers@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::ErrorHandlingHelpers::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180008044  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_8d5ca15cf69e69dee1fdb0dcddeb1e66_@@CA@XZ; void (__cdecl *)()
0x18000804b  mov     cs:qword_18001EB10, rax
0x180008052  call    atexit
0x180008057  mov     rdx, cs:qword_18001EB10; struct _tlgProvider_t *
0x18000805e  mov     rcx, rsi; this
0x180008061  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180008066  mov     r8, rsi; lpContext
0x180008069  lea     rcx, ?wrapper@?1??Instance@ErrorHandlingHelpers@wil@@KAPEAV23@XZ@4V?$static_lazy@VErrorHandlingHelpers@wil@@@details@3@A; lpInitOnce
0x180008070  xor     edx, edx; dwFlags
0x180008072  call    cs:__imp_InitOnceComplete
0x180008078  mov     rcx, [rsp+28h+arg_18]
0x18000807d  mov     r8, rbx
0x180008080  mov     dl, dil
0x180008083  mov     rax, [rcx]
0x180008086  mov     rax, [rax+10h]
0x18000808a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000808f  mov     rbx, [rsp+28h+arg_0]
0x180008094  mov     rsi, [rsp+28h+arg_8]
0x180008099  add     rsp, 20h
0x18000809d  pop     rdi
0x18000809e  retn
```
