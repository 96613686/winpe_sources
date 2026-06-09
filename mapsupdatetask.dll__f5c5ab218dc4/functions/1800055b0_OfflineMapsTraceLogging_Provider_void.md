# OfflineMapsTraceLogging::Provider(void)

- ea: `0x1800055b0`
- end: `0x180005662`
- name: `?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `178`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004edc`
- `0x180006ee4`
- `0x180007004`

## callees

- `0x180001fd4`
- `0x1800033e8`
- `0x1800055b0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800055db`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800055db`

## pseudocode

```c
const struct _tlgProvider_t *OfflineMapsTraceLogging::Provider(void)
{
  union _RTL_RUN_ONCE *v1; // [rsp+20h] [rbp-18h] BYREF
  int v2; // [rsp+28h] [rbp-10h]
  WINBOOL v3; // [rsp+40h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v3 = 0;
  if ( InitOnceBeginInitialize(&`OfflineMapsTraceLogging::Instance'::`2'::wrapper, 0, &v3, (LPVOID *)&v4) && v3 )
  {
    v1 = &`OfflineMapsTraceLogging::Instance'::`2'::wrapper;
    v4 = &qword_18000E440;
    qword_18000E440 = (__int64)&wil::TraceLoggingProvider::`vftable';
    qword_18000E448 = 0;
    byte_18000E450 = 0;
    dword_18000E454 = 0;
    qword_18000E458 = (__int64)&`OfflineMapsTraceLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_b1920e3fd6e26929e52072737012d5c8_::_lambda_invoker_cdecl_);
    v2 = 0;
    wil::details::static_lazy<OfflineMapsTraceLogging>::Completer::~Completer(&v1);
  }
  return (const struct _tlgProvider_t *)v4[1];
}

```

## disassembly

```asm
0x1800055b0  mov     rax, rsp
0x1800055b3  push    rdi
0x1800055b4  sub     rsp, 30h
0x1800055b8  lea     rdi, ?wrapper@?1??Instance@OfflineMapsTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VOfflineMapsTraceLogging@@@details@wil@@A; wil::details::static_lazy<OfflineMapsTraceLogging> `OfflineMapsTraceLogging::Instance(void)'::`2'::wrapper
0x1800055bf  mov     qword ptr [rax+10h], 0
0x1800055c7  mov     rcx, rdi; lpInitOnce
0x1800055ca  mov     dword ptr [rax+8], 0
0x1800055d1  lea     r9, [rax+10h]; lpContext
0x1800055d5  xor     edx, edx; dwFlags
0x1800055d7  lea     r8, [rax+8]; fPending
0x1800055db  call    cs:__imp_InitOnceBeginInitialize
0x1800055e1  test    eax, eax
0x1800055e3  jz      short loc_180005653
0x1800055e5  cmp     [rsp+38h+arg_0], 0
0x1800055ea  jz      short loc_180005653
0x1800055ec  lea     rax, qword_18000E440
0x1800055f3  mov     [rsp+38h+var_18], rdi
0x1800055f8  mov     [rsp+38h+arg_8], rax
0x1800055fd  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x180005604  mov     cs:qword_18000E440, rax
0x18000560b  mov     cs:qword_18000E448, 0
0x180005616  mov     cs:byte_18000E450, 0
0x18000561d  mov     cs:dword_18000E454, 0
0x180005627  lea     rax, ?__hInner@?1???0StaticHandle@OfflineMapsTraceLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `OfflineMapsTraceLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000562e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_b1920e3fd6e26929e52072737012d5c8_@@CA@XZ; void (__cdecl *)()
0x180005635  mov     cs:qword_18000E458, rax
0x18000563c  call    atexit
0x180005641  lea     rcx, [rsp+38h+var_18]
0x180005646  mov     [rsp+38h+var_10], 0
0x18000564e  call    ??1Completer@?$static_lazy@VOfflineMapsTraceLogging@@@details@wil@@QEAA@XZ; wil::details::static_lazy<OfflineMapsTraceLogging>::Completer::~Completer(void)
0x180005653  mov     rax, [rsp+38h+arg_8]
0x180005658  mov     rax, [rax+8]
0x18000565c  add     rsp, 30h
0x180005660  pop     rdi
0x180005661  retn
```
