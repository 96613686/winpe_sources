# wil::ErrorHandlingHelpers::FallbackTelemetryCallback(bool,wil::FailureInfo const &)

- ea: `0x1800095a0`
- end: `0x18000967f`
- name: `?FallbackTelemetryCallback@ErrorHandlingHelpers@wil@@SAX_NAEBUFailureInfo@2@@Z`
- size: `223`
- prototype: `void __fastcall(char, const struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002028`
- `0x1800095a0`
- `0x18000a5f4`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180009652`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180009652`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800095d6`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800095d6`

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
    qword_1800178E8 = 0;
    v7 = &qword_1800178E0;
    qword_1800178E0 = &wil::TraceLoggingProvider::`vftable';
    byte_1800178F0 = 0;
    dword_1800178F4 = 0;
    qword_1800178F8 = (struct _tlgProvider_t *)&`wil::ErrorHandlingHelpers::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_8d5ca15cf69e69dee1fdb0dcddeb1e66_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_1800178E0, qword_1800178F8, v5);
    InitOnceComplete(&`wil::ErrorHandlingHelpers::Instance'::`2'::wrapper, 0, &qword_1800178E0);
  }
  LOBYTE(v4) = a1;
  (*(void (__fastcall **)(LPVOID, __int64, const struct wil::FailureInfo *))(*(_QWORD *)v7 + 16LL))(v7, v4, a2);
}

```

## disassembly

```asm
0x1800095a0  mov     rax, rsp
0x1800095a3  mov     [rax+8], rbx
0x1800095a7  mov     [rax+10h], rsi
0x1800095ab  push    rdi
0x1800095ac  sub     rsp, 20h
0x1800095b0  mov     rbx, rdx
0x1800095b3  mov     qword ptr [rax+20h], 0
0x1800095bb  mov     dil, cl
0x1800095be  mov     dword ptr [rax+18h], 0
0x1800095c5  xor     edx, edx; dwFlags
0x1800095c7  lea     rcx, ?wrapper@?1??Instance@ErrorHandlingHelpers@wil@@KAPEAV23@XZ@4V?$static_lazy@VErrorHandlingHelpers@wil@@@details@3@A; lpInitOnce
0x1800095ce  lea     r9, [rax+20h]; lpContext
0x1800095d2  lea     r8, [rax+18h]; fPending
0x1800095d6  call    cs:__imp_InitOnceBeginInitialize
0x1800095dc  test    eax, eax
0x1800095de  jz      short loc_180009658
0x1800095e0  cmp     [rsp+28h+arg_10], 0
0x1800095e5  jz      short loc_180009658
0x1800095e7  lea     rsi, qword_1800178E0
0x1800095ee  mov     cs:qword_1800178E8, 0
0x1800095f9  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x180009600  mov     [rsp+28h+arg_18], rsi
0x180009605  mov     cs:qword_1800178E0, rax
0x18000960c  mov     cs:byte_1800178F0, 0
0x180009613  mov     cs:dword_1800178F4, 0
0x18000961d  lea     rax, ?__hInner@?1???0StaticHandle@ErrorHandlingHelpers@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::ErrorHandlingHelpers::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180009624  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_8d5ca15cf69e69dee1fdb0dcddeb1e66_@@CA@XZ; void (__cdecl *)()
0x18000962b  mov     cs:qword_1800178F8, rax
0x180009632  call    atexit
0x180009637  mov     rdx, cs:qword_1800178F8; struct _tlgProvider_t *
0x18000963e  mov     rcx, rsi; this
0x180009641  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180009646  mov     r8, rsi; lpContext
0x180009649  lea     rcx, ?wrapper@?1??Instance@ErrorHandlingHelpers@wil@@KAPEAV23@XZ@4V?$static_lazy@VErrorHandlingHelpers@wil@@@details@3@A; lpInitOnce
0x180009650  xor     edx, edx; dwFlags
0x180009652  call    cs:__imp_InitOnceComplete
0x180009658  mov     rcx, [rsp+28h+arg_18]
0x18000965d  mov     r8, rbx
0x180009660  mov     dl, dil
0x180009663  mov     rax, [rcx]
0x180009666  mov     rax, [rax+10h]
0x18000966a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000966f  mov     rbx, [rsp+28h+arg_0]
0x180009674  mov     rsi, [rsp+28h+arg_8]
0x180009679  add     rsp, 20h
0x18000967d  pop     rdi
0x18000967e  retn
```
