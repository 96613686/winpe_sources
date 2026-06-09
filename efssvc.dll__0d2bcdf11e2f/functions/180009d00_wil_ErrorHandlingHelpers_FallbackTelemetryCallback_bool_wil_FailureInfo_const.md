# wil::ErrorHandlingHelpers::FallbackTelemetryCallback(bool,wil::FailureInfo const &)

- ea: `0x180009d00`
- end: `0x180009dec`
- name: `?FallbackTelemetryCallback@ErrorHandlingHelpers@wil@@SAX_NAEBUFailureInfo@2@@Z`
- size: `236`
- prototype: `void __fastcall(bool, const struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002038`
- `0x180009d00`
- `0x18000b04c`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180009db8`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180009db8`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009d36`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009d36`

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
    qword_1800188E8 = 0;
    v7 = &qword_1800188E0;
    qword_1800188E0 = &wil::TraceLoggingProvider::`vftable';
    byte_1800188F0 = 0;
    dword_1800188F4 = 0;
    qword_1800188F8 = (struct _tlgProvider_t *)&`wil::ErrorHandlingHelpers::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_8d5ca15cf69e69dee1fdb0dcddeb1e66_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_1800188E0, qword_1800188F8, v5);
    InitOnceComplete(&`wil::ErrorHandlingHelpers::Instance'::`2'::wrapper, 0, &qword_1800188E0);
  }
  LOBYTE(v4) = a1;
  (*(void (__fastcall **)(LPVOID, __int64, const struct wil::FailureInfo *))(*(_QWORD *)v7 + 16LL))(v7, v4, a2);
}

```

## disassembly

```asm
0x180009d00  mov     rax, rsp
0x180009d03  mov     [rax+8], rbx
0x180009d07  mov     [rax+10h], rsi
0x180009d0b  push    rdi
0x180009d0c  sub     rsp, 20h
0x180009d10  mov     rbx, rdx
0x180009d13  mov     qword ptr [rax+20h], 0
0x180009d1b  mov     dil, cl
0x180009d1e  mov     dword ptr [rax+18h], 0
0x180009d25  xor     edx, edx; dwFlags
0x180009d27  lea     rcx, ?wrapper@?1??Instance@ErrorHandlingHelpers@wil@@KAPEAV23@XZ@4V?$static_lazy@VErrorHandlingHelpers@wil@@@details@3@A; lpInitOnce
0x180009d2e  lea     r9, [rax+20h]; lpContext
0x180009d32  lea     r8, [rax+18h]; fPending
0x180009d36  call    cs:__imp_InitOnceBeginInitialize
0x180009d3d  nop     dword ptr [rax+rax+00h]
0x180009d42  test    eax, eax
0x180009d44  jz      short loc_180009DC4
0x180009d46  cmp     [rsp+28h+arg_10], 0
0x180009d4b  jz      short loc_180009DC4
0x180009d4d  lea     rsi, qword_1800188E0
0x180009d54  mov     cs:qword_1800188E8, 0
0x180009d5f  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x180009d66  mov     [rsp+28h+arg_18], rsi
0x180009d6b  mov     cs:qword_1800188E0, rax
0x180009d72  mov     cs:byte_1800188F0, 0
0x180009d79  mov     cs:dword_1800188F4, 0
0x180009d83  lea     rax, ?__hInner@?1???0StaticHandle@ErrorHandlingHelpers@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::ErrorHandlingHelpers::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180009d8a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_8d5ca15cf69e69dee1fdb0dcddeb1e66_@@CA@XZ; void (__cdecl *)()
0x180009d91  mov     cs:qword_1800188F8, rax
0x180009d98  call    atexit
0x180009d9d  mov     rdx, cs:qword_1800188F8; struct _tlgProvider_t *
0x180009da4  mov     rcx, rsi; this
0x180009da7  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180009dac  mov     r8, rsi; lpContext
0x180009daf  lea     rcx, ?wrapper@?1??Instance@ErrorHandlingHelpers@wil@@KAPEAV23@XZ@4V?$static_lazy@VErrorHandlingHelpers@wil@@@details@3@A; lpInitOnce
0x180009db6  xor     edx, edx; dwFlags
0x180009db8  call    cs:__imp_InitOnceComplete
0x180009dbf  nop     dword ptr [rax+rax+00h]
0x180009dc4  mov     rcx, [rsp+28h+arg_18]
0x180009dc9  mov     r8, rbx
0x180009dcc  mov     dl, dil
0x180009dcf  mov     rax, [rcx]
0x180009dd2  mov     rax, [rax+10h]
0x180009dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ddb  mov     rbx, [rsp+28h+arg_0]
0x180009de0  mov     rsi, [rsp+28h+arg_8]
0x180009de5  add     rsp, 20h
0x180009de9  pop     rdi
0x180009dea  retn
```
