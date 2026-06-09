# wil::details::FeatureLogging::Instance(void)

- ea: `0x1800397dc`
- end: `0x1800398c1`
- name: `?Instance@FeatureLogging@details@wil@@KAPEAV123@XZ`
- size: `229`
- prototype: `struct wil::details::FeatureLogging *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800392f0`

## callees

- `0x180001008`
- `0x180002da4`
- `0x1800397dc`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180039804`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180039804`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800398b0`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800398b0`

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
    qword_180062E58 = 0;
    v2 = &qword_180062E50;
    qword_180062E50 = (__int64)&wil::details::FeatureLogging::`vftable';
    byte_180062E60 = 0;
    dword_180062E64 = 0;
    CallbackContext = &`wil::details::FeatureLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_::_lambda_invoker_cdecl_);
    qword_180062E58 = (__int64)CallbackContext;
    byte_180062E60 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_180062E64 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180062E50 + 8))(&qword_180062E50);
    InitOnceComplete(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &qword_180062E50);
  }
  return (struct wil::details::FeatureLogging *)v2;
}

```

## disassembly

```asm
0x1800397dc  mov     rax, rsp
0x1800397df  push    rbx
0x1800397e0  sub     rsp, 20h
0x1800397e4  lea     r9, [rax+10h]; lpContext
0x1800397e8  mov     qword ptr [rax+10h], 0
0x1800397f0  lea     r8, [rax+8]; fPending
0x1800397f4  mov     dword ptr [rax+8], 0
0x1800397fb  xor     edx, edx; dwFlags
0x1800397fd  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x180039804  call    cs:__imp_InitOnceBeginInitialize
0x18003980a  test    eax, eax
0x18003980c  jz      loc_1800398B6
0x180039812  cmp     [rsp+28h+arg_0], 0
0x180039817  jz      loc_1800398B6
0x18003981d  lea     rbx, qword_180062E50
0x180039824  mov     cs:qword_180062E58, 0
0x18003982f  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x180039836  mov     [rsp+28h+arg_8], rbx
0x18003983b  mov     cs:qword_180062E50, rax
0x180039842  mov     cs:byte_180062E60, 0
0x180039849  mov     cs:dword_180062E64, 0
0x180039853  lea     rax, ?__hInner@?1???0StaticHandle@FeatureLogging@details@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::details::FeatureLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18003985a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_@@CA@XZ; void (__cdecl *)()
0x180039861  mov     cs:CallbackContext, rax
0x180039868  call    atexit
0x18003986d  mov     rcx, cs:CallbackContext; CallbackContext
0x180039874  mov     cs:qword_180062E58, rcx
0x18003987b  mov     cs:byte_180062E60, 1
0x180039882  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180039887  mov     rax, cs:qword_180062E50
0x18003988e  mov     rcx, rbx
0x180039891  mov     cs:dword_180062E64, 1
0x18003989b  mov     rax, [rax+8]
0x18003989f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800398a4  mov     r8, rbx; lpContext
0x1800398a7  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x1800398ae  xor     edx, edx; dwFlags
0x1800398b0  call    cs:__imp_InitOnceComplete
0x1800398b6  mov     rax, [rsp+28h+arg_8]
0x1800398bb  add     rsp, 20h
0x1800398bf  pop     rbx
0x1800398c0  retn
```
