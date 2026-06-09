# wil::details::FeatureLogging::Instance(void)

- ea: `0x180006c6c`
- end: `0x180006d51`
- name: `?Instance@FeatureLogging@details@wil@@KAPEAV123@XZ`
- size: `229`
- prototype: `struct wil::details::FeatureLogging *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800051b0`

## callees

- `0x180001950`
- `0x1800025f0`
- `0x180006c6c`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180006c94`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180006c94`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180006d40`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180006d40`

## pseudocode

```c
struct wil::details::FeatureLogging *wil::details::FeatureLogging::Instance(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_180035B20 = 0;
    v2 = &qword_180035B18;
    qword_180035B18 = (__int64)&wil::details::FeatureLogging::`vftable';
    byte_180035B28 = 0;
    dword_180035B2C = 0;
    CallbackContext = &`wil::details::FeatureLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_::_lambda_invoker_cdecl_);
    qword_180035B20 = (__int64)CallbackContext;
    byte_180035B28 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_180035B2C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180035B18 + 8))(&qword_180035B18);
    InitOnceComplete(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &qword_180035B18);
  }
  return (struct wil::details::FeatureLogging *)v2;
}

```

## disassembly

```asm
0x180006c6c  mov     rax, rsp
0x180006c6f  push    rbx
0x180006c70  sub     rsp, 20h
0x180006c74  lea     r9, [rax+10h]; lpContext
0x180006c78  mov     qword ptr [rax+10h], 0
0x180006c80  lea     r8, [rax+8]; fPending
0x180006c84  mov     dword ptr [rax+8], 0
0x180006c8b  xor     edx, edx; dwFlags
0x180006c8d  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x180006c94  call    cs:__imp_InitOnceBeginInitialize
0x180006c9a  test    eax, eax
0x180006c9c  jz      loc_180006D46
0x180006ca2  cmp     [rsp+28h+arg_0], 0
0x180006ca7  jz      loc_180006D46
0x180006cad  lea     rbx, qword_180035B18
0x180006cb4  mov     cs:qword_180035B20, 0
0x180006cbf  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x180006cc6  mov     [rsp+28h+arg_8], rbx
0x180006ccb  mov     cs:qword_180035B18, rax
0x180006cd2  mov     cs:byte_180035B28, 0
0x180006cd9  mov     cs:dword_180035B2C, 0
0x180006ce3  lea     rax, ?__hInner@?1???0StaticHandle@FeatureLogging@details@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::details::FeatureLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180006cea  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_@@CA@XZ; void (__cdecl *)()
0x180006cf1  mov     cs:CallbackContext, rax
0x180006cf8  call    atexit
0x180006cfd  mov     rcx, cs:CallbackContext; CallbackContext
0x180006d04  mov     cs:qword_180035B20, rcx
0x180006d0b  mov     cs:byte_180035B28, 1
0x180006d12  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180006d17  mov     rax, cs:qword_180035B18
0x180006d1e  mov     rcx, rbx
0x180006d21  mov     cs:dword_180035B2C, 1
0x180006d2b  mov     rax, [rax+8]
0x180006d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d34  mov     r8, rbx; lpContext
0x180006d37  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x180006d3e  xor     edx, edx; dwFlags
0x180006d40  call    cs:__imp_InitOnceComplete
0x180006d46  mov     rax, [rsp+28h+arg_8]
0x180006d4b  add     rsp, 20h
0x180006d4f  pop     rbx
0x180006d50  retn
```
